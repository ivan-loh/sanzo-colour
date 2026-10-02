# Sanzo Colours

A small [Agent Skill](https://agentskills.io) for choosing and applying Sanzo Wada's colour combinations in design-focused coding work.

It pairs the original colour dataset with guidance for retrieving real combinations, assigning design roles, preserving exact values, and checking readable pairings. No dependencies, scripts or network access are required once downloaded.

## Install

Once the repository files are published, install through the [Skills CLI](https://github.com/vercel-labs/skills):

```sh
npx skills add ivan-loh/sanzo-colour --skill sanzo-colours
```

The installer lets you choose supported agents, including Codex, Claude Code, Cursor and OpenCode. Node.js/npm are needed for this installer, not for the skill itself.

For a global installation targeting Codex and Claude Code:

```sh
npx skills add ivan-loh/sanzo-colour --skill sanzo-colours --global --agent codex claude-code
```

Alternatively, copy all five files into a folder named `sanzo-colours` in your agent's skills directory:

- **Codex:** `~/.agents/skills/sanzo-colours/`
- **Claude Code:** `~/.claude/skills/sanzo-colours/`
- **Other agents:** use their documented Agent Skills directory.

Keep all bundled files together. The JSON is a reference for the agent to read with its available file tools; this package does not include a palette generator.

For a manual Codex installation from GitHub:

```sh
mkdir -p ~/.agents/skills
git clone https://github.com/ivan-loh/sanzo-colour.git ~/.agents/skills/sanzo-colours
```

The GitHub repository name is `sanzo-colour`; the installed skill name is `sanzo-colours`. Use the installed folder name shown above so it matches the skill's metadata. Restart your agent session if newly installed skills are not discovered immediately.

This repository follows the [Agent Skills specification](https://agentskills.io/specification): `SKILL.md` at the root, standard YAML frontmatter, and relative resource paths. No agent-specific tool names or plugin manifests are required. Agents without native skill support can read `SKILL.md` directly when given access to all bundled files.

## Use

Ask your agent:

> Use Sanzo Colours to choose a palette for a small contemporary ceramics exhibition website. Give the original combination ID, exact colour names and hex values, and suggest their roles in the design.

Or ask for a specific lookup:

> Use Sanzo Colours to show the original colours in combination 1.

Combination 1 contains **English Red `#d96629`** and **Cerulian Blue `#0093a5`**. To reconstruct a combination, collect every colour whose `combinations` array contains its ID.

## Contents

| File | Purpose |
|---|---|
| [SKILL.md](SKILL.md) | Instructions loaded by the agent |
| [colors.json](colors.json) | 159 colours describing 348 combinations |
| [LICENSE.upstream.md](LICENSE.upstream.md) | Original dataset licence |
| [LICENSE](LICENSE) | MIT licence for the original skill guidance and documentation |

## Source and limitations

The dataset comes from [Matt DesLauriers' dictionary-of-colour-combinations](https://github.com/mattdesl/dictionary-of-colour-combinations), building on Dain M. Blodorn Kim's digitisation of Sanzo Wada's *A Dictionary of Colour Combinations*. The unchanged snapshot is pinned to [`c142bd0`](https://github.com/mattdesl/dictionary-of-colour-combinations/tree/c142bd0bc8049ea48db4da5eb397981f047e8ef4), retrieved 2026-10-02.

Its 348 combinations comprise 120 pairs, 120 triples and 108 quadruples. Screen hex values are converted from print colours and may differ from physical swatches. Mood labels and proposed UI roles are interpretations, not source metadata. Original combinations do not guarantee accessible text contrast; any added neutrals or derived shades should be labelled separately.

This is an independent skill, with no claim of affiliation with Sanzo Wada's publisher or the dataset authors. The upstream MIT copyright notice is preserved in `LICENSE.upstream.md`.
