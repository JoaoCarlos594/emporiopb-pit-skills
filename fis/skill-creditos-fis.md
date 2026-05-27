# Skill FIS — Créditos a Pagar

## Quando ativar
Quando dados da aba Créditos (A Receber) estiverem carregados no contexto FIS.

## Regra de negócio principal
A data de pagamento do título de crédito DEVE ser igual à data de faturamento
do romaneio correspondente na 124. Tolerância: zero dias.

Fórmula: `DataPagamentoCredito == DataFaturamento124[Romaneio]`

## Classificação por data

| Situação | Status |
|---|---|
| Datas iguais | OK — válido |
| Diferença 1-7 dias | ATENÇÃO — verificar |
| Diferença > 7 dias | DIVERGÊNCIA — investigar |
| Sem romaneio correspondente na 124 | SEM REFERÊNCIA — analisar manualmente |

## Formato de resposta obrigatório

```
CRÉDITOS — VALIDAÇÃO DE DATAS
Total de créditos: [N] — R$ [total]

OK (data correta): [N] — R$ [total]
Atenção (1-7 dias): [N] — R$ [total]
Divergências (>7 dias): [N] — R$ [total] ← REQUER AÇÃO
Sem referência na 124: [N] — R$ [total]
```

Para cada DIVERGÊNCIA lista:
- Título | Romaneio | Data Pagamento | Data Faturamento 124 | Diferença em dias

## Ações recomendadas
- Divergência de data: solicitar comprovante de recebimento
- Sem referência: verificar se romaneio existe na 214
- Valor diferente: checar desconto concedido vs contrato
