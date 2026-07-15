# lopes-html

**Design system da Lopes Digital para o Claude** — faça o Claude entregar páginas,
dashboards, apps e relatórios HTML sempre na nossa identidade, sem repetir
instruções a cada pedido.

Instale uma vez. Depois é só pedir: *"gere um dashboard de vendas, tema DZB"* —
o Claude aplica sozinho os tokens, componentes e regras da casa.

---

## O que você ganha

Toda entrega HTML/React do Claude passa a sair, automaticamente:

- **Com a nossa cara** — tokens, tipografia Geist, componentes shadcn/new-york
- **Com toggle claro/escuro** (sol/lua) — metade do time prefere cada modo
- **Mobile-first** — 100% do acesso é por celular; nada quebra em 375px
- **Standalone** — um arquivo `.html` único que abre em qualquer navegador
- **No tema certo** — Lopes (amarelo), DZB (verde), neutro ou tema de cliente

## Instalação (uma vez por pessoa)

> **Antes de começar:** você precisa de um plano pago do Claude (Pro, Max,
> Team ou Enterprise). Não precisa de conta GitHub, não precisa instalar
> nada no computador. Leva uns 2 minutos.

### 🟢 Passo a passo para quem usa o chat ou o Cowork

Funciona igual no **claude.ai (navegador)**, no **app Claude Desktop (aba
Chat)** e no **Cowork**. Se estiver no Desktop e usar o Cowork, entre na aba
**Cowork** antes de seguir os passos.

**Parte 1 — adicionar o catálogo da Lopes (só na primeira vez):**

1. Abra o Claude e olhe a **barra lateral esquerda**
2. Clique no menu **Personalizar** (*Customize*) — é onde ficam plugins,
   skills e conectores
3. Entre na aba **Plugins**
4. Na seção **Plugins pessoais** (*Personal plugins*), clique no botão **"+"**
   e escolha **"Adicionar marketplace"** (*Add marketplace*)
5. Escolha **"Adicionar de um repositório"** (*Add from a repository*) e cole:

   ```
   https://github.com/josevitorls/lopes-html
   ```

6. Confirme. O catálogo "lopes-html" aparece na sua lista

**Parte 2 — instalar o plugin:**

7. Ainda na aba **Plugins**, clique em **"Explorar plugins"** (*Browse
   plugins*), encontre o **lopes-html** e clique em **"Instalar"**

**Pronto. Para conferir se funcionou:** em qualquer conversa, digite `/` na
caixa de mensagem — a skill **lopes-html** deve aparecer na lista.

**Para usar:** não precisa fazer nada especial. Peça normalmente ("faça um
dashboard de captação para a DZB") e o Claude aplica o design system sozinho.
A tabela [Como usar](#como-usar) abaixo tem exemplos de pedidos.

**Quando o José avisar que tem novidade** (tema novo, ajuste de marca): volte
em **Personalizar → Plugins**, abra o marketplace lopes-html e atualize. Nada
para baixar, nada para configurar de novo.

### 🛠️ No Claude Code (terminal — para quem programa)

```
/plugin marketplace add josevitorls/lopes-html
/plugin install lopes-html@lopes-html
```

## Como usar

Peça normalmente, citando o contexto ou o tema:

| Você pede | O Claude faz |
|---|---|
| "Dashboard de captação para investidores" | Detecta DZB, aplica tema verde |
| "Página de acompanhamento de contratos" | Detecta Lopes, aplica tema amarelo |
| "Relatório interno de horas do time" | Tema neutro |
| "Landing page para o cliente X, use o tema dele" | Tema do cliente (se existir no repo) |
| "Use o tema DZB" | Tema explícito vence qualquer detecção |

Se o contexto for ambíguo, o Claude pergunta qual tema usar antes de gerar.

## Temas disponíveis

| Tema | Marca | Cores | Arquivo |
|---|---|---|---|
| Lopes Advogados | Consultoria jurídica | Cinza `#545454` + amarelo `#FFCC00` | `themes/lopes.md` |
| DZB Invest | Captação de investimentos | Preto `#1A1A1A` + amarelo `#FFCC00` | `themes/dzb.md` |
| Neutro | Interno / sem marca | Monocromático zinc | `themes/neutro.md` |
| Cliente exemplo | Template para novos clientes | — | `themes/cliente-exemplo.md` |

## Estrutura do repositório

```
lopes-html/
├── .claude-plugin/marketplace.json      catálogo do marketplace
└── plugins/lopes-html/
    ├── .claude-plugin/plugin.json       manifesto do plugin
    └── skills/lopes-html/
        ├── SKILL.md                     roteador de temas + regras invariantes
        ├── foundation.md                tokens + 22 componentes (base de tudo)
        ├── themes/                      um arquivo por marca/cliente
        └── contexts/crm.md              vocabulário e cores do CRM
```

**Como funciona:** o `SKILL.md` é o "cérebro" — ele decide qual tema carregar
conforme o pedido e impõe as 4 regras invariantes (claro/escuro, mobile 375px,
standalone, shadcn). A `foundation.md` carrega o design system completo. Os
temas só sobrescrevem accent e marca.

## Manutenção (para quem edita)

1. Edite os arquivos (novo tema, ajuste de token, regra nova)
2. Ao criar tema de cliente: copie `themes/cliente-exemplo.md` e adicione a
   linha na tabela de seleção do `SKILL.md`
3. Suba a versão em `plugin.json` e `marketplace.json` (ex.: `1.0.0` → `1.1.0`)
4. Commit + push na branch `main`
5. O time atualiza: `/plugin marketplace update lopes-html` (Claude Code) ou
   pela interface de plugins (Desktop)

### Pendências conhecidas

- [ ] Revisar o piso de 375px a cada release do iOS (hoje: iPhone SE 2ª/3ª ger., iOS 26)

> v1.1.0: temas alinhados aos brandbooks oficiais (ambas as marcas preto +
> amarelo `#FFCC00`) e logos oficiais em `assets/` (variantes claro/escuro).

---

Dúvidas ou sugestões: abra uma issue aqui no repositório ou fale com o José
(josevitor@lopes.digital).
