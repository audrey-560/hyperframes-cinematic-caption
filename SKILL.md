---
name: cinematic-caption
description: Add dynamic cinematic captions to an existing HyperFrames video using mixed-case semantic phrases, progressive word stacks, changing spatial layouts, foreground/background pairings, oversized proof and hero words, animated translucent or video-textured fills, real subject depth, and optional restrained sound accents. Use for cinematic captions, editorial subtitles, dynamic real-estate or creator-reel captions, or requests to make important words, numbers, or locations large, glowing, translucent, animated, or layered around a person.
---

# Cinematic Caption

Turn a transcript into designed editorial moments that live inside the composition instead of a fixed subtitle band. Preserve the underlying edit, footage, narration, music, and brand unless the user asks to change them.

Read `references/style-system.md` completely before designing or editing captions. When the passage contains three or more designed cues, also read `references/dynamic-layout-recipes.md` completely before writing the caption plan.

## Inputs

Accept the active HyperFrames project plus any combination of:

- a source video or existing composition;
- a transcript, SRT/VTT, or word-level timing JSON;
- a requested time range;
- brand fonts, colors, or tone;
- optional requests for glow, graphic inserts, or sound effects.

Treat `$ARGUMENTS` as project, media, range, and style guidance. Discover missing project details locally when safe. Ask only when a missing choice would materially change the result.

## Required workflow

1. Read the active project's instructions and the mandatory `hyperframes` skill. Load `talking-head-recut`, `hyperframes-core`, `hyperframes-animation`, `hyperframes-creative`, and `hyperframes-cli` when available. If adding or changing audio, also load `media-use` and `hyperframes-audio`.
2. Inspect the existing composition, duration, dimensions, tracks, media paths, typography, palette, and motion sidecar. Do not rewrite unrelated scenes.
3. Resolve word-level timing. Prefer an existing transcript. If none exists, use the documented HyperFrames transcription workflow and retain the generated transcript as a project artifact. If a long-pass transcript drifts from the audible speech, retranscribe short overlapping segments and align their local timestamps; never proportionally stretch inaccurate word timings across the media duration.
4. Edit speech into semantic cues, then assign each cue a role and emphasis level using `references/style-system.md`. Promote numbers, locations, decisive contrast words, and payoff language into the proof/hero scale tier when they carry the argument.
5. Inspect a midpoint frame for every cue. Record face, mouth, hair, shoulders, hands, products, UI, text, and usable negative space. Choose a changing sequence of stacked placements from the frames; do not apply one global subtitle position. For a passage of eight seconds or longer, plan at least four distinct layout states when the footage provides safe space.
   When using a foreground subject cutout, also verify its start time, frame rate, duration, scale, and crop against the base footage. Inspect moving hair, hands, and shoulders at multiple timestamps. If a faint duplicate edge remains despite matching timing, rebuild the cutout from the original source pixels plus the matte alpha instead of overlaying independently compressed RGB.
6. Write `cinematic-caption-plan.json` before implementation. Include cue timing, exact displayed text, role, emphasis, placement, `layoutState`, `buildMode`, `flowDirection`, optional `persistenceGroup`, `foregroundText`, `heroText`, depth strategy, `fillSource`, palette, `occlusionBudget`, motion preset, optional graphic support, and optional audio accent.
7. Search the local HyperFrames catalog for relevant caption blocks before hand-authoring. Adapt strong matches to the current composition and brand; never copy another creator's logo, identity, or proprietary assets.
8. Implement captions as the least invasive change: either a dedicated high-numbered overlay track in the current composition or a reusable `compositions/cinematic-captions.html` sub-composition. Namespace new IDs and variables with `cc-`.
9. Keep outer clip elements responsible for timing and layout. Animate inner wrappers. Use one paused, seek-safe timeline driven by HyperFrames time. Add or update the motion sidecar for every animated selector. When the spoken phrase builds progressively, reveal its words or semantic fragments at their actual word starts instead of landing the completed lockup early.
10. If sound accents are requested, source local files through `media-use`, place them on dedicated audio tracks, synchronize their transient to the visual landing, and mix them under intelligible narration. Silence is an intentional option.
11. Run HyperFrames lint/check at cue midpoints and motion boundaries. Capture representative snapshots plus one chronological contact sheet, review timing, repetition, face clearance, occlusion, and legibility, and iterate until checks pass.
12. Start a local preview and give the user the URL. Render only after the normal HyperFrames preview-and-approval gate.

## Outputs

Leave the project with:

- `cinematic-caption-plan.json`;
- caption markup or a reusable caption sub-composition;
- a complete motion sidecar;
- local media and SFX references only;
- representative cue snapshots;
- a chronological caption contact sheet for judging variation;
- a passing HyperFrames check;
- a preview URL and a short note describing hero and audio-accent choices.

## Guardrails

- Keep phrases concise and semantic; do not reproduce every filler word.
- Use mixed case for ordinary support captions. Reserve all caps for acronyms, short proof labels, or a deliberately chosen CTA keyword.
- Keep one primary visual idea per cue and one dominant hero moment per sentence or argument beat.
- Prefer white for normal support captions. Use black only when the actual frame makes white illegible after a restrained outline, shadow, or localized scrim.
- Do not cover a face, mouth, key gesture, product, UI, or important property detail.
- Do not allow the subject to hide more than roughly 35% of a hero word. Aim for 10–30% intentional overlap and reposition or resize when the word cannot be recognized immediately.
- Do not repeat the same placement, alignment, stack geometry, hero scale, and fill treatment across adjacent designed cues.
- Choose one reading direction for each semantic group. Later fragments must continue that path; do not jump down, back up, and down again for the sake of variety.
- Keep captions level by default. Use rotation only when the source brand or explicit direction makes the angle meaningful; arbitrary tilting is not a substitute for composition.
- Preserve identifying letters in hero words. Subject depth may cross outer strokes, but reposition or resize whenever the overlap makes the spelling uncertain.
- For sequential instructional graphics, keep completed evidence visible when the next action depends on it. Place standalone screenshots, folders, and files natively; do not wrap every asset in a generic card.
- Build CTAs as one compact ordered cluster whose setup, action, keyword, and closing line reveal in reading order.
- Do not default to bottom-center karaoke, word pills, rainbow coloring, permanent neon, or a large word on every cue.
- Use glow as a brief emphasis treatment, not as the base caption style.
- Do not claim that text is behind a person unless a real subject matte, cutout, or defensible occlusion mask creates that depth. Without one, place the oversized word in verified negative space.
- A subject cutout must be frame-locked to the base footage and free of visible halos, doubled silhouettes, shadows, or color shifts. Do not add drop shadow to the subject layer. Prefer original source RGB recombined with the matte alpha and an alpha-capable high-quality local encode.
- Use sound effects as punctuation, not wallpaper. Do not add an effect to every phrase.
- Preserve creator-safe margins and the project's platform safe zone.
- Match the user's brand before the reference aesthetic.
- Do not publish, upload, or replace source media without explicit approval.

## Completion standard

The result is complete when the captions are timed to meaning, visually integrated with the subject, restrained enough to preserve hierarchy, seek-safe, locally reproducible, and verified in HyperFrames. A technically valid fixed subtitle strip is not a cinematic-caption result.
