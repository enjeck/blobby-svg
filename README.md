# Blobby

<p align="center">
  <img src="./blobby.gif" width="150" alt="Blobby" />
</p>

<p align="center"><strong>Random SVG Avatar Generator & Blob Character Library</strong></p>

Generate unique, colorful, and random blob characters for your applications. Perfect for default avatars, user placeholders, or adding a touch of personality to your UI.

## Features

- **Unique Avatars**: Infinite variations of shapes, eyes, and colors.
- **Customizable**: Control sizes, palettes, and features (eyes/blush).
- **Lightweight**: Zero dependencies, returns pure SVG strings.
- **Framework Agnostic**: Works with React, Vue, Svelte, or vanilla JS.
- **TypeScript**: Fully typed for excellent developer experience.

<p align="center">
  <a href="https://www.npmjs.com/package/blobby-svg"><img src="https://img.shields.io/npm/v/blobby-svg.svg" alt="npm version"></a>
  <a href="https://www.npmjs.com/package/blobby-svg"><img src="https://img.shields.io/npm/dm/blobby-svg.svg" alt="npm downloads"></a>
  <a href="https://github.com/enjeck/blobby-svg/blob/main/LICENSE"><img src="https://img.shields.io/npm/l/blobby-svg.svg" alt="license"></a>
</p>

No two characters are the same! Each Blobby has a unique body shape, randomly generated colors, and expressive eyes.

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

You can render the SVG directly, or use it as an image source (safer and easier):

```jsx
import { generateBlobby } from "blobby-svg";
import { useMemo } from "react";

function Avatar() {
  const svgUrl = useMemo(() => {
    const svg = generateBlobby({ size: 100 });
    return `data:image/svg+xml;utf8,${encodeURIComponent(svg)}`;
  }, []);

  return <img src={svgUrl} alt="Blobby Avatar" />;
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
