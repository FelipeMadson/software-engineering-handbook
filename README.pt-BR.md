# Manual de Engenharia de Software & Artigos de Arquitetura

[![Verificação de Integridade](https://github.com/FelipeMadson/software-engineering-handbook/actions/workflows/verify-integrity.yml/badge.svg)](https://github.com/FelipeMadson/software-engineering-handbook/actions)
[![Licença: MIT](https://img.shields.io/badge/Licen%C3%A7a-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Integridade: SHA-256 Criptográfico](https://img.shields.io/badge/Integridade-SHA--256-emerald.svg)](ebooks/manifest.json)
[![Bilingue: Inglês & Português](https://img.shields.io/badge/Idioma-EN%20%7C%20PT--BR-blue.svg)](README.md)

Repositório aprofundado de manuais de engenharia de software, whitepapers de arquitetura de sistemas distribuídos e guias de design de sistemas *local-first*, de autoria de **Felipe Madison** com suporte de inteligência artificial determinística local.

[English Version](README.md) · [Portfólio](https://felipemadson.github.io/portfolio/) · [Perfil no GitHub](https://github.com/FelipeMadson)

---

## Sumário dos Volumes & Registro Criptográfico

Cada livro técnico desta coleção possui um hash SHA-256 imutável e contagem estrita de palavras registradas em [`ebooks/manifest.json`](ebooks/manifest.json).

| Vol | Título | Área Central | SHA-256 Verificado | Formato |
|---|---|---|---|---|
| **01** | [Proteção e Idempotência em Filas Assíncronas Distribuídas](ebooks/idempotent-queue-guard/README.md) | Sistemas Distribuídos, Mensageria Resiliente | `01e72a55...` | Markdown & Specs |
| **02** | [Sistemas Colaborativos Local-First com CRDT](ebooks/crdt-offline-first/README.md) | Peer-to-Peer, Sync Offline, Convergência | `1297184a...` | Markdown & Matemática |
| **03** | [Isolamento Multi-Tenant com PostgreSQL Row-Level Security (RLS)](ebooks/multitenant-security-rls/README.md) | Segurança em Bancos de Dados, Nuvem | `1686ce88...` | Markdown & SQL |
| **04** | [Ambientes de Desenvolvimento Determinísticos e Sandboxes](ebooks/deterministic-dev-environments/README.md) | DevEx, Sandboxing, Reprodutibilidade | `56aa122d...` | Markdown & Specs |
| **05** | [Arquitetura de Segredos, Sandboxing e Isolamento em CI/CD](ebooks/arquitetura-de-segredos-e-isolamento-em-ci/README.md) | AppSec, Contêineres Efêmeros, Zero-Trust | `d720b005...` | Markdown & Segurança |
| **06** | [Engenharia de Armazenamento LSM-Tree com MemTable e WAL em Rust](ebooks/engenharia-de-armazenamento-lsm-tree-com-memtable-e-wal-em-rust/README.md) | Programação de Sistemas, Armazenamento, Concorrência | `0a302db6...` | Markdown & Código Rust |
| **07** | [Busca Vetorial de Baixa Latência com WebAssembly SIMD e Grafo HNSW em Rust](ebooks/rust-wasm-simd-vector-search/README.md) | IA de Borda, WASM SIMD, Indexação Vetorial | `2b992d38...` | Markdown & WASM |
| **08** | [Motores Colaborativos em Tempo Real com FastAPI, WebSockets e CRDTs Concorrentes em Python](ebooks/fastapi-realtime-collaborative-engine/README.md) | Tempo Real Distribuído, WebSockets, CRDTs Baseados em Estado | `91836c97...` | Markdown e Código Python |
| **09** | [Guia de Engenharia: Padrões de Consistência Eventual, Event Sourcing e Transactional Outbox de Alta Vazão](ebooks/event-sourcing-transactional-outbox/README.md) | Event Sourcing, CQRS, Transactional Outbox, Consistência Eventual | `a7ad8a1e...` | Markdown & TypeScript / C# |

---

## Topologia Arquitetural Unificada

```
┌────────────────────────────────────────────────────────────────────────┐
│                        CAMADA DE BORDA E CLIENTE                       │
│  ┌──────────────────────────────┐    ┌──────────────────────────────┐  │
│  │ Vol 02: CRDT Local-First Sync│    │ Vol 07: Rust WASM SIMD Vector│  │
│  │ Convergência e Vetores Lógicos    │ Grafo HNSW na Memória Edge   │  │
│  └──────────────┬───────────────┘    └──────────────┬───────────────┘  │
└─────────────────┼───────────────────────────────────┼──────────────────┘
                  ▼                                   ▼
┌────────────────────────────────────────────────────────────────────────┐
│                 MENSAGERIA E SISTEMAS DISTRIBUÍDOS                     │
│  ┌──────────────────────────────┐    ┌──────────────────────────────┐  │
│  │ Vol 01: Fila Idempotente     │    │ Vol 04: Sandbox Determinístico│  │
│  │ Deduplicação e Leases Atômicos    │ Runtimes Herméticos e Isolados│  │
│  └──────────────┬───────────────┘    └──────────────┬───────────────┘  │
└─────────────────┼───────────────────────────────────┼──────────────────┘
                  ▼                                   ▼
┌────────────────────────────────────────────────────────────────────────┐
│                   MOTORES DE ARMAZENAMENTO E SEGURANÇA                 │
│  ┌──────────────────────────────┐    ┌──────────────────────────────┐  │
│  │ Vol 03: PostgreSQL RLS       │    │ Vol 06: LSM-Tree em Rust     │  │
│  │ Separação de Contexto Tenant │    │ MemTable Concorrente e WAL   │  │
│  ├──────────────────────────────┤    ├──────────────────────────────┤  │
│  │ Vol 05: CI/CD Criptográfico  │    │ Encapsulamento Zero-Trust    │  │
│  └──────────────────────────────┘    └──────────────────────────────┘  │
└────────────────────────────────────────────────────────────────────────┘
```

---

## Princípios de Engenharia Demonstrados

### 1. Filas Idempotentes
- Deduplicação em duas fases com transações atômicas no banco local.
- Quarentena de mensagens envenenadas (poison pills) sem perda de contexto operacional.
- Preservação de garantias "once-and-only-once" sob partições severas de rede.

### 2. CRDTs Local-First
- Convergência de estado sem depender de coordenação centralizada síncrona.
- Relógios de Lamport e vetores causais eliminando conflitos de concorrência.
- Replicação delta que reduz o overhead de tráfego de rede em até 90%.

### 3. PostgreSQL RLS Multi-Tenant
- Isolamento criptográfico e de contexto em nível de hardware e banco.
- Invariantes de sessão obrigatórias via `SET LOCAL app.current_tenant_id`.
- Prevenção total contra falhas humanas de esquecimento de filtros por tenant.

### 4. Sandboxes Determinísticos
- Ambientes de compilação perfeitamente reproduzíveis com hashes imutáveis.
- Pinagem estrita de dependências sem wildcards ou updates arbitrários.
- Eliminação do problema crônico "na minha máquina funcionou".

### 5. Isolamento Criptográfico em CI/CD
- Ambientes efêmeros de teste com renúncia irrevogável de privilégios (`ALL`).
- Zero exposição de chaves ou credenciais sensíveis em logs ou stdout/stderr.

### 6. Motor LSM-Tree em Rust
- Log de escrita prévia (Write-Ahead Log - WAL) com garantia `O_SYNC`.
- MemTable concorrente com SkipList para operações sem contenção de mutex global.
- Compactação Leveled SSTable eliminando a amplificação de leitura.

### 7. Busca Vetorial com WebAssembly SIMD
- Aceleração vetorial de 128 bits calculando produto escalar em sub-milissegundos.
- Grafo navegável HNSW executando inteiramente na memória do navegador.
- Privacidade absoluta: vetores de embeddings nunca deixam o dispositivo do cliente.

---

## Verificação e Integridade

Para validar a integridade dos volumes localmente:

```bash
node -e "
  const fs = require('fs'), crypto = require('crypto');
  const manifest = JSON.parse(fs.readFileSync('ebooks/manifest.json', 'utf8'));
  for (const b of manifest) {
    const file = 'ebooks/' + b.slug + '/README.md';
    if (!fs.existsSync(file)) { console.log(b.slug, 'AUSENTE'); continue; }
    const content = fs.readFileSync(file, 'utf8');
    const hash = crypto.createHash('sha256').update(content).digest('hex');
    console.log(b.slug, hash === b.verifiedSha256 ? 'VÁLIDO' : 'DIVERGENTE');
  }
"
```

---

## Autor & Créditos

- **Autor**: Felipe Madison ([@FelipeMadson](https://github.com/FelipeMadson))
- **Metodologia**: Engenharia Local-First, CI Determinístico, Pesquisa Baseada em Evidências
- **Licença**: MIT License
