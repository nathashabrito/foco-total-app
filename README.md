# 🚀 Foco Total

Um web app de gestão de tarefas (MVP) focado em **acessibilidade** e **design inclusivo**, projetado para auxiliar pessoas com dificuldades de organização, TDAH e paralisia de análise a quebrar e gerenciar suas atividades diárias.

Este projeto é um MVP (Minimum Viable Product) desenvolvido para o desafio "Código que Conecta".

## ✨ Features (Funcionalidades)

O projeto cumpre todos os requisitos mínimos do desafio e adiciona diferenciais focados no usuário-alvo.

### ✅ Requisitos Funcionais (MVP)

*   **(RF-01)** Cadastro e Login de Usuários.
*   **(RF-02)** Criação de Tarefas (vinculadas ao usuário).
*   **(RF-03)** Listagem e Busca de Tarefas (por título ou status).
*   **(RF-04)** Atualização de Tarefas (status, descrição, vencimento).
*   **(RF-05)** Exclusão de Tarefas.

### 🧠 Features Extras (Diferenciais de Acessibilidade)

*   **Assistente IA (Gemini):** Ajuda o usuário a quebrar tarefas complexas em passos menores e acionáveis, além de fornecer dicas de organização.
*   **Estilo Kanban:** Uma visualização alternativa em colunas (A Fazer, Em Andamento, Concluído) para gerenciamento visual.
*   **Integração com Calendário (Planejado):** Conexão com Google Calendar/Outlook para sincronizar datas de vencimento.

## 🛠️ Tech Stack (Tecnologias Utilizadas)

Este projeto utiliza uma arquitetura moderna e integrada, otimizada para performance e produtividade do desenvolvedor.

| Categoria | Tecnologia | Descrição |
| :--- | :--- | :--- |
| **Framework** | Next.js | Com App Router, para renderização híbrida. |
| **Linguagem** | TypeScript | Para tipagem estática e segurança de código. |
| **Frontend** | React e Tailwind CSS | Biblioteca de UI e framework CSS utilitário. |
| **Backend** | Next.js API Routes | Funções Serverless para a lógica de negócio. |
| **Banco de Dados** | PostgreSQL | Hospedado no Supabase. |
| **ORM** | Prisma | Para comunicação segura e tipada com o DB. |
| **IA** | Google Gemini API | Para o assistente de quebra de tarefas. |
| **Deploy** | Vercel | Plataforma de hospedagem e CI/CD. |

## 📂 Estrutura do Projeto (Arquitetura Integrada)

Seguimos a arquitetura padrão do Next.js App Router, onde o frontend e o backend coexistem de forma otimizada.

```
foco-total-app/
│
├── prisma/           # Schema e migrações do banco de dados
│
├── src/              # Pasta principal do código-fonte
│   ├── app/          # Rotas de Frontend (React)
│   │   ├── api/      # Rotas de Backend (API Routes)
│   │   ├── layout.tsx
│   │   └── page.tsx
│   │
│   ├── components/   # Componentes React (UI)
│   ├── context/      # Provedores de Contexto (ex: Auth)
│   ├── hooks/        # Custom Hooks React
│   ├── lib/          # Instâncias (Prisma) e helpers
│   ├── types/        # Definições TypeScript
│   └── utils/        # Funções utilitárias
│
├── .env              # Chaves de API (NÃO ENVIAR AO GIT)
├── .env.example      # Molde das chaves (ENVIAR AO GIT)
├── next.config.js
└── package.json
```

## 🏁 Como Rodar o Projeto Localmente

**Pré-requisitos:** Node.js (v18+), Git e uma conta no Supabase (para o banco Postgres).

### 1. Clone o repositório:

```bash
git clone https://github.com/nathashabrito/foco-total-app.git
cd FOCO-TOTAL-APP
```

### 2. Instale as dependências:

```bash
npm install
```

### 3. Configure as Variáveis de Ambiente:

Crie um arquivo `.env` na raiz do projeto (você pode copiar o .env.example). Preencha com suas chaves:

```
DATABASE_URL="postgresql://postgres.kljknihkmytvlgoxoygt:[SENHA_DO_BANCO]@aws-1-us-east-1.pooler.supabase.com:6543/postgres?pgbouncer=true"

DIRECT_URL="postgresql://postgres.kljknihkmytvlgoxoygt:[SENHA_DO_BANCO]@aws-1-us-east-1.pooler.supabase.com:5432/postgres"
```

### 4. Sincronize o Banco de Dados:

Este comando irá ler seu `prisma/schema.prisma` e criar as tabelas no seu banco Supabase.

```bash
npx prisma migrate dev
```

### 5. Rode o servidor de desenvolvimento:

```bash
npm run dev
```

Acesse `http://localhost:3000` no seu navegador.

## 🌳 Fluxo de Git (Vercel Flow)

Este repositório usa o "Vercel Flow" para CI/CD automático.

*   **`main`:** Branch de Produção. O que está aqui está *live*. Merges só acontecem via PR vindo da `develop`.
*   **`develop`:** Branch de Staging/Integração. É a base para novas features e o alvo de todos os PRs de features.
*   **`feature/*`:** Branches de trabalho. Cada nova feature (card do Trello) deve ser criada a partir da `develop` (ex: `git checkout -b feature/backend-auth`). Ao finalizar, abra um Pull Request (PR) para a `develop`.
