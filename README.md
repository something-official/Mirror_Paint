# Mirror Paint

Mirror Paint is a camera-safe painting lab with clear, persistent trails, brush modes, local clearing, and PNG export. It works immediately with a pointer and upgrades to camera motion when permission is granted.

## What this demonstrates

- Drawing a responsive brush trail
- Switching visual modes without external libraries
- Handling camera denial with an immediate pointer fallback
- Clearing local state safely
- Exporting a canvas image locally

## Run it

Open `index.html` in a modern browser. For camera mode, serve the folder from `localhost` or HTTPS, then choose **Start camera**. The project does not need npm, a bundler, or a build step.

## Browser notes

Camera permission is requested only after an explicit button action, video-only constraints are used, and media tracks are stopped when the page is left. The project processes the low-resolution signal in the browser and never uploads frames. If permission is denied, the pointer and sample modes remain usable.

This package intentionally uses a transparent Canvas 2D signal baseline instead of hiding a model download. To study a landmark upgrade, replace `analyzeFrame()` with a landmark provider and preserve the same permission, fallback, cleanup, and reduced-motion contracts.

## How to study this

Start with `index.html`, then read `resize()`, `analyzeFrame()`, and `render()` in `app.js`. Change one mapping at a time: input position, signal energy, trail length, or color range. Keep the interaction understandable before adding a dependency.

## License

Released under the MIT License. See [LICENSE](LICENSE).
