# Concorso — site

Site estático. Sem build, sem dependência. Basta subir os arquivos.

## Publicar no GitHub Pages

1. Crie um repositório novo no GitHub (público, se estiver no plano gratuito).
2. Envie **todos os arquivos desta pasta na raiz do repositório** — não dentro de subpasta.
3. No repositório: **Settings → Pages**.
4. Em *Source*, escolha **Deploy from a branch**; em *Branch*, escolha `main` e a pasta `/ (root)`. Salve.
5. Aguarde de um a dois minutos. O site sobe em `https://SEUUSUARIO.github.io/NOMEDOREPO/`.

## Domínio próprio

O arquivo `CNAME` já está preenchido com `concorso.com.br`.

- **Se o domínio for outro**, edite o `CNAME` e escreva só o domínio, sem `https://` e sem barra.
- **Se ainda não tiver domínio**, apague o arquivo `CNAME` — senão o Pages tenta usar um domínio que não existe e o site não abre.

No registrador (registro.br, por exemplo), aponte:

| Tipo | Nome | Valor |
|---|---|---|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | SEUUSUARIO.github.io |

Depois volte em **Settings → Pages** e marque **Enforce HTTPS**. O certificado leva alguns minutos.

## Antes de publicar

- Troque `concorso.com.br` pelo domínio real em `index.html` (tags `og:url`, `og:image`, `canonical`), em `robots.txt` e em `sitemap.xml`. Se o endereço estiver errado, a prévia de compartilhamento no WhatsApp não carrega a imagem.
- As fotos da Ferrari estão embutidas no `index.html` em base64. Para trocar de carro, substitua os blocos `data:image/webp;base64,...`.
- Fotos e textos são de demonstração. Nada aqui é uma oferta real.

## Endereços internos

O site é uma página só com rotas por hash, então cada tela tem link próprio:

- `/` — entrada
- `/#/inicio` — processo
- `/#/catalogo` — catálogo
- `/#/lote` — lote em apresentação
- `/#/arquivo` — arquivo
- `/#/acesso` — solicitação de acesso

## Arquivos

| Arquivo | Para que serve |
|---|---|
| `index.html` | O site inteiro, com as fotos embutidas |
| `404.html` | Devolve para a home em endereço inexistente |
| `favicon.ico` `favicon.svg` `favicon-16/32/48.png` | Ícone na aba do navegador |
| `apple-touch-icon.png` | Ícone ao salvar na tela inicial do iPhone |
| `icon-192.png` `icon-512.png` `icon-maskable-512.png` | Ícones de Android e instalação |
| `safari-pinned-tab.svg` | Ícone monocromático do Safari |
| `og-image.png` | Prévia ao compartilhar em WhatsApp, LinkedIn, X |
| `site.webmanifest` | Permite instalar como aplicativo |
| `robots.txt` `sitemap.xml` | Indexação em buscadores |
| `CNAME` | Domínio próprio |
| `.nojekyll` | Impede o GitHub de processar os arquivos |

## Formulário

Os campos da tela de acesso ainda não enviam nada — são visuais. Para funcionar sem servidor, aponte para Formspree, Tally ou Google Forms: basta trocar o `onclick` do botão pelo endereço do serviço.
