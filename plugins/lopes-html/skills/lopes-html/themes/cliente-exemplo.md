# Tema — Cliente Exemplo (TEMPLATE — copie este arquivo)

> **Como criar um tema de cliente:**
> 1. Copie este arquivo para `themes/<nome-do-cliente>.md` (use codinome se o repo for público).
> 2. Preencha os overrides e regras abaixo.
> 3. Adicione uma linha na tabela "Seleção de tema" do `SKILL.md`.
> 4. Suba a versão do plugin em `plugin.json` e `marketplace.json` e faça commit.
> 5. O time atualiza o plugin e recebe o tema novo.

Marca **<Nome do Cliente>**. Aplicar SOMENTE os overrides abaixo — todo o resto
vem de `foundation.md`.

## Overrides de tokens

**Modo claro:**

```css
--accent-color: #______;                 /* cor primária da marca do cliente */
--accent-soft: rgba(_, _, _, .10);       /* mesma cor, alpha ~10% */
--chart-1: #______;                      /* geralmente = accent */
--chart-2: #c7c7cc;
```

**Modo escuro:**

```css
--accent-color: #______;                 /* versão mais clara/luminosa do accent */
--accent-soft: rgba(_, _, _, .14);
--chart-1: #______;
--chart-2: #3f3f46;
```

<!-- Se o cliente tiver identidade completa (fundos, tipografia própria), -->
<!-- adicione os overrides extras aqui — mas mantenha a estrutura de tokens -->
<!-- da fundação. Fonte própria: trocar --font-sans e o @import. -->

## Regras de contraste

- Texto sobre superfícies `--accent-color`: `#______` (verificar contraste WCAG AA).
- Se o accent for claro (amarelo, lima, ciano): texto escuro sobre accent,
  e versão escurecida do accent para texto/link sobre fundo claro.

## Marca

- Nome exibido: **<Nome>**.
- Logo: `<caminho ou "lockup tipográfico">`.
- Tom de voz: `<descrever em 1–2 linhas>`.
- Particularidades: `<ex.: sem sidebar, só relatórios; idioma EN; etc.>`
