# Fase 2 — Otimização on-page

**Objetivo:** alinhar o conteúdo já existente à **intenção de busca** do público e
recuperar a autoridade interna que foi perdida ao podar links.

**Impacto:** 🔴 Alto · **Esforço:** Baixo · **Depende de:** Fase 1 (parcial)

---

## 2.1 Títulos e meta descriptions por intenção de busca

O `<title>` da home hoje é voltado à marca — *"Mala Pronta — Monte sua mala em
segundos"* — termo que **ninguém pesquisa**. O público busca o problema.

- [ ] **Home:** front-load do termo de cabeça. Ex.:
  `Lista de Viagem Automática: o que levar na mala | Mala Pronta`
- [ ] **Meta description da home:** incluir termos de busca + CTA, dentro de ~155
  caracteres. Remover o em-dash (já há histórico de limpeza de "—").
- [ ] **Artigos:** já estão razoáveis (ex. "O que levar para praia: lista completa").
  Revisar para garantir que o termo-alvo esteja no início do `<title>`.

### Mapa de termos-alvo (preencher com dados do Search Console depois)

| Página | Termo-alvo principal | Termos secundários |
|--------|----------------------|--------------------|
| Home | "lista de viagem" / "o que levar na mala" | "app lista de viagem", "checklist de viagem" |
| itens-que-salvam-viagem | "itens essenciais para viagem" | "o que não pode faltar na mala" |
| ordem-para-guardar-na-mala | "como arrumar a mala" | "como organizar a mala", "fazer mala" |
| o-que-levar-para-praia | "o que levar para praia" | "lista praia", "mala de praia" |
| itens-mais-subestimados | "itens subestimados viagem" | — |
| como-garantir-que-guardou-tudo | "checklist de viagem" | "como não esquecer nada na viagem" |

> Os termos acima são hipóteses iniciais; validar/ajustar com dados reais na Fase 3.

---

## 2.2 Reconectar artigos órfãos

3 dos 5 artigos ("subestimados", "praia", "checklist final") só são acessíveis por
URL direta — foram desconectados da home e dos cross-links durante a revisão
editorial. Enquanto órfãos, vão indexar mal.

- [ ] Reconectar os 3 artigos assim que forem revisados (home + cross-links).
- [ ] Garantir que **todo artigo** linke para ao menos 2 outros (distribui autoridade).
- [ ] Garantir que a home volte a listar os 5 artigos (ou um índice de blog).
> **Decisão pendente do usuário:** confirmar quando cada artigo está revisado e
> liberado para ser reconectado. Hoje a restrição de cross-link é intencional.

---

## 2.3 Datas machine-readable

- [ ] Trocar "📅 Junho de 2026" (texto) por `<time datetime="2026-06">Junho de 2026</time>`
  em todos os artigos. Frescor de conteúdo é sinal de ranking e de confiança p/ LLM.
- [ ] Manter consistente com o `datePublished` do schema `Article` (Fase 1.1).

---

## 2.4 Ajuste de headings e copy para o termo de cabeça

- [ ] Não existe alvo claro para a busca comercial principal ("lista de viagem").
  A home pode assumir esse papel: incluir o termo de forma natural no H1/H2 e na
  primeira dobra, sem sacrificar a clareza atual.
- [ ] Manter **1 H1 por página** (já está correto) e garantir que H2/H3 dos artigos
  usem variações dos termos-alvo.

---

## 2.5 Higiene on-page

- [ ] `alt` das imagens: já bom; revisar para incluir termo-alvo quando natural.
- [ ] Verificar que nenhum link interno aponta para artigo inexistente.
- [ ] Garantir `meta description` única em cada página (sem duplicatas).

---

## Critérios de aceite da Fase 2

- [ ] Todo `<title>` e `meta description` orientado a intenção, único, e dentro do
  limite de caracteres.
- [ ] Nenhum artigo órfão (todos alcançáveis por link interno) — **após** liberação
  editorial.
- [ ] Datas em `<time datetime>` consistentes com o schema.
- [ ] H1/H2 da home contemplam o termo de cabeça.
