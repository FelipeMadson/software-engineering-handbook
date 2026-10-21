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
| **10** | [Ultra-Low Latency & Extreme Fault-Tolerance: From CPU to Distributed Clusters](ebooks/low-latency-fault-tolerant-systems/README.md) | C++20 Lock-Free Disruptor, LOB Matching, Elixir/OTP Actor Mesh | `1eb06fa7...` | Markdown & C++ / Elixir Code |

---

## 🎓 Formal Academic Research Papers (Dual Format: ABNT NBR 6022 & IEEEtran)

Peer-reviewed grade academic research articles with rigorous mathematical models, verified theorems, formal proofs, compilable LaTeX sources, standalone printable ABNT HTML, and comprehensive bibliographic data in both **ABNT (NBR 6022/6028/6023/10520/14724)** and **IEEE** standards:

| Title & Research Track | Formal Mathematical Specification & Theorems | Mathematical Model | Research Artifacts (IEEE & ABNT) |
| :--- | :--- | :--- | :---: |
| **Deterministic State Machine Replication: Formal Safety and Liveness Verification in Distributed Log Quorums Under Asymmetric Partitions**<br>*(Distributed Systems & Formal Methods)* | • **Theorem 1 (State Machine Safety):** Identical commit index $k$ on non-faulty replicas implies identical command evaluation $C_i(k) = C_j(k)$.<br>• **Theorem 2 (Log Matching Property):** Equal term & index guarantees identical log prefix. | $\mathbf{S}_i = (t_i, v_i, \mathcal{L}_i, c_i, a_i)$<br>Quorum: $\mathcal{Q} = \lfloor N/2 \rfloor + 1$ | **IEEE:** [📄 Paper](papers/deterministic-state-machine-replication-raft/PAPER.md) · [LaTeX](papers/deterministic-state-machine-replication-raft/paper.tex) · [BibTeX](papers/deterministic-state-machine-replication-raft/references.bib)<br>**ABNT:** [📄 Artigo ABNT](papers/deterministic-state-machine-replication-raft/ARTIGO_ABNT.md) · [abntex2](papers/deterministic-state-machine-replication-raft/artigo_abnt.tex) · [BibTeX](papers/deterministic-state-machine-replication-raft/referencias_abnt.bib) · [Audit](papers/deterministic-state-machine-replication-raft/CONFORMIDADE_ABNT.md) |
| **Sub-Millisecond Approximate Nearest Neighbor Search in WebAssembly: 128-Bit SIMD Quantization and Memory-Bounded Graph Traversal**<br>*(Algorithms & Hardware Acceleration)* | • **Quantization Error Bound:** Uniform scalar quantization cosine error strictly bounded by Cauchy-Schwarz inequality: $\|d_c(\mathbf{q}, \mathbf{x}) - d_c(\mathbf{q}, \tilde{\mathbf{x}})\| \le \frac{\sqrt{D}}{255}$.<br>• Hardware SIMD128 dot product vectorization. | $\mathbf{q} \cdot \mathbf{x} = \sum_{k=0}^{D-1} q_k \cdot x_k$<br>$\mathcal{O}(D/4)$ WASM cycles | **IEEE:** [📄 Paper](papers/simd-hnsw-vector-quantization-wasm/PAPER.md) · [LaTeX](papers/simd-hnsw-vector-quantization-wasm/paper.tex) · [BibTeX](papers/simd-hnsw-vector-quantization-wasm/references.bib)<br>**ABNT:** [📄 Artigo ABNT](papers/simd-hnsw-vector-quantization-wasm/ARTIGO_ABNT.md) · [abntex2](papers/simd-hnsw-vector-quantization-wasm/artigo_abnt.tex) · [BibTeX](papers/simd-hnsw-vector-quantization-wasm/referencias_abnt.bib) · [Audit](papers/simd-hnsw-vector-quantization-wasm/CONFORMIDADE_ABNT.md) |
| **Post-Quantum Hybrid Key Encapsulation Mechanisms in Zero-Trust Edge Mesh Networks: An Empirical IND-CCA2 Reduction**<br>*(Cryptography & Network Security)* | • **IND-CCA2 Security Reduction:** Hybrid encapsulation remains indistinguishable under adaptive chosen-ciphertext attack as long as either ML-KEM-768 or X25519 is unbroken.<br>• Dual entropy extraction via Leftover Hash Lemma. | $\mathbf{K} = \text{KDF}(\mathbf{K}_{\text{pqc}} \mathbin{\Vert} \mathbf{K}_{\text{classic}} \mathbin{\Vert} \mathbf{c}_1 \mathbin{\Vert} \mathbf{c}_2)$<br>$\mathbf{A}_{\text{Q}} \le \epsilon_{\text{KEM}} + \epsilon_{\text{ECDH}}$ | **IEEE:** [📄 Paper](papers/post-quantum-hybrid-key-exchange-mesh/PAPER.md) · [LaTeX](papers/post-quantum-hybrid-key-exchange-mesh/paper.tex) · [BibTeX](papers/post-quantum-hybrid-key-exchange-mesh/references.bib)<br>**ABNT:** [📄 Artigo ABNT](papers/post-quantum-hybrid-key-exchange-mesh/ARTIGO_ABNT.md) · [abntex2](papers/post-quantum-hybrid-key-exchange-mesh/artigo_abnt.tex) · [BibTeX](papers/post-quantum-hybrid-key-exchange-mesh/referencias_abnt.bib) · [Audit](papers/post-quantum-hybrid-key-exchange-mesh/CONFORMIDADE_ABNT.md) |
| **Zero-Overhead Linux Kernel Observability: Safe Kernel Probing and Lockless Ring Buffer Serialization with eBPF in Rust**<br>*(Operating Systems & Kernel Systems)* | • **Memory Isolation & Verifier Safety:** Verified static path analysis guarantees zero out-of-bounds access and prevents kernel panic.<br>• **Wait-Free Ring Buffer:** Contention-free multi-producer event staging. | $w_{\text{old}} = \text{atomic\_fetch\_add}(w, L)$<br>Bounded DAG verification | **IEEE:** [📄 Paper](papers/zero-overhead-linux-kernel-ebpf-observability/PAPER.md) · [LaTeX](papers/zero-overhead-linux-kernel-ebpf-observability/paper.tex) · [BibTeX](papers/zero-overhead-linux-kernel-ebpf-observability/references.bib)<br>**ABNT:** [📄 Artigo ABNT](papers/zero-overhead-linux-kernel-ebpf-observability/ARTIGO_ABNT.md) · [abntex2](papers/zero-overhead-linux-kernel-ebpf-observability/artigo_abnt.tex) · [BibTeX](papers/zero-overhead-linux-kernel-ebpf-observability/referencias_abnt.bib) · [Audit](papers/zero-overhead-linux-kernel-ebpf-observability/CONFORMIDADE_ABNT.md) |
| **Zero-Knowledge Succinct Non-Interactive Arguments of Knowledge (zk-SNARKs) in WebAssembly: Constant-Time Pairing Checks over BN254 Curves**<br>*(Applied Cryptography & Privacy)* | • **Soundness in Algebraic Group Model:** False proof acceptance bounded by $q/r$ ($r \approx 2^{254}$).<br>• **Constant-Time Execution:** Elimination of timing side channels in Miller loop iterations. | $e(-A, B) \cdot e(\alpha, \beta) \cdot e(\sum x_i IC_i, \gamma) \cdot e(C, \delta) = 1$<br>$\mathcal{O}(1)$ branchless | **IEEE:** [📄 Paper](papers/zk-snarks-constant-time-pairing-wasm-verifier/PAPER.md) · [LaTeX](papers/zk-snarks-constant-time-pairing-wasm-verifier/paper.tex) · [BibTeX](papers/zk-snarks-constant-time-pairing-wasm-verifier/references.bib)<br>**ABNT:** [📄 Artigo ABNT](papers/zk-snarks-constant-time-pairing-wasm-verifier/ARTIGO_ABNT.md) · [abntex2](papers/zk-snarks-constant-time-pairing-wasm-verifier/artigo_abnt.tex) · [BibTeX](papers/zk-snarks-constant-time-pairing-wasm-verifier/referencias_abnt.bib) · [Audit](papers/zk-snarks-constant-time-pairing-wasm-verifier/CONFORMIDADE_ABNT.md) |
| **High-Throughput Reactive Event Sourcing and Transactional Outbox: Provable Eventual Consistency in Microservice Mesh Topologies**<br>*(Distributed Databases & Stream Processing)* | • **Causal Convergence:** Deterministic projection convergence under monotonic sequencer keys.<br>• **No-Lost-Writes:** Transactional atomicity guarantees zero lost events across crashes. | $S_n = \text{foldl}(\text{apply}, S_0, \mathcal{E})$<br>$\Delta S \iff \text{OutboxEntry} \in \text{Tx}$ | **IEEE:** [📄 Paper](papers/high-throughput-event-sourcing-reactive-cqrs-outbox/PAPER.md) · [LaTeX](papers/high-throughput-event-sourcing-reactive-cqrs-outbox/paper.tex) · [BibTeX](papers/high-throughput-event-sourcing-reactive-cqrs-outbox/references.bib)<br>**ABNT:** [📄 Artigo ABNT](papers/high-throughput-event-sourcing-reactive-cqrs-outbox/ARTIGO_ABNT.md) · [abntex2](papers/high-throughput-event-sourcing-reactive-cqrs-outbox/artigo_abnt.tex) · [BibTeX](papers/high-throughput-event-sourcing-reactive-cqrs-outbox/referencias_abnt.bib) · [Audit](papers/high-throughput-event-sourcing-reactive-cqrs-outbox/CONFORMIDADE_ABNT.md) |

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
