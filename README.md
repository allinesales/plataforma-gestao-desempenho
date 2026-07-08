# 🚀 High Output - Management Hub

Este repositório contém a documentação arquitetural do Hub de Gestão. A plataforma está dividida em duas fases de desenvolvimento: a V1.0 (atualmente em produção) e a V2.0 (expansão para Gestão de RH, Desempenho e Engajamento).

## 🚀 Tecnologias e Infraestrutura
* **Frontend/Backend:** Lovable (React / Vite / TailwindCSS)
* **Banco de Dados & Autenticação:** Supabase (PostgreSQL)

---

## 🏛️ Versão 1.0 - Funcionalidades Atuais (Em Produção)
[⚠️ AVISO PARA VOCÊ: Substitua esta linha pelo texto que o Lovable vai gerar quando você pedir a ele para documentar a versão atual, conforme combinamos no Passo 1]

### Páginas e Navegação
* `/squad/:id`: Painel dinâmico da Squad (Métricas de Total da Equipe, Alertas 'Care'/'Safe' e Produtividade Média).
* `/frameworks`: Central de metodologias aplicadas.

### Dados Atuais (Supabase)
* `squads`: Dados das equipes.
* `members`: Lista de colaboradores vinculados à squad, com status de produtividade (`safe`, `care`) e porcentagem de rendimento.

---

## 🔮 Versão 2.0 - Nova Expansão (Módulo de RH e Engajamento)
O objetivo desta nova fase é automatizar processos de avaliação de desempenho, metas (OKRs), feedbacks e desenvolvimento, conectando-os aos membros que já existem na V1.0.

### 1. Módulo de Desempenho (Performance)
* **Avaliação 360º:** Formulários de autoavaliação, avaliação de gestores e de pares.
* **Matriz 9-Box:** Gráfico visual cruzando Potencial vs. Desempenho dos colaboradores.
* **Configurador de Ciclos:** Tela do RH para abrir, fechar e gerenciar prazos de avaliações.

### 2. Módulo de Alinhamento (Metas e OKRs)
* **Árvore de OKRs:** Exibir os objetivos de cada colaborador diretamente dentro do perfil dele na aba "Membros" da Squad atual.
* **Atualização de Progresso:** Check-ins semanais com barra de progresso (%) ou valores numéricos.

### 3. Módulo de Ritmos (Feedbacks e 1:1s)
* **Botões Rápidos:** Adicionar um botão "Iniciar 1:1" ou "Enviar Elogio" diretamente na linha de cada funcionário (Isabella, João Lopes, etc.) no painel de Status Recente.
* **Mural de Elogios e Gestão de 1:1:** Agendamento de reuniões individuais, histórico de pautas e plano de ações.

### 4. Módulo de Desenvolvimento (PDI)
* **Planos de Desenvolvimento:** Criação de metas de carreira atreladas a competências fracas mapeadas na avaliação.

---

## 🔑 Perfis de Acesso (RBAC) - V2.0
* **Colaborador:** Visualiza e edita apenas seus próprios dados (suas metas, seus feedbacks, suas avaliações).
* **Gestor:** Visualiza os dados de seus liderados diretos e aprova metas/avaliações do time.
* **Admin (RH):** Acesso global a todas as configurações, dashboards consolidados e gerenciamento de usuários.

---

## 🗄️ Estrutura do Banco de Dados Complementar (Supabase)
* `users`: Dados cadastrais dos colaboradores (id, nome, email, cargo, user_role, manager_id).
* `cycles`: Ciclos de avaliação criados pelo RH.
* `evaluations`: Respostas das avaliações (ligada à tabela de membros existente).
* `okrs`: Metas vinculadas ao `member_id` da V1.0.
* `feedbacks`: Registro de feedbacks públicos e privados.
