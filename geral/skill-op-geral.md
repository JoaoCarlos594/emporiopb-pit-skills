# Skill Geral — Ordens de Produção

## Quando ativar
Quando dados de OP estiverem disponíveis no contexto ou quando perguntado
sobre produção, ordens, fases ou status de fabricação.

## Ciclos e fases do e.Millennium

### Ciclo 00 — Produção Principal
| Código | Fase |
|---|---|
| 0000 | AGUARDANDO CORTE |
| 0010 | CORTE |
| 0020 | COSTURA |
| 0030 | ACABAMENTO |
| 0039 | FIM DE PRODUÇÃO |

### Ciclo 01 — Produção Especial
| Código | Fase |
|---|---|
| 9990 | EM ESPERA |
| 9993 | EM PROCESSAMENTO |
| 9996 | FINAL DE PRODUÇÃO |

### Ciclo 11 — Criação/Piloto
| Código | Fase |
|---|---|
| 8001 | CRIAÇÃO BOOK |
| 8044 | APROVAÇÃO PILOTO |
| 8047 | CORREÇÃO PILOTO |
| 8048 | FINALIZAÇÃO DE PILOTOS |

## Flags críticas — investigação imediata
- **BLOQUEIO**: ordem travada — identificar responsável e motivo
- **AGUARD.**: aguardando insumo, aprovação ou liberação — checar prazo
- **REPROCESSO**: peça retornou à fase anterior — calcular impacto no prazo
- **0328**: fase especial de inspeção — verificar laudo
- **8044 / 8047**: piloto em aprovação/correção — não contar como produção

## Flags de conclusão
- FIM DE PRODUÇÃO / FINAL DE PRODUÇÃO / FINALIZAÇÃO → elegível para quitação
- Quitação: apenas após questionário de 4 etapas + verificação física da peça
- Nunca aprova quitação diretamente — sempre escala para auditor

## Formato de resposta

```
ORDENS DE PRODUÇÃO — STATUS
Total de ordens: [N]
Em andamento: [N] — [% do total]
Concluídas: [N]
Com flags críticas: [N] ← ATENÇÃO

POR CICLO:
  Ciclo 00 (Produção): [N] ordens | Fase atual mais frequente: [fase]
  Ciclo 01 (Especial): [N] ordens
  Ciclo 11 (Pilotos):  [N] ordens

CRÍTICOS:
  [OP] | [Produto] | Flag: [BLOQUEIO/AGUARD./REPROCESSO] | [dias na fase]
  → Ação: [instrução]
```
