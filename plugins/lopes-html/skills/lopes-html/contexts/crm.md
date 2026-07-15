# Contexto — CRM Lopes/DZB

Ler SOMENTE quando a entrega for do CRM (telas de Pessoas, Empresas, Negócios,
Tarefas, pipeline, atividades, dashboards operacionais do CRM).

## Produto

CRM **modular e multi-tenant** da Lopes/DZB. Núcleo: Pessoas · Empresas ·
Tarefas · Negócios. Módulos: Vendas, Marketing, Eventos, Operações.
Caráter visual: plano, denso-operacional e sóbrio. Substitui o styling legado
"Gestão Lopes". Namespace do runtime: `window.LopesCRMDesignSystem_86b542`.

## Vocabulário de domínio

- **Estágios da jornada:** Inscrito · Lead · MQL · SQL · Oportunidade · Cliente · Evangelizador.
- **Tipos de atividade:** Nota · Ligação · E-mail · Reunião · Tarefa.
- **Linha de negócio (LOB):** Lopes · DZB · Ambos · Sem interesse.
- O sistema fala em objeto/verbo ("Negócio movido para Oportunidade"), não em
  primeira pessoa. Evitar "você" fora de microcopy.

## Cores semânticas (tokens de status)

**Estágios da jornada**

| Token | Valor | Estágio |
|---|---|---|
| `--stage-inscrito` | `#71717a` | Inscrito |
| `--stage-lead` | `#3b82f6` | Lead |
| `--stage-mql` | `#a855f7` | MQL |
| `--stage-sql` | `#2563eb` | SQL |
| `--stage-oportunidade` | `#f97316` | Oportunidade |
| `--stage-cliente` | `#16a34a` | Cliente |
| `--stage-evangelizador` | `#eab308` | Evangelizador |

**Tipos de atividade** (usados na Timeline — ícone e badge tintados)

| Token | Valor | Tipo |
|---|---|---|
| `--activity-nota` | `#71717a` | Nota |
| `--activity-ligacao` | `#3b82f6` | Ligação |
| `--activity-email` | `#8b5cf6` | E-mail |
| `--activity-reuniao` | `#f59e0b` | Reunião |
| `--activity-tarefa` | `#22c55e` | Tarefa |

**Linha de negócio**

| Token | Valor | LOB |
|---|---|---|
| `--lob-lopes` | `#2563eb` | Lopes |
| `--lob-dzb` | `#16a34a` | DZB |
| `--lob-ambos` | `#7c3aed` | Ambos |
| `--lob-sem` | `#71717a` | Sem interesse |

Regras: cor de status **apenas com significado** — nunca decorativa. Badges de
status via `color` apontando para estes tokens; nunca inventar cor nova.
Tints suaves de status via `color-mix` sobre o token.

## Padrões de tela

- **StageStepper** com os 7 estágios sempre visíveis (quebra linha se preciso).
- **Timeline** com os 5 tipos de atividade e suas cores fixas.
- **SidebarNav** agrupada (Plataforma · Módulos), ordem travada em todas as páginas.
- Fichas de registro: Tabs (Visão geral · Atividades · Negócios · Arquivos).
- Densidade Compacta é comum em listas grandes (`data-density="compact"`).
