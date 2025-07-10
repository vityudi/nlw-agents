# NLW Agents - Frontend Web

> Frontend desenvolvido durante o evento **NLW Agents** da **Rocketseat** 🚀

Interface web moderna e responsiva para o sistema de salas interativas com upload de áudio e perguntas inteligentes. Desenvolvido com React 19 e Tailwind CSS, oferece uma experiência fluida para interação com transcrições de áudio e sistema de Q&A baseado em IA.

## 🎯 Funcionalidades

### 🏠 Gestão de Salas
- Criar novas salas com nome e descrição
- Visualizar lista de salas disponíveis
- Navegar entre diferentes salas

### 🎤 Upload de Áudio
- Interface para gravação de áudio em tempo real
- Upload de arquivos de áudio (WebM, MP3, WAV)
- Feedback visual durante upload e processamento

### ❓ Sistema de Perguntas
- Fazer perguntas sobre o conteúdo das transcrições
- Visualizar histórico de perguntas e respostas
- Interface responsiva para Q&A

### 🎨 Interface Moderna
- Design responsivo e acessível
- Componentes reutilizáveis com shadcn/ui
- Tema consistente com Tailwind CSS
- Animações e feedback visual

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

### Formulários e Validação

- **React Hook Form** - Gerenciamento de formulários
- **Zod** - Validação de schemas e tipagem
- **@hookform/resolvers** - Integração RHF + Zod

### Utilitários

- **class-variance-authority** - Criação de variantes de componentes
- **clsx** + **tailwind-merge** - Combinação de classes CSS
- **dayjs** - Manipulação de datas
- **Biome** - Linter e formatter (configurado com Ultracite)

### APIs e Tipos

- **@types/dom-speech-recognition** - Tipagem para Web Speech API
- Integração com backend API REST
- Tipos TypeScript compartilhados

## 🚀 Setup e Configuração

### Pré-requisitos

- Node.js (versão 18+)
- npm, yarn ou pnpm

### Instalação

1. Clone o repositório e navegue para a pasta web

```bash
git clone <url-do-repositorio>
cd nlw-agents/web
```

2. Instale as dependências

```bash
npm install
```

3. Configure a URL da API (opcional)

O frontend está configurado para se conectar com a API em `http://localhost:3333`. Se necessário, ajuste as URLs nos arquivos de serviços HTTP.

4. Execute o projeto em modo desenvolvimento

```bash
npm run dev
```

5. Acesse `http://localhost:5173`

> **⚠️ Importante**: Certifique-se de que o backend esteja rodando na porta 3333 antes de iniciar o frontend.

- `npm run dev` - Inicia servidor de desenvolvimento
- `npm run build` - Build de produção otimizado
- `npm run preview` - Preview do build de produção

---

_Desenvolvido durante o **NLW Agents** da **Rocketseat** 🚀_

## 📁 Estrutura do Projeto

```
src/
├── components/          # Componentes reutilizáveis
│   ├── ui/             # Componentes de UI (shadcn/ui)
│   │   ├── button.tsx
│   │   ├── card.tsx
│   │   ├── form.tsx
│   │   └── ...
│   ├── create-room-form.tsx
│   ├── question-form.tsx
│   ├── question-list.tsx
│   └── room-list.tsx
├── pages/              # Páginas da aplicação
│   ├── create-room.tsx
│   ├── room.tsx
│   └── record-room-audio.tsx
├── http/               # Serviços de API
│   ├── types/          # Tipos das requisições/respostas
│   ├── use-create-question.ts
│   ├── use-create-room.ts
│   ├── use-rooms-questions.ts
│   └── use-rooms.ts
├── lib/                # Utilitários e helpers
│   ├── dayjs.ts
│   └── utils.ts
├── app.tsx             # Componente raiz com providers
└── main.tsx            # Entry point da aplicação
```

## 🎨 Padrões de Projeto

- **Component Composition** - Uso de Radix UI para componentes compostos
- **Custom Hooks** - Abstrações para chamadas de API com TanStack Query
- **Utility-First CSS** - Tailwind CSS para estilização
- **Path Aliasing** - Imports absolutos com `@/` para melhor organização
- **Type Safety** - TypeScript para tipagem estática
- **Form Validation** - React Hook Form + Zod para validação robusta

## 🌟 Funcionalidades Implementadas

### 🏠 Página Inicial (Create Room)
- Formulário para criação de salas
- Lista de salas existentes
- Navegação para salas específicas

### 🎤 Gravação de Áudio
- Interface para gravação usando Web Speech API
- Upload de arquivos de áudio
- Feedback visual durante gravação/upload

### 💬 Sistema de Q&A
- Formulário para fazer perguntas
- Lista de perguntas e respostas
- Interface responsiva e acessível

## 🔧 Scripts Disponíveis

- `npm run dev` - Inicia servidor de desenvolvimento
- `npm run build` - Build de produção otimizado
- `npm run preview` - Preview do build de produção
- **Server State Management** - TanStack Query para cache e sincronização

## ⚙️ Configurações

- **Biome** configurado para linting e formatting
- **Tailwind CSS v4** com variáveis CSS
- **shadcn/ui** com tema New York
- **Vite** com plugin React e alias de paths
