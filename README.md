# Repolex Knowledge Graph of dask/dask-benchmarks

RDF knowledge graph data for [dask/dask-benchmarks](https://github.com/dask/dask-benchmarks), parsed by [repolex](https://repolex.ai).

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
rlex download dask/dask-benchmarks
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 9956e67abc24c7fb1ea832a5500b411356b03b84
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 9956e67abc24c7fb1ea832a5500b411356b03b84
│           └── chunk-001.nq.gz
├── blob
│   ├── 095464a9ebbe5e7be117c048512e95a264cf8b93.nq.gz
│   ├── 0f4e7974a87a2736bc01c3983ff8489dec9256e4.nq.gz
│   ├── 10a9368bdd2e5aadfd3e3f3c16af2156a45ca3f2.nq.gz
│   ├── 142a08a7934f57841523467f368841c339cc1890.nq.gz
│   ├── 17a74aee32c94d2e78e1f86a614244cf09ed73da.nq.gz
│   ├── 287e7eb8e2a3d8b0252b80e7d156bf7ea52dad8c.nq.gz
│   ├── 46e174e5e2ce9a360ed5a88b91441c871aefc76a.nq.gz
│   ├── 5928c6d1c83b95be9e6da142f0ae680c74e0f40e.nq.gz
│   ├── 5f549136c6e92a8e99b0ff6f8a17512027a86fdb.nq.gz
│   ├── 5fbc1f2199337a06158247400f064e8a7a1bf9bf.nq.gz
│   ├── 70e80b22762f38b58133868dc69828bbd97c79c8.nq.gz
│   ├── 70e8720a0e77e7b5fafb5a6bfc49d27c1eb19b6d.nq.gz
│   ├── 80bb24313dbe6000b7764ec6d8955c7e2aea6fe9.nq.gz
│   ├── 82e8821447e54adb01ce7d205223eb08d6fd1aee.nq.gz
│   ├── 85092fd0866c8894891edd70aa3f2c71c1bd9f4c.nq.gz
│   ├── 97cc02f05b7b7d0844feff633fea8751263d12f4.nq.gz
│   ├── a7f2446ee73e9f6318043ca249e8ae3e7cec23eb.nq.gz
│   ├── ab4175a59fe6a4d47de60f899e7442bb1fde9585.nq.gz
│   ├── b3a3a357d71200c572b4c834084431e7f60cba6e.nq.gz
│   ├── cc07dd54f671a5af86464b6f030520ff75a7fe15.nq.gz
│   ├── d1c2252fd58d2e382863b9d2fd12f086f21efb42.nq.gz
│   ├── dd7b68362109f56c04de7372ac815b91776002e1.nq.gz
│   ├── de5c698126779fbf8dcfb5f7e2b5d161c3eb0362.nq.gz
│   ├── e5c8ee5d3b608a6018aa338648927b2dbbdccc2d.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── f438804db665ebdb8c1d81779825d4643486a72b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 9956e67abc24c7fb1ea832a5500b411356b03b84.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 34 files
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

[dask/dask-benchmarks](https://github.com/dask/dask-benchmarks)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
