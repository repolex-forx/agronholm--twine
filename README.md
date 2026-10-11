# Repolex Knowledge Graph of agronholm/twine

RDF knowledge graph data for [agronholm/twine](https://github.com/agronholm/twine), parsed by [repolex](https://repolex.ai).

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
rlex download agronholm/twine
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── f74eae5506300387572c65c9dbfe240d927788c2
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── f74eae5506300387572c65c9dbfe240d927788c2
│           └── chunk-001.nq.gz
├── blob
│   ├── 0dc337cc3c93b26f91bb225b657005da8b9b56c4.nq.gz
│   ├── 12fa3d18573d728cd90520429dfced140c73e3ce.nq.gz
│   ├── 133706e558f2faed8e707225f9f70b78b8c597ea.nq.gz
│   ├── 18fb10f15a68e35f9572c19da05e5d91c639531d.nq.gz
│   ├── 3048666aede7d7de24cdbe006294f7915bcda698.nq.gz
│   ├── 413a4507c0600f156062d7c0b472ef1caf6c826d.nq.gz
│   ├── 53a6dc274e50ac8c8ab8f7ae6d11791baa79a487.nq.gz
│   ├── 5783a9d6de230d932fc07ff609b04072659e1a3d.nq.gz
│   ├── 58e0733ef97afe3501dc38c0a5b7416da83cf7a9.nq.gz
│   ├── 59a6ebbb932124bf470be58f8e4de915c0256f57.nq.gz
│   ├── 5d87025e88747fe1bdbd67554478a27d516cad6f.nq.gz
│   ├── 68f568c4f10561401a9fe5d11af8e4e093a507c3.nq.gz
│   ├── 6951070acb9f68c542b5eb8499633531a9a4f3b5.nq.gz
│   ├── 69d184778ccc1948e4c562ce3a6809e6fa00caa0.nq.gz
│   ├── 69de737adb23280f64c5fe8770746fd9a4fc81a8.nq.gz
│   ├── 7318c9929e4142a43833ae89d98d540154ec098b.nq.gz
│   ├── 7d87d2d9793173674de0cf601e7a1da7300c6458.nq.gz
│   ├── 824c76a71fb167c24f21260e7ac091479154fbbb.nq.gz
│   ├── 8705fe840ca2cec1a12b392a70040a276f6949b0.nq.gz
│   ├── 8acc0cf051043ba11becb4cd6a56c1e726956fa9.nq.gz
│   ├── 8d28394907d6fcd94036ed42705013d6e90ddd9c.nq.gz
│   ├── 8d70a51d6ede75eaab58dc34426ce9d362e19cf9.nq.gz
│   ├── 91e18a62b67551a4d427e2eaee0d33dcab94e141.nq.gz
│   ├── 9eed3aaee3226aeead56d39a8ac04685fa1f7feb.nq.gz
│   ├── af870cd4593ec95fc29a1d17d344cd5166900e11.nq.gz
│   ├── b02f1d189502a1bdf877a1c961cef9109770f939.nq.gz
│   ├── b38f326855026a0b9ffca4df9ae8e4a6bd71b71c.nq.gz
│   ├── c39b2d00e63c17a287403f18d0bac2e1787975c7.nq.gz
│   ├── c4847ab6ac8a53988ccc3e82d030f28d08f76f78.nq.gz
│   ├── cf6155dddaa2fb19b71a68a8414a5c2b2a602607.nq.gz
│   ├── d08918dbe519a95ea8a621e0c65207c1c371bf36.nq.gz
│   ├── d28eec1edf48768e0cc882d1817445e9300d4352.nq.gz
│   ├── de8ddf40aa03c5a48a88f0fe87421973dc1f68eb.nq.gz
│   ├── e7c603790819925433cc824bcd9d95229b474e1d.nq.gz
│   ├── ecf2e63a7c64a77fa1b9d630c80420185a5c6a41.nq.gz
│   ├── f37935e2ced75b54a21a57aff89cf02f43a57da3.nq.gz
│   ├── f5405e73bc7eeb64c3b89a0bc0d5b18606e5d56a.nq.gz
│   ├── f6b6bfd133de5c8d162acb6f54b91b613f762c77.nq.gz
│   ├── f77f748c19810b2e919afa2b178f58fed5b26c52.nq.gz
│   └── f80a1b557e221be957dc572c757a769f5e7f92a2.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── f74eae5506300387572c65c9dbfe240d927788c2.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 46 files
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

[agronholm/twine](https://github.com/agronholm/twine)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
