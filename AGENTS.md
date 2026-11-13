# Repository Guidelines

## 本项目开发约定

0. **文档先行**：引入库或框架前，先用 Context7 查对应版本的官方文档，避免使用过时的 API 和写法。
1. **测试先行**：每一小块，先把验收场景写成会失败的测试，再写实现；测试全绿才算完成。
2. **规模上限**：函数不超过 50 行，单文件不超过 300 行；超了就拆。

## Project Structure & Module Organization

This repository is currently a documentation-first project:

```text
.
├── AGENTS.md
├── IDEAS.md
└── .agents/skills/ideas-md/SKILL.md
```

- `IDEAS.md` is the project scope baseline for the first version.
- `.agents/skills/ideas-md/SKILL.md` defines how Codex creates and maintains that ledger.
- Application source, tests, and assets are not scaffolded yet. When adding them, update this guide with their directories and ownership boundaries.

## Build, Test, and Development Commands

No package manifest or build system exists yet. Do not assume npm, Cargo, Python, or another toolchain is available.

For current documentation changes, inspect the files directly:

```powershell
Get-Content -Raw -Encoding UTF8 IDEAS.md
Get-Content -Raw -Encoding UTF8 .agents/skills/ideas-md/SKILL.md
```

When the desktop application is introduced, add the exact install, development, build, and test commands for its chosen toolchain to this section.

## Coding Style & Naming Conventions

- Store files as UTF-8 and use Markdown headings to communicate structure.
- Keep `SKILL.md` frontmatter valid; its `name` must remain `ideas-md` and match the skill directory.
- Preserve the exact `IDEAS.md` headings and their order: `# IDEAS`, `## 第一版要做`, then `## 暂不做`.
- Keep explanations short and evidence-based. Do not add implementation plans to `IDEAS.md`.
- When code is added, define its formatter, linter, indentation, and naming rules here before enforcing them.

## Testing Guidelines

There is no automated test suite yet. For documentation-only changes, verify UTF-8 readability, required headings, section order, and links. Test the `ideas-md` workflow against realistic create and update cases when changing that skill.

Once code exists, document the test framework, coverage expectation, test naming pattern, and exact commands here.

## Scope & Agent Instructions

Read `IDEAS.md` before requirement clarification and treat it as the current-version range baseline. New ideas belong in `暂不做` unless the user explicitly includes them in the first version. Do not place full requirements, implementation details, or `AGENTS.md` conventions into `IDEAS.md`.

Use `.agents/skills/ideas-md/SKILL.md` whenever request work changes project scope decisions.

## Commit & Pull Request Guidelines

Git history is not available in this workspace, so no historical convention can be inferred. Use small, focused commits with imperative subjects, for example `docs: add repository guidelines`.

Pull requests should explain the changed behavior or documentation, summarize validation performed, and link relevant issues. Include screenshots when the desktop UI is added; never include secrets or machine-specific paths.
