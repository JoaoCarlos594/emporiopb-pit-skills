# Skill Geral — Protocolo de Conferência de Caixa

## O que é
Protocolo de verificação por tipo de pagamento do caixa
diário do Empório PB. O auditor confere cada categoria e
sinaliza o que está OK ou pendente.

## Quando ativar
Quando o usuário perguntar sobre status da conferência, protocolo,
checklist, ou pedir um resumo por categoria de pagamento.

## Categorias a conferir (em ordem)

1. CARTÕES (Valori + Stone)
2. PIX PRESENCIAL (Stone QR + extratos bancários)
3. PIX E-COMMERCE (Pagar.me)
4. DEPÓSITOS (crédito no extrato = valor depositado)
5. DINHEIRO GO (transferência tesouraria D+1)
6. DINHEIRO SP (depósito conta D+1)
7. BOLETOS E DUPLICATAS (parcelas no gateway)
8. CHEQUE (verificar manualmente)
9. VENDA FUNCIONÁRIO (título a receber no AT)
10. BRINDE (voucher anexado no romaneio)
11. CRÉDITOS (data pagamento = data faturamento)
12. IA sinaliza: Em Aberto, Deb. Prestador, Acerto Sócio, Brinde

## Quando o usuário pedir status da conferência
Responde categoria por categoria com os dados disponíveis:

```
✅ CARTÕES — [N] NSUs conferidos, [N] divergências
✅ PIX PRESENCIAL — [N] confirmados, [N] pendentes
✅ PIX E-COMMERCE — [N] confirmados, [N] pendentes
⚠️ DEPÓSITOS — [N] pendentes — verificar extrato
✅ DINHEIRO GO — transferência D+1 confirmada
✅ DINHEIRO SP — depósito D+1 confirmado
✅ BOLETOS/DUP. — [N] parcelas registradas
⚠️ CHEQUE — verificar manualmente
✅ VENDA FUNCIONÁRIO — [N] títulos confirmados no AT
✅ BRINDE — [N] vouchers anexados
✅ CRÉDITOS — datas conferidas
⚠️ PAGAMENTOS ESPECIAIS — [lista de itens pendentes]
```

## Regras
- Se não houver dados suficientes para uma categoria, marcar com ⚠️ e indicar o que falta
- Nunca omitir categorias com pendência — sempre detalhar
- Pagamentos especiais (Em Aberto, Deb. Prestador, Acerto Sócio, Brinde): sempre listar individualmente
