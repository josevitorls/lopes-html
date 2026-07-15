# Tema — Lopes Advogados (consultoria jurídica)

Fonte: Guia de Identidade Visual Lopes Advogados v1.0 (brandbook oficial).
Aplicar SOMENTE os overrides abaixo — todo o resto vem de `foundation.md`.

## Paleta oficial da marca

| Cor | Hex | Papel |
|---|---|---|
| Cinza Lopes | `#545454` | cor principal do logo e texto de marca |
| Amarelo | `#FFCC00` | o "ponto" da marca — accent |
| Cinza claro | `#F2F2F2` | fundos suaves |
| Preto | `#000000` | apoio |

## Overrides de tokens

**Modo claro:**

```css
--accent-color: #FFCC00;
--accent-soft: rgba(255, 204, 0, .15);
--chart-1: #545454;          /* séries de dados no cinza da marca */
--chart-2: #FFCC00;          /* amarelo como segunda série/destaque */
--primary: #545454;          /* botão primary no cinza Lopes */
--ring: #b8b8b8;
```

**Modo escuro:**

```css
--accent-color: #FFCC00;
--accent-soft: rgba(255, 204, 0, .18);
--chart-1: #d4d4d8;
--chart-2: #FFCC00;
```

## Regras de contraste do amarelo

- **Nunca texto branco sobre amarelo.** Superfícies preenchidas com
  `--accent-color` usam texto `#18181b`.
- Amarelo puro não é cor de texto sobre fundo claro; para links/destaques de
  texto usar `#a16207` no claro e `#FFCC00` no escuro.
- CTA sólido amarelo com texto escuro é permitido em landing pages.

## Logo oficial

Wordmark "lopes." minúsculo (Fira Sans Black adaptada) com ponto amarelo +
"ADVOGADOS" espaçado abaixo à direita.

| Modo | Arquivo |
|---|---|
| Claro | `assets/lopes-claro.png` (cinza `#545454` + ponto amarelo, fundo transparente) |
| Escuro | `assets/lopes-escuro.png` (branca + ponto amarelo, fundo transparente) |

Em HTML standalone, referencie via URL raw do repositório (público):
`https://raw.githubusercontent.com/josevitorls/lopes-html/main/plugins/lopes-html/skills/lopes-html/assets/lopes-claro.png`
(troque `-claro` ⇄ `-escuro` no toggle de tema junto com `data-theme`).
Se a entrega precisar funcionar offline, embutir como data-URI base64.

**Regras do brandbook:** uso apenas na horizontal; sem distorção, rotação,
contorno ou cores fora da paleta; área de proteção mínima = 50% da altura da
letra "o" em todos os lados; favicon/avatar usa o monograma "lps".

## Marca e voz

- Nome exibido: **Lopes Advogados**. Tagline: *"nada tradicional, fugindo do óbvio"*.
- Posicionamento: escritório não-tradicional, direito aliado à tecnologia
  (digital, marketing law, payments, legalops, privacy).
- Tom: moderno, direto e acessível — autoridade sem juridiquês; sério sem ser
  engessado.
- Tipografia da marca é Fira Sans, mas **as entregas HTML usam Geist**
  (decisão de padronização com o design system — o logo é imagem, não texto).
