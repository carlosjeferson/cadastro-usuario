```markdown
# 🧑‍💻 Projeto CRUD de Usuários — Spring Boot

Este projeto é uma aplicação Java desenvolvida com **Spring Boot** que implementa um **CRUD completo (Create, Read, Update, Delete)** de usuários.
Cada usuário possui **nome** e **email**, e os dados são persistidos no banco de dados **PostgresSQL**, garantindo persistência robusta.

---

## 🚀 Tecnologias Utilizadas

- **Java 17+**
- **Spring Boot**
  - Spring Web
  - Spring Data JPA
  - **PostgresSQL Driver**
- **Maven**
- **Postman** (para testes dos endpoints)
- **IntelliJ IDEA** (ambiente de desenvolvimento)

---

## 📁 Estrutura do Projeto

```

src
└── main
├── java
│    └── com.jefferson.cadastro\_usuario
│         ├── controller        \# Camada responsável pelas rotas e endpoints
│         ├── business          \# Camada de regras de negócio (serviços)
│         └── infrastructure    \# Camada de persistência (entidades e repositórios)
└── resources
├── application.properties \# Configuração do banco
└── static / templates     \# (se houver conteúdo web)

````

---

## ⚙️ Configuração do Banco de Dados (PostgresSQL)

O projeto utiliza o **PostgresSQL**. Para executá-lo, garanta que o serviço PostgreSQL esteja rodando localmente (ou via Docker) e configure as credenciais no arquivo abaixo.

**Arquivo:** `src/main/resources/application.properties`

```properties
spring.application.name=cadastro-usuario

# Configuração do banco PostgresSQL
spring.datasource.url=jdbc:postgresql://localhost:5432/nomedobanco
spring.datasource.username=seu_usuario
spring.datasource.password=sua_senha
spring.datasource.driverClassName=org.postgresql.Driver

spring.jpa.database-platform=org.hibernate.dialect.PostgreSQLDialect
spring.jpa.show-sql=true

# Opção de configuração do DDL (Para criar as tabelas automaticamente)
spring.jpa.hibernate.ddl-auto=update
````

**Lembrete:** Substitua `nomedobanco`, `seu_usuario` e `sua_senha` pelas suas credenciais reais.

-----

## 🧠 Endpoints do CRUD

#### 🔹 Criar Usuário

**POST** `/usuarios`

```json
{
  "nome": "Jefferson Carlos",
  "email": "jefferson@email.com"
}
```

#### 🔹 Listar Todos os Usuários

**GET** `/usuarios`

#### 🔹 Buscar Usuário por Email

**GET** `/usuarios/email`

#### 🔹 Atualizar Usuário

**PUT** `/usuarios/{id}`

```json
{
  "nome": "Jefferson Atualizado",
  "email": "novoemail@email.com"
}
```

#### 🔹 Deletar Usuário

**DELETE** `/usuarios/{id}`

-----

## 🧪 Testes e Qualidade de Código

A qualidade do código foi uma prioridade neste projeto, com foco em código limpo (Clean Code) e testabilidade.

  * **Testes Unitários (JUnit):** O projeto inclui cobertura de testes unitários nas camadas de **Business (Service)** e **Controller**, garantindo a robustez das regras de negócio e a estabilidade dos *endpoints*.
  * **Boas Práticas:** A arquitetura em camadas facilita a manutenção, a injeção de dependências e a aplicação dos princípios **SOLID**.

Os endpoints podem ser testados facilmente via **Postman** ou **Insomnia**.

Basta rodar a aplicação e enviar as requisições para:
`http://localhost:8080/usuarios`

-----

## 🧱 Camadas do Projeto

  * **Controller:** Recebe as requisições HTTP e retorna as respostas (camada REST).
  * **Business (Service):** Contém as regras de negócio e validações.
  * **Infrastructure:** Responsável pela persistência de dados (entidades e repositórios JPA).

-----

## 🚀 Como Executar o Projeto

1.  Clone o repositório:
    ```bash
    git clone [[https://github.com/seuusuario/cadastro-usuario.git](https://github.com/seuusuario/cadastro-usuario.git)]
    ```
2.  Acesse a pasta:
    ```bash
    cd cadastro-usuario
    ```
3.  Execute o projeto:
    ```bash
    mvn spring-boot:run
    ```

-----

## ✨ Autor

**Carlos Jeferson**

📧 [carlosjjs500214@gmail.com]

💻 Desenvolvedor Java | Entusiasta em Back-End e APIs REST

-----

## 🧾 Licença

Este projeto é de uso livre para fins de estudo e aprendizado.

```
```
