# 🚀 Sistema de Agendamento - Arquitetura de Microsserviços

Projeto desenvolvido com o objetivo de estudar e aplicar conceitos de **arquitetura de microsserviços**, desenvolvimento de APIs REST, comunicação entre serviços, autenticação e persistência de dados utilizando diferentes bancos de dados.

O sistema é composto por diferentes serviços independentes, cada um responsável por uma parte específica da aplicação.

---

## 📌 Sobre o projeto

O projeto consiste em uma aplicação de **gerenciamento de tarefas e agendamentos**, desenvolvida utilizando Java e Spring Boot.

A aplicação foi estruturada seguindo uma arquitetura baseada em microsserviços, permitindo separar as responsabilidades do sistema em serviços independentes.

A comunicação entre os serviços é realizada através de APIs REST e, em determinados pontos, utilizando **OpenFeign**.

---

## 🏗️ Arquitetura

A aplicação é composta pelos seguintes serviços:

```text
                         ┌─────────────────────┐
                         │       Cliente       │
                         │  Frontend / API     │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │        BFF          │
                         │      :8084          │
                         └──────────┬──────────┘
                                    │
                 ┌──────────────────┼──────────────────┐
                 │                  │                  │
                 ▼                  ▼                  ▼
        ┌────────────────┐ ┌────────────────┐ ┌────────────────┐
        │    Usuário     │ │    Tarefas     │ │  Notificação   │
        │     :8080      │ │     :8081      │ │     :8082      │
        └───────┬────────┘ └───────┬────────┘ └────────────────┘
                │                  │
                ▼                  ▼
        ┌────────────────┐ ┌────────────────┐
        │   PostgreSQL   │ │    MongoDB     │
        └────────────────┘ └────────────────┘
```