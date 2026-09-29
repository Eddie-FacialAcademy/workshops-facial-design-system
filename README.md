# Workshops Facial: Design System

Design system dos **Workshops Facial** (workshops presenciais de HOF, só face: teoria + aula prática ao vivo, com o aluno vendo o professor aplicando). Marca de cor predominante **violeta `#9521FF`** (do logo); tipografia **Silka** (embutida em woff2, headers em **Medium 500**).

Desenvolvido por **Edegar Junior**.

## Entregas

- **index.html**: design system reutilizável (showcase navegável): paleta (institucional + derivada), temas **dark/light**, tipografia (Silka), **gradientes**, **ícones** (Phosphor Thin, copiar SVG), **logos** (copiar/baixar SVG) e sistema de **botões** (variantes/tamanhos/estados); os botões fill/solid usam o token `--cta` (CTA escuro clareado para passar contraste de componente). Click-to-copy em cores, valores e código; download PNG dos gradientes.
  - 🌐 **Online (para compartilhar):** https://eddie-facialacademy.github.io/workshops-facial-design-system/ (GitHub Pages, repo público `workshops-facial-design-system`).

## Design System portátil (`design-system/`)

Pacote para aplicar a marca em **qualquer projeto/ferramenta** (web, React, Framer, agentes de IA).

- **silka.css**: fonte **Silka** (pesos 300 a 700) embutida em woff2/base64, self-contained; linke antes do CSS principal.
- **workshops-facial-design-system.css**: drop-in (tokens dark/light, inclui CTA theme-aware via `--cta` (dark `#8F23E7`, light `#7A1AD6`) + reset + foco + motion + tipografia + botões + chips/badges/status).
- **workshops-facial-design-tokens.json**: tokens legíveis por máquina (Style Dictionary, Framer, IA).
- **Button.tsx**: Code Component Framer/React com Property Controls.
- **DESIGN-SYSTEM.md**: spec completa, 3 formas de aplicar e **prompt pronto para IA**.
- **THEME.md**: como o claro/escuro é configurado e ativado pelo tema do sistema do visitante (web + Framer).

## Notas técnicas

- **Cores:** derivadas das cores institucionais dos Workshops Facial: violeta `#9521FF`, magenta `#C879FF`, lilás `#A289D7`, amarelo claro `#FFE4A4`, vermelho claro `#FFB1BD`, amarelado `#FFCA9B`, branco `#FFFFFF`, preto `#000000` (apoio/linhagem Facial: `#644389`).
- **Tipografia:** Silka (institucional), embutida em base64/woff2; Poppins como fallback (quando a Silka não estiver disponível), depois system-ui. **Headers em Medium (500)**; eyebrow 600; numeral 700; body 300.
- **Ícones:** biblioteca **Phosphor**, peso **Thin** (stroke 1pt na grade 24), `currentColor`.
- **Tema:** dark por padrão; light via `data-theme="light"`; sem atributo segue `prefers-color-scheme`. Toggle persiste em `wf-theme`.
- **Acessibilidade:** contraste em 2 níveis: (1) texto ≥4.5:1; (2) componente/botão vs fundo ≥3:1 (WCAG 1.4.11). O CTA do tema escuro foi ajustado para `#8F23E7` para passar o nível 2; o botão gold no tema light recebe `border:1px solid var(--gold-ink)` para passar o nível 2.

## Publicação

Repo público `workshops-facial-design-system` (conta `Eddie-FacialAcademy`), branch `main`, `index.html` na raiz, GitHub Pages. `.git` fora do OneDrive (`AppData\Local\gitdirs\`); line-endings LF (`.gitattributes`). Deploy: editar → `git add/commit/push` (credencial no Cofre do Windows, sem token). Ver `HANDOFF.md`.

## CHANGELOG

- **1.2.4**: CTA do tema escuro revisado (sólido `#8F23E7`, fim do degradê e hover `#8B2CE5`), dia selecionado do calendário em `--cta-solid`/`--cta-ink`, prévia de tema com o CTA real de cada tema, seletor de DS com a Facial Premium e versão alinhada em todos os arquivos.
- **1.0.0**: CTA do tema escuro ajustado para `#8A1AE6` (gradiente `#9521FF`→`#7A1AD6`; texto branco) via token `--cta` (`--cta-grad`/`--cta-solid`/`--cta-solid-h`/`--cta-ink`); botões `.b.fill`/`.wf-btn.wf-fill` e solid passam a usar `--cta`; botão gold no light com `border:1px solid var(--gold-ink)`; documentada acessibilidade em 2 níveis (texto ≥4.5:1; componente ≥3:1, WCAG 1.4.11).
