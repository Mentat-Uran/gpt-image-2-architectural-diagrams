# Style and composition system

Use a written visual system as the default style authority. Adapt it to the architectural question; do not force every image into a decorative axonometric.

## Core style lock — English prompt block

```text
Restrained professional architectural editorial diagram. Use clean simplified orthographic, sectional, elevational, or parallel-projection geometry appropriate to the stated question. Use a pale warm-white or very light beige field; off-white, light-gray, and muted slate masses; thin stable charcoal outer contours; finer secondary inner edges; flat matte fills; crisp line hierarchy; restrained low-saturation semantic accents; generous negative space; soft neutral contact shadows only where they clarify depth; high-key, quiet, precise, and low-noise presentation. The result should read as a board-quality architectural drawing, not as a photograph, cinematic render, product advertisement, or generic AI concept art.
```

## Core style lock — faithful Chinese meaning

```text
克制、专业的建筑编辑型图解。根据问题选用清晰、简化的正投影、剖面、立面或平行投影几何。使用浅暖白或极浅米色底；灰白、浅灰和低饱和板岩灰体块；细而稳定的炭灰外轮廓；更细的次级内轮廓；平整哑光填色；清楚的线级；少量低饱和语义强调色；充足留白；只在有助于辨认深度时使用柔和中性接触阴影。整体应明亮、安静、精确、低噪，读起来像可用于图版的建筑图，而不是照片、电影式效果图、产品广告或泛化的 AI 概念图。
```

## Semantic graphic system

Keep the meaning of marks stable across a set:

| Status | Suggested treatment |
|---|---|
| verified visible/project-supported | solid charcoal or stable light-gray geometry |
| context not under discussion | pale gray, reduced opacity, finer line |
| current analytical focus | one muted accent with highest contrast |
| generic disciplinary reference | muted blue-gray, thin dashed or secondary |
| author analysis | restrained analytical accent, often dashed or translucent |
| design proposal | one distinct warm or cool accent, consistent across the set |
| removed/demolished | outline, hatch, or muted red only when necessary |
| unknown/unverified | blank, open edge, dotted/dashed neutral boundary, or omitted |

Do not encode five different ideas with five saturated colors. Start with grayscale plus one accent; add a second accent only when the claim requires a comparison.

## Line, fill, and shadow hierarchy

- Use the strongest contour for the primary architectural boundary.
- Use finer contours for internal subdivision, supports, or secondary edges.
- Ghost context instead of deleting all spatial reference.
- Prefer flat matte fills to gradients.
- Use soft contact shadows to separate layers, not atmospheric ambient-occlusion haze.
- Avoid heavy cast shadows that hide linework or imply an effect-render light source.
- Keep repeated modules genuinely repeated; avoid noisy microvariation.
- Preserve open white space around the focus and around future annotations.

## Composition rules

- Center the claim, not necessarily the object.
- Use a single dominant focal relationship.
- Keep context quieter than the focus layer.
- Align coordinated views to a common datum or frame.
- For sequences, repeat the same base, camera, and crop.
- For A/B, match scale and visual weight before comparing.
- For exploded views, separate only the layers required to explain order or interface.
- For a detail fragment, include enough parent geometry to show orientation and location.
- Avoid decorative collage, scattered callout bubbles, floating pseudo-technical arrows, and poster-like composition.

## Family modifiers

Append only the relevant block to the core style lock.

### Site and context

```text
Use a restrained top-down architectural site-analysis drawing with a readable figure-ground base. Keep surrounding urban or landscape context pale and simplified. Highlight only the stated routes, edges, gradients, views, climate vectors, or opportunity/constraint zones. Do not invent contours, property lines, regulatory boundaries, vegetation, or traffic data.
```

### Parti and organization

```text
Reduce the architecture to the minimum number of organizing relations: primary axis, boundary, hierarchy, solid/void, datum, center, threshold, or sectional relation. Omit furniture, minor wall thickness, texture, and construction detail unless they are part of the claim.
```

### Technical section

```text
Use a true diagrammatic architectural section, not a drone view or perspective render. Make levels, cut elements, ground/terrain relation, enclosure, gravity, daylight, sightline, and vertical sequence legible. Use a strong poche only for genuinely cut elements. Leave unsupported terrain, dimensions, and hidden construction unresolved.
```

### Massing transformation

```text
Use a short repeated-base sequence. Preserve the same ground plane, viewpoint, scale, base mass, crop, and lighting in every step. Change one form operation per step and ghost prior or contextual geometry.
```

### Program and circulation

```text
Use a neutral base building with a limited semantic palette for program or movement. Keep zones contiguous and spatially plausible. Make paths continuous, scaled to the architecture, and clearly distinct by user or function only when required. Do not add decorative arrows or arbitrary rainbow zoning.
```

### Environmental logic

```text
Use clean vectors, gradients, shaded zones, or flow fields only where supported by observations, data, simulation, or an explicit proposal. Keep values and endpoints absent unless provided. Separate environmental condition from design response.
```

### Structure, tectonic, and assembly

```text
Use a simplified parallel-projection technical model or a local detail fragment. Show primary and secondary hierarchy, bearing, adjacency, overlap, gap, or assembly order with exact visible counts where specified. Do not fabricate fasteners, seals, membranes, reinforcement, dimensions, fire barriers, drainage, ventilation, or load performance.
```

### Facade, roof, envelope, and module

```text
Use elevation, roof plan, unfolded surface, or a restrained axonometric fragment to show datum, rhythm, opening, panel, seam, rib, joint, layer, and edge relationships. Preserve irregularity or repetition exactly as specified. Keep material impression subordinate to geometric organization.
```

### Existing/proposed or option A/B

```text
Create a strict same-view, same-outline, same-scale comparison. Preserve projection, crop, context, base geometry, line hierarchy, palette, and lighting. Make only the named architectural relation change, and make that change visible in geometry rather than relying on color or text.
```

### Construction, phasing, or operation

```text
Use equal panels or independent matching frames built from one accepted base. Show one temporal state or action per frame. Ghost completed and contextual elements. Do not invent temporary works, logistics, access, machinery, or dependencies not provided.
```

### Board base graphic

```text
Generate the architectural image only. Reserve clean negative space for later titles, captions, legends, dimensions, and sources. Do not generate a finished poster, fake page layout, typography, labels, logos, or watermarks.
```

## Default avoid block

```text
Avoid photorealism, cinematic atmosphere, glossy architectural visualization, dramatic sunset or neon lighting, advertising composition, decorative landscape, dense photo collage, watercolor grain, painterly noise, paper texture, excessive material texture, strong gradients, saturated rainbow colors, deep ambient-occlusion haze, heavy cast shadows, pseudo-technical detail, random rails or supports, invented fasteners or hidden layers, fake dimensions, fake labels, extra arrows, extra panels, watermarks, and logos.
```

## Text policy

Default to no generated text even though current GPT Image models can render text. Architectural boards need editable, consistent, sourceable typography and symbols.

If the user explicitly requires baked-in text:

- provide literal text in quotation marks;
- demand verbatim rendering exactly once;
- specify language, position, alignment, font character, contrast, and hierarchy;
- prohibit all extra letters, numbers, labels, and watermarks;
- verify every character at output size;
- retain a no-text version when practical.

## Transparent-background strategy

Treat transparency as a capability-check workflow because the API and the available built-in execution path may differ.

1. Check the current `$imagegen` instructions and callable tool path.
2. If native transparency is supported in that path, request an isolated subject on a fully transparent PNG/WebP background, exclude scenery/checkerboard/shadow, and preserve alpha through every edit.
3. If native transparency is unavailable, use the chroma-key route defined by `$imagegen`.
4. Preserve the untouched generated source before any local alpha processing.
5. Audit the subject palette before selecting a key color.

### Safe key selection

- Choose a key hue absent from outer contours, internal grids, cell lines, clamps, fasteners, shadows, and accent fills.
- For green roofs plus coral/rose proposal elements, avoid magenta because it overlaps the subject; pure blue may be safer only if all slate-blue subject accents are replaced by neutral gray.
- Prohibit the key hue anywhere inside the subject.
- Keep the keyed background perfectly flat, opaque, and free of shadows or gradients.

### Alpha protection

- Do not widen a global tolerance when fine internal details approach the key hue.
- Prefer connected-background removal or conservative hard-key removal over high-tolerance global deletion.
- Inspect the silhouette, internal grids, clamps, frames, joints, and narrow gaps at 100% and 200%.
- Check corner alpha, nontransparent coverage, bounding box, edge halo, and color fringe.
- Apply a one-pixel edge contraction only after visual inspection and only when it does not erase fine structure.
- Keep a keyed-source version when manual compositing may be safer than automatic removal.

