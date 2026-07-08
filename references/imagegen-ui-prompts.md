# Imagegen UI Prompts

Use the shortest prompt that preserves the product meaning, essential behavior, and the selected reference's system-level structure. Leave visual expression open where the reference should carry it; do not describe the finished interface component by component. When relevant, name the platform or form factor, use representative real content instead of placeholders, and quote only critical on-screen copy. Treat these as selective tools, not required prompt fields. Require one image containing one interface screen only.

Write the prompt itself in English — the instructions, scene, style, and constraints — because imagegen follows English art direction most reliably. The one exception is the on-screen copy: reproduce every on-screen string verbatim in the product's own language, quoted, never translated into English and never paraphrased. So a prompt for a Chinese app reads as English direction with the Chinese UI text quoted inside it. Do not write the whole prompt in the product language; "product language" governs the quoted on-screen copy only.

When you present several art directions of the same screen, keep the product state and critical wording consistent, but do not force an identical full copy block into every prompt. A full repeated copy block can overpower the references and make every direction converge on the same layout. Author one source copy set, then choose the subset each reference skeleton can naturally support. Reuse any repeated string byte-identically, but allow different directions to show different amounts of supporting copy when that preserves distinct UI systems.

For each initial direction, use only its own Mobbin reference and state the runtime-decided influence boundary briefly. Make the Mobbin image primary for the interface system when combining it with a separate mood or art direction. In built-in imagegen mode, make the Mobbin image available locally, inspect it with `view_image`, then immediately call imagegen with a prompt that says `Use the image displayed immediately above this request as the attached reference image` and describes how to use that displayed image. Add `Ignore earlier generated prototype images and earlier reference images in this conversation; use only the image displayed immediately above for this direction.` Do not pass a Mobbin URL as an image reference, and do not treat the absence of an explicit image-path parameter in the built-in tool schema as proof that references are unavailable. Do not put local paths, URLs, or filenames inside the prompt; the `view_image` render is the attachment, and paths belong only in a separate tool-action checklist.

For the three initial directions, each prompt must name a different reference influence contract:

- **Preserve from the reference**: two or three system-level traits such as density, hierarchy, navigation rhythm, card geometry, spacing, hero-to-detail relationship, or control placement.
- **Translate for this product**: one sentence about product-specific subject matter or tone.
- **Do not copy**: brand, exact content, metrics, or product-specific UI from the reference.
- **Do not collapse into**: the sibling layout this direction must avoid, especially the first generated direction's dominant pattern.
- **Palette role**: the dominant neutral and accent colors this direction should use, derived from its own reference and separated from sibling directions.

Avoid putting the same layout contract in all three prompts. If the product requires a shared broad pattern, express it loosely and let each reference decide the detailed structure. Do not force every direction into the same hero/image top plus information panel bottom unless that is the selected direction's actual reference skeleton.

Avoid putting the same palette contract in all three prompts. Do not repeat one brand color phrase such as `evergreen accent`, `teal highlights`, or `blue-green supporting tones` across all exploration directions. Brand color may appear as a small connector, but each direction needs its own dominant palette temperature. If one direction is teal/blue-green, make the others visibly different, for example warm amber plus graphite, muted blue plus white, lavender plus charcoal, or restrained monochrome, as appropriate to their references.

If one direction uses a large scenic/weather hero, prompts for the other directions should explicitly say not to use a full-bleed scenic hero, not to use an upper-half weather painting, and not to use a lower white judgment panel unless their own reference has that structure. For card/list references, make the weather appear as small thumbnails, compact cards, or inline illustrations rather than a dominant hero image.

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
