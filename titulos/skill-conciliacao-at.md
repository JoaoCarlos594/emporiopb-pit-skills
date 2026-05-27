# Skill AT — Conciliação de Títulos

## Quando ativar
Quando `results.matched` estiver disponível após execução da conciliação.

## Score de conciliação
| Score | Critério | Confiança |
|---|---|---|
| 1.0 | Pedido + Valor exatos | Alta — confirmar |
| 0.8 | Pedido igual, valor diferente | Média — verificar valor |
| 0.6 | Valor igual ± 5%, pedido diferente | Baixa — revisar manualmente |

## Classificação de saúde

| % Conciliado | Status |
|---|---|
| ≥ 90% | SAUDÁVEL |
| 70% — 89% | ATENÇÃO |
| < 70% | CRÍTICO |

## Formato de resposta obrigatório

```
CONCILIAÇÃO — RESULTADO
Período: [data início] a [data fim]
Taxa: X% ([N] de [N] títulos conciliados)
Status: SAUDÁVEL / ATENÇÃO / CRÍTICO

Valor total A Receber: R$ [X]
Valor total A Pagar:   R$ [X]
Valor conciliado:      R$ [X]

Divergências de valor: [N] pares — diferença total R$ [X]
Sem match (A Receber): [N] títulos — R$ [X]
Sem match (A Pagar):   [N] títulos — R$ [X]
```

Para cada par com divergência de valor:
```
Par [N]:
  A Receber: [num título] | [parceiro] | R$ [valor] | [vencimento]
  A Pagar:   [num título] | [parceiro] | R$ [valor] | [vencimento]
  Diferença: R$ [X] — [motivo provável]
  Ação: [instrução]
```

## Regras
- Diferença ≤ R$ 0,01 = conferido (arredondamento)
- Diferença de centavos causada por MDR ou desconto = não é erro
- Score 0.6: sempre revisão manual antes de confirmar
