# Cinematic Caption for HyperFrames

A portable AI skill for adding premium spatial editorial captions to HyperFrames videos.

Instead of placing every subtitle in a fixed strip, the skill turns speech into short semantic caption moments. It uses mixed-case white support copy, progressive word stacking, directional spatial layouts, foreground/background pairings, oversized hero words, proof-scale numbers and locations, animated translucent or video-through-text fills, real subject depth, restrained glow, and optional synchronized sound accents.

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

The skill analyzes word timing, edits speech into concise semantic cues, identifies which ideas deserve emphasis, plans a changing sequence of layouts around the subject, implements progressive mixed-depth caption overlays, and verifies both representative frames and the complete visual sequence before rendering.

Designed passages avoid repeating one centered stack without becoming chaotic. Each phrase follows a deliberate reading direction, captions stay level by default, identifying letters remain readable through subject overlap, and CTA fragments stay grouped. Subject-depth layers are checked for frame sync and clean alpha edges so hair and shoulders do not acquire a doubled shadow. Instructional edits can also preserve folders, files, and screenshots across dependent steps without placing generic cards behind every asset.

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
