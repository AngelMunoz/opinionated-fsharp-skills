# Authoring rules for skills in this repo

Each skill is one folder under `skills/` with a `SKILL.md` and, when needed, `scripts/`,
`references/`, or `assets/` subfolders.

- Set `name` to the directory name. Use 1-64 lowercase letters, digits, or hyphens. No
  consecutive, leading, or trailing hyphens.
- Write a `description` of 1-1024 characters. State what the skill does and when to use it.
  The description is the trigger; when in doubt, list more user phrasings, not fewer.
- Keep each completed `SKILL.md` below 500 lines. Move detail into linked files under
  `references/`.
- Use relative links for supporting files, and for sibling skills
  (`../fsharp-env-capabilities/SKILL.md`). They stay valid while skills sit side by side,
  in this repo and after co-installation.
- Ship a proof: a `scripts/run.ps1` that builds or runs the shapes the skill prescribes and
  fails on a wrong result. It must run clean from the skill root on .NET 10 and PowerShell
  7.2 or later.
- Never commit build output. `bin/` and `obj/` are ignored by the root `.gitignore`.
