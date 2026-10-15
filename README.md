# Repolex Knowledge Graph of sphinx-contrib/ansi

RDF knowledge graph data for [sphinx-contrib/ansi](https://github.com/sphinx-contrib/ansi), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/ansi
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── af63f758b13ebde70afd548a755234bd7dd69295
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── af63f758b13ebde70afd548a755234bd7dd69295
│           └── chunk-001.nq.gz
├── blob
│   ├── 179157f2cdf93a000dfafe0d11db62128857fed5.nq.gz
│   ├── 3289f0c13f97b7b12e49e251cb6a05a591254f7d.nq.gz
│   ├── 384384e24606b91e07847afb727d8df901b977b2.nq.gz
│   ├── 3a3a474ddd3c06d0436f235ea3bb10151e94cdf1.nq.gz
│   ├── 6abc150ddb3eb8368a7a5ec96ab87e63ef97c69e.nq.gz
│   ├── 8230be5cf5cf9a0bf5b61e8e825fc2af8c244d74.nq.gz
│   ├── 90d357187b9a783e51f7af3739422fe99be7e7a5.nq.gz
│   ├── 97d09eaff69347ac202a434383ed9bd4119c0430.nq.gz
│   ├── 98f078a212eed1b9db7c9c74eb1cc2f054d32054.nq.gz
│   ├── 99eceb39a172ccaaddc7fa16998b37ad1fd7f5ee.nq.gz
│   ├── 9efd9f838951d3febc930d94869750da3f41cf8c.nq.gz
│   ├── a444debdfcf6f65fc44e4e18bbb10573e61aa5cb.nq.gz
│   ├── ab1c75be492b53b2723038814d33352c2be9f24c.nq.gz
│   ├── b5a7dc29ef0f7f3593b1c61cfc5dfe8a17d3918c.nq.gz
│   ├── bb5094f45f30bdfd6b063a0690f3035c8e122a2c.nq.gz
│   ├── d86677a1ccaf9775297196a115c5ddf4a924c6cb.nq.gz
│   ├── d8df63eb44c982d052aee02efbce6d63a8462bc9.nq.gz
│   ├── ddfdfc104051b43417b2f7db22b1efb0cb299853.nq.gz
│   ├── e50cd58714cd6ed113623beec9b82cfcd60e2c15.nq.gz
│   └── ebc4aa30b5c6427b64f2c418c7d9b8cdb02ff624.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── af63f758b13ebde70afd548a755234bd7dd69295.nq.gz
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

[sphinx-contrib/ansi](https://github.com/sphinx-contrib/ansi)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
