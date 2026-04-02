# DevStore

Projeto de e-commerce construído com Next.js (App Router), React, TypeScript e Tailwind CSS.

A aplicação oferece:

- Vitrine com produtos em destaque
- Busca de produtos por termo
- Página de detalhe por produto
- Carrinho com contagem de itens únicos
- API mockada via rotas internas do Next.js
- Testes E2E com Cypress

## Tecnologias

- Next.js 15
- React 19
- TypeScript
- Tailwind CSS 4
- Zod
- Cypress

## Requisitos

- Node.js 18.18+ (recomendado Node.js 20 LTS)
- npm 9+

## Configuração

1. Instale as dependências:

```bash
npm install
```

2. Crie o arquivo de ambiente local `.env.local` com:

```env
NEXT_PUBLIC_API_BASE_URL="http://localhost:3000"
APP_URL="http://localhost:3000"
```

Observação: também é possível apontar `NEXT_PUBLIC_API_BASE_URL` para uma API remota, desde que ela exponha as rotas esperadas em `/api/products`.

## Executando o projeto

Ambiente de desenvolvimento:

```bash
npm run dev
```

A aplicação ficará disponível em:

- http://localhost:3000

Build de produção:

```bash
npm run build
npm run start
```

## Scripts disponíveis

- `npm run dev`: inicia o servidor de desenvolvimento
- `npm run build`: gera a build de produção
- `npm run start`: inicia a aplicação em modo produção
- `npm run lint`: executa o lint

## Testes E2E (Cypress)

Este projeto possui cenários E2E para:

- Busca de produtos
- Navegação para detalhe de produto
- Adição de item ao carrinho

Para executar os testes, com a aplicação rodando em `http://localhost:3000`:

```bash
npx cypress open
```

Ou em modo headless:

```bash
npx cypress run
```

## Rotas principais

Páginas:

- `/`: home com produtos em destaque
- `/search?q=termo`: resultado da busca
- `/product/[slug]`: detalhe do produto

API:

- `GET /api/products`: lista todos os produtos
- `GET /api/products/featured`: lista produtos em destaque
- `GET /api/products/search?q=termo`: busca por título
- `GET /api/products/[slug]`: detalhe por slug

## Estrutura do projeto

```text
src/
  app/
    (store)/
      (home)/
      product/[slug]/
      search/
    api/products/
  components/
  contexts/
  data/
cypress/
```

## Comportamento do carrinho

O carrinho mantém itens com quantidade, mas o contador no header exibe apenas a quantidade de produtos únicos adicionados.

## Lint

```bash
npm run lint
```

## Licença

Uso educacional e de estudo.
