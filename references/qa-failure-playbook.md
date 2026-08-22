# QA and failure playbook

Review meaning before polish. A beautiful image that communicates the wrong architecture is a failed diagram.

## Required review record

Record pass/fail and a short reason for each:

```text
Claim gate:
No-text reading:
Evidence lanes:
Projection choice:
Base geometry:
Viewpoint / crop / scale:
Exact counts and order:
Unknowns remain unresolved:
A/B change and invariants:
Line/fill hierarchy:
Visual noise and AI-render artifacts:
Text accuracy, if any:
Format / dimensions / alpha / path:
Status and human approval:
```

## No-text check

Hide or ignore every caption, arrow, label, and legend. Ask:

- Can a reader identify the focus?
- Can a reader understand the relation or change?
- Can a reader distinguish base, context, focus, proposal, and unknown?
- Does the image still work if all generated text is removed?

If not, repair geometry, projection, hierarchy, or comparison before adding annotations.

## Common failures and precise corrections

| Failure | Diagnosis | Correction |
|---|---|---|
| Polished but empty | the claim was never defined | return to the one-sentence claim and choose one focus |
| Wrong representation | perspective or axonometric hides the relation | switch to plan, section, elevation, or detail according to the question |
| Effect image replacing analysis | atmosphere, landscaping, materials, and light dominate | remove photorealistic language; use the core style lock and ghost context |
| Drone view replacing human/site relation | viewpoint is dramatic but cannot show level, sightline, or section | request a true technical section with cut geometry and explicit viewpoint relation |
| Exploded advertisement | many layers and fasteners create false technical authority | reduce to the minimum assembly order or interface; abstract unsupported sections |
| Invented construction | model fills hidden profiles, seals, membranes, fasteners, or dimensions | name the unsupported items in the avoid block and leave the zone blank/open/dashed |
| Invented environmental endpoint | flow arrows terminate in a plausible but unverified device or outlet | remove the endpoint; show only supported direction and mark continuation unresolved |
| Program rainbow | every room gets a different saturated color | group by the few semantic categories needed for the claim |
| Floating circulation arrows | route is not anchored to actual space | use a readable plan/section base and continuous, scaled path geometry |
| Form sequence drifts | camera, crop, ground, or mass changes every frame | accept one base first; edit sequentially and repeat all locks |
| A/B difference too subtle | only hue, caption, or minor seam changes | keep common outline/scale and make the chosen geometric relation unmistakable |
| A/B difference too broad | proposal becomes a redesign | use Stage A as the sole edit target; state `change only X`; repeat preserve list |
| Wrong count or order | GPT adds panels, rails, supports, or stages | state exact visible counts and ordered relations in both content and preserve sections |
| Regularized irregularity | existing irregular panels/seams become uniform | describe empty locations, varied spacing, and the exact irregular logic to preserve |
| Random supports or rails | generic solar/product knowledge overrides the requested interface | define one module and exact support/profile count; forbid arrays and extra hardware |
| Style reference leaks content | precedent geometry, vegetation, or objects appear | default to written style; if used, state that content must not transfer |
| Rough sketch is redesigned | cleanup changes the human decision | declare the sketch as geometry/composition authority and list invariants |
| Fake technical text | labels carry wrong claims or gibberish | generate no text; add labels later in layout software |
| Dark, dirty, or glossy finish | strong shadows, grain, texture, or advertising lighting obscure logic | request high-key matte fills, light field, low noise, thin stable contours, no AO haze |
| Cropped architecture | roof, ground, feet, edge, or sequence frame is cut | specify full object/section/extents, padding, and crop locks |
| Too much context | landscape or adjacent objects compete with focus | ghost and simplify context; keep one dominant contrast |
| Too little context | detail has no orientation or parent relation | add a pale parent fragment or locator relation without extra technical claims |
| Prompt bloat | later retries accumulate contradictory adjectives | reset to the decision card; revise one variable and one failure at a time |

## Architecture plausibility checks

Do not replace engineering review, but catch obvious diagram errors:

- Are cut elements distinguishable from elements beyond?
- Are plan, section, elevation, and axonometric conventions internally consistent?
- Do supports meet the elements they appear to support?
- Do routes pass through real openings and connect plausible levels?
- Are gravity and water directions consistent with the shown geometry?
- Do repeated modules align with the shown datum or grid?
- Does an exploded order correspond to a plausible assembly direction without implying unsupported fastening?
- Are proposal elements visually distinct without erasing the existing base?
- Are hidden conditions left unresolved when not evidenced?

Failing one of these checks requires either a prompt correction or an explicit human/engineering decision.

## Input-role audit

Before each call, answer:

- Which image is the edit target?
- Which image controls visible geometry?
- Which image supplies generic knowledge only?
- Is any image supplying style, and could its content leak?
- Is an old AI image being treated as evidence?
- Could the task succeed with fewer inputs?

For a surgical Stage B edit, prefer only the accepted Stage A image. Reintroduce other sources only when the changed relation cannot be specified without them.

## Difference audit for A/B and sequences

Compare:

- outer silhouette;
- projection and camera;
- crop and padding;
- scale and line weight;
- background and contact shadows;
- context placement;
- base grid, seams, and repeated elements;
- intended change region;
- unintended change regions.

The intended region should change strongly enough to read without labels. Unrelated regions should remain stable.

## Transparency and edge QA

Check programmatically where possible and visually at 100%/200%:

- file retains RGBA/alpha rather than being converted to RGB;
- corners are fully transparent for isolated assets;
- opaque/semitransparent coverage is plausible;
- the subject bounding box is neither clipped nor unexpectedly eroded;
- exterior silhouette has no key-color halo;
- internal line grids, clamps, frames, joints, and narrow gaps remain intact;
- shadows are absent unless deliberately retained;
- there are no detached alpha islands from background noise.

If fine details disappear, return to the untouched keyed source. Reduce global tolerance or use connected-background removal. Do not repair eroded technical detail by painting invented pixels.

## Text QA when text is unavoidable

- Compare every character with the exact requested string.
- Verify language, case, punctuation, line breaks, count, and placement.
- Reject extra text, duplicate labels, watermarks, or pseudo-dimensions.
- Confirm the diagram still communicates its geometry if text is hidden.
- Preserve or regenerate a no-text master when the graphic will enter a board workflow.

## Retry discipline

For the first failure:

1. identify one failed relation;
2. write one `change only` instruction;
3. repeat all invariants;
4. inspect the changed and unchanged regions.

For a second materially similar failure:

1. stop image generation;
2. simplify the claim or representation;
3. reduce the number of inputs;
4. draw or obtain a human decision sketch;
5. rebuild the base prompt instead of appending more prose.

## Status language

Use only a status justified by evidence:

- `schematic architectural graphic`;
- `analysis aid`;
- `generic disciplinary reference`;
- `author analysis`;
- `author proposal`;
- `pending verification`;
- `verified drawing` only when verified source geometry and review support it.

Never use AI polish as the reason to call an image final, measured, as-built, engineered, code-compliant, or construction-ready.

