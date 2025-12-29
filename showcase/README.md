# Showcase

Example outputs demonstrating key techniques.

## Examples

Blue glass 3D style outputs in `examples/`. Use any as `--ref` for consistency.

## Gradient Degradation

`gradient_degradation/` shows why to avoid gradients when iterating:

1. `source/original.png` - Clean start with solid black background
2. `01_gradient_added.png` - Added gradient, looks fine
3. `02_first_iteration.png` - Colors drifting
4. `03_second_iteration.png` - Banding visible
5. `04_third_iteration.png` - Muddy, artifacts

**Lesson:** Use solid colors for elements you'll iterate on.

## Backgrounds

`backgrounds/` - Generate backgrounds separately, composite in Canva with your foreground + text.
