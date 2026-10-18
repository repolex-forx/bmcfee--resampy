# Repolex Knowledge Graph of bmcfee/resampy

RDF knowledge graph data for [bmcfee/resampy](https://github.com/bmcfee/resampy), parsed by [repolex](https://repolex.ai).

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
rlex download bmcfee/resampy
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 67263d6fc03028d24b69e775a77d12265c7295d9
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 67263d6fc03028d24b69e775a77d12265c7295d9
│           └── chunk-001.nq.gz
├── blob
│   ├── 0da07729d30bc5361285f496ae6f8f5a0ba701eb.nq.gz
│   ├── 1a90b9ed1ceb36491e9e99f476daf33e5fc42740.nq.gz
│   ├── 1fecdfda2311357cde48a4becd03b6407bed46ea.nq.gz
│   ├── 259d1549d2f1cd169d05b3bdc4a13a8619a000a8.nq.gz
│   ├── 34f38291354825ed65bf2dae4d738796192429d7.nq.gz
│   ├── 389a4aa8654cde4c0f0a63a8c0e7abb70b6979fe.nq.gz
│   ├── 4004e37820cfbcdc8eea909e0895416550861270.nq.gz
│   ├── 4ab4ca10575594a871bbbdf3771ed58c4e50207c.nq.gz
│   ├── 4b0ec62d2c0e5eac319bc440870354258db9e621.nq.gz
│   ├── 4bf51363615943a5e73983e011b22907d9f72d73.nq.gz
│   ├── 5055ed34a677db7bf9352d1a15718018d5001f46.nq.gz
│   ├── 506cef0fcdad86c7213d47abf55463a6fb41811b.nq.gz
│   ├── 55e3a7cf49e89effc91e635a012058f8a4261ca3.nq.gz
│   ├── 570eb7b5bfb25e86b070d89adc2ffcccfbf9e8f2.nq.gz
│   ├── 6b40b52bf5a8ba40f2a06c10b078d7dcf811a659.nq.gz
│   ├── 6e2e4516ea5891c2d0b1be9f7c484f6eedb6357c.nq.gz
│   ├── 7532a658cc57797192c19d21d0ecaf3318315aa0.nq.gz
│   ├── 7dce8dd98d9137429f378396dd1bcf715fcbcdde.nq.gz
│   ├── 8c3f1f277f599057e5c037c92d129fc108f4dd0d.nq.gz
│   ├── 9db7ce8bbf6ba180a7871d64509ba28855adec34.nq.gz
│   ├── a2af2f7089e3d5dd238b609446afb4669b864d31.nq.gz
│   ├── a5960feb3b61d9bc407c6d1048ea5f265daa6399.nq.gz
│   ├── af4c9af786be1592e7b9847ae42ba07f2ca372b3.nq.gz
│   ├── b58bf68ef813dfbf10114ed53517160203c21794.nq.gz
│   ├── b6e223dc0a9e15158e7936682069c6f2eec9c5de.nq.gz
│   ├── bc6a74e952f6c9963a8f6a746b8dfd780d512fe6.nq.gz
│   ├── c118ea9a444f0a43bf6734abbf8902f16a4d48bc.nq.gz
│   ├── c25861f664aa1966ebcc79e426cbb5ca3d9e90c2.nq.gz
│   ├── c9de4e8002c622013e19d66fcec288ac88189d17.nq.gz
│   ├── cf341f6cd5d5732eb5caa043a05de8ca973fb506.nq.gz
│   ├── d41b98e449cb54990988ec1b0cb99d0ddc152b4d.nq.gz
│   ├── d8d1fd9e3bd3ea79fd3699411cdbc5da8da88fc2.nq.gz
│   ├── e74ffbcec65885469a94ba6395c528e82893f7b9.nq.gz
│   ├── f3eec01ffbeff4783bdcb96ccf48d93b2187c02d.nq.gz
│   ├── f486f6d6aecb7d32bdb87539180dafa4328a6a57.nq.gz
│   └── ff52059365813aa7ca1a1564498b31f3b528844c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 67263d6fc03028d24b69e775a77d12265c7295d9.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 44 files
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

[bmcfee/resampy](https://github.com/bmcfee/resampy)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
