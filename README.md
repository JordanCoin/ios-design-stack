# iOS Design Stack

Autonomous iOS design pipeline. Give it a prompt, it designs iOS screens in Pencil MCP,
reviews for taste, builds with XcodeBuildMCP, and iterates until done.

## Usage

```
/ios-design-stack "Design a login screen for iOS.
Requirements:
- Follow Apple HIG
- Clean, minimal, premium feel
- Accessible (Dynamic Type, VoiceOver)
- Dark mode support"
```

## The Pipeline

```
SETUP → DESIGN → REVIEW → BUILD → VERIFY → ITERATE → DONE
```

1. **Setup** — loads iOS design tokens (SF Pro type scale, semantic colors, 8pt grid)
2. **Design** — creates screen in Pencil MCP with Apple HIG compliance
3. **Review** — taste-checks against Design Philosophy (Dieter Rams principles)
4. **Build** — exports to SwiftUI, builds with XcodeBuildMCP, screenshots
5. **Verify** — checks spacing, touch targets, typography, colors, safe areas
6. **Iterate** — fixes issues, loops until all checks pass

## With Ralph Loop (fully autonomous)

```
/ralph-loop "Run /ios-design-stack: Design a settings screen for a fitness app.
Dark mode, SF Pro, minimal. Output <promise>DESIGN_COMPLETE</promise> when done."
```

Ralph keeps iterating until the design passes every check. Typical: 3-5 iterations.

## Install

```bash
# As a Claude Code skill (copy skills to your project)
cp -r skills/* .claude/skills/

# Or install as plugin
claude plugins add .
```

## Skills

| Skill | What |
|-------|------|
| `design-philosophy` | Taste principles — Dieter Rams, "less but better" |
| `ios-design-tokens` | iOS HIG tokens — SF Pro, semantic colors, 8pt grid, radii |
| `pencil-ios-design` | iOS Pencil MCP workflow — screen patterns, layout rules |

## Requirements

- Pencil.dev MCP server (design canvas)
- XcodeBuildMCP (optional — for build validation)
- Ralph Loop plugin (optional — for autonomous iteration)

## Full Collection

For 200+ iOS/Swift/Xcode skills beyond design, see
[ios-skills-collection](https://github.com/JordanCoin/ios-skills-collection).

## License

MIT
