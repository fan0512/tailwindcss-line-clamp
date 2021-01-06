# @tailwindcss/line-clamp

A plugin that provides utilities for visually truncating text after a fixed number of lines.


## Installation

Install the plugin from npm:

```sh
# Using npm
npm install @tailwindcss/line-clamp

# Using Yarn
yarn add @tailwindcss/line-clamp
```

Then add the plugin to your `tailwind.config.js` file:

```js
// tailwind.config.js
module.exports = {
  theme: {
    // ...
  },
  plugins: [
    require('@tailwindcss/line-clamp'),
    // ...
  ],
}
```

## Usage

Use the `line-clamp-{n}` utilities to specify how many lines of text should be visible before truncating::

```html
<p class="line-clamp-3">
  Et molestiae hic earum repellat aliquid est doloribus delectus. Enim illum odio porro ut omnis dolor debitis natus. Voluptas possimus deserunt sit delectus est saepe nihil. Qui voluptate possimus et quia. Eligendi voluptas voluptas dolor cum. Rerum est quos quos id ut molestiae fugit.
</p>
```

To remove any line-clamping, use `line-clamp-none`:

```html
<p class="line-clamp-3 md:line-clamp-none">
  Et molestiae hic earum repellat aliquid est doloribus delectus. Enim illum odio porro ut omnis dolor debitis natus. Voluptas possimus deserunt sit delectus est saepe nihil. Qui voluptate possimus et quia. Eligendi voluptas voluptas dolor cum. Rerum est quos quos id ut molestiae fugit.
</p>
```

> Note that the `line-clamp-{n}` set other properties like `display` and `overflow` in addition to `-webkit-line-clamp` which are not unset by `line-clamp-none`, so depending on what you are trying to achieve you may need to explicitly override those properties with utilities like `flex` or `overflow-visible` as well.

Utilities are for clamping text up to 6 lines are generated by default:

| Class  | CSS |
| ---  | --- |
| `line-clamp-1` |  `overflow: hidden;`<br>`display: -webkit-box;`<br>`-webkit-box-orient: vertical;`<br>`-webkit-line-clamp: 1;` |
| `line-clamp-2` |  `overflow: hidden;`<br>`display: -webkit-box;`<br>`-webkit-box-orient: vertical;`<br>`-webkit-line-clamp: 2;` |
| `line-clamp-3` |  `overflow: hidden;`<br>`display: -webkit-box;`<br>`-webkit-box-orient: vertical;`<br>`-webkit-line-clamp: 3;` |
| `line-clamp-4` |  `overflow: hidden;`<br>`display: -webkit-box;`<br>`-webkit-box-orient: vertical;`<br>`-webkit-line-clamp: 4;` |
| `line-clamp-5` |  `overflow: hidden;`<br>`display: -webkit-box;`<br>`-webkit-box-orient: vertical;`<br>`-webkit-line-clamp: 5;` |
| `line-clamp-6` |  `overflow: hidden;`<br>`display: -webkit-box;`<br>`-webkit-box-orient: vertical;`<br>`-webkit-line-clamp: 6;` |
| `line-clamp-none` | `-webkit-line-clamp: unset;` |

## Configuration

You can configure which values and variants are generated by this plugin under the `lineClamp` key in your `tailwind.config.js` file:

```js
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      lineClamp: {
        7: '7',
        8: '8',
        9: '9',
        10: '10',
      }
    }
  },
  variants: {
    aspectRatio: ['responsive', 'hover']
  }
}
```
