---
name: ui-prototyper
description: "Create product-first UI/UX prototype images for mobile apps, web apps, websites, dashboards, and other digital interfaces. Use Mobbin MCP for scoped design research and imagegen for original final images without letting references redefine the product."
---

# UI Prototyper

Create original UI/UX prototypes that serve the product. Stay within UI/UX design unless product strategy is explicitly requested.

## Lock the product before researching visuals

Before using Mobbin, extract a private product contract from the user's request and materials:

- the screen's job and primary user intent;
- required information, actions, and states;
- information hierarchy and navigation constraints;
- platform, brand, and accessibility constraints;
- elements the product must not contain.

Treat this contract as authoritative for structure and content. Infer reasonable sample content and presentation details, but ask one concise question when a missing fact would materially change the product behavior. Build a private product skeleton from the contract before viewing references. Mobbin must not add features, navigation, entities, terminology, or workflows to that skeleton.

The contract locks what exists, never how it looks. Visual language — composition, typography, color, material, spacing character — stays open at this stage and is decided later from design references. Never derive visual style from product semantics, brand adjectives, or the current implementation's existing UI; that path produces engineer-drawn screens.

Require every visible element in the generated screen to trace back to the product contract. If an element exists only because it appeared in a reference, remove it.

## Research scoped design principles

Use Mobbin after the product skeleton is locked:

- `mcp__mobbin.search_flows`: multi-step flows.
- `mcp__mobbin.search_screens`: individual product screens and states.
- `mcp__mobbin.search_sections`: website sections.

Search for specific design problems such as composer density, inline decisions, hierarchy, typography, material, or state communication rather than a complete product to imitate. For a component-level problem, compare that component across many products instead of studying one product's whole screen. Inspect the returned images. Prefer visually strong, current references, including adjacent categories when they solve the design problem better.

Choose each direction's anchor reference primarily for visual craft worth absorbing — typography, spacing, color, and material that look current and ambitious — even when it comes from an adjacent category. A functionally matching but visually ordinary reference produces ordinary output.

Create a private influence ledger for each direction:

- **Allowed influence**: the reference's full visual craft — composition energy, typographic voice, spacing rhythm, density, color behavior, material, depth, and shape language. Absorb the visual system deeply, not one or two token principles.
- **Forbidden influence**: the reference's product semantics — structure, navigation, content, entities, terminology, workflows, and brand-specific controls. Same visual soul, different product body.

Show the user each Mobbin link and the visual influence it informed. Do not present a reference as the screen to copy.

Attach the direction's anchor reference to imagegen by default when the tool accepts image input. Text-only distillation loses exactly the qualities that make a reference worth using, and unattached research drifts back to generic output. Scope the attachment explicitly in the prompt: absorb the visual language, do not copy the layout, structure, components, or content. Use a narrow crop when only one detail matters, and never attach a reference without stating its intended influence.

## Establish the design language

Generate three original versions of the main screen before expanding a flow. Keep the product contract, information hierarchy, required actions, and product vocabulary consistent across all three. Vary visual language through composition, typography, density, material, color behavior, and interaction expression without inventing new product capabilities. Anchor each direction on a different reference with a distinct visual language; three directions that share one reference's look are a failed exploration.

Generate each direction with a separate imagegen call. Every call must produce one image containing one interface screen only. Present the three images separately and wait for the user to select or combine a direction before generating other screens. When expanding a flow, generate empty, loading, and error states as separate one-screen calls in the selected design language.

Do not ask for prompt approval by default. Infer designer-owned details, provide a concise progress update, and generate directly. Show prompts first only when the user explicitly asks to review them.

## Imagegen

Read `references/imagegen-ui-prompts.md` and `references/visual-quality-gate.md` before generating.

Build prompts in this priority order:

1. Product truth and screen job.
2. Locked information hierarchy, required actions, and prohibited elements.
3. Original composition intent.
4. Visual language brief distilled from the anchor reference, plus the reference attachment itself.
5. Critical on-screen copy in the product language.

Before calling imagegen, derive an allowed-element manifest from the product contract and state that no other visible controls or entities may appear. Attach the anchor reference with its explicit visual-only scope. Keep prompts concise and do not name source products inside the generation prompt. The manifest governs what exists; the reference governs how it looks.

Inspect every result by inventorying all visible controls and entities against the allowed-element manifest, then apply the quality gate. Reject any draft that contains an unlisted element, copies the reference's layout or structure, retains source-product controls or concepts, or looks stiff, dated, or generic. Fix a close result in place; otherwise regenerate — strengthen the visual transfer or switch the anchor reference rather than adding more specification. Show only directions that pass product fidelity, originality, and visual quality.
