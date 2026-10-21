# Repolex Knowledge Graph of astropy/astropy-APEs

RDF knowledge graph data for [astropy/astropy-APEs](https://github.com/astropy/astropy-APEs), parsed by [repolex](https://repolex.ai).

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
rlex download astropy/astropy-APEs
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 755aaa515ee779d836f8a1c1f6a15346dd89d183
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 755aaa515ee779d836f8a1c1f6a15346dd89d183
│           └── chunk-001.nq.gz
├── blob
│   ├── 13bd31d4a43b7b9a022ee42f2e0edfd4b908750e.nq.gz
│   ├── 171ebc943aceddeb736cc96efc16cfd6150bb0d3.nq.gz
│   ├── 2c9438150b66bd566ca495c3011c47e1e726ad68.nq.gz
│   ├── 2fee438091a86642e769e77bc9b2ba1edf5a2597.nq.gz
│   ├── 353183b5aeffb7a2447f4910fb08588e0b7b46ee.nq.gz
│   ├── 41a62826fb48f2cb60a5adbea57a4b2b4a2e0d60.nq.gz
│   ├── 4412f3b9635fbc77bbf97b5f2f382b95280a713d.nq.gz
│   ├── 4f4ef2a416890489723300724c654f84b6d822e6.nq.gz
│   ├── 6537c3490666183a1cb30b641854dedbabe58451.nq.gz
│   ├── 678312238414fc0058c075a8570ed0e533e18444.nq.gz
│   ├── 71726a0badf9f01bd4aeb1ce78fd61b8f06ed758.nq.gz
│   ├── 7b4e3e0290531c2c5acd7b8939266ff814bdad09.nq.gz
│   ├── 7d7e8c2723408867efeaadea9af63628a18bc3c4.nq.gz
│   ├── 84dbaaadaa4f718acfa7e4b09d4d58111065b5b7.nq.gz
│   ├── 983e270d4e9d2851a1f0bd4c582370ba8ac16055.nq.gz
│   ├── a493b41120070b9cae4d2ceabd929c1b7f0f2f5e.nq.gz
│   ├── ba9f402d5267657c17635ebfc625c8be76c6088b.nq.gz
│   ├── c4f38f2251b3391cc6992630316252a9eabd4ed1.nq.gz
│   ├── ce9bc20c6b9771c8d14afa0bdeda080c33c671e6.nq.gz
│   ├── d213b751a8fc5bb4a1c21345f0b702ad4f2f2c74.nq.gz
│   ├── e3c88115e2cb13e9485b43d4c5d1ed65232bfbfa.nq.gz
│   ├── e41a76c7ec9b9be7de768d4aea4c4578d59bb6fe.nq.gz
│   ├── efe306e82ecc7046db5e8ea9f857d3f2cf965475.nq.gz
│   ├── f880b99294a16317d7452e2cf3987afd37a83683.nq.gz
│   ├── f915fd1817f6c64b4165fbf65089cbee9b6eebfd.nq.gz
│   └── fc69b524c07f9cf7a10ead7ce2844954944c9d8f.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 755aaa515ee779d836f8a1c1f6a15346dd89d183.nq.gz
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

[astropy/astropy-APEs](https://github.com/astropy/astropy-APEs)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
