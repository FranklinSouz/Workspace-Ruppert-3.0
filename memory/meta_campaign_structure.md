# Estrutura de Campanhas Meta Ads — Franklin Souza
> Regra permanente. Aplicar sempre que subir campanhas para qualquer cliente.

---

## Regra Geral

- **Sempre CBO** (orçamento na campanha, nunca no conjunto)
- **4 campanhas por cliente** (temperatura × mídia) + remarketing separado
- **Conjuntos = hipóteses de comunicação** (cada conjunto carrega criativos com mesmo motivo central)

---

## Campanhas

### FRIO (2 campanhas)
```
[CAPTAÇÃO] [F] [IMG] tag_mesano - DD/MM/AAAA
[CAPTAÇÃO] [F] [VID] tag_mesano - DD/MM/AAAA
```

**Conjuntos (frio):**
```
01- LL1% - Compradores e/ou Leads
02- LL1% - Seguidores e Engajamento Geral
03- Interesse: [interesse óbvio do nicho]
04- Interesse 2: [interesse secundário]
05- Aberto AD+ (para clientes sem base de engajamento ou negócios locais)
```
→ Todos os conjuntos excluem públicos quentes

### QUENTE (2 campanhas)
```
[CAPTAÇÃO] [Q] [IMG] tag_mesano - DD/MM/AAAA
[CAPTAÇÃO] [Q] [VID] tag_mesano - DD/MM/AAAA
```

**Conjuntos (quente) com exclusões em cascata:**
```
01- Mix 14D  → Visitou perfil + Envolvimento IG + VV + Todos Sites (14D) | sem exclusão
02- Mix 30D  → idem 30D | exclui Mix 14D
03- Mix 60D  → idem 60D | exclui Mix 14D + 30D
04- Mix 90D  → idem 90D | exclui Mix 14D + 30D + 60D
05- Mix 180D → idem 180D | exclui Mix 14D + 30D + 60D + 90D
06- Mix Lista de Leads (todos os lançamentos) | exclui todos acima + Alunos
```
MIX = Envolvimento 14D + Visitou Perfil 14D + VV 14D + Todos Sites 14D

### REMARKETING (1 campanha separada)
```
[RMKT] [Q] [IMGeVID] tag_mesano - DD/MM/AAAA
```
→ Mídia mista (IMG e VID no mesmo conjunto)

**Conjuntos sugeridos:**
```
01- Abriu form mas não enviou (14D)
02- Visitou página de destino (14D)
03- Engajou alto (VV 75%+, 14D)
```

---

## Nomenclatura de Anúncios

```
AD01 - IMG - [gancho ou trecho principal do criativo]
AD02 - VID - [gancho ou trecho principal do criativo]
```

## Limite de Anúncios por Conjunto

| Situação | Máximo de anúncios |
|----------|-------------------|
| Verba baixa | 5 por conjunto |
| Lançamento | 10 por conjunto |

→ Geralmente os mesmos criativos rodam em todos os conjuntos
→ Duplicar conjunto apenas se ultrapassar o limite E cliente tiver verba suficiente

---

## Tipos de Objetivo

| Tipo | Objetivo Meta |
|------|--------------|
| Captação de leads | LEADS |
| Lançamento / OpenCart | OUTCOME_SALES (VENDAS) |

---

## UTM Dinâmicas (aplicar em TODOS os anúncios)

```
LINK/?utm_source={{ad.id}}&utm_campaign={{campaign.name}}&utm_medium={{adset.name}}&utm_content={{ad.name}}&utm_term={{placement}}
```

| Parâmetro | Valor dinâmico | O que captura |
|-----------|---------------|---------------|
| utm_source | `{{ad.id}}` | ID do anúncio |
| utm_campaign | `{{campaign.name}}` | Nome da campanha |
| utm_medium | `{{adset.name}}` | Nome do conjunto |
| utm_content | `{{ad.name}}` | Nome do anúncio |
| utm_term | `{{placement}}` | Posicionamento (feed, stories, reels...) |

→ Sempre anexar ao link de destino antes de subir o anúncio via API

---

## Lembrete Operacional

Antes de subir qualquer campanha:
1. Confirmar temperatura (frio/quente/rmkt)
2. Confirmar tipo de mídia (IMG / VID / misto)
3. Confirmar objetivo (leads ou vendas)
4. Confirmar verba → define limite de anúncios por conjunto
5. Confirmar tag do cliente (ex: npg_mar26, ventura_mar26)
