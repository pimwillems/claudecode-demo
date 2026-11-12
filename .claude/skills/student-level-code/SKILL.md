---
name: student-level-code
description: Write code at second-year ICT student level (Fontys / University of Applied Sciences) so the user can read and understand everything. Use whenever writing, changing, or explaining code in this project (HTML, Tailwind CSS, plain JavaScript, Nuxt, Next). No TypeScript.
---

# Student-level code

The user is a second-year ICT student at a University of Applied Sciences.
They know HTML, CSS and JavaScript well. They have only started learning Nuxt and Next.
Everything you write must be readable and understandable for them.

## Core rule

If a second-year student cannot read it and explain it, simplify it.
Choose the clear solution over the clever one.

## JavaScript

- Use `const` and `let`. Never `var`.
- Use plain `function` declarations or simple arrow functions.
- Use basic array methods: `map`, `filter`, `find`, `forEach`. Prefer a normal `for...of` loop when it is clearer.
- Use `async`/`await` with `try`/`catch` for fetching data.
- Use descriptive names: `userList`, not `ul`. `handleSubmit`, not `hs`.
- Keep functions short. One function does one thing.
- Avoid: nested ternaries, long `reduce` chains, regex-heavy tricks, bitwise operators, generators, proxies, deep destructuring, heavy chaining like `a?.b?.[c]?.()`.
- This project does NOT use TypeScript. Write plain JavaScript only: `.js` files, no type annotations, no `interface`, no `lang="ts"` in Nuxt, no `.tsx` in Next.

## HTML and Tailwind CSS

- Use semantic HTML: `header`, `nav`, `main`, `section`, `footer`, `button`.
- This project uses Tailwind CSS. Style with Tailwind utility classes in the HTML/template (`flex`, `gap-4`, `p-4`, `text-lg`, `bg-blue-500`).
- Use common utilities: Flexbox, Grid, spacing, colors, typography, and responsive prefixes (`md:`, `lg:`). Use `hover:` for hover states.
- Keep class lists readable. Put long lists on separate lines, and keep a logical order (layout, spacing, text, color).
- Avoid advanced Tailwind: arbitrary values like `w-[137px]` (unless really needed), complex `@apply` setups, custom plugins, heavy config changes.
- If a class list is repeated many times, make a component instead of using `@apply`.
- Write plain CSS only when Tailwind cannot do it. Add a short comment explaining why.
- Do not use inline `style` attributes or a second CSS framework.

## Nuxt and Next (they are still learning)

- Use the basics only: pages, components, layouts, routing, props, simple state, fetching data.
- Nuxt: `<script setup>`, `ref`, `computed`, `useFetch`, `pages/`, `components/`. Keep composables simple.
- Next: the App Router basics, function components, `useState`, `useEffect`, a simple `fetch`. Mark `"use client"` only when needed, and say why.
- Avoid advanced features unless asked: middleware, server actions, caching strategies, streaming, parallel/intercepting routes, custom plugins, complex state libraries.
- When using a framework feature for the first time, add a short comment about what it does and why it is used.
- Link to the official docs page for any new concept.

## Comments and explanation

- Add a short comment above each function or block explaining **what** it does and **why**.
- Do not comment every line. Do not state the obvious (`// add 1 to i`).
- Write comments in English, simple words.
- After a change, give a short summary: what changed, in which file, and why.
- If you use a concept a second-year student may not know, explain it in 1-2 sentences.

## Structure

- Small files, clear folder names, one component per file.
- No premature abstraction. Some repetition is better than a confusing helper.
- No extra libraries when plain JS and Tailwind can do the job. If a library is needed, say why.
- Prefer a well-known pattern from the official docs over a custom one.

## Before you finish

Ask yourself:

1. Could the student read this top to bottom and explain it to a classmate?
2. Are all names clear?
3. Did I add anything advanced that was not asked for? Remove it, or explain it.
