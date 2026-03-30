---
name: ios-design-stack
description: >
  Design-to-code pipeline for iOS apps. Orchestrates: canvas design (Pencil MCP),
  taste review (Design Philosophy), build validation (XcodeBuildMCP), autonomous
  iteration (Ralph Loop), and animation debugging (MotionEyes). Use when designing
  iOS UI from scratch, iterating on visual quality, or running a full
  design-build-validate cycle.
---

# iOS Design Stack

Production-grade design-to-code pipeline for iOS. Not a skill collection — a workflow
that chains skills in the right order.

## The Pipeline

```
1. DESIGN      → Pencil MCP (canvas design → real SwiftUI export)
2. REVIEW      → Design Philosophy (taste filter — does this earn its place?)
3. BUILD       → XcodeBuildMCP (compile, run in simulator, screenshot)
4. ITERATE     → Ralph Loop (loop back to step 1 until taste + build pass)
5. DEBUG       → MotionEyes (trace real animation values if motion feels off)
```

Design first. Then critique. Then validate. Then iterate until it's right.

## Step 1: Design — Pencil MCP

Create the UI on canvas. The agent draws real components, not mockups.

- Open or create a `.pen` file with `open_document`
- Get design guidelines with `get_guidelines(topic=mobile-app)`
- Get a style guide with `get_style_guide` for design inspiration
- Design components with `batch_design`
- Export as SwiftUI code

Load the full skill: `skills/pencil-mcp/SKILL.md`

Requires: Pencil.dev account + MCP server configured.

## Step 2: Review — Design Philosophy

Now critique what you just designed. Apply these filters:

- **What's the one feeling this should create?** If you can't answer in one word, redesign.
- **What would Steve Jobs remove?** If you can't find anything to cut, you haven't looked.
- **Does every element earn its place?** If removing it changes nothing, remove it.
- **Dieter Rams #10: "As little design as possible."**

This is the gate. If the design doesn't pass taste, go back to Step 1.
Don't build something that isn't good enough yet.

Load the full skill: `skills/design-philosophy/SKILL.md`

## Step 3: Build — XcodeBuildMCP

The design passed taste review. Now validate it compiles and renders correctly.

```
1. Build the project: xcodebuild or swift build
2. Run in simulator: boot + install + launch
3. Capture screenshot: compare to design intent from Pencil
4. Check for warnings: zero warnings target
```

Skill source: [getsentry/XcodeBuildMCP](https://github.com/getsentry/XcodeBuildMCP)

## Step 4: Iterate — Ralph Loop

If the screenshot doesn't match the design, or taste review fails, loop back.
Ralph catches premature exits and re-feeds the prompt until success criteria are met.

```
/ralph-loop "Fix the [specific issue] in [specific file].
Success criteria:
- Design matches Pencil canvas intent
- Passes Design Philosophy taste check
- Code compiles without warnings
- Screenshot looks correct
Output <promise>COMPLETE</promise> when done." --max-iterations 10
```

The loop goes: design → review → build → screenshot → compare → fix → repeat.

Skill source: [anthropics/claude-code/plugins/ralph-wiggum](https://github.com/anthropics/claude-code)

## Step 5: Debug — MotionEyes (if needed)

When animations don't feel right, don't guess — instrument and measure.

MotionEyes adds temporary logging to SwiftUI views that traces real motion values
(position, opacity, scale) over time. Read the logs, compare to intent, fix.

Skill source: [edwardsanchez/MotionEyes](https://github.com/edwardsanchez/MotionEyes)

## Full Pipeline Example

```
User: "Design a login screen for my fitness app"

Agent:
1. [design] Opens Pencil MCP, gets mobile-app guidelines + style guide
2. [design] Designs login screen on canvas — email, password, submit, logo
3. [review] Taste check: "Clean, trustworthy, premium" — passes
4. [review] Would Apple ship this? The forgot-password link is cluttering. Remove it,
            add it to a secondary flow. Back to Pencil to simplify.
5. [design] Simplified version — just email, password, submit. Cleaner.
6. [review] Passes taste. "Less, but better."
7. [build] Exports SwiftUI, builds project, runs in simulator
8. [build] Screenshots — button alignment is off by 4px
9. [iterate] Ralph loop fixes alignment, re-screenshots
10. [build] Looks correct. Zero warnings. Done.
```

## Standalone Skills

These two skills are original to this repo and can be used independently:

- `skills/pencil-mcp/` — Pencil.dev MCP integration guide
- `skills/design-philosophy/` — Taste and design thinking (Dieter Rams principles)

## Full Skill Collection

For the complete set of 200+ iOS skills (including all skills referenced in this pipeline),
see [ios-skills-collection](https://github.com/JordanCoin/ios-skills-collection).
