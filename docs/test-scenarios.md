# Test Scenarios - Restful Booker API Testing

## 1. Introdução

Este documento apresenta os cenários de teste definidos e executados no projeto Restful Booker API Testing Portfolio.

Os cenários contemplam testes funcionais positivos e negativos, com validações de respostas HTTP, estrutura dos dados retornados, tipos de dados e comportamento da API diante de entradas inválidas.

## 2. Cenários de Teste

### TS-01 - Listar reservas

| Campo | Descrição |
|---|---|
| Método | GET |
| Endpoint | `/booking` |
| Objetivo | Verificar se a API retorna a lista de reservas cadastradas. |
| Pré-condição | API disponível. |
| Resultado esperado | Status 200 OK, resposta JSON contendo uma lista de reservas, com `bookingid` numérico em cada elemento. |
| Resultado observado | Resposta 200 OK, conteúdo JSON e lista de identificadores de reservas. |
| Status | Aprovado |

### TS-02 - Consultar reserva existente

| Campo | Descrição |
|---|---|
| Método | GET |
| Endpoint | `/booking/1` |
| Objetivo | Verificar a consulta de uma reserva existente. |
| Pré-condição | Existência de uma reserva com o ID utilizado. |
| Resultado esperado | Status 200 OK e retorno dos dados da reserva com estrutura e tipos esperados. |
| Resultado observado | Resposta 200 OK com os dados da reserva. |
| Status | Aprovado |

### TS-03 - Consultar reserva inexistente

| Campo | Descrição |
|---|---|
| Método | GET |
| Endpoint | `/booking/5146` |
| Objetivo | Verificar o comportamento da API ao consultar um identificador inexistente. |
| Pré-condição | ID não associado a uma reserva. |
| Resultado esperado | Status 404 Not Found. |
| Resultado observado | Resposta 404 Not Found com mensagem `Not Found`. |
| Status | Aprovado |

### TS-04 - Consultar reserva com ID alfanumérico

| Campo | Descrição |
|---|---|
| Método | GET |
| Endpoint | `/booking/abc` |
| Objetivo | Verificar o comportamento da API ao receber um identificador alfanumérico. |
| Pré-condição | Identificador utilizado não corresponde a uma reserva existente. |
| Resultado esperado | Status 404 Not Found. |
| Resultado observado | Resposta 404 Not Found com mensagem `Not Found`. |
| Status | Aprovado |

### TS-05 - Criar reserva com dados válidos

| Campo | Descrição |
|---|---|
| Método | POST |
| Endpoint | `/booking` |
| Objetivo | Verificar a criação de uma reserva utilizando dados válidos. |
| Dados de teste | Nome, sobrenome, preço numérico, pagamento booleano, datas válidas e necessidade adicional. |
| Resultado esperado | Status 200 OK, retorno de `bookingid` numérico e dados da reserva compatíveis com os enviados. |
| Resultado observado | Resposta 200 OK, identificador numérico e dados retornados conforme enviados. |
| Status | Aprovado |

### TS-06 - Criar reserva sem firstname

| Campo | Descrição |
|---|---|
| Método | POST |
| Endpoint | `/booking` |
| Objetivo | Verificar a validação de campo obrigatório ausente. |
| Dados de teste | Payload válido com o campo `firstname` removido. |
| Resultado esperado | Status 400 Bad Request, indicando rejeição controlada dos dados inválidos. |
| Resultado observado | Resposta 500 Internal Server Error. |
| Status | Reprovado |

### TS-07 - Criar reserva com totalprice inválido

| Campo | Descrição |
|---|---|
| Método | POST |
| Endpoint | `/booking` |
| Objetivo | Verificar a validação do tipo de dado do campo `totalprice`. |
| Dados de teste | Campo `totalprice` enviado como texto (`"duzentos"`). |
| Resultado esperado | Status 400 Bad Request, rejeitando o tipo de dado inválido. |
| Resultado observado | Resposta 200 OK. A reserva foi criada, porém o campo `totalprice` retornou como `null`. |
| Status | Reprovado |

### TS-08 - Criar reserva sem bookingdates

| Campo | Descrição |
|---|---|
| Método | POST |
| Endpoint | `/booking` |
| Objetivo | Verificar a validação de ausência do objeto obrigatório `bookingdates`. |
| Dados de teste | Payload válido com o objeto `bookingdates` removido. |
| Resultado esperado | Status 400 Bad Request, indicando rejeição controlada dos dados incompletos. |
| Resultado observado | Resposta 500 Internal Server Error. |
| Status | Reprovado |

## 3. Resumo dos Resultados

| Resultado | Quantidade |
|---|---:|
| Cenários aprovados | 5 |
| Cenários reprovados | 3 |
| Total | 8 |

Os cenários reprovados identificaram divergências entre os resultados esperados e o comportamento observado da API.

As divergências foram registradas para análise, sem alteração dos critérios de teste para forçar aprovação.

## 4. Observações

A API Restful Booker é pública e compartilhada. Portanto, os resultados podem variar em futuras execuções devido a alterações nos dados, disponibilidade da aplicação ou mudanças no comportamento da API.

Os resultados documentados representam as observações realizadas durante a execução deste projeto.
