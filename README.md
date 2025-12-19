# Spring Boot Users API

API REST para cadastro e listagem de usuários, desenvolvida com Java e Spring Boot, com foco em organização em camadas (Controller, Service, Repository) e boas práticas de desenvolvimento.

---

## Tecnologias
- Java 17
- Spring Boot
- Spring Web
- Spring Data JPA
- Bean Validation
- H2 Database (em memória)
- Maven

---

## Estrutura do Projeto
- controller
- service
- repository
- dto
- entity

---

## Como executar o projeto

### Pré-requisitos
- Java 17+
- Maven (opcional, pois o projeto possui Maven Wrapper)

### Executando (Windows)
```bash
mvnw.cmd spring-boot:run
```

### Executando (Linux/Mac)
```bash
./mvnw spring-boot:run
```

### A aplicação subirá por padrão em:

http://localhost:8080

### Endpoints
Listar usuários

GET /users

### Exemplo:
http://localhost:8080/users

### Banco de Dados (H2)

O projeto utiliza H2 em memória para desenvolvimento e testes.

### Console do H2:
http://localhost:8080/h2-console

### Configurações de acesso:

JDBC URL:
jdbc:h2:mem:testdb

User:
sa

Password:
(em branco)

Observação: como o H2 está em memória, os dados são perdidos quando a aplicação é reiniciada.

### Exemplo de Entidade JPA

A entidade abaixo representa o modelo de usuário persistido no banco de dados, utilizando JPA e Hibernate.

```java
@Entity
public class User {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    private String name;
    private String email;
}
```

### Modelo de Dados

A entidade principal do sistema é User, responsável por representar os usuários cadastrados na aplicação.

Campos:

id (Long)

name (String)

email (String)

### Arquitetura da Aplicação

A aplicação segue o padrão de arquitetura em camadas:

### Controller
Responsável por receber as requisições HTTP e retornar as respostas.

### Service
Contém a regra de negócio da aplicação.

### Repository
Responsável pela comunicação com o banco de dados via Spring Data JPA.

### DTO
Utilizado para transferência de dados entre as camadas, evitando exposição direta das entidades.

### Possíveis Evoluções

Implementação de cadastro de usuários (POST)

Atualização e remoção de usuários (PUT / DELETE)

Validação de dados de entrada

Paginação e ordenação

Integração com banco de dados relacional (PostgreSQL ou MySQL)

Implementação de testes unitários

Documentação com Swagger/OpenAPI

### Autor

Igor Carvalho
Projeto desenvolvido para fins de estudo e portfólio backend com Java e Spring Boot.