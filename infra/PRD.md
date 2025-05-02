# **Product Requirements Document (PRD)**

**Produto**: Workout Tracker

**Versão**: 1.0

**Data**: 02/05/2025

**Responsável**: [Nome do PM ou PO]

---

## **1. Visão Geral do Produto**

O **Workout Tracker** é uma plataforma web para o registro e acompanhamento de treinos físicos. O usuário poderá registrar sessões de treino (aeróbicas e anaeróbicas), acompanhar sua evolução, visualizar progresso em um calendário, estabelecer e monitorar metas, e ter uma visão clara de quais grupos musculares têm sido mais trabalhados.

---

## **2. Objetivos**

- Permitir aos usuários o registro completo de suas rotinas de treino.
- Fornecer visualizações amigáveis para evolução, metas e histórico.
- Ajudar usuários a identificar desequilíbrios ou lacunas no treino (ex: negligência de certos grupos musculares).
- Promover constância com metas e recompensas visuais.

---

## **3. Público-Alvo**

- Pessoas que praticam musculação, corrida, ciclismo, natação ou outras atividades físicas.
- Treinadores que desejam acompanhar a evolução de seus alunos.
- Iniciantes que querem iniciar um registro básico de treino.

---

## **4. Funcionalidades Principais**

### 4.1. **Autenticação**

- Cadastro/Login com email e senha
- Login social (Google)
- Recuperação de senha
- Sessão autenticada com JWT

### 4.2. **Dashboard Principal**

- Resumo semanal de atividades
- Destaques: metas atingidas, volume de carga, tempo ativo
- Avisos/metas pendentes

### 4.3. **Registro de Treino**

- Tipo de treino: Aeróbico ou Anaeróbico
- Para treino anaeróbico:
    - Exercício
    - Séries e repetições
    - Carga (kg)
    - Grupo muscular envolvido
- Para treino aeróbico:
    - Tipo de atividade (corrida, bike, etc)
    - Distância, duração, intensidade
- Notas adicionais (observações)

### 4.4. **Histórico e Calendário**

- Visualização por mês/semana
- Treinos representados como eventos
- Filtro por tipo (aeróbico/anaeróbico)
- Navegação rápida entre datas

### 4.5. **Metas**

- Criação de metas (ex: "Treinar 4x por semana", "Correr 20km no mês")
- Acompanhamento de progresso
- Notificações de cumprimento ou atraso

### 4.6. **Progressão de Carga**

- Visualização por exercício
- Gráficos mostrando aumento/diminuição de carga ao longo do tempo
- Destaques de PRs (Personal Records)

### 4.7. **Grupos Musculares**

- Visão dos grupos mais treinados
- Mapa corporal visual (opcional em v2)
- Alertas para desequilíbrios musculares

---

## **5. Funcionalidades Adicionais (Versões Futuras)**

- Integração com smartwatchs/trackers (Apple Watch, Fitbit, Strava)
- Compartilhamento de treinos com amigos ou treinador
- Treinos recomendados por IA
- Aplicativo mobile (React Native ou Flutter)

---

## **6. Requisitos Técnicos**

- **Frontend**: Next.js com TypeScript
- **Backend**: Spring Boot com REST API
- **Banco Relacional**: PostgreSQL (usuários, treinos, metas, exercícios)
- **Banco NoSQL**: MongoDB (histórico detalhado, logs, anotações ricas)
- **Hospedagem**: Vercel (Frontend), Render/AWS/GCP (Backend)
- **Autenticação**: JWT com refresh token

---

## **7. Métricas de Sucesso**

- % de usuários ativos semanais
- Retenção após 30 dias
- Taxa de conclusão de metas
- Crescimento de carga por exercício
- Feedback NPS de usabilidade

---

## **8. Restrições**

- O MVP não incluirá suporte a dispositivos móveis nativamente.
- Não haverá integração com sensores ou APIs externas inicialmente.
- Versão 1.0 será focada em uso individual (sem recursos sociais).