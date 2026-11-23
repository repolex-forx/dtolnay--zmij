# Repolex Knowledge Graph of dtolnay/zmij

RDF knowledge graph data for [dtolnay/zmij](https://github.com/dtolnay/zmij), parsed by [repolex](https://repolex.ai).

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
rlex download dtolnay/zmij
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 7b7cc48b58028e8af7be87e94c0c1c8936f1a57c
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 7b7cc48b58028e8af7be87e94c0c1c8936f1a57c.nq.gz
│   └── repolex
│       └── 7b7cc48b58028e8af7be87e94c0c1c8936f1a57c
│           └── chunk-001.nq.gz
├── blob
│   ├── 0436f5e13f6f874d1e6bfa257ddb655c3ba4d6fb.nq.gz
│   ├── 09326ce76df99f327cad509bd3a431b411a31ca9.nq.gz
│   ├── 22d89fef587aa40073f219bf2d5d1b2335256bcb.nq.gz
│   ├── 31aa79387f27e730e33d871925e152e35e428031.nq.gz
│   ├── 4bc31dc394135fc1aa166b499d5f346bc0abfc2d.nq.gz
│   ├── 4fffb2f89cbd8f2169ce9914bd16bd43785bb368.nq.gz
│   ├── 5138d50ee4d78d4e6e3ff604104f915b9b0e6e86.nq.gz
│   ├── 5490c80d0a99101f08f26426df72eb91ab6c4ebd.nq.gz
│   ├── 7ed01e03409be6728d5f619b3a4b1b04401db9e7.nq.gz
│   ├── 85b82ec2189569e6ae6b291fc2cc3a25114a4e8a.nq.gz
│   ├── 98fde16b480a3f16265e6ce4561af3830745f208.nq.gz
│   ├── a129a8cbc175f94056c21780917c4d16863c2ed5.nq.gz
│   ├── a735993b190edd799acc3642d5bcc2d9a2d6655e.nq.gz
│   ├── b07ec6e853ab01245846d31b9feb6c92b1cdd1d1.nq.gz
│   ├── b354dc00e46b3a0374a0d55aa34bdc3e2d17018d.nq.gz
│   ├── d479941aa6e655d593b8816e8667bfa2f7e25dd3.nq.gz
│   ├── e370817e5992eec1f56bd751715185803f9135de.nq.gz
│   ├── f70074a22f9ed352e9fbc3f5e2a2f264eefcd340.nq.gz
│   └── fec958208c176d8b7e37a44aecb661db3ed3d4dc.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 7b7cc48b58028e8af7be87e94c0c1c8936f1a57c.nq.gz
├── filetree
│   └── 7b7cc48b58028e8af7be87e94c0c1c8936f1a57c.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 29 files
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

[dtolnay/zmij](https://github.com/dtolnay/zmij)

---
*Parsed on 2026-11-23 by [repolex](https://repolex.ai)*
