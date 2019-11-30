### Central de Erros
### Objetivo
Em projetos modernos é cada vez mais comum o uso de arquiteturas baseadas em serviços ou microsserviços. Nestes ambientes complexos, erros podem surgir em diferentes camadas da aplicação (backend, frontend, mobile, desktop) e mesmo em serviços distintos. Desta forma, é muito importante que os desenvolvedores possam centralizar todos os registros de erros em um local, de onde podem monitorar e tomar decisões mais acertadas. Neste projeto vamos implementar um sistema para centralizar registros de erros de aplicações.

A arquitetura do projeto é formada por:

## Backend - API
Criar endpoints para serem usados pelo frontend da aplicação
criar um endpoint que será usado para gravar os logs de erro em um banco de dados relacional
a API deve ser segura, permitindo acesso apenas com um token de autenticação válido
## Frontend
deve implementar as funcionalidades apresentadas nos wireframes
deve ser acessada adequadamente tanto por navegadores desktop quanto mobile
deve consumir a API do produto
desenvolvida na forma de uma Single Page Application
## Observações
Se a aceleração tiver ênfase no backend (Java, Python, C#, Go, PHP, etc) a equipe deve obrigatoriamente implementar a API. A implementação do frontend é considerado um bônus importante
Se a aceleração tiver ênfase em frontend (React, Vue, Angular, etc) a equipe deve obrigatoriamente implementar o frontend da aplicação e o backend pode ser substituido por uma aplicação mock. A implementação da API é considerado um bônus importante
## Wireframes
Os wireframes a seguir servem para demonstrar as funcionalidades básicas da aplicação.

[Documento Codenation - Central de Erros](https://github.com/codenation-dev/squad-1-ad-java-softplan-1/blob/master/Codenation_%20acelerando%20a%20carreira%20de%20quem%20acelera%20o%20mundo.pdf)

## Git Guidelines

Todo commit deve ter um comentário que possua o mínimo de informações sobre as modificações feitas,
lembre-se de dar um `git pull` na branch master antes de criar uma nova branch ou
dar um `git push` na master.

## Ferramentas
* [Trello para gerenciamento de projetos;](https://trello.com/)
* [Postman](https://www.getpostman.com/)
* [Swagger](https://swagger.io/)
* [Sonar](https://www.sonarqube.org/)
* [Heroku](https://www.heroku.com/)
* [Node](https://nodejs.org/en/)
* [React](https://pt-br.reactjs.org/)
* [H2Database](https://www.h2database.com/html/main.html)
* [Java](https://www.h2database.com/html/main.html)
* [Spring](https://www.h2database.com/html/main.html)
* [Maven](https://www.h2database.com/html/main.html)
* [DBDiagram](https://dbdiagram.io/)

## Solução

### Classe Log
Devemos criar um pacote utilitário com métodos que retornem s mensagens de log para cada caso de uso:
Backend, FrontEnd e Mobile e Desktop, portanto ela deve ter métodos static que implementem a geração de Logs.

A classe de Log pode ser abstract para que as classes que utilizarem o Log implementem os métodos de Log de forma
personalizada.

* Entidade,
* Timestamp,
* Descrição,

## Lista de Tarefas
1. Criar a modelagem conceitual do BD;
2. Criar as entidades em java com base na modelagem feita (André);
3. Criar Repository(Guilherme) e Service(Eduardo);
4. Definir as rotas (controller) (Leonardo/Eduardo);
5. Testar as rotas com Postman(Ariel);
6. Autenticação e Autorização;
7. Criar as telas de front-end:
   - Cadastro de Usuário;
   - Login;
   - Consulta de erros;
   - (Opcional) Arquivo com erros que irão popular o banco de dados em x minutos;
8. Deploy (Heroku?)
9. Testes (Opcional)
10. Slides da apresentação;
# roupa_de_sapo
Squad 1 Aceleradev Java Florianópolis

## Fluxo de trabalho
Todas as novas *branches* devem ser criadas a partir da `staging`, para isso execute os seguintes comandos no seu terminal:
- ```git checkout staging``` -> entra na branch staging  <br />
- ```git pull origin staging``` -> atualiza seu repositório local com as modificações da staging <br />
- ```git checkout -b nome_da_sua_branch_de_trabalho``` -> cria e entra na sua branch de trabalho, (*é aqui onde você irá realizar todas as suas modificaçes, irá fazer commits e push*). <br />
Ao finalizar seu trabalho em sua branch local você pode fazer o merge dela com a staging. <br />
## Merge com staging
Entre em: https://github.com/Guiarrd/roupa_de_sapo/branches. <br /> <br />
Na seção *Active branches* procure a sua branch e aperte no botão **New pull request**. <br /> <br />
Você será redirecionado para uma nova página. Logo abaixo do título **Open a pull request** tem dois botões de spinner com uma seta **<-** entre eles. O da direita deve estar selecionado com a sua branch de trabalho e o da esquerda deve estar com a branch staging selecionada, caso não esteja assim selecione estas opções no *spinner*. Escreva uma mensagem sobre este *pull request* e aperte no botão **Create pull request**. Caso sua branch de trabalho possua algum conflito com a *staging* você não poderá dar o *merge* automaticamente, mas ainda poderá criar o *pull request*.<br /> <br />
Com o *pull request* criado caso não haja conflitos aperte no botão de **merge** na página do *pull request* criado e fim. Se houver conflitos você precisará resolvê-los localmente.
## Resolução de conflitos com IntelliJ
Abra o intelliJ, execute os comandos: <br />
- ```git checkout staging``` -> entra na branch staging  <br />
- ```git pull origin staging``` -> atualiza seu repositório local com as modificações da staging <br />
- ```git checkout nome_da_sua_branch_de_trabalho``` -> entra na sua branch de trabalho <br />
No canto inferior direito na barra de navegação click em Git: nome_da_sua_branch, no menu que abrir selecione a branch staging e aperte em *Merge into current*. Resolva os conflitos que surgirem e faça um **push**.
## Testando
Para testar com o Postman você pode utilizar o usuário pré cadastrado. Basta fazer a requisição do token com um POST no endpoint: http:localhost:8080/oauth/token passando no body um  *form-data* com os parâmetros:

- **grant_type**: password
- **username**: john@domain.com
- **password**: 123456 <br />

Na aba de authorization selecione *Basic Auth* e preencha os campos da seguinte forma:

- **Username**: codenation
- **Password**: 123 <br />

Você também pode criar um usuário na rota http://localhost:8080/user com um POST passando simplesmente o JSON contendo as informaçes do novo usuário e depois utilizar o email e senha cadastrados para conseguir um token e ficar autorizado a acessar as outras rotas da **API**.<br />

Em posse de um token válido você pode acessar qualquer rota da **API** realizando as requisições com autorização do tipo Bearer Token.
## Swagger

Nesse projeto foi utilizado o editor Swagger para a validação e documentação da API desenvolvida pelos integrantes da squad. Nesse editor estão descritos todos os endpoints com os métodos que executam e os respectivos parâmetros. Inclui também os modelos do banco de dados utilizado.

Pode ser acessado no endpoint: http://localhost:8080/swagger-ui.html

