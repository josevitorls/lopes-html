# lopes-html

**Design system da Lopes Digital para o Claude** â€” faÃ§a o Claude entregar pÃ¡ginas,
dashboards, apps e relatÃ³rios HTML sempre na nossa identidade, sem repetir
instruÃ§Ãµes a cada pedido.

Instale uma vez. Depois Ã© sÃ³ pedir: *"gere um dashboard de vendas, tema DZB"* â€”
o Claude aplica sozinho os tokens, componentes e regras da casa.

---

## O que vocÃª ganha

Toda entrega HTML/React do Claude passa a sair, automaticamente:

- **Com a nossa cara** â€” tokens, tipografia Geist, componentes shadcn/new-york
- **Com toggle claro/escuro** (sol/lua) â€” metade do time prefere cada modo
- **Mobile-first** â€” 100% do acesso Ã© por celular; nada quebra em 375px
- **Standalone** â€” um arquivo `.html` Ãºnico que abre em qualquer navegador
- **No tema certo** â€” Lopes (amarelo), DZB (verde), neutro ou tema de cliente

## InstalaÃ§Ã£o (uma vez por pessoa)

### No Claude Desktop / Cowork

1. Abra **ConfiguraÃ§Ãµes â†’ Capabilities** (Recursos)
2. Em plugins/marketplaces, adicione: `josevitorls/lopes-html`
3. Instale o plugin **lopes-html**

### No Claude Code (terminal)

```
/plugin marketplace add josevitorls/lopes-html
/plugin install lopes-html@lopes-html
```

> Repo privado? VocÃª precisa de conta GitHub com acesso a este repositÃ³rio e
> git autenticado na mÃ¡quina (`gh auth login`).

## Como usar

PeÃ§a normalmente, citando o contexto ou o tema:

| VocÃª pede | O Claude faz |
|---|---|
| "Dashboard de captaÃ§Ã£o para investidores" | Detecta DZB, aplica tema verde |
| "PÃ¡gina de acompanhamento de contratos" | Detecta Lopes, aplica tema amarelo |
| "RelatÃ³rio interno de horas do time" | Tema neutro |
| "Landing page para o cliente X, use o tema dele" | Tema do cliente (se existir no repo) |
| "Use o tema DZB" | Tema explÃ­cito vence qualquer detecÃ§Ã£o |

Se o contexto for ambÃ­guo, o Claude pergunta qual tema usar antes de gerar.

## Temas disponÃ­veis

| Tema | Marca | Accent | Arquivo |
|---|---|---|---|
| Lopes | Consultoria jurÃ­dica | Amarelo `#FFCC00` | `themes/lopes.md` |
| DZB | CaptaÃ§Ã£o de investimentos | Verde `#16a34a` | `themes/dzb.md` |
| Neutro | Interno / sem marca | MonocromÃ¡tico zinc | `themes/neutro.md` |
| Cliente exemplo | Template para novos clientes | â€” | `themes/cliente-exemplo.md` |

## Estrutura do repositÃ³rio

```
lopes-html/
â”œâ”€â”€ .claude-plugin/marketplace.json      catÃ¡logo do marketplace
â””â”€â”€ plugins/lopes-html/
    â”œâ”€â”€ .claude-plugin/plugin.json       manifesto do plugin
    â””â”€â”€ skills/lopes-html/
        â”œâ”€â”€ SKILL.md                     roteador de temas + regras invariantes
        â”œâ”€â”€ foundation.md                tokens + 22 componentes (base de tudo)
        â”œâ”€â”€ themes/                      um arquivo por marca/cliente
        â””â”€â”€ contexts/crm.md              vocabulÃ¡rio e cores do CRM
```

**Como funciona:** o `SKILL.md` Ã© o "cÃ©rebro" â€” ele decide qual tema carregar
conforme o pedido e impÃµe as 4 regras invariantes (claro/escuro, mobile 375px,
standalone, shadcn). A `foundation.md` carrega o design system completo. Os
temas sÃ³ sobrescrevem accent e marca.

## ManutenÃ§Ã£o (para quem edita)

1. Edite os arquivos (novo tema, ajuste de token, regra nova)
2. Ao criar tema de cliente: copie `themes/cliente-exemplo.md` e adicione a
   linha na tabela de seleÃ§Ã£o do `SKILL.md`
3. Suba a versÃ£o em `plugin.json` e `marketplace.json` (ex.: `1.0.0` â†’ `1.1.0`)
4. Commit + push na branch `main`
5. O time atualiza: `/plugin marketplace update lopes-html` (Claude Code) ou
   pela interface de plugins (Desktop)

### PendÃªncias conhecidas

- [ ] Confirmar mapeamento: Lopes = jurÃ­dica, DZB = captaÃ§Ã£o (marcado com `TODO` nos temas)
- [ ] Substituir lockups tipogrÃ¡ficos pelos logos oficiais (SVG) quando disponÃ­veis
- [ ] Revisar o piso de 375px a cada release do iOS (hoje: iPhone SE 2Âª/3Âª ger., iOS 26)

---

DÃºvidas ou sugestÃµes: abra uma issue aqui no repositÃ³rio ou fale com o JosÃ©
(josevitor@lopes.digital).

