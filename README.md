# The [`wasmtime.dev`](https://wasmtime.dev/) Homepage

The Wasmtime homepage is generated with [the Cobalt static site
generator](https://cobalt-org.github.io).

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
