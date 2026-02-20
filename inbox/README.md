# OncoSil — Inbox de Documentos

Este diretório é o ponto de entrada para novos documentos, laudos, áudios e mensagens que precisam ser processados e integrados à plataforma OncoSil.

## Estrutura

| Pasta | Descrição | Formatos Aceitos |
|-------|-----------|-----------------|
| `laudos/` | Laudos médicos, exames, resultados de biópsia | PDF, JPG, PNG |
| `audios/` | Gravações de consultas, áudios de WhatsApp | MP3, WAV, OGG, M4A |
| `mensagens/` | Mensagens de texto, anotações, dúvidas | TXT, MD |
| `prontuarios/` | Prontuários, receitas, prescrições | PDF, DOCX |

## Fluxo de Processamento

1. **Recebimento** — Documento é colocado na pasta correspondente
2. **Triagem** — Classificação por tipo e urgência
3. **Análise** — Extração de dados clínicos com cross-checking
4. **Verificação** — Validação cruzada contra documentos-fonte existentes
5. **Integração** — Dados verificados são incorporados ao HTML principal
6. **Arquivo** — Documento movido para `analises/verificadas/` ou `analises/historico/`

## Como Enviar Documentos

### Opção 1: Via GitHub (recomendado)
Faça upload diretamente na pasta correspondente via GitHub web interface.

### Opção 2: Via Manus
Envie os documentos como anexo em uma nova tarefa do projeto OncoSil.

### Opção 3: Via WhatsApp (futuro)
Integração planejada com WhatsApp Business API para recebimento automatizado.

## Notas de Segurança

- Todos os documentos contêm dados sensíveis de saúde (LGPD)
- O repositório deve permanecer **privado** quando contiver dados reais
- Nunca compartilhe links públicos para documentos médicos
- Dados anonimizados podem ser usados para pesquisa com consentimento
