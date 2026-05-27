# Skill Geral — Ponto

## Quando ativar
Quando dados de ponto estiverem disponíveis no contexto ou quando perguntado
sobre jornada, horas extras, atrasos ou banco de horas.

## Jornada padrão Empório PB
| Parâmetro | Valor |
|---|---|
| Entrada | 08:00 |
| Saída | 18:00 |
| Jornada total | 10h |
| Horas de trabalho | 8h |
| Intervalo (almoço) | 2h |

## Cálculos
- Horas extras = horas trabalhadas − 8h (se positivo)
- Horas faltantes = 8h − horas trabalhadas (se positivo)
- Atraso = hora de entrada real − 08:00 (se positivo)
- Saída antecipada = 18:00 − hora de saída real (se positivo)

## Alertas automáticos

| Situação | Alerta | Ação |
|---|---|---|
| Atraso > 30 min | Notificar gestor | Registrar ocorrência |
| Atraso > 60 min | Escalar RH | Exige justificativa |
| HE > 2h/dia | Verificar autorização | Confirmar com gestor |
| HE acumuladas > 20h/mês | Banco de horas crítico | Programar folga compensatória |
| Falta sem justificativa | Acionar RH | Descontar em folha |
| Saída antecipada > 1h | Notificar gestor | Verificar autorização |

## Formato de resposta

```
PONTO — ANÁLISE DO PERÍODO
Período: [início] a [fim]
Funcionários analisados: [N]
Total de registros: [N]

RESUMO:
  Total horas extras acumuladas: [X]h
  Total horas faltantes: [X]h
  Saldo banco de horas: [+/-X]h
  Funcionários com ocorrências: [N]

OCORRÊNCIAS:
  Atrasos > 30min: [N]
  HE > 2h/dia: [N] ocorrências
  Faltas sem justificativa: [N]

TOP OCORRÊNCIAS:
  [Funcionário] | [Data] | Tipo: [atraso/HE/falta] | Detalhe: [X min/h]
```

## Regras
- Não expõe dados sensíveis de funcionários (salário, dados pessoais) na resposta
- Horas extras somente são válidas com autorização prévia do gestor
- Banco de horas negativo > 8h = escalar para RH imediatamente
