# Handoff: Workshops Facial Design System (Versão 1.3.0 · estado em 2026-09-29)

Desenvolvido por **Edegar Junior**. Ponto de retomada; atualizar conforme avançar.

## ✅ Concluído

### Design system online (GitHub Pages)
- **URL pública:** https://eddie-facialacademy.github.io/workshops-facial-design-system/
- Repo público `workshops-facial-design-system` (conta `Eddie-FacialAcademy`), branch `main`, `index.html` na raiz.
- `index.html`: showcase self-contained, dark/light automático + toggle, click-to-copy, **copiar/baixar SVG** de logos+ícones, **download PNG** dos gradientes.

### Pacote portátil (`design-system/`)
- `silka.css` · `workshops-facial-design-system.css` · `workshops-facial-design-tokens.json` · `Button.tsx` · `THEME.md` · `DESIGN-SYSTEM.md`.

### CTA escuro mais claro + acessibilidade em 2 níveis
- CTA do **tema escuro** clareado para `#8F23E7` via token `--cta` (corrige WCAG 1.4.11, contraste de componente) e adoção de acessibilidade em 2 níveis (texto ≥ 4.5:1; componente/botão ≥ 3:1). Registrado em `design-system/CHANGELOG.md`.

### Marca (violeta vívido)
- **Cor predominante:** violeta vívido `#9521FF` (do logo). Institucionais (8): violeta, magenta `#C879FF`, lilás `#A289D7`, dourado claro `#FFE4A4`, rosa claro `#FFB1BD`, pêssego `#FFCA9B`, branco, preto.
- **Logos** Workshops Facial (4 composições) embutidos como `<symbol>` `currentColor` (seguem o tema: branco no dark, `#241733` no light).
- **Tipografia** Silka: **headers em Medium (500)**; eyebrow 600; numeral 700; body 300.

### CTA theme-aware (token `--cta`)
- O CTA (botão preenchido/sólido) é **theme-aware** via token `--cta`. Os botões `.b.fill` / `.wf-btn.wf-fill` (e sólido) passaram a usar `--cta` em vez de `--primary` / `--primary-bright` diretamente, garantindo o CTA correto por tema.
- **Tema escuro:** CTA em **violeta vívido** `#8F23E7` (gradiente `#9521FF → #8B2CE5`; hover `#8B2CE5`; texto branco). O `#644389` antigo "apagava" no fundo escuro (~2.6:1) e reprovava o contraste de componente (WCAG 1.4.11); por isso foi clareado.
- **Tema claro:** CTA = `#7A1AD6` (gradiente `#7A1AD6 → #5E12A8`; texto branco).
- **Tokens:** `--cta-grad` / `--cta-solid` / `--cta-solid-h` / `--cta-ink`.

### Acessibilidade (2 níveis)
- **Nível 1, texto:** contraste ≥ 4.5:1.
- **Nível 2, componente/botão vs fundo:** contraste ≥ 3:1 (WCAG 1.4.11, Non-text Contrast).
- O CTA do tema escuro foi clareado para `#8F23E7` justamente para passar o **nível 2** (Non-text Contrast). Ver entrada correspondente no `design-system/CHANGELOG.md`.

## Deploy / git (durável)
- `.git` **fora do OneDrive**: `AppData\Local\gitdirs\` (fonte: `_online-design-system/`, espelho de `../index.html`).
- **LF** travado (`.gitattributes`); `.gitignore` barra `desktop.ini`.
- **Auth:** Git Credential Manager (Cofre do Windows): push **silencioso, sem token**. Republicar: editar → `git add/commit/push`.

## 🔜 Próximo (Framer)
- A landing já está montada na `/workshops-facial-v2` (Framer). Componentização em andamento (ver `../framer-api/FRAMER-BUILD-RECIPE.md` na pasta do projeto da landing).
- Aplicar os Text Styles (L/M/S = 1200/810/390) e Color Styles a partir deste design system (ver `design-system/DESIGN-SYSTEM.md`).

## Arquivos-chave
- Showcase: `index.html`
- Pacote portátil: `design-system/` (css, tokens.json, Button.tsx, silka.css, DESIGN-SYSTEM.md, THEME.md)
- Docs: `README.md`, `HANDOFF.md`
