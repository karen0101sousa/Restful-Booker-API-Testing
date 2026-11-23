# Test Plan - Restful Booker API Testing

## 1. Identificação do Projeto

| Informação | Descrição |
|---|---|
| Projeto | Restful Booker — API Testing Portfolio |
| Aplicação | Restful Booker API |
| Tipo de projeto | Testes funcionais de API |
| Ferramenta principal | Postman |
| Base URL | https://restful-booker.herokuapp.com |
| Objetivo | Praticar e demonstrar conhecimentos de testes funcionais, validações, testes negativos e automação de API. |

## 2. Objetivo

Este projeto tem como objetivo validar o comportamento dos endpoints da API Restful Booker, verificando se as respostas recebidas atendem aos comportamentos esperados.

O projeto busca aplicar conceitos de Quality Assurance, incluindo análise de requisitos, elaboração de cenários de teste, execução de testes funcionais, validações de respostas HTTP e automação de verificações utilizando Postman.

Também tem como objetivo identificar e documentar comportamentos divergentes em relação às expectativas definidas para os testes.

## 3. Escopo dos Testes

### 3.1 Dentro do escopo

- Listagem de reservas.
- Consulta de reservas existentes.
- Consulta de reservas inexistentes.
- Consulta utilizando identificadores alfanuméricos.
- Criação de reservas com dados válidos.
- Criação de reservas com dados inválidos ou campos obrigatórios ausentes.
- Validação de status codes HTTP.
- Validação do formato e estrutura das respostas.
- Validação de campos, tipos de dados e valores retornados.
- Automação dos testes utilizando scripts do Postman.
- Execução dos testes através do Collection Runner.

### 3.2 Fora do escopo

- Testes de performance e carga.
- Testes de segurança aprofundados.
- Testes de interface gráfica.
- Testes de compatibilidade entre navegadores.
- Testes de infraestrutura e monitoramento.
- Testes completos de todos os endpoints disponibilizados pela API.

## 4. Estratégia de Testes

Os testes serão realizados utilizando uma abordagem funcional, combinando execução manual e automação.

### 4.1 Testes exploratórios e manuais

Inicialmente, serão realizadas requisições para explorar o comportamento da API, observar as respostas e identificar possíveis divergências entre o comportamento observado e o esperado.

### 4.2 Testes funcionais

Serão avaliados os comportamentos dos endpoints selecionados, considerando entradas válidas e inválidas, campos obrigatórios, tipos de dados e respostas HTTP.

### 4.3 Testes negativos

Serão utilizados dados inválidos ou incompletos para verificar como a API responde a situações inesperadas ou entradas que não atendem aos requisitos definidos.

### 4.4 Automação de testes

As verificações serão automatizadas utilizando scripts JavaScript no Postman, com assertions para validar status codes, estrutura das respostas, tipos de dados e valores retornados.

Os testes automatizados serão organizados em uma Collection e executados utilizando o Collection Runner.

## 5. Ambiente e Ferramentas

| Ferramenta | Utilização |
|---|---|
| Postman | Execução e automação dos testes de API |
| JavaScript | Implementação das verificações automatizadas |
| Restful Booker API | API utilizada como objeto de teste |
| Git e GitHub | Versionamento e publicação do projeto |
| Markdown | Documentação do projeto |

## 6. Critérios de Entrada e Saída

### 6.1 Critérios de entrada

- API disponível para acesso.
- Endpoints selecionados identificados.
- Requisições configuradas no Postman.
- Cenários de teste definidos.
- Dados de teste preparados.

### 6.2 Critérios de saída

- Todos os cenários planejados executados.
- Resultados das verificações registrados.
- Comportamentos divergentes documentados.
- Scripts automatizados revisados.
- Collection exportada e validada através de importação.

A aprovação de todos os testes não é obrigatória para o encerramento, desde que os resultados e as divergências identificadas estejam analisados e documentados.

## 7. Riscos e Limitações

- A API utilizada é pública e compartilhada, podendo sofrer alterações realizadas por outros usuários.
- Dados e identificadores de reservas podem mudar entre execuções.
- A disponibilidade da API pode sofrer instabilidades.
- Respostas podem variar ao longo do tempo, impactando a reprodução dos resultados.
- Os resultados representam o comportamento observado durante as execuções realizadas e não garantem a ausência de defeitos na aplicação.

## 8. Entregáveis

- Plano de testes.
- Cenários de testes documentados.
- Collection Postman com scripts automatizados.
- Relatório de execução dos testes.
- Evidências das execuções.
- README com apresentação do projeto e instruções para utilização.
- Repositório GitHub contendo os artefatos do projeto.
