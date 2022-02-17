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
preenchimento de senha de acordo com algumas regras de sua escolha, respectivamente e um botão de confirmação.\ 
(Minimo 8 caracteres, deve possuír caracteres especiais, etc...)

Como o foco deste teste não está nos dados do back-end, para se realizar o login / cadastro, deverá ser utilizado a API mencionada acima, com o Resource 
*/users?email=XXX* passando apenas o e-mail para se obter os dados fake de usuário e 
armazená-los no aplicativo. Sugerimos o uso do SQLite, com o package acima, mas fica a sua escolha.

### Listagem de Albuns (Master)

Uma vez "logado" e com os dados do usuário em mãos, o próximo passo é a apresentação de todos os Albums de fotos que o usuário possúi em seu nome.

Para isso, desejamos a apresentação de uma tela de Listagem, estilo Master de Master/detail, com o Widget CardList, onde cada Card apresentará o nome do Album e uma opção
de exclusão caso o usuário assim deseje. 
 
* Não é necessário a chamada de um DELETE desta funcionalidade visto que a API é um sistema fake, porém a retirada da listagem é obrigatória.

* Cada Card no CardList deverá ser um link para a próxima tela.

### Listagem de Fotos (Master)

Ao ser selecionado um dos albums, desejamos a apresentação de uma tela de Listagem, estilo Master de Master/detail, com o Widget CardList, onde cada Card apresentará o 
título da Foto, um pequeno Thumbnail da Foto, o Preço desta foto (Valor fictício, porém no formato *R$ 9999,99*) e uma opção de exclusão caso o usuário assim deseje. 

* Não é necessário a chamada de um DELETE desta funcionalidade visto que a API é um sistema fake, porém a retirada da listagem é obrigatória.

* Cada Card no CardList deverá ser um link para a próxima tela.

### Venda de Fotos (Detail)

Nesta tela, desejamos que sejam apresentados os dados da Foto selecionada, assim como a possibilidade de serem alterados os dados, e a opção de venda de foto, onde 
apenas desejamos que seja gerada uma notificação (Podendo ser uma tela de transição animada) de venda efetuada com sucesso, apresentando a data da venda e posteriomente a 
opção de Download da imagem escolhida para o aplicativo.

* Não é necessário a chamada de um PUT/PATCH desta funcionalidade visto que a API é um sistema fake, porém a alteração dos dados deverá estar refletida no local 
de armazenamento do aplicativo escolhido acima (SQLite, por exemplo).
* É obrigatório ao clicar na opção de venda da foto que seja pedido a permissão de armazenamento de arquivos no aplicativo.

## Endpoints

Busca de Usuário por e-mail: [```GET /users?email=<E-mail fake presente na API>```](https://jsonplaceholder.typicode.com/users?email=Sincere@april.biz) \
Busca de Albums por usuário: [```GET /users/<ID>/albums```](https://jsonplaceholder.typicode.com/users/1/albums) \
Busca de Fotos por Album: [```GET /albums/<ID>/photos```](https://jsonplaceholder.typicode.com/albums/1/photos) 

* É obrigatório o uso de todos os endpoints acima no app, pois iremos aplica um teste de Rastreamento do sistema para averiguar que todos estejam sendo chamados com os 
dados dinâmicos, de acordo com os e-mails/ids retornados da API.

## Entrega

Um ponto importante para este teste é que gostariamos de avaliá-lo em algum aparelho fisíco, portanto é necessário que seja realizado a geração de um pacote 
instalável (*Apk ou *App) presente junto ao código para que possamos instalá-lo e utilizado nos nossos mobiles.

* Não é necessário o registro do aplicativo em nenhum serviço de distribuição digital de aplicativos, como Google Play ou App Store.

Caso precise de ajuda, entre e contato conosco:
* [Yury](mailto:yury@expensemobi.com.br)
* [Vinícius](mailto:vinicius@expensemobi.com.br)
