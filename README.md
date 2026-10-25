# opinionated-fsharp-skills

Opinionated F# agent skills in the [Agent Skills format](https://agentskills.io). Install with
the [skills CLI](https://github.com/vercel-labs/skills), which supports Claude Code, Codex,
Cursor, opencode, ZCode, and 75 more agents.

## Install

```bash
npx skills add AngelMunoz/opinionated-fsharp-skills
```

List before installing:

```bash
npx skills add AngelMunoz/opinionated-fsharp-skills --list
```

## Skills

| Skill | What it does |
| --- | --- |
| fsharp-module-shape | One `.fs` file per service group: interfaces first, `module private Helpers`, one module per interface, plain implementation functions, and a `create` factory that returns an object expression. |
| fsharp-function-parameters | Tupled arguments by default, curried only by design, three parameters or fewer with `env` counted, one contextual object (`FnArgs` record) past three, and `InlineIfLambda` callbacks on inline functions only. |

Each skill carries a proof you can run from its folder:

```powershell
pwsh ./scripts/run.ps1
```

## Requirements

- .NET 10 SDK and PowerShell 7.2 or later, for the proof scripts.
- The scripts run `dotnet build`, `dotnet run`, and `dotnet fsi` only. They write inside their
  own skill folder.

## Related skills

Both skills link to siblings from [TheAngryByrd/fsharp-skills](https://github.com/TheAngryByrd/fsharp-skills):
`fsharp-env-capabilities`, `fsharp-signature-files`, and `fsharp-iwsam-errors`. The links are
relative paths such as `../fsharp-env-capabilities/SKILL.md`.

The Agent Skills format has no dependency field. The links resolve when both repos are
installed into the same skills directory of the same agent, because the CLI places each skill
folder side by side. Install both:

```bash
npx skills add TheAngryByrd/fsharp-skills
npx skills add AngelMunoz/opinionated-fsharp-skills
```

When you install a single skill with `--skill`, or install the two repos for different agents,
the sibling links dangle. The skills still work; only the cross-links point nowhere.

## Authoring

See [skills/README.md](skills/README.md) for the folder rules each skill must follow.
