# Prasanna Kumar Popuri

**SDE 3.** I build **AI agents and MCP tools that fail closed** — typed contracts, shadow mode, human-in-the-loop, audit. Not chatbots with a REST call behind the prompt.

[![lattice-mcp](https://img.shields.io/github/stars/popuripk/lattice-mcp?style=flat&label=lattice-mcp)](https://github.com/popuripk/lattice-mcp)
[![forge-agent](https://img.shields.io/github/stars/popuripk/forge-agent?style=flat&label=forge-agent)](https://github.com/popuripk/forge-agent)

Production background: distributed systems (Amazon L5), enterprise platforms, **MCP tool governance**, multi-agent orchestration. Hyderabad.

## Lattice — agent stack

A set of small, serious libraries. Each repo clones, tests, and demos **without an API key**.

```
   ┌─────────────┐     ┌──────────────────┐     ┌─────────────────┐
   │ forge-agent │────►│   lattice-mcp    │────►│  domain MCP     │
   │ atlas       │     │  policy kernel   │     │  ewm · self-svc │
   └─────────────┘     │  shadow · HITL   │     └─────────────────┘
          │            │  audit · schema  │
          ▼            └──────────────────┘
   lattice-eval              ▲
   golden traces             │
                       lattice-memory
```

| Repo | What it is |
|---|---|
| [**lattice-mcp**](https://github.com/popuripk/lattice-mcp) | Policy kernel for MCP tools. Shadow / live / autonomous. Deny lists. Approval. Audit. |
| [**lattice-mcp-py**](https://github.com/popuripk/lattice-mcp-py) | The same gateway in Python. Zero deps. |
| [**forge-agent**](https://github.com/popuripk/forge-agent) | Agent loop you can read. Scripted model for CI. OpenAI-compatible when you want a network. |
| [**atlas-orchestrator**](https://github.com/popuripk/atlas-orchestrator) | Multi-agent planner + specialists on a **blackboard**. No hidden agent-to-agent RPC. |
| [**lattice-eval**](https://github.com/popuripk/lattice-eval) | Contract tests. If a write fires in shadow mode, CI goes red. |
| [**lattice-memory**](https://github.com/popuripk/lattice-memory) | Knowledge-graph memory: remember / relate / recall / search. File-backed. |
| [**ewm-ops-mcp**](https://github.com/popuripk/ewm-ops-mcp) | Warehouse-ops MCP. Overdue tasks, blocked deliveries, SoD on goods issue. |
| [**self-service-mcp**](https://github.com/popuripk/self-service-mcp) | Workplace MCP. Directory, time off, tickets. Compensation is structurally denied. |

## Opinions the code enforces

1. **The model is not the security boundary.** Policy runs before the handler.
2. **Writes are planned, then approved.** Shadow mode never mutates, even with `approve=true`.
3. **Denied tools stay registered.** Hidden capabilities surprise you. Explicit denials teach the agent *and* the eval harness.
4. **Evals should not need a live LLM.** Script the loop. Assert the trace types. Gate the merge.

## Elsewhere

- LinkedIn: [prasanna-kumar-popuri](https://linkedin.com/in/prasanna-kumar-popuri)
- Email: popuripk@gmail.com
