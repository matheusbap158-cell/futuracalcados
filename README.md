# Futura Calçados e Acessórios (demo)

Landing page de demonstração, HTML único (`index.html`), sem dependências além das fontes do Google Fonts. Não publicada.

## Estrutura
- `index.html`: o site (hero com arcos, faixa em movimento, coleção filtrável com coração, "Qual é o seu passo", gaveta "Minha seleção", "Compre sem sair de casa" com grupo de ofertas, a loja, avaliações, contato com mapa)
- `Copy.txt`: texto da página
- `design-system-futura.md` / `.html`: design system
- `assets/`: 17 fotos otimizadas, logo "fc" sem fundo (escura e clara), favicon e imagem de compartilhamento
- `Logo/`, `Imagens/`, `Fotos/`, `Info copy/`, `Link do ...txt`: materiais de origem
- `Fotos/_com-rosto-nao-usadas/`: duas fotos com o rosto de pessoas na loja, que não entram no site. O `.gitignore` deixa `Imagens/`, `Fotos/` e `Info copy/` fora do git (originais de terceiros, prints com pessoas e nomes completos de avaliadores); só `index.html` e `assets/` vão para o repositório, junto com os textos e o design system

## Como funciona o catálogo
Os modelos ficam na lista `P` dentro do `<script>` do `index.html` (arquivo, nome, tipo, cor e ocasiões). Para trocar fotos ou nomes, edite essa lista e coloque o `.jpg` em `assets/`. A seleção da cliente é guardada no `localStorage` do aparelho dela (chave `futura_sel`).

## Como visualizar
Na pasta da agência: `node "_ferramentas/preview-local.mjs" "4. Meus Clientes/2. Demos e propostas/futuracalcados"` e abrir o endereço mostrado. Se o navegador de teste deixar a aba em segundo plano (`document.visibilityState` igual a `hidden`), animações e capturas congelam; abrir uma aba nova e ativa resolve.

## Antes de publicar
- O `index.html` tem `<meta name="robots" content="noindex, nofollow">` para a demo não aparecer no Google. Remover ao publicar o site definitivo.
- Os itens `[A CONFIRMAR]` aparecem no site com borda tracejada; a lista completa está na ficha em `4. Meus Clientes/_Fichas/Futura Calcados.pdf`.
- Confirmar nomes, marcas e autorização das fotos de produto (parecem de campanhas das marcas e de postagens da loja).
- Confirmar o endereço da loja online (o Maps mostra lojavirtualnuvem.com.br) e o que o grupo de ofertas envia.
- Pedir a logo em alta resolução (o arquivo tem 150 px).
- Usar endereço absoluto em `og:image` e `twitter:image` quando houver domínio.
- A foto da botinha preta foi recortada para não mostrar a tatuagem do tornozelo.
