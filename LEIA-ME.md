# Site Charme Cosméticos

Página de links da Charme Cosméticos, perfumaria de perfumes árabes importados e Brand Collection,
no Shopping Popular, em Cuiabá, MT. HTML, CSS e JavaScript puros: não precisa instalar nada.
Para ver no computador, abra `site/index.html` no navegador.

## Pastas

```
00site/
  LEIA-ME.md                     este guia (não vai para a hospedagem)
  site/                          o site: é exatamente o que vai para a HostGator
    index.html                   página e textos em português
    .htaccess                    compressão, cache e segurança na HostGator (arquivo oculto)
    llms.txt                     resumo da loja para IAs (ChatGPT, Claude, Perplexity)
    robots.txt                   libera o site para o Google
    assets/css/style.css         visual: cores, fontes, espaçamentos
    assets/js/i18n.js            textos em inglês
    assets/js/main.js            número do WhatsApp, idioma, tema claro/escuro, cursor, animações
    assets/img/                  logo, flor, ícones e banners (JPEG + WebP)
  originais/                     imagens em alta resolução, para refazer banners e logo
  publicar/
    charme-cosmeticos-site.zip   a pasta site/ compactada, pronta para enviar
```

## Onde trocar cada coisa

| O quê | Onde |
|---|---|
| Textos em português | `site/index.html`. Os blocos editáveis têm comentário `EDITAR`. |
| Textos em inglês | `site/assets/js/i18n.js`. Cada chave corresponde a um `data-i18n="…"` no HTML. |
| Número do WhatsApp | `site/assets/js/main.js`, no topo: `WHATSAPP = '5565984598834'`. Vale para todos os botões. |
| Mensagem pronta de cada botão | `site/index.html`, atributo `data-wa="…"` do botão. |
| E-mail e avaliação no Google | `site/index.html`, seção `REDES SOCIAIS` (ainda sem link). |
| Banners | Cada banner tem 4 arquivos em `site/assets/img`: `banner-N.jpg`, `banner-N.webp` (1200 × 540 px), `banner-N-800.jpg` e `banner-N-800.webp` (800 × 360 px). Troque os 4. |
| Logo e flor | `site/assets/img/logo.png` e `flor.png` (brancos, fundo transparente). |
| Ícone da aba | `site/assets/img/favicon.png` (64 × 64) e `apple-touch-icon.png` (180 × 180). |
| Mapa | `site/index.html`, seção `MAPA`. Como trocar o local está no comentário. |
| Palavras da faixa rolando | `site/index.html`, em `.ticker`. Escreva cada palavra uma vez só. |
| Cores da marca | `site/assets/css/style.css`, tokens `--brand*` no topo. Rosa `#b80259` e rosa claro `#e3609f`. |
| Resumo para IAs | `site/llms.txt`. Atualize quando mudar produtos, links ou contato. |

## Regras

- Se mudar um texto em português, mude também o inglês com a mesma chave no `i18n.js`.
- Nomes de produtos e marcas não são traduzidos.
- O idioma e o tema escolhidos ficam salvos no navegador de cada visitante.
- Depois de qualquer mudança, gere o zip de novo (veja abaixo).

## Publicar na HostGator

1. No cPanel, abra o **Gerenciador de Arquivos** e entre na pasta `public_html` (ou na pasta do domínio).
2. Clique em **Carregar** e envie `publicar/charme-cosmeticos-site.zip`.
3. Clique com o botão direito no zip > **Extrair**. Depois apague o zip do servidor.
4. Confira que `index.html`, `.htaccess`, `llms.txt`, `robots.txt` e a pasta `assets` ficaram direto dentro de `public_html`.
   O `.htaccess` fica oculto: ative "Mostrar arquivos ocultos" em Configurações.
5. Ative o SSL grátis do domínio no cPanel. Depois, no `.htaccess`, tire o `#` das 3 últimas linhas para forçar `https://`.
6. No `index.html`, troque `SEUDOMINIO` pelo endereço do site nas 3 linhas comentadas do topo e tire o comentário.
   Sem isso, a imagem não aparece quando o link é compartilhado no WhatsApp.
7. Abra o site no celular e teste os botões.

## Gerar o zip de novo

No Terminal:

```
cd "/Users/matheus/002 SITE/00site/site" && rm -f ../publicar/charme-cosmeticos-site.zip && zip -r -X ../publicar/charme-cosmeticos-site.zip . -x "*.DS_Store"
```
