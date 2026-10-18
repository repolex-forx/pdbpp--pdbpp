# Repolex Knowledge Graph of pdbpp/pdbpp

RDF knowledge graph data for [pdbpp/pdbpp](https://github.com/pdbpp/pdbpp), parsed by [repolex](https://repolex.ai).

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
rlex download pdbpp/pdbpp
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── e1c2e347cc55a6dd89e058e56a1366ada68884bc
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── e1c2e347cc55a6dd89e058e56a1366ada68884bc
│           └── chunk-001.nq.gz
├── blob
│   ├── 0053566d0c55af25c052ea489ba44189c81dbc5f.nq.gz
│   ├── 0749e26fa4181a1786f4d12a67b7f0f641a2f852.nq.gz
│   ├── 0ce9d6da6181856a74464aa4bfb84d13f01db485.nq.gz
│   ├── 13fb90d6a50c2a2265a5fac1ddc99cb951d700ae.nq.gz
│   ├── 15ad1c6f138196c8c7f941f8a07fb00cd75e6c12.nq.gz
│   ├── 270d10c37f46cc812a27d2c31fec94dfa31d0c75.nq.gz
│   ├── 46979bc150d5f919185427d610eb1f8d4cdef926.nq.gz
│   ├── 5a503685c12b470cfc71aee178b0f01210aa5d16.nq.gz
│   ├── 71db556b41d78795730c0ae35e24633a96ef44cd.nq.gz
│   ├── 8d28b523312fb54f32b4e6ddeb264c172040b19f.nq.gz
│   ├── 9868e2f589561a5f1777a2ca988d99191457266a.nq.gz
│   ├── 9e8d1190d401899a5549170b34b35ac16912bbff.nq.gz
│   ├── a02b1bac1c01e6d867d056a452fe337103765f73.nq.gz
│   ├── a89b7eaf1422038a69d5c40799d0feb92f8c3faf.nq.gz
│   ├── b710fc4b4d4c5f655b18178888c958d01b4593a9.nq.gz
│   ├── c05e348a6280ce5a5eabd0c7d236dc60eda38ded.nq.gz
│   ├── c506f7c0d10ab3464d8c693c2a1d59046932a839.nq.gz
│   ├── c5e7ea8ad0481281aa12b1df70149c0a727b2c84.nq.gz
│   ├── c64aa2201cd95f9cb91ee2e2096af80245558881.nq.gz
│   ├── cfda0aec25d55753cafe41c146bc8b1f4a4dbdda.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e9b1091567cca5b0a930be84dfe5af886e3873cd.nq.gz
│   └── eb64b6cfeb6f98e5bd9d9a94a156abd3a1142c22.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── e1c2e347cc55a6dd89e058e56a1366ada68884bc.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 31 files
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

[pdbpp/pdbpp](https://github.com/pdbpp/pdbpp)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
