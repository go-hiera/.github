<p align="center"><img src="https://raw.githubusercontent.com/go-hiera/brand/main/social/go-hiera.png" alt="go-hiera" width="640"></p>

<h1 align="center">go-hiera</h1>
<p align="center"><strong>Puppet's Hiera 5 hierarchical data-lookup engine in pure Go — no cgo.</strong></p>

<p align="center">
  🌐 <a href="https://go-hiera.github.io">Website</a> ·
  📚 <a href="https://go-hiera.github.io/docs/">Documentation</a>
</p>

<p align="center">
  <a href="https://go-hiera.github.io/docs/"><img alt="Docs" src="https://img.shields.io/badge/docs-mkdocs--material-7C3AED?style=flat-square"></a>
  <a href="https://github.com/go-hiera/hiera/blob/main/LICENSE"><img alt="License: BSD-3-Clause" src="https://img.shields.io/badge/license-BSD--3--Clause-blue?style=flat-square"></a>
  <img alt="Go 1.26.4+" src="https://img.shields.io/badge/go-1.26.4%2B-00ADD8?style=flat-square&logo=go&logoColor=white">
  <img alt="Coverage 100%" src="https://img.shields.io/badge/coverage-100%25-1a7f37?style=flat-square">
</p>

---

**go-hiera** is a pure-Go (no cgo) reimplementation of Puppet's
[**Hiera 5**](https://www.puppet.com/docs/puppet/latest/hiera.html) hierarchical
data-lookup engine. It loads a `hiera.yaml` v5 configuration, walks the
configured hierarchy of data sources, and resolves a key to a typed value —
honouring Hiera's merge behaviours, per-key `lookup_options`, dotted-key
digging, and the full `%{...}` interpolation grammar, with interpolation-loop
detection.

Resolving a hierarchy of YAML/JSON data with merge and interpolation is fully
deterministic and needs **no Ruby interpreter**, so it lives here as pure Go.
The variable/fact **`Scope`** it resolves interpolation against is a pluggable
interface the caller injects, so a facts engine such as **go-facter** — or the
Ruby binding **go-ruby-hiera**, which maps Ruby's `Hiera` API and Puppet's
`lookup()` / automatic data binding onto it — plugs its own facts in without a
hard dependency.

## Repositories

| Repo | What it is |
| --- | --- |
| [**hiera**](https://github.com/go-hiera/hiera) | The Hiera 5 lookup engine: config loader, `yaml_data`/`json_data` backends, `first`/`unique`/`hash`/`deep` merges with `lookup_options`, dotted dig, and `%{...}` interpolation. |
| [**brand**](https://github.com/go-hiera/brand) | Logo and brand assets for the org. |
| [**docs**](https://github.com/go-hiera/docs) | MkDocs-Material + mike documentation site. |
| [**go-hiera.github.io**](https://github.com/go-hiera/go-hiera.github.io) | Hugo landing page. |

Pure-Go, CGO-free, BSD-3-Clause, 100% test coverage, and green across the six
64-bit Go targets (amd64, arm64, riscv64, loong64, ppc64le, s390x).
