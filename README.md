# 🏢 Condominium Management System

### Arquitetura de Microserviços com Spring Boot

---

## 📌 Visão Executiva

O **Condominium Management System** é uma plataforma corporativa desenvolvida para gerenciar operações de condomínios de forma escalável, segura e modular.

A solução adota uma arquitetura baseada em **microserviços**, permitindo a evolução independente de cada domínio de negócio, alta disponibilidade e facilidade de manutenção.

---

## 🎯 Objetivos do Projeto

* Garantir **escalabilidade horizontal**
* Promover **baixo acoplamento entre domínios**
* Facilitar **manutenção e evolução contínua**
* Implementar **boas práticas de arquitetura corporativa**
* Suportar ambientes distribuídos e cloud-native

---

## 🏗️ Arquitetura da Solução

A aplicação segue princípios de:

* **Microservices Architecture**
* **Domain-Driven Design (DDD)**
* **API First Design**
* **Database per Service**

### 🔷 Componentes Principais

* **API Gateway** → Ponto único de entrada
* **Service Discovery** → Registro e descoberta de serviços
* **Config Server** → Centralização de configurações
* **Microserviços independentes**
* **Mensageria (event-driven, opcional)**

### 📊 Diagrama Simplificado

```
                ┌────────────────────┐
                │    API Gateway     │
                └─────────┬──────────┘
                          │
    ┌──────────────┬──────┼──────────────┬──────────────┐
    │              │      │              │              │
Funcionários   Administrativo  Contratos   Fornecedores   Financeiro
 Service         Service       Service      Service       Service
```

---

## 📦 Domínios / Microserviços

### 👨‍💼 Funcionários Service

Gestão de colaboradores do condomínio.

* Cadastro de funcionários
* Controle de cargos
* Gestão de vínculos

---

### 🏢 Administrativo Service

Gestão estrutural do condomínio.

* Cadastro de condomínios
* Unidades (apartamentos/casas)
* Gestão de moradores

---

### 📄 Contratos Service

Controle de contratos com terceiros.

* Cadastro de contratos
* Controle de vigência
* Alertas de expiração

---

### 🤝 Fornecedores Service

Gestão de parceiros e prestadores.

* Cadastro de fornecedores
* Classificação por serviço
* Histórico de relacionamento

---

### 💰 Financeiro Service (Contas a Pagar)

Gestão financeira.

* Contas a pagar
* Controle de pagamentos
* Relatórios financeiros

---

## ⚙️ Stack Tecnológica

| Categoria      | Tecnologia                  |
| -------------- | --------------------------- |
| Backend        | Java 17+, Spring Boot       |
| Cloud          | Spring Cloud                |
| Persistência   | JPA / Hibernate             |
| Banco de Dados | PostgreSQL / Oracle         |
| Build          | Maven / Gradle              |
| Containers     | Docker                      |
| Orquestração   | Kubernetes (opcional)       |
| Segurança      | Spring Security + JWT       |
| Mensageria     | RabbitMQ / Kafka (opcional) |

---

## 📁 Estrutura do Repositório

```
condominio-system/
│
├── gateway/
├── discovery-server/
├── config-server/
│
├── funcionarios-service/
├── administrativo-service/
├── contratos-service/
├── fornecedores-service/
├── financeiro-service/
│
└── shared-libraries/
```

---

## 🚀 Deploy e Execução

### 🔧 Pré-requisitos

* Java 17+
* Maven ou Gradle
* Docker (recomendado)
* Banco de dados configurado

### ▶️ Execução Local

```bash
# Clonar repositório
git clone https://github.com/italoaraujosantos/SGC-SistemasISACgit

# Acessar serviço
cd funcionarios-service

# Executar aplicação
mvn spring-boot:run
```

---

## 🔗 Comunicação entre Serviços

* **REST APIs** (Feign Client / WebClient)
* **Event-driven (opcional)** via mensageria
* **API Gateway como orquestrador de entrada**

---

## 🔐 Segurança

* Autenticação via **JWT**
* Autorização baseada em papéis (RBAC)
* Proteção centralizada via API Gateway
* Integração futura com **OAuth2 / Identity Providers**

---

## 📊 Observabilidade

* Logs centralizados (ELK Stack)
* Monitoramento com Prometheus + Grafana
* Health checks com Spring Actuator

---

## 🧪 Qualidade e Testes

* Testes unitários (JUnit, Mockito)
* Testes de integração (Spring Boot Test)
* Pipeline CI/CD (recomendado)

---

## 📈 Escalabilidade

* Serviços independentes escaláveis
* Deploy containerizado
* Pronto para ambientes cloud (AWS, Azure, GCP)

---

## 📌 Boas Práticas Adotadas

* Separação por contexto de domínio
* Uso de DTOs para comunicação
* Versionamento de APIs
* Baixo acoplamento entre serviços
* Configuração externa (12-factor app)

---

## 🤝 Contribuição

1. Fork do repositório
2. Criação de branch (`feature/<nome>`)
3. Commit das alterações
4. Push para o repositório
5. Abertura de Pull Request

---

## 📄 Licença

Este projeto está sob a licença a definir

---

## 📬 Contato

Projeto desenvolvido com foco em arquitetura corporativa moderna e boas práticas de engenharia de software.

---
