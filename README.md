# 2D Graphics Editor (C)

A menu-driven, terminal-based 2D graphics editor written in C. It draws shapes as `*` characters on a 30 × 60 text canvas.

## Features

- Draw a **line** between two points (Bresenham's line algorithm)
- Draw a **rectangle** from a top-left corner, width, and height
- Draw a **triangle** from three points
- Draw a **circle** from a centre point and radius
- **Display** the canvas at any time
- **Clear** the canvas and start over
- Out-of-range points are ignored, so shapes can't write outside the canvas

## Built with

- C (standard library only: `stdio.h`, `stdlib.h`, `math.h`)

## Build and run

```bash
gcc graphics_editor_working.c -o graphics_editor -lm
./graphics_editor
```

`-lm` links the math library, which the circle code needs for `sin` and `cos`.

## Usage

Pick an option from the menu and enter the values when prompted. Coordinates are `(row, column)`, with `(0, 0)` at the top-left. Rows run 0-29 and columns run 0-59.

| Option | Action | Input |
|---|---|---|
| 1 | Draw line | `x1 y1 x2 y2` |
| 2 | Draw rectangle | `row col width height` |
| 3 | Draw triangle | `x1 y1 x2 y2 x3 y3` |
| 4 | Draw circle | `center_x center_y radius` |
| 5 | Delete picture | none |
| 6 | Display picture | none |
| 7 | Modify picture (clear canvas) | none |
| 8 | Exit | none |

Example: choose `1`, enter `2 5 20 40`, then choose `6` to see a line across the canvas.

## How it works

- The canvas is a 2D `char` array, and every shape ends up as calls to a single `plot()` function.
- Lines use Bresenham's algorithm, which needs only integer arithmetic.
- Triangles are three lines, and rectangles are four edges.
- Circles step through 360 angles and convert each one to a point using `cos` and `sin`.

## Screenshot

[Add a screenshot of the terminal showing a drawing.]

## Roadmap

- [ ] Validate all input, not only the menu choice
- [ ] Save and load drawings from a file
- [ ] Filled shapes
- [ ] Choose the drawing character
- [ ] Split the code into multiple files and add a Makefile

## About me

I'm Christen, a first-year CSE student learning C, Java, Python, and web development. I'm interested in cloud computing and working toward my first open-source contribution.
