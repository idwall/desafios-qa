Parte do dia-a-dia na IDwall inclui desenvolvermos e aprimoramos *APIs* oferecendo experiências de integração de APIs para nossos clientes.

Como nós nos divertimos trabalhando, às vezes trabalhamos para nos divertir! Sua missão é desenvolver uma automação para uma de nossas principais APIs. 

Do que se trata esta API? https://docs.idwall.co/docs/overview

Como posso fazer a integração? 
- Criando um relatório: https://docs.idwall.co/docs/what-is-a-report
- Obtendo informações de um relatório: https://docs.idwall.co/docs/get-report

Para início do desafio, é necessário solicitar um Token de Autorização. Normalmente, enviamos junto com o teste para seu e-mail.

O desafio está dividido em duas partes:
1. Cenários conhecidos
2. Cenário não conhecido

## Cenários conhecidos
1. Onde os dados de envio estão vazios e nossa API retorna erros controlados.

Massa de dados a ser utilizada:
```bash
POST https://api-v2.idwall.co/relatorios
{
    "matriz": "consultaPessoaDefault",
    "parametros": {
        "cpf_data_de_nascimento": "",
        "cpf_nome": "",
        "cpf_numero": ""
    }
}

Response: 
{
    "error": "Bad Request",
    "message": "É necessário enviar ao menos um parâmetro para criação do relatório.",
    "status_code": 400
}
```

2. Onde os dados de envio estão inconsistentes e nossa API retorna validações controladas alertando as irregularidades. Considerar os dois cenários a seguir:

```bash
Cenário 1: Regra de data diferente

POST https://api-v2.idwall.co/relatorios
{
    "matriz": "consultaPessoaDefault",
    "parametros": {
        "cpf_data_de_nascimento": "28/09/1988",
        "cpf_nome": "Gabriel Oliveira",
        "cpf_numero": "07614917677"
    }
}

Response: 
{
    "result": {
        "numero": "XPTO-12341234141234",
        "status": "CONCLUIDO",
        "nome": "consultaPessoaDefault",
        "mensagem": "Inválido. [ERROR] Não foi possível validar: Data de nascimento informada está divergente da constante na base de dados da Secretaria da Receita Federal do Brasil.",
        "resultado": "INVALID",
        ...
    },
    "status_code": 200
}
```
```bash
Cenário 2: Regra de nome diferente

POST https://api-v2.idwall.co/relatorios
{
    "matriz": "consultaPessoaDefault",
    "parametros": {
        "cpf_data_de_nascimento": "25/05/1987",
        "cpf_nome": "Gabriel Oliveira",
        "cpf_numero": "07614917677"
    }
}

Response:
{
    "result": {
        "numero": "XPTO-12341234141234",
        "status": "CONCLUIDO",
        "nome": "consultaPessoaDefault",
        "mensagem": "Inválido. [INVALID] Nome diferente do cadastrado na Receita Federal.",
        "resultado": "INVALID",
        ...
    },
    "status_code": 200
}
```

## Cenário não conhecido
O cenário não conhecido deve ser preparado para o caso onde o relatório possui os dados de input condizentes aos dados reais de uma pessoa. No caso, para não expor os dados verdadeiros de algum usuário, considere montar um cenário onde podemos validar o status como **CONCLUIDO** e o resultado como **VALID**. O sucesso deste cenário será validado com dados de um dos nossos integrates do time :)

```bash
Cenário 1: Regra de data diferente

POST https://api-v2.idwall.co/relatorios
{
    "matriz": "consultaPessoaDefault",
    "parametros": {
        "cpf_data_de_nascimento": "Data verdadeira",
        "cpf_nome": "Nome verdadeiro",
        "cpf_numero": "CPF verdadeiro"
    }
}

Response: 
{
    "result": {
        "numero": "XPTO-12341234141234",
        "status": "CONCLUIDO",
        "nome": "consultaPessoaDefault",
        "mensagem": "Válido.",
        "resultado": "VALID",
        ...
    },
    "status_code": 200
}
```

## Como entregar?
Utilize alguns dos frameworks mais conhecidos de mercado orientado a tests funcionais para APIs. Um exemplo muito utilizado é o [Cucumber](https://cucumber.io) em suas respectivas linguagens Ruby, Python, etc.

- Descreva como executar os testes;
- Caso tenha conhecimento, utilize Docker para execução dos testes;
- Adicione observações caso necessário;

### Dicas
 - Utilize a documentação da IDwall API para guiar nos cenários de testes;
 - Os exemplos ilustram situações do dia-a-dia;
 - Qualquer dúvida, independênte de qual seja, nos envie um e-mail;
