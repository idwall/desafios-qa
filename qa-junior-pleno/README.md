# Desafio para a vaga de QA Junior e Pleno
## Parte 1 - Planejamento de testes
Objetivo: Criar um documento descrevendo os testes a serem realizados no blog da Idwall [blog.idwall.co](https://blog.idwall.co/)
### Escopo
* Os testes deverão cobrir **somente** a página principal
* Incluir na validação tudo o que for relevante para uma validação mínima da página. Exemplos: links para posts, caixas de pesquisa, menus etc.
* Os cenários/casos de testes devem armazenados na pasta ```1-planning```, especificados na linguagem [Gherkin](https://cucumber.io/docs/gherkin/reference/) ou em formato de planilha. No caso de planilha, especificar os testes utilizando **obrigatoriamente** as seguintes colunas: _Dados dos testes_, _Procedimento_ e _Resultado Esperado_
## Parte 2 - Execução dos testes
Objetivo: Executar os testes planejados na Parte 1, evidenciar os testes executados, criar métricas de execução e registro de defeitos.
### Escopo
* Armazenar na pasta ```2-execution``` métricas dos testes executados (sumário da execução, total de casos de teste _passed_, _failed_ etc.)
* Armazenar também um registro de defeitos encontrados durante a execução, em formato de planilha.
* Os defeitos devem ser descritos de uma maneira que seja de fácil compreensão aos possíveis envolvidos (desenvolvedores, outros QAs, gerentes de projeto etc.). Utilize como referência [este post do CartoonTester](https://cartoontester.blogspot.com/2012/02/art-of-bug-reporting.html) 
* Não se esqueça de evidenciar os defeitos encontrados adequadamente!
## Parte 3 - Automação dos testes
Objetivo: Automatizar um cenário/caso de teste do [blog da Idwall](https://blog.idwall.co/)
### Escopo
* Automatizar o seguinte caso de teste:
```
Cenário: Pesquisar um post no blog da Idwall
    Quando acesso o blog da Idwall
    E pesquiso um post informando um título existente
    Então deve exibir o post pesquisado em uma página de resultados
```
* Utilizar o framework de teste de sua preferência (ex. JUnit, MSTest, RSpec, Cucumber, Cypress, TestCafé, Nightwatch etc.)
* Armazenar o código da automação na pasta ```3-automation```
* Criar também um README.md, com as instruções necessárias para executar a automação.
* Lembre-se que a máquina de quem efetuará a avaliação nem sempre contém todos os pacotes, programas e afins, necessários para a execução. Portanto, seja bem descritivo! 