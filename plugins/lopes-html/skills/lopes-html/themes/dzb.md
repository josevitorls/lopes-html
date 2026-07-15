# Tema — DZB (captação de investimentos)

<!-- TODO(José): confirmar que DZB = captação de investimentos. Ajustar descrição se necessário. -->

Marca **DZB**. Accent verde sobre a base zinc da fundação.
Aplicar SOMENTE os overrides abaixo — todo o resto vem de `foundation.md`.

## Overrides de tokens

**Modo claro:**

```css
--accent-color: #16a34a;
--accent-soft: rgba(22, 163, 74, .10);
--chart-1: #16a34a;
--chart-2: #c7c7cc;
```

**Modo escuro:**

```css
--accent-color: #22c55e;
--accent-soft: rgba(34, 197, 94, .14);
--chart-1: #22c55e;
--chart-2: #3f3f46;
```

## Regras de uso do verde

- Superfícies preenchidas com `--accent-color` usam texto branco no claro
  (`#16a34a` passa contraste) e `#09090b` no escuro (`#22c55e` é claro).
- Botão `primary` continua `--primary` (zinc) — verde é accent. CTA de landing
  page pode usar sólido verde.
- Atenção semântica: verde também significa "sucesso/positivo". Em telas com
  deltas financeiros (`trend="up"` verde), evitar excesso de verde decorativo
  para não diluir o significado — preferir accent em elementos estruturais
  (barra ativa, progress, foco).

## Marca

- Nome exibido: **DZB**.
- Logo: sem asset oficial — lockup tipográfico (Geist 600, tracking -0.015em)
  como placeholder.
- Tom de voz: preciso e orientado a números em ferramentas; institucional e de
  credibilidade em materiais para investidores. Valores sempre em formato BR.
