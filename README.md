# Site da Ceres · soluções em tecnologia

Site de página única da Ceres, feito para revisão do Bruno antes de qualquer publicação em domínio próprio.

> Esta é uma versão de revisão. O site continua com `noindex`, e o `Disallow: /` do `robots.txt` deve sair junto com o `noindex` somente depois da aprovação do Bruno e da mudança para o domínio próprio. Só então o schema.org passa a valer para busca.

## Decisões

- Tema preto dominante porque a marca da Ceres, no cartão final do vídeo do próprio cliente, é branca sobre preto.
- `@cerestec` não foi suposto: aparece como marca d'água nos vídeos que o Bruno enviou.
- O vídeo do Instagram é vídeo institucional do Bruno, não filmagem de conserto. A legenda anterior descrevia algo que o vídeo não mostrava.
- Os outros dois vídeos são montagem de computador e computador montado. A legenda de cada um diz o serviço mostrado.
- Mapa e vídeo são opt-in: nada de terceiro e nenhum `.mp4` carrega antes de um clique.
- O WhatsApp está ativo. O único ponto de edição para trocar o número fica no fim do `index.html`, na constante `WHATSAPP`.
- Cada cartão de serviço abre o WhatsApp com uma mensagem própria, usando `data-msg`.
- A nota 5,0 com 229 avaliações aparece em destaque na página para conversão. `aggregateRating` não é emitido porque avaliação da própria empresa no site da própria empresa é self-serving e não é elegível a rich result para `LocalBusiness`/`Organization`.

## Dados locais

O endereço confirmado é Rua Cardoso de Morais, 145 - Sl 411 - Bonsucesso, Rio de Janeiro/RJ, CEP 21032-025. Antes do domínio próprio, ainda é preciso o ok do Bruno para o número e a sala.

O link do perfil no Google usa `cid`, que é canônico e permanente. Não é link de busca que expira.

O `geo` foi removido porque a coordenada disponível não é confiável. O mapa passou a abrir por nome do negócio e endereço, e continua opt-in.

O telefone confirmado no perfil é `(21) 99143-7505`. Antes do domínio próprio, ainda é preciso o Bruno confirmar que este telefone é o mesmo número do WhatsApp da Ceres.

O Google Ads bloqueia anúncio pago de assistência técnica terceirizada ao consumidor. Isso torna o orgânico e o perfil local o canal viável no Google, então o `LocalBusiness` e o NAP consistente têm peso maior neste site.

O domínio não foi perdido: a empresa perdeu o site publicado na Wix, não o domínio. Não é preciso comprar domínio novo; basta apontar o DNS ou transferir.

## O que falta

| Item | Por que falta |
|---|---|
| Logo em arquivo | Existe cartão de marca no fim do vídeo, mas não arquivo próprio |

## Confirmar antes do domínio próprio

- Confirmar com o Bruno que `(21) 99143-7505` é o mesmo número do WhatsApp da Ceres.
- Confirmar com o Bruno o número e a sala do endereço antes da publicação em domínio próprio.

## Estrutura

```text
index.html      página inteira
style.css       estilo
assets/         fotos, posters e vídeos reais da Ceres
robots.txt      bloqueio de indexação enquanto é rascunho
```

## Como abrir

Abra `index.html` no navegador. Não precisa instalar nada.
