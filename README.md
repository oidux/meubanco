# Empréstimo · controle de gastos

App de controle de gastos em duas moedas (BRL e EUR) com totais que se atualizam automaticamente a cada lançamento. Arquivo único `index.html`, sem build, sem servidor, sem dependências em runtime (apenas Google Fonts e a API pública de cotação).

## Como usar localmente

Dê duplo clique em `index.html` — abre no navegador padrão. Tudo é salvo automaticamente no `localStorage`.

## Funcionalidades

- **Hero com Total Geral** em € grande, sparkline da evolução por dia e dois sub-totais (Cartão BRL e Outros EUR).
- **Adicionar gasto** com prefixo R$/€ no campo valor que muda conforme a moeda escolhida no segmented control.
- **Tabela** com busca por observação, filtro por moeda (Tudo / BRL / EUR), edição inline e confirmação de exclusão inline (sem `confirm()` no meio do fluxo).
- **Cotação EUR → BRL automática** (AwesomeAPI ao abrir o app, refresh quando estiver com mais de 12h). Pill clicável no rodapé pra editar manualmente — Enter salva, Esc cancela.
- **Toasts** discretos no canto inferior direito pra cada ação.
- **Exportar CSV** (abre no Excel direto), **Backup JSON**, **Importar JSON**.
- **Responsivo:** layout reorganiza no mobile, esconde colunas pouco essenciais (moeda e € convertido), busca colapsa.

## Deploy no GitHub Pages

1. Crie um repositório no GitHub.
2. Na pasta:
   ```bash
   git remote add origin https://github.com/SEU_USUARIO/NOME_REPO.git
   git push -u origin main
   ```
3. **Settings → Pages → Source: Deploy from a branch → Branch: main / (root) → Save**.
4. Em ~1 minuto fica online em `https://SEU_USUARIO.github.io/NOME_REPO/`.

## Sobre o `localStorage`

- Funciona offline. Funciona em qualquer host estático (GitHub Pages, Vercel, Netlify, servidor próprio).
- Os dados ficam **no navegador do dispositivo** que acessa, não na nuvem. Se você abrir no celular e no PC, são duas "cópias" separadas.
- Use **Backup JSON** pra mover dados entre dispositivos ou pra fazer um snapshot manual antes de operações arriscadas.
- Se você limpar histórico/cache do navegador os dados somem.

## Estrutura

- `index.html` — HTML, CSS e JS num único arquivo.
- `README.md` — este arquivo.

## Design

Tema **warm** (paleta neutra quente com accent índigo `#4f46e5`), fonte **Archivo** (Google Fonts), tabelas em CSS grid (não `<table>`), tabular-nums em todos os números monetários e datas. Tokens de cor/raio/sombra ficam declarados como custom properties no topo do `<style>`.
