# Repolex Knowledge Graph of samuelcolvin/batson-perf

RDF knowledge graph data for [samuelcolvin/batson-perf](https://github.com/samuelcolvin/batson-perf), parsed by [repolex](https://repolex.ai).

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
rlex download samuelcolvin/batson-perf
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 107627c5bab579127d1e2ae0fd9a512b1e2c1fc8
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 107627c5bab579127d1e2ae0fd9a512b1e2c1fc8
│           └── chunk-001.nq.gz
├── blob
│   ├── 43287fbcf266f1dab0fd54bd296351bc533c43e6.nq.gz
│   ├── 739c51a84a17fac29247b9742b23290c0aeafed0.nq.gz
│   ├── 7773e7f2317204e211d0f94005ee7dfcc35bc7b3.nq.gz
│   ├── 7e58cd7bca7f1e10b8780f6d5064e60da3906a26.nq.gz
│   ├── ac8f051f5b462db6a196f80e87bab8bd0751e5c9.nq.gz
│   └── d77a23c2ea8e4a07900d1ae9289402c4c0cf4885.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 107627c5bab579127d1e2ae0fd9a512b1e2c1fc8.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 12 files
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

[samuelcolvin/batson-perf](https://github.com/samuelcolvin/batson-perf)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
