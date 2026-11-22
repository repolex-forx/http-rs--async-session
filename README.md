# Repolex Knowledge Graph of http-rs/async-session

RDF knowledge graph data for [http-rs/async-session](https://github.com/http-rs/async-session), parsed by [repolex](https://repolex.ai).

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
rlex download http-rs/async-session
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 9a2805dc8a4dc1f43b6337106a96c52472b47573
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 9a2805dc8a4dc1f43b6337106a96c52472b47573.nq.gz
│   └── repolex
│       └── 9a2805dc8a4dc1f43b6337106a96c52472b47573
│           └── chunk-001.nq.gz
├── blob
│   ├── 4212ab6efa37e63bffa2a51bbcc53ca6860fcf4f.nq.gz
│   ├── 45ea29fa301c66616f69e89349bb324561033225.nq.gz
│   ├── 5470b5abde56aac1dd99f6b6b5ba2bcc3a768861.nq.gz
│   ├── 5c747ef10d3499ae12c1a940726d3dc5789cbded.nq.gz
│   ├── 7fb65de37b70336125ba25d204db569fe6e7a413.nq.gz
│   ├── 860085a78beda9efced4b7ce07a10b18b774cef9.nq.gz
│   ├── 8b137891791fe96927ad78e64b0aad7bded08bdc.nq.gz
│   ├── 991cf25c75c91b52ca4ba37d42dbb1233362bf82.nq.gz
│   ├── a11172a7f118fab3579b834bd5305121a2a908b6.nq.gz
│   ├── b75a1449ca02dbf707674ad43a9cd7c449d651ef.nq.gz
│   ├── bc76cbe97322938a8db77cd63b62ecb870a6585e.nq.gz
│   ├── d02f05007f4d64783bf3abad2fe425cf783953a4.nq.gz
│   ├── d0c31b24bba4bed8ec25ed631070259888c558d8.nq.gz
│   └── d149485aff4dfd7f07da2ac217ef6745b4a56116.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 9a2805dc8a4dc1f43b6337106a96c52472b47573.nq.gz
├── filetree
│   └── 9a2805dc8a4dc1f43b6337106a96c52472b47573.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 24 files
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

[http-rs/async-session](https://github.com/http-rs/async-session)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
