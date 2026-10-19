# Taggart

**Qualquer agente, harness original.**

Taggart é uma ADE (agentic development environment) open source para macOS. Ela roda Claude Code, Codex, Gemini CLI e qualquer outro agente de terminal do jeito que eles são, num terminal real, e organiza o trabalho em volta: tasks, worktrees, contexto compartilhado, review e entrega.

> Status: em design. Nada para instalar ainda.

## Princípios

- **Harness original:** nunca reimplementa o agente; abre o CLI num PTY.
- **Qualquer agente:** todo CLI que roda em terminal entra; hooks deixam a integração mais rica.
- **Local-first, zero telemetria:** nada sai da máquina além do que os próprios CLIs enviam.
- **Minimalista:** o terminal no centro, o resto só quando precisa.

## Como funciona

- **Task** é o objeto central: vem de uma issue (Linear, GitHub), sessão livre, card ou goal.
- Cada task ganha um **worktree** com branch própria e um ou mais agentes.
- Um **daemon** segura as sessões; fechar o app não mata nenhum agente.
- Quatro abas sobre os mesmos dados: **Foco**, **Grid**, **Board**, **Review**.

## Stack

Tauri + xterm.js no app, daemon em Rust com os PTYs, worktrees e tasks (SQLite).

## Roadmap

1. **v0.1 · Dia 1:** daemon, Task + worktree, aba Foco, claude/codex/gemini, status via hooks.
2. **v0.2 · Contexto:** instruções unificadas, spec por task, memória via MCP, handoff, review, PR/CI, gates.
3. **v0.3 · Escala:** abas Grid e Board, Linear e GitHub, supervisor para goals, acesso remoto.
4. **v1 · Empresas:** audit log, políticas centrais, config de time.

Mantido por [AIFBR](https://github.com/aifbr). Licença [Apache-2.0](LICENSE).
