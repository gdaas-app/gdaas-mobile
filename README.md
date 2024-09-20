# gdaas-mobile

## Docker compose

Para subir o projeto com docker-compose, basta executar o comando abaixo:

```bash
  docker compose --file docker-compose.yml up -d
```

Isso irá subir o backend, banco de dados e redis, e os endpoints estarão disponíveis em:

- Backend: http://localhost:3000
- Banco de dados: http://localhost:5432
- Redis: http://localhost:6379

## Banco de dados

Para criar a estrutura e popular o banco de dados é necessário executar os comandos abaixo no terminal do container do backend:

```bash
npx knex --knexfile "./dist/database/config/knexfile.js" --migrations-directory "../migrations"   migrate:latest
npx knex --knexfile "./dist/database/config/knexfile.js" seed:run
```

Para conectar no banco de dados, utilize as seguintes credenciais:

- Host: 127.0.0.1
- Database: gdaas
- Username: usuario
- Password: senha
- Port: 5432