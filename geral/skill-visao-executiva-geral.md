# Skill Geral — Visão Executiva

## Quando ativar
Quando perguntado sobre situação geral, resumo do dia, briefing executivo,
ou quando nenhum módulo específico for solicitado.

## Dados necessários no contexto
- FIS: total romaneios, divergências, valor faturado vs recebido
- Títulos: taxa de conciliação, pendências, vencidos
- Ponto: funcionários, ocorrências do período
- OP: ordens ativas, flags críticas

## Escala de status por módulo

| % Saudável | Status |
|---|---|
| ≥ 90% | 🟢 SAUDÁVEL |
| 70-89% | 🟡 ATENÇÃO |
| < 70% | 🔴 CRÍTICO |

Para FIS: saudável = % romaneios conferidos ≥ 90%
Para Títulos: saudável = % conciliados ≥ 90%
Para Ponto: saudável = % funcionários sem ocorrência ≥ 80%
Para OP: saudável = % ordens sem flags críticas ≥ 85%

## Formato de resposta obrigatório

```
EMPÓRIO PB — SITUAÇÃO GERAL
Data: [hoje] | Hora: [agora]

┌─────────────────────────────────────────────┐
│ FIS:     [🟢/🟡/🔴 STATUS]                  │
│   [N] romaneios | [N] divergências           │
│   Faturado: R$ [X] | Recebido: R$ [X]        │
│   DIF total: R$ [X]                          │
├─────────────────────────────────────────────┤
│ TÍTULOS: [🟢/🟡/🔴 STATUS]                  │
│   [N] conciliados de [N] ([X]%)              │
│   [N] pendentes | [N] vencidos               │
├─────────────────────────────────────────────┤
│ PONTO:   [🟢/🟡/🔴 STATUS]                  │
│   [N] funcionários | [N] ocorrências         │
│   HE acumuladas: [X]h                        │
├─────────────────────────────────────────────┤
│ OP:      [🟢/🟡/🔴 STATUS]                  │
│   [N] ordens ativas | [N] críticas           │
└─────────────────────────────────────────────┘

PRIORIDADES DO DIA:
1. [item mais crítico com ação específica]
2. [segundo mais crítico]
3. [terceiro mais crítico]

MÓDULOS SEM DADOS:
[lista módulos com dados ausentes — recomenda carregar arquivos]
```

## Regras
- Se módulo sem dados: status = ⚪ SEM DADOS (não usa 🔴)
- Prioridades ordenadas por impacto financeiro total (maior R$ primeiro)
- Nunca inventa dados — usa exatamente o que está no contexto
- Se todos os módulos sem dados: "Carregue os arquivos de cada módulo para ver o briefing executivo"
