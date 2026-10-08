## Invaris Labs

**Security infrastructure for autonomous AI agents.**

AI agents read untrusted data, call tools, keep memory, hand work to other agents and take real actions. One poisoned document or tool response can make an agent leak secrets, call a tool it shouldn't, or do something that can't be undone. Invaris Labs builds open-source tools to **test** agents for that kind of behaviour and to give them **verifiable identity and limited authority**.

[Website](https://invaris-labs.pages.dev/) · [Writing](https://arunima-chaudhuri.hashnode.dev) · [X](https://x.com/InvarisLabs) · [LinkedIn](https://www.linkedin.com/company/invarislabs)

---

### Projects

#### 🛡️ [AgentSec](https://github.com/invarislabs/invaris-agentsec): adversarial testing for AI agents

Runs stateful attack scenarios against complete agent workflows (LLMs, retrieval, memory, MCP servers, tools and sensitive actions), records the execution trace, and checks that your security policy held the whole way through.

- **What it tests:** direct and indirect prompt injection, tool-output and MCP poisoning, unsafe retrieved documents, memory poisoning, unauthorized tool use, dangerous tool chains, secret leakage, loops and budget overruns, deceptive action reports, multi-agent privilege abuse, and regressions across models and prompts
- **MCP scanning:** poisoned tool descriptions, tool shadowing and rug pulls
- **Standards:** findings map to the OWASP Top 10 for Agentic Applications (ASI01–ASI10)
- **CI-first:** CLI, pytest plugin and GitHub Action, with reports in terminal, JSON, HTML, Markdown and SARIF
- **Local by default:** no traces leave your machine

```bash
pip install invaris-agentsec
agentsec init   # scaffold an agentsec.yaml policy
agentsec test   # run the suite
```

#### 🔑 [AgentAuth](https://github.com/invarislabs/agent-auth): identity and delegated authority for AI agents

Gives each agent a self-certifying DID backed by an Ed25519 keypair. The agent signs every request, so no API key or bearer token ever crosses the wire.

- **Scoped capability grants:** short-lived permissions that can only narrow, never widen, when passed down to sub-agents, and every action traces back to the person who authorized it
- **Limits:** spend, rate, use and resource limits, enforced across the whole delegation chain
- **Control:** revocation that cascades, kill switches, and key rotation with pre-rotation
- **Tooling:** CLI, Python SDK and FastAPI integration

---

### Writing

- **[What Does a Passing Agent Security Test Actually Prove?](https://arunima-chaudhuri.hashnode.dev/what-does-a-passing-agent-security-test-actually-prove)** (Oct 2026)  
  Five ways an agent can pass a security test without resisting anything, drawn from AgentSec runs against seven frameworks, two memory stores and the Claude Code CLI.
- **[Allowed Isn't Authorized: Testing What Your AI Agent Does With the Permissions It Already Has](https://arunima-chaudhuri.hashnode.dev/allowed-isn-t-authorized-testing-what-your-ai-agent-does-with-the-permissions-it-already-has)** (Oct 2026)  
  A hands-on guide to AgentSec 0.7's authority checks: task scope, data flow, honest reporting, identity boundaries and multi-agent delegation.
- **[AgentSec 101: How to Stop Your AI Agent From Going Rogue](https://arunima-chaudhuri.hashnode.dev/agentsec-101-how-to-stop-your-ai-agent-from-going-rogue-a-beginner-to-pro-guide)** (Sep 2026)  
  A beginner-to-pro walkthrough: install, test the bundled practice agent, write a policy, then replay, compare, CI and the optional judge.
- **[I Asked My Coding Agent for a Yes or No. It Made a Commit.](https://arunima-chaudhuri.hashnode.dev/i-asked-my-coding-agent-for-a-yes-or-no-it-made-a-commit)** (Sep 2026)  
  The origin story behind AgentSec.

More at [arunima-chaudhuri.hashnode.dev](https://arunima-chaudhuri.hashnode.dev).

---

### Get involved

We're looking for **design partners** and **contributors**. Useful places to start:

- adversarial test cases and attack packs
- framework adapters
- MCP security testing
- documentation

Open an issue or PR on either repo, or reach out at **arunimachaudhuri2020@gmail.com**.

---

<sub>Founded by [Arunima Chaudhuri](https://github.com/tinniaru3005) ([LinkedIn](https://www.linkedin.com/in/arunima-chaudhuri)).</sub>
