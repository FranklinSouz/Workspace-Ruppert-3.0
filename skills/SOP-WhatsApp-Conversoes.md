# SOP — Rastreamento de Conversões via WhatsApp Business (Etiquetas)
**Versão:** 1.0  
**Data:** 2026-03-25  
**Aplicável a:** Clientes CAVE com campanhas Click-to-WhatsApp ou Mensagens  
**Responsável pela implantação:** Gestor de tráfego CAVE  

---

## 🎯 Objetivo

Configurar o rastreamento de conversões de vendas realizadas via WhatsApp, conectando etiquetas do WhatsApp Business ao Meta Ads como eventos de conversão (omni_purchase / Purchase).

---

## ✅ Pré-requisitos (validar antes de começar)

| Item | Como verificar | Bloqueante? |
|------|---------------|-------------|
| Conta WhatsApp Business App ativa (não número pessoal) | Abrir o app — deve mostrar "Business" | ✅ Sim |
| Número WPP **não** está em outro Business Manager | BM → Contas → WhatsApp | ✅ Sim |
| Acesso de Admin ao Business Manager do cliente | BM → Pessoas → verificar role | ✅ Sim |
| Cliente tem atendimento via WhatsApp estruturado | Perguntar ao cliente | ✅ Sim |
| Equipe de atendimento treinável | Alinhamento com o cliente | ⚠️ Crítico |

> ⚠️ **Se o cliente usa número pessoal no WhatsApp:** precisa migrar para WhatsApp Business App antes de seguir. Não há atalho.

---

## 📋 Passo a Passo de Implantação

### FASE 1 — Conectar WhatsApp ao Business Manager

1. Acessar **business.facebook.com** com conta Admin
2. Menu lateral → **Configurações do Negócio** (ícone de engrenagem)
3. Aba **Contas** → **Contas do WhatsApp**
4. Clicar em **Adicionar** → **Conectar um número do WhatsApp Business**
5. Seguir o fluxo de verificação (código SMS ou ligação)
6. Confirmar que o número aparece listado com status **Ativo**

> 📌 *Se o número já estiver conectado a outro BM, o cliente precisa desconectar primeiro — pode gerar atrito. Alinhar antes.*

---

### FASE 2 — Criar etiqueta de venda no WhatsApp Business App

No celular do cliente (WhatsApp Business App):

1. Ir em **Configurações** → **Etiquetas** → **Nova etiqueta**
2. Criar a etiqueta com nome padronizado: `✅ Venda Fechada`
   - Alternativas aceitáveis: `Pedido Confirmado`, `Compra Realizada`
   - ⚠️ **Não usar variações** — toda a equipe deve usar exatamente o mesmo nome
3. Salvar

> 💡 *Recomendação: criar também etiquetas de funil (ex: `🔥 Lead Quente`, `💬 Em Negociação`) para ter visibilidade das etapas antes da venda.*

---

### FASE 3 — Mapear etiqueta como evento de conversão no BM

1. Acessar **business.facebook.com**
2. Menu lateral → **Gerenciador de Eventos** (ou buscar "Events Manager")
3. Selecionar a fonte de dados do WhatsApp (deve aparecer após vincular na Fase 1)
4. Ir em **Configurações** → **Conversões do WhatsApp**
5. Clicar em **Adicionar evento**
6. Mapear:
   - **Etiqueta:** `✅ Venda Fechada` (exatamente como criado)
   - **Evento do Meta:** `Purchase`
7. Salvar e confirmar

> 📌 *Se não aparecer a opção de Conversões do WhatsApp, aguardar até 24h após vincular o número. Se persistir, verificar se o número está corretamente conectado ao BM.*

---

### FASE 4 — Configurar campanha com objetivo correto

1. Criar nova campanha no Ads Manager
2. **Objetivo:** Mensagens **ou** Leads (com destino WhatsApp)
   - Objetivo "Vendas" com evento de conversão WhatsApp também funciona em contas com histórico
3. No conjunto de anúncios:
   - **Destino da mensagem:** WhatsApp
   - **Evento de otimização:** Selecionar `Purchase` (omni_purchase) se disponível
4. No anúncio: configurar mensagem de abertura automática (icebreaker)
5. Publicar

---

### FASE 5 — Treinamento da equipe de atendimento

Este é o passo mais crítico. Sem adesão da equipe, o rastreamento falha.

**Briefing obrigatório para atendentes:**

> "Toda vez que fechar uma venda pelo WhatsApp, você PRECISA aplicar a etiqueta ✅ Venda Fechada na conversa. Isso é o que faz nossa campanha de anúncios saber que funcionou. Se esquecer, a venda não aparece no sistema e não conseguimos provar resultado."

**Checklist de treinamento:**
- [ ] Mostrar onde ficam as etiquetas no WPP Business App
- [ ] Demonstrar como aplicar em uma conversa
- [ ] Simular um caso de venda e pedir para o atendente etiquetar
- [ ] Definir responsável por auditar etiquetas semanalmente

---

## 🔍 Validação — Como confirmar que está funcionando

Após configurar, aguardar 24-48h com atendimentos ativos e verificar:

1. **Gerenciador de Eventos** → Source WhatsApp → checar se eventos `Purchase` estão chegando
2. **Ads Manager** → Colunas → adicionar `Compras (omni_purchase)` e `Valor de conversão`
3. Cruzar com vendas reais reportadas pelo cliente para calibrar

> ⚠️ Lembrete de expectativa para o cliente: "O número pode ser ligeiramente menor que as vendas reais — depende 100% da disciplina de etiquetar. É o sinal mais próximo disponível sem CRM integrado."

---

## ⚠️ Limitações — Comunicar ao cliente no onboarding

| Limitação | Impacto | Como mitigar |
|-----------|---------|--------------|
| Depende de etiquetar manualmente | Venda não etiquetada = invisível para o Meta | Treinar equipe + auditoria semanal |
| Janela de atribuição: 7 dias (padrão) | Vendas após 7 dias do clique não são atribuídas | Informar o cliente; pode ajustar para 1 dia se preferir |
| Não é rastreamento em tempo real | Delay de até 24h para aparecer no Ads Manager | Alinhar expectativa |
| Não substitui CRM | Sem dados de LTV, histórico do cliente etc. | Apresentar solução CRM como upgrade |

---

## 🚀 Upgrade — Versão com CAPI + CRM (para clientes com volume)

Quando o cliente tem volume > ~50 vendas/mês via WhatsApp, vale propor:

1. **WhatsApp Business API** (via provedor: Zenvia, Twilio, Take Blip, etc.)
2. **CRM integrado** (HubSpot, RD Station, Kommo)
3. **Disparo de evento via CAPI** no momento exato da venda marcada no CRM

Resultado: rastreamento preciso, independente de memória humana, com deduplicação e matching avançado.

> 💡 *Esse modelo pode ser um produto CAVE: "Implantação de rastreamento avançado WhatsApp". Precificável separado da gestão de tráfego.*

---

## 📁 Documentos de Suporte

- [ ] Template de briefing para cliente (expectativas de rastreamento)
- [ ] Roteiro de treinamento de atendentes (versão impressa/PDF)
- [ ] Print-guide passo a passo para configurar etiquetas no WPP Business App

---

*SOP elaborado por Ruppert para uso interno da CAVE Assessoria.*

