# Repolex Knowledge Graph of AbstractUmbra/audioop

RDF knowledge graph data for [AbstractUmbra/audioop](https://github.com/AbstractUmbra/audioop), parsed by [repolex](https://repolex.ai).

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
rlex download AbstractUmbra/audioop
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 14e6553f7aa49dab825313a06863fc2d134e97da
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 14e6553f7aa49dab825313a06863fc2d134e97da
│           └── chunk-001.nq.gz
├── blob
│   ├── 0386ed138aa005ece445d57364c5ab03999cf88c.nq.gz
│   ├── 2a82275986921b83901264f4ca7f5aaa06644bf5.nq.gz
│   ├── 3953191f74122435b5d86667af20d01708407e4f.nq.gz
│   ├── 3dd4922692c90d84fda4583fa04735c1b3cbc9a5.nq.gz
│   ├── 50c3e249e18738706f16396ec99d89d0c597e93c.nq.gz
│   ├── 54d098519e86346a4ae8f9209bf005d949741710.nq.gz
│   ├── 95491092723b395c0ff8a0372fe28ea81498dcfb.nq.gz
│   ├── 996eaf533e64911c055c9fd6a6ef1166a4a4045e.nq.gz
│   ├── a68a09f6ae03f83fdbdf278744b94e08700ca048.nq.gz
│   ├── a8c6575e4299838791348b8bf8808a8a15f38be4.nq.gz
│   ├── c6678b5e5f2e1ebdd58aec25ddcd3829452474d4.nq.gz
│   ├── df439c1ec64cb791cdfc387ca8ab7b111753d541.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ef6472e32d263de24d9a09ab6f522d8f6194341e.nq.gz
│   └── f26bcf4d2de6eb136e31006ca3ab447d5e488adf.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 14e6553f7aa49dab825313a06863fc2d134e97da.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 23 files
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

[AbstractUmbra/audioop](https://github.com/AbstractUmbra/audioop)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
