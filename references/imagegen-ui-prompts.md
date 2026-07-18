# Imagegen UI Prompts

Write the prompt around the product, not around a reference. Use Mobbin research to improve judgment before generation; do not ask imagegen to recreate a competitor screen.

## Product-first prompt contract

Keep prompts short and include only what materially controls the result:

- **Product truth**: what the screen enables and for whom.
- **Required structure**: the hierarchy, content, actions, and states already justified by the product.
- **Allowed elements**: an exhaustive manifest of visible controls and entities; forbid anything not listed.
- **Original composition intent**: how this direction expresses that hierarchy without borrowing a source layout.
- **Visual language brief**: a compact craft description distilled from the anchor reference — typographic voice, palette behavior, spacing character, density, shape and depth language. This brief carries the design sense; write it with care, not as an afterthought.
- **Critical copy**: exact on-screen strings in the product language.
- **Exclusions**: product-specific elements that must not appear.

Write instructions, scene, style, and constraints in English. Quote on-screen copy verbatim in the product language. When the copy is non-Latin, name the script explicitly next to the quoted strings (for example, Simplified Chinese characters). Fill the screen with realistic, representative sample content and real-feeling data; placeholder text and lorem ipsum are forbidden. Require one image containing one interface screen only.

Name the platform and device class when they materially shape the result (native iOS chrome, Android Material behavior, or responsive web). One anchor phrase is enough; do not pile on OS version numbers, component-level fidelity vocabulary, or layout measurements, which compress composition into stale templates.

Do not name Mobbin source products inside the generation prompt. Do not describe their navigation, component sequence, or screen skeleton. Attach the anchor reference image by default: visual craft does not survive text-only distillation, and an unattached reference rarely influences the result. When attaching, scope it in the prompt — state which visual dimensions the image may influence (typography, spacing, color behavior, material, composition feel) and forbid copying its layout, structure, components, and content. If the user explicitly requests close emulation, disclose that tradeoff and scope the attachment to the requested visual dimension.

Keep exclusion lists short and specific. If the same unwanted element survives two generations, rephrase the exclusion as a positive description of what belongs there instead of lengthening the negative list.

Keep product nouns out of the art direction unless the user explicitly wants a literal theme. Words such as butler, premium, friendly, finance, health, or AI define content and behavior; they do not justify portraits, mascots, gold-and-cream luxury styling, neon futurism, or decorative heroes.

For three exploration directions, keep the same product contract and core scenario. Change composition and visual language, not product capabilities or vocabulary. Use only the copy each composition needs, while keeping repeated strings byte-identical.

## Charts and dense data

Image models render approximate charts and garble dense small labels. For dashboards and data screens:

- Name each chart type (line, bar, donut) instead of saying "chart" or "graph".
- Supply the exact numbers, labels, and legend strings as content; never let the model invent figures.
- Keep dense small text to a minimum; prefer one clear figure over a wall of labels.
- Avoid 3D charts and pies with more than five segments.

## Editing a close result

When a generated screen is close, attach that generated prototype as the edit target. Keep its validated product structure and change only the named failing detail. Do not attach a competitor screenshot as the edit target.

## Optional scaffold for a drifting final

Use this only when a selected high-fidelity final keeps drifting:

- **Use case / asset**: one shippable screen and its product job.
- **Product contract**: required hierarchy, actions, states, and exclusions.
- **Original composition**: one sentence defining this direction's own layout logic.
- **Visual principles**: the visual language brief, compressed to a few lines.
- **Text**: exact product-language copy.
- **Avoid**: unapproved features, source-product remnants, imitation, clutter, and extra screens.

Keep every line short. This is an intent checklist, not a component-by-component specification.
