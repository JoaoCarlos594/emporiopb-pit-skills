# Empório PB — Pit Skills

Skills especializadas por módulo para os agentes Pit Bull.
Carregadas dinamicamente via GitHub raw com cache de 1 hora.

Base URL: `https://raw.githubusercontent.com/JoaoCarlos594/emporiopb-pit-skills/main/`

| Módulo | Pasta | Skills |
|---|---|---|
| FIS | `fis/` | romaneios, boletos, créditos, pagamentos especiais, divergências |
| Títulos | `titulos/` | conciliação, vencimentos, críticas, não conciliados |
| Geral | `geral/` | OP, ponto, visão executiva |

## Cache por módulo

```
localStorage['pit_skills_fis_cache']   + pit_skills_fis_ts
localStorage['pit_skills_at_cache']    + pit_skills_at_ts
localStorage['pit_skills_geral_cache'] + pit_skills_geral_ts
```

TTL: 1 hora por módulo. Recarregado automaticamente ao expirar.
