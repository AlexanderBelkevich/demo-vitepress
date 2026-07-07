# Getting Started

MyLib is a zero-dependency utility for formatting and parsing dates.

## Quick Start

Install the package:

```bash
npm install my-lib
```

```ts
import { formatDate } from 'my-lib'

formateDate(new Date('2026-06-20'), 'DD.MM.YYYY')
// => "20.06.2026"
```