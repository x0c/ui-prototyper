# Imagegen UI Prompts

Write prompts around the product and a deliberate visual proposition, not a reference or a component checklist. Mobbin informs the designer's judgment; it does not enter first-round imagegen calls.

## Prompt order

Put the direction charter first, because imagegen needs to know what makes this version visually unlike the other two. Then include:

1. **Visual proposition**: composition and reading path; dominant visual protagonist; contrast, repetition, alignment, proximity, color, material, typography, icon, or illustration intent.
2. **Screen truth**: what this screen enables and the user decision it supports.
3. **Product guardrails**: only the required actions, states, information, exact copy, and exclusions that would change product behavior if wrong.
4. **Reference scope, only in a later targeted edit**: attach an accepted anchor only after a direction was selected and a named craft failure remains. State the one visual dimension it may improve and forbid copying layout, structure, components, content, and identity. Omit this section for all first-round exploration calls.
5. **Critical copy**: quote exact on-screen strings in the product language.

Write instructions, scene, style, and constraints in English. Quote on-screen copy verbatim in the product language. For non-Latin copy, name the script explicitly, for example “Simplified Chinese characters”. Use real, representative content; placeholder text and lorem ipsum are forbidden. Require one image containing one interface screen only.

Name the platform or device class only when it materially affects the result. Do not pile up OS-version, component-fidelity, measurement, or full component-inventory language: that turns a visual exploration into the same safe template three times.

## Product guardrails without a visual straightjacket

List the functional elements that must be present, the ones that must not exist, and the exact text that matters. Do not phrase this as “show only” every visible object unless the user truly supplied a pixel-level specification. Functional constraints do not forbid non-functional design assets such as a meaningful signal visualization, an icon family, an illustration, a graphic system, or expressive typography.

Do not name Mobbin source products inside the prompt. The attachment should transfer visual craft, not product semantics. Keep exclusions short and specific. Use positive visual moves rather than blanket aesthetic bans such as “no cards, no shadows, no gradients, no illustrations”; those lists often erase the direction's visual vocabulary and leave a generic template. If the same unwanted element survives twice, describe the positive alternative rather than extending a negative list.

Keep product nouns out of art direction unless the user explicitly wants a literal theme. A useful visual asset must support comprehension, hierarchy, or product identity; it must not invent a person, feature, destination, or action.

## Research-first, reference-free exploration

Use Mobbin to sharpen direction charters, not as a mandatory input to the generator. First-round prompts must not include a reference image. This avoids literal transfer from a source product and prevents a small, generic, or product-specific screenshot from dominating the visual result.

After the user selects a direction, consider a source image only for a targeted edit. Ask privately: is its craft legible at the target scale; does it add one specific visual move beyond the selected direction; and can it transfer without importing the source screen's product body? If any answer is no, retain the research insight but do not attach the image. Tiny generic mobile screens, one-off product scenes, and sources whose appeal is inseparable from an article, recording timeline, meditation scene, or dashboard are usually research-only, not anchors.

Keep the product contract and shared scenario stable, but let each direction express it through a genuinely different visual system. Vary the composition, focal device, typography, density, color logic, material, grouping, and icon or illustration treatment when appropriate. Do not reuse the same “sidebar, status row, central card, utility strip” skeleton merely because it is familiar.

Build all first three prompts from their charters, not generic words such as “modern”, “premium”, or “beautiful”. Use reference-free generation as the default, not as an inferior control. If a later attachment makes the selected direction safer, more literal, or less memorable, discard it and retain the original.

Use only the copy each composition needs and paste common strings verbatim from one source. A direction is invalid if another direction could become it through a simple background or palette change.

## Charts and dense data

Image models render approximate charts and garble dense small labels. For dashboards and data screens:

- Name each chart type (line, bar, donut) instead of saying “chart” or “graph”.
- Supply the exact numbers, labels, and legend strings as content; never let the model invent figures.
- Keep dense small text to a minimum; prefer one clear figure over a wall of labels.
- Avoid 3D charts and pies with more than five segments.

## Editing a close result

When a generated screen is close, attach that prototype as the edit target. Preserve its validated product structure and change only the named failing detail. Do not attach a competitor screenshot as the edit target.

For a selected high-fidelity final that keeps drifting, use a short scaffold: visual proposition, screen truth, product guardrails, exact text, and avoid list. It is an intent checklist, not a component-by-component specification.
