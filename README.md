# scss-utils

SASS (SCSS specifically) utilities that I use in my projects

![Dart Sass](https://img.shields.io/badge/Dart%20Sass-1.52.2-ff69b4)
![License](https://img.shields.io/github/license/tinytengu/scss-utils)
![Issues](https://img.shields.io/github/issues/tinytengu/scss-utils)
![Forks](https://img.shields.io/github/forks/tinytengu/scss-utils)
![Stars](https://img.shields.io/github/stars/tinytengu/scss-utils)

# Structure

- [breakpoints](https://github.com/tinytengu/scss-utils/blob/main/src/_breakpoints.scss) - media-query breakpoints
- [colors](https://github.com/tinytengu/scss-utils/blob/main/src/_colors.scss) - colors utilities
- [utils](https://github.com/tinytengu/scss-utils/blob/main/src/_utils.scss) - useful utility stuff

# How to use

If you're using Vite make sure you installed `sass` package, then simply put the following in your `defineConfig` function located in `vite.config.js` file:

```javascript
css: {
  preprocessorOptions: {
    scss: {
      additionalData: `
      @use "./src/css/scss-utils" as su;
      `,
    },
  },
}
```

Where `"./src/css/scss-utils"` is the path to `scss-utils` folder.

It will look kinda like so:

```javascript
import { defineConfig } from "vite";
import vue from "@vitejs/plugin-vue";

export default defineConfig({
  plugins: [vue({ reactivityTransform: true })],
  css: {
    preprocessorOptions: {
      scss: {
        additionalData: `
        @use "./src/css/scss-utils" as su;
        `,
      },
    },
  },
});
```

Now feel free to use anything from `scss-utils` using `su` namespace, e.g:

```scss
@debug su.color(red, 800);
@debug su.replace-sub("scss utils", " ", "-");

.row {
  width: 100vw;

  @include md {
    width: 500px;
  }
}

.column {
  height: 100vh;

  @include breakpoint(xxl) {
    height: 50vh;
  }
}
```

Of coures, you can change `namespace` for whatever name you want, doesn't matter.

---
