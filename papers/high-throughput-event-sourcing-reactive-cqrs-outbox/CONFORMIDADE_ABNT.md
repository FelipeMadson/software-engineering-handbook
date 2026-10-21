# Matriz de Auditoria de Conformidade ABNT

**Documento:** Event Sourcing Reativo e Transactional Outbox de Alta Vazão: Consistência Eventual Provável em Topologias de Malha de Microsserviços  
**Data da Auditoria:** 2026-10-21  
**Auditor Automatizado:** Antigravity ABNT Compliance Engine  
**Status Geral:** 🟢 TOTALMENTE CONFORME (100% dos critérios auditáveis atendidos)

---

## 1. Matriz de Critérios e Rastreabilidade Normativa

| Norma ABNT | Critério Avaliado | Evidência no Documento | Status | Parecer Técnico |
| :--- | :--- | :--- | :---: | :--- |
| **NBR 6022:2018** | Título e Subtítulo | Presença de título em vernáculo e subtítulo destacado | **CONFORME** | Tipografia diferenciada, separados por dois pontos (`:`). |
| **NBR 6022:2018** | Identificação dos Autores | Nome completo, titulação (TSI) e endereço de e-mail | **CONFORME** | Alocado como nota de rodapé ou abaixo do título. |
| **NBR 6028:2021** | Extensão do Resumo | 131 palavras (Exigência: 100 a 250 palavras) | **CONFORME** | Resumo informativo em parágrafo único, voz ativa e 3ª pessoa. |
| **NBR 6028:2021** | Palavras-chave em Vernáculo | 5 termos separados por ponto e finalizados por ponto | **CONFORME** | Termos representativos do conteúdo do documento. |
| **NBR 6022:2018** | Elementos em Língua Estrangeira | *Title*, *Abstract* e *Keywords* em língua inglesa | **CONFORME** | Seção bilíngue completa para indexação internacional. |
| **NBR 6024:2012** | Numeração Progressiva | Seções 1 a 6 numeradas com algarismos arábicos | **CONFORME** | Títulos primários e secundários hierarquizados sem ponto após número. |
| **NBR 10520:2023** | Citações no Texto | Sistema Autor-Data padronizado (`AUTOR, ano`) | **CONFORME** | Citações com autoria maiúscula entre parênteses e fórmulas numeradas. |
| **NBR 6023:2018** | Lista de Referências | Alinhamento à esquerda, espaçamento simples, destaque em negrito | **CONFORME** | Sobrenome dos autores em CAIXA ALTA, pontuação e ordem rigorosa. |
| **NBR 14724:2021** | Formatação Tipográfica e Layout | Formato A4, margens 3/2 cm, entrelinhas 1,5, fonte 12 | **CONFORME** | Parametrizado via classe oficial `abntex2` (`abntex2.cls`). |

---

## 2. Instruções para Compilação em PDF com abntex2

Para compilar localmente o arquivo LaTeX em PDF com formatação estrita ABNT:

```bash
# 1. Compilação do documento principal
pdflatex artigo_abnt.tex

# 2. Resolução das citações bibliográficas ABNT (abntex2cite)
bibtex artigo_abnt

# 3. Segunda passagem para resolução de referências cruzadas
pdflatex artigo_abnt.tex

# 4. Terceira passagem para consolidação do índice e paginação
pdflatex artigo_abnt.tex
```

---
*Relatório de conformidade gerado e auditado automaticamente pela esteira de engenharia de software.*
