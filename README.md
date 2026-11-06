# Repolex Knowledge Graph of sphinx-contrib/proof

RDF knowledge graph data for [sphinx-contrib/proof](https://github.com/sphinx-contrib/proof), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download sphinx-contrib/proof
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4ec61dc59d7b9f837aee486c0ee0c2903c904130
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 4ec61dc59d7b9f837aee486c0ee0c2903c904130
│           └── chunk-001.nq.gz
├── blob
│   ├── 0b3f003ad23366ab022f1fb6f878e6026419c102.nq.gz
│   ├── 151168d7c3f14954972ac31a64c3c21c19fb89e8.nq.gz
│   ├── 15ea0fc19ee1ac354eadbbda8ca22780e021d741.nq.gz
│   ├── 222be0078f18424d8c791803031d9f2f59fc8aeb.nq.gz
│   ├── 2a3b632cbbb61720830d6b612ee5703a466a9396.nq.gz
│   ├── 2cb2b5195d808cfc99512f2cc559c125ac087e4e.nq.gz
│   ├── 35e07e66e868e23e69981b8046b028c710f7bf3a.nq.gz
│   ├── 4c35f030ca707b865bfa0fd9d837d0aa324f627a.nq.gz
│   ├── 55779763e7f4617ae5910f4ebbbbcfe5e5816abe.nq.gz
│   ├── 570672ed6efcf488c3cfaa48e91d1fb32437ee1c.nq.gz
│   ├── 5a36e7bf92392c1c38c90ad2dbb7752ceb66c878.nq.gz
│   ├── 5f9cfaa4f027e95a11e1e6093a3f81acd888821c.nq.gz
│   ├── 666c26f6d3f7a1c8ef5cf1d8cb0ac55a67aef25b.nq.gz
│   ├── 70c314103c3ca8dc3a3057f4c7354effc227d1f8.nq.gz
│   ├── 93472c9f83cf8937d6d53da6ee844606beac7cf5.nq.gz
│   ├── a485625d427fe22dc5597483e2581751cc127516.nq.gz
│   ├── afc9170eb61eede40bf977636d3a7f0e63012c0b.nq.gz
│   ├── b2115b9cd843db17be5a6887b671fbedbfb02ad1.nq.gz
│   ├── c000cad997ffe94b9e7d5d958e9d0f76d840b847.nq.gz
│   ├── c39995baedb3985f168f924311bca699dbe6bbee.nq.gz
│   ├── c563950bfb53f382331f1eb00916c2706d95c479.nq.gz
│   ├── c784c8af3e8251384c69a8d3ae9c7bd7aa05acf5.nq.gz
│   ├── d0a347dbfd26c2dd457fc290c78d0506f3a5ed71.nq.gz
│   ├── d4877e27865864fab02d2488e5e280b75cf0142b.nq.gz
│   ├── dba13ed2ddf783ee8118c6a581dbf75305f816a3.nq.gz
│   ├── df261310482f2eee775de1a32186779f943aa87c.nq.gz
│   ├── e14aa0f7d9e2cbb4e99d4ebb368bdafd791bd55c.nq.gz
│   ├── e278735b661add0c98619cee3b4807d9b63d1a8b.nq.gz
│   ├── ec470fd55ed6b762eb9567126a94ededa4ab1ad9.nq.gz
│   ├── fb8f97ac655b39763b697aa47f337819f2131526.nq.gz
│   ├── fb9abe8028375a1934f71db572e771caf1604fd7.nq.gz
│   └── fe0c530ddfbe608dcff6c90491b590cca009881d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 4ec61dc59d7b9f837aee486c0ee0c2903c904130.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 39 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[sphinx-contrib/proof](https://github.com/sphinx-contrib/proof)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
