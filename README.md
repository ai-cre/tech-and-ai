# Claude Rule Enforcer (CRE)

**Security guardrails for AI coding assistants. Stop your agent from doing stupid things.**

Your AI coding agent can run any command on your machine. Delete files. Push code. Wipe databases. The only thing stopping it is a text file it can ignore whenever it wants.

**CRE blocks dangerous actions before they execute. The AI cannot bypass it.**

## What it does

```
AI tries:  rm -rf /
CRE:       BLOCKED. Recursive delete.

AI tries:  git push --force
CRE:       BLOCKED. Force push.

AI tries:  ssh server2 "dangerous command"
CRE:       BLOCKED. Evasion detected.

AI tries:  echo hello
CRE:       allowed.
```

## Two layers

- **L1 (regex):** Instant pattern matching. Blocks rm -rf, force push, fork bombs, remote evasion. Sub-10ms. No API key needed.
- **L2 (LLM):** Advisory intent checking. Reads conversation context, checks if the user actually asked for this. Configurable model (MiniMax, GPT, GLM).

## Works with

Claude Code, Cursor, Windsurf, Copilot, Codex, OpenClaw, Amp.

## Install

```bash
curl -fsSL https://ai-cre.uk/install.sh | bash
```

One command. Dashboard at `localhost:8766`. L1 enforcement ready.

## Links

- **Website:** [ai-cre.uk](https://ai-cre.uk)
- **Contact:** leo@data4u.uk

## License

Business Source License 1.1
