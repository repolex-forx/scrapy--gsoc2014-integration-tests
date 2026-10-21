# Repolex Knowledge Graph of scrapy/gsoc2014-integration-tests

RDF knowledge graph data for [scrapy/gsoc2014-integration-tests](https://github.com/scrapy/gsoc2014-integration-tests), parsed by [repolex](https://repolex.ai).

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
rlex download scrapy/gsoc2014-integration-tests
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 81ee2765eaeeaaad6044a8347d3ccf414d895985
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 81ee2765eaeeaaad6044a8347d3ccf414d895985
│           └── chunk-001.nq.gz
├── blob
│   ├── 0ddf1cc8cd20cfc6bcc5aae070b75f9e9ade5935.nq.gz
│   ├── 3a24f7bc3c4eb4be0eb943da606591521d1385ee.nq.gz
│   ├── 6a9301d40941203b38b3e468728e027958ad8160.nq.gz
│   ├── 7098aea7fdc4033c661c37d86cdb80fa695fae40.nq.gz
│   ├── 770ad0f48116c0949ab1d8210dd1bfc0d158db5d.nq.gz
│   ├── 7744a37b242283d79fdb1de2a1bc03ff4dd7d90e.nq.gz
│   ├── 7f97e384350591a2fc9cfb7de72614f68775dc6e.nq.gz
│   ├── 94464dcb31c1a237ed52478c667edf5fb4c1e290.nq.gz
│   └── fd09f0b17b7d8b600ca4d4c14fb5d99592943177.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 81ee2765eaeeaaad6044a8347d3ccf414d895985.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 15 files
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

[scrapy/gsoc2014-integration-tests](https://github.com/scrapy/gsoc2014-integration-tests)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
