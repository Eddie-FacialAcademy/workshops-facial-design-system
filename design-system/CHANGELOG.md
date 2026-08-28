# Changelog — Workshops Facial Design System

Todas as mudanças relevantes deste design system são registradas aqui.
O formato segue [Keep a Changelog](https://keepachangelog.com/pt-BR/1.1.0/) e o
versionamento segue [SemVer](https://semver.org/lang/pt-BR/):

- **MAJOR** — muda ou remove um token/API público (quebra compatibilidade).
- **MINOR** — adiciona de forma retrocompatível (novo componente/token/variante).
- **PATCH** — correções que não mudam a API (bug, contraste, ajuste fino).

---

## [Não lançado]

_Nada pendente no momento._

## [1.2.2] — 2026-08-28
### Corrigido
- Documentação de cor "Secundário": o swatch da seção Cores e a tabela de
  Color Styles mostravam um valor que não era o token `--mut` real do tema
  (drift herdado do molde). Agora exibem o valor vivo do token nos dois temas.
- Grafia: "antiimproviso" corrigido para "anti-improviso" e "pra o" para
  "para o" na seção Voz e tom.

## [1.2.1] — 2026-08-28
### Alterado
- Menu "Design systems" agora inclui a Fotografia na HOF, nova marca do
  ecossistema (sete marcas no seletor).

## [1.2.0] — 2026-08-25
### Adicionado
- Favicon da página: badge arredondado na cor da marca com o ícone oficial do
  logo em branco, embutido como SVG data-URI no `<head>` (a página segue
  self-contained, sem requisição extra).

## [1.1.1] — 2026-08-25
### Corrigido
- Anel de foco em duas camadas: `--focus` agora é `0 0 0 2px var(--bg),
  0 0 0 4px var(--focus-ring)`, com `--focus-ring` sólido por tema (escuro
  `#C879FF`, claro `#7A1AD6`). O anel antigo (accent com 55% de opacidade, valor
  único pros dois temas) media abaixo de 3:1 contra os fundos e reprovava a
  WCAG 1.4.11. Sincronizado em showcase, CSS do pacote, tokens.json e docs.
- Drift de reskin corrigido: o `tokens.json` e o bloco "Tokens" do showcase
  traziam o valor de foco lilás da Facial; agora usam o violeta da marca.
- Guard de alto contraste (`forced-colors`) com `outline` `!important`: o
  indicador de foco não é mais anulado pelo `outline:none` dos componentes.

## [1.1.0] — 2026-08-25
### Adicionado
- Menu "Design systems" na navegação do showcase: acesso direto aos design
  systems das seis marcas (Facial Academy, Facial Class, Facial Scale,
  Workshops Facial, Corporal Academy, Corporal Class), com a marca atual
  sinalizada e acordeão próprio no menu mobile.

## [1.0.0] — 2026-06-19

Primeira versão do Workshops Facial, derivado do Facial Academy: paleta vívida
violeta+magenta, logo próprio e domínio presencial. Reúne fundações, camada de
produto e camada de maturidade/processo.

### Fundações
- Arquitetura de tokens em 3 camadas (`primitive → semantic/intent → component`).
- Cores, gradientes e tipografia (Silka, com fallback `system-ui`) da identidade violeta+magenta da marca.
- Theming **dark/light** com paridade total e contraste **WCAG AA** em todos os textos.
- Numerais com `tabular-nums` global.
- Tokens de fundação: opacidade, border-width, blur, breakpoints/grid, elevação
  semântica (surface → modal), sizing/touch ≥ 44px e aspect-ratio.

### Produto
- **Forms:** input, textarea, select, checkbox/radio/toggle, helper, erro e sucesso
  inline + matriz canônica de estados (default/focus/filled/disabled/error/success/read-only).
- **Feedback:** alert/banner inline, toast, spinner, skeleton e empty state.
- **Overlays:** modal/dialog, tooltip e popover.
- **Estrutura:** tabs, accordion, avatar (+ grupo e status), breadcrumb, paginação
  e variantes de card (básico, interativo, mídia, horizontal).

### CTA & acessibilidade de componente
- Token de CTA theme-aware `--cta` (e derivados `--cta-grad` / `--cta-solid` / `--cta-solid-h` / `--cta-ink`) como camada de componente para o botão de ação principal. Os botões preenchidos/sólidos (`.b.fill` / `.wf-btn.wf-fill` e variantes solid) consomem `--cta` em vez de referenciar `--roxo2` / `--roxo-bright` diretamente.
- Contraste de componente do CTA no **tema escuro**: o violeta do CTA é `#8A1AE6` (gradiente `#9521FF → #7A1AD6`; hover `#7A1AD6`; texto branco). O valor `#644389` "apagava" sobre o fundo escuro (~2.6:1 vs fundo) e reprovava na WCAG 1.4.11 (Non-text Contrast). O **tema claro** usa CTA `#7A1AD6` (gradiente `#7A1AD6 → #5E12A8`; texto branco).
- Acessibilidade documentada em **2 níveis** para botões/CTA: (1) **texto** ≥ 4.5:1 e (2) **componente/botão vs. fundo** ≥ 3:1 (WCAG 1.4.11). O CTA do tema escuro usa o violeta vívido `#8A1AE6` justamente para passar o nível 2.

### Maturidade & processo
- Seção "Princípios & processo": arquitetura de tokens, princípios de motion e do/don't.
- Este `CHANGELOG.md` e o `CONTRIBUTING.md` (governança, regra das 3 equipes, SemVer).
- Menu de navegação fixo com scrollspy no showcase + respiro de layout revisado.

[Não lançado]: #não-lançado
[1.0.0]: #100--2026-06-19
