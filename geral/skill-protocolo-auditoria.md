# Skill Geral — Protocolo de Auditoria Empório PB

## Quando ativar
Quando o usuário perguntar "posso fechar a auditoria?", "auditoria está ok?",
"checklist", "protocolo" ou qualquer variação dessas perguntas.

## Checklist obrigatório antes de fechar auditoria

Antes de declarar uma auditoria como concluída, verificar:

[ ] 1. Cartões: todos NSUs localizados na Stone ou Valori
[ ] 2. PIX: todos confirmados no Stone ou extrato bancário
[ ] 3. Depósitos: todos com crédito confirmado no extrato
[ ] 4. Dinheiro: transferência D+1 confirmada no extrato
[ ] 5. Boletos/Dup.: todas parcelas registradas no gateway
[ ] 6. Venda Funcionário: todos com título no AT
[ ] 7. Brinde: todos com voucher anexado
[ ] 8. Créditos: datas de pagamento = datas de faturamento
[ ] 9. Pagamentos especiais: todos validados manualmente
[ ] 10. DIF = 0 em todos os romaneios

## Comportamento obrigatório
Responder com o checklist acima preenchido com os dados disponíveis,
marcando ✅ ou ❌ para cada item com base nos dados carregados.
Se não houver dados suficientes para um item, marcar com ⚠ e indicar o que falta verificar.

## Formato final
```
AUDITORIA [PERÍODO] — STATUS FINAL

✅/❌ 1. Cartões: [resumo]
✅/❌ 2. PIX: [resumo]
✅/❌ 3. Depósitos: [resumo]
✅/❌ 4. Dinheiro: [resumo]
✅/❌ 5. Boletos/Dup.: [resumo]
✅/❌ 6. Venda Funcionário: [resumo]
✅/❌ 7. Brinde: [resumo]
✅/❌ 8. Créditos: [resumo]
✅/❌ 9. Pagamentos especiais: [resumo]
✅/❌ 10. DIF = 0: [resumo]

RESULTADO: APROVADA / REPROVADA / PENDÊNCIAS
[Lista de pendências se houver]
```

## Regras
- Todos os 10 itens devem ser ✅ para APROVADA
- Qualquer ❌ = REPROVADA, listar o que falta
- Nunca declarar APROVADA com dados incompletos
