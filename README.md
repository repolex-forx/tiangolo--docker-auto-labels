# Repolex Knowledge Graph of tiangolo/docker-auto-labels

RDF knowledge graph data for [tiangolo/docker-auto-labels](https://github.com/tiangolo/docker-auto-labels), parsed by [repolex](https://repolex.ai).

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
rlex download tiangolo/docker-auto-labels
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c11b19fc8a16720b6f1d917cebf255701ebff5a0
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── c11b19fc8a16720b6f1d917cebf255701ebff5a0
│           └── chunk-001.nq.gz
├── blob
│   ├── 0045fb8182cf94a55db192aa3bc8c4c7e033da47.nq.gz
│   ├── 092988dca25771a498ae9640531336263689fb0d.nq.gz
│   ├── 0ffc101a3f23548392499fe5104f3f8cf4d4e91b.nq.gz
│   ├── 3036cfc7271cd9a226433b909e4867011608e155.nq.gz
│   ├── 32ea3e8d48ad2251ef686d4980959323ffbf6a18.nq.gz
│   ├── 38d00c5ef5d9580c7c04e7cdfe048352c7283e12.nq.gz
│   ├── 6beb113301f07a74ebb328f5ec1abc8cd17818a5.nq.gz
│   ├── 80867e81c43b391b1b5b81876a42d4d6372c82f0.nq.gz
│   ├── 91428a6aaa2eaf590760dd48279b8b829b54034a.nq.gz
│   ├── 9453cd011dec9d54f6ba877ad4bd7357b51280c4.nq.gz
│   ├── a643b2696305b386b93409e77f89e050b0f63c88.nq.gz
│   ├── a6587aeab980dde9eedcf5fe7a5314f6ce9bff98.nq.gz
│   ├── bc89f2c3c16b38364adaa93272971c0e99c161db.nq.gz
│   ├── c7b27d7548dbf299ca332ad1d5d829a39eda7463.nq.gz
│   ├── c90bfcbad623f4a61ba783e79cfd5002ce2235de.nq.gz
│   ├── cd972a0ba47221bf96acedfaed8f3b5cba819849.nq.gz
│   ├── d56378811242de023474893e83a1b5905b66c2ae.nq.gz
│   ├── df112e9d602a3e49dc11d36c4b774a90b526554a.nq.gz
│   ├── e051c911f416e91ee1c5eee7c853d0226c052f80.nq.gz
│   └── ed61140615b3128b7667f153d9b372fc8e2656df.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── c11b19fc8a16720b6f1d917cebf255701ebff5a0.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 28 files
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

[tiangolo/docker-auto-labels](https://github.com/tiangolo/docker-auto-labels)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
