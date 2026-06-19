# Plano de SEO — Mala Pronta

Documentação do trabalho de SEO para o site do Mala Pronta, com o objetivo de
**atrair tráfego qualificado por busca orgânica** (Google) e **fortalecer a
presença em respostas de LLMs**.

## Contexto

- O app já tem **ASO bem otimizado** (~180 installs orgânicos/mês via lojas).
  SEO de site é o canal complementar de **topo de funil**: captura quem pesquisa
  o problema ("o que levar na viagem") antes de procurar um app.
- A landing page **já converte bem** quem chega. O gargalo hoje é a **descoberta**
  (indexação + ranqueamento), não a conversão.
- Já existem **5 artigos de blog revisados** em `malapronta/artigos/`, além da home.

## Expectativa realista

- Tráfego de SEO é maior em volume, porém **menos qualificado** que o de ASO
  (topo de funil). A conversão visitante→install é baixa, compensada pelo volume.
- **Prazo:** primeiros sinais em 2-3 meses; tração real em 6+ meses. Domínio novo,
  sem backlinks, leva tempo para ganhar confiança.
- A maior parte do trabalho restante é **técnico/mecânico**, não reescrita de
  conteúdo — baixo esforço para destravar o que já existe.

## Fases

| Fase | Arquivo | Foco | Esforço | Impacto |
|------|---------|------|---------|---------|
| 1 | [fase-1-fundacao-tecnica.md](fase-1-fundacao-tecnica.md) | Schema, sitemap, robots, canonical, OG | Médio | 🔴 Alto |
| 2 | [fase-2-otimizacao-onpage.md](fase-2-otimizacao-onpage.md) | Títulos/descriptions por intenção, links internos, datas | Baixo | 🔴 Alto |
| 3 | [fase-3-submissao-medicao.md](fase-3-submissao-medicao.md) | Search Console, sitemap, acompanhamento | Baixo | 🟡 Médio |
| 4 | [fase-4-conteudo-crescimento.md](fase-4-conteudo-crescimento.md) | Conteúdo long-tail, backlinks, escala | Alto (contínuo) | 🟡 Médio/longo prazo |

> **Ordem recomendada:** 1 → 2 → 3 antes de iniciar a 4. As fases 1 e 2 destravam
> indexação e elegibilidade a rich results / citação por IA com mínimo impacto no
> conteúdo já revisado.

## Estado atual do site (auditoria — jun/2026)

**Bom:**
- HTML semântico, `lang="pt-BR"`, hierarquia de headings correta (1 H1/página)
- `alt` descritivo, `loading="lazy"`, `fetchpriority="high"` no hero
- URLs limpas e descritivas nos artigos
- Breadcrumb visual presente

**Faltando (oportunidades):**
- ❌ Nenhum dado estruturado (JSON-LD) em nenhuma página
- ❌ Sem `sitemap.xml` e sem `robots.txt`
- ❌ Sem `<link rel="canonical">`
- ❌ Open Graph só na home; artigos sem OG e sem `og:image`
- ❌ Títulos/descriptions voltados à marca, não à intenção de busca
- ❌ Datas não machine-readable (`<time datetime>` ausente)
- ⚠️ 3 dos 5 artigos órfãos (sem links internos da home/entre artigos)

## Convenção

Cada arquivo de fase usa checklists `- [ ]` para acompanhar o progresso. Marcar
`- [x]` conforme concluído. Itens com snippet de código são prontos para colar.
