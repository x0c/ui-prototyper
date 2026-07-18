---
name: ui-prototyper
description: "Create product-faithful, visually ambitious UI/UX prototype images for mobile apps, web apps, websites, and dashboards. Use Mobbin selectively as design research and imagegen to explore genuinely different original directions without copying a reference or inventing product behavior."
---

# UI Prototyper

Create original UI/UX prototypes that serve the product. Stay within UI/UX design unless product strategy is explicitly requested.

## Separate product truth from presentation freedom

Before researching visuals, establish a private product contract:

- the screen's job, user intent, required information, actions, states, navigation boundaries, exact copy, and exclusions;
- any information hierarchy or placement explicitly fixed by the user;
- platform, brand, and accessibility constraints.

The contract locks product capabilities and user-specified hierarchy, not a wireframe. Unless the user supplied a detailed layout specification, do not turn it into a fixed rail, header, card, panel, or control sequence before exploration. A functional control, data entity, or navigation item must trace to the product contract. A non-functional visual element must trace to the selected design direction: typography, iconography, illustration, visual metaphor, material, color, or compositional device are allowed when they clarify the product's job without implying a new capability.

Do not infer visual style from product semantics, brand adjectives, or the existing implementation. That path produces engineer-drawn reskins.

## Research visual systems, then let a reference earn attachment

Use Mobbin after the contract is locked when it can answer a specific visual question:

- `mcp__mobbin.search_flows` for multi-step flows.
- `mcp__mobbin.search_screens` for screen and state problems.
- `mcp__mobbin.search_sections` for web composition problems.

Search for the visual problem that needs solving: hierarchy, reading cadence, compositional tension, typographic voice, color behavior, material, density, illustration, icon language, or state communication. Inspect the returned images. Adjacent categories are welcome when their design craft solves the problem better.

Do not treat a found screen as an automatic imagegen attachment. Give it a private attachment check. Attach it only when its visual system is visibly strong at the target screen size, contributes a concrete move not already present in the direction charter, and can transfer without borrowing its core product semantics. Reject a reference whose appeal depends mainly on its product-specific scene, feature, timeline, article, dashboard, or one-off illustration; a generic native screen is not a visual anchor.

Create a private influence ledger for an accepted anchor. It may deeply influence composition energy, typography, spacing, color, material, depth, shape language, and visual assets. It must not contribute product semantics: structure, navigation, content, entities, terminology, workflows, or brand-specific controls. Same visual soul, different product body.

Show the user any Mobbin links that informed a direction. The first exploratory batch is generated from the direction charters alone: do not attach competitor or Mobbin images to those calls. This preserves the research insight without giving a source image enough visual weight to pull the result back to its familiar product template.

Consider attaching an accepted anchor only after a user selects a direction and a specific craft problem remains unsolved. The attachment must have a named purpose—such as repairing typographic rhythm, material, or spatial tension—and it must be used for a targeted edit, not to redraw the selected product screen wholesale.

## Author three irreducible directions

Before generating, write a private direction charter for each option. It must name:

- the composition and reading-path thesis;
- the dominant visual protagonist (for example, type, a live signal, an illustration, a graphic system, or a material field);
- the intended contrast, repetition, alignment, proximity, and color behavior;
- the handling of iconography or illustration when it improves comprehension or gives the screen a memorable identity.

The three charters must be visually incompatible, not alternate palettes for one composition. If changing the colors would make one charter indistinguishable from another, discard it. When the product does not dictate a fixed layout, explore different spatial topologies and ways of grouping the same capabilities. Preserve product behavior and mandatory hierarchy; do not preserve an unrequested component sequence.

The first exploration batch is reference-free unless the user explicitly asks to emulate, combine, or attach a supplied/named source. This is not a weaker fallback: it prevents a source image from overpowering the original design proposition. Write charters as positive visual moves; do not replace art direction with a long list of aesthetic prohibitions.

Illustration and icons are neither mandatory decoration nor forbidden by a functional manifest. Use a product-relevant visual device when it makes a state, rhythm, or concept easier to understand; never add a mascot, photo, or control merely to make the screen look designed.

## Generate and inspect

Read `references/imagegen-ui-prompts.md` and `references/visual-quality-gate.md` before generating.

Generate one interface screen per imagegen call and one call per direction. Start every prompt with the direction charter, then state the screen job and concise product guardrails. Keep shared product-language copy byte-identical across directions. Do not attach Mobbin images during first-round exploration. Do not ask for prompt approval unless the user explicitly asks to review prompts.

Use a manifest only to lock required functional elements, states, exact copy, and truly prohibited product behavior. Do not use an exhaustive "show only" inventory that bans every icon, illustration, graphic treatment, or alternate grouping and collapses exploration into a reskin.

Inspect each result against the product contract and quality gate. Then inspect the three results side by side. Reject and regenerate any direction that is merely a palette, theme, or material swap of another, even when it independently looks polished. Present only three directions that pass product fidelity, originality, craft, and pairwise divergence. After the user selects or combines a direction, generate additional screens and empty, loading, and error states as separate one-screen calls in that chosen system. Use a qualifying Mobbin attachment only for a targeted later edit when the selected direction has a named craft failure.
