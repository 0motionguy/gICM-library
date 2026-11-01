# gICM Library

A library of agent, skill, command, MCP and settings files for AI-assisted Web3 development with Claude Code.

This is the plain-files side of the [gICM](https://github.com/0motionguy/gICM) marketplace: Markdown and JSON that you copy into a project's `.claude/` folder, with no code to run. The set leans towards Solana and EVM work (Anchor, Hardhat, Foundry, Uniswap, Chainlink, subgraphs) and also covers general backend, DevOps, testing and performance topics. The hub repo holds a newer and larger copy of this content under `.claude/`.

## What it does

- **68 subagents** in `agents/`: Markdown with YAML frontmatter (`name`, `description`, `tools`, `model`) and role, expertise and workflow sections, for example `icm-anchor-architect`, `solana-guardian-auditor` and `smart-contract-auditor`.
- **92 skills** in `skills/`: 87 folders with a `SKILL.md` and 5 single-file skills, written as a short quick reference that expands into deeper sections.
- **93 slash-command docs** in `commands/`, such as `/deploy-hardhat`, `/audit-security`, `/gas-report` and `/test-gen`.
- **82 MCP server entries** in `mcp/`: 66 JSON configs with environment-variable placeholders, 41 per-server READMEs and a few index files.
- **48 settings docs** in `settings/`, grouped into development, integration, monitoring, optimization, performance and security.

All counts come from the file tree.

## How it's built

Plain Markdown with YAML frontmatter, plus JSON for MCP configs. There is no build step, no dependency and no test suite; `package.json` holds metadata only. Skills use a progressive-disclosure layout: a quick reference first, then sections you can load when needed.

## Repository layout

- `agents/`: one Markdown file per subagent
- `skills/`: one folder per skill (`SKILL.md`), plus a few single-file skills
- `commands/`: one Markdown file per slash command, with `COMMANDS_SUMMARY.md`
- `mcp/`: `<name>.json` configs, `<name>-README.md` guides and index files
- `settings/`: settings docs in six category folders

## Use it

```bash
# one agent, one skill, one command
cp agents/icm-anchor-architect.md <your-project>/.claude/agents/
cp -r skills/solana-anchor-mastery <your-project>/.claude/skills/
cp commands/deploy-hardhat.md <your-project>/.claude/commands/
```

For an MCP server, open `mcp/<name>.json`, merge its `mcpServers` entry into your MCP settings and fill in the environment variables it lists (for example `ALCHEMY_API_KEY` for `alchemy.json`).

## Status

Beta. A content snapshot from November 2025 (one commit). Much of it was generated with Claude Code, as the previous README noted, and the files have not been tested one by one against the tools they describe, so review MCP configs and deploy commands before you use them.
