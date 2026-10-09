# Connect the Dots Maker

Turn any drawing into a printable connect-the-dots worksheet for kids' activity books.

The interface is available in English and Spanish, and the printed sheet follows the selected language.

## Usage

Open `index.html` in a browser. No install or build step is needed for now.

## Features

- Upload an image (file picker, drag and drop, or paste), or start from the built-in examples (fish, star, house).
- Detects the silhouette, traces its outer contour and turns it into numbered dots.
- Corners always get a dot; the remaining dots are spaced evenly along the outline.
- Keeps inner details (eyes, mouth) as pre-drawn lines on line drawings.
- Adjustable difficulty (10 to 120 dots), number size, and Letter or A4 paper.
- Optional header parts: name and date boxes, title, instructions, and reference drawing.
- On-screen solution preview and PNG export at 300 dpi.

## How it works

1. Grayscale conversion and binarization with Otsu's threshold (or a manual one), inverting automatically on dark backgrounds.
2. Morphological closing, hole filling, and selection of the largest connected component.
3. Moore-neighbor contour tracing, arc-length resampling, and smoothing.
4. Corner detection by turning angle, then the remaining dots are split between corners in proportion to segment length.
5. Labels are placed outside the shape, avoiding overlaps with other labels, dots, and the outline.

## Works best with

Silhouettes or bold line drawings on a white background, with a closed outline.

## Roadmap

- Multi-page album with PDF export.
- Album cover page.

## License

MIT
