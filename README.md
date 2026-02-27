# iOS Design Stack

A production-grade design-to-code pipeline for iOS apps using AI agents.

## The Stack

| Layer | Tool | Purpose |
|-------|------|---------|
| **Taste** | Design Philosophy | Sets quality bar, prevents AI slop |
| **Design** | Pencil.dev + MCP | Canvas design → SwiftUI code |
| **Build** | XcodeBuildMCP | Compile, run, screenshot, validate |
| **Iterate** | Ralph Loop | Autonomous iteration until complete |
| **Debug** | MotionEyes | Trace real animation values from logs |

## How It Works

```
Design Philosophy → Pencil MCP → XcodeBuildMCP → Ralph Loop
     (taste)         (design)      (validate)     (iterate)
```

1. **Design Philosophy** filters for taste before any work starts
2. **Pencil MCP** lets agent design on canvas and export real SwiftUI
3. **XcodeBuildMCP** builds, runs in simulator, captures screenshots
4. **Ralph Loop** catches exit attempts, re-feeds prompt until done

## Quick Start

```bash
# Install skills
npx openskills install ios-design-stack

# Or manually copy to your skills directory
cp -r skills/* ~/.openclaw/skills/
```

## Usage with Ralph

```bash
/ralph-loop "Design a login screen for iOS. 
Requirements:
- Follow Apple HIG
- Clean, minimal, premium feel
- Accessible (Dynamic Type, VoiceOver)
- Dark mode support

Use Pencil MCP to design, XcodeBuildMCP to validate.
Output <promise>COMPLETE</promise> when:
- Design matches philosophy guidelines
- Code compiles without warnings
- Screenshot looks correct" --max-iterations 20
```

## Skills Included

- `design-philosophy/` — Taste and design thinking
- `pencil-mcp/` — Pencil.dev MCP integration
- `ralph-loop/` — Autonomous iteration pattern

## Requirements

- Claude Code or compatible agent
- Pencil.dev account (for Pencil MCP)
- Xcode 15+ (for XcodeBuildMCP)
- XcodeBuildMCP CLI installed

## License

MIT
