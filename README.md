# Restful Booker - API Testing Portfolio

Projeto de portfólio voltado à prática de **Quality Assurance (QA)**, com foco em testes funcionais e automação de testes de API utilizando Postman.

O projeto utiliza a API pública Restful Booker para explorar endpoints, validar respostas HTTP, executar testes positivos e negativos e analisar comportamentos divergentes em relação aos resultados esperados.

## Objetivos

- Aplicar conceitos de testes funcionais de API.
- Compreender e validar métodos HTTP e códigos de resposta.
- Elaborar cenários de testes positivos e negativos.
- Validar estruturas JSON, campos e tipos de dados.
- Automatizar verificações utilizando JavaScript no Postman.
- Analisar e documentar resultados de execução.

## Tecnologias e Ferramentas

| Tecnologia         | Utilização                             |
| ------------------ | -------------------------------------- |
| Postman            | Execução e automação dos testes de API |
| JavaScript         | Scripts de validação e assertions      |
| Restful Booker API | API utilizada nos testes               |
| Git e GitHub       | Versionamento e publicação             |
| Markdown           | Documentação técnica                   |

## Aplicação sob Teste

**API:** Restful Booker

**Documentação oficial:** https://restful-booker.herokuapp.com/apidoc/index.html

**Base URL:** https://restful-booker.herokuapp.com

A Restful Booker é uma API pública de demonstração que disponibiliza operações relacionadas ao gerenciamento de reservas.

## Escopo dos Testes

O projeto contempla oito cenários de testes funcionais, divididos em duas categorias.

### 1. Consultas de reservas — GET

- Listar reservas.
- Consultar reserva existente.
- Consultar reserva inexistente.
- Consultar reserva utilizando ID alfanumérico.

### 2. Criação de reservas — POST

- Criar reserva com dados válidos.
- Criar reserva sem o campo obrigatório `firstname`.
- Criar reserva com `totalprice` de tipo inválido.
- Criar reserva sem o objeto obrigatório `bookingdates`.

## Automação

As verificações foram implementadas utilizando scripts JavaScript na seção **Post-response** do Postman.

Foram utilizadas assertions para validar:

- Códigos de resposta HTTP.
- Formato e estrutura das respostas JSON.
- Presença de campos esperados.
- Tipos de dados.
- Valores retornados pela API.

A execução automatizada foi realizada por meio do **Collection Runner**.

## Resultados da Execução

A Collection possui oito requisições e 22 verificações automatizadas.

| Resultado | Quantidade |
| --------- | ---------: |
| Passed    |         19 |
| Failed    |          3 |
| Total     |         22 |

**Taxa de aprovação: 86,4%.**

### Análise das divergências

Três verificações apresentaram resultados diferentes dos critérios esperados:

| Cenário                    | Esperado        | Observado                 |
| -------------------------- | --------------- | ------------------------- |
| Criação sem `firstname`    | 400 Bad Request | 500 Internal Server Error |
| `totalprice` inválido      | 400 Bad Request | 200 OK, com valor `null`  |
| Criação sem `bookingdates` | 400 Bad Request | 500 Internal Server Error |

Os resultados foram mantidos e documentados para demonstrar a análise do comportamento da API diante de entradas inválidas.

## Estrutura do Projeto

```text
restful-booker-api-testing/
├── postman/
│   └── Restful Booker - API Testing Portfolio.postman_collection.json
├── docs/
│   ├── test-plan.md
│   ├── test-scenarios.md
│   └── test-execution-report.md
└── README.md
```

## Como Executar os Testes

### Pré-requisitos

- Postman instalado.
- Acesso à internet.
- Acesso à API Restful Booker.

### Passo a passo

1. Clone este repositório:

```bash
git clone https://github.com/SEU-USUARIO/restful-booker-api-testing.git
```

2. Abra o Postman.

3. Importe o arquivo localizado em:

```text
postman/Restful Booker - API Testing Portfolio.postman_collection.json
```

4. Abra a Collection importada.

5. Confira a variável `baseUrl`, configurada na própria Collection:

```text
https://restful-booker.herokuapp.com
```

6. Selecione a Collection e execute pelo **Collection Runner**.

7. Consulte os resultados das verificações após a execução.

**Observação:** a API é pública e compartilhada. Os dados podem sofrer alterações entre execuções. As requisições POST criam registros na aplicação, portanto novas execuções podem gerar reservas adicionais.

## Documentação

Os documentos complementares estão disponíveis na pasta `docs/`:

- [Plano de Testes](docs/test-plan.md)
- [Cenários de Teste](docs/test-scenarios.md)
- [Relatório de Execução](docs/test-execution-report.md)

## Aprendizados

Durante o desenvolvimento deste projeto, foram praticados conceitos importantes de QA:

- Análise do comportamento de APIs REST.
- Planejamento e modelagem de testes.
- Testes funcionais positivos e negativos.
- Validação de respostas HTTP e estruturas JSON.
- Automação de testes com Postman e JavaScript.
- Interpretação de resultados e identificação de divergências.
- Documentação de evidências e resultados de testes.

## Considerações Finais

Este projeto representa uma etapa do meu desenvolvimento profissional na área de Quality Assurance, reunindo práticas de planejamento, execução, automação e análise de testes de API.

O objetivo foi desenvolver uma visão mais crítica sobre a qualidade de software, compreendendo não apenas como executar testes, mas também como interpretar seus resultados e documentar os comportamentos observados.

---

**Projeto desenvolvido para fins de estudo e construção de portfólio em Quality Assurance.**
