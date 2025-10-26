# lab02-debugging

Stephen Gavin Sears

worked with Rebecca Feng

[link](https://www.shadertoy.com/view/WcffDl) to solution

- first bug: line 97 missing 2 in 'vec2' - found by compiler 

- second bug: line 100 use uv2 with screen offset instead of uv - result of uv2 was never used, so tried plugging it in. Also screen was not centered.

- third bug: line 14 used x instead of y for perspective division - spheres were squished, culprit was view to world calculation (uses screen dimensions)

- fourth bug: line 78 used eye vector for reflection, instead use dir - no lighting was present, so looked at shading calculation. Since eye was used, all shading will return same color, and also doesn't fit equation.

- fifth bug: line 18 num march steps too low, doubled to fix problem - with strange warped shapes being rendered, the raymarcher was the first suspect (plus all other parts had been looked at by this point). Optimized raymarching has more steps at edges of objects, so changing number of steps was worth a shot.
