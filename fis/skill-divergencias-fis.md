# Skill FIS — Divergências

## Quando ativar
Quando DIF != 0 (fora da tolerância ±0.01) em qualquer romaneio da Análise Geral.

## Classificação por severidade

| DIF | Classificação | Ação |
|---|---|---|
| < -100 | CRÍTICO | Investigar imediatamente |
| entre -100 e -0.01 | ATENÇÃO | Verificar até 24h |
| > 0.01 | CRÉDITO | Confirmar se é recebimento duplicado |

## Análise obrigatória por divergência
Para cada romaneio com DIF != 0:

1. **Adquirente** — Qual está faltando ou com valor incorreto?
   - Stone: verificar ULTIMO STATUS = "Aprovada" + STONE ID correto
   - Valori: verificar Status = "Confirmada" + NSU na col A
   - Valori Varejo: verificar Status col P (idx 15)
   - PIX Stone: verificar Situacao = "Liquidado"

2. **NSU** — Foi localizado em alguma máquina?
   - Não localizado → linha laranja → verificar manualmente
   - NSU nulo (boleto) → usar extrato bancário

3. **Condição** — Qual é o meio de pagamento esperado?
   - CRÉDITO → busca obrigatória nas adquirentes
   - BOLETO/DUPLICATA → verificar extrato D+2
   - PIX → verificar PIX Stone + extratos das 3 contas
   - DEPÓSITO → verificar extratos 21422-1, 21424-8, 13004690-0

## Formato de resposta

```
DIVERGÊNCIAS — ANÁLISE COMPLETA
Total: [N] romaneios | Valor total exposto: R$ [soma |DIF|]

CRÍTICOS (DIF < -100): [N]
[Romaneio] | [Cliente] | NSU: [X] | Faturado: R$[X] | Recebido: R$[X] | DIF: R$[X]
  → Causa provável: [análise]
  → Ação: [instrução específica]

ATENÇÃO (DIF entre -100 e -0.01): [N]
[lista]

CRÉDITOS (DIF > 0): [N]
[lista]
```

## Causas mais comuns
- MDR (taxa da operadora) sendo deduzida do valor bruto → não é divergência real
- NSU incorreto na 214 (erro de digitação) → verificar junto ao cliente
- Transação cancelada após fechamento → verificar estorno na adquirente
- Boleto pago em agência diferente → verificar extrato
- PIX recebido mas não identificado → busca por valor ± R$ 0,01 nas 3 contas
