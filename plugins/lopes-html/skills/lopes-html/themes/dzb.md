# Tema — DZB Invest (captação de investimentos)

Fonte: Guia de Identidade Visual DZB Invest (brandbook oficial).
Aplicar SOMENTE os overrides abaixo — todo o resto vem de `foundation.md`.

## Paleta oficial da marca

| Cor | Hex | Papel |
|---|---|---|
| Preto profundo | `#1A1A1A` | solidez, credibilidade, autoridade |
| Amarelo | `#FFCC00` | o "ponto" da marca — dinamismo, inovação |

## Overrides de tokens

**Modo claro:**

```css
--accent-color: #FFCC00;
--accent-soft: rgba(255, 204, 0, .15);
--foreground: #1A1A1A;       /* preto profundo da marca */
--primary: #1A1A1A;
--chart-1: #1A1A1A;
--chart-2: #FFCC00;
```

**Modo escuro:**

```css
--accent-color: #FFCC00;
--accent-soft: rgba(255, 204, 0, .18);
--chart-1: #fafafa;
--chart-2: #FFCC00;
```

## Diferenciação vs. tema Lopes

Ambas as marcas são preto + amarelo `#FFCC00`. A distinção vem de:

- **Neutro:** DZB usa preto profundo `#1A1A1A` (contraste duro, sóbrio);
  Lopes usa cinza `#545454` (mais suave).
- **Logo** e **tom de voz** (abaixo).
- No CRM, as cores de LOB (`--lob-lopes` azul / `--lob-dzb` verde) são
  **apenas tags de categorização** — não são cores de marca.

## Regras de contraste do amarelo

- **Nunca texto branco sobre amarelo.** Superfícies com `--accent-color` usam
  texto `#1A1A1A`.
- Texto/link em destaque: `#a16207` no claro, `#FFCC00` no escuro.
- CTA sólido amarelo com texto `#1A1A1A` é permitido em landing pages.

## Logo oficial

Wordmark "DZB" em maiúsculas com **ponto amarelo** + "INVEST" em itálico
(versão completa: DZB com ponto em cima e INVEST abaixo; versão compacta:
apenas "DZB" com o ponto — para avatares e espaços pequenos).

| Modo | Arquivo |
|---|---|
| Claro | `assets/dzb-claro.png` (preta, fundo transparente) |
| Escuro | `assets/dzb-escuro.png` (branca, fundo transparente) |
| Claro compacta | `assets/dzb-claro-compacta.png` |
| Escuro compacta | `assets/dzb-escuro-compacta.png` |

Em HTML standalone, referencie via URL raw do repositório (público):
`https://raw.githubusercontent.com/josevitorls/lopes-html/main/plugins/lopes-html/skills/lopes-html/assets/dzb-claro.png`
(troque `-claro` ⇄ `-escuro` no toggle de tema junto com `data-theme`).
Se a entrega precisar funcionar offline, embutir como data-URI base64.

**Regras do brandbook:** proporções originais sempre (sem esticar/comprimir),
sem rotação/diagonal, cores só da paleta; área de proteção = largura da letra
"D" em todos os lados.

## Marca e voz

- Nome exibido: **DZB Invest**. Taglines: *"Your Growth, Our Expertise"* ·
  *"Investimentos inteligentes"* · *"Cuidando, no presente, do seu futuro"*.
- Posicionamento: captação de investimentos offshore para startups e empresas;
  parceria estratégica premium, sem complicações.
- Tom: força e tradição com inovação e movimento — preciso, orientado a
  números, institucional com dinamismo. Valores sempre em formato BR.
- Tipografia da marca é Fira Sans + New Spirit, mas **as entregas HTML usam
  Geist** (decisão de padronização com o design system — o logo é imagem).
