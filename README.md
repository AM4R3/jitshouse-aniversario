# Aniversário Jitshouse — landing page

Página de venda da imersão **Aniversário Jitshouse** — 04, 05 e 06 de setembro de 2026,
Praia do Rosa (Imbituba/SC), com Rodrigo Klippel e seis convidados confirmados.

O site oficial ([jitshouse.com](https://jitshouse.com)) tem só uma home com carrossel —
as páginas de cada imersão estão quebradas (404). Esta é a página de venda que falta.

**Objetivo de conversão:** compra direta no checkout da InfinitePay.
Todos os CTAs primários — nav, hero, seção de investimento, CTA final e barra
sticky do mobile — apontam para o produto, **na mesma aba**:

    https://loja.infinitepay.io/jitshouse_lifestyle/yne5701-ticket-silver-aniversario-jitshouse

**R$ 490,00** (de R$ 590,00, −17%), exibido na landing exatamente como no checkout.
Vendedor que aparece no checkout: *Rodrigo de Mello Klippel*.

O WhatsApp (`wa.me/555199041589`, resolvido do `wa.link/62tfjd`) virou canal
**secundário de dúvidas**, em três pontos e em estilo de link, nunca de botão:
seção de investimento, CTA final e rodapé.

HTML único, sem framework, sem build. Só o Google Fonts é externo. 58 KB.

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

A biblioteca inteira do site (217 imagens, via `/wp-json/wp/v2/media`) foi baixada e
revisada em contact sheet antes da escolha.

| Arquivo | O que é | Onde aparece |
|---|---|---|
| `img/brasao.webp` | brasão Jitshouse Lifestyle | nav, hero, carimbo, CTA, rodapé |
| `img/hero-rosa.webp` | **a enseada da Praia do Rosa vista do alto** | hero |
| `img/openmat.webp` | **open mat cheio, sob a faixa da JitsHouse** | prato de "A experiência" |
| `img/rodrigo-retrato.webp` | **retrato real do Rodrigo de quimono** | seção do anfitrião |
| `img/lugar-onda.webp` | surfista na onda da Praia do Rosa | "O lugar", full-bleed |
| `img/exp-grupo.webp` | a turma reunida na faixa da JitsHouse | galeria |
| `img/exp-gelo.webp` | Rodrigo no banho de gelo | galeria |
| `img/exp-movimento.webp` | prática de movimento no deck, luz de fim de tarde | galeria |
| `img/exp-mesa.webp` | balcão de pedra do café da manhã | galeria |
| `img/exp-piscina.webp` | piscina da casa entre a mata | galeria |
| `img/exp-quarto.webp` | quarto com varanda para o verde | galeria |
| `img/exp-casa.webp` | a casa do alto: piscina e deck | galeria |
| `img/exp-porsol.webp` | pôr do sol sobre o mar | galeria |
| `img/convidado-*.webp` | os 6 retratos dos convidados | seção dos convidados |
| `img/og.jpg` | Open Graph 1200×630 | compartilhamento |

Total: ~1,3 MB.

**Sobre os retratos dos convidados:** são recortes circulares do card oficial, em 316 px.
Existem fotos em alta de quatro deles na biblioteca do site — Carlos André, Matheus Viana,
Pedro Wiggers e Julyano Machado — mas com fundos diferentes entre si (parede escura,
arquibancada de competição). Trocar só quatro deixaria a grade de medalhões desigual, então
mantive os seis iguais, do card. Se quiser as fotos em alta, é decisão de tratamento —
aí vale trocar os seis e mudar o formato.

**Fotos que ficaram de fora de propósito:** a biblioteca tem muita imagem de outras imersões
(Caraíva, Ilhabela, Florianópolis, Costa Rica, Day Trainings) e de atletas que não estão
neste evento. Nenhuma entrou. As fotos de praia e de casa aqui são da Praia do Rosa;
as de tatame e de grupo não afirmam local nenhum.

---

## Copy real (nada inventado)

Vem dos materiais oficiais da marca:

- "Viva o Jiu Jitsu. Viva o Lifestyle." — assinatura do card
- "3 dias de muito jiu jitsu" — card
- Os quatro pilares — "Jiu jitsu de alto nível · Local incrível · Energia positiva ·
  Amigos e irmãos de tatame" — card de convidado confirmado
- "Criei a Jitshouse para provar que o jiu-jitsu vai além do tatame." — Rodrigo Klippel
- Os seis convidados, com equipe/função, do card oficial

**A programação não foi inventada.** A seção de experiência mostra os eixos reais da
imersão e diz que a grade completa vai por WhatsApp na confirmação; o bloco pronto pra
receber a grade real está comentado no HTML. O preço, esse sim, é o real do checkout —
ver a seção abaixo.

---

## O que foi verificado na loja (24/08/2026)

Puxei a loja e a página do produto e conferi antes de escrever o preço:

- **Preço:** R$ 490,00, de R$ 590,00, badge −17%. Bate com a conta: 100/590 = 16,9%.
- **Tier único:** a loja tem exatamente 4 produtos — um por imersão (Aniversário R$ 490,
  Caraíva R$ 1.790, Preview Costa Rica R$ 2.190, Costa Rica R$ 8.990). Só existe **um**
  produto do Aniversário e ele não tem seletor de variação, só de quantidade.
  O "Ticket Silver" do slug não tem irmão Gold. ✔ checklist respondido
- **Sem data de virada de lote:** a descrição do produto é só "Aniversario Jitshouse /
  04,05 e 06 de setembro". Nada de prazo. Por isso a tag diz `-17% · preço atual`
  em vez de inventar um "até DD/MM".
- **Formas de pagamento:** a loja só revela na tela final do checkout. Não afirmo
  bandeiras nem número de parcelas na landing — fica como pendência.
- **Fluxo mobile:** landing → checkout testado a 390px. A página do produto abre,
  mostra R$ 490,00 / R$ 590,00 e os botões "Comprar agora" e "Adicionar ao carrinho",
  sem estouro horizontal. Não avancei para a tela de pagamento (exige dados reais).

## Atenção: o que o ingresso inclui

A versão anterior desta página dizia que o valor incluía "hospedagem, refeições e
atividades". **Isso foi removido** — era suposição, e agora que a pessoa compra sem
falar com ninguém, seria suposição cara.

A loja não detalha o que está incluso, e R$ 490 por três dias fica muito abaixo das
outras imersões da própria Jitshouse (Caraíva R$ 1.790), o que sugere que o ingresso
cobre a participação, não a estadia. Enquanto o Rodrigo não confirmar, a página não
afirma nada — e o link de dúvidas no WhatsApp fica logo abaixo do preço.

## Pendências

- [ ] Grade real dos 3 dias → seção 05 (bloco `TIMELINE` comentado, é só descomentar)
- [ ] **O que o ingresso de R$ 490 inclui** (hospedagem? refeições?) → seção 09
- [ ] O desconto tem data de virada de lote? Se tiver, a tag vira "-17% · até DD/MM"
- [ ] Parcelas e formas de pagamento ativas no checkout → linha de pagamento
- [ ] A vaga confirma automático após o pagamento, ou o Rodrigo confirma na mão?
- [ ] Bio real do Rodrigo: graduação, equipe, credenciais → seção 07
- [ ] Links das landings das próximas imersões → seção 10
- [ ] Fotos dos convidados em alta resolução
- [ ] Confirmar o crédito "site por Baruc Amare" no rodapé

---

## SEO

`title` e `description` em pt-BR, canonical, Open Graph + Twitter card com o card
oficial, e Schema.org `Event` completo — datas ISO, `Place` com endereço,
`organizer` e os sete `performer` (anfitrião + convidados). O `offers` traz o preço
real — R$ 490,00 BRL, `InStock`, apontando para o checkout — e precisa ser atualizado
junto com a landing sempre que o valor mudar na loja.
