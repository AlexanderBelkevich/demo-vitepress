# formatDate

Formats a Date into a string using a token pattern.

## Signature

```ts
function formatDate(date: Date, pattern: string, options?: FormatOptions): string
```

## Parameters

| Parameter | Type          | Required | Description                     |
| --------- | ------------- | -------- | ------------------------------- |
| date      | Date          | yes      | The date to format              |
| pattern   | string        | yes      | Token pattern (e.g. YYYY-MM-DD) |
| options   | FormatOptions | no       | Locale and other overrides      |