### Notes: front start, import with npm

## the starter is in (this repo)[https://github.com/julienemo/julie_front_starter]

**Main Front Assets Compiling**

- To compile JS : have webpack, specify one by one all files that are to be compiled in `entry` array of `webpack.config.js`. To import a whole folder as entry point is no recommended but possible. See `webpack.config.js`.

- To compile CSS: have CSS plugin (mini-css-extract-plugin), add parsing rule, import one by one all CSS and Cie to be compiled in one or multiple of JS files to be compiled, add plugin in `webpack.config.js`. Loaders that translate SASS and SCSS to CSS are another story.

- To compile images, have image loaders, add parsing rule, specify them in CSS and cie. Images called in html with normal src somehow works without compiling.

- To compile font, have file file loader, add font file parsing rule, specify font-face in corresponding CSS.

---

**On imports**

1. normally in a simple local one page without webpacker, calling import/export wouldn't even work

**Side notes**

1. `npm init` provides a choice to "entry". This doesn't seem to be related to the `webpack.config.js` entries

2. The relative path of any entry starts with `./` meaning, current directory.

3. Any time there is a change in the files that are to be bundled, need to re-bundle, otherwise the bundled result won't just update itself. Unless if I `watch`

4. What `watch` does, is to launch the build and not get out, so that every time any watched thing is changed, refresh the page and the change is on. Although it seems to work only when you don't change the `config.js`, otherwise need to rerun

5. `npm install -D` means install as devDependency

6. browsers have no clue of what `.scss` is. If we add `.scss` in `href` link without compiling, the best of what a browser can do is ignore this stylesheet. Yes, event in dev, event locally, no compiling, no understanding SCSS

7. to share variable definition across scss files, there are extra imports to do, that I didn't get...Just so I know that I can't just define var in another file and expect it to be recognized
