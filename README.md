# Cinematic Caption for HyperFrames

A portable AI skill for adding premium spatial editorial captions to HyperFrames videos.

Instead of placing every subtitle in a fixed strip, the skill turns speech into short semantic caption moments. It scores the words that actually carry the claim, builds each sentence in spoken order, keeps related fragments in one spatial group, and uses mixed-case support copy, heavy display typography, translucent glass heroes, real subject depth, and restrained sound accents.

## Requirements

- A local [HyperFrames](https://github.com/heygen-com/hyperframes) project
- An AI coding agent that supports installable `SKILL.md` skills
- Source footage or an existing HyperFrames composition

## Install

Clone the repository into the skills directory used by your AI coding agent.

### Codex and compatible agents

```bash
git clone https://github.com/audrey-560/hyperframes-cinematic-caption.git \
  ~/.agents/skills/cinematic-caption
```

### Claude Code

```bash
git clone https://github.com/audrey-560/hyperframes-cinematic-caption.git \
  ~/.claude/skills/cinematic-caption
```

Restart the agent after installation so it can discover the skill.

## Use

Invoke it directly:

```text
$cinematic-caption
```

Or ask naturally:

- “Apply the Cinematic Caption skill to this video.”
- “Add cinematic spatial captions to this HyperFrames project.”
- “Make the important words large, translucent, and animated.”
- “Give these captions a premium real-estate editorial style.”

The skill analyzes word timing, scores hero candidates for meaning and proof value, edits speech into ordered semantic groups, maps the speaker’s movement across each cue, plans controlled layout changes around that motion envelope, implements progressive mixed-depth overlays, and verifies both representative frames and the complete visual sequence before rendering.

Designed passages avoid both fixed-template repetition and random movement. Each sentence has one reading direction, consistent internal spacing, and a subject-relative anchor. Parallel hero lists can hold one stable placement instead of moving on every word; unrelated beats change only one or two design properties at a time. The default translucent treatment is neutral silver-white glass: source footage remains visible through a 32–55% fill, a fine rim preserves readability, and lower strokes can sit behind the subject when a clean matte exists.

## What it produces

- A `cinematic-caption-plan.json` timing and design plan
- Caption markup or a reusable caption sub-composition
- Seek-safe motion metadata
- Local media and optional sound-effect references
- Verification snapshots and a passing HyperFrames check
- A chronological caption contact sheet for reviewing layout variety
- A local preview for approval

## Validate

```bash
python3 ~/.codex/skills/.system/skill-creator/scripts/quick_validate.py .
```

## License

The skill instructions and reference materials are available under the MIT License.
