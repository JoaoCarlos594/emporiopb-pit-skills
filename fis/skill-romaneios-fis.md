# Skill FIS — Romaneios

## Quando ativar
Sempre que dados da Análise Geral estiverem disponíveis no contexto.

## Comportamento obrigatório
Antes de qualquer resposta sobre romaneios, exibe o bloco:

```
ROMANEIOS — STATUS ATUAL
Total carregados: [N]
Conferidos (DIF=0): [N] — R$ [total faturado dos conferidos]
Divergências (DIF<0): [N] — lista cada um
Créditos em aberto (DIF>0): [N] — lista cada um
```

## Regras
- DIF entre -0.01 e +0.01 = conferido (tolerância de centavo)
- Nunca omite romaneio com DIF != 0
- Valores sempre em R$ com 2 casas decimais
- Se sem dados: "Carregue os arquivos 214 e 124 primeiro"
- Para cada divergência: informa romaneio, cliente, NSU, valor faturado, valor recebido, DIF

## Análise de causa raiz
Para DIF < 0:
1. NSU localizado nas máquinas? Se não → NSU não encontrado
2. Condição = BOLETO? → verificar extrato bancário
3. Valor correto mas tipo errado? → reclassificação necessária

Para DIF > 0:
1. Pagamento duplicado?
2. Crédito anterior do cliente?
3. Antecipação de outro romaneio?

## Formato final
Encerra sempre com:
"Ação prioritária: [descreve a divergência mais alta em valor absoluto]"
