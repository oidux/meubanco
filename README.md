# Empréstimo Elias

Controle de gastos em duas moedas (BRL e EUR) com totais que se atualizam automaticamente a cada lançamento. App estático em um único arquivo `index.html` — sem build, sem servidor, sem dependências em tempo de execução.

## Como usar localmente

1. Dê duplo clique em `index.html` (abre no navegador padrão).
2. Tudo é salvo automaticamente no `localStorage` do navegador.

## Funcionalidades

- **Adicionar gasto:** data, valor original, moeda (BRL/EUR), observação.
- **Editar/excluir** qualquer linha pela própria tabela.
- **Cotação EUR → BRL automática:** busca da [AwesomeAPI](https://docs.awesomeapi.com.br/api-de-moedas) ao abrir o app (e quando a cotação salva tem mais de 12h). Pode ser sobrescrita manualmente a qualquer momento.
- **Totais em tempo real:**
  - Total Cartão (BRL): soma dos valores em BRL, no original e convertidos para €.
  - Total Outros (EUR): soma dos valores em EUR.
  - Total Geral (€): soma de tudo já em €.
- **Exportar CSV** (abre direto no Excel) e **JSON** (backup).
- **Importar JSON** para restaurar um backup.

## Subir no GitHub Pages (deploy gratuito)

1. Crie um repositório novo no GitHub (ex: `emprestimo-elias`).
2. No terminal, dentro desta pasta:

   ```bash
   git init
   git add index.html README.md
   git commit -m "Primeira versão"
   git branch -M main
   git remote add origin https://github.com/SEU_USUARIO/emprestimo-elias.git
   git push -u origin main
   ```

3. No GitHub: **Settings → Pages → Source: Deploy from a branch → Branch: main / (root) → Save**.
4. Em ~1 minuto o site fica online em `https://SEU_USUARIO.github.io/emprestimo-elias/`.

## Sobre o `localStorage`

Os dados ficam salvos **no navegador do dispositivo onde você acessar**, não no GitHub. Isso significa:

- Funciona offline.
- Não tem custo nem servidor.
- **Não sincroniza** entre celular e PC — cada navegador tem sua "cópia". Use **Exportar JSON** para fazer backup ou mover dados de um dispositivo para outro.
- Se você limpar o histórico/cache do navegador, os dados somem. Faça backup se for fazer isso.

## Estrutura

- `index.html` — HTML, CSS e JS num único arquivo. Toda a lógica está no `<script>` no fim.
- `README.md` — este arquivo.

## Próximos passos possíveis (se um dia precisar)

- **Sincronizar entre dispositivos:** trocar `localStorage` por Supabase ou Firebase (cerca de 30 linhas de mudança).
- **Categorias customizadas:** adicionar coluna "Categoria" independente da moeda.
- **Gráficos:** evolução por dia/semana usando Chart.js.
- **PWA:** transformar em app instalável no celular.
