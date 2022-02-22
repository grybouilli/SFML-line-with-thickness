# SFML line with thickness !

## Explanations
### The problematic

The SFML library gives tools to render stripped lines but their thickness is set and stuck to one pixel. The class from this repo aims to let users render lines with thickness of choice. 

### The maths behind the approach

A line with thickness is basically a triangle. The tricky part of rendering a set of connected thick lines is to put the corners of the connected rectangles in the right spot.

When adding a new point to create a new line to the set of connected lines, the placement of the two corners of the previous 'rectangle' need to be readjusted. The two new spots are the intersection between each sides direction lines. See the drawing below:

![Drawing of the math model](https://github.com/grybouilli/SFML-line-with-thickness/blob/1e89c4b1115d3eaaa6852aa5001920c09bc7d5c1/thick_line_math_model.png)

We're adding a new point with the middle point between H and M. The previous point of the set of lines is E. The offset points of E to be calculated are J and I. They are the intersection between the lines directed by the vectors u and v which are also the vectors giving the directions of the lines.

## Examples
