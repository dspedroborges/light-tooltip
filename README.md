# @light-tooltip.js

This is literally just a tooltip. All you gotta do is add the `tooltip-{position}` attribute to your element with the desired content. That's it.

## Installation

```html
<script src="light-tooltip.min.js"></script>
```

## Size

- **minified:** ~1KB
- **compressed (tar.gz):** ~0.5KB

That's it. That's the whole library.

## Quick Start

```html
<button tooltip-top="I'm a tooltip!">Hover me</button>

<script src="light-tooltip.min.js"></script>
```

## Positions

The `tooltip-{position}` attribute accepts 8 position values:

| Position | Description |
|----------|-------------|
| `t` | Top (centered) |
| `tl` | Top-left |
| `tr` | Top-right |
| `b` | Bottom (centered) |
| `bl` | Bottom-left |
| `br` | Bottom-right |
| `l` | Left (centered) |
| `r` | Right (centered) |

### Examples

```html
<!-- Top center -->
<span tooltip-t="Top tooltip">Hover</span>

<!-- Top left -->
<span tooltip-tl="Top left">Hover</span>

<!-- Top right -->
<span tooltip-tr="Top right">Hover</span>

<!-- Bottom center -->
<span tooltip-b="Bottom tooltip">Hover</span>

<!-- Bottom left -->
<span tooltip-bl="Bottom left">Hover</span>

<!-- Bottom right -->
<span tooltip-br="Bottom right">Hover</span>

<!-- Left -->
<span tooltip-l="Left tooltip">Hover</span>

<!-- Right -->
<span tooltip-r="Right tooltip">Hover</span>
```

---

## Styling

The library applies minimal inline styles. You can override them with your own CSS:

```css
[style*="--tooltip-bg"] { /* not applicable - uses inline styles */ }

/* The tooltip element is fixed position with these defaults */
div[style*="position: fixed"] {
  /* override tooltip styles */
}
```

To customize tooltip appearance, you can target the fixed div:

```css
/* Target the tooltip after it's created */
body > div[style*="position: fixed"][style*="z-index: 9999"] {
  background: #007bff !important;
  font-size: 14px !important;
  padding: 8px 12px !important;
}
```

---

## Complete Examples

### Basic Tooltips

```html
<!DOCTYPE html>
<html>
<head>
  <style>
    .btn {
      padding: 10px 20px;
      margin: 10px;
      background: #333;
      color: white;
      border: none;
      cursor: pointer;
      border-radius: 4px;
    }
    .btn:hover {
      background: #555;
    }
  </style>
</head>
<body>
  <button class="btn" tooltip-t="I'm on top!">Top</button>
  <button class="btn" tooltip-b="I'm at bottom!">Bottom</button>
  <button class="btn" tooltip-l="I'm on the left!">Left</button>
  <button class="btn" tooltip-r="I'm on the right!">Right</button>

  <script src="light-tooltip.min.js"></script>
</body>
</html>
```

### Icon Tooltips

```html
<!DOCTYPE html>
<html>
<head>
  <style>
    .icon-btn {
      width: 40px;
      height: 40px;
      border-radius: 50%;
      border: 2px solid #333;
      background: transparent;
      cursor: pointer;
      font-size: 20px;
    }
    .icon-btn:hover {
      background: #f0f0f0;
    }
  </style>
</head>
<body>
  <button class="icon-btn" tooltip-tl="Home">🏠</button>
  <button class="icon-btn" tooltip-t="Search">🔍</button>
  <button class="icon-btn" tooltip-tr="Settings">⚙️</button>

  <script src="light-tooltip.min.js"></script>
</body>
</html>
```

### Form Validation Hints

```html
<!DOCTYPE html>
<html>
<head>
  <style>
    form {
      max-width: 400px;
      margin: 20px auto;
    }
    label {
      display: block;
      margin-bottom: 5px;
      font-weight: bold;
    }
    input {
      width: 100%;
      padding: 8px;
      margin-bottom: 15px;
      border: 1px solid #ccc;
      border-radius: 4px;
    }
  </style>
</head>
<body>
  <form>
    <label>Email</label>
    <input type="email" placeholder="Enter email" tooltip-bl="We'll never share your email">

    <label>Password</label>
    <input type="password" placeholder="Enter password" tooltip-bl="Must be at least 8 characters">

    <button type="submit" tooltip-b="Click to submit">Submit</button>
  </form>

  <script src="light-tooltip.min.js"></script>
</body>
</html>
```

### Image Alt Text

```html
<!DOCTYPE html>
<html>
<head>
  <style>
    img {
      width: 200px;
      margin: 20px;
      border-radius: 8px;
      cursor: pointer;
    }
  </style>
</head>
<body>
  <img src="cat.jpg" tooltip-b="A cute cat" alt="Cat">
  <img src="dog.jpg" tooltip-b="A friendly dog" alt="Dog">
  <img src="bird.jpg" tooltip-b="A colorful bird" alt="Bird">

  <script src="light-tooltip.min.js"></script>
</body>
</html>
```

---

## Browser Support

Chrome, Firefox, Safari, Edge - any modern browser with getBoundingClientRect support.

## License

MIT
