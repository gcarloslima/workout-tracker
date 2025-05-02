### ADR-001: Arquitetura Base do Workout Tracker

**Título**: Definição da Arquitetura Base do Produto Workout Tracker

**Status**: Aceito

**Data**: 02/05/2025

**Contexto**:

Estamos iniciando o desenvolvimento de um aplicativo web chamado **Workout Tracker**, focado no registro e acompanhamento de treinos físicos (aeróbicos e anaeróbicos), com funcionalidades como:

- Registro de exercícios por tipo (aeróbico/anaeróbico)
- Acompanhamento de progressão de carga
- Metas de treino e acompanhamento de conclusão
- Visualização em calendário
- Análise de grupos musculares trabalhados
- Histórico e estatísticas de desempenho

O sistema precisará ser escalável, com uma boa separação entre frontend e backend, persistência de dados relacionais e semi-estruturados, além de performance e segurança adequadas.

---

**Decisão**:

Adotaremos a seguinte arquitetura e stack tecnológica:

- **Frontend**: [Next.js](https://nextjs.org/) (React-based, com suporte SSR/SSG e ótima DX)
- **Backend**: [Spring Boot](https://spring.io/projects/spring-boot) (Java)
- **Banco de Dados Relacional**: [PostgreSQL](https://www.postgresql.org/)
- **Banco de Dados NoSQL**: [MongoDB](https://www.mongodb.com/)
- **API REST/GraphQL**: Inicialmente REST com possibilidade futura de adoção de GraphQL

---

**Justificativa**:

1. **Next.js**:
    - Suporte a renderização híbrida (SSR/SSG/ISR), ideal para páginas públicas e dashboard.
    - Boa integração com TypeScript e bibliotecas modernas de UI.
    - SEO-friendly e ótimo desempenho para interfaces responsivas e ricas.
2. **Spring Boot**:
    - Robusto, maduro e com ótima estrutura para APIs RESTful.
    - Suporte a segurança via Spring Security.
    - Facilidade de integração com PostgreSQL e MongoDB.
    - Escalabilidade e confiabilidade para lógicas de negócio mais complexas.
3. **PostgreSQL**:
    - Utilizado para entidades relacionais e dados estruturados, como usuários, treinos, exercícios, progresso de carga, metas e histórico.
    - Recursos avançados como JSONB, constraints e stored procedures.
4. **MongoDB**:
    - Utilizado para armazenar dados semi-estruturados, como logs de sessões de treino, registros históricos detalhados, templates de treinos personalizados.
    - Flexibilidade na modelagem para dados que podem variar bastante entre usuários.
5. **Separação de responsabilidades**:
    - Frontend e backend desacoplados com comunicação via API REST.
    - Backend será exposto via `/api/**` com autenticação JWT.
    - Autenticação centralizada via backend com frontend consumindo tokens.

---

**Consequências**:

- A separação clara de responsabilidades permite escalar o frontend e backend independentemente.
- A dualidade entre PostgreSQL e MongoDB aumenta a complexidade de persistência, exigindo decisões claras sobre onde armazenar determinados dados.
- O uso de Spring Boot exige uma curva de aprendizado maior, mas oferece robustez e extensibilidade.
- Next.js facilitará a entrega rápida de MVP com UX moderna e interativa.
- Demandará uma boa estratégia de DevOps para orquestrar os dois bancos e os dois serviços (frontend/backend).

---

**Alternativas Consideradas**:

- **Frontend-only com Firebase**: Simples, mas não atenderia aos requisitos de customização e escalabilidade da lógica de negócios.
- **Monolito com Node.js + Mongo**: Simples de início, porém difícil de manter conforme o crescimento do produto.

---

**Próximos Passos**:

- Definir esquemas iniciais de banco de dados (Postgres e MongoDB)
- Estabelecer contratos de API entre Next.js e Spring Boot
- Definir o fluxo de autenticação e autorização
- Montar um ambiente de desenvolvimento local com Docker