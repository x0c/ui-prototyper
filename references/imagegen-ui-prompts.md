# Imagegen UI Prompts

Use the shortest prompt that translates the selected reference into the user's product. Make reference fidelity stronger than descriptive art direction: preserve the reference's system-level structure and visual grammar, then change only product meaning, essential behavior, critical copy, and restrained brand accents. Do not describe the finished interface component by component. Require one image containing one interface screen only.

Write the prompt itself in English — the instructions, scene, style, and constraints — because imagegen follows English art direction most reliably. The one exception is the on-screen copy: reproduce every on-screen string verbatim in the product's own language, quoted, never translated into English and never paraphrased. So a prompt for a Chinese app reads as English direction with the Chinese UI text quoted inside it. Do not write the whole prompt in the product language; "product language" governs the quoted on-screen copy only.

When you prepare several art directions of the same screen, keep the product state and critical wording consistent, but do not force an identical full copy block into every prompt. A full repeated copy block can overpower the references and make every direction converge on the same layout. Author one source copy set, then choose the subset each reference skeleton can naturally support. Reuse any repeated string byte-identically, but allow different directions to show different amounts of supporting copy when that preserves distinct UI systems.

For each initial direction, use only its own Mobbin primary reference. Materialize it locally and inspect it with `view_image`. When imagegen accepts explicit local image inputs, pass the local Mobbin image through that mechanism; otherwise use the displayed image as context. State that this reference is the source interface system, not a mood board, and isolate it from earlier images. Do not put local paths, URLs, or filenames inside the prompt.

Prefer a compact reference-translation contract such as: `Use the attached reference as the source interface system. Preserve its content scale, density, typography hierarchy, spacing rhythm, geometry, material, control placement, and icon weight. Translate only the copy, data, actions, and restrained brand accents for <product>.` Remove any listed dimension that does not apply to the inspected reference.

Keep product nouns out of the art direction unless the user explicitly wants a literal theme. Words such as butler, premium, friendly, finance, health, or AI should define content and behavior, not automatically create portraits, mascots, gold-and-cream luxury styling, neon futurism, or decorative heroes.

For the three initial directions, each prompt must name a different reference influence contract:

- **Preserve from the reference**: the system-level traits that make it recognizable, including scale, density, type hierarchy, geometry, material, spacing, and control placement.
- **Translate for this product**: one sentence about product-specific subject matter or tone.
- **Do not copy**: brand, exact content, metrics, or product-specific UI from the reference.
- **Do not collapse into**: the sibling layout this direction must avoid, especially the first generated direction's dominant pattern.
- **Palette role**: the reference-derived dominant neutral and accents, changed only when the product already has a defined brand system.

Avoid putting the same layout contract in all three prompts. If the product requires a shared broad pattern, express it loosely and let each reference decide the detailed structure. Do not force every direction into the same hero/image top plus information panel bottom unless that is the selected direction's actual reference skeleton.

Do not force artificial palette separation. Distinct primary references should naturally produce distinct palette temperatures and material systems. If three results still converge, replace a reference rather than inventing arbitrary color themes.

When a generated screen is already close, correct it by editing in place instead of regenerating from text. Make the generated image visible with `view_image`, name it in the next prompt as the edit target, and instruct the model to keep the entire layout, hierarchy, on-screen copy, and spacing unchanged while changing only the one named thing (for example an illustration's medium, or a single tab label). You may show one external real-product screenshot — not only a Mobbin image — as a secondary system reference in the same conversation to anchor the correction. This preserves what already works and keeps the correction from drifting back into a full UI specification.

## Optional scaffold for high-fidelity finals

The default above — short prompt, reference-carried visual direction — is what the three exploration directions must use. For a single high-fidelity *final* screen, when a short prompt keeps drifting to a generic template, you may instead write a structured scaffold. Use it only at the finishing stage and only for the one screen being finalized; never for the three exploration directions. It trades some composition freedom for reliability, so reach for it when short prompts have already failed, not by default. The fields, each one line:

- **Use case / Asset type**: e.g. `ui-mockup` · `shippable high-fidelity iOS home screen for <product>`.
- **Image N role**: for every visible reference image, state what to preserve from it (interface system) and what not to copy (branding, metrics).
- **Primary request**: one single screen, the page/state, and the concrete scene.
- **Style/medium**: the art direction in one phrase.
- **Text (verbatim)**: quote every on-screen string exactly, in the product language.
- **Constraints**: the few unbreakable spatial/interaction rules (e.g. a clear upper-stage/lower-information split, practical tap targets, one interface screen only).
- **Avoid**: an explicit negative list of the clutter this product must not show (scores, percentages, raw weather numbers, charts, stacked cards, stickers, emoji, photo background, login, watermark, extra device frames).

Keep every line short; the scaffold is a checklist of intent, not a component-by-component UI specification. If a field adds nothing for this screen, drop it.
