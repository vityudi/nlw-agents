# NLW Agents

> Projeto desenvolvido durante o evento da Rocketseat

## 🛠 Tecnologias e Bibliotecas

### Frontend Framework

- **React 19** - Biblioteca para interfaces de usuário
- **TypeScript** - Superset JavaScript com tipagem estática
- **Vite** - Build tool e dev server

### Estilização

- **Tailwind CSS v4** - Framework CSS utilitário
- **Lucide React** - Biblioteca de ícones
- **Radix UI** - Componentes acessíveis e primitivos
- **shadcn/ui** - Sistema de componentes baseado em Radix UI

### Roteamento e Estado

- **React Router DOM** - Roteamento client-side
- **TanStack Query (React Query)** - Gerenciamento de estado servidor

### Utilitários

- **class-variance-authority** - Criação de variantes de componentes
- **clsx** + **tailwind-merge** - Combinação de classes CSS
- **Biome** - Linter e formatter (configurado com Ultracite)

## 🚀 Setup e Configuração

### Pré-requisitos

- Node.js (versão 18+)
- npm, yarn ou pnpm

### Instalação

1. Clone o repositório

```bash
git clone <url-do-repositorio>
cd web
```

2. Instale as dependências

```bash
npm install
```

3. Execute o projeto em modo desenvolvimento

```bash
npm run dev
```

4. Acesse `http://localhost:5173`

### Scripts Disponíveis

```bash
# Desenvolvimento
npm run dev

# Build de produção
npm run build

# Preview do build
npm run preview
```

## 📁 Estrutura do Projeto

```
src/
├── components/ui/     # Componentes de UI (shadcn/ui)
├── lib/              # Utilitários e helpers
├── pages/            # Páginas da aplicação
├── app.tsx           # Componente raiz com providers
└── main.tsx          # Entry point da aplicação
```

## 🎨 Padrões de Projeto

- **Component Composition** - Uso de Radix UI para componentes compostos
- **Utility-First CSS** - Tailwind CSS para estilização
- **Path Aliasing** - Imports absolutos com `@/` para melhor organização
- **Type Safety** - TypeScript para tipagem estática
- **Server State Management** - TanStack Query para cache e sincronização

## ⚙️ Configurações

- **Biome** configurado para linting e formatting
- **Tailwind CSS v4** com variáveis CSS
- **shadcn/ui** com tema New York
- **Vite** com plugin React e alias de paths
