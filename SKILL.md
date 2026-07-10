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

Use the references for design insight without copying a complete product. For the three initial directions, choose three visually distinct primary references; prefer different products when they provide the strongest contrast, but optimize for reference quality rather than provenance. Inspect each screen, do not reuse one reference across directions, and show the user each Mobbin link with its intended influence.

For every Mobbin image selected as a primary reference, make the actual image visible in the conversation before calling imagegen. If the Mobbin tool returns a local image path, inspect that file with `view_image`. If it returns only a remote image or page URL, download or otherwise materialize the screenshot locally, then inspect it with `view_image`. Treat this displayed image as the imagegen reference; do not conclude that imagegen cannot use references just because the built-in tool call schema has only a text `prompt` field.

Reference attachment rule: writing a local path or URL inside the prompt is not an attachment. The attachment is the image that was actually displayed in the conversation with `view_image` immediately before the imagegen call. Never say "imagegen can only receive text prompts", "there is no image input parameter, so references cannot be attached", or "I will use the Mobbin image as text-only influence" after a `view_image` path is available. Those are execution errors. If a reference image can be displayed with `view_image`, use it as the image input context and proceed through imagegen.

Do not ask preference questions by default. Infer the design direction, representative content, and sample data from the user's request and available materials, then generate immediately. Ask only when a required asset or product fact is missing, cannot be reasonably inferred, and would make the prototype unusable; keep that blocking question concise.

## Establish the design language

Generate three alternative versions of the main screen before designing the rest of a flow. They must read as three coherent and clearly different design languages, not superficial variants of one system. If they do not, regenerate the weak direction.

Generate the three directions with three separate imagegen calls. Every call must produce one image containing one interface screen only, never a multi-screen composition.

Present the three images separately and briefly explain the experiential difference between them. Wait for the user to select or combine a direction before generating any other screen. After selection, preserve that design language across the remaining screens, generating every screen with its own imagegen call.

Pass each selected Mobbin image to its corresponding imagegen call by default and use it only for that direction. In built-in imagegen mode, "pass" means: first show exactly that local image with `view_image`, then call imagegen immediately afterward with a prompt that names the attached reference as "the image displayed immediately above this request". Also tell imagegen to ignore earlier generated prototype images and earlier reference images in the same conversation; otherwise previous directions can leak into later directions. Do not put local paths, remote URLs, or file labels inside the prompt text; keep them only in your private tool checklist or user-facing reference list outside the prompt. Treat the displayed image as the primary reference for the interface system; other creative style or art-direction ideas are secondary and must not reduce the reference to an isolated visual detail. Decide the exact influence boundary at runtime after inspecting it. Skip the image input only when the user explicitly asks not to use it.

Do not neutralize the three references with the same over-specified layout, the same full copy block, or the same dominant palette. Shared product constraints are allowed, and the core scenario should stay comparable, but each direction must keep a different system-level skeleton from its own reference: information density, navigation rhythm, hero-to-detail relationship, card shape language, spacing, control placement, palette temperature, accent hierarchy, and visual emphasis. Let the reference determine which pieces of copy appear, where they appear, how much supporting text fits, and which non-brand colors carry the screen. If two prompts contain the same layout sentence, the same full on-screen copy list, the same color instruction, or would naturally produce the same screen with different artwork, rewrite them before generation.

Before writing the three initial prompts, create a private divergence matrix with one row per direction:

- **Reference skeleton to preserve**: the layout structure that must survive generation.
- **Forbidden sibling pattern**: the pattern this direction must not collapse into, especially the strongest previous or first direction.
- **Copy scope**: the minimal copy needed to prove the same product state without forcing the same layout.
- **Palette role**: the dominant neutrals and one or two accent colors this direction should use, derived from the reference and separated from sibling directions.

Use the matrix to write prompts. For any direction whose reference is not a large hero/weather-stage screen, explicitly forbid a full-bleed scenic hero image, an upper-half weather painting, and a lower white judgment panel unless that structure exists in the reference. If the only honest prompt still describes the same skeleton as another direction, choose a different Mobbin reference before generating.

Treat the product brand color as a connector, not a flood fill. Do not put the same phrase such as "evergreen accent", "teal highlights", "blue-green supporting tones", or an equivalent color family into all three prompts. At most one exploration direction may use teal/blue-green as the dominant accent unless the user explicitly asks for a teal brand study. For the others, keep the brand color in logos, selected controls, or tiny status marks while letting the reference supply a different palette temperature, such as warm amber, graphite, muted blue, lavender, or restrained monochrome. If the prompt would make all generated screens read as the same color system, rewrite the palette line before generation.

## Imagegen

Read `references/imagegen-ui-prompts.md`, then use `imagegen` to generate the final prototype images.

Do not show generation prompts or ask for approval by default. After inspecting the references, compose and self-check the prompts privately, give the user a concise progress update with the selected Mobbin links and intended influence, and generate immediately. Show prompts first only when the user explicitly asks to review or edit them; if the user supplies wording, reproduce it exactly.

Every prompt must be finished before use: complete sentences with no truncated, spliced, or dangling clauses; balanced quotation marks, brackets, and parentheses; and verbatim on-screen copy wherever the same string is intentionally reused. Keep local paths, URLs, filenames, and tool-action notes out of the prompt. Do not force byte-identical full copy blocks across all three directions when that would collapse the layouts; reuse only the core scenario copy that each reference skeleton can naturally support.

Before the three initial imagegen calls, use this direct-generation checklist:

1. Confirm there are three different Mobbin primary references, one per direction.
2. Confirm each primary reference has been inspected visually via `view_image`.
3. Confirm each private prompt passes the copy, syntax, layout-divergence, and palette-divergence checks.
4. Execute each direction as: call `view_image` for that direction's Mobbin reference -> call imagegen with the prepared prompt -> inspect the result before moving to the next direction. Do this even if the same image was displayed earlier while exploring; the last visible image before each imagegen call should be that direction's primary reference. The prompt must explicitly say to ignore previous generated prototype images and use only this immediately preceding reference for the current direction.

If a reference image cannot be made visible in the conversation, try another suitable Mobbin reference. If none can be attached, report the blocker instead of generating while implying that a reference was attached. Continue with text-only influence only when the user explicitly requested it.

Inspect every generated image for single-screen compliance, UI/UX consistency, design quality, duplicated on-screen copy or controls, palette separation, and meaningful system-level influence from its Mobbin reference. Also compare the three generated directions against each other; if two directions share the same skeleton and differ mostly by artwork, color, or copy, or if all three read as the same teal/blue-green color system, treat the weaker one as failed even if it is visually polished. Do not tell the user that a failed direction succeeded. Stop, mark the draft invalid, and present a corrected prompt for that direction before generating more directions. If the user or your own inspection indicates the result did not meaningfully use the Mobbin reference, regenerate it after re-displaying the correct Mobbin image with `view_image`; do not pivot to HTML/CSS or text-only reference generation unless the user explicitly asks for a deterministic non-imagegen workflow. If the reference appears to have influenced only decoration or one isolated region, or one detail is off, apply the smallest targeted correction instead of expanding the prompt into a full UI specification. Prefer editing in place by making the generated image visible with `view_image`, naming it as the edit target in the next prompt, and changing only the one named thing, rather than regenerating the whole screen from text.
