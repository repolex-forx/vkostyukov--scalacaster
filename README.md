# Repolex Knowledge Graph of vkostyukov/scalacaster

RDF knowledge graph data for [vkostyukov/scalacaster](https://github.com/vkostyukov/scalacaster), parsed by [repolex](https://repolex.ai).

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
rlex download vkostyukov/scalacaster
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 807f0a954cf7715e3d0e976fe47cf29a4edb1955
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 807f0a954cf7715e3d0e976fe47cf29a4edb1955
│           └── chunk-001.nq.gz
├── blob
│   ├── 07af641b5a00bd633c5b50612beff51704feb334.nq.gz
│   ├── 09ed61d32000379bd6cba897a010054ed3a80ee4.nq.gz
│   ├── 0f308fbb250a7a057b0843a40045f801a08ff633.nq.gz
│   ├── 4605f0819b61a817b0d77ee683f00925c8869afa.nq.gz
│   ├── 4bed89328a360e0ece8cd0a96b737dcb5b61b57e.nq.gz
│   ├── 509129976d23a6b1a63dec27d09c0f922a1bc616.nq.gz
│   ├── 7b918ffa4a5d4512552b74739ab44d3933334425.nq.gz
│   ├── 7c0eef73277e6783fac02e971b4668401c12bb1a.nq.gz
│   ├── 820f2ca59f65cc3e3df88ef3e1e0934599154dbe.nq.gz
│   ├── 8216bcc2b2d8ca98a489ca67cd9469902e4678a4.nq.gz
│   ├── 88672451bd6e04e35bc512cbf8c85e5b1a529d47.nq.gz
│   ├── 8bda18884e2bf890e49e2a4f029af92fbab1fb08.nq.gz
│   ├── 8d3943759fc23470f7004b51310b6415c61dd03c.nq.gz
│   ├── 9ff67233359c26158b6c2f1c47c5c9095634471f.nq.gz
│   ├── a0312f25b956916e49a6ef618d8d8bc6e91ed33d.nq.gz
│   ├── a09760b6178feeda89051e2b05d07048290ad2b6.nq.gz
│   ├── a9090d6c7ea5983909a379e21d6a524e827be678.nq.gz
│   ├── adc8bf473d17cd3b66080fda2f258454fc90d395.nq.gz
│   ├── afb4ff8701fb3dd59e05cfeb041f2250ef34b2ef.nq.gz
│   ├── c3f5f93420797014b1818b3b9fe381b97dccc619.nq.gz
│   ├── c669898fcf95a1df86201eac825d0c78299d8683.nq.gz
│   ├── d29050c9563675d85d5f83913b4ce4977d1f654f.nq.gz
│   ├── e6b19473b116849058c469f1fff2d21693dde0f9.nq.gz
│   ├── eec955e11ded7bd67fbd9b0b2d245e55aae91ad8.nq.gz
│   └── ef498e823c223fb1272dc58268426825c801e40e.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 807f0a954cf7715e3d0e976fe47cf29a4edb1955.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 33 files
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

[vkostyukov/scalacaster](https://github.com/vkostyukov/scalacaster)

---
*Parsed on 2026-11-10 by [repolex](https://repolex.ai)*
