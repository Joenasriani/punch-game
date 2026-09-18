# Stress Buster 3000

A browser-based interactive image-manipulation game built with HTML, CSS, and vanilla JavaScript.

The game displays a selected image on a `<canvas>` and applies localized deformation and visual feedback when the player punches the image with pointer or touch input.

## Features

- Built-in selectable image library
- Local custom-image upload
- Pointer and touch interaction
- Canvas-based smudge/deformation effect
- Procedural impact particles
- Screen-shake feedback
- Synthesized punch sound using the Web Audio API
- Reset control
- PNG export of the modified image
- Responsive square game canvas

## Implementation

The project is implemented as a single-page browser application.

- **HTML** provides the interface and game structure.
- **Tailwind CSS** is loaded from the CDN for utility styling.
- **JavaScript** handles input, image loading, canvas processing, animation, and export.
- **Canvas 2D** stores and modifies image pixel data.
- **Web Audio API** generates the punch sound at runtime.

Punch interactions map the pointer position into canvas coordinates, deform nearby pixels within a radius, add a subtle darkened impact region, spawn short-lived particles, and trigger screen shake.

Custom images are read with the browser `FileReader` API and rendered directly into the game canvas.

## Running

No build step is required.

Serve the repository with any static HTTP server and open `index.html` in a modern browser. Serving over HTTP is preferable to opening the file directly because the built-in image assets use root-relative paths such as `/img/trump.jpg`.

## Controls

- Select a thumbnail to load a built-in image.
- Upload an image with the custom image control.
- Click or tap the canvas to punch the image.
- Use **Reset** to restore the currently selected image.
- Use **Save** to export the modified canvas as `punched.png`.

## Repository Structure

```text
.
├── index.html
└── img/
```

`index.html` contains the interface, styling, game logic, audio generation, canvas processing, and export behavior. The `img/` directory contains the built-in target images.
