# Criando Tabelas no PostgreSQL

Para criar uma table em PostgreSQL iremos usar o comando `CREATE TABLE`.

Primeiro vamos executar o comando para entrar na tabela que criamos, teremos que fazer isso para entrar no shell do `psql` dentro do banco de dados que criamos, dessa maneira:

`psql empresa`

Depois executar essa query para criarmos a tabela:

```sql
CREATE TABLE usuarios (
    id SERIAL PRIMARY KEY,
    nome varchar(20) NOT NULL,
    sobrenome varchar(20) NOT NULL,
    idade int
);
```

Foi usado `SERIAL` ao invés de `int`, pois `SERIAL` a cada vez que inserimos um dado automaticamente o id é incrementado, assim não precisamos ficar pesquisando qual foi o ultimo id inserido e somar mais um, pois o PostgreSQL já irá fazer isso.

Para criarmos a tabela, podemos inserir o nome, depois `(`, todos os campos e seus tipos primitivos, separando com uma vírgula, e fechando com um `);`.

Criamos um id, sendo `SERIAL`. nome sendo um `varchar(20)`, assim o nome terá no máximo 20 caracteres, a mesma coisa com o sobrenome e a idade sendo `int`, representando um número inteiro.

O `NOT NULL` serve para determinamos que o campo não deve ser nulo, que ele precisa ser preenchido, o único campo que não é obrigatório que seja preenchido é o campo de idade.

## Proximo =>

[Inserindo dados na tabela](../inserindo-dados/README.md)
