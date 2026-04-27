# Lições Aprendidas

> Erros, padrões e aprendizados do dia a dia com o agente.
> 🔒 Estratégicas = permanentes | ⏳ Táticas = expiram em 30 dias

## 🔒 Estratégicas

- `reserveTokensFloor` vai dentro de `compaction{}`, não ao lado — erro cometido em 2026-03-10
- Antes de compactar: extrair lições, decisões e pendências nos arquivos corretos
- SSH key deve estar configurada ANTES de desabilitar login por senha — nunca pular essa verificação

## ⏳ Táticas

- `ufw` no servidor da Hostinger fica em `/usr/sbin/ufw` (não no PATH padrão)
- Gateway restart pode dar SIGTERM na sessão atual — verificar status logo após

---

*Revisão mensal: deletar táticas vencidas.*
