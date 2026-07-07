# Installation

## Requirements

MyLib works in any modern JavaScript environment:

- Node.js 18 or higher
- Any modern browser
- Deno and Bun are supported

## Package Managers

::: code-group

```bash [npm]
npm install my-lib
```

```bash [yarn]
yarn add my-lib
```

```bash [pnpm]
pnpm add my-lib
```

```bash [bun]
bun add my-lib
```

:::

## CDN

For quick prototyping, load MyLib directly from a CDN:

```html
<script type="module">
  import { formatDate } from 'https://esm.sh/my-lib'

  console.log(formatDate(new Date(), 'YYYY-MM-DD'))
</script>
```

## Importing

MyLib is ESM-first and fully tree-shakeable. Import only what you use:

```ts
// import individual functions
import { formatDate, parseDate } from 'my-lib'
```

::: warning
MyLib does not ship a CommonJS build. If you need `require()`, use a bundler that handles ESM, or the CDN build.
:::
