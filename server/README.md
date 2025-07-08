# NLW Agents

Projeto desenvolvido durante o evento da **Rocketseat**, focado na criação de uma API robusta para gerenciamento de agentes utilizando tecnologias modernas do ecossistema Node.js.

## 🛠️ Tecnologias Utilizadas

### Backend

- **Node.js** com TypeScript nativo (`--experimental-strip-types`)
- **Fastify** - Framework web rápido e eficiente
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
DATABASE_URL=postgres://docker:docker@localhost:5432/agents
```

3. **Inicie o banco de dados:**

```bash
docker-compose up -d
```

4. **Execute as migrações:**

```bash
npx drizzle-kit migrate
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

- `GET /health` - Health check da aplicação
- `GET /rooms` - Lista todas as salas disponíveis

## 📁 Estrutura do Projeto

```
src/
├── db/
│   ├── schema/          # Schemas do banco (Drizzle)
│   ├── migrations/      # Migrações do banco
│   └── connection.ts    # Configuração da conexão
├── http/
│   └── routes/          # Rotas da API
├── env.ts               # Configuração de ambiente
└── server.ts            # Entrada da aplicação
```

## 🗃️ Banco de Dados

O projeto utiliza PostgreSQL com a extensão pgvector, ideal para operações com vetores e AI. O schema é gerenciado pelo Drizzle ORM, garantindo type-safety e migrações automáticas.

---

_Desenvolvido durante o NLW da Rocketseat 🚀_
