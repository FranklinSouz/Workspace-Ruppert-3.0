# Feedback & Aprendizado

> Consultado ANTES de cada sugestão relevante.
> Quando Franklin rejeita algo, o motivo fica aqui — e eu não repito o erro.

## Domínios

| Arquivo | O que cobre |
|---------|-------------|
| `feedback/content.json` | Tom, formato, estilo de conteúdo e comunicações |
| `feedback/tasks.json` | Como executo tarefas, abordagem operacional |
| `feedback/recommendations.json` | Sugestões estratégicas, ferramentas, frameworks |
| `feedback/digest.json` | Resumos, relatórios e sínteses de informação |

## Como registrar feedback

Quando Franklin rejeitar algo, ele fala:
> "Ruppert, rejeito isso porque [motivo]"

Eu identifico o domínio e registro no JSON correto:

```json
{
  "date": "YYYY-MM-DD",
  "context": "descrição do que foi sugerido",
  "decision": "reject | adjust | approve",
  "reason": "motivo real",
  "tags": ["tag1", "tag2"]
}
```

## Regras de uso

- **`reject`** → nunca repetir
- **`adjust`** → usar versão ajustada como referência
- **`approve`** → reforçar esse padrão
- **Máx 30 entradas por arquivo (FIFO)** — entrada mais antiga sai quando chegar no limite
- **Revisão mensal** — consolidar padrões recorrentes em `memory/lessons.md`

---

## Feedbacks registrados

| Data | Contexto | Decisão | Motivo |
|------|----------|---------|--------|
| 2026-04-07 | Análises de Meta Ads com muitos subtítulos, parágrafos explicativos e seções longas | reject | Franklin quer respostas curtas e diretas, sem perder profundidade — bullet points enxutos, sem repetição |
