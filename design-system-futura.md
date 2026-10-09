# Design system: Futura Calçados e Acessórios

Base: o monograma "fc" em caligrafia dentro de uma moldura quadrada (preto sobre um tom pêssego), a paleta nude, caramelo e branco-cru dos calçados fotografados e o vermelho profundo dos pedestais das fotos de tênis. A loja vende moda: o site precisa parecer uma revista de estilo, com a foto como protagonista.

## Tom visual (3 linhas)
1. Editorial e quente: areia, nude e caramelo, com preto no texto e no botão principal.
2. Arcos como forma assinatura, vindos do pedestal em arco da foto da mule, para emoldurar as fotos.
3. Tipografia serifada em itálico nas palavras de estilo, sans limpa no resto, e detalhes que lembram vitrine (faixa em movimento e selo giratório).

## 1. Cores

| Papel | Token | Hex | Uso |
|---|---|---|---|
| Areia | --sand-50 | #FAF5EE | Fundo padrão |
| Areia 2 | --sand-100 | #F2E8DA | Seções alternadas, cartões |
| Areia 3 | --sand-200 | #E7D6BF | Bordas e chips |
| Nude | --nude-300 | #D9B99B | Detalhes e fundos de arco |
| Caramelo | --caramel-500 | #C27B3E | Detalhes gráficos (não é cor de texto) |
| Caramelo texto | --caramel-700 | #8A4C1C | Texto de destaque sobre areia (contraste 6,4:1) |
| Caramelo claro | --caramel-300 | #E3B07A | Destaque sobre fundo escuro (contraste 9:1) |
| Preto quente | --ink-900 | #17110D | Texto forte, botão principal e seções escuras |
| Marrom | --ink-800 | #2A201A | Cartões sobre fundo escuro |
| Texto secundário | --muted | #6B5B4E | Apoio (contraste 6:1) |
| Vermelho | --red-700 | #8E1B27 | Único acento forte (coração, contador, selo) |
| Linha | --line | #E2D3BF | Divisores |
| WhatsApp | --wa-500 | #25D366 | **Exclusivo** do botão e do flutuante (texto escuro #17110D) |
| Alerta | --alert-600 | #B3261E | Erro |

Regras: o caramelo #C27B3E nunca é cor de texto sobre areia; use o #8A4C1C. O vermelho só em detalhes pequenos. O verde do WhatsApp nunca é decorativo.

## 2. Tipografia

| Uso | Fonte | Peso |
|---|---|---|
| Títulos | Instrument Serif (normal e itálico) | 400 |
| Corpo e rótulos | DM Sans | 400, 500 e 700 |

Link de fontes: `https://fonts.googleapis.com/css2?family=Instrument+Serif:ital@0;1&family=DM+Sans:wght@400;500;700&display=swap`

Hierarquia (desktop / mobile):
- H1: 104 px / 54 px, entrelinha 0,95, palavras de estilo em itálico
- H2: 64 px / 40 px, entrelinha 1
- H3: 30 px / 26 px
- Corpo: 18 px / 16 px, DM Sans 400, entrelinha 1,7
- Rótulo: 12 px, DM Sans 700, caixa alta, espaçamento 0,18em
- Botão: 14 px, DM Sans 700, caixa alta, espaçamento 0,1em

## 3. Componentes

**Botão principal:** preto quente, texto areia, pílula de 56 px. Hover: sobe 2 px e fica marrom.
**Botão secundário:** contorno preto de 1,5 px, texto preto; em fundo escuro, contorno e texto areia.
**Botão WhatsApp:** verde #25D366 com texto preto, pílula.
**Foto em arco:** topo em semicírculo, base reta, fundo nude enquanto carrega. Hover: a foto dá um leve zoom.
**Coração (guardar):** botão redondo de 44 px sobre a foto; ativo = vermelho preenchido, com um pequeno estouro de brilho.
**Chip de filtro e de resposta:** pílula com borda fina; selecionado = preto com texto areia.
**Gaveta "Minha seleção":** painel lateral areia com miniaturas, contador vermelho e botão de WhatsApp.
**Campos:** linha de baixo, fundo transparente, foco com linha preta grossa.
**Placeholder de pendência:** borda tracejada com "[A CONFIRMAR]", sempre visível.

## 4. Estética
- Formas: arcos nas fotos, pílulas nos botões, cantos de 4 px nos cartões.
- Sombras: quase nenhuma; profundidade vem de contraste de cor e de foto grande.
- Espaçamento (base 8): 8, 16, 24, 32, 48, 80, 120 px.
- Movimento: faixa deslizando, selo giratório, fotos que entram em sequência, parallax leve no hero. Tudo desligado com `prefers-reduced-motion`.

## Momento assinatura: Tendência, conforto e estilo
Seção fixa que acompanha a rolagem: o título da bio da loja é dividido em três palavras que acendem uma a uma, e a foto em arco ao lado troca junto. Desliga com `prefers-reduced-motion` (as três fotos aparecem lado a lado). Categorias (Sandálias, Tênis, Botas, Mules e sapatilhas) entram como arcos com o nome sobre a foto e a contagem de modelos.

## 5. Conversão para WhatsApp
- CTA no topo, no hero, na gaveta "Minha seleção", no "Qual é o seu passo", em "Compre sem sair de casa", no contato e no fim.
- **Perguntar sobre este modelo**: link em cada foto que abre o WhatsApp já com o nome do modelo.
- **Duas ferramentas**: "Minha seleção" (a cliente favorita fotos e envia a lista) e "Qual é o seu passo" (três perguntas e três sugestões). As duas terminam numa mensagem pronta.
- Grupo de ofertas no WhatsApp como segunda porta de entrada.
- Sem preço, desconto, prazo ou estoque prometido.

## Tokens prontos (CSS)

```css
:root{
  --sand-50:#FAF5EE; --sand-100:#F2E8DA; --sand-200:#E7D6BF; --nude-300:#D9B99B;
  --caramel-300:#E3B07A; --caramel-500:#C27B3E; --caramel-700:#8A4C1C;
  --ink-900:#17110D; --ink-800:#2A201A; --muted:#6B5B4E;
  --red-700:#8E1B27; --line:#E2D3BF;
  --wa-500:#25D366; --alert-600:#B3261E;
  --font-display:'Instrument Serif',Georgia,serif;
  --font-body:'DM Sans',-apple-system,'Segoe UI',sans-serif;
  --r-sm:4px; --r-pill:999px;
}
```
