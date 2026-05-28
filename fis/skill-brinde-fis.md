# Skill FIS — Brinde

## Quando ativar
Quando qualquer romaneio tiver Brinde > 0.

## Regra de negócio
Obrigatório: voucher físico deve estar anexado no romaneio.
Sem voucher = auditoria não pode ser fechada.

## Formato de resposta
```
BRINDES — VERIFICAÇÃO DE VOUCHER
Com voucher: [N]
Sem voucher: [N] — AUDITORIA BLOQUEADA

Para cada sem voucher:
- Romaneio: [X] | Valor brinde: R$ [Y]
- Ação: localizar voucher físico e anexar no sistema
- CRÍTICO: não fechar auditoria sem voucher confirmado
```

## Regras
- Voucher ausente = bloqueio total da auditoria daquele romaneio
- Classificação: ALTO quando sem voucher
- Ação obrigatória antes de fechar: confirmação física do voucher
