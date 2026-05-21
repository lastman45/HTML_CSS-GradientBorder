# Gradient Border

A pure CSS animated rainbow gradient border effect rendered as a glowing circle. No JavaScript required.

## Preview

A 300×300px circular element with a continuously animating rainbow glow border — cycling through red, orange, yellow, green, cyan, blue, violet, and pink.

## Files

| File | Description |
|---|---|
| `GradientBorder.html` | Markup structure |
| `GradientBorder.css` | All styles and animation |

## How It Works

The effect uses a CSS `::before` pseudo-element positioned behind the main circle via `z-index: -1`. The pseudo-element carries a `linear-gradient` with rainbow stops and an oversized `background-size: 450%`, which is then animated by shifting `background-position` — creating the illusion of a flowing color loop. A `filter: blur(5px)` gives it the soft glow quality.

```
.gradient-border-box          ← circular container
    ::before                  ← animated gradient pseudo-element (the "border")
    .content                  ← inner circle (place your image here)
```

## Usage

### Basic setup

1. Clone or download both files into the same folder.
2. Open `GradientBorder.html` in a browser.

### Adding a profile image

In `GradientBorder.css`, find the `.content` rule and uncomment the `background-image` line:

```css
.content {
    background-image: url("your-image.jpg"); /* ← add your image path here */
    background-size: cover;
    border-radius: 50%;
}
```

### Customising the effect

| Property | Location | What it changes |
|---|---|---|
| `inset: -4px` | `::before` | Border thickness |
| `filter: blur(5px)` | `::before` | Glow spread |
| `animation: ... 20s` | `::before` | Rotation speed (lower = faster) |
| `background` gradient stops | `::before` | Colors in the gradient |
| `width` / `height` | `.gradient-border-box` | Circle size |

### Changing the animation speed

```css
animation: gradient-border 20s linear infinite;
/*                          ^^^
                            Adjust this value */
```

## Browser Support

Works in all modern browsers that support CSS `@keyframes`, `linear-gradient`, and `filter`. No polyfills needed.

## Dependencies

- [Font Awesome 7](https://cdnjs.cloudflare.com/ajax/libs/font-awesome/7.0.0/css/all.min.css) — loaded via CDN in the HTML head (unused in the base demo; available for adding icons inside `.content`).

## License

Free to use and adapt.
