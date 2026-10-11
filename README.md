# Repolex Knowledge Graph of python-trio/trzmq

RDF knowledge graph data for [python-trio/trzmq](https://github.com/python-trio/trzmq), parsed by [repolex](https://repolex.ai).

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
rlex download python-trio/trzmq
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 275ce1d9272456bc44230b7c9e3dc93c318e8978
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 275ce1d9272456bc44230b7c9e3dc93c318e8978
│           └── chunk-001.nq.gz
├── blob
│   ├── 12d553b6f869d34aebb3f7c418f8bd275bb9d36e.nq.gz
│   ├── 14ab4eff15087f5cbc887af27a8d4fdb3e6e0f69.nq.gz
│   ├── 24560ef62986eac2f961bcad9bce4111353cdfbd.nq.gz
│   ├── 5ae330f9d0d9dd3bb564341578310a5896cf9db8.nq.gz
│   └── bdbf33de373664be3d1a63829c7df358b4bb6e25.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 275ce1d9272456bc44230b7c9e3dc93c318e8978.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 13 files
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

[python-trio/trzmq](https://github.com/python-trio/trzmq)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
