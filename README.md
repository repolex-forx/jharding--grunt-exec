# Repolex Knowledge Graph of jharding/grunt-exec

RDF knowledge graph data for [jharding/grunt-exec](https://github.com/jharding/grunt-exec), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download jharding/grunt-exec
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 25fa05b466f6e016a8998a0cf42df6dc3019f85c
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 25fa05b466f6e016a8998a0cf42df6dc3019f85c.nq.gz
│   └── repolex
│       └── 25fa05b466f6e016a8998a0cf42df6dc3019f85c
│           └── chunk-001.nq.gz
├── blob
│   ├── 0096874542a98b7fc18261d9c3673d8489fbe086.nq.gz
│   ├── 3d3ff480ad68dd6124cff08adcabc53b0052837b.nq.gz
│   ├── 3f308e80614446b19c672df3a8e2aef5145c815c.nq.gz
│   ├── 423efe7ee014b0b6ff048d02e1949beb5861ab98.nq.gz
│   ├── 6585f99d4ff52d0163ec86337991e4ae8d003eed.nq.gz
│   ├── 8d5b7ae2218ca5a4fb40309fc607c34d4fb9c5ef.nq.gz
│   ├── a59d9b8ba1259bdd550328ba4ea6264416049a0a.nq.gz
│   ├── e22e37338499e2e9ccc600c41b4c06696e7aaba2.nq.gz
│   └── fc6e747990d4b0c33f33b554a4a3d52828ba997e.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 25fa05b466f6e016a8998a0cf42df6dc3019f85c.nq.gz
├── filetree
│   └── 25fa05b466f6e016a8998a0cf42df6dc3019f85c.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 19 files
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

## Source repository

[jharding/grunt-exec](https://github.com/jharding/grunt-exec)

---
*Parsed on 2026-04-13 by [repolex](https://repolex.ai)*
