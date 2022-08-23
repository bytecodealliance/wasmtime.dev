# The [`wasmtime.dev`](https://wasmtime.dev/) Homepage

The Wasmtime homepage is generated with [the Cobalt static site
generator](https://cobalt-org.github.io).

## Overview

Every file and directory that isn't prefixed with `.` or `_` ends up in the
built website.

Markdown files are rendered to HTML.

Each file is processed by the `liquid` templating engine so we can
include/extend/loop/etc should we choose to.

* `_cobalt.yml`: Cobalt static site generator configuration.
* `index.md`: The markdown source for the main `index.html` page.
* `install.sh`: The bash script users curl to install Wasmtime on macOS and
  Linux.
* `_layouts/`: HTML skeletons that we can use/extend for individual pages.
  * `_layouts/default.liquid`: The default HTML skeleton for our website.
* `assets/`: Static assets: JS, CSS, images, fonts, etc...
  * `assets/css`: CSS files.
    * `assets/css/fonts`: Webfonts.
  * `assets/images`: Image files.
  * `assets/scripts`: JS scripts.
* `_site/`: The built website. This is checked into the repo so github pages can
  access it. Don't edit these files by hand, edit the sources and rebuild
  instead. Don't review these files, review the original sources instead. CI
  will check that `_site` doesn't diverge from rebuilding the original sources.

## Set Up

Install the `cobalt` CLI:

```
$ cargo install cobalt-bin
```

## Building

To re-build the `wasmtime.dev` website, run

```
cobalt build
```

The built site will be in `_site/`.

## Development

To start a local server and rebuild the website whenever a file is changed, run

```
cobalt serve
```

and visit http://localhost:1024/ in your browser.
