# Criando nosso usuário no PostgreSQL

Agora vamos criar o nosso próprio usuário no PostgreSQL para podermos criar bancos de dados, tabelas, inserir dados, ver dados, etc.

# Linux

Caso você esteja em um Linux, primeiro crie seu usuário:

`sudo -u postgres createuser $USER`

Depois crie um banco de dados para ele, podendo assim ser acessado:

`sudo -u postgres createdb $USER`

Agora podemos acessar o PostgreSQL usando `psql`, que abirá o shell interativo do PostgreSQL, nele que iremos trabalhar.

# Windows

Você não precisa fazer essa configuração, pois ela já foi feita na instalação do PostgreSQL

## Proximo =>

[Como será nosso projeto?](../projeto/README.md)
