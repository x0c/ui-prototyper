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

Treat this contract as authoritative. Infer reasonable sample content and presentation details, but ask one concise question when a missing fact would materially change the product behavior. Build a private product skeleton from the contract before viewing references. Mobbin must not add features, navigation, entities, terminology, or workflows to that skeleton.

Require every visible element in the generated screen to trace back to the product contract. If an element exists only because it appeared in a reference, remove it.

## Research scoped design principles

Use Mobbin after the product skeleton is locked:

- `mcp__mobbin.search_flows`: multi-step flows.
- `mcp__mobbin.search_screens`: individual product screens and states.
- `mcp__mobbin.search_sections`: website sections.

Search for specific design problems such as composer density, inline decisions, hierarchy, typography, material, or state communication rather than a complete product to imitate. Inspect the returned images. Prefer visually strong, current references, including adjacent categories when they solve the design problem better.

Create a private influence ledger for each direction:

- **Allowed influence**: one to three scoped principles such as density, typography rhythm, material restraint, or action emphasis.
- **Forbidden influence**: the reference's product structure, navigation, content, terminology, brand-specific controls, and distinctive full-screen composition.

Show the user each Mobbin link and the scoped principle it informed. Do not present a reference as the screen to copy.

Do not attach a full competitor screen to imagegen by default. Full-screen attachments strongly bias composition and can turn research into imitation. Attach a Mobbin image only when the user explicitly requests close emulation or when a narrowly cropped reference is needed for one visual detail; state that narrow influence in the prompt. Never attach a reference merely because the tool supports image input.

## Establish the design language

Generate three original versions of the main screen before expanding a flow. Keep the product contract, information hierarchy, required actions, and product vocabulary consistent across all three. Vary visual language through composition, typography, density, material, color behavior, and interaction expression without inventing new product capabilities.

Generate each direction with a separate imagegen call. Every call must produce one image containing one interface screen only. Present the three images separately and wait for the user to select or combine a direction before generating other screens.

Do not ask for prompt approval by default. Infer designer-owned details, provide a concise progress update, and generate directly. Show prompts first only when the user explicitly asks to review them.

## Imagegen

Read `references/imagegen-ui-prompts.md` and `references/visual-quality-gate.md` before generating.

Build prompts in this priority order:

1. Product truth and screen job.
2. Locked information hierarchy, required actions, and prohibited elements.
3. Original composition intent.
4. Scoped visual principles distilled from Mobbin research.
5. Critical on-screen copy in the product language.

Use brand-new generation without competitor image attachments by default. Keep prompts concise and do not name source products inside the generation prompt. Product meaning must dominate visual influence.

Inspect every result against the quality gate. Reject any draft that contains an element not justified by the product contract, resembles one source screen's overall composition, retains source-product controls or concepts, or looks visually dated. Fix a close result in place; otherwise regenerate from the product skeleton with narrower research influence. Show only directions that pass product fidelity, originality, and visual quality.
