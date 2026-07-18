---
name: ui-prototyper
description: "Create product-faithful, visually ambitious UI/UX prototype images for mobile apps, web apps, websites, and dashboards. Use Mobbin MCP for focused design research and imagegen to explore genuinely different design directions without copying a reference or inventing product behavior."
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

## Research visual systems, not competitor products

Use Mobbin after the contract is locked:

- `mcp__mobbin.search_flows` for multi-step flows.
- `mcp__mobbin.search_screens` for screen and state problems.
- `mcp__mobbin.search_sections` for web composition problems.

Search for the visual problem that needs solving: hierarchy, reading cadence, compositional tension, typographic voice, color behavior, material, density, illustration, icon language, or state communication. Inspect the returned images. Choose a visually ambitious anchor for each direction; adjacent categories are welcome when their design craft solves the problem better.

Create a private influence ledger for each direction. The anchor may deeply influence composition energy, typography, spacing, color, material, depth, shape language, and visual assets. It must not contribute product semantics: structure, navigation, content, entities, terminology, workflows, or brand-specific controls. Same visual soul, different product body.

Show the user the three Mobbin links and the visual influence each informed. Attach that direction's anchor image to its imagegen call whenever image input is available. In the prompt, explicitly scope the attachment to visual craft and forbid copying its layout, structure, components, content, and identity.

## Author three irreducible directions

Before generating, write a private direction charter for each option. It must name:

- the composition and reading-path thesis;
- the dominant visual protagonist (for example, type, a live signal, an illustration, a graphic system, or a material field);
- the intended contrast, repetition, alignment, proximity, and color behavior;
- the handling of iconography or illustration when it improves comprehension or gives the screen a memorable identity.

The three charters must be visually incompatible, not alternate palettes for one composition. If changing the colors would make one charter indistinguishable from another, discard it. When the product does not dictate a fixed layout, explore different spatial topologies and ways of grouping the same capabilities. Preserve product behavior and mandatory hierarchy; do not preserve an unrequested component sequence.

Illustration and icons are neither mandatory decoration nor forbidden by a functional manifest. Use a product-relevant visual device when it makes a state, rhythm, or concept easier to understand; never add a mascot, photo, or control merely to make the screen look designed.

## Generate and inspect

Read `references/imagegen-ui-prompts.md` and `references/visual-quality-gate.md` before generating.

Generate one interface screen per imagegen call and one call per direction. Start every prompt with the direction charter, then state the screen job and concise product guardrails. Keep shared product-language copy byte-identical across directions. Do not ask for prompt approval unless the user explicitly asks to review prompts.

Use a manifest only to lock required functional elements, states, exact copy, and truly prohibited product behavior. Do not use an exhaustive "show only" inventory that bans every icon, illustration, graphic treatment, or alternate grouping and collapses exploration into a reskin.

Inspect each result against the product contract and quality gate. Then inspect the three results side by side. Reject and regenerate any direction that is merely a palette, theme, or material swap of another, even when it independently looks polished. Present only three directions that pass product fidelity, originality, craft, and pairwise divergence. After the user selects or combines a direction, generate additional screens and empty, loading, and error states as separate one-screen calls in that chosen system.
