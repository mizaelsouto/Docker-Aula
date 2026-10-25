# 🐳 Laboratório Prático de Docker & Containers (`Docker-Aula`)

![Docker](https://img.shields.io/badge/Docker-Containerization-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-24.13-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-5.3-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Bitnami-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)

Repositório prático para o ensino de **containerização de aplicações backend e banco de dados** utilizando **Docker**, **Docker Compose**, **Node.js (Fastify + TypeScript + Prisma)** e **PostgreSQL**, com scripts automatizados de provisionamento multiplataforma (Windows PowerShell e macOS/Linux Bash).

---

## 🏗️ Arquitetura do Ambiente

| Serviço / Container | Imagem Base | Porta Local | Função |
| :--- | :--- | :--- | :--- |
| **`api`** (`aula-docker-api`) | `node:24.13.1-alpine` | `3333:3333` | API REST construída com **Fastify 5**, **TypeScript** e **Prisma ORM**. |
| **`database`** | `bitnami/postgresql:latest` | `5432:5432` | Banco de dados relacional PostgreSQL com volume persistente (`postgres_data`). |

---

## 📂 Estrutura de Arquivos

- `Dockerfile`: Definição da imagem da aplicação Node.js Alpine com build TypeScript.
- `docker-compose.yml`: Orquestração dos serviços `api` e `database`, variáveis de ambiente e rede.
- `provision.ps1`: Script automatizado de provisionamento para **Windows (PowerShell)**.
- `provision.sh`: Script automatizado de provisionamento para **macOS e Linux (Bash)**.
- `Orientacoes.html` & `Tecnologias.html`: Guias visuais interativos de apoio para a aula.
- `package.json` & `tsconfig.json`: Configuração de dependências (`fastify`, `pg`, `@prisma/client`, `bcryptjs`).

---

## 🚀 Como Executar

### Opção 1: Script de Provisionamento Automatizado

**No macOS / Linux (Bash):**
```bash
chmod +x provision.sh
./provision.sh
```

**No Windows (PowerShell):**
```powershell
.\provision.ps1
```

### Opção 2: Comandos Manuais do Docker Compose

```bash
# Subir os containers em segundo plano realizando o build da imagem
docker compose up -d --build

# Verificar o status dos containers
docker compose ps

# Acompanhar os logs da API em tempo real
docker compose logs -f api
```

---

## 👨‍🏫 Autor

**Professor Mizael Souto** (`@mizaelsouto`) — [LinkedIn](https://www.linkedin.com/in/mizaelsouto)
