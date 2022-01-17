# node-url-shortening-service

Serviço de encurtamento de URLs feito em NodeJS e Express.

## Live Demo

Encurtar a URL - https://url-shortener-unyleya.herokuapp.com/shorten?url=http://www.google.com <br>
Vistar URL encurtada - http://url-shortener-unyleya.herokuapp.com/v

## Rodando localmente

Certifique-se de ter os [Node.js](http://nodejs.org/) e [Heroku Toolbelt](https://toolbelt.heroku.com/) instalados.

```sh
$ git clone https://github.com/adrianogba/node-url-shortening-service.git # or clone your own fork
$ cd node-url-shortening-service
$ npm install
$ npm start
```

O app irá rodar em [localhost:5000](http://localhost:5000/).

## Deploy no Heroku

```
$ heroku create
$ git push heroku master
$ heroku open
```

## Configurando o Heroku Postrgres Database

- [Adicionando database Heroku Postgres](https://devcenter.heroku.com/articles/getting-started-with-nodejs#provision-a-database)

SQL exemplo da base:

```
CREATE TABLE shorturls (
  id int primary key NOT NULL,
  long_url varchar(255) unique NOT NULL,
  created_date int NOT NULL,
  creator_ip char(15) NOT NULL,
  created_by int NOT NULL,
  referrals int NOT NULL default '0'
);
```

Exemplo da estrutura das tabelas

```
 id |          long_url           | created_date  |   creator_ip    | creator_user_id | referrals 
----+-----------------------------+---------------+-----------------+-----------------+-----------
  1 | http://www.unyleya.edu.br   | 1484139363025 | 222.111.222.111 |               1 |         0
  2 | http://www.google.com       | 1484141076745 | 222.111.222.111 |               1 |         1
  3 | http://www.facebook.com     | 1484552390269 | 222.111.222.111 |               1 |         0
```

## Documentação

Para mais informações sobre o Node.js no Heroku, seguem os artigos:

- [Getting Started with Node.js on Heroku](https://devcenter.heroku.com/articles/getting-started-with-nodejs)
- [Heroku Node.js Support](https://devcenter.heroku.com/articles/nodejs-support)
- [Node.js on Heroku](https://devcenter.heroku.com/categories/nodejs)
- [Best Practices for Node.js Development](https://devcenter.heroku.com/articles/node-best-practices)
- [Using WebSockets on Heroku with Node.js](https://devcenter.heroku.com/articles/node-websockets)

