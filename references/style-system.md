# Cinematic Caption Style System

Use this reference to turn speech into a repeatable, generic design system. It is inspired by editorial social-video craft, not by any one creator's identity.

## 1. Edit the transcript into cues

- Default to 2–5 displayed words and roughly 0.65–1.8 seconds per cue.
- Break on meaning, contrast, breath, and rhetorical turns rather than fixed word counts.
- Remove filler and terminal punctuation unless punctuation is the visual idea.
- Keep ordinary support text in natural mixed case. Reserve all caps for acronyms, short proof labels, or an intentionally forceful CTA keyword.
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

Build semantic groups before styling individual cues. A group is one clause, contrast, proof statement, payoff, or CTA. Give every displayed fragment a `semanticGroupId` and an `orderIndex` that follows speech order. Omit filler when useful, but never rearrange the remaining words merely to fill empty space.

Choose one stack grammar for each group:

- `support → hero`: context first, decisive word second;
- `eyebrow → hero → qualifier`: compact setup, dominant idea, then clarification;
- `proof label → number/location`: evidence label before the large proof value;
- `cta setup → action → keyword → tail`: the complete instruction in chronological order;
- `parallel hero sequence`: consecutive list items replace one another in the same anchor zone.

Treat phrases as semantic units when wrapping. Do not split an adjective from its noun, a preposition from its object, or an action from its required keyword when they can fit together.

## 2. Assign emphasis deliberately

Use three levels:

- `support`: 52–80 px in a 1080×1920 composition, regular or medium weight, predominantly clean white;
- `anchor`: 76–112 px, semibold or bold, one accent color or weight shift;
- `hero`: 150–240 px, extra-bold or condensed display face, reserved for a claim reversal, decisive payoff, important number/location, or CTA keyword. A very short number or location may reach 280 px when the frame supports it.

Default distribution: about 60–75% support, 20–35% anchor, and no more than 5–15% hero. Do not promote a word merely because it is a noun.

For every possible hero, score the decision before styling:

- `+3` if removing the word would weaken or change the claim;
- `+2` for concrete proof such as a number, location, named feature, or result;
- `+2` for a spoken stress, reversal, punchline, payoff, or CTA keyword;
- `+1` when the word is short enough to remain powerful and readable at hero scale;
- `−3` for filler, connective language, or a generic noun with no argumentative weight;
- `−2` when a nearby cue already expresses the same emphasis;
- `−2` when safe placement would hide identifying letters or important scene content.

Use `hero` at a score of 4 or higher and normally choose only the highest-scoring candidate in an argument beat. Use `anchor` when the idea matters but does not clear the hero threshold. A rhetorical parallel list may promote several consecutive items as one `heroSequence`; record the shared reason instead of pretending each item is a separate payoff. It is valid for a passage to have no hero word.

Prefer strong weight and scale contrast over decorative effects. For a typical 8–12 second passage, use white support, one neutral glass family, and at most one accent hue unless the brand or meaning clearly needs more.

Use a three-part typography hierarchy:

- support: a clean, locally bundled sans in its real regular or medium weight;
- hero: a genuine extra-bold, black, or condensed display face whose font file contains that exact weight;
- editorial accent: an occasional serif or italic face for a conversational action, aside, or CTA—not for every cue.

Do not alias a 700 file as 800 or 900, use browser-synthesized bolding, or fake weight with a large outline. Avoid excessive negative tracking and inspect hero words at full resolution for merged strokes, false cross-lines, and ambiguous letters.

Use white as the normal support-caption default. On a bright frame, preserve white with a restrained dark stroke, drop shadow, or localized feathered scrim before switching the text itself to black. Use black support copy only when it is clearly the more readable editorial choice for that exact frame.

## 3. Place captions around the subject

For portrait 1080×1920 work, use x=90–990 and y=240–1520 as the baseline safe zone unless the project defines stricter margins.

At the start, midpoint, and end of each designed cue:

1. locate the face, mouth, hair, shoulders, hands, products, UI, and existing text;
2. combine those samples into a motion envelope so a safe placement remains safe throughout the cue;
3. find the largest calm negative-space region or a clean outer hair/shoulder edge for real depth;
4. keep foreground support at least 40 px from the face and mouth throughout the cue;
5. stack the phrase into one to three intentional lines with the anchor creating the visual edge;
6. preserve the group's anchor zone and reading path until the sentence, shot, or argument changes.

For each semantic group, record a `flowDirection` such as `upper-left-to-lower-right`, `top-to-bottom`, or `left-to-right`. Successive fragments may move farther along that vector or stay aligned, but must not reverse direction. Spatial variety comes from a new group choosing a justified path, not from zigzagging inside one sentence.

Valid placements include upper-left, upper-right, shoulder-left, shoulder-right, center-gap, lower-left, and lower-right. Avoid the bottom platform UI zone and avoid placing thin white type over bright windows or sky without a restrained shadow, scrim, or alternate color.

Across a typical 8–12 second passage, use roughly three to five layout states when the footage and argument provide safe transitions. Vary one or two properties between unrelated groups: anchor zone, alignment, scale relationship, depth, fill, or motion. Do not change all of them at once. A parallel hero sequence is one layout state even when several words replace one another inside it.

Keep related lines close enough to read as one unit:

- support-to-support: line-height 0.96–1.10 with no arbitrary spacer;
- support-to-hero or hero-to-qualifier: roughly 0.15–0.45 times the support font size;
- CTA action-to-keyword: visually adjacent, usually no more than one support line-height apart;
- unrelated groups: separate clearly or replace the earlier group instead of leaving ambiguous floating fragments.

Within a top-to-bottom group, each later fragment's top edge must stay level with or below the previous fragment. Within a left-to-right group, each later fragment must stay level with or to the right. Never use up-down-up or left-right-left order inside one sentence.

For progressive speech, let semantic fragments accumulate into the final lockup at their word starts. A phrase may begin as compact support copy, hand off to a background hero word, and finish with a foreground payoff. Do not reveal the completed lockup before its words are spoken.

When automatic face/object detection is unavailable, use conservative placement and verify the start, midpoint, and end snapshots manually.

## 4. Choose the visual treatment

### Clean editorial

Use for most cues: precise sans-serif type, modest tracking, no box, and a soft text shadow only when needed for contrast.

### Weight or scale shift

Mix thin/regular support words with one bold anchor. Keep the phrase visually coherent; the anchor should read first without making support text disappear.

### Hero-scale word

Use when the language delivers a reversal, payoff, proof point, or CTA. Let the word briefly overshoot and settle. A hero may sit behind or beside the subject only when masking and contrast remain legible.

### Proof-scale number or location

Treat an important number, city, region, address fragment, percentage, or named place as visual evidence. Set it substantially larger than ordinary anchors—often 170–280 px in portrait—and allow it to span much of the frame width. Pair it with a much smaller white label. Position it behind the subject only with a real depth treatment; otherwise place it in the largest face-safe negative-space region.

### Tinted-glass hero fill

Use neutral silver-white tinted glass as the default translucent hero treatment. Set the glyph fill to roughly 32–55% opacity so the actual room, landscape, or source footage remains visible through the letters. Add a crisp 0.75–1.25 px rim, a restrained inner highlight, and an optional soft light sweep. Keep the letterform steady while the internal highlight moves for roughly 0.4–0.8 seconds. Repeating scan lines, striped bands, and obvious raster textures are opt-in treatments rather than part of the default glass look.

Use silver-white for a clean glass sequence. Introduce one hue per word only when the brand, footage, or meaning benefits from it; do not turn one word into a pastel rainbow. Reserve multicolor, flag, map, image, or video texture for speech that semantically justifies it.

For true video-through-type, use a duplicated local video clipped to the exact glyphs and driven by composition time. If a dimensional treatment is explicitly requested, reuse the same local font geometry for every layer and keep bevel or extrusion shallow. Tinted glass itself does not require extrusion.

### Behind-subject depth

True behind-person typography uses three layers:

1. base footage;
2. oversized hero or proof type;
3. a foreground subject matte or cutout above the type.

Keep ordinary support captions above the subject layer. If a clean matte is unavailable, use a manually verified occlusion mask only for a stable shot. Otherwise do not fake the depth—place the word beside or above the person with face clearance. Hair, hands, and gestures count as part of the subject silhouette.

The foreground layer must share the base footage's exact timing and geometry. Confirm start time, frame rate, duration, dimensions, crop, and object-fit before judging the matte. Inspect at least three frames with visible movement in hair, hands, or shoulders. A soft duplicate contour can come from separately compressed foreground RGB even when timing matches; rebuild the cutout from the original source pixels and the existing matte alpha so the foreground and background colors remain identical. Use a high-quality alpha-capable local encode and never add a cosmetic shadow to the subject layer.

Record an `occlusionBudget` for each background hero. Aim for 10–30% of the glyph area crossing hair, shoulders, arms, or torso; 35% is the upper limit for a short familiar word. Face and mouth coverage never counts as acceptable overlap. If identifying letters disappear, reposition or resize the word.

When a clean matte exists, prefer a 10–22% hairline or outer-head overlap for the most important hero words. A large word floating above an unused gap usually feels weaker than one whose lower strokes tuck behind the subject. Preserve the upper glyph structure so the complete word remains readable.

Treat identifying internal glyphs as protected. For words with repeated or narrow letters, preserve enough of the center to make spelling immediate; prefer overlap at the first or last outer stroke. Confirm the exact displayed spelling in a midpoint snapshot rather than trusting the DOM text alone.

### Soft bloom

Reserve for luminous, aspirational, technology, energy, reveal, or premium-payoff language, or when the user explicitly asks for glow. Animate a 0.20–0.40 second bloom at entry, then settle to a readable edge. Use layered text-shadow or a blurred duplicate at low opacity. Never leave a thick neon halo around routine dialogue.

### Evidence graphics

Maps, listing cards, photos, icons, numbers, or mini-panels may support `proof` cues. Treat them as evidence attached to the sentence, not decorative filler. Prefer one cluster with clear hierarchy. Rounded cards can use a faint rim light or bloom, but should remain subordinate to the message.

Keep standalone evidence visually native. A screenshot may use its own edge and a restrained shadow; folders and files should appear as objects. Add a panel only when it represents a real browser, chat, dialog, or other interface surface. For sequential instructions, assign related assets a `persistenceGroup` and retain completed steps while the next dependent action appears when the frame has room.

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

Rotate sound identity across adjacent hero beats. A useful sequence might use bass impact, one glass shimmer, a digital servo or airy sweep, a dry clockwork tick, a mechanical toggle, and a final low impact. Reserve shimmer for one luminous reveal. Adjacent beats must not reuse the same chime, and high-frequency accents must not overlap without a specific reason.

## 7. Plan schema

Create `cinematic-caption-plan.json` with this shape:

```json
{
  "version": 1,
  "range": { "start": 0, "end": 12.4 },
  "accent": "#F2F5F7",
  "cues": [
    {
      "id": "cc-001",
      "semanticGroupId": "claim-01",
      "orderIndex": 2,
      "start": 0.42,
      "end": 1.58,
      "text": "electricity cheaper",
      "role": "contrast",
      "emphasis": "hero",
      "heroReason": "The reversal carries the claim; score 6",
      "placement": "shoulder-right",
      "anchorZone": "subject-right-hairline",
      "layoutState": "background-hero-with-foreground-support",
      "buildMode": "foreground-background-handoff",
      "flowDirection": "upper-left-to-lower-right",
      "persistenceGroup": null,
      "foregroundText": "electricity",
      "heroText": "cheaper",
      "stackGap": "0.28em-support",
      "subjectEnvelope": {
        "sampleTimes": [0.42, 1.0, 1.58],
        "protected": ["face", "mouth", "right-hand"]
      },
      "depthStrategy": "subject-cutout",
      "treatment": "neutral-silver-tinted-glass",
      "fillSource": "transparent-silver-white-with-soft-light-sweep",
      "palette": ["rgba(255,255,255,0.52)", "rgba(198,211,220,0.30)"],
      "occlusionBudget": 0.18,
      "motion": "firm-settle-with-soft-light-sweep",
      "graphic": null,
      "audioAccent": {
        "type": "muted-bass-impact",
        "start": 1.04,
        "gain": 0.18
      },
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
- Every hero has a recorded semantic reason and clears the hero threshold, or belongs to one documented parallel hero sequence.
- Normal support copy is predominantly white and stacked with intentional hierarchy.
- Important numbers and locations receive a visibly larger proof tier when present.
- Layout changes happen between argument beats, while fragments in the same sentence or parallel list retain a stable anchor.
- Ordinary support text uses mixed case unless a clear semantic reason calls for all caps.
- Progressive builds follow actual word starts and never reveal the completed phrase early.
- Unrelated adjacent hero cues vary one or two design properties; parallel hero sequences remain visually stable.
- Behind-subject claims correspond to a real matte or occlusion mask.
- The subject layer is frame-locked to the base footage and has no visible halo, doubled edge, shadow, or color shift at hair, hands, or shoulders.
- Background hero words remain recognizable within their recorded occlusion budgets.
- Hero-word spelling is visually unambiguous; identifying internal glyphs are not hidden.
- Hero words use real bundled display weights; no synthetic bolding, merged strokes, false cross-lines, or excessive negative tracking is visible.
- Each semantic group follows its declared direction without vertical or horizontal reversals.
- Every group reads in spoken order, uses consistent internal spacing, and contains no orphaned phrase fragments.
- Captions remain level unless an explicit style rationale justifies rotation.
- Sequential instructional assets persist when the next step depends on them, without generic framing around native assets.
- CTA fragments form one compact cluster and reveal in reading order.
- A dimensional translucent word uses one exact-font mask across fill, rim, highlight, and extrusion, with animated texture visible from its first readable frame.
- Tinted-glass hero words preserve visible source detail through a 32–55% neutral or justified single-hue fill and sit close enough to a clean matte for 10–22% intentional hairline overlap.
- Glow settles to crisp readable type.
- No foreground cue enters the recorded face/mouth motion envelope or covers a key gesture, product, UI, or important scene detail.
- Caption contrast works on its actual midpoint frame.
- Audio transients land with visuals and do not mask narration.
- Adjacent hero beats have distinct primary sound identities; shimmer occurs only once and no repeated chimes overlap.
- Motion remains correct when seeking directly to any cue.
- A chronological contact sheet reads as one coherent sequence without repeated centered stacks.
- HyperFrames lint, runtime, layout, motion, and contrast checks pass.
