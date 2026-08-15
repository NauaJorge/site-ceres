# Site da Ceres · soluções em tecnologia

Site de página única da Ceres. Publicado na Vercel, projeto `ceres-tecnologia`, domínio `cerestecnologia.com.br`.

## Decisões

- Tema escuro dominante porque a marca da Ceres é branca sobre fundo escuro. O preto puro `#0d0d0d` original endurecia a página e foi trocado por um grafite fosco `#23262b`. Todo texto, o amarelo da marca e o wordmark branco ficam acima de 10:1 (AAA).
- Ao mudar `--preto` no `:root`, mudar junto o `rgba()` do `.topo` e o `<meta name="theme-color">` do `index.html`. Esses dois não usam a variável.
- `@cerestec` não foi suposto: aparece como marca d'água nos vídeos que o Bruno enviou.
- São quatro vídeos, todos do Instagram da Ceres:
  - hero: o Bruno na bancada, primeira prova social da página;
  - "Serviço sendo feito": montagem de computador e computador montado, os dois de bancada;
  - "Onde estamos": o Bruno na sala, mostrando a pessoa e o espaço. Fica aqui e não na faixa de bancada porque não é demonstração de serviço, e como terceira coluna não acrescenta altura, já que o cartão do endereço é alto por causa do mapa.
- O botão de play fica no canto inferior esquerdo, não no centro. Centralizado ele caía em cima do assunto de todo quadro: as mãos na bancada num vídeo, o texto da placa que o Bruno segura no outro.
- Mapa e vídeo são opt-in: nada de terceiro e nenhum `.mp4` carrega antes de um clique. O hero carrega só o poster do vídeo, não o vídeo.
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
