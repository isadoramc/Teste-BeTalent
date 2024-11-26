# Relatório de API Testing - Restful Booker

## 1. Cenários

### 1.1 Autenticação

#### 1.1.1 Gerar token de autenticação
  Endpoint: POST /auth
  Descrição: Enviar credenciais válidas para gerar um token de autenticação.
  Entrada: {
    "username": "admin",
    "password": "password123"
}
  Resultado esperado:
    Código de status 200 OK.
    Retorno de um token válido.
  Resultado obtido: Token gerado corretamente. Código 200.

#### 1.1.2 Tentar gerar token com credenciais inválidas
  Endpoint: POST /auth
  Descrição: Testar credenciais inválidas para validar o comportamento de erro.
  Entrada: {
    "username": "invalid_user",
    "password": "wrong_password"
}
  Resultado esperado:
    Código de status 403 Forbidden.
    Retorno de uma mensagem de erro indicando falha na autenticação.
  Resultado obtido: Token não gerado. Código 403.

### 1.2 Gestão de reservas

#### 1.2.1 Criar uma nova reserva
  Endpoint: POST /booking
  Descrição: Criar uma nova reserva enviando os dados do cliente.
  Entrada: {
    "firstname": "John",
    "lastname": "Doe",
    "totalprice": 123,
    "depositpaid": true,
    "bookingdates": {
        "checkin": "2024-01-01",
        "checkout": "2024-01-10"
    },
    "additionalneeds": "Breakfast"
}
  Resultado esperado:
    Código de status 200 OK.
    Retorno dos dados da reserva criada, incluindo o bookingid.
  Resultado obtido: Reserva criada corretamente. Código 200.

#### 1.2.2 Buscar uma reserva específica
  Endpoint: GET /booking/{id}
  Descrição: Buscar uma reserva existente pelo seu ID.
  Entrada: {id} substituído pelo ID válido.
  Resultado esperado:
    Código de status 200 OK.
    Retorno dos detalhes da reserva correspondente.
  Resultado obtido: Reserva encontrada. Código 200.

#### 1.2.3 Listar todas as reservas
  Endpoint: GET /booking
  Descrição: Retornar uma lista de todas as reservas disponíveis.
  Resultado esperado:
    Código de status 200 OK.
    Retorno de uma lista de objetos com IDs de reservas.
  Resultado obtido: Reservas listadas. Código 200.

#### 1.2.4 Atualizar uma reserva existente
  Endpoint: PUT /booking/{id}
  Descrição: Atualizar os dados de uma reserva existente.
  Entrada: Dados da reserva com modificações.
  Resultado esperado:
    Código de status 200 OK.
    Retorno dos dados da reserva atualizados.
  Resultado obtido: Reserva atualizada, Código 200.

#### 1.2.5 Deletar uma reserva
  Endpoint: DELETE /booking/{id}
  Descrição: Deletar uma reserva específica pelo seu ID.
  Resultado esperado:
    Código de status 201 Created (conforme especificação da API).
    Confirmação do delete.
  Resultado obtido: Reserva deletada. Código 201.

### 1.3 Filtros e buscas

#### 1.3.1 Buscar reservas por nome
  Endpoint: GET /booking?firstname={firstname}
  Descrição: Retornar reservas filtradas pelo nome do cliente.
  Entrada: Nome no parâmetro firstname.
  Resultado esperado:
    Código de status 200 OK.
    Retorno de uma lista de reservas correspondentes.
  Resultado obtido: Retorno dos caracteres "[]". Código 200.

#### 1.3.2 Buscar reservas por data de check-in
  Endpoint: GET /booking?checkin={date}
  Descrição: Retornar reservas filtradas pela data de check-in.
  Entrada: Data no formato YYYY-MM-DD.
  Resultado esperado:
    Código de status 200 OK.
    Retorno de uma lista de reservas correspondentes.
    Resultado obtido: Reservas encontradas. Código 200.

#### 1.3.3 Buscar reservas por data de check-out
  Endpoint: GET /booking?checkout={date}
  Descrição: Retornar reservas filtradas pela data de check-out.
  Entrada: Data no formato YYYY-MM-DD.
  Resultado esperado:
    Código de status 200 OK.
    Retorno de uma lista de reservas correspondentes.
  Resultado obtido: Reservas encontradas. Código 200.
