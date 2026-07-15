---
name: lopes-html
description: >
  Design system da Lopes Digital para TODA entrega visual em HTML ou React —
  páginas, landing pages, dashboards, apps, relatórios interativos, protótipos.
  Use SEMPRE que for gerar HTML standalone ou componentes visuais para a Lopes,
  a DZB ou clientes. Aplica tema por empresa/cliente, modo claro/escuro
  obrigatório, mobile-first (piso 375px) e componentes no padrão shadcn.
---

# lopes-html — Design System da Lopes Digital

Toda entrega visual segue este fluxo, nesta ordem:

## Fluxo de trabalho

1. **Leia `foundation.md`** (sempre) — tokens, fundamentos visuais e a referência
   dos 22 componentes. É a base comum de todos os temas.
2. **Selecione o tema** pela tabela abaixo e leia SOMENTE o arquivo correspondente
   em `themes/`. O tema define accent, marca e ajustes — nunca substitui a fundação.
3. **Se a entrega for do CRM** (telas de Pessoas, Empresas, Negócios, Tarefas,
   pipeline, atividades), leia também `contexts/crm.md` — vocabulário de domínio
   e cores semânticas de status.
4. **Aplique as regras invariantes** (seção abaixo). Elas valem para todo tema,
   todo cliente, toda entrega — sem exceção.
5. **Rode o checklist final** antes de entregar.

## Seleção de tema

| Contexto do pedido | Tema |
|---|---|
| Consultoria jurídica, contratos, pareceres, marca Lopes | `themes/lopes.md` |
| Captação de investimentos, investidores, pitch, marca DZB | `themes/dzb.md` |
| Cliente específico com tema próprio no repositório | `themes/<cliente>.md` |
| Usuário indicou tema explicitamente ("use o tema X") | o tema indicado |
| Entrega interna/genérica sem marca | `themes/neutro.md` |
| Ambíguo ou tema de cliente inexistente | pergunte ao usuário (AskUserQuestion), oferecendo os temas disponíveis |

> Para criar tema de cliente novo: copie `themes/cliente-exemplo.md`, preencha e
> adicione uma linha nesta tabela via commit no repositório.

## Regras invariantes (NUNCA ignorar, valem para todos os temas)

### 1. Modo claro/escuro — sempre

- Todo HTML entrega **toggle sol/lua** fixo no canto superior direito
  (ícones Lucide `Sun`/`Moon`, botão `ghost` tamanho `icon`).
- Default: respeita `prefers-color-scheme` do dispositivo.
- Preferência persiste em `localStorage` (arquivos standalone abertos no
  navegador). Em artifacts do claude.ai, use estado em memória.
- Implementação: tokens CSS da fundação em `:root` (claro) sobrescritos em
  `[data-theme="dark"]`. O toggle só troca o atributo `data-theme` no nó raiz.
- **Nenhuma cor hardcoded fora dos tokens.** O tema define apenas valores de
  tokens — claro e escuro saem de graça.

### 2. Mobile-first — sempre

- Referência mínima: **375px de largura** (iPhone SE 2ª/3ª geração — menor
  iPhone suportado pelo iOS atual; revisar a cada release do iOS).
- Layout parte de 375px e escala para cima. Nada pode quebrar, transbordar ou
  exigir scroll horizontal da página em 375px.
- `<meta name="viewport" content="width=device-width, initial-scale=1">` e
  `env(safe-area-inset-*)` para notch/home indicator.
- Alvos de toque ≥ 44×44px. Fontes de inputs ≥ 16px (evita zoom automático do iOS).
- Sidebar (shell de app): vira drawer off-canvas com botão hambúrguer abaixo de
  768px; header mantém 56px.
- Tabelas largas: viram cards empilhados no mobile, ou recebem scroll horizontal
  interno ao próprio container (nunca da página).
- Grids de KPI: 1 coluna em 375px, 2 colunas ≥ 480px, 3–4 colunas ≥ 1024px.

### 3. Standalone — sempre

- **Arquivo único**: CSS e JS inline, bibliotecas apenas via CDN.
- Sem build step, sem imports locais, sem arquivos auxiliares. Abre por duplo
  clique em qualquer navegador.
- Setup CDN padrão (React + Babel + Lucide) e o wrapper `DSIcon` estão em
  `foundation.md` §Setup. Os componentes do design system são **recriados inline
  no próprio arquivo** seguindo a especificação da fundação — não existe bundle
  externo para linkar.

### 4. shadcn como base — preferencial

- Antes de criar componente do zero, verifique se existe equivalente na
  referência de 22 componentes da fundação (que segue shadcn/new-york) ou na
  lista shadcn/ui, e replique sua anatomia: variants, sizes, estados,
  acessibilidade.
- Em React com build (raro): importar de `@/components/ui/*`.
- Em HTML standalone (padrão): reproduzir a anatomia com estilos inline
  referenciando `var(--token)`, conforme a fundação.
- Customização de UI/UX por caso acontece **nos tokens e variants do tema**,
  nunca alterando a estrutura base do componente.

## Checklist final (antes de entregar)

- [ ] Toggle sol/lua presente, funcional, persistindo preferência
- [ ] Testado mentalmente em 375px: sem overflow horizontal, toque ≥ 44px
- [ ] Arquivo único, todas as dependências via CDN
- [ ] Zero cores hardcoded — tudo via `var(--token)`
- [ ] Tema correto aplicado (accent, marca)
- [ ] PT-BR e formatos BR (`R$ 1.480.000,00` · `20/04/2026` · `14:20`)
- [ ] Sem emoji na UI; ícones apenas Lucide
- [ ] Exclusões confirmam ("Remover? · Sim / Não"); um primary por grupo de ação
