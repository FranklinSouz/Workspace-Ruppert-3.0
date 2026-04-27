---
name: analise-de-msg-compra
description: >
  Skill para análise de campanhas Meta Ads com foco em Mensagens (WhatsApp) e Compra Direta.
  Use quando o usuário pedir análise de campanhas Meta, gerenciador de anúncios, CPA,
  custo por compra, custo por mensagem, leads de WhatsApp, campanhas de mensagens,
  campanhas de compra, diagnóstico de tráfego pago, otimização, leitura de CSV exportado
  do Meta Ads, ou recomendações de escalar, manter, pausar e testar campanhas.
---

# Meta Ads — Skill de Análise de Campanhas

## Visão Geral

Esta skill orienta a análise de campanhas de Meta Ads para agências de marketing digital, com foco em diagnóstico preciso e recomendações de ação. Os dados podem chegar via:
- **Acesso direto ao Gerenciador de Anúncios**
- **CSV exportado** do Meta Ads Manager

O output esperado é sempre: **diagnóstico + recomendações de ação**, calibrado pelo tipo e janela de análise.

---

## 1. Contexto de Cliente (obrigatório antes de qualquer análise)

Antes de analisar, confirme ou solicite as seguintes informações do cliente:

```text
- Tipo de campanha predominante: [ ] Mensagens (WhatsApp) [ ] Compra Direta [ ] Ambas
- Ticket médio do produto/serviço (R$): ___
- Meta de CPA aceitável (R$): ___ (se definida no onboarding)
- Volume mínimo de leads/dia esperado: ___ (para campanhas de mensagem)
- Fase atual: [ ] Teste [ ] Estabilizada [ ] Escala
- Nível de prioridade do cliente: [ ] Normal [ ] Alta Prioridade / Atrito
```

Se esses dados não estiverem disponíveis no contexto, pergunte ao usuário antes de prosseguir.

---

## 2. Tipos de Campanha

### 2A. Campanha de Mensagens (MSG) → Leads via WhatsApp
Objetivo no Meta: **Mensagens**
O time comercial recebe os leads no WhatsApp. Compras são registradas via **etiquetas do WhatsApp** e aparecem no gerenciador como eventos de conversão.

**Dinâmica dupla:** esta campanha é cobrada tanto por volume de leads quanto por vendas geradas. A análise deve considerar as **duas dimensões**.

### 2B. Campanha de Compra Direta
Objetivo no Meta: **Vendas / Conversões**
Compras rastreadas via Pixel ou API de Conversões. Funil direto: anúncio → produto → compra.

---

## 3. Hierarquia de Métricas

### Métricas Primárias (decisão principal)
- **Compras** (`purchases` / Compras)
- **Custo por Compra (CPA)** (`cost_per_purchase`)
- **ROAS** (`purchase_roas`) como suporte

### Métricas Secundárias (suporte à decisão)

**Campanhas MSG**
- Mensagens iniciadas
- Custo por mensagem
- Leads qualificados
- CTR (link)
- CPM
- Frequência
- Alcance / Impressões

**Campanhas de Compra**
- CTR (link)
- CPM
- Frequência
- Alcance / Impressões

### Regra de Ouro
- A métrica primária responde: **estamos gerando resultado financeiro?**
- A métrica secundária responde: **temos volume e eficiência de processo para chegar lá?**

---

## 4. Critério de Avaliação do CPA

O CPA nunca deve ser avaliado em valor absoluto — sempre **relativo ao ticket do produto**.

```text
Índice CPA = CPA Real ÷ Ticket Médio

Índice < 0.10    → Excelente
Índice 0.10–0.20 → Bom
Índice 0.20–0.35 → Aceitável
Índice 0.35–0.50 → Atenção
Índice > 0.50    → Crítico
```

Exemplos:
- Produto R$100, CPA R$120 → Índice 1.2 → inviável
- Produto R$10.000, CPA R$500 → Índice 0.05 → excelente
- Produto R$500, CPA R$150 → Índice 0.30 → aceitável

> Sempre confirmar margem do produto antes de classificar uma campanha como inviável.

---

## 5. Tipos de Análise e Protocolo

### Análise Diária
Use para operação, atrito, checagem de funcionamento ou alertas.

Foco:
- Conta rodando?
- Orçamento consumindo?
- Queda ou pico brusco em CPA, CPM ou mensagens?
- Algo quebrou (pixel, evento, criativo)?

Saída esperada:
- Resumo de status
- Alertas
- Ação imediata se necessário

**Não tomar decisões definitivas com base em 1 dia isolado.**

### Análise de 3 Dias
Use em **fase de teste** ou logo após otimizações.

Foco:
- Tendência inicial da campanha
- Direção do CPA
- Volume de mensagens/leads
- Resposta à otimização implantada

Saída esperada:
- Tendência observada
- Ajuste pontual recomendado
- Próximo passo

**Não é janela suficiente para decisões definitivas de escalar ou pausar sem contexto forte.**

### Análise Semanal (7 dias)
É a janela principal de decisão.

Foco:
- Comparação com os 7 dias anteriores
- Compras e CPA
- Volume de mensagens e custo por mensagem
- O que puxa resultado
- O que drena orçamento sem retorno

Decisões possíveis:
- ✅ Escalar
- ⏸️ Pausar
- 🔄 Manter sob teste

### Análise de 15 Dias
Use para validar tendência e reduzir ilusão de período curto.

Foco:
- Consistência das decisões semanais
- Sazonalidade ou distorção pontual
- Custo médio mais confiável

### Análise Mensal
Use para fechamento e report ao cliente.

Foco:
- Compras totais
- Investimento
- CPA médio
- Faturamento atribuído / ROAS
- Top campanhas, testes, aprendizados e plano seguinte

---

## 6. Matriz de Decisão Semanal

```text
Primária (Compras/CPA) | Secundária (Leads/MSG) | Decisão
───────────────────────┼─────────────────────────┼────────────────────────────
✅ CPA aceitável        | ✅ Volume adequado      | ESCALAR
✅ CPA aceitável        | ⚠️ Volume baixo         | MANTER + investigar entrega
⚠️ CPA alto (limite)   | ✅ Volume adequado      | MANTER SOB TESTE (3 dias)
⚠️ CPA alto (limite)   | ⚠️ Volume baixo         | OTIMIZAR criativos/público
🔴 CPA inviável         | ✅ Volume alto          | PAUSAR conjunto, testar novo
🔴 CPA inviável         | ⚠️ Volume baixo         | PAUSAR e replanejar estratégia
✅ CPA aceitável        | 🔴 Volume crítico (0-1) | ATENÇÃO: alinhar com comercial
```

> Em campanhas de mensagens, se há muito lead e pouca compra, alinhar com o comercial antes de culpar a campanha.

---

## 7. Estrutura do Report Mensal

```markdown
# Relatório de Performance — [Nome do Cliente] — [Mês/Ano]

## Resumo Executivo
- Total de compras no período
- CPA médio
- Investimento total
- Faturamento atribuído (se disponível)
- ROAS médio

## Performance por Campanha
- Campanha | Investimento | Compras | CPA | Mensagens (se MSG)

## Destaques do Mês
- Top 3 criativos/conjuntos
- Melhor campanha principal
- Melhor campanha secundária (se MSG)

## O que foi testado
- Lista de testes e resultados

## Aprendizados
- Insights do período

## Plano para o Próximo Mês
- Campanhas a escalar
- Novos testes
- Ajustes estratégicos
```

---

## 8. Sinais de Alerta (Red Flags)

### Críticos
- Campanha consumindo orçamento com zero compras por mais de 3 dias
- CPA > 2x o limite aceitável do cliente
- Pixel/API sem disparar eventos de compra
- Frequência > 4.0 em menos de 7 dias
- CPM subindo > 40% sem ganho proporcional de resultado

### Atenção
- Queda > 30% no volume de mensagens sem alteração de orçamento
- CPA subindo por 3+ dias consecutivos
- CTR abaixo de 1%
- Campanha com apenas 1 compra em 7 dias

---

## 9. Limitações e Cuidados

- Confirmar janela de atribuição antes de concluir
- Evitar decisões definitivas em fase de aprendizado
- 1 compra não define tendência
- Considerar sazonalidade e eventos do período
- Em campanhas MSG, compras por etiqueta podem entrar com delay de 24–72h

