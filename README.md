# iOS Design Stack

A design-to-code pipeline for iOS apps using AI agents. Not a skill collection — a workflow.

## The Pipeline

```
Pencil MCP → Design Philosophy → XcodeBuildMCP → Ralph Loop
  (create)    (review/filter)      (validate)     (iterate)
```

1. **Pencil MCP** — agent designs on canvas, exports real SwiftUI code
2. **Design Philosophy** — reviews for taste, filters AI slop, enforces "less but better"
3. **XcodeBuildMCP** — builds, runs in simulator, captures screenshots
4. **Ralph Loop** — if it doesn't pass taste or build checks, loop back to step 1
5. **MotionEyes** — traces real animation values when debugging motion

## Install

```bash
# As a Claude Code skill
cp -r skills/* ~/.claude/skills/

# Or use the full collection (200+ skills with auto-routing)
git clone https://github.com/JordanCoin/ios-skills-collection
claude plugins add ios-skills-collection
```

## Usage

```bash
/ios-design-stack "Design a login screen for iOS.
Requirements:
- Follow Apple HIG
- Clean, minimal, premium feel
- Accessible (Dynamic Type, VoiceOver)
- Dark mode support"
```

Or invoke the pipeline steps manually:

```
1. Read skills/pencil-mcp/SKILL.md — design on canvas
2. Read skills/design-philosophy/SKILL.md — review for taste
3. Use XcodeBuildMCP to build + screenshot
4. Use Ralph Loop to iterate until taste + build both pass
5. Use MotionEyes if animations need debugging
```

## What's in This Repo

| File | What it is |
|------|-----------|
| `SKILL.md` | The pipeline orchestrator — loads when invoked |
| `skills/pencil-mcp/` | Original: Pencil.dev MCP integration guide |
| `skills/design-philosophy/` | Original: Dieter Rams principles, taste building |

## External Dependencies

These tools are used by the pipeline but maintained in their own repos:

| Tool | Source | Purpose |
|------|--------|---------|
| XcodeBuildMCP | [getsentry/XcodeBuildMCP](https://github.com/getsentry/XcodeBuildMCP) | Build, run, screenshot |
| Ralph Loop | [anthropics/claude-code](https://github.com/anthropics/claude-code) | Autonomous iteration |
| MotionEyes | [edwardsanchez/MotionEyes](https://github.com/edwardsanchez/MotionEyes) | Animation debugging |
| Xcode Previews | [Iron-Ham/XcodePreviews](https://github.com/Iron-Ham/XcodePreviews) | Visual preview capture |
| ASO Skills | [Eronred/aso-skills](https://github.com/Eronred/aso-skills) | App Store Optimization |

## Full Collection

This repo is the focused design pipeline. For the complete set of 200+ iOS/Swift/Xcode
skills with auto-routing hooks, see [ios-skills-collection](https://github.com/JordanCoin/ios-skills-collection).

## Requirements

- Claude Code or compatible agent
- Pencil.dev account (for Pencil MCP)
- Xcode 15+ (for XcodeBuildMCP)
- XcodeBuildMCP installed

## License

MIT
