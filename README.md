# NLW Agents - Sistema de Salas e Perguntas com IA

> Projeto desenvolvido durante o evento **NLW Agents** da **Rocketseat** 🚀

Este projeto demonstra a criação de um sistema completo de salas interativas onde é possível fazer upload de áudios, transcrever automaticamente usando IA (Google Gemini) e fazer perguntas baseadas no conteúdo das transcrições.

## 📋 Sobre o Projeto

O **NLW Agents** é uma aplicação fullstack que permite:

- 🏠 **Criar salas temáticas** para organizar conteúdo
- 🎤 **Upload e transcrição de áudios** usando Google Gemini AI
- ❓ **Sistema de perguntas e respostas** baseado no conteúdo transcrito
- 🔍 **Busca semântica** usando embeddings e PostgreSQL com pgvector
- 💬 **Interface moderna e intuitiva** para interação

## 🏗️ Arquitetura

O projeto está organizado em duas partes principais:

```
nlw-agents/
├── server/          # Backend API (Node.js + Fastify)
├── web/             # Frontend SPA (React + Vite)
└── README.md        # Este arquivo
```

### 🎯 Fluxo da Aplicação

1. **Criação de Salas**: Usuários criam salas com nome e descrição
2. **Upload de Áudio**: Upload de arquivos de áudio nas salas
3. **Transcrição Automática**: Google Gemini converte áudio em texto
4. **Geração de Embeddings**: Criação de vetores semânticos para busca
5. **Perguntas e Respostas**: IA responde perguntas baseadas nas transcrições

## 🛠️ Tecnologias Principais

### Backend
- **Node.js** com TypeScript nativo
- **Fastify** - Framework web performático
- **PostgreSQL** + **pgvector** - Banco com suporte a vetores
- **Drizzle ORM** - ORM type-safe
- **Google Gemini AI** - Transcrição e geração de respostas
- **Zod** - Validação de schemas

### Frontend
- **React 19** + **TypeScript**
- **Vite** - Build tool moderna
- **Tailwind CSS v4** - Estilização utilitária
- **TanStack Query** - Gerenciamento de estado servidor
- **React Router** - Roteamento SPA
- **shadcn/ui** - Sistema de componentes

## 🚀 Como Executar

### Pré-requisitos

- Node.js 20+
- Docker e Docker Compose
- Conta Google Cloud Platform (para Gemini AI)

### 1. Clone o repositório

```bash
git clone <url-do-repositorio>
cd nlw-agents
```

### 2. Configure o Backend

```bash
cd server
npm install

# Configure as variáveis de ambiente
cp .env.example .env
# Edite o .env com suas configurações
```

### 3. Inicie o banco de dados

```bash
docker-compose up -d
```

### 4. Execute as migrações

```bash
npm run db:migrate
npm run db:seed  # (opcional) dados de exemplo
```

### 5. Inicie o servidor

```bash
npm run dev
```

### 6. Configure o Frontend

```bash
cd ../web
npm install
npm run dev
```

### 7. Acesse a aplicação

- Frontend: http://localhost:5173
- Backend API: http://localhost:3333

## 📚 Documentação Detalhada

Para informações mais específicas sobre cada parte do projeto:

- [📖 Documentação do Backend](./server/README.md)
- [📖 Documentação do Frontend](./web/README.md)

## 🌟 Funcionalidades Principais

### 🏠 Gestão de Salas
- Criar salas com nome e descrição
- Listar todas as salas disponíveis
- Navegar entre salas

### 🎤 Upload e Transcrição de Áudio
- Upload de arquivos de áudio (WebM, MP3, WAV)
- Transcrição automática usando Google Gemini
- Armazenamento de transcrições no banco

### ❓ Sistema de Q&A Inteligente
- Fazer perguntas sobre o conteúdo das aulas
- Respostas geradas por IA baseadas nas transcrições
- Busca semântica usando embeddings

### 🔍 Busca Semântica
- Geração de embeddings para transcrições
- Busca vetorial no PostgreSQL com pgvector
- Respostas contextualizadas e precisas

## 🤝 Contribuindo

Este projeto foi desenvolvido durante o NLW Agents da Rocketseat como material educativo. Sinta-se à vontade para:

- Fazer fork do projeto
- Criar issues para reportar bugs
- Propor melhorias
- Enviar pull requests

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

## 🎓 Sobre o NLW

O **Next Level Week (NLW)** é um evento online e gratuito da **Rocketseat** onde são desenvolvidos projetos práticos do zero, explorando tecnologias modernas e conceitos avançados de programação.

**Rocketseat** - Plataforma de educação em tecnologia focada em programação e desenvolvimento de software.

---

⭐ Se este projeto foi útil para você, considere dar uma estrela no repositório!
