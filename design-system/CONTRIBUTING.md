# Contribuindo: Workshops Facial Design System

Este guia descreve **como o sistema evolui** sem virar uma colcha de retalhos.
Vale para a web (HTML/CSS + tokens) e para o Framer.

## Princípios inegociáveis

1. **Token-first.** Nunca use hex/raio/sombra solto; consuma os tokens. O token
   semântico **nunca sugere valor** (`--btn-bg`, não `--roxo-500`); o de componente
   referencia o semântico, nunca o primitivo direto.
2. **Paridade dark/light + WCAG AA em dois níveis.** O contraste vale nos **dois**
   temas em **dois níveis**: **(1) texto** ≥ 4.5:1 (texto grande ≥ 3:1); **(2)
   componente/botão e estados** (incl. foco), elemento não-textual vs fundo ≥ 3:1
   (WCAG 1.4.11, Non-text Contrast). Cor nunca comunica sozinha: sempre acompanhada
   de ícone ou texto.
3. **A11y by design.** Foco visível em tudo que é focável, navegação por teclado e
   semântica HTML correta entram desde o início, não como auditoria depois. O foco
   visível e os contornos de componentes também cumprem o contraste de não-texto
   ≥ 3:1 (WCAG 1.4.11), conforme o nível 2 do princípio de contraste.

## Quando algo vira padrão: regra das 3 equipes

Só promovemos a **componente/token oficial** o que tem **3+ usos reais** distintos.
Antes disso, é um padrão local. Isso evita inchar o sistema com peças de uso único.

## Gate de "pronto" (definition of done)

Um componente só fecha quando tem **os quatro**:

- **Design**: todos os estados, variantes e tamanhos.
- **A11y**: teclado, foco e semântica, mais contraste nos **dois níveis** nos dois
  temas: texto ≥ 4.5:1 e componente/botão (incl. foco) vs fundo ≥ 3:1 (WCAG 1.4.11).
  Componentes como o CTA preenchido não fecham sem passar o nível 2.
- **Código**: implementação consumindo tokens.
- **Doc**: quando usar, quando não usar (do/don't) e exemplo.

## Versionamento (SemVer) + CHANGELOG

Siga o [SemVer](https://semver.org/lang/pt-BR/): **MAJOR** quebra, **MINOR** adiciona
retrocompatível, **PATCH** corrige. **Toda** mudança visível entra no `CHANGELOG.md`
na mesma alteração, sem exceção.

## Depreciação

Nada some de repente. Marque como `deprecated`, mantenha por **pelo menos um MINOR**
com aviso e caminho de migração, e só remova em uma **MAJOR**.

## Fluxo

1. **Proponha** o problema/uso (não a solução pronta).
2. **Revise** com quem mantém o sistema (cabe ao sistema ou é caso local?).
3. **Implemente** consumindo tokens + cumpra o gate de pronto.
4. **Documente** + atualize o `CHANGELOG.md`.
5. **Publique** nos dois temas testados.

## Linguagem

Documentação e UI writing inclusivos: evite "só", "simplesmente", "fácil", "óbvio".
O que é óbvio para quem criou raramente é para quem chega depois.
