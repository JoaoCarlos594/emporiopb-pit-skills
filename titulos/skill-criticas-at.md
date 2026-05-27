# Skill AT — Críticas por Pedido Cancelado / Inconsistência

## Quando ativar
Quando `window.atCriticasContext` estiver populado, ou quando o usuário
perguntar sobre críticas, inconsistências ou pedidos problemáticos.

## Tipos de crítica monitorados
1. **Título A Receber sem pedido correspondente** — recebeu mas não há pedido registrado
2. **Título A Pagar sem pedido correspondente** — pagou mas não há pedido registrado
3. **Pedido cancelado com título em aberto** — pedido foi cancelado mas há cobrança pendente
4. **Duplicidade** — mesmo pedido aparece 2x em A Receber ou 2x em A Pagar
5. **Valor inconsistente** — título difere do valor do pedido em mais de 5%

## Priorização
Ordena por valor total exposto (|Receber| + |Pagar|) decrescente.
Foca análise nos top 10 maiores exposições.

## Classificação de severidade

| Situação | Severidade |
|---|---|
| A Receber + A Pagar pendentes no mesmo pedido | CRÍTICO |
| Apenas A Receber pendente | ATENÇÃO |
| Apenas A Pagar pendente | ATENÇÃO |
| Duplicidade | ALTO |

## Formato de resposta

```
CRÍTICAS — ANÁLISE
Total de críticas: [N] | Valor total exposto: R$ [X]

TOP [N] MAIORES EXPOSIÇÕES:
[N]. Pedido: [num] | Parceiro: [nome]
     A Receber: R$ [X] | A Pagar: R$ [X] | Exposição: R$ [X]
     Tipo: [tipo crítica]
     Ação: [instrução específica]
```

## Ações por tipo
- Pedido cancelado + título aberto: solicitar cancelamento do título ou nota de crédito
- Duplicidade: identificar qual é o original e cancelar a duplicata
- Valor inconsistente: solicitar reemissão com valor correto
- Sem pedido: verificar se é adiantamento ou lançamento manual
