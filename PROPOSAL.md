# RSM: Reason's Swiss-cheese Model Implementation Proposal

## Applying "Multi-Agent Models of Organizational Intelligence" to Build a Reliable Multi-Agent Framework

**Paper Reference:** Vijayaraghavan et al., "If You Want Coherence, Orchestrate a Team of Rivals: Multi-Agent Models of Organizational Intelligence" (arXiv:2601.14351, January 2026)

---

## 1. Executive Summary

This proposal outlines the design and implementation of **RSM** (Reason's Swiss-cheese Model) — an open-source multi-agent orchestration framework that implements the organizational intelligence patterns described in the referenced paper. The core insight: **reliability emerges not from perfect components, but from careful orchestration of imperfect ones through opposing incentives and cascaded critique layers.**

RSM will provide a reusable framework for building multi-agent systems where specialized agents (planners, executors, critics, responders) operate within a stage-gated organizational structure, achieving >90% error interception before outputs reach users.

### Key Goals

- Implement the **Team of Rivals** pattern with asymmetric veto authority
- Build a **cascaded critique system** inspired by Reason's Swiss Cheese Model
- Separate **reasoning from execution** via remote code execution
- Provide **FSM-based orchestration** with checkpointing and time-travel
- Enable **context isolation** preventing LLM context contamination
- Ship as a **composable Python framework** usable across domains

---

## 2. Paper Analysis: Core Concepts to Implement

### 2.1 Three Orchestration Patterns (Paper Table 1)

The paper identifies three multi-agent patterns of increasing sophistication:

| Pattern | Error Detection | User Exposure | Cost |
|---------|----------------|---------------|------|
| **Tool Chaining** (sequential) | Self-review only | Direct | Lowest |
| **Sub-Agent Parallelization** (fan-out) | Parent aggregates | Conflicts undetected | Medium |
| **Organizational Council** (stage-gated) | Cascaded critics | Approved outputs only | Highest |

**RSM implements Pattern 3** — the Organizational Council — as its primary mode, with the ability to fall back to simpler patterns when cost/latency constraints require it.

### 2.2 Agent Taxonomy (50+ Roles in Paper)

The paper describes eight agent categories:

1. **Planners** — Parse queries, retrieve context, construct execution DAGs, enforce guardrails, pre-declare acceptance criteria
2. **Executors** — Orchestrate plan execution, route to specialists, manage iterative refinement
3. **Data Writers** — Source-specific code generation (SQL, Python, APIs) with unified abstractions
4. **Critics** — Domain-specialized validators with independent veto authority (code, output, chart, plan)
5. **Responders** — User-facing approval/escalation/clarification handling
6. **Summarizers** — Distill intermediate results for context minimization
7. **SME Experts** — Domain-specific guidance (financial, visualization, reconciliation)
8. **Coordinators** — Manage orchestration routing and handoffs

### 2.3 Cascaded Critique (Swiss Cheese Model)

Three-layer error interception:

```
Layer 0: Clean pass (24.9% of sessions need no critique)
Layer 1: Inner-loop critics — Code (86% catch rate), Chart (1.8%)
Layer 2: Outer-loop critic — Output validation (14.6% catch of escapees)
Residual: 7.9% reaches users (ambiguity, subjectivity, edge cases)
```

**Combined: 92.1% success rate** from imperfect components with misaligned failure modes.

### 2.4 Key Design Principles

- **Asymmetric veto authority**: One "no" from the right critic stops work; unanimous approval advances it
- **Context isolation**: Reasoning models never see raw data; only schemas, summaries, sample rows
- **Structured message passing**: Pydantic-validated messages, not free-text; type-safe inter-agent boundaries
- **Checkpointing**: Full state serialization at decision points; pause/resume/time-travel
- **Adaptive model allocation**: Junior models for routine work; senior models on critique failure
- **Pre-declared acceptance criteria**: Success criteria defined before execution, not post-hoc

---

## 3. Proposed Architecture

### 3.1 High-Level System Design

```
┌─────────────────────────────────────────────────────────┐
│                     USER INTERFACE                        │
│                  (CLI / API / Web SDK)                    │
└──────────────────────┬──────────────────────────────────┘
                       │
┌──────────────────────▼──────────────────────────────────┐
│                   COORDINATOR LAYER                       │
│  ┌──────────┐  ┌───────────┐  ┌───────────────────┐     │
│  │ Router   │  │ FSM Engine│  │ Checkpoint Manager│     │
│  └──────────┘  └───────────┘  └───────────────────┘     │
└──────────────────────┬──────────────────────────────────┘
                       │
┌──────────────────────▼──────────────────────────────────┐
│                   PLANNING STAGE                          │
│  ┌──────────┐  ┌───────────┐  ┌──────────┐             │
│  │ Planner  │  │ Retriever │  │ Plan     │             │
│  │ Agent    │  │ Agent     │  │ Critic   │             │
│  └──────────┘  └───────────┘  └──────────┘             │
│                       │                                   │
│              ┌────────▼────────┐                         │
│              │ Execution DAG   │                         │
│              │ + Acceptance    │                         │
│              │   Criteria      │                         │
│              └─────────────────┘                         │
└──────────────────────┬──────────────────────────────────┘
                       │ (User Approval Gate)
┌──────────────────────▼──────────────────────────────────┐
│                  EXECUTION STAGE                          │
│  ┌──────────────────────────────────────────────┐       │
│  │         INNER LOOP TEAM (per DAG node)        │       │
│  │  ┌────────┐  ┌──────────┐  ┌──────────────┐ │       │
│  │  │ Writer │→ │ Executor │→ │ Code Critic  │ │       │
│  │  │ Agent  │  │ (Sandbox)│  │ (Veto Auth)  │ │       │
│  │  └────────┘  └──────────┘  └──────────────┘ │       │
│  │       ↑          │              │ reject     │       │
│  │       └──────────┘──────────────┘            │       │
│  └──────────────────────────────────────────────┘       │
│                       │ approve                           │
│  ┌────────────┐  ┌────▼───────┐                         │
│  │ Summarizer │← │ Results    │                         │
│  └────────────┘  └────────────┘                         │
└──────────────────────┬──────────────────────────────────┘
                       │
┌──────────────────────▼──────────────────────────────────┐
│                 VALIDATION STAGE                          │
│  ┌──────────────┐  ┌───────────────┐                    │
│  │ Output Critic │  │ Domain Expert │                    │
│  │ (Outer Loop)  │  │ (Optional SME)│                    │
│  └──────────────┘  └───────────────┘                    │
│         │ reject → re-execute (no replan)                 │
│         │ approve → respond                               │
└──────────────────────┬──────────────────────────────────┘
                       │
┌──────────────────────▼──────────────────────────────────┐
│                  RESPONSE STAGE                           │
│  ┌───────────┐  ┌──────────────┐  ┌──────────────┐     │
│  │ Responder │  │ Session Log  │  │ Memory Store │     │
│  └───────────┘  └──────────────┘  └──────────────┘     │
└─────────────────────────────────────────────────────────┘
```

### 3.2 FSM State Machine

The orchestration engine uses a finite state machine with these states:

```
INTAKE → PLANNING → PLAN_REVIEW → EXECUTION → INNER_CRITIQUE
   ↑                     │              ↑            │
   │                     │ reject       │   approve  │ reject
   │                     ↓              │            ↓
   │               USER_CLARIFY    SUMMARIZE    RETRY_WRITE
   │                                    │
   │                              OUTER_CRITIQUE
   │                                    │
   │                              ┌─────┴─────┐
   │                          approve      reject
   │                              │            │
   │                          RESPONSE    RE_EXECUTE
   │                              │
   └──────────────────── COMPLETE/ESCALATE
```

Each transition is logged, checkpointed, and auditable.

### 3.3 Message Protocol

All inter-agent communication uses structured, validated messages:

```python
class AgentMessage(BaseModel):
    """Pydantic-validated structured message between agents."""
    id: UUID
    timestamp: datetime
    source_agent: AgentRole
    target_agent: AgentRole
    fsm_state: FSMState
    message_type: MessageType  # request, response, critique, escalation
    payload: dict[str, Any]
    acceptance_criteria: list[AcceptanceCriterion] | None
    context_scope: ContextScope  # controls visibility (ray tracing)
    parent_message_id: UUID | None
    checkpoint_id: UUID | None
```

---

## 4. Component Design

### 4.1 Module Structure

```
rsm/
├── pyproject.toml
├── README.md
├── PROPOSAL.md
│
├── src/
│   └── rsm/
│       ├── __init__.py
│       ├── core/                    # Core orchestration
│       │   ├── __init__.py
│       │   ├── fsm.py              # Finite state machine engine
│       │   ├── coordinator.py      # Top-level coordinator
│       │   ├── router.py           # Task classification & routing
│       │   ├── checkpoint.py       # State serialization & time-travel
│       │   └── session.py          # Session management & logging
│       │
│       ├── agents/                  # Agent implementations
│       │   ├── __init__.py
│       │   ├── base.py             # Base agent protocol & registry
│       │   ├── planner.py          # Planning agents
│       │   ├── writer.py           # Code/content generation agents
│       │   ├── executor.py         # Sandboxed execution agents
│       │   ├── critic.py           # Critique agents (code, output, plan)
│       │   ├── summarizer.py       # Context compression agents
│       │   ├── responder.py        # User-facing response agents
│       │   └── expert.py           # Domain SME agents
│       │
│       ├── messages/                # Structured communication
│       │   ├── __init__.py
│       │   ├── protocol.py         # Message types & validation
│       │   ├── bus.py              # Message bus / event system
│       │   └── visibility.py       # Context ray tracing / scoping
│       │
│       ├── execution/               # Isolated execution layer
│       │   ├── __init__.py
│       │   ├── sandbox.py          # Sandboxed code execution
│       │   ├── primitives.py       # 50+ transformation primitives
│       │   └── isolation.py        # Context isolation & summarization
│       │
│       ├── critique/                # Cascaded critique system
│       │   ├── __init__.py
│       │   ├── cascade.py          # Swiss cheese cascade orchestration
│       │   ├── code_critic.py      # Syntax, logic, security validation
│       │   ├── output_critic.py    # Acceptance criteria validation
│       │   ├── plan_critic.py      # DAG soundness validation
│       │   └── veto.py             # Asymmetric veto authority logic
│       │
│       ├── planning/                # Plan construction
│       │   ├── __init__.py
│       │   ├── dag.py              # Execution DAG construction
│       │   ├── acceptance.py       # Pre-declared acceptance criteria
│       │   └── retriever.py        # Context retrieval (memory/metadata)
│       │
│       ├── memory/                  # Persistence & recall
│       │   ├── __init__.py
│       │   ├── store.py            # PostgreSQL + pgvector memory
│       │   ├── semantic.py         # Semantic search across sessions
│       │   └── session_log.py      # Event-sourced audit trail
│       │
│       ├── models/                  # LLM provider abstraction
│       │   ├── __init__.py
│       │   ├── provider.py         # Multi-provider interface
│       │   ├── allocation.py       # Model tier allocation strategy
│       │   └── fallback.py         # Cross-provider fallback
│       │
│       └── config/                  # Configuration
│           ├── __init__.py
│           ├── settings.py         # Global settings (Pydantic Settings)
│           └── teams.py            # Team composition definitions
│
├── tests/
│   ├── unit/
│   │   ├── test_fsm.py
│   │   ├── test_agents.py
│   │   ├── test_critique.py
│   │   ├── test_messages.py
│   │   ├── test_execution.py
│   │   └── test_checkpoint.py
│   ├── integration/
│   │   ├── test_cascade.py
│   │   ├── test_inner_loop.py
│   │   └── test_end_to_end.py
│   └── conftest.py
│
└── examples/
    ├── financial_reconciliation/    # Paper's reference task
    ├── code_review/                 # Code review pipeline
    └── data_analysis/               # General data analysis
```

### 4.2 Core Components

#### 4.2.1 FSM Engine (`core/fsm.py`)

The heart of RSM. Manages state transitions, enforces valid paths, and emits events.

```python
class FSMState(str, Enum):
    INTAKE = "intake"
    PLANNING = "planning"
    PLAN_REVIEW = "plan_review"
    USER_APPROVAL = "user_approval"
    EXECUTION = "execution"
    INNER_CRITIQUE = "inner_critique"
    RETRY_WRITE = "retry_write"
    SUMMARIZE = "summarize"
    OUTER_CRITIQUE = "outer_critique"
    RE_EXECUTE = "re_execute"
    RESPONSE = "response"
    ESCALATION = "escalation"
    COMPLETE = "complete"

class FSMTransition(BaseModel):
    from_state: FSMState
    to_state: FSMState
    condition: str  # human-readable guard condition
    guard: Callable[[AgentMessage], bool]

class OrchestrationFSM:
    """Finite state machine governing agent coordination."""

    def __init__(self, transitions: list[FSMTransition]):
        self._state = FSMState.INTAKE
        self._transitions = self._build_transition_map(transitions)
        self._history: list[FSMTransition] = []

    async def advance(self, message: AgentMessage) -> FSMState:
        """Attempt state transition based on incoming message."""
        ...

    def checkpoint(self) -> Checkpoint:
        """Serialize complete FSM state for persistence."""
        ...

    def restore(self, checkpoint: Checkpoint) -> None:
        """Restore FSM from a checkpoint (time-travel)."""
        ...
```

#### 4.2.2 Base Agent Protocol (`agents/base.py`)

All agents implement a common protocol, enabling composition and registry-based instantiation.

```python
class AgentRole(str, Enum):
    PLANNER = "planner"
    WRITER = "writer"
    EXECUTOR = "executor"
    CODE_CRITIC = "code_critic"
    OUTPUT_CRITIC = "output_critic"
    PLAN_CRITIC = "plan_critic"
    SUMMARIZER = "summarizer"
    RESPONDER = "responder"
    EXPERT = "expert"
    COORDINATOR = "coordinator"

class AgentTier(str, Enum):
    """Model capability tier for adaptive allocation."""
    JUNIOR = "junior"      # Fast, economical (routine generation)
    STANDARD = "standard"  # Balanced (most tasks)
    SENIOR = "senior"      # Most capable (complex critique, escalation)

class BaseAgent(Protocol):
    """Protocol all RSM agents must implement."""
    role: AgentRole
    tier: AgentTier

    async def process(self, message: AgentMessage) -> AgentMessage:
        """Process an incoming message and produce a response."""
        ...

    async def can_handle(self, message: AgentMessage) -> bool:
        """Whether this agent can handle the given message."""
        ...

_AGENT_REGISTRY: dict[AgentRole, type[BaseAgent]] = {}

def register_agent(role: AgentRole):
    """Decorator to register agent implementations."""
    def decorator(cls):
        _AGENT_REGISTRY[role] = cls
        return cls
    return decorator
```

#### 4.2.3 Cascaded Critique (`critique/cascade.py`)

Implements the Swiss Cheese Model — multiple imperfect layers with misaligned failure modes.

```python
class CriticVerdict(str, Enum):
    APPROVE = "approve"
    REJECT = "reject"
    ESCALATE = "escalate"

class CriticResult(BaseModel):
    verdict: CriticVerdict
    critic_role: AgentRole
    reasoning: str
    issues: list[str]
    severity: Literal["low", "medium", "high", "critical"]
    retry_hints: list[str]  # guidance for the writer on retry

class CascadedCritique:
    """
    Swiss Cheese Model implementation.

    Multiple imperfect layers of defense where misaligned failure modes
    prevent errors from propagating to users.

    Layer 1 (Inner Loop): Code Critic — syntax, logic, security
    Layer 2 (Inner Loop): Domain Critic — visualization, format standards
    Layer 3 (Outer Loop): Output Critic — acceptance criteria validation
    """

    def __init__(
        self,
        inner_critics: list[BaseAgent],  # Layer 1-2
        outer_critics: list[BaseAgent],  # Layer 3
        max_inner_retries: int = 5,
        max_outer_retries: int = 2,
    ):
        self.inner_critics = inner_critics
        self.outer_critics = outer_critics
        self.max_inner_retries = max_inner_retries
        self.max_outer_retries = max_outer_retries

    async def run_inner_loop(
        self,
        writer: BaseAgent,
        executor: BaseAgent,
        task: AgentMessage,
    ) -> tuple[AgentMessage, list[CriticResult]]:
        """
        Writer → Executor → Critics loop.
        On rejection: retry with critic feedback (no replanning).
        On persistent failure: escalate to senior model or user.
        """
        ...

    async def run_outer_loop(
        self,
        result: AgentMessage,
        acceptance_criteria: list[AcceptanceCriterion],
    ) -> tuple[AgentMessage, list[CriticResult]]:
        """
        Validate final output against pre-declared acceptance criteria.
        Rejection triggers re-execution (not replanning).
        """
        ...
```

#### 4.2.4 Execution Sandbox (`execution/sandbox.py`)

Separation of reasoning from execution — agents write code, the sandbox runs it.

```python
class ExecutionResult(BaseModel):
    """Result from sandboxed code execution."""
    success: bool
    stdout: str
    stderr: str
    return_value: Any | None
    summary: DataSummary  # schemas, stats, sample rows — NOT raw data
    execution_time_ms: float
    lineage: list[LineageRecord]  # column-level provenance

class DataSummary(BaseModel):
    """Compact representation of results for agent context."""
    schema: dict[str, str]        # column → type
    row_count: int
    sample_rows: list[dict]       # first N rows
    statistics: dict[str, Any]    # means, quartiles, counts
    outliers: list[dict] | None
    # Raw data NEVER enters this model

class ExecutionSandbox:
    """
    Isolated execution environment.

    Core principle: reasoning models (brains) never directly touch
    raw data or tool outputs. They write code; this sandbox runs it.
    Only summaries return to agent context.
    """

    async def execute(self, code: str, context: ExecutionContext) -> ExecutionResult:
        """Execute code in isolated environment, return summary only."""
        ...

    async def execute_dag_node(
        self, node: DAGNode, inputs: dict[str, DataSummary]
    ) -> ExecutionResult:
        """Execute a single DAG node with its dependencies resolved."""
        ...
```

#### 4.2.5 Checkpoint & Time-Travel (`core/checkpoint.py`)

```python
class Checkpoint(BaseModel):
    """Complete serialized state at a decision point."""
    id: UUID
    timestamp: datetime
    fsm_state: FSMState
    agent_states: dict[AgentRole, dict]
    message_history: list[AgentMessage]
    execution_results: dict[UUID, ExecutionResult]
    dag_progress: dict[str, NodeStatus]
    metadata: dict[str, Any]

class CheckpointManager:
    """Enables pause/resume and time-travel to any decision point."""

    async def save(self, session_id: UUID, checkpoint: Checkpoint) -> None: ...
    async def load(self, checkpoint_id: UUID) -> Checkpoint: ...
    async def list_checkpoints(self, session_id: UUID) -> list[Checkpoint]: ...
    async def rollback(self, checkpoint_id: UUID) -> OrchestrationFSM: ...
```

#### 4.2.6 Model Allocation (`models/allocation.py`)

Adaptive model selection based on task difficulty and retry count.

```python
class ModelAllocationStrategy:
    """
    Adaptive model allocation per the paper's strategy:
    - Junior models handle routine generation
    - Standard models for most tasks
    - Senior models engage on critique failure or escalation
    - Cross-provider fallback for resilience
    """

    def select_model(
        self,
        role: AgentRole,
        retry_count: int = 0,
        task_complexity: float = 0.5,
    ) -> ModelConfig:
        """
        Select model tier based on role and context.

        Writers start junior, upgrade on critique rejection.
        Critics always run at standard or senior tier.
        Escalations always use senior tier.
        """
        ...
```

---

## 5. Technology Stack

| Layer | Technology | Rationale |
|-------|-----------|-----------|
| **Language** | Python 3.12+ | Ecosystem maturity, LLM library support |
| **Async Runtime** | asyncio + anyio | Agent concurrency, I/O parallelism |
| **Data Validation** | Pydantic v2 | Structured message passing (paper requirement) |
| **LLM Providers** | litellm / provider SDKs | Multi-provider abstraction, fallback |
| **Execution Sandbox** | Docker / subprocess isolation | Context isolation, security |
| **Memory Store** | PostgreSQL + pgvector | Semantic search, session persistence |
| **Message Bus** | In-process async (phase 1), Redis Streams (phase 2) | Agent communication |
| **DAG Engine** | NetworkX + custom scheduler | Execution plan modeling |
| **Config** | Pydantic Settings + YAML | Team composition, model allocation |
| **Testing** | pytest + pytest-asyncio | Unit, integration, property tests |
| **Build** | uv + pyproject.toml | Modern Python packaging |
| **Observability** | structlog + OpenTelemetry | Structured logging, tracing |

---

## 6. Implementation Roadmap

### Phase 1: Core Framework (Foundation)

**Goal:** Minimal viable orchestration loop — one writer, one critic, one executor.

1. Project scaffolding (pyproject.toml, src layout, CI)
2. Message protocol with Pydantic validation
3. Base agent protocol and registry
4. FSM engine with basic state transitions
5. Simple writer agent (code generation)
6. Execution sandbox (subprocess-based)
7. Code critic agent (syntax + logic validation)
8. Single inner loop: Writer → Executor → Critic → Retry
9. CLI entry point for testing

**Deliverable:** A working inner loop that generates code, executes it, and iterates on critic feedback.

### Phase 2: Planning & DAGs

**Goal:** Add planning layer with DAG construction and acceptance criteria.

1. Planner agent with DAG construction
2. Plan critic agent (DAG soundness validation)
3. Pre-declared acceptance criteria system
4. User approval gate (CLI-based)
5. Retriever agent for context gathering
6. DAG executor (sequential + parallel node execution)

**Deliverable:** Full planning → approval → execution pipeline for multi-step tasks.

### Phase 3: Cascaded Critique & Organizational Council

**Goal:** Implement the full Swiss Cheese Model and Team of Rivals.

1. Output critic (outer loop against acceptance criteria)
2. Cascaded critique orchestration (inner + outer loops)
3. Asymmetric veto authority implementation
4. Escalation paths (retry → senior model → user)
5. Adaptive model allocation (junior/standard/senior tiers)
6. Summarizer agents for context minimization
7. Cross-provider model fallback

**Deliverable:** Full organizational council with >90% error interception target.

### Phase 4: Persistence & Memory

**Goal:** Add state persistence, checkpointing, and semantic memory.

1. Checkpoint manager with full state serialization
2. Time-travel (rollback to any checkpoint)
3. Session logging (event-sourced audit trail)
4. PostgreSQL + pgvector memory store
5. Semantic search across prior sessions
6. Session pause/resume capability

**Deliverable:** Persistent, auditable sessions with time-travel debugging.

### Phase 5: Extensibility & Production Readiness

**Goal:** Make the framework composable and production-grade.

1. Plugin system for custom agents and critics
2. Domain expert agent framework
3. Transformation primitives library (50+ operations)
4. Data source connectors (CSV, SQL, APIs)
5. Web API (FastAPI) for programmatic access
6. OpenTelemetry integration for observability
7. Cost tracking and attribution per session
8. Comprehensive documentation and examples

**Deliverable:** Production-ready framework with extensible architecture.

---

## 7. Key Design Decisions

### 7.1 Why Asymmetric Veto (Not Voting)

The paper demonstrates that democratic voting among agents degrades accuracy. Self-verification actually made single agents *worse* (accuracy dropped below 60% baseline). Instead:

- Critics hold **independent veto authority** — one rejection blocks advancement
- Approval requires **unanimous consent** from all relevant critics
- This prevents "groupthink" and consensus-seeking that masks errors

### 7.2 Why Separate Reasoning from Execution

The paper shows that when LLMs see raw data in their context window:
- Context gets contaminated with irrelevant details
- Working set is limited to context window size
- Models hallucinate patterns in noisy data

RSM enforces: agents write code → sandbox executes → only summaries return.

### 7.3 Why Pre-Declared Acceptance Criteria

Post-hoc evaluation allows goal-post shifting. The paper's approach:
1. Planner declares success criteria **before** execution
2. Output critic validates **against those criteria** (not vibes)
3. This makes critique objective and reproducible

### 7.4 Why Structured Messages (Not Free Text)

The paper treats inter-agent communication as a noisy channel (Shannon's theorem). Pydantic-validated structured messages:
- Eliminate parsing ambiguity
- Enforce type-safe boundaries
- Enable visibility filtering (context ray tracing)
- Make the system auditable

---

## 8. Success Metrics

Drawing from the paper's evaluation methodology:

| Metric | Target | Paper Baseline |
|--------|--------|----------------|
| Error interception rate | >90% | 92.1% |
| Inner-loop catch rate | >80% | 86.0% |
| First-pass success rate | >20% | 24.9% |
| Recovery within 2 retries | >35% | 40.1% (157/392) |
| Compute overhead for recovery | <45% | 38.6% |
| Residual user rejection | <10% | 7.9% |

---

## 9. Example: Financial Reconciliation (Paper Reference Task)

The paper's evaluation task — reconciling 9 PDF invoices against QuickBooks data — serves as our reference implementation:

```
User Query: "Reconcile these invoices against our QuickBooks expenses.
             Flag any discrepancies."

RSM Execution:
  1. PLANNING:
     - Planner constructs 8-step DAG:
       Steps 1-3: Extract data from 3 vendor PDFs (parallel)
       Step 4: Parse QuickBooks export
       Step 5: Consolidate invoice line items
       Step 6: Standardize vendor names (fuzzy matching, ≥0.85)
       Step 7: Run reconciliation logic (±$0.01 tolerance, ±7 days)
       Step 8: Generate discrepancy report
     - Acceptance criteria: "Identify all discrepancies >$0.01
       between invoice totals and QuickBooks entries"

  2. USER APPROVAL: Plan presented for sign-off

  3. EXECUTION (per DAG node):
     Inner Loop:
       Writer generates extraction code →
       Sandbox executes →
       Code Critic validates (catches invoice_number parse error) →
       Writer retries with critic feedback →
       Code Critic approves →
       Summarizer compresses results

  4. OUTER CRITIQUE:
     Output Critic validates: "Found $40 discrepancy in cloud
     vendor — matches acceptance criteria" → APPROVE

  5. RESPONSE: Structured report with citations to source documents
```

---

## 10. Risks and Mitigations

| Risk | Impact | Mitigation |
|------|--------|------------|
| LLM cost escalation from retries | High compute bills | Adaptive model tiers; junior models first; cost caps per session |
| Latency from sequential critique | Poor user experience | Parallel inner-loop critics; async DAG execution; strategic routing |
| Critic false positives | Unnecessary retries, wasted compute | Track false positive rates; tune critic thresholds; escalation limits |
| Context window limits | Incomplete agent reasoning | Summarizer agents; context isolation; chunked processing |
| Provider outages | System unavailability | Cross-provider fallback; checkpoint-based recovery |
| Scope creep in agent interactions | Infinite retry loops | Max retry limits per layer; cost budgets; forced escalation |

---

## 11. Open Questions for Discussion

1. **Language choice**: Python is proposed for ecosystem compatibility. Should we consider Rust/Go for the orchestration core with Python for agent logic?
2. **Execution sandbox**: Docker containers vs. subprocess isolation vs. WASM? Trade-offs between security, startup time, and complexity.
3. **Initial domain focus**: The paper validates on financial reconciliation. Should RSM ship domain-agnostic first, or with a reference domain?
4. **Memory backend**: PostgreSQL + pgvector is proven but heavy. SQLite + local embeddings for development?
5. **MCP integration**: Should RSM expose tools via the Model Context Protocol for interop with existing agent frameworks?

---

## 12. Conclusion

RSM implements the paper's central thesis: **coherence emerges not from perfect models, but from opposing forces holding outputs within acceptable boundaries.** By building the Team of Rivals pattern, cascaded Swiss Cheese critique, and strict reasoning/execution separation as a reusable framework, RSM makes organizational intelligence accessible beyond the paper's specific financial reconciliation domain.

The phased roadmap ensures each increment is independently valuable — Phase 1 alone delivers a working inner-loop critique system that improves any code-generation pipeline's reliability.

---

*Proposal generated from analysis of arXiv:2601.14351 — "If You Want Coherence, Orchestrate a Team of Rivals: Multi-Agent Models of Organizational Intelligence" (Vijayaraghavan et al., 2026)*
