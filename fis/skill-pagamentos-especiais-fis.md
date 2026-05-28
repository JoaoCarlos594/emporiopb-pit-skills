# Skill FIS — Pagamentos Especiais

## Quando ativar
Quando qualquer romaneio da Análise Geral tiver valor > 0 em qualquer
das colunas de pagamento especial.

## Colunas monitoradas
| Coluna | Descrição | Nível de risco |
|---|---|---|
| EmAberto | Valor ainda não recebido | Alto |
| DebPrestador | Débito de prestador | Médio |
| AcertoSocio | Acerto interno entre sócios | Alto — documentar |
| Brinde | Produto dado como brinde | Baixo — conferir estoque |
| FreeInfluencer | Produto para influencer | Médio — verificar contrato |
| CreditoCliente | Crédito gerado para o cliente | Alto — verificar origem |

## Comportamento obrigatório
Lista TODOS os romaneios com qualquer pagamento especial.
Nunca fecha auditoria sem listar pagamentos especiais identificados.

## Formato de resposta

```
PAGAMENTOS ESPECIAIS — SITUAÇÃO
Total de romaneios com pagamentos especiais: [N]
Valor total envolvido: R$ [soma de todos]

POR TIPO:
EmAberto:        [N] romaneios — R$ [total] ← verificar recebimento
AcertoSocio:     [N] romaneios — R$ [total] ← documentar
DebPrestador:    [N] romaneios — R$ [total]
CreditoCliente:  [N] romaneios — R$ [total]
Brinde:          [N] romaneios — R$ [total]
FreeInfluencer:  [N] romaneios — R$ [total]
```

Para cada romaneio lista:
```
[Romaneio] | [Cliente] | Tipo: [campo] | R$ [valor] | [Ação recomendada]
```

## Regras
- AcertoSocio > R$ 1.000: sempre pede documentação/justificativa
- EmAberto > 30 dias: aciona protocolo de cobrança
- FreeInfluencer: verifica se há contrato/NF correspondente
- CreditoCliente: verifica se é devolução ou adiantamento

VENDA FUNCIONÁRIO:
- Romaneio [X] — Funcionário [Y] — R$ [valor] — [N] parcelas
- Status: COM TÍTULO / SEM TÍTULO
- Ação: verificar parcelamento e confirmar título no AT

BRINDE:
- Romaneio [X] — R$ [valor]
- Voucher: ANEXADO / PENDENTE
- Ação se pendente: localizar voucher físico ANTES de fechar
