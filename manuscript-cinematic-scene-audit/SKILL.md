---
name: manuscript-cinematic-scene-audit
description: >
  Cinematic blocking and scene-population auditor for any narrative manuscript.
  Reads each scene the way a film director would — tracking every body in the room,
  every environmental detail a camera would see, all movement and physical
  continuity, the emotional reactions that would register on an actor's face, and
  the internal debate a character would voice in voiceover. Use when the author
  says "cinematic pass", "movie screen audit", "read this like a director", "do we
  account for everyone in the scene", "blocking pass", "camera test", "who's in the
  room", "did we forget anyone", "does the movement track", "would I see this on a
  big screen", "physical continuity check", "where is everyone", or "scene
  population audit". DISTINCT from prose-immersion-audit (which judges line craft):
  this audits spatial logic, blocking, full scene population, and cinematic
  completeness. It diagnoses and flags; it does NOT rewrite prose.
---

# Manuscript Cinematic Scene Audit

You read each scene the way a **film director reads a screenplay before shooting**:
visualizing it on a large screen in real time, tracking every person, every
movement, every piece of environment, and every emotional beat a camera would need
to capture.

If something would confuse a director on set — "wait, where is she standing when
this happens?", "we never established they were outside", "the third character is
still in this room and no one is acknowledging her" — that is a defect.

The target standard: a reader should be able to close their eyes after any
paragraph and draw a rough diagram of the scene — who is there, where they are,
what the space looks like, and what everyone is feeling.

## STEP 0 — Resolve the project profile

From the current working directory, walk **up** for `.manuscript/profile.md`.
- **Found** → read it. Drivers for this pass: the POV character(s), the cast and
  any **special spatial/mobility or sensory traits** to track (set in the bible /
  `canon_source` / `load_bearing` / Notes), and any animal or non-human characters
  that occupy space.
- **Not found** → invoke `manuscript-profile-setup`, then continue. If the author
  declines, audit from what's on the page and note the cast/traits were unset.

Load the cast and their physical traits, mobility patterns, and established
dynamics from the profile's canon source if one exists — some characters have
spatial needs (a wheelchair, a cane, low vision, a guide animal, a child carried)
or are non-human (a working dog, a horse) and must be tracked physically every
scene they're in, not treated as stationary props.

## STEP 1 — Scope declaration

State what you're auditing: scene / chapter / span of chapters. For a full
manuscript or many chapters, sample at minimum:
- An opening or establishing scene
- A scene with 3+ characters
- A high-tension / confrontation scene
- A quiet character moment

State which scenes you sampled. For a chapter-level or full request, work chapter
by chapter.

## STEP 2 — The Cinematic Audit (required output per scene)

```
## CINEMATIC AUDIT — [Scene / Chapter]
*Location: [where are we] | Characters present: [who is in this scene]*

### SCENE POPULATION
Who is physically present? List every named and unnamed character who should be in
the space. Flag anyone who:
- Was in the previous scene and vanished without exit
- Should logically be present but is never acknowledged
- Appears suddenly without having entered
- Is forgotten for long stretches while others interact

### BLOCKING & MOVEMENT TRACKING
Walk the scene chronologically; flag every place where:
- A character moves without that movement being accounted for (teleports)
- We lose track of where someone is standing / sitting / positioned
- Physical actions are inconsistent (she was sitting, now she crosses the room —
  was she ever established as standing?)
- Two characters do things that can't both happen (both reach for the same object
  from opposite sides of the room)
- A character with a tracked spatial/mobility/sensory trait navigates implausibly
  or that navigation goes untracked
- An animal or non-human character's position, attention, or behavior is dropped

### ENVIRONMENT & ATMOSPHERE ON SCREEN
What would a camera see? Flag any place where:
- The space has no visual, sonic, or atmospheric establishment (a floating void)
- We're in a named setting but it isn't present — architecture, light, weather,
  time of day, sound, season
- A location changes character mid-scene without explanation (noisy, then intimate —
  what happened?)
- Props or furniture are used without being established (a letter picked up that
  was never placed on the desk)

### EMOTIONAL REGISTER — WHAT THE CAMERA CATCHES
Would a skilled actor playing each character know what they're feeling here? Flag:
- A character reacting to significant news/confrontation/revelation with no visible
  response
- Emotions named in narration but not shown in body, face, or behavior
- A secondary character present for an emotionally charged moment with no reaction
  (they are furniture)
- Physical response inconsistent with the moment (calm body when panic would read)

### INTERNAL DEBATE — THE VOICEOVER TEST
For the POV character, flag any beat where:
- A significant decision is made with no visible internal deliberation
- They observe something suspicious and don't process it internally
- They're in conflict (want two things; don't want what they're about to do) and
  that conflict is absent from the narration
- A chance to show reasoning, doubt, or self-contradiction is missed
- The reader is ahead of the POV character, who seems not to process what the
  reader can see

### WHAT PLAYS PERFECTLY
1–3 specific moments that would land fully on screen — name them so they're protected.

### DEFECT SUMMARY
| Defect | Location (quote or beat) | Severity: STOP / FIX / NOTE |
|--------|--------------------------|------------------------------|
| [blocking gap] | "[quote]" | STOP / FIX / NOTE |
| [missing character] | [beat] | STOP / FIX / NOTE |
| [environment void] | [beat] | STOP / FIX / NOTE |
| [emotional absence] | "[quote]" | STOP / FIX / NOTE |
| [internal debate missing] | [beat] | STOP / FIX / NOTE |

STOP = breaks the scene; must fix before submission
FIX  = weakens the scene; should fix before submission
NOTE = worth revisiting; optional improvement
```

## STEP 3 — Chapter / Pass Summary

```
# CINEMATIC AUDIT — PASS SUMMARY

## CRITICAL DEFECTS (STOP-level — fix before submission)
All STOP defects across the pass with chapter reference.

## RECURRING PATTERNS
Defect types appearing in 2+ scenes — habits, not isolated misses. Name the pattern
and the chapters where it appears.

## STRONGEST CINEMATIC MOMENTS
2–4 scenes or beats that play at full movie quality. Name them by chapter.

## TOP PRIORITIES
The 3 most impactful fixes across the whole pass, ordered by story impact.
```

## Severity definitions

- **STOP** — a reader (or viewer) would stop and be confused: continuity break,
  impossible blocking, a forgotten character, a scene with no established location,
  an emotional absence during a major revelation.
- **FIX** — followable, but plays less vividly than it should: a tracked
  character's movement undertracked, a generic setting, a flat secondary presence in
  a charged moment.
- **NOTE** — the scene works; an opportunity to deepen, not a flaw.

## What this skill does NOT do

- Not line-level craft, filter words, or immersion quality → `manuscript-prose-immersion-audit`.
- Not canon/consistency defects → `manuscript-continuity-audit`.
- Not mystery logic / clue fairness → `manuscript-fair-play-audit`.
- Not marketability / acquisitions → `manuscript-publisher-critique`.
- Not rewriting prose → the author's writing/voice skill.

Its sole job: **does this scene play on a big screen?**

## Tracking notes (pull specifics from the profile)

- **Characters with spatial/mobility/sensory traits.** For each scene they're in,
  track where they're positioned, how they navigate the space, what they can and
  can't perceive, and whether any assistive person/animal is guiding or at rest.
  They are not stationary; their movement must be physically accounted for.
- **Animal / non-human characters.** A working animal in a scene is not a prop.
  Track its physical position, its behavioral reactions to strangers, tension, and
  environment, and when it's active vs. settled. It shouldn't vanish for long
  stretches.
- **Ensemble scenes.** When 3+ characters share a space, every character not
  explicitly written out should get *some* acknowledgment — a glance, a posture
  shift, a background reaction — or a clear note that they've stepped away.
