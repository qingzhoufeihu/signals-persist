# Signals with Storage

Signals are awesome. Make them even more awesome by **persisting them across sessions**.

This library allows you to easily persist your signals across sessions. It works in Preact

It's as simple as this:

```ts
import { signalL, signalS } from "@jagger/signals-persist";

export const countWithLocalStorage = signalL("count", 0);
export const countWithSessionStorage = signalS("count", 0);
```

## Installation

```sh
npx jsr add @jagger/signals-persist

or

pnpx jsr add @jagger/signals-persist

or

deno add @jagger/signals-persist
```

## Usage

Customize your storage:

```ts
import { persistSignal, Storage } from "@jagger/signals-persist";

const storage: Storage = window.localStorage;

export const signalX = <T>(key: string, initialValue: T) =>
  persistSignal(key, initialValue, storage);
```
