# cn Utility Function

This repository contains a utility function that combines and merges class names using `clsx` and `tailwind-merge` libraries.

## Code

```typescript
import { clsx, type ClassValue } from "clsx";
import { twMerge } from "tailwind-merge";

export const cn = (...inputs: ClassValue[]) => twMerge(clsx(inputs));
```

## Explanation

### Purpose
The `cn` function simplifies managing and merging CSS class names in your project. It ensures class name conflicts are resolved correctly when using Tailwind CSS.

### How It Works
1. **`clsx`**: Conditionally combines class names into a single string.
   - Example: `clsx("btn", isActive && "btn-active")` results in `"btn btn-active"` if `isActive` is `true`.

2. **`twMerge`**: Resolves conflicting Tailwind CSS classes.
   - Example: `twMerge("p-4 p-2")` returns `"p-2"`, keeping the last class that applies to the same property.

3. **`cn`**: Combines both functionalities, making it easy to:
   - Handle conditional classes.
   - Resolve Tailwind CSS class conflicts.

## Usage

```typescript
import { cn } from "./path-to-your-cn-file";

const buttonClass = cn("btn", isPrimary && "btn-primary", "p-4", "p-2");
console.log(buttonClass); // Outputs: "btn btn-primary p-2" (if isPrimary is true)
```

## Requirements
Ensure the following dependencies are installed in your project:

- `clsx`
- `tailwind-merge`

You can install them via npm, yarn, or bun:

### Using npm
```bash
npm install clsx tailwind-merge
```

### Using yarn
```bash
yarn add clsx tailwind-merge
```

### Using bun
```bash
bun add clsx tailwind-merge
```

## License
This code is available under the [MIT License](LICENSE).

---

Feel free to use this utility function to streamline class name management in your Tailwind CSS projects.
