---
name: sanzo-colours
description: Use when a design-focused coding agent needs Sanzo Wada colour combinations, a Sanzo-inspired palette for an interface or visual design, or help selecting and applying colours from A Dictionary of Colour Combinations.
license: MIT; bundled dataset licence in LICENSE.upstream.md
---

# Sanzo Colours

Choose and apply Sanzo Wada's combinations using the bundled [colors.json](colors.json). Let original combinations supply the colour vocabulary and the design brief determine their composition.

## Retrieve a combination

Resolve `colors.json` relative to this skill's directory. Read or query it with available file tools rather than recalling values from memory. It contains 159 colour records describing 348 combinations of two, three or four colours.

To retrieve combination **N**, collect every record whose `combinations` array contains N. IDs are 1–348. To find combinations containing a colour, locate its record and retrieve the members of its combination IDs. Multiple required colours must share an ID.

The array is organised by colour, not palette. `swatch` identifies a source chapter; record order does not assign design roles. Preserve exact source names and hex values, including unusual spellings. Mood labels and UI roles are interpretations, not source metadata.

## Choose and apply

For an exact lookup, return the requested source information directly. For palette selection:

1. Read the subject, audience, medium, brand constraints and atmosphere from the brief. If these are unavailable, ask one focused question about the intended design.
2. Retrieve real combinations. For an open brief, compare two or three candidates through their lightness, intensity, warm/cool relationships and fit with the content.
3. Select one and propose background, text, surface, accent or decorative roles. Establish visual hierarchy through deliberate coverage; equal proportions are unnecessary.
4. Apply exact source hex values through the project's existing tokens or CSS variables.
5. Verify actual foreground/background pairs using a contrast tool or calculation. WCAG AA requires 4.5:1 for normal text and 3:1 for large text (at least 24 CSS px, or 18.67 CSS px bold). Essential non-text visual information needs 3:1 against adjacent colours. Do not use colour alone to convey meaning. Mark unmeasured contrast **unverified**.

If originals cannot support a required role, explain the limitation. Offer an **added neutral** or **derived shade** only when needed and list it separately. Label subsets **a subset of combination N** and adaptations **based on combination N**. Preserve explicit brand colours; report a conflict when no original combination fits.

## Output

Give the combination ID, a compact table of original names/hex values and proposed roles, a brief rationale, and contrast results or unverified status for the pairs used. List additions separately. Exact lookups need only the requested source information.

## Example

Combination **1** contains **English Red `#d96629`** and **Cerulian Blue `#0093a5`**. For an exhibition site, one could carry a dominant visual field and the other graphic details. These roles are interpretations; readable text requires independent contrast checks.

## Source

Sanzo Wada's *A Dictionary of Colour Combinations*, digitised by Dain M. Blodorn Kim and revised by Matt DesLauriers. See [README.md](README.md) for pinned provenance and [LICENSE.upstream.md](LICENSE.upstream.md) for the dataset licence. Screen conversions may differ from printed swatches.
