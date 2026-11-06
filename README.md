# Repolex Knowledge Graph of apple/ml-fastvit

RDF knowledge graph data for [apple/ml-fastvit](https://github.com/apple/ml-fastvit), parsed by [repolex](https://repolex.ai).

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
rlex download apple/ml-fastvit
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 441ad35437f14b3b13f37ac391726e096d4e0e72
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 441ad35437f14b3b13f37ac391726e096d4e0e72
│           └── chunk-001.nq.gz
├── blob
│   ├── 1aafce737c3cd106bcf118016d5f870960269779.nq.gz
│   ├── 1e2ee9cbb6a667b9f5fe364d991fa763f6af3e2e.nq.gz
│   ├── 2af0157fbec55c216e06ef9a55f4a98e13a29d46.nq.gz
│   ├── 38675e743f5c1b72c67749e53aa1cff27749c5ce.nq.gz
│   ├── 4078c3a4d368d672dc3cfffc27a7e75c01342507.nq.gz
│   ├── 426704eed499ee3901b3fa968176f5bd2a9cf154.nq.gz
│   ├── 50b5c56c8624c4981b0522a8f40a85f2b2a6b0a8.nq.gz
│   ├── 54a5a14f3d5fa8d6b1b0305990ae179221f64b23.nq.gz
│   ├── 56ee291cff411ba879fe54a02b50b8ccd9d36003.nq.gz
│   ├── 660677a087c6f3d800806929b5d544bdc3c15a2c.nq.gz
│   ├── 6cc4a3612f7d7ce639d1b333bd0e110e930ff759.nq.gz
│   ├── 6f0363ea7a219828345fb8901ccf098a152e3eed.nq.gz
│   ├── 82601f0ab5a9e532be9dd57f454b02fb26348149.nq.gz
│   ├── 97d350dd23d63a4bed6267014002f22f2b920913.nq.gz
│   ├── b71a2698eaf2b2b549ad067534fd3645568e3d8f.nq.gz
│   ├── ba9db6118dcad815fa4ca3a620bc89328a8e50a0.nq.gz
│   ├── bc67583aa0a4673f63151b11196d42ea514c39e1.nq.gz
│   ├── c7a9b0d0a49f92c9730cd4194e73e61930af2cdc.nq.gz
│   ├── d6e0eb7a480d0a6603bfadcf2476df097ae4ab24.nq.gz
│   ├── dade95935e263d349498d7d4d8a4bac9c1ef6267.nq.gz
│   ├── db3e723822e9efe6a57c23d540b92b9a48e9cf29.nq.gz
│   ├── dcd560d6da419932d30d2a050d56e8263e1d1ffc.nq.gz
│   └── ef52fcb78b8e2ddf2ce56c5cda9eff876b1206df.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 441ad35437f14b3b13f37ac391726e096d4e0e72.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 29 files
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

[apple/ml-fastvit](https://github.com/apple/ml-fastvit)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
