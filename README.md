 📝 ToDo List API

Esta API REST implementa um sistema de **lista de tarefas (To‑Do List)**, permitindo criar, listar, editar e excluir tarefas.  
O projeto é desenvolvido em **Java com Spring Boot** e segue a arquitetura em camadas (Controller, Service, Repository) para separação de responsabilidades.  
Cada entidade `Todo` corresponde a uma tabela no banco de dados, mapeada via JPA.

---

 🚀 Tecnologias Utilizadas

- Java 17+
- Spring Boot
- Spring MVC
- Spring Data JPA (Hibernate)
- MySQL
- Swagger / OpenAPI (via Springdoc)
- Maven (com Maven Wrapper)
- Spring Boot DevTools (opcional)

> O Spring Data JPA simplifica o acesso ao banco MySQL, automatizando operações CRUD.

---

 🧠 Boas Práticas e Arquitetura

- Camadas Separadas (MVC): Controllers cuidam das requisições HTTP, Services da lógica de negócio e Repositories do acesso ao banco de dados.  
- Princípios SOLID: Classes com responsabilidade única, uso de interfaces e injeção de dependência.  
- DRY – Don’t Repeat Yourself: Evita duplicações de código e centraliza a lógica reutilizável.  
- Reutilização e Coesão: Uso de DTOs, validações e estrutura RESTful clara e coesa.

---

## ⚙️ Instalação e Execução Local

 1. Clonar o repositório:
```bash
git clone https://github.com/joaodevlopes/todo-list.git
cd todo-list/desafio-todolist
```
2. Configurar o banco de dados MySQL:
Crie um banco de dados no MySQL com o nome todo_db (ou outro de sua preferência) e atualize o arquivo src/main/resources/application.properties:

spring.datasource.url=jdbc:mysql://localhost:3306/todo_db
spring.datasource.username=seu_usuario
spring.datasource.password=sua_senha
spring.jpa.hibernate.ddl-auto=update

3. Executar a aplicação:
./mvnw spring-boot:run
A aplicação estará disponível em:
 http://localhost:8080
O Hibernate criará a tabela automaticamente com base na entidade Todo.

🗃️ Estrutura do Banco de Dados

A aplicação utiliza o MySQL como sistema de banco de dados, e o Spring Data JPA é responsável por mapear automaticamente a entidade `Todo` para a tabela `todo`. A estrutura da tabela é composta pelos seguintes campos:

- id: chave primária do tipo inteiro Long (BIGINT), gerada automaticamente com incremento. Representa o identificador único de cada tarefa.
- nome: campo de texto que armazena o título da tarefa. Exemplo: “Estudar Java”.
- descricao: campo de texto mais longo, usado para detalhar a tarefa. Exemplo: “Estudar orientação a objetos e coleções”.
- concluido: campo booleano TRUE OR FALSE (verdadeiro ou falso) que representa se a tarefa foi concluída.
- prioridade: campo numeral que indica o nível de prioridade da tarefa, podendo conter valores como 0 a 10.

A tabela é criada automaticamente no banco de dados ao rodar a aplicação pela primeira vez, caso o parâmetro `spring.jpa.hibernate.ddl-auto` esteja definido como `update`.

📘 Documentação Swagger

A API possui documentação interativa gerada com Swagger via Springdoc OpenAPI. Essa documentação pode ser acessada diretamente no navegador após iniciar o projeto localmente:

- Interface Swagger: `http://localhost:8080/swagger-ui/index.html`  

Através do Swagger UI é possível testar todos os endpoints diretamente do navegador, visualizar os parâmetros de entrada e examinar as respostas esperadas.

👨‍💻 Autor
João Gabriel Lopes
GitHub: @joaodevlopes
