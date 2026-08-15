# Site da Ceres · soluções em tecnologia

Site de página única da Ceres. Publicado na Vercel, projeto `ceres-tecnologia`, domínio `cerestecnologia.com.br`.

## Decisões

- Tema escuro dominante porque a marca da Ceres é branca sobre fundo escuro. O preto puro `#0d0d0d` original endurecia a página e foi trocado por um grafite fosco `#23262b`. Todo texto, o amarelo da marca e o wordmark branco ficam acima de 10:1 (AAA).
- Ao mudar `--preto` no `:root`, mudar junto o `rgba()` do `.topo` e o `<meta name="theme-color">` do `index.html`. Esses dois não usam a variável.
- `@cerestec` não foi suposto: aparece como marca d'água nos vídeos que o Bruno enviou.
- São quatro vídeos, todos do Instagram da Ceres:
  - hero: o Bruno na bancada, primeira prova social da página;
  - "Serviço sendo feito": montagem de computador, computador montado e o Bruno na sala, os três com a mesma largura.
- Os três vídeos ficam a 300px. Vídeo 9:16 ganha 1,8px de altura para cada 1px de largura, então a largura é o único controle real sobre a altura da seção. A 300px a fileira ocupa 940px dos 1120px da faixa: enche a largura sem a seção voltar aos 900px que tinha antes.
- Nos breakpoints a fileira nunca cai para duas colunas, senão o terceiro vídeo ficaria sozinho na segunda linha. Até 920px os três encolhem juntos; abaixo de 640px empilham em coluna única a 270px.
- A linha de apoio da seção diz "gravado dentro da Ceres", e não "na bancada", porque o vídeo da sala não é de bancada.
- O botão de play fica no canto inferior esquerdo, não no centro. Centralizado ele caía em cima do assunto de todo quadro: as mãos na bancada num vídeo, o texto da placa que o Bruno segura no outro.
- Vídeo é opt-in: nenhum `.mp4` carrega antes de um clique. O hero carrega só o poster, não o vídeo.
- O mapa **não** é mais opt-in. Por decisão do cliente ele vem carregado, sem clique. Isso significa que o Google recebe uma requisição de todo visitante que rolar até "Onde estamos". O `loading="lazy"` segura a requisição até a seção chegar perto da tela, então não pesa no primeiro carregamento.
- O `frame-src` do CSP libera só `https://www.google.com`. O embed responde com um redirect, mas o destino continua no mesmo host (`/maps/embed`), então a política cobre. Se o endereço do embed mudar de host, o mapa quebra e é preciso ajustar o `vercel.json`.
- As fotos da galeria foram recortadas para 3:4 no arquivo-fonte. Antes eram proporções misturadas forçadas no mesmo slot por `object-fit: cover`, e o corte caía em lugar errado.
- O WhatsApp está ativo. O único ponto de edição para trocar o número fica no fim do `index.html`, na constante `WHATSAPP`.
- Cada cartão de serviço abre o WhatsApp com uma mensagem própria, usando `data-msg`.
- A nota 5,0 com 229 avaliações aparece em destaque na página para conversão. `aggregateRating` não é emitido porque avaliação da própria empresa no site da própria empresa é self-serving e não é elegível a rich result para `LocalBusiness`/`Organization`.

## Dados locais

O endereço é Rua Cardoso de Morais, 145 - Sl 411 - Bonsucesso, Rio de Janeiro/RJ, CEP 21032-025, confirmado pelo Bruno.

O telefone é `(21) 99143-7505`, confirmado pelo Bruno como o mesmo número do WhatsApp.

O link do perfil no Google usa `cid`, que é canônico e permanente. Não é link de busca que expira.

O `geo` foi removido porque a coordenada disponível não é confiável. O mapa abre por nome do negócio e endereço, e continua opt-in.

O Google Ads bloqueia anúncio pago de assistência técnica terceirizada ao consumidor. Isso torna o orgânico e o perfil local o canal viável no Google, então o `LocalBusiness` e o NAP consistente têm peso maior neste site.

O domínio antigo era `cerestecnologia.com`, na Wix. Foi comprado um domínio novo no Registro.br, `cerestecnologia.com.br`, e o site passou a ser servido pela Vercel.

## Publicação

O deploy é pela Vercel, projeto `ceres-tecnologia` no escopo `naua-jorge-s-projects`.

```
vercel deploy          # preview
vercel deploy --prod   # produção
```

DNS no Registro.br:

```
@      A       76.76.21.21
www    CNAME   cname.vercel-dns.com.
```

O `vercel.json` define CSP, HSTS e cache. O `.vercelignore` mantém `.qa/` e este README fora do deploy.

## Estrutura

```text
index.html      página inteira
style.css       estilo
assets/         fotos, posters e vídeos reais da Ceres
robots.txt      libera indexação e aponta o sitemap
sitemap.xml     uma URL, o domínio próprio
vercel.json     headers de segurança e cache
.qa/            capturas de revisão, fora do deploy e do git
```

As capturas em `.qa/` são de uma versão anterior da página e não servem de referência visual.

## Como abrir

Abra `index.html` no navegador. Não precisa instalar nada.
