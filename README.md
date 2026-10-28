# Repolex Knowledge Graph of mne-tools/mne-kit-gui

RDF knowledge graph data for [mne-tools/mne-kit-gui](https://github.com/mne-tools/mne-kit-gui), parsed by [repolex](https://repolex.ai).

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
rlex download mne-tools/mne-kit-gui
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 412f7939d1bafa917a498be404c57b046bd8e6dd
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 412f7939d1bafa917a498be404c57b046bd8e6dd
│           └── chunk-001.nq.gz
├── blob
│   ├── 00a7b00c94e08b86c765d47689b6523148c46eec.nq.gz
│   ├── 1166c59261cf361d664df088d585f3878c8dd0be.nq.gz
│   ├── 1965f967f99fa3e548c39670599df3977c73b139.nq.gz
│   ├── 1c4a23656d07d5bb4fc48eef8839b328f7a31020.nq.gz
│   ├── 2350e09ff75c2d73a0b4b0effccb20718574d3fb.nq.gz
│   ├── 2413a87d7b36e3fa18355912008ffbfdbff69515.nq.gz
│   ├── 33968c1088b72c8b70514cb41d1a721231486ad3.nq.gz
│   ├── 37a5d3f0a46cf34f4b231bb1fc42d1b66ab652b0.nq.gz
│   ├── 3a81ea31004b68b614c47f4376cdb28c0be9337f.nq.gz
│   ├── 408f379cd31b55b4717ea896e0c8eb5bf1f2496d.nq.gz
│   ├── 47ed5136f372ec2e52326b217a0a891e964dee59.nq.gz
│   ├── 4bd1026d5f8b2506a98d6b8c07d3ea1734e66f29.nq.gz
│   ├── 4e32e6981d363b2ad851efef4a01b60debc55907.nq.gz
│   ├── 52551f58399050a65c047a5a7ab69f1ca530814b.nq.gz
│   ├── 6329638bae140fc41af2f92b3ea1cbb15d371ff2.nq.gz
│   ├── 678ec384958fa70e739452fcb0826ad1fee4f5e8.nq.gz
│   ├── 79c68d7696c9b149c19da5d2d6f1c78ab9b346ea.nq.gz
│   ├── 7c5100942aae489ca04d07d2c69a4d8f6f8470fe.nq.gz
│   ├── 86fa4746cbce5df04a78ebd1d037a027bd33fd35.nq.gz
│   ├── 871e487eb87dc02cfcbc30e49fee8d9cd82c63c2.nq.gz
│   ├── 89577aaab645a259186ab24b48a155acd636615f.nq.gz
│   ├── 9e321750cb0b377b85fa29f6fd6279696d1cf070.nq.gz
│   ├── ac91423c416985d394fe9c63a3cbfcbb12e439ac.nq.gz
│   ├── aec9bca51b43b113a621cf939461100d0925dc14.nq.gz
│   ├── b792b08e5589ce6dffc0a6983e117045f0b082f9.nq.gz
│   ├── bc95b10dcd25a28508eddb5f0193a1ec344386ac.nq.gz
│   ├── d447d85d360aefdb55a5f8d63dcbb26c8301b2a8.nq.gz
│   ├── d6851d87113b9b63cb43dfa194111b3b012415d4.nq.gz
│   ├── dec2fc37e0205a1e9ba5b2ad80e0eeca11424150.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ef3aed3ac404cf943f63e9e0a7da642d4fcae699.nq.gz
│   ├── f43bbcf59eea45c72027003ea1d6359ee74af25c.nq.gz
│   ├── f54915d4c1cfe4fb79b8e0f80f390bb9bf02e5a1.nq.gz
│   ├── f5d4fd97aa457b3ec3f125985eb6a16fac97636d.nq.gz
│   └── f95d76e1055aef2be09326d5c8fc5da37ee6fbe0.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 412f7939d1bafa917a498be404c57b046bd8e6dd.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 43 files
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

[mne-tools/mne-kit-gui](https://github.com/mne-tools/mne-kit-gui)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
