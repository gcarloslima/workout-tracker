# Workout Tracker 🏋️‍♂️

Aplicativo web para registro e acompanhamento de treinos físicos (aeróbicos e anaeróbicos), com funcionalidades como metas, calendário, análise de desempenho e histórico completo.

---

## 📐 Arquitetura Base

O projeto adota uma arquitetura desacoplada entre **frontend** e **backend**, com persistência de dados tanto em bancos **relacionais** quanto **NoSQL**, garantindo flexibilidade, escalabilidade e performance.

### 🔧 Tecnologias

| Camada         | Stack                                                                 |
|----------------|-----------------------------------------------------------------------|
| Frontend       | [Next.js](https://nextjs.org/) (React, TypeScript, SSR/SSG)          |
| Backend        | [Spring Boot](https://spring.io/projects/spring-boot) (Java)         |
| Banco Relacional| [PostgreSQL](https://www.postgresql.org/)                           |
| Banco NoSQL    | [MongoDB](https://www.mongodb.com/)                                  |
| Autenticação   | JWT (via backend Spring Security)                                     |
| Comunicação    | REST API (`/api/**`)                                                  |

---

## ✨ Funcionalidades Planejadas

- Cadastro e login de usuários
- Registro de treinos aeróbicos e anaeróbicos
- Acompanhamento de progressão de carga
- Definição e acompanhamento de metas
- Visualização em calendário
- Análise de grupos musculares trabalhados
- Histórico de treinos e estatísticas de desempenho
- Templates de treino personalizados

---

## 🚀 Próximos Passos

- [ ] Definir esquemas iniciais do banco de dados (PostgreSQL e MongoDB)
- [ ] Definir contratos de API entre frontend e backend
- [ ] Implementar autenticação via JWT
- [ ] Montar ambiente de desenvolvimento local com Docker

---

## 🐳 Desenvolvimento com Docker

Será utilizado Docker para facilitar a orquestração do ambiente local com:

- `frontend`: container com Next.js
- `backend`: container com Spring Boot
- `db`: container com PostgreSQL
- `mongo`: container com MongoDB

> Em breve será disponibilizado o `docker-compose.yml` com todas as configurações necessárias.

---

## 📁 Estrutura do Projeto

```bash
workout-tracker/
├── frontend/             # Projeto Next.js
├── backend/              # Projeto Spring Boot
├── infra/                # Infraestrutura (Docker, scripts, etc.)
├── docs/                 # Documentos como ADRs, diagramas, etc.
└── README.md
```

## 📄 Licença

Este projeto está em desenvolvimento e será licenciado futuramente.
