# Nuxt Aos

[![npm version][npm-version-src]][npm-version-href]
[![npm downloads][npm-downloads-src]][npm-downloads-href]
[![License][license-src]][license-href]
[![Nuxt][nuxt-src]][nuxt-href]

A Nuxt module for adding animate on scroll to your application.

- [✨ &nbsp;Release Notes](/CHANGELOG.md)
<!-- - [🏀 Online playground](https://stackblitz.com/github/your-org/nuxt-aos?file=playground%2Fapp.vue) -->
<!-- - [📖 &nbsp;Documentation](https://example.com) -->

## Features

<!-- Highlight some of the features your module provide here -->
- ⛰ &nbsp;Easily add animate on scroll library to your nuxt app

## Quick Setup

1. Add `nuxt-aos` dependency to your project

```bash
# Using pnpm
pnpm add -D nuxt-aos

# Then (very important until the module has fixed)
pnpm add -D aos
```

2. Add `nuxt-aos` to the `modules` section of `nuxt.config.ts`

```js
export default defineNuxtConfig({
  modules: [
    'nuxt-aos'
  ]
})
```

follow the below step carefully it's important to make it work on Nuxt3

For example:

```html
<div data-aos="fade-up"></div>
```
Thanks to @YourItalianChef<br>
//////create [[plugins]] folder then create [[aos.js]] <br>
[Note:: Using ts idm will auto download the file b care 4]////////
```js
import {defineNuxtPlugin} from '#app'
import AOS from 'aos';
import 'aos/dist/aos.css';

export default defineNuxtPlugin((nuxtApp) => {
    if (typeof window !== 'undefined') {
        nuxtApp.AOS = AOS.init({
            once: false,
        });
    }
});
```
[[nuxt.config.ts]]
```js
plugins: [
        {src: '~/plugins/aos.js', mode: 'client'}
    ],
```
// webstorm autocomplete download both and activate in [libraries] settings//


use this link if you want to use aos on-the-fly
use "useHead" function on Nuxt3
```html
<link href="https://unpkg.com/aos@2.3.1/dist/aos.css" rel="stylesheet">
<script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>

```



## Development

```bash
# Install dependencies
npm install

# Generate type stubs
npm run dev:prepare

# Develop with the playground
npm run dev

# Build the playground
npm run dev:build

# Run ESLint
npm run lint

# Run Vitest
npm run test
npm run test:watch

# Release new version
npm run release
```

<!-- Badges -->
[npm-version-src]: https://img.shields.io/npm/v/nuxt-aos/latest.svg?style=flat&colorA=18181B&colorB=28CF8D
[npm-version-href]: https://npmjs.com/package/nuxt-aos

[npm-downloads-src]: https://img.shields.io/npm/dm/nuxt-aos.svg?style=flat&colorA=18181B&colorB=28CF8D
[npm-downloads-href]: https://npmjs.com/package/nuxt-aos

[license-src]: https://img.shields.io/npm/l/nuxt-aos.svg?style=flat&colorA=18181B&colorB=28CF8D
[license-href]: https://npmjs.com/package/nuxt-aos

[nuxt-src]: https://img.shields.io/badge/Nuxt-18181B?logo=nuxt.js
[nuxt-href]: https://nuxt.com
