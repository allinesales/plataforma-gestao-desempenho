# plataforma-gestao-desempenho
# Plataforma de Gestão de Desempenho e Engajamento (MVP)

Esta é a documentação de arquitetura, módulos e regras de negócio da plataforma de RH desenvolvida no Lovable. O objetivo da ferramenta é automatizar processos de avaliação de desempenho, metas (OKRs), feedbacks e desenvolvimento de colaboradores.

## 🚀 Tecnologias e Infraestrutura
* **Frontend/Backend:** Lovable (React / Vite / TailwindCSS)
* **Banco de Dados & Autenticação:** Supabase (PostgreSQL)

---

## 🗺️ Mapa de Módulos e Funcionalidades

### 1. Módulo de Desempenho (Performance)
* **Avaliação 360º:** Formulários de autoavaliação, avaliação de gestores e de pares.
* **Matriz 9-Box:** Gráfico visual cruzando Potencial vs. Desempenho dos colaboradores.
* **Configurador de Ciclos:** Tela do RH para abrir, fechar e gerenciar prazos de avaliações.

### 2. Módulo de Alinhamento (Metas e OKRs)
* **Árvore de OKRs:** Visualização de objetivos da empresa desdobrados para times e indivíduos.
* **Atualização de Progresso:** Check-ins semanais com barra de progresso (%) ou valores numéricos.

### 3. Módulo de Ritmos (Feedbacks e 1:1s)
* **Mural de Elogios:** Feedbacks públicos baseados nos valores da cultura da empresa.
* **Gestão de 1:1:** Agendamento de reuniões individuais, histórico de pautas e plano de ações.

### 4. Módulo de Desenvolvimento (PDI)
* **Planos de Desenvolvimento:** Criação de metas de carreira atreladas a competências fracas mapeadas na avaliação.

---

## 🔑 Perfis de Acesso (RBAC)
* **Colaborador:** Visualiza e edita apenas seus próprios dados (suas metas, seus feedbacks, suas avaliações).
* **Gestor:** Visualiza os dados de seus liderados diretos e aprova metas/avaliações do time.
* **Admin (RH):** Acesso global a todas as configurações, dashboards consolidados e gerenciamento de usuários.

---

## 🗄️ Estrutura do Banco de Dados (Sugestão para o Supabase)
* `users`: Dados cadastrais dos colaboradores (id, nome, email, cargo, user_role, manager_id).
* `cycles`: Ciclos de avaliação criados pelo RH (id, nome, data_inicio, data_fim, status).
* `reviews`: Respostas das avaliações (id, cycle_id, evaluator_id, evaluatee_id, respostas_json).
* `objectives`: Metas e OKRs (id, user_id, titulo, tipo, progresso, parent_id).
* `feedbacks`: Registro de feedbacks (id, sender_id, receiver_id, mensagem, e_publico).
