# Repolex Knowledge Graph of klen/muffin-redis

RDF knowledge graph data for [klen/muffin-redis](https://github.com/klen/muffin-redis), parsed by [repolex](https://repolex.ai).

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
rlex download klen/muffin-redis
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 423bfc31bf4aa59528dd5cb9c324f7669b276069
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 423bfc31bf4aa59528dd5cb9c324f7669b276069
│           └── chunk-001.nq.gz
├── blob
│   ├── 07de1baef6aaf3f657dff669366511c71e159b8b.nq.gz
│   ├── 0a6ee958310ca78a98bf4803c291d5898c7fd5b4.nq.gz
│   ├── 1fc2edd33ecad2907f9520e79600ff3dbe7f04ad.nq.gz
│   ├── 23c5c150f58bdd129447223d88288e859f8cccb1.nq.gz
│   ├── 5f1d5686f3dc12105665875988bbe0b90d32c2bc.nq.gz
│   ├── 64db419928aa7360cc84a843b5583f5d86a47ffc.nq.gz
│   ├── 666ce2a519fd8f0c3599a11f968422b82612ca92.nq.gz
│   ├── 6a8f2f98f9170eeb0f5f92c8940455903a591c56.nq.gz
│   ├── 6e3c0e6da89a0d27531245e6edfdc5bc7623b8e3.nq.gz
│   ├── 78df056a6afd6b2f7c5a8695635380a19f30acd9.nq.gz
│   ├── 7a3f07ab83552f47a8705fa5d22729a324a2f71a.nq.gz
│   ├── 7f819e60e1a9da7c06d5438727cc80d9f50fd426.nq.gz
│   ├── 8be5a75df0676c4198821a519cc54ccdbbba7418.nq.gz
│   ├── abd6850fadeb0c659cee0bfccbd1c0d740b965b3.nq.gz
│   ├── aeba5a06726f4598576c8bf6f35d0a254f496d79.nq.gz
│   ├── b19861789d39f0fed14cbecea92ecbef1f33bde6.nq.gz
│   ├── b5d6009ec33410833949315c47199e524a646dde.nq.gz
│   ├── b88f06576a9a941938191b09e9f695867c4c3c52.nq.gz
│   ├── c9db9563b5d0a187416a8ab6562a070f4aafae3d.nq.gz
│   ├── ce48f87110f5a00c4f3320f9ed0c8e630cb23daf.nq.gz
│   ├── d063574d7f82f53b73cccb989fc0dc1b523251e9.nq.gz
│   ├── d5a0d0a97e5fc1d7c12603419177f86dc2396a0d.nq.gz
│   ├── e4dcc8624c52ea3d704cb10151f72a560a89ee69.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── e728d03676c20ba87a39556e60b642f5df17ebde.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 423bfc31bf4aa59528dd5cb9c324f7669b276069.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 33 files
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

[klen/muffin-redis](https://github.com/klen/muffin-redis)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
