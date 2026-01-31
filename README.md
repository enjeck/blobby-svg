# Blobby

<p align="center">
  <img src="https://raw.githubusercontent.com/enjeck/Blobby/main/blobby.gif" width="150" alt="Blobby" />
</p>

<p align="center"><strong>Generate random SVG blob characters</strong></p>

<p align="center">
  <a href="https://www.npmjs.com/package/blobby-svg"><img src="https://img.shields.io/npm/v/blobby-svg.svg" alt="npm version"></a>
  <a href="https://www.npmjs.com/package/blobby-svg"><img src="https://img.shields.io/npm/dm/blobby-svg.svg" alt="npm downloads"></a>
  <a href="https://github.com/enjeck/Blobby/blob/main/LICENSE"><img src="https://img.shields.io/npm/l/blobby-svg.svg" alt="license"></a>
</p>

No two characters are the same! Each Blobby has a unique body shape, randomly generated colors, and expressive eyes. Perfect for avatars, placeholders, or adding personality to your app.

## Installation

```bash
npm install blobby-svg
```

## Usage

### Basic Usage

```javascript
import { generateBlobby } from "blobby-svg";

// Generate a random blob character
const svg = generateBlobby();

// Use in DOM
document.getElementById("avatar").innerHTML = svg;
```

### With Options

```javascript
import { generateBlobby } from "blobby-svg";

const svg = generateBlobby({
  size: 200, // SVG dimensions (default: 400)
  colors: ["#ff6b6b", "#4ecdc4", "#45b7d1"], // Custom color palette
  includeEyes: true, // Show eyes (default: true)
  includeBlush: true, // Show blush circles (default: true)
});
```

### React Example

```jsx
import { generateBlobby } from "blobby-svg";
import { useMemo } from "react";

function Avatar() {
  const svg = useMemo(() => generateBlobby({ size: 100 }), []);

  return <div dangerouslySetInnerHTML={{ __html: svg }} />;
}
```

### Default Colors

You can also import the default color palettes:

```javascript
import { defaultColors, defaultBgColors } from "blobby-svg";

console.log(defaultColors); // Body colors
console.log(defaultBgColors); // Background colors
```

## API

### `generateBlobby(options?)`

Returns an SVG string of a randomly generated blob character.

#### Options

| Option         | Type       | Default         | Description                           |
| -------------- | ---------- | --------------- | ------------------------------------- |
| `size`         | `number`   | `400`           | Width and height of the SVG in pixels |
| `colors`       | `string[]` | `defaultColors` | Array of hex colors for the blob body |
| `includeEyes`  | `boolean`  | `true`          | Whether to include eyes               |
| `includeBlush` | `boolean`  | `true`          | Whether to include blush circles      |

## Demo

Try it out: [https://enjeck.com/Blobby](https://enjeck.com/Blobby)

## License

MIT © [enjeck](https://github.com/enjeck)
