# Desafio QA Junior Idwall – Teste Automatizado

Este projeto tem o intuito de instruir todos os passos a serem seguidos para a realização de um teste automatizado no blog da Idwall, referente a terceira parte do desafio para a vaga de QA Junior, proposto pela empresa Idwall, com o seguinte caso de teste:
```
Cenário: Pesquisar um post no blog da Idwall
	Quando acesso o blog da Idwall
	E clico na lupa
	E informo o título de um post existente
	E digito <ENTER>
	Então deve exibir o post pesquisado em uma página de resultados
```

## Primeiros Passos

Inicialmente, é necessário a instalação do Eclipse (versão JEE 2019-06 ou superior) como ambiente de desenvolvimento, o JDK (versão 12.0 ou superior).

### Pré-requisitos

Além da instalação das versões atualizadas do Eclipse e JDK (que já irão conter o Maven para build da automação e o JUnit para escrever os testes), é necessário também instalação do Selenium WebDriver para Java, o download do geckodriver, o driver para realizar testes com o navegador Firefox e o próprio Firefox na versão 69.0 ou superior.

Para instalar o Selenium, deve acessar a URL (http://www.selenium.org/download/), e na sessão ‘Selenium Cliente & WebDriver Language Bindings’ selecionar a versão para Java.
Para o geckodriver, não é necessário a instalação do mesmo, somente o download e instanciá-lo via código. A URL para download é (http://github.com/mozilla/geckodriver/releases) e selecionar o driver na versão v0.25 ou superior, no Sistema Operacional correspondente.


### Instalando o ambiente de desenvolvimento

Instalação do Eclipse IDE

```
Acessar a URL (http://eclipse.org) e clicar no botão download. Não é necessário a instalação do Eclipse, basta descompactá-lo e abrir o executável.
```
## Importanto o projeto para dentro do Eclipse

No repositório do Github existe uma pasta 3-automation, onde dentro dessa pasta está o arquivo TesteAutomatizado.zip;
Ao extrair o arquivo, verifique a pasta do projeto com o nome 'TesteIDwall';
Dentro do Eclipse, vá em FILE>IMPORT>GENERAL>EXISTING PROJECTS INTO WORKSPACE e clique no botão NEXT;
Na janela IMPORT PROJECTS, selecione a opção SELECT ROOT DIRECTORY e clique em BROWSE.., e selecione a mesma pasta do projeto 'TesteIDwall', e clique em FINISH.

### Objetivo do Teste

O intuito deste teste é realizar uma pesquisa na barra de busca por um post existente e retornar a pàgina de resultados com o post pesquisado. Porém, feito totalmente de forma automatizada dentro do Eclipse, sem a necessidade de abrir ou fechar o navegador manualmente.

### Realizando o Teste no Eclipse

Com o projeto 'TesteIDwall' importado, é necessário abrir a classe 'VerificarPostExistente', no campo TesteIDwall>src/main/java>(default package)>VerificarPostExistente.java e clicar duas vezes sobre a mesma.
Com a classe aberta, o seguinte código abaixo será exibido no Eclipse:
```
import org.junit.Test;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.firefox.FirefoxDriver;
import org.openqa.selenium.Keys;

public class VerificarPostExistente {

			@Test
			public void Pesquisar() {
			WebDriver driver = new FirefoxDriver();
			driver.manage().window().maximize();
			driver.get("https://blog.idwall.co/");
			driver.findElement(By.id("top-search")).click();
			driver.findElement(By.id("s")).sendKeys("Como criar uma política de segurança da informação");
			driver.findElement(By.id("s")).sendKeys(Keys.ENTER);
			driver.quit();
			}
}
```
Com o código aberto na tela, clique com o botão direito em qualquer linha do código>Run As>1 JUnit Test.

## Resultado do Teste

Após a execução do teste,  no menu inferior onde constam as abas 'Console', 'Progress', 'Markers',... existe a aba JUnit referente ao report status do Teste;
Do lado esquerdo consta o nome da classe testad VerificarPostExistente>Pesquisar, e do lado direito o Failure Trace, onde em caso de erro apareceria o log com o motivo do erro do teste.

## Ferramentas e frameworks necessários para realização do Teste

* [JDK](http://www.dropwizard.io/1.0.2/docs/) – Java Development Kit
* [Maven](https://maven.apache.org/) - Dependency Management
* [Selenium WebDriver](https://rometools.github.io/rome/) – Ferramenta para testes
* [Eclipse](https://maven.apache.org/) – Ambiente de Desenvolvimento
* [JUnit](https://rometools.github.io/rome/) – Framework para testes unitários em Java
* [GeckoDriver](https://rometools.github.io/rome/) – Framework para testes unitários em Java
* [Mozilla Firefox](https://www.mozilla.org/pt-BR/firefox/new/) - Navegador web

## Autor

* **Leandro Alves**  [Github](https://github.com/leandroalves011)

