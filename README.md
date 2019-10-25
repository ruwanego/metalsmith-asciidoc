# metalsmith-asciidoctor

[![npm version](https://badge.fury.io/js/metalsmith-asciidoc.svg)](https://badge.fury.io/js/metalsmith-asciidoctor)
[![Build Status](https://travis-ci.org/ruwanego/metalsmith-asciidoc.svg?branch=master)](https://travis-ci.org/ruwanego/metalsmith-asciidoc)

Metalsmith plugin to transform AsciiDoc files to HTML using [asciidoctor.js](http://asciidoctor.org/docs/asciidoctor.js/).

## Installation

With `npm`:

```bash
npm install --save-dev metalsmith-asciidoc
```

With `yarn`:

```bash
yarn add --dev metalsmith-asciidoc
```

## Usage

```js
var asciidoctor = require("metalsmith-asciidoc");

Metalsmith(__dirname)
  /* ... */
  .use(asciidoc())
  /* ... */
```

By default, the plugin will process all `.adoc` files and render them to HTML. You can customize this
default behavior by setting the `pattern` property on a configuration object.

```js
.use(asciidoctor({
  pattern: "**/*.asciidoc"
}))
```

You can also pass custom options to the `asciidoctor.js` by setting the `options` property. Please
note that this will also allow you to provide custom attributes.

```js
.use(asciidoctor({
  options: {
    safe: "safe",
    attributes: {
      "note-caption": "Hinweis",
      "warning-caption": "Warnung"
    }
  }
}))
```

## License

MIT
