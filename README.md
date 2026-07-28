# Portfólio — Vagner de Oliveira

Site institucional/portfólio político de **Hitler Vagner Candido de Oliveira** (Vagner de Oliveira) — ex-prefeito de Chácara–MG e ex-vereador de Juiz de Fora–MG.

## O que é

Um site de **página única, em HTML/CSS/JS puro**, sem framework e sem build. Todo o código (CSS e JavaScript) está **embutido no próprio `index.html`**, e a navegação entre "páginas" é feita por um roteador interno via âncora (`#`), sem recarregar.

## Estrutura

```
index.html          → o site inteiro (HTML + CSS + JS embutidos; foto do hero em base64)
assets/
  emendas-orcamento-2014.pdf … 2025.pdf   → documentos oficiais das emendas (por ano)
  vagner.jpg, share.jpg                    → foto e imagem de compartilhamento (Open Graph)
  realizacoes/                             → (pasta para fotos das entregas, se adicionar)
README.md
.gitignore
```

## Seções do site

- **Sobre** — biografia + áreas de atuação (cards com ícone).
- **Trajetória** — linha do tempo dos cargos.
- **Números** — produção legislativa (leis, projetos, emendas, requerimentos etc.), com listas clicáveis.
- **Entregas** — cards de realizações que abrem uma "matéria" (modal) com texto e fonte.
- **Transparência**
  - **Emendas Parlamentares** — blocos por ano (**2014–2025**), cada um com total, divisão por área (cards clicáveis que abrem uma subpágina por tema) e o PDF oficial para download. Total: **215 emendas · ~R$ 7,9 milhões destinados**. Todos os valores foram conferidos contra os documentos oficiais da Câmara Municipal de Juiz de Fora.
  - **Prefeito de Chácara** — destinação de verbas / LDO 2009.
- **Contato** — formulário que abre o WhatsApp.

## Como rodar localmente

Basta abrir o `index.html` no navegador. Para simular um servidor (recomendado, evita bloqueios de alguns navegadores):

```bash
npx --yes serve .
```

## Como publicar (GitHub Pages)

Por ser um site estático, pode ser hospedado de graça no **GitHub Pages**: suba o repositório, ative Pages na branch `main` (pasta raiz `/`), e o site fica no ar em `https://SEU-USUARIO.github.io/NOME-DO-REPO/`.

> Importante: os **downloads dos PDFs** e a **imagem de compartilhamento** dependem da pasta `assets/`. Sempre mantenha `index.html` e `assets/` juntos.

## Observações técnicas

- A foto principal (hero) está embutida em **base64** dentro do `index.html`, então o visual funciona mesmo enviando só o HTML.
- Os **downloads de emendas** apontam para arquivos locais em `assets/` (funcionam offline, desde que a pasta vá junto).
- Há um **vídeo do Instagram embutido** em uma das matérias (Entregas → "Escola no lugar da festa agropecuária"); ele exige internet para carregar.
- As matérias das entregas só mostram foto se houver um arquivo de imagem correspondente em `assets/realizacoes/`; sem imagem, a área de foto simplesmente não aparece.
