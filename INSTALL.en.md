# Install OFFBRIEF

[简体中文](INSTALL.md) · [English](INSTALL.en.md)

Current version: **1.3.0**. Skill identifier and installed directory name: **offbrief**.

OFFBRIEF follows the [Agent Skills directory specification](https://agentskills.io/specification) and uses the host’s model and tools. The skill has no runtime scripts, so it does not require an additional Python or Node.js installation or a separate model API configuration.

## Option 1: ask the host to install it

In an AI tool that supports installing skills and accessing repositories, say:

```text
Install this Agent Skill: https://github.com/ZzzShisi/offbrief
The skill is named offbrief, and SKILL.md is at the repository root.
Use a Skills directory recognized by your environment.
Preserve the relative locations of references/ and assets/.
If an older version is installed, back it up and avoid loading duplicate copies.
Confirm that metadata.version is 1.3.0 after installation.
```

If the host only supports importing a skill archive, use Option 2.

## Option 2: install the dedicated ZIP

Download [OFFBRIEF_v1.3.0.zip](dist/OFFBRIEF_v1.3.0.zip). It contains the skill resources and license.

### WorkBuddy

Provide the archive through your WorkBuddy environment’s supported skill-installation flow. In an environment that supports installation through chat, ask:

```text
Install the attached OFFBRIEF skill.
If an older version exists, back it up and update to version 1.3.0.
Check that offbrief/SKILL.md and its reference resources are present.
```

Refresh the skill or start a new session as required by that environment, then perform the short check below. See [WorkBuddy’s official skill documentation (Chinese)](https://open.workbuddy.cn/docs/skill) for its structure and platform guidance. Follow the requirements of the actual installation interface.

### ZIP layout

The dedicated archive contains:

```text
offbrief/
├── SKILL.md
├── references/
├── assets/
└── LICENSE
```

If your host explicitly requires `SKILL.md` at the ZIP root, extract the archive and compress the contents of `offbrief/` together, keeping their relative structure.

GitHub’s **Code → Download ZIP** downloads the entire repository, including documentation and images. For direct archive import, use the dedicated skill ZIP linked above.

## Option 3: install in a local Codex Skills directory

Codex discovers local skills from `~/.agents/skills` and project `.agents/skills` directories. See the [official skill-discovery and installation guidance](https://learn.chatgpt.com/docs/build-skills#where-codex-loads-local-skills).

The following commands require Git. If the target already contains a skill named `offbrief`, back up and resolve the older copy first. Cloning does not overwrite an existing destination.

### Windows PowerShell

```powershell
git clone "https://github.com/ZzzShisi/offbrief" "$env:USERPROFILE\.agents\skills\offbrief"
```

### macOS / Linux

```bash
git clone "https://github.com/ZzzShisi/offbrief" "$HOME/.agents/skills/offbrief"
```

Alternatively, extract the dedicated ZIP and place the whole `offbrief/` directory under the recognized Skills directory. For one project, use that project’s `.agents/skills/offbrief/`.

If the skill does not appear, restart Codex and check its skill list. Codex CLI supports explicit invocation through `$offbrief`; implicit matching depends on the description, configuration, and context.

## A short check after installation

1. **Check the version.** Confirm `metadata.version` is `1.3.0` in the installed file.
2. **Ask about its capabilities.** It should describe finding directions, making progress, delivering work, and reviewing results.
3. **Try an ongoing task.** “I’m working on ____, and I’m stuck at ____. Help me find another approach.” Look for an option relevant to your constraints.
4. **Try an exact request.** “Correct only these two typos. Don’t add suggestions.” It should stay within the specified edit.

If a natural request does not activate the skill, explicitly select `offbrief` first, then investigate the host’s discovery mechanism. An insight integrated into a deliverable may not have a separate skill heading.

## Updates

If you installed through Git and have no local modifications, enter the actual installed directory and run:

```text
git pull --ff-only
```

If you modified the skill locally, preserve your changes and inspect the differences before updating. For ZIP installations, download the new archive, retain a backup, and use the original host’s replacement flow.

## Tested environments

Version 1.3.0 workflow tests, implicit-discovery observations, and file-delivery checks were conducted in a local Codex environment. The WorkBuddy installation and trial feedback received for 1.2.0 concerns that earlier version. It does not establish automatic loading of 1.3.0 in every WorkBuddy environment. See the [original testing record (Chinese)](docs/TESTING.md).

Official documentation checked on 2026-10-14. The English guide translates the existing installation instructions; it does not add an English-language runtime test claim.
