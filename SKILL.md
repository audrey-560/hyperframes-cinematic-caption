---
name: cinematic-caption
description: Apply designed cinematic captions to an existing HyperFrames video by selecting hero words from speech, building ordered mixed-case stacks, placing type around a speaker, and using subject-aware depth, translucent fills, or restrained sound accents. Use for cinematic captions, editorial subtitles, dynamic real-estate or creator-reel captions, or requests to make important words, numbers, or locations large, animated, or layered around a person.
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
4. Edit speech into semantic groups and ordered display fragments, then assign each cue a role and emphasis level using `references/style-system.md`. Score hero candidates for semantic importance, proof value, rhetorical stress, and legibility; record why the chosen word is the hero. Do not promote a word merely because it is a noun or sounds visually interesting.
5. Inspect the start, midpoint, and end of every designed cue. Record the motion envelope of the face, mouth, hair, shoulders, hands, products, UI, existing text, and usable negative space. Choose a coherent sequence of subject-relative anchor zones. Vary layouts between argument beats, but keep one stable anchor for fragments that belong to the same sentence or parallel list.
   When using a foreground subject cutout, also verify its start time, frame rate, duration, scale, and crop against the base footage. Inspect moving hair, hands, and shoulders at multiple timestamps. If a faint duplicate edge remains despite matching timing, rebuild the cutout from the original source pixels plus the matte alpha instead of overlaying independently compressed RGB.
6. Write `cinematic-caption-plan.json` before implementation. Include cue timing, exact displayed text, `semanticGroupId`, `orderIndex`, role, emphasis, `heroReason`, placement, `anchorZone`, `layoutState`, `buildMode`, `flowDirection`, optional `persistenceGroup`, `foregroundText`, `heroText`, `stackGap`, subject motion envelope, depth strategy, `fillSource`, palette, `occlusionBudget`, motion preset, optional graphic support, and optional audio accent.
7. Search the local HyperFrames catalog for relevant caption blocks before hand-authoring. Adapt strong matches to the current composition and brand; never copy another creator's logo, identity, or proprietary assets.
8. Implement captions as the least invasive change: either a dedicated high-numbered overlay track in the current composition or a reusable `compositions/cinematic-captions.html` sub-composition. Namespace new IDs and variables with `cc-`.
9. Keep outer clip elements responsible for timing and layout. Animate inner wrappers. Use one paused, seek-safe timeline driven by HyperFrames time. Add or update the motion sidecar for every animated selector. When the spoken phrase builds progressively, reveal its words or semantic fragments at their actual word starts instead of landing the completed lockup early.
10. If sound accents are requested, source local files through `media-use`, place them on dedicated audio tracks, synchronize their transient to the visual landing, and mix them under intelligible narration. Silence is an intentional option.
11. Run HyperFrames lint/check at cue midpoints and motion boundaries. Capture early, midpoint, and late frames for subject-layered heroes plus one chronological contact sheet. Review semantic timing, reading order, within-group spacing, controlled variation, face clearance, occlusion, and legibility, then iterate until checks pass.
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
- Build typography as a hierarchy: a clean sans for support, a genuine heavy or condensed display face for hero words, and an occasional editorial serif or italic accent for conversational actions such as a CTA. Bundle every chosen face locally.
- Declare only font weights that exist in the bundled file. Never synthesize a heavy weight from a lighter font, force thickness with oversized strokes, or tighten tracking until adjacent glyphs merge. Inspect repeated, narrow, and crossbar-heavy letters at full resolution.
- Keep one primary visual idea per cue and one dominant hero moment per sentence or argument beat.
- Prefer white for normal support captions. Use black only when the actual frame makes white illegible after a restrained outline, shadow, or localized scrim.
- Do not cover a face, mouth, key gesture, product, UI, or important property detail.
- When a clean matte exists, create power through proximity: place important hero words close enough to the subject for intentional depth instead of floating them high in unused negative space. Prefer 10–22% overlap around hair or outer head contours and reposition whenever identifying letters become ambiguous.
- Do not repeat a complete layout recipe across unrelated argument beats. When adjacent fragments form one sentence or parallel grammatical list, lock them to one anchor zone and treatment unless the subject or shot changes; vary timing or scale subtly instead of making the viewer chase the text.
- Choose one reading direction for each semantic group. Later fragments must continue that path; do not jump down, back up, and down again for the sake of variety.
- Keep captions level by default. Use rotation only when the source brand or explicit direction makes the angle meaningful; arbitrary tilting is not a substitute for composition.
- Preserve identifying letters in hero words. Subject depth may cross outer strokes, but reposition or resize whenever the overlap makes the spelling uncertain.
- For sequential instructional graphics, keep completed evidence visible when the next action depends on it. Place standalone screenshots, folders, and files natively; do not wrap every asset in a generic card.
- Build CTAs as one compact ordered cluster whose setup, action, keyword, and closing line reveal in reading order.
- Keep the CTA action word visually adjacent to its keyword; treat them as one unit rather than two labels in competing zones.
- Do not default to bottom-center karaoke, word pills, rainbow coloring, permanent neon, or a large word on every cue.
- Use glow as a brief emphasis treatment, not as the base caption style.
- Default translucent hero words to neutral silver-white tinted glass with visible source footage, a fine rim, and an optional soft light sweep. Introduce a restrained hue only when the brand, footage, or meaning justifies it. Do not add repeating scan lines or banded textures unless the user explicitly requests that graphic treatment. Avoid pastel rainbow fills, heavy bevel/extrusion, and decorative depth that makes the word feel like a detached title.
- Do not claim that text is behind a person unless a real subject matte, cutout, or defensible occlusion mask creates that depth. Without one, place the oversized word in verified negative space.
- A subject cutout must be frame-locked to the base footage and free of visible halos, doubled silhouettes, shadows, or color shifts. Do not add drop shadow to the subject layer. Prefer original source RGB recombined with the matte alpha and an alpha-capable high-quality local encode.
- Use sound effects as punctuation, not wallpaper. Do not add an effect to every phrase. Rotate the palette across adjacent hero beats: reserve shimmer for one luminous reveal, use no more than one primary accent per landing, and stack effects only when the combination has a specific narrative purpose.
- Preserve creator-safe margins and the project's platform safe zone.
- Match the user's brand before the reference aesthetic.
- Do not publish, upload, or replace source media without explicit approval.

## Completion standard

The result is complete when the captions are timed to meaning, visually integrated with the subject, restrained enough to preserve hierarchy, seek-safe, locally reproducible, and verified in HyperFrames. A technically valid fixed subtitle strip is not a cinematic-caption result.
