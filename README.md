# Repolex Knowledge Graph of kennethreitz/crayons

RDF knowledge graph data for [kennethreitz/crayons](https://github.com/kennethreitz/crayons), parsed by [repolex](https://repolex.ai).

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
rlex download kennethreitz/crayons
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── b1b78c9a357e0c348a1288ee5ef0318f08ccf257
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── b1b78c9a357e0c348a1288ee5ef0318f08ccf257
│           └── chunk-001.nq.gz
├── blob
│   ├── 2372a83eec90c989aa1093a6a499fe3ccc82ce01.nq.gz
│   ├── 6dc492fcb0efc3e658a5f62f1b8ec81e3bc49a3c.nq.gz
│   ├── 791930b366c5ba3e14f8f219eb842a88b4fc1503.nq.gz
│   ├── 7f0daf5f56e312007129183e9a626f6b3c27a313.nq.gz
│   ├── 7f35db24e1e4fb373df261eed9e860b2c89e71fe.nq.gz
│   ├── 8b1b549329e186d5c128b5f653c08b8b80fabfa8.nq.gz
│   ├── ccb33cfec2800574eb07496846948be2d06ef7e0.nq.gz
│   ├── d59698306826ac1189825113c2a6b19a9da2c3eb.nq.gz
│   ├── fc298c656f369004615e7bd836d3436c733db33e.nq.gz
│   └── fc4b04a0e0af27f0a611200caf53e953a1662a21.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── b1b78c9a357e0c348a1288ee5ef0318f08ccf257.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 18 files
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

[kennethreitz/crayons](https://github.com/kennethreitz/crayons)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
