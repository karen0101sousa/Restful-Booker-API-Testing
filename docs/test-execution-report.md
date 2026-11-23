# Test Execution Report - Restful Booker API Testing

## 1. Identificação da Execução

| Informação | Descrição |
|---|---|
| Projeto | Restful Booker — API Testing Portfolio |
| Aplicação | Restful Booker API |
| Tipo de teste | Testes funcionais de API |
| Ferramenta | Postman |
| Método de execução | Collection Runner |
| Total de cenários | 8 |
| Total de verificações automatizadas | 22 |

## 2. Ambiente de Testes

Os testes foram executados utilizando o Postman, com requisições HTTP direcionadas à API pública Restful Booker.

**Base URL:**

`https://restful-booker.herokuapp.com`

A Collection foi organizada em duas pastas:

- `01 - Booking`: testes de consulta de reservas.
- `02 - Validações e testes negativos`: testes de criação de reservas.

As verificações foram implementadas com scripts JavaScript na seção Post-response do Postman.

## 3. Resumo dos Resultados

A execução da Collection pelo Collection Runner apresentou os seguintes resultados:

| Resultado | Quantidade |
|---|---:|
| Passed | 19 |
| Failed | 3 |
| Total | 22 |

**Taxa de aprovação:** 86,4%.

**Taxa de reprovação:** 13,6%.

Os resultados representam as verificações automatizadas executadas, e não a quantidade de cenários de teste.

## 4. Análise dos Resultados

### 4.1 Verificações aprovadas

Das 22 verificações executadas, 19 foram aprovadas.

As verificações aprovadas contemplaram:

- Validação dos códigos de resposta HTTP.
- Validação do formato JSON.
- Validação da estrutura dos dados retornados.
- Verificação de campos obrigatórios nas respostas.
- Verificação dos tipos de dados.
- Validação dos dados retornados após a criação de uma reserva.

### 4.2 Verificações reprovadas

Três verificações apresentaram resultados diferentes dos critérios esperados.

| Cenário | Resultado esperado | Resultado observado |
|---|---|---|
| POST sem firstname | 400 Bad Request | 500 Internal Server Error |
| POST com totalprice inválido | 400 Bad Request | 200 OK, com `totalprice` retornado como `null` |
| POST sem bookingdates | 400 Bad Request | 500 Internal Server Error |

**Análise:**

- **Ausência de firstname:** a API retornou erro interno do servidor em vez de uma resposta de validação controlada.
- **totalprice inválido:** a API aceitou a requisição e criou a reserva, mas retornou o campo `totalprice` como `null`.
- **Ausência de bookingdates:** a API retornou erro interno do servidor diante da ausência de um objeto obrigatório.

Esses comportamentos representam divergências entre os resultados observados e os critérios definidos para os testes.

Como a aplicação é uma API pública de demonstração, os resultados devem ser interpretados considerando suas limitações e a possibilidade de mudanças no comportamento do serviço.

## 5. Conclusão

A execução permitiu validar os principais comportamentos selecionados da API Restful Booker, incluindo consultas, criação de reservas e tratamento de entradas inválidas.

A automação com Postman possibilitou executar verificações de forma organizada e identificar divergências entre o comportamento esperado e o comportamento observado.

As três verificações reprovadas foram mantidas no relatório, pois representam resultados relevantes para a análise de qualidade da API.

O projeto atingiu seu objetivo de praticar testes funcionais de API, elaboração de cenários, automação de verificações e análise de resultados.

## 6. Limitações

- A API utilizada é pública e compartilhada.
- Os dados podem ser alterados por outros usuários.
- Identificadores de reservas podem variar entre execuções.
- Os resultados representam o comportamento observado durante a execução documentada.
- A execução não contempla testes aprofundados de segurança ou performance.

## 7. Entregáveis da Execução

- Collection Postman exportada em formato v2.1.
- Scripts automatizados de validação.
- Plano de testes.
- Cenários de teste.
- Relatório de execução.
- Evidências das execuções, quando disponíveis.
