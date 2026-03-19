🏢 Sistema de Gestão de Condomínios

Sistema de gestão de condomínios desenvolvido com Java + Spring Boot, utilizando arquitetura de microserviços e integração com frontend em Angular 2.4.10.

O projeto foi projetado com foco em modularização por domínio, escalabilidade e manutenção facilitada, seguindo boas práticas como DDD (Domain Driven Design) e separação em camadas.

🚀 Tecnologias Utilizadas
🔧 Backend

Java 17+

Spring Boot

Spring Cloud (Eureka, Config Server, Gateway)

Spring Data JPA

Hibernate

Oracle Database

Maven

JWT (Spring Security)

🎨 Frontend

Angular 2.4.10

Node.js 7.5.0

TypeScript

🧪 Testes

JUnit

Mockito

🧩 Arquitetura

O sistema é baseado em microserviços independentes, onde cada módulo representa um domínio do negócio.

📌 Componentes principais

API Gateway

Entrada única para o frontend Angular

Responsável por roteamento e segurança

Service Discovery (Eureka)

Registro e descoberta dinâmica dos serviços

Config Server

Centralização de configurações

📦 Módulos do Sistema

Cada módulo é um microserviço independente com sua própria base de dados (ou schema no Oracle).

👨‍💼 Funcionários (funcionarios-service)

Cadastro e gestão de funcionários

Controle de cargos e vínculos com o condomínio

🏢 Administrativo (administrativo-service)

Gestão de condomínios, blocos e unidades

Configurações gerais

📄 Contratos (contratos-service)

Gestão de contratos de prestadores e fornecedores

Controle de vigência e renovações

🚚 Fornecedores (fornecedores-service)

Cadastro e gestão de fornecedores

Histórico de serviços

💰 Contas a Pagar (contas-pagar-service)

Controle financeiro

Registro e acompanhamento de despesas

🗂️ Estrutura do Projeto
condominio-system/
│
├── api-gateway/
├── service-discovery/
├── config-server/
│
├── funcionarios-service/
├── administrativo-service/
├── contratos-service/
├── fornecedores-service/
├── contas-pagar-service/
│
├── frontend-angular/
│
└── common-lib/
🧱 Padrão de Camadas (Backend)

Cada microserviço segue a seguinte estrutura:

src/main/java/com/condominio/<modulo>/
│
├── controller/      # Camada REST
├── service/         # Regras de negócio
├── repository/      # Acesso a dados (JPA)
├── domain/          # Entidades
├── dto/             # Objetos de transferência
├── config/          # Configurações
└── exception/       # Tratamento de erros
🔗 Comunicação entre Serviços

REST (Spring OpenFeign)

Autenticação via JWT

Integração via API Gateway

🔐 Segurança

Autenticação com JWT

Autorização baseada em perfis:

ADMIN

SINDICO

FUNCIONARIO

Validação centralizada no Gateway

▶️ Como Executar o Projeto
📋 Pré-requisitos

Java 17+

Maven

Node.js 7.5.0

Oracle Database configurado

🔄 Backend

Subir os serviços na ordem:

1. config-server
2. service-discovery
3. api-gateway
4. microserviços

Executar cada serviço:

mvn clean install
mvn spring-boot:run
🎨 Frontend
cd frontend-angular
npm install
npm start
🧪 Testes

Execução de testes unitários:

mvn test

Uso de JUnit para testes

Uso de Mockito para mock de dependências

Foco em testes de serviços e regras de negócio

📊 Boas Práticas Aplicadas

Separação por domínio (DDD)

Arquitetura em microserviços

Baixo acoplamento

Alta coesão

Uso de DTOs para comunicação

Tratamento centralizado de exceções

Testes automatizados

📈 Melhorias Futuras

Mensageria (RabbitMQ ou Kafka)

Observabilidade (Logs centralizados + métricas)

Circuit Breaker (Resilience4j)

Containerização com Docker

Orquestração com Kubernetes

Pipeline CI/CD



