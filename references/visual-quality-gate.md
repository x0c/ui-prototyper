# Product, Originality, and Visual Quality Gate

Evaluate generated prototypes in this order. A later strength never compensates for an earlier failure.

## 1. Product fidelity

Fail the draft when:

- any visible element cannot be traced to the product contract;
- a required action, state, or piece of information is missing or visually subordinated;
- reference-derived navigation, modes, labels, entities, controls, or workflows appear;
- the interface suggests the product behaves differently from the user's requirements;
- decorative styling makes a simple product feel more complex than it is.
- an avatar, attachment affordance, menu, mode, status, or secondary action appears without being listed in the allowed-element manifest.
- placeholder text, lorem ipsum, or invented gibberish copy appears where realistic content was required.

Ask of every element: “Would we still need this if no reference had shown it?” If not, remove it.

Inventory every visible interactive element before judging aesthetics. Do not rely on a general impression that the screen is product-faithful.

## 2. Originality

Originality constrains product structure, not visual craft. Absorbing a reference's visual language deeply is the goal; copying its product body is the failure.

Fail the draft when:

- its layout skeleton, control placement, or component sequence is recognizably copied from one reference;
- it retains source-product chrome, distinctive icons, modes, pagination, feedback rows, or domain content;
- the result is effectively a reskin with different copy and brand color;
- a reference attachment dictated the product structure instead of only the visual language.

References contribute visual soul, never product body. Combine research insights through an original composition anchored in the product contract.

## 3. Visual quality

Fail the draft when it introduces unrequested oversized controls, excessive rounded containers, heavy shadows, glossy gradients, faux luxury, faux futurism, cross-platform legacy patterns, implausible safe areas, or generic template styling. Fail it equally for current AI-default styling: emoji used as navigation or action icons, all-caps micro-header labels, colored glow or tinted shadows, decorative stat-banner rows, and identical icon-topped feature cards. For data screens, fail invented or inconsistent figures, 3D charts, pies with more than five segments, and illegible dense labels. Do not fix a dated result by adding words such as modern, premium, beautiful, or futuristic.

Fail above all the engineer-drawn look: default template typography, everything boxed in uniform containers, no deliberate color or spacing voice, no visible craft. A draft that could have been produced without any design reference has failed this gate by definition. The anchor reference's visual language must be visibly present; if removing the reference attachment would not change the result, the reference did not work — regenerate with stronger visual transfer or a stronger reference.

## Recovery order

1. Delete every element that lacks a product justification.
2. If the reference's structure leaked in, restate the visual-only scope and regenerate with the same reference.
3. If the result is stiff or generic, strengthen the visual transfer: re-scope the attachment toward the reference's typography, color, and spacing, or switch to a visually stronger reference.
4. Regenerate with an original composition intent.
5. If only one detail fails, edit the generated prototype in place without changing the validated product structure.

Show only drafts that pass all three gates.
