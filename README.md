# Repolex Knowledge Graph of NousResearch/hermes-plugin-byterover

RDF knowledge graph data for [NousResearch/hermes-plugin-byterover](https://github.com/NousResearch/hermes-plugin-byterover), parsed by [repolex](https://repolex.ai).

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
rlex download NousResearch/hermes-plugin-byterover
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 644b5d8007ece364fd09122d9b225a00442f5f1f
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 644b5d8007ece364fd09122d9b225a00442f5f1f.nq.gz
│   └── repolex
│       └── 644b5d8007ece364fd09122d9b225a00442f5f1f
│           └── chunk-001.nq.gz
├── blob
│   ├── 00f2d38d8063d0c6b219c0081e51888063b0c55e.nq.gz
│   ├── 3cfdcd2125af8de7bddf5059b7c8eb2460d8199f.nq.gz
│   ├── 6b93a272ffcf81348d5dbb6f7324e85b0a4a28e4.nq.gz
│   ├── 6e23f0a828bb644a4fc40caec89cd965378ccbd5.nq.gz
│   ├── 75410e73319c72cd3e991a501c5455eb78f38375.nq.gz
│   ├── a6645c3c529899ac21d8ed9e51a19958a5614920.nq.gz
│   └── e357b1208cf65f2c0655d99ba6c58a6819120505.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 644b5d8007ece364fd09122d9b225a00442f5f1f.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 14 files
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

[NousResearch/hermes-plugin-byterover](https://github.com/NousResearch/hermes-plugin-byterover)

---
*Parsed on 2026-09-30 by [repolex](https://repolex.ai)*
