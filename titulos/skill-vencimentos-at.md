# Skill AT — Vencimentos

## Quando ativar
Quando títulos com data de vencimento estiverem carregados (A Receber ou A Pagar).

## Data de referência
Sempre usar a data atual do sistema (`new Date()`) como base para calcular atrasos.

## Classificação por urgência

| Situação | Classificação | Ação |
|---|---|---|
| Vencido > 90 dias | CRÍTICO | Risco de inadimplência — acionar jurídico |
| Vencido 30-90 dias | ALTO | Acionar cobrança imediata |
| Vencido 1-29 dias | MÉDIO | Notificar cliente/fornecedor |
| Vence em 7 dias | ATENÇÃO | Preparar cobrança preventiva |
| Vence em 8-30 dias | A VENCER | Monitorar |
| Vence em > 30 dias | EM DIA | Normal |

## Formato de resposta obrigatório

```
VENCIMENTOS — SITUAÇÃO ATUAL
Data de referência: [hoje]

A RECEBER:
  Críticos (>90d):    [N] títulos — R$ [total]
  Alto (30-90d):      [N] títulos — R$ [total]
  Médio (1-29d):      [N] títulos — R$ [total]
  A vencer em 7d:     [N] títulos — R$ [total]
  Em dia:             [N] títulos — R$ [total]

A PAGAR:
  [mesma estrutura]

TOTAL VENCIDO: R$ [total A Receber + A Pagar vencidos]
```

Para CRÍTICOS e ALTO, lista individualmente:
```
[Num Título] | [Parceiro] | Venceu: [data] | [N] dias | R$ [valor] | Status: [status]
```

## Regras
- Títulos em status "quitado" ou "pago" = excluir da análise de vencimento
- Título vencido com data de pagamento = já recebido, não é inadimplência
- Feriados bancários não ajustam o vencimento automaticamente
