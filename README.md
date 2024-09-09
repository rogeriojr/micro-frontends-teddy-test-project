
# Projeto Micro Front-ends com Next.js, TypeScript e Docker

Este projeto é uma aplicação de micro front-ends utilizando **Next.js** com **TypeScript**, integrando microserviços para **parceiros** e **empresas externas**. Ele possui funcionalidades de **CRUD** para ambas as entidades, além de autenticação com uma página de login funcional.

## Funcionalidades

1. **Login**:
   - Página de login com opção de "Manter conectado" utilizando **cookies** ou **localStorage**.
   - Redireciona o usuário para a página inicial após o login.
   - Se o usuário já estiver logado (nome no cookie/localStorage), ele será automaticamente redirecionado para a página inicial.

2. **Parceiros**:
   - Listagem de todos os parceiros integrados.
   - Funções de **adicionar**, **editar** e **excluir** parceiros.
   - Paginação na tabela de parceiros.

3. **Empresas Externas**:
   - Listagem de todas as empresas externas integradas.
   - Funções de **adicionar**, **editar** e **excluir** empresas.
   - Paginação na tabela de empresas.

4. **Integração com APIs**:
   - API de Parceiros: `https://644060ba792fe886a88de1b9.mockapi.io/v1/test/partners`
   - API de Empresas Externas: `https://655cf25525b76d9884fe3153.mockapi.io/v1/external-companies`

5. **Paginação e Compartilhamento de Links**:
   - A paginação é aplicada nas tabelas de parceiros e empresas externas.
   - Compartilhamento de links garante que o usuário será redirecionado para a página exata após o login.

6. **Testes Automatizados**:
   - Configurado com **Jest** e **React Testing Library**.
   - Testes unitários para a página de login.

## Tecnologias Utilizadas

- **Next.js** (com suporte ao **App Router**)
- **React** (base da interface)
- **TypeScript** (tipagem estática)
- **Jest** (testes unitários)
- **Styled-components** (estilização)
- **Docker** (containerização)
- **Yarn** (gerenciador de pacotes)

## Estrutura do Projeto

```bash
micro-frontends-project/
├── core-frontend/
│   ├── app/
│   │   ├── login/
│   │   │   ├── page.tsx  # Página de login
│   │   │   └── login.module.css  # Estilo da página de login
│   │   ├── page.tsx  # Página inicial
│   │   └── page.module.css  # Estilo da página inicial
│   ├── __tests__/  # Testes unitários
│   ├── jest.config.js  # Configuração do Jest
│   ├── Dockerfile  # Configuração do Docker
│   └── package.json  # Configurações do projeto
├── partners/
│   ├── app/
│   │   ├── page.tsx  # Página de parceiros com CRUD
│   │   └── page.module.css  # Estilo da página de parceiros
│   ├── Dockerfile  # Configuração do Docker
│   └── package.json  # Configurações do projeto
├── docker-compose.yml  # Configuração do Docker Compose
└── README.txt  # Este arquivo
```

## Pré-requisitos

- **Node.js** (>= 14.x)
- **Yarn** (>= 1.x)
- **Docker** (>= 20.x)

## Como Executar

1. **Clone o repositório**:
   ```bash
   git clone https://github.com/rogeriojr/micro-frontends-teddy-test-project
   cd micro-frontends-project
   ```

2. **Suba os serviços com Docker**:
   ```bash
   docker-compose up --build
   ```

3. **Acesse a aplicação**:
   - **Core Frontend (Login, Home)**: `http://localhost:3000`
   - **Parceiros (CRUD de parceiros)**: `http://localhost:3001`
   - **Empresas Externas (CRUD de empresas)**: `http://localhost:3002`

## Como Rodar os Testes

Para rodar os testes unitários, execute o seguinte comando:

```bash
yarn test
```

## Deploy