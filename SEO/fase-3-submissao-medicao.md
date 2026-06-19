# Fase 3 — Submissão e medição

**Objetivo:** colocar o site nos olhos do Google e começar a medir, para que as
decisões de conteúdo da Fase 4 sejam baseadas em dados reais — não em hipóteses.

**Impacto:** 🟡 Médio (mas indispensável) · **Esforço:** Baixo · **Depende de:** Fases 1 e 2

---

## 3.1 Google Search Console (GSC)

- [x] Propriedade verificada no Search Console.
- [x] `sitemap.xml` enviado (`https://malapronta.galeotech.com.br/sitemap.xml`) —
  status "Processado", 3 páginas encontradas.
- [x] Indexação solicitada para as 3 URLs (home + 2 artigos) via URL Inspection.
- [ ] Conferir relatório de **Cobertura/Indexação** (aguardar alguns dias após
  a solicitação de indexação).
- [ ] Conferir relatório de **Enhancements** para validar os rich results
  (FAQ, Article, Breadcrumb) reconhecidos.

---

## 3.2 Validação técnica

- [ ] Rodar todas as páginas no
  [Rich Results Test](https://search.google.com/test/rich-results) — solicitado,
  resultado ainda pendente.
- [ ] Rodar a home no [PageSpeed Insights](https://pagespeed.web.dev/) — registrar
  baseline de Core Web Vitals (provavelmente já bom: site estático + lazy load).
- [ ] Validar `sitemap.xml` e `robots.txt` (sem 404, sem bloqueios indevidos).
- [ ] Conferir que o canonical de cada página aponta para a URL correta.

---

## 3.3 Analytics

- [x] GA4 instalado nas 3 páginas do Mala Pronta (home + 2 artigos), propriedade
  "Mala Pronta" (measurement ID `G-0Y0J58BNZZ`).
- [x] Evento de conversão: Enhanced Measurement do GA4 rastreia automaticamente
  cliques em links externos (outbound clicks), o que já cobre os botões de
  Google Play/App Store sem precisar de evento customizado.
- [x] `privacy.html` atualizado para mencionar o uso do Google Analytics no site.

---

## 3.4 Acompanhamento (rotina)

- [ ] Definir cadência de revisão do GSC (sugestão: mensal nos primeiros 6 meses).
- [ ] A cada revisão, anotar no [fase-4](fase-4-conteudo-crescimento.md):
  - Termos que começaram a aparecer (Impressões > 0)
  - Termos em posição 5-20 (oportunidade de otimizar e subir)
  - Páginas com impressão mas CTR baixo (revisar title/description)

---

## Critérios de aceite da Fase 3

- [ ] Propriedade verificada no GSC com sitemap enviado e aceito.
- [ ] Home + 5 artigos indexados, sem erros de cobertura.
- [ ] Rich results validados sem erro.
- [ ] Baseline de tráfego e (se aplicável) de conversão registrado.
