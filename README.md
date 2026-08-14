# Site da Ceres · soluções em tecnologia

Site institucional de página única da **Ceres**, assistência técnica de computadores, notebooks e
celulares. Feito pela [SoftWave Soluções](https://instagram.com/softwavesolucoes).

> **Esta é uma versão de revisão.** Foi publicada para o Bruno, dono da Ceres, ver a estrutura e o
> visual antes de qualquer coisa ir ao ar em domínio próprio. Os blocos marcados em amarelo na
> página ainda esperam informação da Ceres, e a página está com `noindex` para não aparecer em
> busca enquanto estiver incompleta.

## Contexto

A Ceres perdeu o domínio que estava na Wix e ficou sem site. O Instagram
[@cerestec](https://instagram.com/cerestec) continua ativo e os vídeos mandam a pessoa para o
"link da bio", que hoje não tem destino próprio. Este site existe para ser esse destino.

## Decisões de projeto

- **Objetivo único:** levar a pessoa ao WhatsApp. Sem carrinho, sem login, sem formulário longo.
- **Público:** boa parte dos clientes tem pouca familiaridade com tecnologia. Por isso a linguagem
  é simples, o botão é grande e não há jargão técnico em lugar nenhum.
- **Preto e amarelo:** identidade que a Ceres já usa no Instagram. Preto domina, amarelo é ação e
  destaque pontual. Texto sobre amarelo é sempre escuro, e o foco do teclado não depende só de cor.
- **Sem framework e sem build.** HTML, CSS e nada mais. Abre rápido, é fácil de hospedar em
  qualquer lugar e qualquer pessoa consegue mexer depois.
- **Sem dependência externa.** Nenhuma fonte, ícone ou script vindo de CDN. Os ícones são SVG
  escritos no próprio HTML. A página não quebra se um serviço de terceiro cair.
- **Mobile primeiro.** Quem procura conserto de celular procura pelo celular.

## Nada aqui é inventado

Regra do projeto: nenhuma informação da Ceres foi escrita por suposição.

- As fotos são reais, enviadas pelo Bruno.
- Os serviços listados são os que a Ceres confirmou que faz.
- **Não há avaliação escrita no site.** As avaliações da Ceres no Google são boas e verdadeiras, e
  é justamente por isso que nenhuma foi redigida por conta própria. Elas entram com o texto real,
  o nome de quem escreveu, a nota e o link do perfil.
- Endereço, horário, telefone e WhatsApp aparecem como pendência até serem confirmados.

## O que falta para publicar de verdade

| # | O que falta | Onde entra |
|---|---|---|
| 1 | Número de WhatsApp | Botão do topo, botão flutuante e rodapé |
| 2 | Endereço completo | Seção "Onde estamos", mapa e dados de negócio local |
| 3 | Horário de funcionamento | Seção "Onde estamos" |
| 4 | Texto das avaliações do Google, com nome, nota e link do perfil | Seção "Quem já foi atendido" |
| 5 | Confirmar se atende presencial, remoto ou os dois, e se o orçamento sai antes do conserto | Passo 2 de "Como funciona" |
| 6 | Logo em arquivo, de preferência vetor ou PNG com fundo transparente | Topo e rodapé |
| 7 | E-mail de contato, se quiser que apareça | Rodapé |

Quando esses itens chegarem, sai o `noindex`, entram os dados de negócio local para busca e o site
pode ir para domínio próprio.

## Estrutura

```
index.html      página inteira
style.css       estilo
assets/         fotos reais da Ceres
robots.txt      bloqueio de indexação enquanto é rascunho
```

## Como abrir

Baixe e abra o `index.html` no navegador. Não precisa instalar nada.
