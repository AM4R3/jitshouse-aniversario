# Aniversário Jitshouse — landing page

Página de venda da imersão **Aniversário Jitshouse** — 04, 05 e 06 de setembro de 2026,
Praia do Rosa (Imbituba/SC), com Rodrigo Klippel e seis convidados confirmados.

O site oficial ([jitshouse.com](https://jitshouse.com)) tem só uma home com carrossel —
as páginas de cada imersão estão quebradas (404). Esta é a página de venda que falta.

**Objetivo de conversão:** garantir a vaga pelo WhatsApp oficial
(`wa.me/555199041589`, resolvido do `wa.link/62tfjd` publicado no site).
Secundário: a loja oficial na InfinitePay.

HTML único, sem framework, sem build. Só o Google Fonts é externo. 52 KB.

---

## Template

Esta página foi construída para ser **clonada** para as outras imersões
(Caraíva, Esquenta Costa Rica, Réveillon Costa Rica).

- O bloco `DADOS DA IMERSÃO`, no topo do `index.html`, lista tudo que muda.
- No corpo, cada ponto de troca está marcado com `[DADO: ...]`.
- O que ainda falta de informação real está marcado com `[SUBSTITUIR]`.

```bash
grep -n "\[DADO:\|\[SUBSTITUIR\]\|\[VALIDAR\]" index.html
```

---

## Paleta

Amostrada pixel a pixel dos ativos oficiais (`Logo-jitshouse.png` e o card
`Aniversario-V5-Site.jpg`) — **não** dos hexes estimados do brief, porque o verde real
da marca é bem mais profundo.

| Token | Hex | De onde veio | Contraste |
|---|---|---|---|
| `--floresta` | `#04211E` | fundo do card oficial | superfície |
| `--floresta-2` | `#01100F` | seções profundas | superfície |
| `--verde-rosa` | `#004030` | o verde da rosa do brasão | 9.7:1 no papel |
| `--ouro` | `#C5B178` | o aro do brasão | 8.0:1 na floresta |
| `--ouro-quente` | `#C38018` | o lettering "JITSHOUSE" do card | 5.2:1 |
| `--areia` | `#F9DA85` | o triângulo do brasão | 12.4:1 |
| `--papel` | `#F0E8D6` | pôster impresso | 13.9:1 |
| `--tinta` | `#1C2420` | texto sobre papel | 13.0:1 |

Dourado nunca em corpo de texto sobre papel (2.5:1) — no papel ele só aparece como
filete, moldura e carimbo. Todos os textos aferidos ficaram entre 5.2:1 e 14.2:1.

---

## Imagens

Todas reais, baixadas da própria biblioteca de mídia do `jitshouse.com`.
Nenhuma imagem de IA, nenhum banco de imagem.

| Arquivo | O que é | Origem |
|---|---|---|
| `img/brasao.webp` | brasão Jitshouse Lifestyle | `Logo-jitshouse.png` |
| `img/hero-casa.webp` | aérea da casa, piscina e mata | galeria 2026/08 |
| `img/lugar-onda.webp` | surfista na onda da Praia do Rosa | galeria 2026/07 |
| `img/rodrigo.webp` | retrato do Rodrigo (recorte circular) | `RODRIGO-KLIPPEL.jpg` |
| `img/convidado-*.webp` | os 6 retratos dos convidados | recortados do card oficial |
| `img/exp-*.webp` | deck, movimento, tatame, mesa, piscina, quarto, área comum | galerias 2026/07–08 |
| `img/card-aniversario.webp` | o card oficial da imersão | `Aniversario-V5-Site.jpg` |
| `img/og.jpg` | Open Graph 1200×630 | topo do card oficial |

Total: ~1 MB. Os retratos dos convidados vêm do card em 316 px — **pedir as fotos
originais** para dobrar a nitidez em telas retina.

---

## Copy real (nada inventado)

Vem dos materiais oficiais da marca:

- "Viva o Jiu Jitsu. Viva o Lifestyle." — assinatura do card
- "3 dias de muito jiu jitsu" — card
- Os quatro pilares — "Jiu jitsu de alto nível · Local incrível · Energia positiva ·
  Amigos e irmãos de tatame" — card de convidado confirmado
- "Criei a Jitshouse para provar que o jiu-jitsu vai além do tatame." — Rodrigo Klippel
- Os seis convidados, com equipe/função, do card oficial

**Programação e preço não foram inventados.** A seção de experiência mostra os eixos
reais da imersão e diz que a grade completa vai por WhatsApp; a de investimento diz
"vagas limitadas" e leva pro WhatsApp. Os blocos prontos pra receber os dados reais
estão comentados no HTML.

---

## Pendências

- [ ] Grade real dos 3 dias → seção 05 (bloco `TIMELINE` comentado, é só descomentar)
- [ ] Preço, lotes, formas de pagamento e o que está incluso → seção 09
      (e acrescentar `offers` no JSON-LD)
- [ ] Link direto do produto na loja InfinitePay (hoje aponta pra loja inteira)
- [ ] Bio real do Rodrigo: graduação, equipe, credenciais → seção 07
- [ ] Links das landings das próximas imersões → seção 10
- [ ] Fotos dos convidados em alta resolução
- [ ] Confirmar o crédito "site por Baruc Amare" no rodapé

---

## SEO

`title` e `description` em pt-BR, canonical, Open Graph + Twitter card com o card
oficial, e Schema.org `Event` completo — datas ISO, `Place` com endereço,
`organizer` e os sete `performer` (anfitrião + convidados). Sem `offers` enquanto
não houver preço.
