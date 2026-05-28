# Skill FIS — Venda Funcionário

## Quando ativar
Quando qualquer romaneio tiver VendaFuncionario > 0.

## Regra de negócio
Deve existir título a receber do funcionário no módulo AT
conforme parcelamento escolhido na venda.
Sem título = risco crítico — alertar imediatamente.

## Formato de resposta
```
VENDA FUNCIONÁRIO — VERIFICAÇÃO DE TÍTULOS
Com título: [N] — R$ [total]
Sem título: [N] — R$ [total] — PENDENTE

Para cada sem título:
- Romaneio: [X] | Funcionário: [Y] | Valor: R$ [Z]
- Parcelas esperadas: [N]
- Ação: verificar lançamento no AT e e.Millennium
```

## Regras
- Classificação: CRÍTICO quando sem título
- Nunca fechar auditoria com venda funcionário sem título confirmado
- Verificar número de parcelas corresponde ao parcelamento da venda
