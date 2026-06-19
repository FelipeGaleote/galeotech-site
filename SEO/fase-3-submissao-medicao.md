# Fase 3 — Submissão e medição

**Objetivo:** colocar o site nos olhos do Google e começar a medir, para que as
decisões de conteúdo da Fase 4 sejam baseadas em dados reais — não em hipóteses.

**Impacto:** 🟡 Médio (mas indispensável) · **Esforço:** Baixo · **Depende de:** Fases 1 e 2

---

## 3.1 Google Search Console (GSC)

- [ ] Criar/verificar a propriedade no Search Console (verificação via DNS ou
  tag HTML no `<head>`).
- [ ] Enviar o `sitemap.xml` (criado na Fase 1.2).
- [ ] Solicitar indexação das páginas principais (URL Inspection → Request Indexing).
- [ ] Conferir relatório de **Cobertura/Indexação**: garantir que home + 5 artigos
  estão indexados, sem erros.
- [ ] Conferir relatório de **Enhancements** para validar os rich results
  (FAQ, Article, Breadcrumb) reconhecidos.

---

## 3.2 Validação técnica

- [ ] Rodar todas as páginas no
  [Rich Results Test](https://search.google.com/test/rich-results).
- [ ] Rodar a home no [PageSpeed Insights](https://pagespeed.web.dev/) — registrar
  baseline de Core Web Vitals (provavelmente já bom: site estático + lazy load).
- [ ] Validar `sitemap.xml` e `robots.txt` (sem 404, sem bloqueios indevidos).
- [ ] Conferir que o canonical de cada página aponta para a URL correta.

---

## 3.3 Analytics

- [ ] Confirmar se há analytics no site (GA4 ou alternativa). Se não houver,
  decidir se adiciona — necessário para medir tráfego→conversão (clique no
  "Baixar grátis").
- [ ] Definir o **evento de conversão** (clique para a loja) para medir a
  qualidade do tráfego de SEO vs. ASO.
> **Decisão pendente do usuário:** quer instrumentar analytics no site? Qual
> ferramenta? (Impacta privacidade/política — já existe `privacy.html`.)

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
