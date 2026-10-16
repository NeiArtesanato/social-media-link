# Néia Artesanatos — página de links

Página única (estilo "link na bio") da loja Néia Artesanatos, que vende aviamentos e armarinho: linhas para amigurumi, kits, tecidos. A loja **não** vende peças prontas; os textos devem falar de matéria-prima, não de "feito à mão".

## Estrutura

- `index.html` — a página inteira (HTML + CSS inline, sem build, sem JS além do necessário).
- `logo.jpg` — logo completa (fundo branco; usada com `mix-blend-mode: multiply`).
- `Flor_LOGO.png` — só a flor; usada no avatar redondo e como favicon.
- `og-image-v2.jpg` — imagem de prévia do link (Open Graph), 1200×630.

## Publicação

- Hospedado no GitHub Pages: https://neiartesanato.github.io/social-media-link/
- O Pages publica a partir da `main`. Branches: `main`, `develop`, `feat/*`.
- Commits em inglês, padrão Conventional Commits (`feat:`, `fix:`, `chore:`...).

## Conteúdo e marca

- Interface em português (pt-BR).
- Slogan: "A matéria-prima da sua arte." (fonte Dancing Script). Tagline: "Aviamentos & armarinho".
- Fontes: Inter (texto), Dancing Script (slogan), Cormorant Garamond (monograma de fallback).
- Cores: rosa da página `--accent: #b5476b`; rosa da logo `#c70661`; verde da logo `#9cc157`.
- Botões: WhatsApp e Instagram usam as cores oficiais de cada plataforma; a loja usa o rosa da marca.
- Links: WhatsApp `https://wa.me/5518996340125`, Instagram `https://www.instagram.com/neia.artesanatos.ep/`, loja `https://www.neiaartesanatos.com.br/`, "Como chegar" = rota do Google Maps até R. Osvaldo C. Feitosa, 140 - Pres. Epitácio/SP (botão azul Google).

## Prévia do link (Open Graph / WhatsApp)

- `og:image` precisa de URL absoluta, < 600 KB, largura ≥ 300px, proporção ≤ 4:1.
- O WhatsApp guarda a prévia em cache: ao trocar a imagem, **renomeie o arquivo** (`og-image-v3.jpg`...) e atualize `og:image` e `og:image:secure_url`, em vez de usar `?v=`.
- Mesmo cumprindo os requisitos, o WhatsApp tem mostrado a prévia como miniatura pequena (testado no iPhone). A imagem deve continuar legível nesse tamanho: logo grande, pouco texto.
- Para testar: Sharing Debugger da Meta (https://developers.facebook.com/tools/debug/) e envio pelo app do celular com uma URL nova (ex.: `?v=NN` no link da página).

## Cartão digital (`cartao/`)

Imagem 1080×1350 (exportada em 2x) para enviar como **foto** no WhatsApp, com o link na legenda — foto sempre aparece grande, ao contrário da prévia de link.

- `cartao/cartao.html` — fonte do cartão (logo, slogan, contatos, QR code).
- `cartao/qrcode.svg` — QR code da página, gerado com `segno` (correção de erro "H", por isso a flor no centro não atrapalha a leitura).
- `cartao/cartao-digital.jpg` — imagem final. Para regerar, tirar screenshot com Chrome headless:
  `chrome --headless=new --hide-scrollbars --force-device-scale-factor=2 --window-size=1080,1350 --virtual-time-budget=8000 --screenshot=out.png file:///.../cartao/cartao.html` e converter para JPG.
- Depois de mudar o QR code ou o tamanho da flor, confirmar que o QR ainda é lido (ex.: `zxing-cpp`).
