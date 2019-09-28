### Central de Erros
### Objetivo
Em projetos modernos é cada vez mais comum o uso de arquiteturas baseadas em serviços ou microsserviços. Nestes ambientes complexos, erros podem surgir em diferentes camadas da aplicação (backend, frontend, mobile, desktop) e mesmo em serviços distintos. Desta forma, é muito importante que os desenvolvedores possam centralizar todos os registros de erros em um local, de onde podem monitorar e tomar decisões mais acertadas. Neste projeto vamos implementar um sistema para centralizar registros de erros de aplicações.

A arquitetura do projeto é formada por:

## Backend - API
criar endpoints para serem usados pelo frontend da aplicação
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

## Git Guidelines

Todo commit deve ter um comentário que possua o mínimo de informações sobre as modificações feitas,
lembre-se de dar um `git pull` na branch master antes de criar uma nova branch ou
dar um `git push` na master.

## Solução

### Classe Log
Devemos criar um pacote utilitário com métodos que retornem as mensagens de log para cada caso de uso:
Backend, FrontEnd e Mobile e Desktop, portanto ela deve ter métodos static que implementem a geração de Logs.

* Entidade
* Timestamp
* Descrição

