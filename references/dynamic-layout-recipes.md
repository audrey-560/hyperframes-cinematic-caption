# Dynamic Layout Recipes

Use this reference when a passage has three or more designed caption cues. The goal is a coherent sequence that keeps recomposing around the speaker instead of repeating a centered template.

## Sequence grammar

Plan the passage as a sequence, not isolated title cards. Across eight to twelve seconds, use roughly three to five distinct layout states when safe transitions exist. Change state at a sentence, shot, subject-position, or argument boundary—not simply because a new word begins.

Choose a `flowDirection` for every semantic group. A group may read upper-left to lower-right, top to bottom, or left to right, but its later fragments cannot reverse that direction. Never manufacture dynamism with an up-down-up sequence. Start a new path only when the sentence, shot, or section changes.

Useful state changes include:

1. compact upper-left or upper-right support stack;
2. large background hero with small foreground support;
3. foreground chest-level payoff with a background shoulder word;
4. offset proof word or number spanning the calm side of the frame;
5. wide headline above the subject with slight hair or shoulder overlap;
6. CTA keyword behind the subject paired with an unobstructed foreground instruction.

Change one or two structural properties at a time. Use a variation budget across anchor zone, alignment, scale relationship, depth, font accent, fill, and motion; a new group does not need all seven to change.

When several adjacent hero words complete one parallel list, lock them to one subject-relative anchor zone so the viewer can compare them without chasing the text around the frame. Resume spatial variation when the sentence, subject position, or shot changes.

Keep the font system intentional: reuse one clean support sans, select a genuine heavy display face for hero words, and introduce a serif or italic accent only where its editorial tone adds meaning. Variation comes from hierarchy, not random typeface changes.

Keep the color system intentional: white support, neutral silver-white glass, and at most one accent family per short passage by default. Reusing the neutral glass across a parallel hero sequence is continuity, not repetition.

Keep text level by default. Create energy through scale contrast, alignment, foreground/background pairings, fill motion, and timing. Rotate only when a source design system or explicit user direction makes the angle part of the visual language.

## Progressive builds

Choose one `buildMode` for each cue:

- `replace`: the prior phrase clears and a complete short phrase enters;
- `progressive`: semantic fragments appear at their word starts and accumulate into one lockup;
- `foreground-background-handoff`: support copy establishes the idea, then the hero word lands behind the subject;
- `proof-reveal`: a small label appears first, followed by a substantially larger number, location, or concrete noun;
- `cta-build`: conversational setup appears first, the action word enters in front, and the keyword lands last as the hero.

Use `progressive` or a handoff mode for the most important sentence. Do not show the finished phrase before it has been spoken.

For every group, sketch the final reading order before assigning coordinates. Use the group's `orderIndex` values to place fragments monotonically along its `flowDirection`. If the final arrangement cannot be read in speech order while paused, rebuild the stack before animating it.

Keep a CTA in one compact visual cluster. Reveal setup, action, keyword, and closing line in the same reading direction; a later keyword must not jump above an earlier action word.

Place the CTA action word close enough to the keyword that they read as a single instruction. The closing line should follow immediately rather than floating in a distant zone.

## Depth and occlusion

Behind-subject type requires a real matte or cutout. Put base footage below the hero, the hero on a middle layer, the subject matte above it, and ordinary support copy on the foreground layer.

Before placing type, verify that the cutout and base footage have matching start time, frame rate, duration, dimensions, crop, and scale. Review moving silhouette edges at early, middle, and late depth cues. If timing matches but a faint shadow or duplicate contour remains, treat it as an RGB/alpha encoding problem: recombine the original source pixels with the matte alpha and encode that foreground at high quality. Do not hide the defect with blur, scale offsets, or subject drop shadows.

Set an `occlusionBudget` for every background hero:

- `0.10–0.20`: light hair or shoulder crossing;
- `0.20–0.30`: strong depth while retaining immediate readability;
- `0.30–0.35`: maximum for very short, familiar words;
- above `0.35`: reject the placement and reposition or resize.

Never count face or mouth coverage as acceptable overlap. Prefer crossing the lower third of letters with hair, shoulders, arms, or torso. Keep a crisp rim or stroke around translucent fills so hidden and visible portions still form one readable word.

Protect identifying internal letters. If the matte makes a word appear misspelled even though the source text is correct, the placement fails. Move the word so overlap lands on an outer stroke or reduce the occlusion budget.

## Persistent instructional evidence

When captions accompany a step-by-step workflow, use a shared `persistenceGroup` for objects that should accumulate. For example, keep the source folder, footage file, and destination project visible while the AI prompt is typed. Remove completed evidence only when the frame becomes crowded or the next instruction no longer depends on it.

Present native assets without decorative shells: screenshots can use a light shadow, and folders or files can stand alone. Use cards only for real browser, chat, dialog, or application surfaces.

## Fill hierarchy

Use fills because they support meaning or sequence variety, not as automatic decoration.

1. Ordinary support: clean mixed-case white text with a restrained shadow or local scrim.
2. Anchor: white plus one weight or scale shift; optionally one footage-derived accent.
3. Tinted-glass hero: neutral silver-white at 32–55% opacity by default, visible source footage, a fine rim, and an optional soft light sweep. Add a restrained hue only with semantic or brand justification. Repeating scan lines or striped textures require explicit intent.
4. Video-through-type: a duplicated local video moves inside the glyphs while letter geometry remains stable. Use for words about motion, change, transparency, place, or visual proof.
5. Image, map, or flag texture: use only when the spoken content names that place, region, country, property, or evidence source.

Unrelated hero cues should not repeat the exact same palette, scale, and motion as a complete recipe. A documented parallel hero sequence may deliberately reuse neutral silver-white, scale, and placement so its items compare cleanly.

For 3D-like translucent type, reuse the exact same local font for the fill mask, rim, highlight, and extrusion. The animated texture must be visible from the word's first readable frame; keep bevel and extrusion restrained enough that counters and crossbars remain clean.

## Sound palette rotation

Give adjacent hero landings distinct primary accents. Use low impact for mass, a single shimmer for the most luminous reveal, a servo or airy sweep for motion, a dry tick for timing, and a mechanical clack for an action cue. Do not reuse the same ding or chime on neighboring beats. Use one primary accent per landing unless a deliberate layered event is documented in the caption plan.

## Motion recipes

- Support fragments: 10–18 px directional rise, 0.16–0.24 seconds, 80–180 ms semantic stagger.
- Hero handoff: support establishes first; hero lands on its spoken word with a 0.26–0.36 second firm settle.
- Video-through-type: the word settles first; the internal footage continues moving while the outline stays crisp.
- Foreground payoff: enter from the nearest open side by 14–28 px without bounce.
- CTA build: conversational setup, then action word, then hero keyword. Keep the final reading order obvious.

Use blur only for a short transition or bloom. Settle to sharp text within 0.4 seconds.

## Anti-repetition review

Create a chronological contact sheet of cue midpoints and reject the sequence if any of these are true:

- three unrelated groups share the same centerline and full layout recipe;
- two unrelated hero words use the same palette, scale, placement, and motion;
- adjacent hero beats reuse the same chime or stack multiple high-frequency accents;
- every phrase is already complete on its first visible frame;
- the subject hides a hero word’s identifying letters;
- the foreground subject shows a halo, doubled silhouette, shadow, or color shift against the base footage;
- a semantic group reverses its chosen reading direction;
- paused fragments do not read in spoken order or use visibly inconsistent gaps;
- a caption is tilted without an explicit visual rationale;
- a CTA action and keyword are separated into competing zones;
- a hero face is synthetically bolded, overly tracked inward, or shows merged strokes or false cross-lines;
- translucent words use pastel rainbow fills, excessive bevel/extrusion, or float above a large unused gap when a clean subject matte could create stronger proximity;
- sequential instructional assets disappear before the dependent action appears;
- all support copy uses the same width, alignment, and vertical zone;
- hero treatments outnumber clean support cues;
- a location, flag, or map texture appears without semantic justification.

The final sequence should feel authored as one editorial passage. Related fragments share a clear spatial system; meaningful beat changes receive controlled variation.
