# OncoSil — Análises Processadas

Este diretório armazena todas as análises realizadas, organizadas por status de verificação.

## Estrutura

| Pasta | Descrição |
|-------|-----------|
| `verificadas/` | Análises com cross-checking completo, prontas para integração |
| `pendentes/` | Análises em andamento ou aguardando validação profissional |
| `historico/` | Versões anteriores de análises (versionamento) |

## Padrão de Nomenclatura

```
YYYY-MM-DD_tipo_descricao.md
```

Exemplos:
- `2026-02-20_auditoria_phd_v3.md`
- `2026-02-20_verificacao_botbal_aacrio.md`
- `2026-03-01_analise_laudo_kowalski.md`

## Níveis de Confiança

Cada análise deve indicar seu nível de confiança:

| Nível | Significado |
|-------|-------------|
| **Verificado** | Cross-checked contra documentos-fonte, múltiplas referências |
| **Alta confiança** | Baseado em fontes primárias, mas sem cross-check completo |
| **Moderada** | Baseado em fontes secundárias ou dados parciais |
| **Pendente validação** | Requer revisão por profissional de saúde |
| **Relato familiar** | Informação não confirmada em documentação médica |
