# Fase 2 — Otimização on-page

**Objetivo:** alinhar o conteúdo já existente à **intenção de busca** do público e
recuperar a autoridade interna que foi perdida ao podar links.

**Impacto:** 🔴 Alto · **Esforço:** Baixo · **Depende de:** Fase 1 (parcial)

---

## 2.1 Títulos e meta descriptions por intenção de busca

O `<title>` da home hoje é voltado à marca — *"Mala Pronta — Monte sua mala em
segundos"* — termo que **ninguém pesquisa**. O público busca o problema.

- [x] **Home:** front-load do termo de cabeça. Title aplicado:
  `Lista de Viagem Automática: o que levar na mala | Mala Pronta`
- [x] **Meta description da home:** incluído termo de busca + CTA, sem em-dash,
  dentro de ~155 caracteres.
- [ ] **Artigos:** títulos atuais já são razoáveis (ex. "A ordem certa para guardar
  na mala"). Não alterados nesta rodada — revisar se dados reais (Fase 3) apontarem
  termo-alvo diferente do que já está no título.

### Mapa de termos-alvo (preencher com dados do Search Console depois)

> Nota: itens-mais-subestimados, o-que-levar-para-praia e como-garantir-que-guardou-tudo
> foram excluídos do site. Restam apenas os 2 artigos abaixo.

| Página | Termo-alvo principal | Termos secundários |
|--------|----------------------|--------------------|
| Home | "lista de viagem" / "o que levar na mala" | "app lista de viagem", "checklist de viagem" |
| itens-que-salvam-viagem | "itens essenciais para viagem" | "o que não pode faltar na mala" |
| ordem-para-guardar-na-mala | "como arrumar a mala" | "como organizar a mala", "fazer mala" |

> Os termos acima são hipóteses iniciais; validar/ajustar com dados reais na Fase 3.

---

## 2.2 Reconectar artigos órfãos

**N/A — resolvido por exclusão.** Os 3 artigos que estavam órfãos (subestimados,
praia, checklist final) foram excluídos do site, não apenas desconectados. Não há
mais conteúdo órfão: os 2 artigos restantes (itens-que-salvam-viagem,
ordem-para-guardar-na-mala) se linkam mutuamente e estão na home.

- [x] Garantir que **todo artigo** linke para ao menos 1 outro (hoje cada um linka
  para o único outro artigo restante — distribuição de autoridade trivial com 2 artigos).
- [x] Home lista os artigos atuais (2, não mais 5 — ver nota em 2.1).

---

## 2.3 Datas machine-readable

- [x] Trocar "📅 Junho de 2026" (texto) por `<time datetime="2026-06">Junho de 2026</time>`
  em todos os artigos. Já aplicado durante a Fase 1 nos 2 artigos atuais.
- [x] Consistente com o `datePublished` do schema `Article` (ambos `"2026-06"`).

---

## 2.4 Ajuste de headings e copy para o termo de cabeça

- [x] H1 da home atualizado para incluir o termo de cabeça: "Lista de viagem
  automática: monte sua mala em segundos."
- [x] Mantido **1 H1 por página**; H2/H3 dos artigos já usam variações naturais
  dos termos-alvo (ex. "A ordem certa para guardar na mala") — não alterados.

---

## 2.5 Higiene on-page

- [x] `alt` das imagens: revisado; ícones decorativos com `alt=""`, ícones de loja
  com texto descritivo. Nenhuma alteração necessária.
- [x] Verificado: nenhum link interno aponta para artigo inexistente.
- [x] `meta description` única em cada página (home e os 2 artigos), sem duplicatas.

---

## Critérios de aceite da Fase 2

- [x] Todo `<title>` e `meta description` orientado a intenção, único, e dentro do
  limite de caracteres.
- [x] Nenhum artigo órfão (todos alcançáveis por link interno).
- [x] Datas em `<time datetime>` consistentes com o schema.
- [x] H1/H2 da home contemplam o termo de cabeça.
