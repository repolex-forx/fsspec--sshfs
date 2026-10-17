# Repolex Knowledge Graph of fsspec/sshfs

RDF knowledge graph data for [fsspec/sshfs](https://github.com/fsspec/sshfs), parsed by [repolex](https://repolex.ai).

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
rlex download fsspec/sshfs
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 3d2d681b4abbaa412ee961b9953d57ee277a019a
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 3d2d681b4abbaa412ee961b9953d57ee277a019a
│           └── chunk-001.nq.gz
├── blob
│   ├── 0a3921c4448a658c15ed893976bf7e11ccfc92b4.nq.gz
│   ├── 0f4cfdc380de3d29fa590f55afd71339141659c8.nq.gz
│   ├── 141baf7192c8e04db6e2a23727b65c34bb65378b.nq.gz
│   ├── 14713074eed1879f933ecf228397200209378317.nq.gz
│   ├── 1510a29cc24bb5a8c00792fbe3ff1db7d4711d10.nq.gz
│   ├── 1c8bfb8aa3b38e33830d4293da10a76beb4780e7.nq.gz
│   ├── 24336306860a2059a2d0968acfd53cea16a9fcaf.nq.gz
│   ├── 29456ecb685367e60680d99f2aae944a48b88141.nq.gz
│   ├── 2f3c45db4c4f6d639bbc74f3deef2c62808c8945.nq.gz
│   ├── 430c76ec5f335002127235a98720981ab200fcb3.nq.gz
│   ├── 4a9ee6bec2d7fae285d2d4333342535a141e8006.nq.gz
│   ├── 5ad658b14e7063598bfc315d67cb72216f5e66c3.nq.gz
│   ├── 63f4c9e7fdf2831d067b781572290c6c33807f78.nq.gz
│   ├── 6f2e206dcea6108b7f600138bc23e576063027a3.nq.gz
│   ├── 7d51ef4ed58a683b311ec4298b8c142780cb897f.nq.gz
│   ├── 8e7af337c88df83730f67f500b24a331493b6a96.nq.gz
│   ├── 9c42bf7b5a2e358e6850331a1432f2b38f4b8c6e.nq.gz
│   ├── cd5eba396f268aefc4b5ce2affea11b9175c6318.nq.gz
│   ├── ceb88ca26a871b2383032274a83d3f226ea258b7.nq.gz
│   ├── eab6315f906d2002987a3f8b1f5ddc6f1cdec0fc.nq.gz
│   ├── f42abb30c59bc4d2fe56523dd8aff3104ac43a6f.nq.gz
│   ├── f4f8b18a42606d0ada39bbda1fc7a37dce8a3f6c.nq.gz
│   ├── f8f594067ff9fd7697d09719746542eb8c692c09.nq.gz
│   └── fb2b02d20b09cb02c55c3087feefcc1dab4d0af0.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 3d2d681b4abbaa412ee961b9953d57ee277a019a.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 32 files
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

[fsspec/sshfs](https://github.com/fsspec/sshfs)

---
*Parsed on 2026-10-17 by [repolex](https://repolex.ai)*
