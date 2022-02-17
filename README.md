# Teste para Sêniors - App Flutter

Para este teste, será necessário ao dev criar um app em Flutter que irá consultar uma api de venda de fotos, com tela de login e listagem de dados fake.

Stack desejada:

* Flutter:
  * [flutter.dev](https://flutter.dev/)
  * [Flutterando](https://flutterando.com.br/)
* API:
  * [Dados fake](https://jsonplaceholder.typicode.com/)
* Banco de Dados:
  * [SQLite](https://sqlite.org/index.html)
  * [SQFlite](https://pub.dev/packages/sqflite) 
* TDD:
  * [Testes unitários](https://resocoder.com/flutter-clean-architecture-tdd/) apenas (Não são necessários testes integrados)
* Geração de App:
  * Android 
  * iOS (Opcional)

## App

Serão necesários a criação de 3 telas (Login / Cadastro, Listagem de Albuns, Listagens de Fotos e Compra de Fotos) 

### Login / Cadastro

Nesta tela, serão apresenados 2 campos de texto, um para o e-mail dos usuários, outro para a senha, sendo que ambos deverão possuir validação de Texto no formato E-mail e 
preenchimento de senha de acordo com algumas regras de sua escolha (Minimo 8 caracteres, deve possuír caracteres especiais, etc...), respectivamente e um botão de confirmação.

Como o foco deste teste não está nos dados do back-end, para se realizar o login / cadastro, deverá ser utilizado a API mencionada acima, com o Resource 
[/users?email=XXX](https://jsonplaceholder.typicode.com/users?email=Sincere@april.biz) passando apenas o e-mail para se obter os dados fake de usuário e 
armazená-los no aplicativo. Sugerimos o uso do SQLite, com o package acima, mas fica a sua escolha.

### Listagem de Albuns (Master)
### Listagem de Fotos (Master)
### Compra de Fotos (Detail)

Ao consultar a API de câmbio deverá ser informado a data atual.

A API a ser consultada será a: https://olinda.bcb.gov.br/olinda/servico/PTAX/versao/v1/odata/CotacaoDolarDia(dataCotacao=@dataCotacao)?@dataCotacao='11-01-2021'&$top=100&$skip=0&$format=json&$select=cotacaoCompra,cotacaoVenda,dataHoraCotacao

Nela, deverá ser informada apenas a data de cotação atual. (Parâmetro `@dataCotacao`)

O retorno da consulta será o seguinte: ![Response Body](https://user-images.githubusercontent.com/1773788/141181294-28f0d93e-2a74-416f-91a2-0ae9875def09.png)

As 3 informações principais deverão ser armazenadas no bano de dados de sua escolha (Schema fica a sua escolha também)


## Endpoints

* Consultar Câmbio Atual: ```GET /cambio/atual``` - Ultima taxa gerada e processada por nós da plataforma de câmbio. 

Caso precise de ajuda, entre e contato conosco:
* [Yury](mailto:yury@expensemobi.com.br)
* [Vinícius](mailto:vinicius@expensemobi.com.br)
