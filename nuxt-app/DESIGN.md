# Gear – Design guide

Based on the home screen design. Everything is built with Nuxt + Tailwind CSS.
All colors and fonts live in `app/assets/css/main.css` (the `@theme` block). Never type a hex code in a component, use the token.

## Colors

| Token | Hex | Tailwind class | Use for |
|---|---|---|---|
| `primary` | `#01699f` | `bg-primary`, `text-primary` | Icon tiles, arrows, active tab, profile circle |
| `primary-dark` | `#014f78` | `bg-primary-dark` | Pressed state of primary things |
| `ink` | `#0b0d45` | `text-ink` | Titles and main text |
| `muted` | `#6b7a89` | `text-muted` | Subtitles, labels, inactive tabs |
| `page` | `#c9dff4` | `bg-page` | Page background |
| `page-light` | `#e0edf8` | `bg-page-light` | Wave decoration in the background |
| `surface` | `#fcfcfc` | `bg-surface` | Cards, tab bar, back button |
| `line` | `#dadde1` | `border-line` | Borders and dividers |

## Typography

- Text: **Public Sans** (`font-sans`, default). Loaded automatically by `@nuxt/fonts`.
- Logo word "Gear": **Barlow Condensed** bold (`font-logo`). Only used in `AppLogo`.

| Style | Classes |
|---|---|
| Page title | `text-4xl font-semibold text-ink` |
| Card title | `text-lg font-semibold text-ink` |
| Subtitle | `text-base text-muted` |
| Small label | `text-sm text-muted` |
| Section heading | `text-sm font-semibold uppercase tracking-wider text-muted` |
| Tab label | `text-sm font-medium` |

## Shape and spacing

- Cards: `rounded-card border border-line bg-surface shadow-sm` (radius 1rem).
- Icon tiles: `rounded-tile bg-primary` (radius 0.875rem), white icon.
- Round buttons (back, profile): `rounded-full`, `size-11`.
- Page: one column, `max-w-md`, `px-5`. Space between main buttons: `gap-4`.

## Icons

Use `<Icon name="mdi:..." />` from the Material Design Icons set ([browse here](https://icones.js.org/collection/mdi)).
The icon is 1em big, so **size it with `text-*`** (`text-2xl`, `text-3xl`, `text-4xl`), not `size-*`.

## Components

All live in `app/components/`.

### `AppHeader`
Back button (optional) + logo + profile circle.

| Prop | Type | Default | Meaning |
|---|---|---|---|
| `back-to` | String | `''` | Link of the back button. Empty = no back button. |
| `initials` | String | `'RS'` | Letters in the profile circle. |

```vue
<AppHeader />                       <!-- home: no back button -->
<AppHeader back-to="/" />           <!-- detail page: back button -->
```

### `MainButton`
Big button with an icon tile, title, subtitle and arrow.

| Prop | Type | Required | Meaning |
|---|---|---|---|
| `label` | String | yes | Title |
| `subtitle` | String | no | Grey text under the title |
| `icon` | String | yes | Icon name, e.g. `mdi:lock-open` |
| `to` | String | yes | Link |

```vue
<MainButton label="Mijn kluis" subtitle="Al uw documenten op één plek." icon="mdi:lock-open" to="/kluis" />
```

### `TabBar` + `TabBarItem`
`TabBar` gets a list of tabs and shows a `TabBarItem` (icon, label, link) for each one.
The current page is colored `primary` automatically.

```vue
<script setup>
const tabs = [
  { label: 'Home', icon: 'mdi:home', to: '/' },
  { label: 'Kluis', icon: 'mdi:lock', to: '/kluis' }
]
</script>
<template>
  <TabBar :items="tabs" />
</template>
```

The app's tabs are defined once in `app/layouts/default.vue`.

### `AppLogo`
The Gear logo. Used inside `AppHeader`.

## Adding a new page

1. Create `app/pages/<name>.vue`.
2. Start it with `<AppHeader back-to="/" />`.
3. Use `MainButton` for main actions and the card style above for everything else.
4. Need a new tab? Add one line to `tabs` in `app/layouts/default.vue`.

## Not done yet

- The wave background from the design (use `bg-page` / `bg-page-light` and an SVG).
- Real profile page and real content pages (now placeholders).
- Logo is rebuilt from two icons. Replace `AppLogo` with the real SVG when available.
