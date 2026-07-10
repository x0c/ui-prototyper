---
name: ui-prototyper
description: "Create UI/UX prototype images for mobile apps, web apps, websites, dashboards, and other digital interfaces. Use Mobbin MCP for references and imagegen for final images."
---

# UI Prototyper

Create UI/UX prototypes. Stay within UI/UX design unless product strategy is explicitly requested.

## Explore

Use Mobbin MCP before proposing a design direction and inspect the returned images:

- `mcp__mobbin.search_flows`: multi-step flows.
- `mcp__mobbin.search_screens`: individual product screens and states.
- `mcp__mobbin.search_sections`: website sections.

Separate functional relevance from visual quality. A screen is not a valid primary reference merely because it has the right feature; it must also express a strong, current visual system appropriate to the target platform. Search adjacent product categories when the functionally closest results look dated or generic. When available, inspect two or three screens from the same product or flow to verify that the chosen screen represents a coherent system rather than a one-off state.

For the three initial directions, choose three visually distinct primary references. Inspect each screen, do not reuse one reference across directions, and show the user each Mobbin link with its intended influence. Reject a candidate before generation when its typography, density, platform chrome, iconography, material treatment, or control scale already looks dated or conflicts with the target product.

For every Mobbin image selected as a primary reference, make the actual image visible in the conversation before calling imagegen. If the Mobbin tool returns a local image path, inspect that file with `view_image`. If it returns only a remote image or page URL, download or otherwise materialize the screenshot locally, then inspect it with `view_image`. Treat this displayed image as the imagegen reference; do not conclude that imagegen cannot use references just because the built-in tool call schema has only a text `prompt` field.

Reference attachment rule: writing a local path or URL inside the prompt is not an attachment. Inspect every primary reference with `view_image`. When the imagegen tool exposes an explicit local-reference input such as `referenced_image_paths`, pass the materialized Mobbin image through it as well; use the displayed-image context only as a fallback when no explicit image input exists. Never rely on prose alone after a local reference is available.

Do not ask preference questions by default. Infer the design direction, representative content, and sample data from the user's request and available materials, then generate immediately. Ask only when a required asset or product fact is missing, cannot be reasonably inferred, and would make the prototype unusable; keep that blocking question concise.

## Establish the design language

Generate three alternative versions of the main screen before designing the rest of a flow. They must read as three coherent and clearly different design languages, not superficial variants of one system. If they do not, regenerate the weak direction.

Generate the three directions with three separate imagegen calls. Every call must produce one image containing one interface screen only, never a multi-screen composition.

Present the three images separately and briefly explain the experiential difference between them. Wait for the user to select or combine a direction before generating any other screen. After selection, preserve that design language across the remaining screens, generating every screen with its own imagegen call.

Pass each selected Mobbin image to its corresponding imagegen call and use it only for that direction. Inspect it with `view_image`, attach the local image through the strongest supported image-input mechanism, and tell imagegen to ignore earlier prototype and reference images. Do not put local paths, remote URLs, or file labels inside the prompt text. Treat the Mobbin image as the source interface system, not a mood board: preserve its scale, density, typography hierarchy, spacing rhythm, component geometry, material, elevation, control placement, and icon weight unless a product requirement makes one of those dimensions inapplicable. Skip the image input only when the user explicitly asks not to use it.

Translate the reference instead of theming the product noun. Change product-specific copy, data, actions, and restrained brand accents; do not turn words such as “butler”, “premium”, “friendly”, “finance”, or “AI” into an invented visual costume. Unrequested portraits, mascots, luxury styling, sci-fi styling, decorative gradients, and oversized hero treatments are reference-fidelity failures.

Do not neutralize the three references with the same over-specified layout, the same full copy block, or the same dominant palette. Shared product constraints are allowed, and the core scenario should stay comparable, but each direction must keep a different system-level skeleton from its own reference: information density, navigation rhythm, hero-to-detail relationship, card shape language, spacing, control placement, palette temperature, accent hierarchy, and visual emphasis. Let the reference determine which pieces of copy appear, where they appear, how much supporting text fits, and which non-brand colors carry the screen. If two prompts contain the same layout sentence, the same full on-screen copy list, the same color instruction, or would naturally produce the same screen with different artwork, rewrite them before generation.

Before writing the three initial prompts, create a private divergence matrix with one row per direction:

- **Reference skeleton to preserve**: the layout structure that must survive generation.
- **Visual-system signature**: the reference's density, type hierarchy, material, geometry, and control scale that must remain recognizable.
- **Forbidden sibling pattern**: the pattern this direction must not collapse into, especially the strongest previous or first direction.
- **Copy scope**: the minimal copy needed to prove the same product state without forcing the same layout.
- **Palette role**: the reference-derived dominant neutrals and accents; do not invent a new theme merely to make siblings look different.

Use the matrix to write prompts. If the only honest prompt still describes the same skeleton as another direction, choose a different Mobbin reference before generating. Let each reference supply its own palette and material system; use the product brand as a restrained connector unless the user supplied a complete design system.

## Imagegen

Read `references/imagegen-ui-prompts.md` and `references/visual-quality-gate.md`, then use `imagegen` to generate the final prototype images.

Do not show generation prompts or ask for approval by default. After inspecting the references, compose and self-check the prompts privately, give the user a concise progress update with the selected Mobbin links and intended influence, and generate immediately. Show prompts first only when the user explicitly asks to review or edit them; if the user supplies wording, reproduce it exactly.

Every prompt must be finished before use: complete sentences with no truncated, spliced, or dangling clauses; balanced quotation marks, brackets, and parentheses; and verbatim on-screen copy wherever the same string is intentionally reused. Keep local paths, URLs, filenames, and tool-action notes out of the prompt. Do not force byte-identical full copy blocks across all three directions when that would collapse the layouts; reuse only the core scenario copy that each reference skeleton can naturally support.

Before the three initial imagegen calls, use this direct-generation checklist:

1. Confirm there are three different Mobbin primary references, one per direction.
2. Confirm each primary reference has been inspected visually via `view_image`.
3. Confirm each private prompt passes the copy, syntax, layout-divergence, and palette-divergence checks.
4. Execute each direction as: call `view_image` for that direction's Mobbin reference -> attach that local reference through the strongest supported image input -> call imagegen with the prepared prompt -> inspect the result before moving to the next direction. The prompt must explicitly isolate the current reference from earlier images.

If a reference image cannot be made visible in the conversation, try another suitable Mobbin reference. If none can be attached, report the blocker instead of generating while implying that a reference was attached. Continue with text-only influence only when the user explicitly requested it.

Inspect every generated image against `references/visual-quality-gate.md` and its primary Mobbin reference. Also compare the three generated directions against each other; if two share the same skeleton and differ mostly by artwork, color, or copy, treat the weaker one as failed. Do not show failed drafts as valid options. If reference fidelity or contemporary platform quality fails, first regenerate with a shorter reference-translation prompt and stronger explicit attachment; after a second failure, replace the reference instead of accumulating negative instructions. If the result is already close, edit it in place and change only the failing detail.
