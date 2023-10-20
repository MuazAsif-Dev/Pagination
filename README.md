<div align="center">
  <h1>Next-Genesis: A Next.js Starter Template 🚀</h1>
</div>

## Table of Contents

- [Overview](#overview)
- [Tooling](#tooling-🛠️)
  - [Code Quality](#code-quality-🔍)
    - [ESLint plugins and configs](#eslint-plugins-and-configs)
  - [Style Reusability](#style-reusability-🎨)
  - [Validation](#validation-🛡️)
- [Utilities](#utilities-🧰)
- [Getting Started](#getting-started-🏁)

## Overview

Next-Genesis is a Next.js Starter Template equipped with pre-configured development tools and libraries to kickstart your web development projects efficiently. This template is designed to save you time and streamline the development process. Below, you'll find a detailed overview of the tooling and how to get started.

## Tooling 🛠️

### Code Quality 🔍

Next-Genesis ensures code quality by integrating several essential tools:

- [**Prettier**](https://prettier.io) : Prettier is a formatter that helps maintain a consistent code style, making your codebase clean and easy to read.

- [**ESLint**](https://eslint.org) : ESLint is a powerful code linter that helps catch errors, enforce code style, and maintain code quality.

- [**Husky**](https://typicode.github.io/husky/) : Husky provides Git hooks that prevent bad git commit, git push, and more by running scripts.

- [**Lint-Staged**](https://github.com/lint-staged/lint-staged#readme) : Lint-Staged allows you to run linters on pre-committed files, ensuring that only clean and properly formatted code is committed.

- [**CommitLint**](https://commitlint.js.org/#/) : CommitLint enforces a consistent commit message format, enhancing collaboration and version control.

#### ESLint plugins and configs:

- [**@typescript-eslint/eslint-plugin**](https://www.npmjs.com/package/@typescript-eslint/eslint-plugin) : An ESLint plugin which provides lint rules for TypeScript codebases.

- [**eslint-config-next**](https://www.npmjs.com/package/eslint-config-next) : Includes Next.js' base ESLint configuration along with a stricter Core Web Vitals rule-set.

- [**eslint-plugin-import**](https://www.npmjs.com/package/eslint-plugin-import) : This plugin intends to support linting of ES2015+ (ES6+) import/export syntax, and prevent issues with misspelling of file paths and import names.
- [**eslint-plugin-jsx-a11y**](https://www.npmjs.com/package/eslint-plugin-jsx-a11y) : Static AST checker for accessibility rules on JSX elements.
- [**eslint-plugin-react**](https://www.npmjs.com/package/eslint-plugin-react) : React specific linting rules for eslint
- [**eslint-plugin-react-hooks**](https://www.npmjs.com/package/eslint-plugin-react-hooks) : This ESLint plugin enforces the [Rules of Hooks](https://reactjs.org/docs/hooks-rules.html).
- [**eslint-plugin-simple-import-sort**](https://www.npmjs.com/package/eslint-plugin-simple-import-sort) : Easy autofixable import sorting.

- [**eslint-plugin-tailwindcss**](https://www.npmjs.com/package/eslint-plugin-tailwindcss) : Rules enforcing best practices and consistency using Tailwind CSS.

### Style Reusability 🎨

Next-Genesis makes it easy to manage styles and ensure reusability:

- [**Tailwind CSS**](https://tailwindcss.com) : A utility-first CSS framework that simplifies styling and ensures a consistent look and feel across your application.

- [**Class Variance Authority**](https://cva.style/docs) : A library that helps enforce class naming conventions , making it easier to manage your styles.

- [**clsx**](https://github.com/lukeed/clsx#readme) : A utility for conditionally joining class names, making it simple to apply dynamic styles to your components.

- [**Tailwind-Merge**](https://github.com/dcastil/tailwind-merge) : A library used for merging Tailwind CSS classes, enabling more dynamic and flexible styling.

### Validation 🛡️

- [**Zod**](https://zod.dev) : This is a TypeScript-first schema validation library.

## Utilities 🧰

- **cn** : A utility helper to conditionally join class names and merge tailwind classes without conflicts. _Inspired by shadcn/ui_.

  ```javascript
  import { type ClassValue, clsx } from "clsx";
  import { twMerge } from "tailwind-merge";

  export function cn(...inputs: ClassValue[]) {
    return twMerge(clsx(inputs));
  }
  ```

- **env** : An object that contains the project's environment variables validated by zod. Add fields to the `envSchema` object to match your `.env` file so that they can be validated.

  ```javascript
  import z from "zod";

  const envSchema = z.object({
  	SOME_SECRET: z.string().nonempty(),
  	ANOTHER_SECRET: z.string().nonempty(),
  });

  export const env = envSchema.parse(process.env);
  ```

## Getting Started 🏁

First, install the dependencies:

```bash
npm install
```

Next, run the development server:

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.
