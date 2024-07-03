# API-Barbearia
API em C# para um sistema CRUD de barbearia, utilizando DOT.NET Core 8.0, DDD, Entity Framework, Identity e JWT.


# Barber Shop API

Esta API foi desenvolvida em C# utilizando o .NET Core 8.0 para gerenciar o cadastro de clientes e o agendamento de horários para os serviços de uma barbearia. A aplicação utiliza Entity Framework para o acesso ao banco de dados, Identity para a autenticação e autorização de usuários, e JWT para validação dos usuários.

## Funcionalidades

- Cadastro de clientes
- Agendamento de horários para serviços
- Operações CRUD (Create, Read, Update, Delete) para clientes e agendamentos
- Autenticação e autorização de usuários utilizando JWT
- Documentação da API com Swagger

## Tecnologias Utilizadas

- .NET Core 8.0
- Entity Framework Core
- ASP.NET Core Identity
- JWT (JSON Web Tokens) para autenticação
- SQL Server
- Swagger para documentação da API

## Configuração do Projeto

### Requisitos

- [.NET Core SDK 8.0](https://dotnet.microsoft.com/download)
- [SQL Server](https://www.microsoft.com/sql-server/sql-server-downloads)
- [Visual Studio](https://visualstudio.microsoft.com/) ou qualquer IDE de sua preferência

1. Clone o repositório:

   git clone https://github.com/DIC/barber_shop_api.git
   cd barber_shop_api


2. Configure a string de conexão com o banco de dados no arquivo appsettings.json:

json
Copiar código
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=(localdb)\\mssqllocaldb;Database=BarberShopDb;Trusted_Connection=True;MultipleActiveResultSets=true"
  },
  "Jwt": {
    "Key": "sua_chave_secreta_aqui",
    "Issuer": "sua_issuer_aqui",
    "Audience": "sua_audience_aqui"
  }
}


3. Execute as migrações do Entity Framework para criar o banco de dados:

Copiar código
dotnet ef database update
Execute a aplicação:

Copiar código
dotnet run
Estrutura da API
Controllers

ClienteController
Endpoint: /api/clientes
Descrição: Este controlador fornece operações CRUD para gerenciar clientes.

Operações:
GET /api/clientes: Retorna a lista de clientes.
GET /api/clientes/{id}: Retorna um cliente específico.
POST /api/clientes: Cria um novo cliente.
PUT /api/clientes/{id}: Atualiza um cliente existente.
DELETE /api/clientes/{id}: Deleta um cliente.

AgendamentoController
Endpoint: /api/agendamentos
Descrição: Este controlador fornece operações CRUD para gerenciar agendamentos de horários.

Operações:
GET /api/agendamentos: Retorna a lista de agendamentos.
GET /api/agendamentos/{id}: Retorna um agendamento específico.
POST /api/agendamentos: Cria um novo agendamento.
PUT /api/agendamentos/{id}: Atualiza um agendamento existente.
DELETE /api/agendamentos/{id}: Deleta um agendamento.

AuthController
Endpoint: /api/auth
Descrição: Este controlador fornece endpoints para registro e login de usuários.

Operações:
POST /api/auth/register: Registra um novo usuário.
POST /api/auth/login: Realiza o login de um usuário.

DTOs
ClienteDTO
Descrição: Utilizado para transferir dados dos clientes entre as diferentes camadas da aplicação.

AgendamentoDTO
Descrição: Utilizado para transferir dados dos agendamentos entre as diferentes camadas da aplicação.

UsuarioDTO
Descrição: Utilizado para transferir dados de usuário, como e-mail e senha, especialmente para operações de registro e login.

UsuarioToken
Descrição: Utilizado para transferir as informações do token JWT emitido após a autenticação.

Data
ApplicationDbContext
Descrição: Define a estrutura do banco de dados para a aplicação, incluindo as tabelas para clientes e agendamentos, além de integrar a funcionalidade de autenticação e autorização fornecida pelo ASP.NET Core Identity.

Documentação da API
A documentação da API pode ser acessada através do Swagger no endpoint /swagger.



Este arquivo `README.md` fornece uma visão geral completa da API, incluindo suas funcionalidades, tecnologias utilizadas, configuração do projeto, estrutura dos controladores, DTOs e a documentação da API. 


