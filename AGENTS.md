---
name: "Uber Flake"
description: "Opinionated Nix flake template with dev tools built in"
category: "Template / DevOps"
author: "ACME OSS Team"
tags: ["nix", "flake", "template"]
lastUpdated: "2025-06-18"
---

# AGENTS.md – Contract for Autonomous Coding Agents

> **If you are an LLM-powered agent** (Copilot coding-agent, ChatGPT Codex, Devin, Zencoder, etc.) **you MUST follow every rule below for every file you touch**. Violations will cause CI to fail and your PR to be closed.

---

## 0. Scope & Precedence
| Level | File path | Applies to | Priority |
|-------|-----------|-----------|----------|
| 1 | `system/user prompt` | Current session | 🥇 |
| 2 | Nearest `AGENTS.md` | Folder subtree | 🥈 |
| 3 | Repo-root `AGENTS.md` | Whole repo | 🥉 |
| 4 | `~/.codex/AGENTS.md` or `~/.codex/instructions.md` | Global user prefs | 🏅 |

---

## 1. Project Capsule
A minimal template to bootstrap Nix-based projects using flake-parts, treefmt and pre-commit hooks.
Use `nix flake init --template github:jmmaloney4/uber-flake` to get started.

---

## 2. Directory Contract
<small>(Update this table whenever paths change.)</small>

| Path | Intent | Touch policy |
|------|--------|--------------|
| `/` | Flake definition | **Modifiable** |
| `/default` | Template files | **Modifiable** |

---

## 3. Tech Stack & Runtime
| Tool | Version | Install |
|------|---------|---------|
| Nixpkgs | `nixos-unstable` | via flake input |
| treefmt | unspecified | managed by flake |

---

## 4. Coding Conventions
* **Language**: Nix expressions only.
* **Style**: `treefmt` with `alejandra` for formatting.
* **Comments**: Provide context for any non-obvious Nix constructs.

---

## 5. Testing Strategy
* TODO: define automated tests.

---

## 6. Build & Run Recipes
```bash
nix develop         # enter dev shell
nix run .#fmt       # format the repo
nix flake check     # sanity checks
```

---

## Programmatic Checks
Run the commands below before every commit and ensure they succeed:
```bash
nix run .#fmt
nix flake check
```
