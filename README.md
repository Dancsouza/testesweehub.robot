# testesweehub.robot

Teste Técnico QA - Blog do Agi & Dog API
Este repositório contém a automação de testes para os desafios Web (Blog do Agi) e API (Dog API), utilizando Robot Framework.

Tecnologias e Bibliotecas
Linguagem: Python

Framework: Robot Framework

Web: Browser Library (baseada em Playwright)

API: RequestsLibrary

Automação Web (Blog do Agi)
Os cenários automatizados cobrem a funcionalidade de pesquisa do blog:

Busca com sucesso: Valida se termos existentes retornam resultados.

Busca sem resultados: Valida a mensagem de erro para termos inexistentes.

Automação API (Dog API)
Validação de integridade dos endpoints:

GET /breeds/list/all: Valida se o status é 200 e se a estrutura do JSON contém a lista de raças.

GET /breed/{breed}/images: Valida se o retorno é uma lista de URLs de imagens.

GET /breeds/image/random: Valida a estrutura da resposta para uma imagem aleatória.

Como Executar Localmente
1. Pré-requisitos
Possuir o Python 3.10+ instalado.

(Opcional) Criar um ambiente virtual: python -m venv venv e ativá-lo.

2. Instalação
Instale as dependências listadas no arquivo requirements.txt:

Bash
pip install -r requirements.txt
Após instalar a Browser Library, é necessário inicializar os binários do Playwright:

Bash
rfbrowser init
3. Execução dos Testes
Para rodar todos os testes (Web e API) e gerar os relatórios em uma pasta específica:

Bash
robot -d ./results tests/

Autor
Nome: Danilo Souza

LinkedIn: https://www.linkedin.com/in/danilo-carlos-de-souza-04077868/
