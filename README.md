# Claude Vulkan Skill

A Claude Code skill that answers Vulkan and MoltenVK questions by referencing locally cloned official repositories, rather than relying solely on training data.

## What it does

When you ask anything about Vulkan, MoltenVK, graphics programming, GPU APIs, render passes, pipelines, synchronization, extensions, validation layers, or Metal interop, this skill directs Claude to consult local reference repos first. This ensures answers reflect the actual spec and source rather than potentially outdated training knowledge.

### Reference repos included

| Repo | Purpose |
|------|---------|
| `references/Vulkan-Docs` | Official Vulkan spec and reference pages |
| `references/Vulkan-Headers` | `vulkan.h`, `vk_platform.h`, extension headers |
| `references/Vulkan-Guide` | Best practices and conceptual guides |
| `references/MoltenVK` | MoltenVK source and Metal interop |

## Installation

Clone with `--recurse-submodules` — the reference repos are git submodules:

```bash
git clone --recurse-submodules <repo-url> ~/.claude/skills/vulkan
```

If you already cloned without submodules, initialize them after:

```bash
git submodule update --init --recursive
```

## Usage

Once installed, Claude will automatically use this skill whenever you ask Vulkan-related questions in a session where the skill is available. Claude will grep and read from the local reference repos and cite which file the answer comes from.
