# Repolex Knowledge Graph of simonw/datasette-json-html

RDF knowledge graph data for [simonw/datasette-json-html](https://github.com/simonw/datasette-json-html), parsed by [repolex](https://repolex.ai).

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
rlex download simonw/datasette-json-html
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── bb4c2ed9538745f866a781be8db04f70e0531cc8
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── bb4c2ed9538745f866a781be8db04f70e0531cc8
│           └── chunk-001.nq.gz
├── blob
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 2ba2afc85f65dcd2aa7b6d78741812d06a1118ea.nq.gz
│   ├── 3270878931579eb0d844af38ad7ecfeb40bcfc4f.nq.gz
│   ├── 60680a744fefb2baddf159d5b030003e047195fe.nq.gz
│   ├── 74091fbf4dd2655365a867c955ad5e1f52659599.nq.gz
│   ├── 7d146d2fae2274420d93b37621b49bf9ceedbb90.nq.gz
│   ├── 958d123ec7fd19c7903f3a61068a7fe36f71f907.nq.gz
│   ├── 991d61c809056470c4f627bd00db9f188d99a634.nq.gz
│   ├── b6d1d3d7ab45c6045c420d8f2c0e8e7f63edeaec.nq.gz
│   ├── de5b95d82030e62036cb986b6000b07548bc95dd.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── bb4c2ed9538745f866a781be8db04f70e0531cc8.nq.gz
├── issue
│   └── issue.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 18 files
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

[simonw/datasette-json-html](https://github.com/simonw/datasette-json-html)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
