# Visual Quality Gate

Use this gate after every generated prototype and compare the result directly with its primary reference. Do not judge “modern” from adjectives alone.

## Reference selection

Reject a primary reference when it is only functionally relevant but visually generic, dated, or mismatched to the target platform. Prefer a visually excellent adjacent-category screen over a mediocre exact-category match. Verify the system across nearby screens from the same product when possible.

## Reference fidelity

Require the generated screen to retain the reference's recognizable:

- content scale and information density;
- typography hierarchy and line-length rhythm;
- spacing, margins, and content width;
- component geometry, corner treatment, borders, elevation, and material;
- navigation and composer placement;
- icon scale, weight, and visual restraint.

Changing copy, data, actions, and restrained brand accents is expected. Replacing the reference system with a generic template is not.

## Automatic failure signals

Unless the user or primary reference explicitly requests them, fail a draft that introduces:

- oversized headings, buttons, pills, cards, or excessive empty space;
- thick borders, heavy shadows, glossy gradients, or every element inside a rounded container;
- a hamburger menu, floating avatar, portrait, mascot, emblem, or decorative hero absent from the reference;
- faux-luxury shorthand such as cream, gold, serif type, and a suited person merely because the product is called a butler or premium;
- faux-futuristic shorthand such as neon, excessive glass, glowing gradients, or sci-fi controls merely because the product uses AI;
- Android Material patterns in an iOS prototype, or platform chrome inconsistent with the reference;
- desktop-like scale, implausible safe areas, legacy status/navigation treatment, or controls that look transplanted from an old template;
- a visual result that would look essentially unchanged if the Mobbin reference were removed.

Do not “fix” a dated result by adding the words modern, beautiful, premium, or futuristic. Strengthen reference preservation and remove competing art direction.

## Recovery order

1. Shorten the prompt to a reference-first translation: preserve the interface system and change only product content.
2. Reattach the reference through the strongest explicit image input and regenerate.
3. If the system is right but one detail is wrong, edit the generated screen in place.
4. If a second full generation still looks dated or generic, replace the primary reference.

Show only directions that pass both reference fidelity and platform-quality checks.
