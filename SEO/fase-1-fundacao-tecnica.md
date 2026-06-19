# Fase 1 — Fundação técnica

**Objetivo:** dar ao Google e às LLMs a infraestrutura para descobrir, entender e
confiar no site. É a fase de maior impacto e mexe quase nada no conteúdo.

**Impacto:** 🔴 Alto · **Esforço:** Médio · **Pré-requisito de:** Fase 3

---

## 1.1 Dados estruturados (JSON-LD)

O site não tem **nenhum** `application/ld+json`. É o item mais crítico para rich
results no Google e para citação por IA.

### Home (`malapronta/index.html`)

- [x] **`MobileApplication`** — faz o app ser entendido como produto/app.
```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "MobileApplication",
  "name": "Mala Pronta",
  "operatingSystem": "ANDROID, IOS",
  "applicationCategory": "TravelApplication",
  "description": "App que cria automaticamente a lista de itens ideal para a sua viagem.",
  "offers": { "@type": "Offer", "price": "0", "priceCurrency": "BRL" },
  "installUrl": "https://play.google.com/store/apps/details?id=com.galeotech.malapronta"
  /* adicionar "aggregateRating" se houver avaliações nas lojas — ver 1.5 */
}
</script>
```

- [x] **`FAQPage`** — já existem 6 perguntas em HTML na home; marcá-las habilita
  rich snippet de FAQ e é o formato que LLMs citam. Replicar as 6 perguntas/respostas
  atuais no schema (manter sincronizado com o HTML).
```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    { "@type": "Question", "name": "O app é gratuito?",
      "acceptedAnswer": { "@type": "Answer", "text": "Sim, o Mala Pronta é totalmente gratuito." } }
    /* ... repetir para as 6 perguntas do FAQ ... */
  ]
}
</script>
```

- [x] **`Organization`** (Galeo Tech) — consolida a entidade entre os 3 sites.
```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "name": "Galeo Tech",
  "url": "https://galeotech.com.br",
  "logo": "https://.../assets/icon.png"
}
</script>
```

### Cada artigo (`malapronta/artigos/*.html`)

> Nota: dos 5 artigos originais, 3 foram excluídos do site (itens-mais-subestimados,
> o-que-levar-para-praia, como-garantir-que-guardou-tudo). Restam 2: itens-que-salvam-viagem
> e ordem-para-guardar-na-mala. Os itens abaixo foram aplicados a esses 2.

- [x] **`Article`** — com `headline`, `datePublished`, `author`, `publisher`
  (Galeo Tech), `image`. A data textual ("Junho de 2026") agora também tem
  `<time datetime="2026-06">` legível por máquina.
- [x] **`BreadcrumbList`** — o breadcrumb visual já existe; marcar habilita
  breadcrumb nos resultados.
```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Article",
  "headline": "A ordem certa para guardar na mala",
  "description": "...meta description do artigo...",
  "datePublished": "2026-06-01",
  "author": { "@type": "Organization", "name": "Mala Pronta" },
  "publisher": {
    "@type": "Organization", "name": "Galeo Tech",
    "logo": { "@type": "ImageObject", "url": "https://.../assets/icon.png" }
  }
}
</script>
```

> ⚠️ Definir antes a **URL canônica de produção** (domínio final). Ver bloqueio em 1.6.

---

## 1.2 sitemap.xml

- [x] Criar `malapronta/sitemap.xml` com a home + 2 artigos atuais, cada um com `<lastmod>`.
- [x] Sem sitemap, a descoberta depende só de links internos — e a linkagem foi
  podada (3 artigos órfãos), então isso é importante agora.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url><loc>https://.../malapronta/</loc><lastmod>2026-06-19</lastmod></url>
  <url><loc>https://.../malapronta/artigos/itens-que-salvam-viagem.html</loc></url>
  <!-- ... demais artigos ... -->
</urlset>
```

---

## 1.3 robots.txt

- [x] Criar `robots.txt` permitindo crawl e apontando para o sitemap.
```
User-agent: *
Allow: /
Sitemap: https://malapronta.galeotech.com.br/sitemap.xml
```
> Criado em `malapronta/robots.txt` — Cloudflare Pages serve esse projeto na raiz
> de `malapronta.galeotech.com.br`, então o arquivo já fica na raiz do domínio.

---

## 1.4 Canonical + Open Graph em todas as páginas

- [x] Adicionar `<link rel="canonical" href="...">` em **todas** as páginas
  (home + 2 artigos). Previne duplicação e diluição.
- [x] Adicionar Open Graph completo nos **2 artigos** (hoje só a home tem, e
  parcial): `og:title`, `og:description`, `og:type=article`, `og:url`, `og:image`.
- [x] Adicionar `og:image` na home (hoje ausente) — usar print do app ou banner.
- [x] Adicionar Twitter Cards (`twitter:card=summary_large_image`) — relevante p/
  compartilhamento (WhatsApp/Instagram são o canal nº 1 do público BR).

---

## 1.5 Prova social (se disponível)

- [ ] Se o app já tem avaliações nas lojas, adicionar `aggregateRating` ao
  `MobileApplication`. Aumenta CTR e probabilidade de citação por IA.
  > **Decisão pendente:** confirmar nota e nº de avaliações atuais nas lojas.

---

## 1.6 Bloqueios / decisões pendentes

- [x] **Definir o domínio canônico de produção.** Resolvido: migração para Cloudflare
  concluída, `malapronta.galeotech.com.br` é a URL de produção usada em todo
  schema/canonical/sitemap/OG.

---

## Critérios de aceite da Fase 1

- [ ] Toda página tem ao menos um bloco JSON-LD válido (testar no
  [Rich Results Test](https://search.google.com/test/rich-results)).
- [ ] `sitemap.xml` e `robots.txt` acessíveis e válidos.
- [ ] Toda página com `canonical` + OG completo + Twitter Card.
- [ ] Zero erros no Rich Results Test para FAQPage, Article e MobileApplication.
