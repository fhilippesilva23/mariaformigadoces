# Maria Formiga Doces

Site de pedidos da Maria Formiga Doces (doces de leite artesanais em pote de 650g).
O cliente escolhe os sabores, monta o pedido e finaliza pelo WhatsApp.

Site estático: HTML, CSS e JavaScript puros, sem build e sem dependências.

## Estrutura

```
index.html        página inteira (estilos e scripts incluídos)
og.jpg            imagem de pré-visualização ao compartilhar o link
assets/           fotos dos potes, logo e favicon
.nojekyll         faz o GitHub Pages servir os arquivos como estão
```

## Como editar preços, WhatsApp, entrega e Pix

No `index.html`, procure por `CONFIGURAÇÃO DA LOJA`:

```js
const CONFIG={
  whatsapp:'5599992304930',   // DDI + DDD + número, só dígitos
  whatsappExibir:'(99) 99230-4930',
  taxaEntrega:8,              // R$ por entrega
  freteGratisAcima:120,       // R$ (subtotal com desconto)
  descontoQtd:4,              // a partir de quantos potes
  descontoPct:10,             // % de desconto
  pix:'99992304930'           // chave Pix
};
```

Os preços ficam logo abaixo, na lista `PRODUCTS` (campo `preco`). Os kits ficam em `KITS`.
O Instagram está no rodapé e no botão flutuante (`mariaformiga.pbs`).

## Publicar no GitHub Pages

1. Envie todos os arquivos para um repositório público.
2. Em **Settings → Pages**, escolha **Deploy from a branch**, branch `main` e pasta `/ (root)`.
3. O site fica em `https://SEU-USUARIO.github.io/NOME-DO-REPOSITORIO/`.

Depois de publicar em outro endereço, atualize em `index.html` as tags `og:url` e `og:image`
(estão apontando para `https://mariaformigadoces.netlify.app`).

## Publicar na Netlify ou na Vercel

Arraste a pasta inteira (ou conecte o repositório). Não há comando de build; o diretório de publicação é a raiz.
