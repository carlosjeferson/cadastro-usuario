```markdown
# 🧑‍💻 Projeto CRUD de Usuários — Spring Boot

Este projeto é uma aplicação Java desenvolvida com **Spring Boot** que implementa um **CRUD completo (Create, Read, Update, Delete)** de usuários.  
Cada usuário possui **nome** e **email**, e os dados são armazenados em um banco de dados **H2 em memória**.

---

## 🚀 Tecnologias Utilizadas

- **Java 17+**
- **Spring Boot**
  - Spring Web
  - Spring Data JPA
  - H2 Database
- **Maven**
- **Postman** (para testes dos endpoints)
- **IntelliJ IDEA** (ambiente de desenvolvimento)

---

## 📁 Estrutura do Projeto
```

src
└── main
├── java
│    └── com.jefferson.cadastro\_usuario
│         ├── controller        \# Camada responsável pelas rotas e endpoints
│         ├── business          \# Camada de regras de negócio (serviços)
│         └── infrastructure    \# Camada de persistência (entidades e repositórios)
└── resources
├── application.properties \# Configuração do banco e console H2
└── static / templates     \# (se houver conteúdo web)

````

---

## ⚙️ Configuração do Banco de Dados (H2)

O projeto usa o **H2 em memória**, facilitando os testes sem precisar de instalação local.

**Arquivo:** `src/main/resources/application.properties`

```properties
spring.application.name=cadastro-usuario

# Habilita o console do H2
spring.h2.console.enabled=true
spring.h2.console.path=/h2-console

# Configuração do banco
spring.datasource.url=jdbc:h2:mem:usuario
spring.datasource.driverClassName=org.h2.Driver
spring.datasource.username=sa
spring.datasource.password=

spring.jpa.database-platform=org.hibernate.dialect.H2Dialect
spring.jpa.show-sql=true
````

Após rodar a aplicação, acesse o console em:

👉 `http://localhost:8080/h2-console`

Use a URL JDBC: `jdbc:h2:mem:usuario`

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

#### 🔹 Buscar Usuário por ID

**GET** `/usuarios/{id}`

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

## 🧩 Testes

Os endpoints podem ser testados facilmente via **Postman** ou **Insomnia**.

Basta rodar a aplicação e enviar as requisições para:
`http://localhost:8080/usuarios`

-----

## 🧱 Camadas do Projeto

  * **Controller:** Recebe as requisições HTTP e retorna as respostas (camada REST).
  * **Business (Service):** Contém as regras de negócio e validações.
  * **Infrastructure:** Responsável pela persistência de dados (entidades e repositórios JPA).

-----

## 🧪 Como Executar o Projeto

1.  Clone o repositório:
    ```bash
    git clone [https://github.com/seuusuario/cadastro-usuario.git](https://github.com/seuusuario/cadastro-usuario.git)
    ```
2.  Acesse a pasta:
    ```bash
    cd cadastro-usuario
    ```
3.  Execute o projeto:
    ```bash
    mvn spring-boot:run
    ```
4.  Acesse no navegador:
    `http://localhost:8080/h2-console`

-----

## ✨ Autor

**Carlos Jeferson**

📧 [carlosjjs500214@gmail.com]

💻 Desenvolvedor Java | Entusiasta em Back-End e APIs REST

-----

## 🧾 Licença

Este projeto é de uso livre para fins de estudo e aprendizado.
