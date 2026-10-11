# 📊 Finance AI

Plataforma SaaS de **gestão financeira pessoal com relatórios gerados por IA**. O usuário registra receitas, despesas e investimentos, acompanha um dashboard mensal e, no plano Premium, recebe um relatório com dicas personalizadas gerado pela OpenAI.

> 📺 Projeto construído acompanhando a **Full Stack Week** de [Felipe Rocha • Full Stack Club](https://www.youtube.com/@dicasparadevs) no YouTube, para aprender Next.js, Stripe e integração com IA na prática. As melhorias que fiz por conta própria estão na seção [Minhas melhorias](#-minhas-melhorias).

![Next.js](https://img.shields.io/badge/Next.js_14-000000?style=flat&logo=nextdotjs&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![Prisma](https://img.shields.io/badge/Prisma-2D3748?style=flat&logo=prisma&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white)
![Clerk](https://img.shields.io/badge/Clerk-6C47FF?style=flat&logo=clerk&logoColor=white)
![Stripe](https://img.shields.io/badge/Stripe-635BFF?style=flat&logo=stripe&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=flat&logo=openai&logoColor=white)
![Tailwind](https://img.shields.io/badge/Tailwind-06B6D4?style=flat&logo=tailwindcss&logoColor=white)

## ✨ Funcionalidades

- **Login** com Clerk
- **Dashboard mensal**: saldo, depósitos, despesas e investimentos, com seletor de mês
- **Gráfico de pizza** da distribuição entre depósitos, despesas e investimentos (Recharts)
- **Gastos por categoria** com barras de progresso
- **Últimas transações** e página com **tabela completa** (TanStack Table)
- **Criar e editar transações** em um diálogo com formulário validado (React Hook Form + Zod) e campo de valor em R$
- **Assinatura Premium** com **Stripe Checkout** e **webhook** que ativa ou cancela o plano
- **Plano gratuito** limitado a 10 transações por mês
- **Relatório com IA** (GPT-4o mini) para usuários Premium, renderizado em Markdown

## 🧱 Arquitetura

```
app/
├── (home)/          # dashboard: cards, gráficos, últimas transações, relatório de IA
├── transactions/    # tabela de transações
├── subscription/    # planos e checkout do Stripe
├── login/
├── api/webhooks/    # webhook do Stripe
├── _actions/        # Server Actions (criar/editar transação)
├── _data/           # consultas ao banco (dashboard, limite do plano)
└── _components/ui/  # componentes shadcn/ui
```

Next.js 14 com **App Router** e **Server Actions**; o banco é acessado só no servidor via Prisma. Qualidade de código com ESLint, Prettier, Husky e lint-staged.

## 🚀 Como rodar

```bash
git clone https://github.com/LucianoMachadoS/finance-ai.git
cd finance-ai
npm install
```

Crie um `.env` (nunca suba esse arquivo para o GitHub):

```env
DATABASE_URL=
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=
CLERK_SECRET_KEY=
STRIPE_SECRET_KEY=
NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY=
STRIPE_WEBHOOK_SECRET=
STRIPE_PREMIUM_PLAN_PRICE_ID=
NEXT_PUBLIC_STRIPE_CUSTOMER_PORTAL_URL=
APP_URL=http://localhost:3000
OPENAI_API_KEY=
```

```bash
npx prisma migrate dev
npm run dev
```

## 📚 O que aprendi

Next.js com Server Components e Server Actions, autenticação com Clerk, pagamentos recorrentes com Stripe e webhooks, integração com a API da OpenAI, Prisma com PostgreSQL e componentes acessíveis com shadcn/ui.

---
Feito por [Luciano Machado](https://github.com/LucianoMachadoS) · [LinkedIn](https://www.linkedin.com/in/luciano-machado-9253a1265/)
