# Auditoria PhD — OncoSil HTML v3.2
## Cross-checking contra todos os documentos-fonte

### CORREÇÕES JÁ APLICADAS NO HTML ATUAL (CONFIRMADAS)

| # | Item | Status | Linha |
|---|------|--------|-------|
| 1 | NCT05608044 — "Ativo, não recrutando" | OK | 1425, 1894 |
| 2 | NCT06634875 → NCT04896697 para Vilastobart | OK | 1905 |
| 3 | BOT/BAL DCR: 69% (não 70%) | OK | 1413, 1417 |
| 4 | AAC França — programa nacional (não exclusivo Gustave Roussy) | OK | 1425, 2082 |
| 5 | CRISPR-TILs — nota MSI-H adicionada | OK | 1614 |
| 6 | Vilastobart — "sem metástase hepática" | OK | 1734 |
| 7 | Muzastotug — "em combinação com pembrolizumab" | VERIFICAR | — |
| 8 | Metástase laríngea — ~15-20 casos | OK | 1153, 1370 |
| 9 | NCT07227636 — recrutando | OK | 1884 |
| 10 | NCT05141721 — ativo | OK | 1898 |
| 11 | NCT01174121 — recrutando, custo coberto | OK | 1912, 2004, 2072 |

### CORREÇÕES PENDENTES IDENTIFICADAS

| # | Item | Problema | Ação |
|---|------|----------|------|
| A | Ref [4] PMC link | PMC9909257 é Aljariri, NÃO Pant. Pant é PMC12768924 | Corrigir link |
| B | Ref [2] Koutsouveli | Autor é "Pikros" no HTML, mas doc-fonte diz "Misiakos" | Verificar e corrigir |
| C | BOT/BAL dados AACR-IO fev/2026 | HTML não tem dados mais recentes (341 pts, mOS 17.2m geral, 38% 2y OS geral) | ADICIONAR |
| D | BATTMAN Phase 3 | Não mencionado no HTML — trial registracional 834 pts | ADICIONAR |
| E | STELLAR-303 NDA ao FDA | Zanzalintinib NDA submetido fev/2026 — marco histórico | ADICIONAR |
| F | Brasil acesso nomeado BOT/BAL | Documento diz "Brasil já tem acesso via programa nomeado" | ADICIONAR |
| G | Lancet Editorial | "The dawn of immunotherapy in MSS CRC" — não citado | ADICIONAR ref |
| H | JAMA Jan 2026 | CCR principal causa morte <50 anos nos EUA | ADICIONAR contexto |
| I | Cadonilimab NCT | HTML usa NCT05747716, doc-fonte diz NCT05839470 | VERIFICAR |
| J | Ivonescimab dados | HTML diz ORR 82%, doc-fonte diz 81.8% | Corrigir para 81.8% |
| K | Muzastotug Fast Track | Verificar se diz "em combinação com pembrolizumab" | VERIFICAR |

### DADOS NOVOS DO BOT/BAL AACR-IO (19/02/2026) PARA INTEGRAR

- Dados gerais (341 pts, cutoff 13/12/2025): ORR 17%, CBR 26%, mOS 17.2m, 2y OS 38%
- Biomarcadores: inflamação sistêmica negativa, atividade imune tumoral positiva
- BOT/BAL funciona mesmo com baixa infiltração imune (≥34 células/mm²)
- Biomarcadores integrados (C-index 0.73)
- imAEs nas primeiras 12 semanas: mOS 22.4m vs 13.7m
- ~1,200 pacientes tratados total
- BATTMAN Phase 3: 834 pts planejados, sites ativados
- NEST-1 neoadjuvante: 12 pts, resposta patológica maior
- Parceria Zydus: $141M
- Brasil: acesso via programa nomeado

### STELLAR-303 (NOVO PARA INTEGRAR)

- Zanzalintinib + Atezolizumab vs Regorafenib — Fase 3 CONCLUÍDA
- mOS: 10.9m vs 9.4m
- NDA submetido ao FDA (fev/2026)
- PRIMEIRO regime IO com benefício em fase 3 para CCR MSS refratário
