# manuscript-cinematic-scene-audit — Claude Code Skill

A cinematic blocking and scene-population auditor for **any** narrative manuscript.
It reads each scene the way a film director reads a screenplay before shooting —
tracking every body in the room, every environmental detail a camera would see, all
movement and physical continuity, the emotional reactions that would register on an
actor's face, and the internal debate a character would voice in voiceover.

> The test: after any paragraph, could a reader close their eyes and draw the scene —
> who's there, where they stand, what the space looks like, and what everyone feels?

It **diagnoses and flags**; it does not rewrite prose.

## What it catches

- **Scene population** — characters who vanish without exiting, appear without
  entering, or are forgotten while others interact ("did we forget anyone?").
- **Blocking & movement** — teleporting characters, lost positions, impossible
  simultaneous actions, untracked navigation for characters with spatial/mobility/
  sensory traits, dropped animal characters.
- **Environment on camera** — floating-void scenes with no established space; a named
  setting that isn't actually present.
- **Emotional register** — reactions a camera would need that aren't on the page;
  emotions named in narration but not shown in body/face/behavior.
- **The voiceover test** — decisions, suspicions, and inner conflict the POV
  character should be processing but isn't.

Output is a per-scene audit + a pass summary with STOP / FIX / NOTE severities.

## How it knows your book

On run it walks **up** from your working folder for `.manuscript/profile.md` (the
[Manuscript Editorial Suite](https://github.com/dinaf2026-web) profile). From it the
skill pulls the POV character(s), the cast, and any characters with special spatial,
mobility, sensory, or non-human traits to track. No project is hard-coded — if
there's no profile, it audits from what's on the page and says so.

## Install

```powershell
# Windows (PowerShell)
Copy-Item .\manuscript-cinematic-scene-audit "$env:USERPROFILE\.claude\skills" -Recurse -Force
```
```bash
# macOS / Linux
cp -r manuscript-cinematic-scene-audit ~/.claude/skills/
```

Then ask Claude: **"cinematic pass on chapter 3"**, **"who's in the room in this
scene?"**, or **"read this like a director."**

## Part of a suite

This is one pass in the Manuscript Editorial Suite (continuity, fair-play,
prose-immersion, publisher, listing). It runs standalone, or alongside the others
via the suite's router.

## Author
[@dinaf2026-web](https://github.com/dinaf2026-web)

## License
MIT
