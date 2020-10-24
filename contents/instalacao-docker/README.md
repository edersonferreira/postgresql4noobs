# Instalação do PostgreSQL via Docker Compose

A instalação do PostgreSQL via docker-compose é bem simples.

# Criando um arquivo docker-compose.

Crie um arquivo chamado `docker-compose.yml`

Dentro dele voce adiciona o conteúdo abaixo:

```
version: '3.5'

services:
  postgres:
    container_name: postgres_container-4noobs
    image: postgres
    environment:
      POSTGRES_USER: ${POSTGRES_USER:-postgres}
      POSTGRES_PASSWORD: ${POSTGRES_PASSWORD:-changeme}
      PGDATA: /data/postgres
    volumes:
       - postgres:/data/postgres
    ports:
      - "5432:5432"
    networks:
      - postgres
    restart: unless-stopped

  pgadmin:
    container_name: pgadmin_container-4noobs
    image: dpage/pgadmin4
    environment:
      PGADMIN_DEFAULT_EMAIL: ${PGADMIN_DEFAULT_EMAIL:-pgadmin4@pgadmin.org}
      PGADMIN_DEFAULT_PASSWORD: ${PGADMIN_DEFAULT_PASSWORD:-admin}
    volumes:
       - pgadmin:/root/.pgadmin
    ports:
      - "${PGADMIN_PORT:-5050}:80"
    networks:
      - postgres
    restart: unless-stopped

networks:
  postgres:
    driver: bridge

volumes:
    postgres:
    pgadmin:
```

- `version`, versão do Compose.
- `networks`, networks a serem criadas dentro da stack.
- `volumes`, (armazenamentos) a serem criadas dentro da stack.

## Execute esse arquivo usando

`docker-compose up -d `

- `-d`, é pra esconder os logs dos containers.

## Para parar os containers via docker-compose

`docker-compose down`

Pronto! o PostgreSQL e Pgadmin4 estão rodando no seu sistema via docker!

## Proximo =>

[O que é um banco de dados?](../oque-bd/README.md)
