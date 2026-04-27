# Thresholds de Alerta por Cliente

> Alertar Franklin imediatamente se qualquer métrica ultrapassar o limite abaixo.

## Regra Geral (enquanto não tiver threshold específico por cliente)

| Métrica | Alerta se |
|---------|-----------|
| CPL | Subir >40% em relação à média dos últimos 7 dias |
| CTR | Cair abaixo de 0.8% em campanha fria |
| Budget diário | Zerar antes das 20h |
| Campanha | Parar inesperadamente (status ≠ ACTIVE sem motivo) |
| Frequência | Ultrapassar 3.5 em campanha fria |
| ROAS | Cair abaixo de 2x em campanha quente |

## Clientes com threshold específico

*(Preencher conforme Franklin informar)*

| Cliente | Métrica | Threshold |
|---------|---------|-----------|
| NPG | CPL | A confirmar |
| Ventura Arq | CPL leads | A confirmar — cliente em risco |
| Kasa Marchi | CPL | A confirmar |
| Terracini | CPL | A confirmar |
| Jucy Santos | CPL | A confirmar |
| Runemal | CPL | A confirmar |

## Protocolo de Alerta

Quando threshold ultrapassado:
1. Identificar causa provável (criativos, público, sazonalidade, concorrência)
2. Montar mensagem de alerta com: cliente + métrica + valor atual + valor normal + causa provável + sugestão de ação
3. Enviar para Franklin (`telegram:1034862412`)
4. Aguardar instrução antes de alterar qualquer coisa

*Atualizado: 2026-03-18*

