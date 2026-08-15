# Site da Ceres

Site de página única da Ceres, publicado na Vercel no projeto `ceres-tecnologia`.

## Estrutura

```text
index.html      página inteira
style.css       estilos
assets/         fotos, posters e vídeos usados no site
robots.txt      libera indexação e aponta o sitemap
sitemap.xml     URL principal do domínio próprio
vercel.json     headers de segurança e cache
```

## Publicação

```powershell
vercel deploy
vercel deploy --prod
```

O deploy não deve incluir arquivos locais, credenciais, `.env*`, `.git/`, `.vercel/`,
README ou capturas de QA. Ver `.vercelignore`.

## Segurança

- Não versionar tokens, `.env*` ou arquivos gerados pela Vercel CLI.
- Não colocar comentários internos no HTML público.
- Manter legendas públicas genéricas, sem expor função, localização ou disponibilidade de pessoas específicas.
- Endereço, telefone, Instagram e mapa são dados públicos do negócio e fazem parte do SEO local.
