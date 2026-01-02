# Holographic 3D Card

A premium holographic card effect with smooth 3D tilt animations, built with pure HTML, CSS, and vanilla JavaScript. No dependencies required.

## Features

- **3D Tilt Effect** - Card tilts toward cursor with smooth lerp animation
- **Holographic Sheen** - Rainbow light refraction that moves with the cursor
- **Parallax Depth** - Image layer lifts forward in 3D space
- **Edge Glow** - Dynamic colored glow that intensifies on hover
- **Image Upload** - Upload your own image or drag & drop
- **Touch Support** - Works on mobile devices
- **Accessibility** - Respects `prefers-reduced-motion`

## Usage

1. Open `index.html` in any modern browser
2. Hover over the card to see the 3D effect
3. Upload your own image using the button or drag & drop

## How It Works

### 3D Transform System
```css
.card {
  transform: rotateX(var(--rx)) rotateY(var(--ry));
  transform-style: preserve-3d;
}
```

JavaScript tracks mouse position, normalizes it to -1 to 1, and updates CSS variables with smooth interpolation (lerp).

### Layer Stack
| Layer | Purpose |
|-------|---------|
| `.glow-layer` | Soft bloom behind card |
| `.image-layer` | Main image with `translateZ(40px)` |
| `.shine-layer` | Holographic rainbow gradient |
| `.specular-layer` | Moving light spot |
| `.noise-layer` | Subtle grain texture |

### Image Upload
Images are converted to base64 Data URLs and stored in browser memory. No server required - everything runs client-side.

## Browser Support

- Chrome 80+
- Firefox 75+
- Safari 13+
- Edge 80+

## Customization

Edit CSS variables in `:root` to customize:

```css
:root {
  --card-width: 320px;
  --card-height: 450px;
  --card-radius: 16px;
  --max-tilt: 25deg;
  --perspective: 1200px;
  --z-lift: 40px;
}
```
