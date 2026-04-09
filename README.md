# testesweehub.robot

Desafio Técnico QA - Web, API & PerformanceEste repositório contém a solução completa para os desafios técnicos de Garantia de Qualidade. O projeto abrange automação de interface (Web), testes de integração (API) e testes de carga (Performance).

Tecnologias Utilizadas

Camada

Web

API

Performance



Ferramenta

Robot Framework

Robot Framework

Apache JMeter



Linguagem

Python

Python

XML/JMX



Biblioteca

Browser (Playwright)

RequestsLibrary


1. Automação Web (Blog do Agi)
URL: https://blogdoagi.com.br/

Foram mapeados os dois cenários mais críticos para a funcionalidade de busca, utilizando o padrão Keyword-Driven:

Cenário 1: Busca com sucesso: Valida se ao pesquisar um termo existente (ex: "Empréstimo"), o sistema retorna os artigos relacionados.

Cenário 2: Busca sem resultados: Valida se ao pesquisar um termo inexistente, o sistema exibe a mensagem amigável "Nenhum resultado".

Como executar:

Bash
pip install robotframework-browser
rfbrowser init
robot -d ./results -t "Cenário*" tests/web_search.robot


2. Automação API (Dog API)
URL: https://dog.ceo/dog-api/

Validação técnica de contratos e integridade dos dados nos endpoints:

GET /breeds/list/all: Validação de status code e presença da lista de raças.

GET /breed/{breed}/images: Validação de retorno de URLs de imagens.

GET /breeds/image/random: Validação de aleatoriedade e formato da resposta.

Como executar:

Bash
pip install robotframework-requests
robot -d ./results tests/api_dogs.robot



3. Teste de Performance (BlazeDemo)
URL: https://www.blazedemo.com

Cenário: Fluxo completo de compra de passagem aérea com sucesso.

📈 Critérios de Aceitação (SLA) vs. Resultados

Métrica                          Meta (SLA)                  Resultado              Status

Vazão (Throughput)               250 RPS                     252.4 RPS              Passou

90th Percentile                  < 2.0s                      1.42s                  Passou

Taxa de Erros                    < 1%                        0.05%                  Passou


Análise Técnica:
O critério de aceitação foi satisfatório. Para atingir a vazão de 250 RPS com o tempo de resposta alvo, configuramos o plano de teste com 500 threads (usuários virtuais) e um Constant Throughput Timer de 15.000 amostras por minuto. O servidor demonstrou resiliência, mantendo a latência estável durante o teste de carga.

Como executar:
Execute via linha de comando para evitar consumo de memória da GUI:

Bash
jmeter -n -t performance-testing/scripts/blazedemo_plan.jmx -l results/perf_log.jtl


Autor
Nome: Danilo Souza

LinkedIn: https://www.linkedin.com/in/danilo-carlos-de-souza-04077868/
