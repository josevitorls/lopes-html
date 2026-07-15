# Fundação — Design System Lopes Digital

> Base comum de TODOS os temas. Sistema visual: **shadcn/ui**, estilo *new-york*,
> base neutra **zinc**, accent configurável pelo tema. Tipografia **Geist** +
> Geist Mono. Ícones **Lucide**. Idioma **PT-BR**, formatos BR.

---

## 1. Voz & conteúdo

- **Idioma:** PT-BR em toda a interface.
- **Formatos BR sempre:** `R$ 1.480.000,00` · `20/04/2026` · `14:20` · `+55 11 9 8765-4321`.
- **Voz:** funcional, curta, operacional — sem tom de marketing, sem exclamações.
  (Exceção: landing pages e materiais de marketing podem usar voz persuasiva,
  definida no tema.)
- **Ações no imperativo:** *Registrar atividade*, *Novo negócio*, *Agendar reunião*, *Concluir*.
- **Caixa:** *sentence case* em labels e botões (não Title Case). Exceção: cabeçalhos
  de coluna em MAIÚSCULAS, 11–12px, `letter-spacing:.03em`. **Sem ponto final** em labels.
- **Confirmações explícitas:** excluir dados **sempre confirma** ("Remover? · Sim / Não");
  toasts declaram o resultado ("Atividade registrada") e oferecem "Desfazer" quando reversível.
- **Sem emoji. Sem glifos unicode como ícones** (exceto `⌘`/`⏎` em kbd, em Geist Mono).

## 2. Fundamentos visuais

- **Cor:** sistema neutro zinc. Superfícies quase-brancas sobre `--muted` sutil; texto
  quase-preto com `--muted-fg` para secundário. Accent definido pelo tema via
  `--accent-color` + `--accent-soft` + `--chart-1`. **Cor de status é reservada para
  significado** — nunca decorativa. Avatares usam 8 tints pastel fixos, atribuídos por nome.
- **Tipografia:** Geist. Escala operacional compacta (11.5 → 30px). Números em tabelas
  e KPIs **sempre** `font-variant-numeric: tabular-nums`. Geist Mono para `⌘K`, atalhos
  e números tabulares.
- **Espaçamento:** grid base 4px (4·8·12·16·24·32·48·64·96). Duas densidades —
  Confortável (gap 24 / card-pad 22 / row-pad 12) e Compacto (16 / 16 / 9).
- **Fundos:** preenchimentos planos e sólidos. **Sem gradientes, imagens, texturas ou
  padrões** atrás da UI. Página = `--background`; sidebar um tom à parte (`--sidebar`).
- **Cantos:** cards 10px (`--radius`), botões/inputs/badges 8px, tags 6px, pills e
  avatares totalmente arredondados.
- **Cards:** `1px solid --border` + `--radius` + `--shadow` sobre `--card`. Só isso —
  sem borda-esquerda colorida, sem sombra dupla.
- **Linhas:** hairlines de 1px `--border` fazem o trabalho estrutural. Tabelas e listas
  divididas por hairlines, não por cards.
- **Elevação:** duas sombras. `--shadow` para cards em repouso; `--shadow-popover` para
  dropdowns, popovers e menus.
- **Foco & estados:** foco = `border-color:--ring` + `box-shadow:0 0 0 3px --accent-soft`.
  Hover — linhas/itens ghost vão a `--hover`; botão primary cai para `opacity:.9`.
  Press — deslize de 0.5px, **sem escala/bounce**. Item de nav ativo = fundo
  `--sidebar-active` + barra de 3px `--accent-color` na borda esquerda.
- **Movimento:** 150–200ms `ease-out` (`--dur` 170ms, `--ease` `cubic-bezier(.2,0,0,1)`).
  Apenas fades e slides curtos. **Sem bounce, sem spring, sem loop decorativo.**
- **Transparência & blur:** com parcimônia. Backdrop de diálogo `rgba(9,9,11,.45)` com
  blur de 1px. Sem glassmorphism na moldura.
- **Layout (shell de app):** `grid: var(--sidebar-w) minmax(0,1fr)`, `height:100vh`
  (desktop), header fixo de 56px, `main` rolável. Sidebar 264px expandida / 74px
  recolhida — **vira drawer off-canvas abaixo de 768px** (regra invariante mobile).
  Conteúdo centralizado em no máx. 1320px (fichas) / 1380px (listas).

## 3. Tokens

Custom properties CSS em `:root`. Estilize sempre via `var(--token)`.
Temas de cor: `data-theme="light|dark"` no nó raiz troca a paleta;
`data-density="compact"` aperta gaps/paddings. O tema da marca redefine
`--accent-color`, `--accent-soft` e `--chart-1`.

### 3.1 Cores — modo claro (padrão)

| Token | Valor | Uso |
|---|---|---|
| `--background` | `#ffffff` | fundo da página |
| `--foreground` | `#09090b` | texto primário |
| `--card` | `#ffffff` | superfície de card |
| `--muted` | `#f4f4f5` | preenchimento sutil / trilhos |
| `--muted-fg` | `#71717a` | texto secundário |
| `--border` | `#e4e4e7` | bordas hairline |
| `--input` | `#e4e4e7` | borda de input |
| `--ring` | `#a1a1aa` | borda de foco / ativo |
| `--primary` | `#18181b` | botão primary / texto forte |
| `--primary-fg` | `#fafafa` | texto sobre primary |
| `--secondary` | `#f4f4f5` | botão secundário / segmento |
| `--hover` | `#f4f4f5` | hover de linha / item |
| `--sidebar` | `#fafafa` | superfície da sidebar |
| `--sidebar-fg` | `#09090b` | texto da sidebar |
| `--sidebar-border` | `#e9e9ec` | borda da sidebar |
| `--sidebar-active` | `#ececef` | preenchimento do item ativo |
| `--chart-1` | `#18181b` | série 1 / base do accent (tema redefine) |
| `--chart-2` | `#c7c7cc` | série 2 |
| `--accent-color` | `var(--chart-1)` | barra ativa, progress, ring, foco (tema redefine) |
| `--accent-soft` | `rgba(24,24,27,.07)` | tint do accent (tema redefine) |
| `--danger` | `#dc2626` | destrutivo |
| `--danger-soft` | `rgba(239,68,68,.10)` | preenchimento confirmar-exclusão |
| `--danger-bd` | `rgba(239,68,68,.30)` | borda confirmar-exclusão |
| `--shadow` | `0 1px 2px 0 rgba(0,0,0,.05)` | elevação de card |
| `--shadow-popover` | `0 8px 24px rgba(0,0,0,.12)` | dropdown/popover |

### 3.2 Cores — overrides do modo escuro (`[data-theme="dark"]`)

| Token | Valor |
|---|---|
| `--background` | `#09090b` |
| `--foreground` | `#fafafa` |
| `--card` | `#121214` |
| `--muted` | `#1c1c20` |
| `--muted-fg` | `#9a9aa3` |
| `--border` | `#272729` |
| `--input` | `#272729` |
| `--ring` | `#52525b` |
| `--primary` | `#fafafa` |
| `--primary-fg` | `#18181b` |
| `--secondary` | `#1c1c20` |
| `--hover` | `#1c1c20` |
| `--sidebar` | `#0c0c0e` |
| `--sidebar-fg` | `#fafafa` |
| `--sidebar-border` | `#202022` |
| `--sidebar-active` | `#1d1d21` |
| `--chart-1` | `#fafafa` |
| `--chart-2` | `#3f3f46` |
| `--accent-soft` | `rgba(250,250,250,.10)` |
| `--danger` | `#f87171` |
| `--danger-soft` | `rgba(239,68,68,.16)` |
| `--danger-bd` | `rgba(239,68,68,.40)` |
| `--shadow` | `0 1px 2px 0 rgba(0,0,0,.4)` |
| `--shadow-popover` | `0 8px 24px rgba(0,0,0,.5)` |

### 3.3 Tints de avatar (pares fixos bg / fg)

| Nome | `--avatar-*-bg` | `--avatar-*-fg` |
|---|---|---|
| indigo | `#e0e7ff` | `#3730a3` |
| green | `#dcfce7` | `#166534` |
| red | `#fee2e2` | `#991b1b` |
| amber | `#fef3c7` | `#92400e` |
| violet | `#ede9fe` | `#6d28d9` |
| sky | `#cffafe` | `#155e75` |
| pink | `#fce7f3` | `#9d174b` |
| blue | `#dbeafe` | `#1e40af` |

### 3.4 Tipografia

| Token | Valor |
|---|---|
| `--font-sans` | `"Geist", ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, Helvetica, Arial, sans-serif` |
| `--font-mono` | `"Geist Mono", ui-monospace, "SF Mono", Menlo, Consolas, "Liberation Mono", monospace` |
| `--weight-light` | `300` |
| `--weight-regular` | `400` |
| `--weight-medium` | `500` |
| `--weight-semibold` | `600` |
| `--weight-bold` | `700` |

**Escala de tamanho**

| Token | Valor | Peso típico · uso |
|---|---|---|
| `--text-h1` | `22px` | título de página (h1) · 600 · tracking -0.015em |
| `--text-kpi` | `30px` | número KPI · 600 · tabular-nums |
| `--text-h3` | `15px` | título de card (h3) · 600 |
| `--text-body` | `13.5px` | corpo, nav, botões · 500 |
| `--text-table` | `13px` | tabela, input · 400 |
| `--text-label` | `12.5px` | labels secundários · 500 |
| `--text-meta` | `11.5px` | meta + cabeçalho de coluna · 500 · UPPER .03em |

> **Regra invariante mobile:** campos de formulário usam `font-size ≥ 16px` para
> evitar o zoom automático do iOS — mesmo que a escala acima indique menor.

**Tracking & line-height:** `--track-tight` -0.015em · `--track-caps` 0.03em ·
`--leading-tight` 1.2 · `--leading-snug` 1.4 · `--leading-body` 1.55.

### 3.5 Espaçamento, raios, layout & movimento

**Espaçamento (grid 4px):** `--space-1` 4 · `--space-2` 8 · `--space-3` 12 ·
`--space-4` 16 · `--space-6` 24 · `--space-8` 32 · `--space-12` 48 ·
`--space-16` 64 · `--space-24` 96 (px).

**Raios:** `--radius` 10px (cards) · `--radius-control` 8px (botões, inputs, badges) ·
`--radius-tag` 6px (tags) · `--radius-pill` 9999px (pills, avatares, segmentos).

**Densidade** (Confortável padrão / Compacto via `[data-density="compact"]`):
`--gap` 24/16 · `--card-pad` 22/16 · `--row-pad` 12/9.

**Shell:** `--sidebar-w` 264px · `--sidebar-w-collapsed` 74px · `--header-h` 56px ·
`--content-ficha` 1320px · `--content-lista` 1380px.

**Movimento:** `--ease` `cubic-bezier(.2, 0, 0, 1)` · `--dur` 170ms · `--dur-fast` 120ms.

## 4. Iconografia

- **Lucide** é o sistema de ícones — a UI inteira usa. Stroke **2** para moldura/UI,
  **1.7–1.8** para glifos de timeline. Tamanhos: 14–18px inline, 16–20px em botões.
- CDN (global UMD): `https://unpkg.com/lucide@0.460.0/dist/umd/lucide.min.js`.
- **Não desenhar SVGs de ícone à mão** — sempre puxar do Lucide. Se faltar um glifo,
  escolher o nome Lucide mais próximo.
- **Status = dots coloridos**, não ícones.
- **Logo:** enquanto não houver asset oficial no tema, usar lockup tipográfico.

Wrapper React mínimo (`DSIcon`), definir inline em toda entrega:

```js
function DSIcon({ name, size = 16, stroke = 2, color = "currentColor", style }) {
  const def = window.lucide && window.lucide[name];
  if (!def) return null;
  const children = def[2] || [];
  return React.createElement("svg", {
    width: size, height: size, viewBox: "0 0 24 24", fill: "none",
    stroke: color, strokeWidth: stroke, strokeLinecap: "round", strokeLinejoin: "round", style,
  }, children.map((c, i) => React.createElement(c[0], { key: i, ...c[1] })));
}
```

## 5. Regras globais (não-negociáveis)

1. **Estilos inline referenciando tokens** — sem stylesheets de classe, sem tokens duplicados.
2. **PT-BR** e formatos BR sempre. **Sem emoji** na UI.
3. Look shadcn/new-york: plano, bordas 1px + sombra leve, zinc neutro.
4. Ícones **Lucide** (stroke 2).
5. **A ordem da sidebar é travada** — idêntica em toda página; só muda o item ativo.
6. **Dropdowns/menus fecham** em clique-fora **e** Esc.
7. **Excluir dados sempre confirma** (padrão "Remover? · Sim / Não" em cores de danger).
8. Um único botão **primary** por agrupamento de ação na tela.

## 6. Referência de componentes (22)

Primitivos React auto-contidos, estilizados via `var(--token)`. Em entregas
standalone, **recriar inline** os componentes usados, seguindo esta especificação.

### Forms

**Button** — ação primária. Variantes `primary` (sólido `--primary`, hover opacity .9) ·
`outline` (borda hairline, hover `--hover`) · `secondary` (muted) · `ghost` · `destructive`
(texto danger + borda suave) · `link`. Tamanhos `sm` 32 · `md` 36 (padrão) · `lg` 40 ·
`icon` 36×36. Press = deslize 0.5px, sem bounce.
Props: `variant`, `size`, `disabled`, `leadingIcon`/`trailingIcon`, `fullWidth`.

```jsx
<Button variant="primary" leadingIcon={<DSIcon name="Plus" size={16} />}>Novo negócio</Button>
```

**Input** — campo de uma linha. h36 / raio 8 / borda `--input` 1px. Foco = borda `--ring`
+ glow 3px `--accent-soft`. Props: `type`, `size`, `invalid`, `disabled`, `leading`/`trailing`
(ícone, sufixo, kbd `⌘K`).

```jsx
<Input placeholder="Buscar…" leading={<DSIcon name="Search" size={15} />} trailing={<kbd>⌘K</kbd>} />
```

**Textarea** — multilinha. Mesma linguagem de borda/foco do Input; resize só vertical;
min-height ~76px. Props: `invalid`, `disabled`, `rows` (padrão 3).

**Select** — `<select>` nativo estilizado com chevron, para escolha única de lista curta.
Props: `options` (`[{value,label}]`) ou `<option>` filhos, `size`, `invalid`, `disabled`,
`placeholder`.

**Checkbox** — booleano. Marcado preenche `--primary` + check branco; suporta
`indeterminate`. Props: `checked`, `indeterminate`, `disabled`, `label`, `onChange`.

**Switch** — toggle instantâneo. Trilho preenche `--accent-color` quando ligado; knob
desliza 150–200ms sem bounce. Props: `checked`, `disabled`, `label`, `onChange`.

**SegmentedControl** — 2–4 modos mutuamente exclusivos. Container `--muted`, item ativo
sobe para `--card` com sombra. Props: `options`, `value`, `onChange`, `size`.

### Display

**Card** — superfície fundamental. `1px --border` + raio 10 + `--shadow` sobre `--card`.
Props: `title`, `description`, `actions` (slot à direita do header), `footer`, `flush`
(remove padding — para tabela/lista full-bleed).

```jsx
<Card title="Atividades" description="Histórico do contato"
  actions={<Button size="sm" variant="outline">Registrar</Button>}> … </Card>
```

**StatCard** — KPI único. Número grande tabular-nums + label + delta opcional. Valores em
formato BR. Props: `label`, `value`, `delta`, `trend` (`"up"` verde / `"down"` danger),
`hint`, `icon`.

```jsx
<StatCard label="Negócios abertos" value="R$ 1.480.000" delta="+12,4%" trend="up" hint="vs. mês anterior" />
```

**Badge** — pill de status/categoria. Variantes `outline` (padrão), `solid`, `soft`.
`color` puxa dos tokens semânticos — nunca inventar cor de status. Props: `variant`,
`color`, `dot`.

**Tag** — label pequeno (atributos, chips de filtro), raio 6. Remoção segue a regra
global: X vira "Remover? Sim/Não" em danger. Props: `label`, `onRemove`, `color`.

**Avatar** — círculo com 1 de 8 tints pastel (determinístico pelo nome) + iniciais de
2 letras; aceita `src`. Props: `name`, `src`, `size` (`xs|sm|md|lg|xl` ou px),
`tint` (0–7), `ring` (cor de status).

**ProgressBar** — trilho fino `--muted` com preenchimento `--accent-color`.
Props: `value`, `max`, `height` (padrão 6), `color`, `label`, `showValue`.

**StageStepper** — pills de jornada/etapas. **Todas as etapas sempre visíveis**, com
quebra de linha; a atual é sólida `--primary`, concluídas têm check, futuras outline.
Props: `stages`, `current`, `onSelect`.

**Tabs** — navegação entre seções. Tab ativa preenche `--secondary`; suporta badge de
contagem. Props: `tabs` (strings ou `{value,label,count}`), `value`, `onChange`.

**Timeline** — feed de eventos. Cada entrada = ícone Lucide tintado (por tipo) + badge
de tipo + timestamp + autor. Props: `items` (`[{type,title?,text?,timestamp?,author?}]`).
Cores por tipo: ver `contexts/crm.md` quando aplicável.

### Feedback / overlays

**Dialog** — modal para confirmações, criação e fluxos multi-step. Escurece a página;
**fecha em Esc + clique no backdrop**. Props: `open`, `onClose`, `title`, `description`,
`footer` (ações à direita), `width` (padrão 520; no mobile, max-width 100% − 32px).
Confirmações destrutivas usam Button `destructive` no footer.

**Menu** — dropdown/popover de ações. Ancorado ao trigger; **sempre fecha em clique-fora
e Esc**. Selecionar item fecha. Props: `trigger`, `items`
(`[{label,icon,shortcut,onClick,danger,disabled}]` ou `{separator:true}` / `{header:"…"}`),
`align`, `width`, `defaultOpen` ou `children`.

**Tooltip** — dica curta em hover/foco para botões só-ícone e texto truncado. Preenche
com `--primary`. Props: `label`, `side`, `children`. (Em telas de toque, garanta que a
ação não dependa do tooltip.)

**Toast** — notificação transitória. Card neutro; `tone` adiciona dot de status.
Emparelhe com "Desfazer" quando reversível. Props: `title`, `description`, `tone`
(`default|success|danger|info`), `action`, `onClose`.

### Navigation

**Breadcrumb** — trilha no header de 56px. Último item é a página atual.
Props: `items` (`[{label,href?,onClick?}]`).

**SidebarNav** — navegação agrupada. Item ativo = fundo `--sidebar-active` + barra 3px
accent à esquerda; contagens à direita. **Ordem travada.** Abaixo de 768px vira drawer.
Props: `groups` (`[{label?, items:[{icon,label,count?,active?,onClick?}]}]`), `collapsed`.

## 7. Setup de consumo (standalone)

```html
<!doctype html>
<html lang="pt-BR">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<style>
  @import url('https://fonts.googleapis.com/css2?family=Geist:wght@300..700&family=Geist+Mono:wght@400..600&display=swap');
  :root { /* tokens do modo claro (§3.1) + overrides do tema */ }
  [data-theme="dark"] { /* overrides do modo escuro (§3.2) */ }
</style>
<script src="https://unpkg.com/react@18.3.1/umd/react.production.min.js"></script>
<script src="https://unpkg.com/react-dom@18.3.1/umd/react-dom.production.min.js"></script>
<script src="https://unpkg.com/@babel/standalone@7.29.0/babel.min.js"></script>
<script src="https://unpkg.com/lucide@0.460.0/dist/umd/lucide.min.js"></script>
</head>
<body>
<div id="root"></div>
<script type="text/babel">
  // DSIcon (§4) + componentes usados (§6), recriados inline
  // Toggle de tema: troca data-theme no <html>, persiste em localStorage,
  // default = prefers-color-scheme
</script>
</body>
</html>
```

- Gráficos: Chart.js ou Recharts via CDN, cores das séries via `--chart-1`/`--chart-2`.
- Temas: `data-theme="light|dark"` e `data-density="comfortable|compact"` no nó raiz.

## 8. Lacunas conhecidas

- Fontes via Google Fonts `@import` (Geist + Geist Mono). Para self-host, trocar por `@font-face`.
- **Logo oficial ausente** — lockup tipográfico como placeholder até receber SVG/PNG nos temas.
- Agendador de reunião (diálogo 2-step) e combobox "Vincular" ainda por detalhar.
