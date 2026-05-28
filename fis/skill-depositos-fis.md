# Skill FIS — Depósitos

## Quando ativar
Quando qualquer romaneio tiver Deposito > 0.

## Regra de negócio
Para cada depósito deve existir um crédito no extrato bancário
(21424-8, 13008019-9, 109045-3 ou 21422-4) com:
- Valor idêntico (tolerância ±R$0,01)
- Data igual ou D+1

## Formato de resposta
```
DEPÓSITOS — CONFIRMAÇÃO EXTRATO
Confirmados: [N] — R$ [total]
Pendentes: [N] — R$ [total] — REQUER AÇÃO IMEDIATA

Para cada pendente:
- Romaneio: [X] | Data: [D] | Valor: R$ [Y]
- Extratos verificados: 21424, 13008, 109045, 21422
- Ação: localizar depósito físico ou contatar tesouraria
```

## Regras
- Pendência de depósito = risco financeiro alto
- Sempre verificar todos os 4 extratos antes de marcar pendente
- Alertar imediatamente ao responsável financeiro se pendente
