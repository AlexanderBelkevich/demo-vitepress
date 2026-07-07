# Configuration

MyLib works with zero configuration, but you can set global defaults if you want consistent behavior across your app.

## Global Defaults

Set a default locale and format once, at app startup:

```ts
import { configure } from 'my-lib'

configure({
  locale: 'en-US',
  defaultFormat: 'YYYY-MM-DD'
})
```

After this, calls without an explicit format use the default:

```ts
import { formatDate } from 'my-lib'

formatDate(new Date())
// → "2026-06-20"  (uses defaultFormat)
```

## Options

| Option          | Type     | Default        | Description                          |
| --------------- | -------- | -------------- | ------------------------------------ |
| `locale`        | `string` | `'en-US'`      | Locale used for month and day names  |
| `defaultFormat` | `string` | `'YYYY-MM-DD'` | Format used when none is passed      |
| `weekStart`     | `number` | `1`            | First day of week (0 = Sun, 1 = Mon) |

## Per-call Override

Global defaults can always be overridden per call:

```ts
formatDate(new Date(), 'DD MMMM', { locale: 'fr-FR' })
// → "20 juin"
```

::: tip
Per-call options always win over global configuration. Use globals for app-wide defaults, per-call options for exceptions.
:::

::: warning
parseData invalid string
:::

::: danger
Do not use the deprecated oldFormat method
:::

::: info
Do not use the deprecated oldFormat method
:::

::: details
Do not use the deprecated oldFormat method
:::

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
:::

```ts{3}
import { formatDate } from 'my-lib'

const result = formatDate(new Date(), 'YYYY/MM/DD')
```