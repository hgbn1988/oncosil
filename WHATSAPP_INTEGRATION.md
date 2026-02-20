# OncoSil — Integração WhatsApp e Fluxos de Comunicação

## Visão Geral

Este documento descreve as opções viáveis para integrar o OncoSil com WhatsApp, permitindo que família, paciente e profissionais enviem documentos, mensagens e recebam atualizações de forma prática e segura.

## Opções de Integração

### Opção 1: Fluxo Manual via Manus (Imediato — Recomendado para Agora)

O fluxo mais simples e imediato, sem necessidade de infraestrutura adicional.

**Como funciona:**
1. Família/paciente recebe um laudo, áudio de consulta ou tem uma dúvida
2. Envia o documento/mensagem para o Hugo via WhatsApp normalmente
3. Hugo abre uma nova tarefa no projeto OncoSil no Manus
4. Anexa o documento e descreve o que precisa (análise, verificação, integração)
5. O agente processa, analisa com rigor PhD, cross-checks e atualiza o HTML
6. Hugo recebe o resultado e compartilha com a família/equipe médica

**Vantagens:** Zero custo, zero infraestrutura, funciona hoje, máxima qualidade de análise.
**Limitações:** Requer intermediação manual do Hugo.

### Opção 2: Grupo WhatsApp + Manus como Hub Central

**Estrutura proposta:**
- **Grupo "OncoSil — Família"** — Hugo, familiares, paciente
- **Grupo "OncoSil — Equipe Médica"** — Hugo, médicos envolvidos (se concordarem)
- **Hub Central** — Hugo consolida informações e processa via Manus

**Fluxo:**
1. Qualquer membro envia documento/dúvida no grupo
2. Hugo coleta e abre tarefa no Manus com o contexto
3. Resultado é compartilhado no grupo apropriado
4. Decisões são registradas e versionadas no repositório

### Opção 3: WhatsApp Business API + Automação (Futuro — Requer Desenvolvimento)

Integração automatizada usando a API oficial do WhatsApp Business.

**Componentes necessários:**
- Conta WhatsApp Business API (via Meta Business Suite)
- Servidor backend (Node.js/Python) para receber webhooks
- Integração com OpenAI API para processamento inicial
- Pipeline de análise com cross-checking automatizado
- Dashboard web para revisão humana antes de responder

**Provedores recomendados para a API:**
| Provedor | Custo Mensal | Mensagens/mês | Observação |
|----------|-------------|---------------|------------|
| Twilio | ~$15 + $0.005/msg | Ilimitado | Mais robusto, documentação excelente |
| MessageBird | ~$10 + $0.004/msg | Ilimitado | Bom custo-benefício |
| WATI | R$249/mês | 1.000 incluídas | Interface em português, suporte BR |
| Baileys (open-source) | Grátis | Ilimitado | Não oficial, risco de ban |

**Fluxo automatizado:**
```
WhatsApp → Webhook → Classificação IA → Análise → Revisão Humana → Resposta
```

**Nota de segurança:** Dados médicos via WhatsApp exigem cuidado com LGPD. A API oficial do WhatsApp Business oferece criptografia end-to-end, mas o processamento no servidor intermediário precisa ser seguro.

### Opção 4: Telegram Bot (Alternativa Técnica Superior)

O Telegram oferece uma API de bots muito mais flexível que o WhatsApp, sem custos.

**Vantagens sobre WhatsApp:**
- API gratuita e sem restrições
- Suporte nativo a arquivos grandes (até 2GB)
- Bots podem processar documentos automaticamente
- Grupos com até 200.000 membros
- Canais para atualizações unidirecionais
- Formatação Markdown nativa

**Desvantagem:** Nem todos usam Telegram no Brasil.

## Recomendação Estratégica

| Fase | Opção | Quando |
|------|-------|--------|
| **Agora** | Opção 1 (Manual via Manus) | Imediato |
| **Curto prazo** | Opção 2 (Grupos WhatsApp) | Esta semana |
| **Médio prazo** | Opção 3 (WhatsApp Business API) | 2-4 semanas |
| **Paralelo** | Opção 4 (Telegram Bot) | 1 semana |

## Fluxo de Trabalho Recomendado (Imediato)

```
┌─────────────────────────────────────────────────────┐
│                    FAMÍLIA / PACIENTE                │
│  (WhatsApp, e-mail, presencial)                     │
└──────────────────────┬──────────────────────────────┘
                       │ documentos, dúvidas, áudios
                       ▼
┌─────────────────────────────────────────────────────┐
│                    HUGO (Hub Central)                │
│  Recebe, organiza, prioriza                         │
└──────────────────────┬──────────────────────────────┘
                       │ tarefa no projeto OncoSil
                       ▼
┌─────────────────────────────────────────────────────┐
│              MANUS (Agente Ultra-PhD)                │
│  Analisa, cross-checks, pesquisa, atualiza HTML     │
└──────────────────────┬──────────────────────────────┘
                       │ resultado verificado
                       ▼
┌─────────────────────────────────────────────────────┐
│              REPOSITÓRIO ONCOSIL                     │
│  inbox/ → analises/ → index.html → GitHub Pages     │
└──────────────────────┬──────────────────────────────┘
                       │ site atualizado + relatório
                       ▼
┌─────────────────────────────────────────────────────┐
│         FAMÍLIA / EQUIPE MÉDICA / PACIENTE          │
│  Acessa via link, recebe resumo via WhatsApp        │
└─────────────────────────────────────────────────────┘
```

## Segurança e LGPD

- Dados médicos são dados sensíveis (Art. 11, LGPD)
- Repositório GitHub deve ser **privado** quando contiver dados reais
- O site público (GitHub Pages) não deve conter dados que identifiquem a paciente sem consentimento
- Áudios de consulta requerem consentimento do médico para gravação
- Recomenda-se termo de consentimento para compartilhamento de dados no grupo
