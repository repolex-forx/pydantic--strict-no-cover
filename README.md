# Repolex Knowledge Graph of pydantic/strict-no-cover

RDF knowledge graph data for [pydantic/strict-no-cover](https://github.com/pydantic/strict-no-cover), parsed by [repolex](https://repolex.ai).

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
rlex download pydantic/strict-no-cover
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 6c644106e03138abae01d8d60105d4a7ad4916a1
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 6c644106e03138abae01d8d60105d4a7ad4916a1
│           └── chunk-001.nq.gz
├── blob
│   ├── 0158d7f4437a7c681a37010be74fafff8254b59e.nq.gz
│   ├── 24ee5b1be9961e38a503c8e764b7385dbb6ba124.nq.gz
│   ├── 2f32272eace56ddca96ef8ef92e5ffe930f1035b.nq.gz
│   ├── 36168bbdae093491df1c89d8ec89bd7876ee2a99.nq.gz
│   ├── 3abf8f801d0fbe23077e40ffb5ff9516d2e39333.nq.gz
│   ├── 505a3b1ca2716907d5b292ab90c36df043c42bb6.nq.gz
│   ├── a01521bb5ea8b1a1c0484cfedb57073002d124d7.nq.gz
│   ├── a66987802750c5472b2d6e555caffaa57cabfbbc.nq.gz
│   ├── b7354be2cee1d4177c56c2c4e015ec8e02fd2c62.nq.gz
│   ├── bf110f1102e35a9647413c032adedace0ff31f58.nq.gz
│   └── c2f91267dadaba33339c4b8e15e26fd5e1ea4cdd.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 6c644106e03138abae01d8d60105d4a7ad4916a1.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 19 files
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

[pydantic/strict-no-cover](https://github.com/pydantic/strict-no-cover)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
