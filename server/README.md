# NLW Agents - Backend API

> Backend desenvolvido durante o evento **NLW Agents** da **Rocketseat** 🚀

API REST para o sistema de salas interativas com transcrição de áudio e perguntas inteligentes usando Google Gemini AI. Este backend gerencia salas, upload de áudios, transcrições automáticas e sistema de perguntas e respostas baseado em busca semântica.

## 🎯 Funcionalidades

### 🏠 Gestão de Salas
- **POST** `/rooms` - Criar nova sala
- **GET** `/rooms` - Listar todas as salas

### 🎤 Upload e Transcrição de Áudio
- **POST** `/rooms/:roomId/audio` - Upload de arquivo de áudio
- Transcrição automática usando Google Gemini AI
- Geração de embeddings para busca semântica

### ❓ Sistema de Q&A
- **POST** `/rooms/:roomId/questions` - Criar pergunta
- **GET** `/rooms/:roomId/questions` - Listar perguntas da sala
- Respostas geradas por IA baseadas nas transcrições

### 🔍 Busca Semântica
- Armazenamento de embeddings no PostgreSQL com pgvector
- Busca vetorial para encontrar conteúdo relevante
- Respostas contextualizadas usando RAG (Retrieval-Augmented Generation)

## 🛠️ Tecnologias Utilizadas

### Backend

- **Node.js** com TypeScript nativo (`--experimental-strip-types`)
- **Fastify** - Framework web rápido e eficiente
- **Google Gemini AI** - Transcrição de áudio e geração de respostas
- **Zod** - Validação de schemas e tipagem
- **PostgreSQL** com **pgvector** - Banco de dados relacional com suporte a vetores
- **Drizzle ORM** - ORM moderno e type-safe

### Ferramentas de Desenvolvimento

- **Biome** - Linter e formatter
- **Docker** - Containerização do banco de dados
- **Drizzle Kit** - Migrações de banco
- **TypeScript** - Tipagem estática

## 🏗️ Padrões de Projeto

- **REST API** com validação de tipos
- **Schema-first** development com Zod
- **Type-safe** database operations com Drizzle ORM
- **Environment configuration** com validação
- **CORS** habilitado para integração frontend

## 🚀 Setup e Configuração

### Pré-requisitos

- Node.js 20+
- Docker e Docker Compose
- PostgreSQL (via Docker)

### Instalação

1. **Clone o repositório e instale as dependências:**

```bash
npm install
```

2. **Configure as variáveis de ambiente:**
   Crie um arquivo `.env` na raiz do projeto:

```env
PORT=3333
DATABASE_URL=postgres://docker:docker@localhost:5432/nlw-agents
GEMINI_API_KEY=your_gemini_api_key_here
```

> **⚠️ Importante**: Você precisa de uma chave da API do Google Gemini. Obtenha em: [Google AI Studio](https://aistudio.google.com/)
3. **Inicie o banco de dados:**

```bash
docker-compose up -d
```

4. **Execute as migrações:**

```bash
npm run db:migrate
```

5. **Popule o banco com dados iniciais (opcional):**

```bash
npm run db:seed
```

### Executando o Projeto

**Desenvolvimento:**

```bash
npm run dev
```

**Produção:**

```bash
npm start
```

A API estará disponível em `http://localhost:3333`

### Endpoints Disponíveis

#### Salas
- `GET /health` - Health check da aplicação
- `GET /rooms` - Lista todas as salas disponíveis
- `POST /rooms` - Cria uma nova sala

#### Perguntas
- `GET /rooms/:roomId/questions` - Lista perguntas de uma sala
- `POST /rooms/:roomId/questions` - Cria pergunta em uma sala

#### Upload de Áudio
- `POST /rooms/:roomId/audio` - Upload e transcrição de áudio

## 📁 Estrutura do Projeto

```
src/
├── db/
│   ├── schema/          # Schemas do banco (Drizzle)
│   │   ├── rooms.ts     # Schema das salas
│   │   ├── questions.ts # Schema das perguntas
│   │   └── audio-chunks.ts # Schema dos áudios transcritos
│   ├── migrations/      # Migrações do banco
│   ├── connection.ts    # Configuração da conexão
│   └── seed.ts          # Dados iniciais
├── http/
│   └── routes/          # Rotas da API
│       ├── create-room.ts
│       ├── get-rooms.ts
│       ├── create-question.ts
│       ├── get-room-questions.ts
│       └── upload-audio.ts
├── services/
│   └── gemini.ts        # Integração com Google Gemini AI
├── env.ts               # Configuração de ambiente
└── server.ts            # Entrada da aplicação
```

## 🤖 Integração com Google Gemini AI

O projeto utiliza o Google Gemini para:

- **Transcrição de Áudio**: Conversão de arquivos de áudio em texto
- **Geração de Embeddings**: Criação de vetores semânticos para busca
- **Geração de Respostas**: Respostas contextualizadas baseadas nas transcrições

## 🗃️ Banco de Dados

O projeto utiliza PostgreSQL com a extensão **pgvector** para:

- Armazenamento de dados relacionais (salas, perguntas, áudios)
- Busca vetorial usando embeddings
- Operações semânticas para o sistema de Q&A

O schema é gerenciado pelo **Drizzle ORM**, garantindo type-safety e migrações automáticas.

## 🔧 Scripts Disponíveis

- `npm run dev` - Inicia o servidor em modo desenvolvimento
- `npm start` - Inicia o servidor em modo produção
- `npm run db:generate` - Gera migrações do banco
- `npm run db:migrate` - Executa migrações pendentes
- `npm run db:seed` - Popula o banco com dados iniciais

---

_Desenvolvido durante o **NLW Agents** da **Rocketseat** 🚀_
