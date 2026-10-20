# Software Engineering Handbook & Architecture Whitepapers

[![Integrity Verification](https://github.com/FelipeMadson/software-engineering-handbook/actions/workflows/verify-integrity.yml/badge.svg)](https://github.com/FelipeMadson/software-engineering-handbook/actions)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Verification: Cryptographic SHA-256](https://img.shields.io/badge/Integrity-SHA--256-emerald.svg)](ebooks/manifest.json)
[![Bilingual: English & Portuguese](https://img.shields.io/badge/Language-EN%20%7C%20PT--BR-blue.svg)](README.pt-BR.md)

An exhaustive, peer-grade repository of software engineering handbooks, distributed systems architecture whitepapers, and local-first systems design manuals authored by **Felipe Madison** with local deterministic AI assistance.

[Versão em Português](README.pt-BR.md) · [Portfolio](https://felipemadson.github.io/portfolio/) · [GitHub Profile](https://github.com/FelipeMadson)

---

## Volume Overview & Cryptographic Ledger

Every book in this collection is backed by an immutable cryptographic SHA-256 checksum and exact word count recorded in [`ebooks/manifest.json`](ebooks/manifest.json).

| Vol | Title | Focus Area | Verified SHA-256 | Format |
|---|---|---|---|---|
| **01** | [Guarding Distributed Asynchronous Queues with Idempotency](ebooks/idempotent-queue-guard/README.md) | Distributed Systems, Resilient Messaging | `01e72a55...` | Markdown & Specs |
| **02** | [Local-First Collaborative Systems with Conflict-Free Replicated Data Types (CRDT)](ebooks/crdt-offline-first/README.md) | Peer-to-Peer, Offline Sync, State Merging | `1297184a...` | Markdown & Math |
| **03** | [Enterprise Multi-Tenant Data Isolation with PostgreSQL Row-Level Security (RLS)](ebooks/multitenant-security-rls/README.md) | Database Security, Cloud Tenancy | `1686ce88...` | Markdown & SQL |
| **04** | [Deterministic Development Environments and Reproducible Sandboxes](ebooks/deterministic-dev-environments/README.md) | DevEx, Sandbox Isolation, Supply-Chain | `56aa122d...` | Markdown & Specs |
| **05** | [Arquitetura de Segredos, Sandboxing e Isolamento Criptográfico em CI/CD](ebooks/arquitetura-de-segredos-e-isolamento-em-ci/README.md) | AppSec, Ephemeral Containers, Zero-Trust | `d720b005...` | Markdown & Security |
| **06** | [Engenharia de Armazenamento LSM-Tree com MemTable e WAL em Rust](ebooks/engenharia-de-armazenamento-lsm-tree-com-memtable-e-wal-em-rust/README.md) | Systems Programming, Storage Engines, Concurrency | `0a302db6...` | Markdown & Rust Code |
| **07** | [Busca Vetorial de Baixa Latência com WebAssembly SIMD e Grafo HNSW em Rust](ebooks/rust-wasm-simd-vector-search/README.md) | Edge AI, WASM SIMD, Vector Indexing | `2b992d38...` | Markdown & WASM |
| **08** | [Motores Colaborativos em Tempo Real com FastAPI, WebSockets e CRDTs Concorrentes em Python](ebooks/fastapi-realtime-collaborative-engine/README.md) | Distributed Realtime, WebSockets, State-based CRDTs | `91836c97...` | Markdown & Python Code |
| **09** | [High-Throughput Event Sourcing, Reactive CQRS, and Transactional Outbox Patterns](ebooks/event-sourcing-transactional-outbox/README.md) | Event Sourcing, CQRS, Transactional Outbox, Eventual Consistency | `a7ad8a1e...` | Markdown & TypeScript / C# |

---

## Architectural Topology

```
┌────────────────────────────────────────────────────────────────────────┐
│                        CLIENT & EDGE LAYER                             │
│  ┌──────────────────────────────┐    ┌──────────────────────────────┐  │
│  │ Vol 02: CRDT Local-First Sync│    │ Vol 07: Rust WASM SIMD Vector│  │
│  │ State Merging & Vector Clocks│    │ HNSW Graph on Edge Memory    │  │
│  └──────────────┬───────────────┘    └──────────────┬───────────────┘  │
└─────────────────┼───────────────────────────────────┼──────────────────┘
                  ▼                                   ▼
┌────────────────────────────────────────────────────────────────────────┐
│                   DISTRIBUTED SYSTEMS & MESSAGING                      │
│  ┌──────────────────────────────┐    ┌──────────────────────────────┐  │
│  │ Vol 01: Idempotent Queue     │    │ Vol 04: Deterministic Sandbox│  │
│  │ Deduplication & Lease Engine │    │ Reproducible Container Runtimes│
│  └──────────────┬───────────────┘    └──────────────┬───────────────┘  │
└─────────────────┼───────────────────────────────────┼──────────────────┘
                  ▼                                   ▼
┌────────────────────────────────────────────────────────────────────────┐
│                     STORAGE & SECURITY ENGINES                         │
│  ┌──────────────────────────────┐    ┌──────────────────────────────┐  │
│  │ Vol 03: PostgreSQL RLS       │    │ Vol 06: Rust LSM-Tree Storage│  │
│  │ Tenant Context Separation    │    │ Concurrent MemTable & WAL    │  │
│  ├──────────────────────────────┤    ├──────────────────────────────┤  │
│  │ Vol 05: Cryptographic CI/CD  │    │ Zero-Trust Key Encapsulation │  │
│  └──────────────────────────────┘    └──────────────────────────────┘  │
└────────────────────────────────────────────────────────────────────────┘
```

---

## Summary of Core Architectural Principles

### 1. Guarding Distributed Queues
- **Two-phase state deduplication** with atomicity guarantees.
- Poison message quarantine without data loss.
- High-throughput idempotency under network partitions ($CAP$ Theorem constraints).

### 2. Local-First Collaborative CRDTs
- State-based ($CvRDT$) and Operation-based ($CmRDT$) state convergence.
- Lamport timestamps and Vector clocks for causal ordering without central lock contention.
- Delta-state replication reducing bandwidth by up to 90% in peer meshes.

### 3. Multi-Tenant PostgreSQL RLS
- Enforcing hardware-isolated data security within a unified relational cluster.
- Session-scoped `SET LOCAL app.current_tenant_id` invariants.
- Defense-in-depth against SQL injection bypassing multi-tenancy.

### 4. Deterministic Sandboxes
- Cryptographically reproducible execution environments.
- Lockfile pinning, networkless compilation, and container hermeticism.
- Elimination of *"works on my machine"* syndrome across developer teams.

### 5. Cryptographic CI/CD Isolation
- Ephemeral worker sandboxes with `ALL` capabilities dropped.
- Kernel-level privilege isolation (`no-new-privileges`).
- Zero-token exposure architecture in build logs and execution environments.

### 6. LSM-Tree Storage Engine in Rust
- Append-only Write-Ahead Log (WAL) with `O_SYNC` durability guarantees.
- Lock-free / fine-grained read-write MemTable with `SkipList` ordering.
- Leveled SSTable compaction eliminating read amplification.

### 7. WebAssembly SIMD Vector Search in Rust
- 128-bit SIMD micro-parallelized cosine similarity and dot product calculations.
- Hierarchical Navigable Small World (HNSW) graph traversal directly in edge browser memory.
- Zero-cloud leak: private semantic embeddings never leave the user's client device.

---

## Verification & Integrity

To verify the integrity of all volumes locally:

```bash
node -e "
  const fs = require('fs'), crypto = require('crypto');
  const manifest = JSON.parse(fs.readFileSync('ebooks/manifest.json', 'utf8'));
  for (const b of manifest) {
    const file = 'ebooks/' + b.slug + '/README.md';
    if (!fs.existsSync(file)) { console.log(b.slug, 'MISSING'); continue; }
    const content = fs.readFileSync(file, 'utf8');
    const hash = crypto.createHash('sha256').update(content).digest('hex');
    console.log(b.slug, hash === b.verifiedSha256 ? 'VALID' : 'MISMATCH');
  }
"
```

---

## Author & Credits

- **Author**: Felipe Madison ([@FelipeMadson](https://github.com/FelipeMadson))
- **Methodology**: Local-First Engineering, Deterministic CI, Evidence-Based Research
- **License**: MIT License
