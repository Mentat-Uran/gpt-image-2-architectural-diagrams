---
name: gpt-image-2-architectural-diagrams
description: Create, edit, and review evidence-bounded non-render architectural graphics with GPT Image 2, including schematic plans, sections, elevations, axonometrics, exploded assemblies, site and context maps, parti, massing, program, circulation, environmental, structural, tectonic, envelope, detail, phasing, process, and same-scale comparison diagrams. Use for architectural boards, reports, studio work, competitions, case studies, and technical explanation whenever the requested image is architectural but not an effect render. Pair with the system imagegen skill for image-tool execution. Do not use it to present AI output as measured CAD/BIM/construction documentation or verified project evidence.
---

# GPT Image 2 Architectural Diagrams

## Purpose

Use this skill as the default architecture-specific layer for any requested architectural graphic that is **not an effect render**. Produce a clear architectural argument before producing a polished image.

Cover, among other outputs:

- schematic site plans, plans, sections, elevations, and projection drawings;
- axonometric, exploded axonometric, cutaway, and assembly views;
- site, context, figure-ground, access, climate, and sensory diagrams;
- parti, geometry, massing, program, adjacency, and circulation studies;
- daylight, sun, wind, shade, water, energy, and environmental diagrams;
- structural, load-path, tectonic, detail, envelope, roof, facade, and module studies;
- renovation, adaptive reuse, phasing, construction, operation, and process sequences;
- same-scale existing/proposed, option A/B, and before/after comparisons;
- restrained raster base graphics for architectural boards and reports.

Treat an effect image, atmospheric render, or photorealistic interior/exterior visualization as outside the default trigger. Use `$imagegen` alone for that work unless the user also requests a separate analytical or technical image.

Treat precise measured drawings, dimensioned construction documents, CAD/BIM models, and editable vector linework as a separate production boundary. This skill may prepare a schematic or presentation image from verified geometry, but must not imply survey accuracy, buildability, code compliance, or construction authority.

## Pair with the system image workflow

Load and follow `$imagegen` before any actual generation or edit. Let that skill govern the available tool path, model routing, input inspection, workspace copying, file naming, transparency handling, and final delivery. Do not silently switch models or bypass its execution rules.

Use this skill to govern:

- architectural question selection;
- representation choice;
- evidence and uncertainty;
- prompt architecture;
- geometry locks and edit invariants;
- architectural visual language;
- discipline-specific QA.

Do not call an image tool when the user only asks for diagnosis, planning, a prompt, or a review.

## Read the references deliberately

- Read [diagram-taxonomy.md](references/diagram-taxonomy.md) before choosing the diagram family or projection.
- Read [evidence-and-prompt-contract.md](references/evidence-and-prompt-contract.md) before writing a prompt, selecting inputs, or generating.
- Read [style-and-composition.md](references/style-and-composition.md) when defining the visual system, composition, family-specific modifiers, or transparent-background strategy.
- Read [qa-failure-playbook.md](references/qa-failure-playbook.md) before reviewing an output or rewriting a failed prompt.

## Required workflow

### 1. Establish authority and scope

Read applicable `AGENTS.md`, project evidence rules, and task-specific notes. Inspect actual source drawings and images instead of trusting filenames, captions, old AI outputs, or summaries.

Separate five lanes before prompting:

1. verified project fact;
2. generic disciplinary or manufacturer reference;
3. author analysis or interpretation;
4. design proposal or hypothesis;
5. unknown or pending verification.

Never promote a lower lane into a higher one. An AI image is an expression aid, not evidence.

When researching architectural precedents online, extract transferable diagram methods and vocabulary. Do not copy a distinctive composition, treat a web diagram as project evidence, or pass it to the generator unless the user explicitly authorizes that role and the source can lawfully be used.

### 2. Write the one-sentence claim

Complete this sentence before choosing a style:

> This image should let the reader understand ______ without relying on a caption.

Use one primary claim per image. Split competing claims into coordinated images rather than creating a dense all-in-one graphic.

Identify:

- audience and final use;
- diagram family;
- representation and viewpoint;
- verified base geometry;
- visual focus;
- single proposed change, if any;
- invariants that must remain unchanged;
- unknowns that must remain blank, dashed, abstract, or explicitly unresolved.

If the viewpoint, base geometry, comparison change, or interpretation is a design decision and the user has not supplied it, pause for that decision. Do not let the model decide it invisibly.

### 3. Choose representation from the question

Choose the smallest representation that makes the claim legible:

- use plan for organization, adjacency, access, figure-ground, and horizontal movement;
- use section for level, gravity, terrain, daylight, enclosure, sightline, and vertical relations;
- use elevation for facade rhythm, openings, datum, proportion, and surface organization;
- use axonometric for layered systems, program distribution, circulation, and assembly;
- use exploded axonometric only when separation or order is the actual subject;
- use a detail fragment for a local interface, junction, fastening logic, or material transition;
- use a sequence with one repeated base for transformation, construction, phasing, and operation;
- use same-view, same-outline, same-scale A/B for design change and option comparison.

Prefer a restrained 2D diagram over a decorative 3D object when 3D adds no explanatory value.

### 4. Build the decision card and input ledger

Use the templates in [evidence-and-prompt-contract.md](references/evidence-and-prompt-contract.md). Assign every input image exactly one declared role, such as edit target, visible-geometry evidence, data base, generic concept reference, or style reference.

Default to written style constraints instead of a style image. Do not mix an edit target, rough sketch, old AI image, case photograph, and unrelated precedent without a precise role for each.

For an evidence-led new view, use only the minimum source that constrains visible geometry. For an A/B proposal:

1. generate or clean the existing/base image from evidence;
2. edit that accepted image into the proposal;
3. change only the named relation;
4. repeat all viewpoint, crop, outline, scale, lighting, palette, and geometry invariants.

### 5. Write the bilingual prompt package

Always provide, preserve, and save:

1. the exact English prompt sent to GPT Image 2;
2. a faithful Chinese translation with no added or omitted constraints;
3. editable variables and locked invariants;
4. an input-role table;
5. the evidence and uncertainty boundary;
6. the output status, such as `analysis aid`, `author proposal`, `schematic`, or `pending verification`.

Order the prompt as a maintainable architectural brief:

1. use case and intended reading;
2. asset type and diagram family;
3. primary claim;
4. input roles, if any;
5. representation and viewpoint;
6. architectural content and relations;
7. geometry locks and exact counts;
8. the single change, for edits;
9. evidence boundary and deliberate unknowns;
10. visual hierarchy, palette, linework, fills, and shadows;
11. composition and crop;
12. text policy;
13. preserve list;
14. avoid list.

Use concrete nouns and relations. State exact visible counts when counts matter. Avoid ambiguous shorthand such as “make it architectural,” “improve the roof,” or “add technical detail.”

### 6. Generate or edit conservatively

Follow `$imagegen` for tool use. In addition:

- make one distinct asset per generation call;
- use one accepted base across a sequence or comparison family;
- generate without titles, captions, legends, arrows, dimensions, and labels by default;
- add typography and precise annotations later in a deterministic layout tool;
- keep unknown construction incomplete rather than plausible-looking;
- preserve the original source and every accepted intermediate;
- copy final outputs into the project workspace with versioned, non-colliding names.

If baked-in text is explicitly required, quote the exact literal text, specify its placement and hierarchy, forbid all extra text, and verify every character. Never let model-written labels become the only carrier of the claim.

### 7. Review in architectural order

Review the output using [qa-failure-playbook.md](references/qa-failure-playbook.md), in this order:

1. **Claim gate:** Does the image communicate the one-sentence claim without text?
2. **Evidence gate:** Does every visible assertion belong to the correct lane?
3. **Geometry gate:** Are base outline, viewpoint, scale, counts, and invariants preserved?
4. **Comparison gate:** For A/B, is the intended geometric change unmistakable and everything else stable?
5. **Architectural gate:** Is the chosen projection appropriate, spatially coherent, and free of invented hidden systems?
6. **Visual gate:** Is hierarchy carried by line weight, opacity, fill, and limited accents rather than decoration?
7. **File gate:** Are size, format, crop, alpha, edges, and saved path valid?

Inspect important details at 100% and 200%. For transparent assets, inspect internal line grids and fine components as carefully as the outer silhouette.

### 8. Iterate one variable at a time

Use a surgical follow-up:

> Change only X. Preserve A, B, C, D, and E exactly. Do not change anything else.

Repeat critical invariants on every edit. Do not keep appending broad stylistic requests to a failing prompt.

After two materially wrong attempts, stop generation. Return to the one-sentence claim, decision card, input roles, base representation, or a human sketch. More retries do not resolve an undecided architectural question.

### 9. Hand off with an honest status

Report:

- exact saved paths;
- generation or edit mode;
- source/input roles;
- exact English prompt and Chinese translation location;
- preserved invariants and intentional unknowns;
- QA performed and unresolved defects;
- whether the output is a schematic, analysis aid, author proposal, or verified drawing.

Do not call an image formal, final, as-built, measured, engineered, code-compliant, or construction-ready without the corresponding evidence and human approval.

## Stop conditions

Stop and request direction when:

- the requested output depends on an undecided viewpoint, geometry, endpoint, assembly, module, or design move;
- a source image's role cannot be determined;
- evidence conflicts materially;
- the user requests a precise measured drawing but no authoritative geometry exists;
- a web reference would be needed as content, not merely method inspiration, without authorization;
- two iterations fail the same architectural relation;
- a generated result would be presented as verified evidence or a formal deliverable without review.

