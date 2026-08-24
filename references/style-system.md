# Cinematic Caption Style System

Use this reference to turn speech into a repeatable, generic design system. It is inspired by editorial social-video craft, not by any one creator's identity.

## 1. Edit the transcript into cues

- Default to 2–5 displayed words and roughly 0.65–1.8 seconds per cue.
- Break on meaning, contrast, breath, and rhetorical turns rather than fixed word counts.
- Remove filler and terminal punctuation unless punctuation is the visual idea.
- Keep a cue to one line when practical. Use two lines only for a deliberate hero lockup.
- Let important phrases hold longer; do not make every spoken word visible.

Assign one semantic role:

- `setup`: context that prepares a claim;
- `anchor`: the key noun or idea;
- `contrast`: a reversal such as cheaper/not expensive;
- `proof`: a number, location, feature, or concrete example;
- `aside`: a short conversational bridge;
- `payoff`: the sentence's conclusion;
- `cta`: the requested next action.

## 2. Assign emphasis deliberately

Use three levels:

- `support`: 52–80 px in a 1080×1920 composition, regular or medium weight, predominantly clean white;
- `anchor`: 76–112 px, semibold or bold, one accent color or weight shift;
- `hero`: 150–240 px, extra-bold or condensed display face, reserved for a claim reversal, decisive payoff, important number/location, or CTA keyword. A very short number or location may reach 280 px when the frame supports it.

Default distribution: about 60–75% support, 20–35% anchor, and no more than 5–15% hero. Do not promote a word merely because it is a noun.

Prefer strong weight and scale contrast over decorative effects. Use at most one accent hue in a scene. Choose the brand accent when available; otherwise derive one high-contrast accent from the footage.

Use white as the normal support-caption default. On a bright frame, preserve white with a restrained dark stroke, drop shadow, or localized feathered scrim before switching the text itself to black. Use black support copy only when it is clearly the more readable editorial choice for that exact frame.

## 3. Place captions around the subject

For portrait 1080×1920 work, use x=90–990 and y=240–1520 as the baseline safe zone unless the project defines stricter margins.

At each cue midpoint:

1. locate the face, mouth, hands, products, UI, and existing text;
2. find the largest calm negative-space region;
3. place the cue there with at least 40 px visual clearance from the face and mouth;
4. stack the phrase into one to three intentional lines with the anchor creating the visual edge;
5. keep the reading path coherent across adjacent cues while changing zones often enough to feel composed;
6. alternate positions when the subject, gesture, cut, or argument motivates the move.

Valid placements include upper-left, upper-right, shoulder-left, shoulder-right, center-gap, lower-left, and lower-right. Avoid the bottom platform UI zone and avoid placing thin white type over bright windows or sky without a restrained shadow, scrim, or alternate color.

Across a typical 8–12 second passage, use at least three distinct placement states when the footage provides safe space. Vary alignment and stack geometry as well as x/y position: left stair-step, right stair-step, centered hero plus small eyebrow, or a large background proof word with a compact foreground support stack.

When automatic face/object detection is unavailable, use conservative placement and verify every midpoint snapshot manually.

## 4. Choose the visual treatment

### Clean editorial

Use for most cues: precise sans-serif type, modest tracking, no box, and a soft text shadow only when needed for contrast.

### Weight or scale shift

Mix thin/regular support words with one bold anchor. Keep the phrase visually coherent; the anchor should read first without making support text disappear.

### Hero-scale word

Use when the language delivers a reversal, payoff, proof point, or CTA. Let the word briefly overshoot and settle. A hero may sit behind or beside the subject only when masking and contrast remain legible.

### Proof-scale number or location

Treat an important number, city, region, address fragment, percentage, or named place as visual evidence. Set it substantially larger than ordinary anchors—often 170–280 px in portrait—and allow it to span much of the frame width. Pair it with a much smaller white label. Position it behind the subject only with a real depth treatment; otherwise place it in the largest face-safe negative-space region.

### Translucent animated fill

For selected hero and proof words, replace a hard fill with a translucent spectral, gradient, footage, flag, map, or texture fill clipped inside the glyphs. Keep a crisp white or dark rim so the word remains readable. Let the internal fill drift or change for roughly 0.5–1.2 seconds after the word lands while the glyph itself holds steady.

Use content-relevant colors. A flag palette is appropriate only when country, region, civic identity, or the source art makes it meaningful. Otherwise derive two or three colors from the brand or footage. Do not apply the treatment to every anchor.

For true video-through-type, use a duplicated local video or texture layer clipped to the glyphs and driven by the composition time. For a lightweight spectral version, use a multi-stop gradient with transparent color stops and deterministic background-position motion.

### Behind-subject depth

True behind-person typography uses three layers:

1. base footage;
2. oversized hero or proof type;
3. a foreground subject matte or cutout above the type.

Keep ordinary support captions above the subject layer. If a clean matte is unavailable, use a manually verified occlusion mask only for a stable shot. Otherwise do not fake the depth—place the word beside or above the person with face clearance. Hair, hands, and gestures count as part of the subject silhouette.

### Soft bloom

Reserve for luminous, aspirational, technology, energy, reveal, or premium-payoff language, or when the user explicitly asks for glow. Animate a 0.20–0.40 second bloom at entry, then settle to a readable edge. Use layered text-shadow or a blurred duplicate at low opacity. Never leave a thick neon halo around routine dialogue.

### Evidence graphics

Maps, listing cards, photos, icons, numbers, or mini-panels may support `proof` cues. Treat them as evidence attached to the sentence, not decorative filler. Prefer one cluster with clear hierarchy. Rounded cards can use a faint rim light or bloom, but should remain subordinate to the message.

### Subject transition

A cutout, silhouette, or foreground wipe may bridge a major section change. Use it sparingly and only when clean source separation is available. Do not fabricate an inaccurate mask.

## 5. Motion vocabulary

Keep entries fast and decisive, generally 0.18–0.45 seconds.

- `support-cascade`: 10–22 px rise with opacity and a 30–55 ms word stagger;
- `firm-settle`: 0.88–1.04–1 scale for an anchor or hero landing;
- `editorial-wipe`: overflow-hidden reveal for a clean phrase or location;
- `directional-snap`: 18–36 px move from the nearest frame edge;
- `rule-draw`: short underline or divider that draws after the anchor arrives;
- `bloom-settle`: glow and blur peak at entry, then reduce while the glyph stays crisp;
- `fill-drift`: the glyph lands first, then the translucent internal color or footage moves while letter geometry stays fixed;
- `depth-reveal`: a large word enters on the middle layer and is partially occluded by a real foreground subject matte;
- `card-orbit`: evidence cards enter from different nearby vectors and settle into one organized cluster;
- `foreground-wipe`: subject or architectural edge motivates the transition.

Use transform and opacity for primary motion. Keep animation deterministic and seek-safe. Do not stack bounce, blur, rotation, and glow on the same routine cue.

## 6. Sound-design mapping

Sound is optional. When used, attach it to the visual landing rather than the animation start:

- support caption: usually silent; an occasional soft tick is enough;
- directional move or wipe: short airy whoosh;
- anchor landing: muted pop or light impact;
- hero word or payoff: low, controlled thump with a short transient;
- bloom or luminous reveal: subtle shimmer layered quietly above the landing;
- evidence-card cluster: one entry whoosh plus small staggered ticks, not one large hit per card;
- major section transition: brief reverse riser into a single landing impact.

Default to no more than one audible accent per emphasis beat and leave quiet gaps. Keep narration intelligible, avoid harsh high-frequency clicks, and duck or reduce accents under consonant-heavy speech. Never imply that generic SFX are part of the reference creator's licensed audio.

## 7. Plan schema

Create `cinematic-caption-plan.json` with this shape:

```json
{
  "version": 1,
  "range": { "start": 0, "end": 12.4 },
  "accent": "#DFFF49",
  "cues": [
    {
      "id": "cc-001",
      "start": 0.42,
      "end": 1.58,
      "text": "electricity cheaper",
      "role": "contrast",
      "emphasis": "hero",
      "placement": "shoulder-right",
      "depthStrategy": "negative-space",
      "treatment": "translucent-animated-fill",
      "motion": "firm-settle-with-fill-drift",
      "graphic": null,
      "audioAccent": "light-impact",
      "notes": "Keep 60 px clear of face"
    }
  ]
}
```

Use exact seconds. Cue IDs must be stable so markup, tracks, motion metadata, snapshots, and revisions can refer to the same moment.

## 8. HyperFrames implementation

- Put each cue on a dedicated overlay track or inside a caption sub-composition.
- For behind-subject type, place base footage on the lowest visual track, hero/proof type on a middle track, and the foreground subject matte on a higher track. Keep support copy above all three.
- Use outer clips for `data-start`, `data-duration`, placement, and bounds.
- Animate an inner `.cc-motion` wrapper.
- Namespace IDs, classes, variables, and timeline labels with `cc-`.
- Build one paused timeline and drive it from the HyperFrames time source.
- Use local fonts, media, and SFX. Do not depend on remote assets at render time.
- Record every animated selector and its properties in the motion sidecar.
- If adapting registry components, keep their contract but restyle them for the active project.

## 9. Verification checklist

- Every spoken idea that needs support has a readable cue.
- Timing follows semantic delivery rather than arbitrary intervals.
- Hero words are rare and genuinely important.
- Normal support copy is predominantly white and stacked with intentional hierarchy.
- Important numbers and locations receive a visibly larger proof tier when present.
- Placement changes across the passage rather than repeating one subtitle position.
- Behind-subject claims correspond to a real matte or occlusion mask.
- Glow settles to crisp readable type.
- No cue covers a face, mouth, hand gesture, product, UI, or important scene detail.
- Caption contrast works on its actual midpoint frame.
- Audio transients land with visuals and do not mask narration.
- Motion remains correct when seeking directly to any cue.
- HyperFrames lint, runtime, layout, motion, and contrast checks pass.
