# Evidence and prompt contract

Use this contract before every prompt or image-tool call. It keeps architectural decisions visible and makes later correction possible.

## Decision card

```text
Working title:
Audience and use:
One-sentence claim:
Diagram family:
Representation / projection:
Viewpoint and crop:
Verified base geometry:
Primary focus:
One proposed change, if any:
Locked invariants:
Exact visible counts, if relevant:
Evidence lane for every visible element:
Deliberate unknowns / unresolved zones:
Text policy:
Output status:
```

If the one-sentence claim, representation, base geometry, or proposed change is not decidable from the sources, stop and obtain a human decision.

## Evidence ledger

| Lane | What belongs here | Allowed visual treatment | Never imply |
|---|---|---|---|
| Verified project fact | visible survey/photo content, authoritative plan/section/model, confirmed dimensions or data | solid, stable, highest-confidence linework | more precision than the source provides |
| Generic reference | disciplinary principle, code/manufacturer family, precedent method | secondary, dashed, muted, clearly generic | as-built or project-specific truth |
| Author analysis | interpretation derived from sources | analytical accent, dashed or diagrammatic | independently verified fact |
| Design proposal | chosen intervention or hypothesis | distinct proposal color or same-scale B state | existing condition or engineered resolution |
| Unknown | missing endpoint, hidden layer, dimension, performance, assembly, or decision | blank, open, dashed boundary, neutral placeholder | plausible-looking completion |

## Input-role ledger

Assign each input one role. Use the minimum number of images needed.

| Role | Permitted use | Required prompt language |
|---|---|---|
| Edit target | the image whose geometry/layout is being changed | `Image 1 is the edit target. Change only...` |
| Visible-geometry evidence | constrains only visible outline, rhythm, proportion, or relation | state exactly which visible facts it supports and what it does not support |
| Authoritative drawing/model | constrains verified projection or geometry | identify scale/authority and forbid model extrapolation beyond it |
| Data base | constrains values, zones, vectors, or measured fields | state source and units; do not let the model invent numbers or legends |
| Generic concept reference | supplies a generic assembly or disciplinary idea | say it is not project evidence and must not donate project-specific geometry |
| Style reference | supplies only visual treatment | default to written style instead; identify content that must not transfer |
| Human sketch | records a human decision or composition | preserve its chosen relations; do not beautify by redesigning them |
| Prior accepted AI image | controls continuity across a sequence/edit | state exact invariants and status as non-evidence |

Avoid using an old failed AI image as evidence. Avoid assigning one image both geometry and style authority unless that double role is intentional and explicitly approved.

## Source boundary statement

Write a short statement before generation:

```text
Supported:
- ...

Generic / transferable only:
- ...

Author analysis or proposal:
- ...

Unknown and intentionally unresolved:
- ...

This output must not be used as evidence for:
- ...
```

## Exact English prompt template

Use short labeled sections. Remove irrelevant sections; do not fill them with vague prose.

```text
Use case:
Create a [schematic / analytical / technical / comparative] architectural graphic for [board, report, studio review, case study]. It should let the reader understand [ONE-SENTENCE CLAIM] without relying on labels.

Asset type:
[DIAGRAM FAMILY] using a [plan / section / elevation / axonometric / exploded axonometric / detail fragment / same-scale A-B / sequence] representation. This is not a photorealistic effect render.

Input roles:
- Image 1: [ROLE AND EXACT AUTHORITY].
- Image 2: [ROLE AND EXACT AUTHORITY].
[Omit if text-only generation.]

Representation and viewpoint:
[ORTHOGRAPHIC OR PARALLEL PROJECTION, VIEW DIRECTION, CROP, SCALE RELATION, CAMERA LOCKS].

Architectural content and relations:
- [VISIBLE ELEMENT AND ITS RELATION].
- [VISIBLE ELEMENT AND ITS RELATION].
- [EXACT COUNT OR ORDER WHEN IT MATTERS].

Geometry locks:
Preserve exactly: [BASE OUTLINE, VIEWPOINT, PROPORTIONS, LEVELS, GRID, RHYTHM, COUNT, CROP].

Change:
Change only [ONE GEOMETRIC OR RELATIONAL CHANGE]. Keep everything else the same.
[Omit for new generation.]

Evidence boundary:
Show [SUPPORTED FACTS] as stable direct relations. Treat [GENERIC CONTENT] as abstract only. Treat [PROPOSAL] as an author proposal. Leave [UNKNOWNS] blank, open, dashed, or unresolved. Do not invent [HIDDEN SYSTEMS, ENDPOINTS, DIMENSIONS, FASTENERS, PERFORMANCE].

Visual language:
[INSERT THE CORE STYLE LOCK AND THE RELEVANT FAMILY MODIFIER FROM style-and-composition.md].

Composition:
[FOCAL HIERARCHY, GHOSTED CONTEXT, NEGATIVE SPACE, ALIGNMENT, PANEL OR SEQUENCE STRUCTURE].

Text policy:
No titles, captions, legends, labels, dimensions, scale bars, north arrows, numbers, letters, watermarks, or logos. Reserve clean negative space for later annotation.

Preserve:
[REPEAT ALL CRITICAL INVARIANTS, INCLUDING VIEW, SCALE, OUTLINE, PALETTE, LIGHTING, AND ACCEPTED DETAILS].

Avoid:
[FAMILY-SPECIFIC FAILURE MODES], decorative landscape, advertising composition, glossy product rendering, photorealistic atmosphere, strong gradients, heavy shadows, noisy textures, fake technical detail, and extra elements.
```

## Faithful Chinese translation template

Translate the exact English prompt section by section. Preserve:

- every count, order, axis, viewpoint, and crop;
- every `change only` and `preserve exactly` clause;
- every evidence limitation and unknown;
- every prohibited element;
- all editable placeholders and variable names.

Do not make the Chinese version “smoother” by adding architectural assumptions. Do not omit repeated invariants merely because they sound redundant.

## Editable variable sheet

```text
CASE_OR_PROJECT =
AUDIENCE =
FINAL_USE =
PRIMARY_CLAIM =
DIAGRAM_FAMILY =
PROJECTION =
VIEW_DIRECTION =
BASE_GEOMETRY =
FOCUS_LAYER =
CHANGE_ONLY =
PRESERVE_EXACTLY =
EXACT_COUNTS =
SUPPORTED_FACTS =
GENERIC_REFERENCE_ONLY =
AUTHOR_PROPOSAL =
UNKNOWNS =
ACCENT_1 =
ACCENT_2 =
BACKGROUND_MODE =
OUTPUT_ASPECT_OR_SIZE =
TEXT_POLICY =
OUTPUT_STATUS =
```

## Two-stage comparison contract

Use this route when A and B must be directly comparable:

### Stage A — establish the common base

- Use only the minimum authoritative evidence.
- Lock view, projection, crop, outline, scale, context, palette, and lighting.
- Remove invented details before accepting A.
- Save A as an independent, versioned source.

### Stage B — surgical edit

- Use accepted A as the edit target.
- Do not reintroduce unrelated sources unless their role is essential and declared.
- State `Change only [X]`.
- Repeat all locks from Stage A.
- Verify difference maps visually: the intended region should change; unrelated regions should not.

## Multi-image series contract

For coordinated assets:

- one distinct asset per call;
- one shared prompt header for style and geometry locks;
- one asset-specific claim and focus layer;
- stable projection, palette, background, line hierarchy, and crop logic;
- no attempt to make several unrelated deliverable images through one `n` request;
- preserve the accepted base across later calls or edits.

## Web-reference boundary

When online research is useful:

- record the title and URL;
- extract generic methods such as projection choice, layer separation, hierarchy, or sequence structure;
- do not treat precedent geometry, site facts, details, or performance as belonging to the current project;
- do not imitate a distinctive image one-for-one;
- prefer text-only style synthesis over passing the web image to the model;
- disclose if a web image is ever used as an explicit input.

## Output record

Save beside the output or in the project notes:

```text
Output path:
Created at:
Mode: text-to-image / edit / local alpha processing
Model/tool path:
Input paths and roles:
Exact English prompt path:
Faithful Chinese translation path:
Editable variables:
Locked invariants:
Intentional unknowns:
QA performed:
Known defects:
Status: schematic / analysis aid / author proposal / pending verification / verified drawing
Human approval state:
```

