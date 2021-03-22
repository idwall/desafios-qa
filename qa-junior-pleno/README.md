# Desafio para a vaga de QA Junior e Pleno
## Parte 1 - Planejamento de testes
Objetivo: Criar um documento descrevendo os testes a serem realizados no blog da Idwall [blog.idwall.co](https://blog.idwall.co/)
### Escopo
* Os testes deverão cobrir **somente** a página principal
* Incluir na validação tudo o que for relevante para uma validação mínima da página. Exemplos: links para posts, caixas de pesquisa, menus etc.
* Os cenários/casos de testes devem armazenados na pasta ```1-planning```, especificados na linguagem [Gherkin](https://cucumber.io/docs/gherkin/reference/) ou em formato de planilha. No caso de planilha, especificar os testes utilizando **obrigatoriamente** as seguintes colunas: _Dados dos testes_, _Procedimento_ e _Resultado Esperado_
## Parte 2 - Automação dos testes
Objetivo: Automatizar dois cenários descritos no documento da **Parte 1**
### Escopo
* Utilizar o framework de teste de sua preferência (ex. JUnit, MSTest, RSpec, Cucumber, Cypress, TestCafé, Nightwatch etc.)
* Armazenar o código da automação na pasta ```2-automation```
* Criar também um README.md, com os passos necessários para configurar o ambiente e executar seus testes.
* Ponto extra se criar um ```Dockerfile``` :whale: para seu projeto :wink:
