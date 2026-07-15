# Tema — Lopes (consultoria jurídica)

<!-- TODO(José): confirmar que Lopes = consultoria jurídica. Ajustar descrição se necessário. -->

Marca **Lopes**. Accent amarelo da marca sobre a base zinc da fundação.
Aplicar SOMENTE os overrides abaixo — todo o resto vem de `foundation.md`.

## Overrides de tokens

**Modo claro e escuro (iguais, salvo indicado):**

```css
--accent-color: #FFCC00;
--accent-soft: rgba(255, 204, 0, .15);   /* claro */
--chart-1: #FFCC00;
--chart-2: #c7c7cc;                       /* claro · escuro: #3f3f46 */
```

**Modo escuro:** `--accent-soft: rgba(255, 204, 0, .18)`.

## Regras de contraste do amarelo

- **Nunca texto branco sobre o amarelo.** Qualquer superfície preenchida com
  `--accent-color` usa texto `#18181b`.
- Botão `primary` continua `--primary` (zinc escuro/claro conforme o modo) — o
  amarelo é accent (barra ativa, progress, foco, série 1 de gráfico, destaques),
  não cor de botão. Para CTA de landing page, pode-se usar botão sólido amarelo
  com texto `#18181b`.
- Em texto sobre fundo claro, não usar `#FFCC00` puro (contraste insuficiente);
  para texto/link em destaque usar `#a16207` (amber-700) no claro e `#FFCC00`
  no escuro.

## Marca

- Nome exibido: **Lopes**.
- Logo: sem asset oficial — lockup tipográfico (Geist 600, tracking -0.015em)
  como placeholder.
- Tom de voz: sóbrio e técnico-jurídico em ferramentas; claro e confiável em
  materiais externos. Sem juridiquês desnecessário em UI.
