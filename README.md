# Repolex Knowledge Graph of Textualize/textual-plotext

RDF knowledge graph data for [Textualize/textual-plotext](https://github.com/Textualize/textual-plotext), parsed by [repolex](https://repolex.ai).

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
rlex download Textualize/textual-plotext
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 9fa23e7c486c69654b85445fe90bcb53c218925b
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 9fa23e7c486c69654b85445fe90bcb53c218925b
│           └── chunk-001.nq.gz
├── blob
│   ├── 1d337b7b906a3c3b30204a8afa5660a6ccdbd216.nq.gz
│   ├── 2ededb18131b44ec0ba7fe1e17234c2fb3b565e3.nq.gz
│   ├── 328119147416b6e8c9e0424a76fa34062b3b01f7.nq.gz
│   ├── 4577a59bc86daed03e8de659942256bf0c6fbffc.nq.gz
│   ├── 559a0a0f9dcb5202aaade51cc05c5474e755fb5e.nq.gz
│   ├── 64777da0fbb4b64e1c9bd2c05af650b9d8497a17.nq.gz
│   ├── 690c3ce361a3d276dac25aa9853e8d72d0afe412.nq.gz
│   ├── 6bdb69d406de3a6c92a2baeb478827b35da447e7.nq.gz
│   ├── 7615b8695ea3c2c8f107e43e9edb82815c51c565.nq.gz
│   ├── 80d505985cfd33884235ea51be383821c2d39b87.nq.gz
│   ├── 83bb4ef25a657a6932775f07af9a110e430ed574.nq.gz
│   ├── 8462cc2ca0e3141dbedf650961f345b150907c50.nq.gz
│   ├── 9a45d4a89f65b8c73fb56c5ad0eb82febaea9809.nq.gz
│   ├── a37d48f2854ab8f9112d428054fbcd4bb3ac4320.nq.gz
│   ├── ae1744f82b586ba7d9f3b27d713a55470e7f5273.nq.gz
│   ├── b329dada64317d5d5193b90c2f0080ab4c6957e1.nq.gz
│   ├── ba6ecd08dfc4aa8f964de33fbb1e6828088d2f3f.nq.gz
│   ├── c1ecd4f9c6ba00e21ec98acad1ca2ad9e2816258.nq.gz
│   ├── c9f36f8b5bce5ca06a3535b42be1e84f83b2bc27.nq.gz
│   ├── d7c6bc2d339b49278fe5840596a6f3b08351ba68.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e738234f986e5f42fe51b0b3c2a1249b1551c624.nq.gz
│   └── ea01567def2cb430f9353aca49804e77cb24fd11.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 9fa23e7c486c69654b85445fe90bcb53c218925b.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 31 files
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

[Textualize/textual-plotext](https://github.com/Textualize/textual-plotext)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
