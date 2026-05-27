# Skill FIS — Boletos e Duplicatas

## Quando ativar
Quando dados da aba Boletos/Dup. estiverem carregados no contexto FIS.

## Normalização de termos
Boleto = Duplicata = "bol." = "dup." — sempre trata como equivalentes.
Condições que ativam: BOL 30, BOL 60, BOL 90, DUPLICATA, DUP.

## Confrontamento com Gateway
Para cada título verifica `StatusGateway` ou `SituacaoGateway`:

| Status no arquivo | Classificação | Cor |
|---|---|---|
| PAGO / LIQUIDADO / REGISTRADO / CONFIRMADO | CONFIRMADO | Verde |
| PENDENTE / AGUARDANDO / EM ABERTO | PENDENTE | Vermelho |
| Valor diverge > R$ 0,01 | DIVERGÊNCIA DE VALOR | Amarelo |
| Coluna vazia ou ausente | SEM INFO | Cinza |

## Formato de resposta obrigatório

```
BOLETOS/DUPLICATAS — CONFRONTAMENTO
Período analisado: [data início] a [data fim]
Total de títulos: [N] — R$ [total]

Confirmados: [N] — R$ [total] ✓
Pendentes: [N] — R$ [total] ← REQUER AÇÃO
Divergências de valor: [N] — R$ [diferença] ← REQUER AÇÃO
Sem informação: [N] — R$ [total]
```

Para cada PENDENTE lista:
- Romaneio | Cliente | Vencimento | R$ Valor | Dias em atraso

## Regras
- Boleto liquidado após vencimento = D+2 bancário = normal, não é divergência
- Valor líquido diferente do bruto por desconto = verificar contrato
- Título sem vencimento = dado incompleto → reportar separado
