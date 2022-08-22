---
layout: default.liquid
title: Wasmtime
---

<style>
section pre {
  padding: 1em;
}
</style>

<section class="section-hero">
<div class="container w-container">

# Wasmtime

## A fast and secure runtime for WebAssembly

A <a href="https://bytecodealliance.org/">Bytecode Alliance</a> project

</div>
</section>

<section id="install-section">
<div class="container w-container">

## Install

<style>
.dn {
  display: none;
}
.db {
  display: block;
}
</style>

<div id="platform-instructions-unix" class="dn">

It looks like you’re running macOS or Linux. To download and install Wasmtime,
run the following in your terminal, then follow the on-screen instructions.

```sh
curl https://wasmtime.dev/install.sh -sSf | bash
```

You can also download binaries directly from the [GitHub
Releases](https://github.com/bytecodealliance/wasmtime/releases) page.

</div>

<div id="platform-instructions-win" class="dn">

It looks like you’re running Windows. To install Wasmtime, download and run the
following, and then follow the onscreen instructions.

[Wasmtime Installer](https://github.com/bytecodealliance/wasmtime/releases/download/dev/wasmtime-dev-x86_64-windows.msi)

If you’re a Windows Subsystem for Linux user run the following in your terminal,
then follow the on-screen instructions to install Wasmtime.

```sh
curl https://wasmtime.dev/install.sh -sSf | bash
```

</div>

<div id="platform-instructions-default" class="db">

If you’re running macOS or Linux, download and install Wasmtime by running the
following in your terminal and following the on-screen instructions.

```sh
curl https://wasmtime.dev/install.sh -sSf | bash
```

--------------------------------------------------------------------------------

If you are running Windows, download and run the [Wasmtime
Installer](https://github.com/bytecodealliance/wasmtime/releases/download/dev/wasmtime-dev-x86_64-windows.msi)
then follow the on-screen instructions.

--------------------------------------------------------------------------------

Alternatively, you can download releases for all supported platforms from the
[Wasmtime GitHub page](https://github.com/bytecodealliance/wasmtime/releases).

</div>

</div>
</section>

<section class="section-tinted">
<div class="container w-container">

## Example

If you've got the [Rust compiler
installed](https://www.rust-lang.org/tools/install) then you can take some Rust
source code:

```rust
fn main() {
    println!("Hello, world!");
}
```

and compile/run it with:

```sh
$ rustup target add wasm32-wasi
$ rustc hello.rs --target wasm32-wasi
$ wasmtime hello.wasm
Hello, world!
```

</div>
</section>

<section>
<div class="container w-container">

## Features

* **Fast**. Wasmtime is built on the optimizing [Cranelift] code generator to
  quickly generate high-quality machine code either at runtime or
  ahead-of-time. Wasmtime's runtime is also optimized for cases such as
  efficient instantiation, low-overhead transitions between the embedder and
  wasm, and scalability of concurrent instances.

* **[Secure]**. Wasmtime's development is strongly focused on the correctness of
  its implementation with 24/7 fuzzing donated by [Google's OSS Fuzz],
  leveraging Rust's API and runtime safety guarantees, careful design of
  features and APIs through an [RFC process], a [security policy] in place
  for when things go wrong, and a [release policy] for patching older versions
  as well. We follow best practices for defense-in-depth and known
  protections and mitigations for issues like Spectre. Finally, we're working
  to push the state-of-the-art by collaborating with academic
  researchers to formally verify critical parts of Wasmtime and Cranelift.

* **[Configurable]**. Wastime supports a rich set of APIs and build time
  configuration to provide many options such as further means of restricting
  WebAssembly beyond its basic guarantees such as its CPU and Memory
  consumption. Wasmtime also runs in tiny environments all the way up to massive
  servers with many concurrent instances.

* **[WASI]**. Wasmtime supports a rich set of APIs for interacting with the host
  environment through the [WASI standard](https://wasi.dev).

* **[Standards Compliant]**. Wasmtime passes the [official WebAssembly test
  suite](https://github.com/WebAssembly/testsuite), implements the [official C
  API of wasm](https://github.com/WebAssembly/wasm-c-api), and implements
  [future proposals to WebAssembly](https://github.com/WebAssembly/proposals) as
  well. Wasmtime developers are intimately engaged with the WebAssembly
  standards process all along the way too.

[Wasmtime]: https://github.com/bytecodealliance/wasmtime
[Cranelift]: https://github.com/bytecodealliance/wasmtime/blob/main/cranelift/README.md
[Google's OSS Fuzz]: https://google.github.io/oss-fuzz/
[security policy]: https://bytecodealliance.org/security
[RFC process]: https://github.com/bytecodealliance/rfcs
[release policy]: https://docs.wasmtime.dev/stability-release.html
[Secure]: https://docs.wasmtime.dev/security.html
[Configurable]: https://docs.rs/wasmtime/latest/wasmtime/struct.Config.html
[WASI]: https://docs.rs/wasmtime-wasi/latest/wasmtime_wasi/
[Standards Compliant]: https://docs.wasmtime.dev/stability-wasm-proposals-support.html

</div>
</section>

<section>
<div class="container w-container">

## Language Support

You can use Wasmtime from a variety of different languages through embeddings of
the implementation:

* **[Rust]** - the [`wasmtime` crate]
* **[C]** - the [`wasm.h`, `wasi.h`, and `wasmtime.h` headers][c-headers], [CMake](crates/c-api/CMakeLists.txt) or [`wasmtime` Conan package]
* **[C++]** - the [`wasmtime-cpp` repository][C++] or use [`wasmtime-cpp` Conan package]
* **[Python]** - the [`wasmtime` PyPI package]
* **[.NET]** - the [`Wasmtime` NuGet package]
* **[Go]** - the [`wasmtime-go` repository]

[Rust]: https://bytecodealliance.github.io/wasmtime/lang-rust.html
[C]: https://bytecodealliance.github.io/wasmtime/examples-c-embed.html
[`wasmtime` crate]: https://crates.io/crates/wasmtime
[c-headers]: https://bytecodealliance.github.io/wasmtime/c-api/
[Python]: https://bytecodealliance.github.io/wasmtime/lang-python.html
[`wasmtime` PyPI package]: https://pypi.org/project/wasmtime/
[.NET]: https://bytecodealliance.github.io/wasmtime/lang-dotnet.html
[`Wasmtime` NuGet package]: https://www.nuget.org/packages/Wasmtime
[Go]: https://bytecodealliance.github.io/wasmtime/lang-go.html
[`wasmtime-go` repository]: https://pkg.go.dev/github.com/bytecodealliance/wasmtime-go
[C++]: https://github.com/bytecodealliance/wasmtime-cpp
[`wasmtime` Conan package]: https://conan.io/center/wasmtime
[`wasmtime-cpp` Conan package]: https://conan.io/center/wasmtime-cpp

</div>
</section>

<section>
<div class="container w-container">

## Documentation

The [wasmtime guide][guide] is the best starting point to learn about what
Wasmtime can do for you or help answer your questions about Wasmtime. If you're
curious in contributing to Wasmtime, [it can also help you do
that][contributing]!

[contributing]: https://bytecodealliance.github.io/wasmtime/contributing.html
[guide]: https://bytecodealliance.github.io/wasmtime

</div>
</section>

<script src="assets/scripts/tools-install.js"></script>
<script>
  select_platform();
</script>
