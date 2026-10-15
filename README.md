# Repolex Knowledge Graph of click-contrib/click-repl

RDF knowledge graph data for [click-contrib/click-repl](https://github.com/click-contrib/click-repl), parsed by [repolex](https://repolex.ai).

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
rlex download click-contrib/click-repl
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── cab5f48382dfff7b7449b3a182f5f9e34ae53050
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── cab5f48382dfff7b7449b3a182f5f9e34ae53050
│           └── chunk-001.nq.gz
├── blob
│   ├── 00f6ec62f91199bb9f267e87ea689f5bcd8902bd.nq.gz
│   ├── 04e89ce047c906e06b309b04f215bd119c7ce548.nq.gz
│   ├── 06d3ae6bc8b1b5d35c5f1cf85461f56de81db8c9.nq.gz
│   ├── 0a10f106d19edaa2463bac1d55874d122cba2d90.nq.gz
│   ├── 1046ccdd34bd409ab73c89f7b17626d094a6a873.nq.gz
│   ├── 1617d20a580b25554e40eb3aeeab28720b425f8c.nq.gz
│   ├── 1846ea5d54a050b117effe623ef27e0ed1c7beb5.nq.gz
│   ├── 1aba38f67a2211cf5b09466d7b411206cb7223bf.nq.gz
│   ├── 25793bee32ad094ba231ccb3ef2c78abc57dba7f.nq.gz
│   ├── 2a178e31ee456347c8f1d683102f274bcd8dd992.nq.gz
│   ├── 30829e788dc5499429c3b503386d34894f06c2f7.nq.gz
│   ├── 37f852f9ece4b4f6bc47729ccd280d22cdde150f.nq.gz
│   ├── 3c1e87567ed2054dc5f66375f562dc5f8b87e8d2.nq.gz
│   ├── 3e6883830fca32c8e2b50d4c9630733f3f256564.nq.gz
│   ├── 42ecb61a58e0f0248b2039eb022f40c8268cbc25.nq.gz
│   ├── 431f5a675ba8305b3be79cf4a42bb0da8c90f449.nq.gz
│   ├── 4e8141832bf4634fe3e12704b243849d99af83be.nq.gz
│   ├── 5b5d05d2628e6a21ab0474592f8117f9a5834170.nq.gz
│   ├── 606882bc83d4df134adb55549f9a90ba6a992d4c.nq.gz
│   ├── 607e4510712e282e72f44cb84ec1137b7f28e176.nq.gz
│   ├── 6238668e771f4af1b0302bedca8c79b27415e1c2.nq.gz
│   ├── 6eafbddbf2fcac506fa0157c5971f1fc0df6a975.nq.gz
│   ├── 6f07e8eb48b6a2065eebdd6dba02751735a32cee.nq.gz
│   ├── 72b8a9d2f30678a5afb5ec229efaf70280f6e513.nq.gz
│   ├── 75d12ac8209cf9d1490b4e5fef276d499d6abd4a.nq.gz
│   ├── 78c7dd0975f786b3dc7339ee792294986c151466.nq.gz
│   ├── 79d30fac32fe065ee3f89e6b52fdfb151b9e29fc.nq.gz
│   ├── 7e410902f70dc5c1e6bf4eae275a641f9f6bd7c6.nq.gz
│   ├── 83cda50b138f4ea2cfe0bc0bafdcf1cf2d6c3f32.nq.gz
│   ├── 8fb48f969e55e56ae21cce246ec79f902c962db8.nq.gz
│   ├── 9389593409c3464b73ad82f89705322373501538.nq.gz
│   ├── 995622c0ffc230ec672e6a840fdce637fe366705.nq.gz
│   ├── aac06cadc4aa5ebc2f13664904fea667d8e70390.nq.gz
│   ├── b791222dc847f986e7471999f02cd76b49150878.nq.gz
│   ├── cc4586aecd5c20185d9a888ab07d275e4ec194b0.nq.gz
│   ├── d846e77249f5a805cf3e64ca7a5f0b58c01cfbfd.nq.gz
│   ├── da609fff79aecb61bf45a188751ff4fcc483ebab.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ebe71329822eb8a5c116ad159ae2f9c833b5a9bf.nq.gz
│   └── f4fb238d7b67d3dd6ec5c66a5d4771929b7a5ea3.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── cab5f48382dfff7b7449b3a182f5f9e34ae53050.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 48 files
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

[click-contrib/click-repl](https://github.com/click-contrib/click-repl)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
