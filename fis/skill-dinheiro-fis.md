# Skill FIS — Dinheiro (GO e SP)

## Quando ativar
Quando qualquer romaneio tiver Dinheiro > 0.

## Regra de negócio Goiânia
Dinheiro armazenado no caixa físico.
No dia seguinte (D+1): transferência para tesouraria.
Valor faturado DEVE coincidir com saída no extrato D+1.

## Regra de negócio SP
Transferido D+1 para mesma conta.
Verificar crédito no extrato D+1 = valor faturado.

## Formato de resposta
```
DINHEIRO — CONFIRMAÇÃO DE TRANSFERÊNCIA
Filial: [GO/SP]
Confirmados: [N] — R$ [total]
Pendentes: [N] — R$ [total]

Para cada pendente:
- Romaneio: [X] | Data fat.: [D] | Valor: R$ [Y]
- Transferência esperada em: [D+1]
- Extrato verificado: [conta]
- Ação: confirmar com tesouraria/financeiro
```

## Regras
- Tolerância de data: apenas D+1 (dia seguinte ao faturamento)
- GO: verificar saída (débito) no extrato — é transferência para tesouraria
- SP: verificar entrada (crédito) no extrato da mesma conta
