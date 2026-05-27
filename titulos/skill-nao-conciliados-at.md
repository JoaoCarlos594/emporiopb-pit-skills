# Skill AT — Não Conciliados

## Quando ativar
Quando `unmatchedA` (A Receber sem par) ou `unmatchedB` (A Pagar sem par)
tiverem registros após execução da conciliação.

## Análise por título sem par
Para cada título não conciliado, verifica em ordem:

1. **Valor similar** — há título no outro lado com mesmo valor ± 5%?
   → Possível: match não feito por divergência no número do pedido
   
2. **Pedido similar** — há título no outro lado com mesmo pedido, valor diferente?
   → Possível: reemissão com valor corrigido, versão antiga não cancelada
   
3. **Data próxima** — há título com mesmo valor mas data diferente (±15 dias)?
   → Possível: atraso no lançamento ou prazo diferente

4. **Parceiro coincide** — há qualquer título do mesmo parceiro no outro lado?
   → Possível: número de pedido divergente por erro de digitação

## Formato de resposta

```
NÃO CONCILIADOS — ANÁLISE
A Receber sem par: [N] títulos — R$ [total]
A Pagar sem par:   [N] títulos — R$ [total]
Valor total em risco: R$ [total]

SEM PAR — A RECEBER:
[Num] | [Parceiro] | R$ [valor] | Vcto: [data] | [hipótese de causa]
  → Ação: [instrução]

SEM PAR — A PAGAR:
[mesma estrutura]
```

## Ações recomendadas por causa
- Valor similar encontrado: propor match manual e registrar justificativa
- Pedido diferente: contatar parceiro para confirmar numeração correta
- Nenhuma correspondência: verificar se o lançamento foi feito na planilha errada
- Apenas um lado: solicitar ao parceiro emissão do título faltante
- Título muito antigo (>90d sem par): considerar baixa manual com justificativa

## Regras
- Nunca sugere baixa sem justificativa documentada
- Match manual requer aprovação do gestor financeiro
- Títulos sem par > R$ 5.000 sempre escalam para análise gerencial
