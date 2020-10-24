# Instalação do PostgreSQL no Linux

A instalação do PostgreSQL no Linux é bem simples.

## Debian, Ubuntu, Linux Mint e derivados

Execute este comando em um terminal:

`sudo apt-get install postgresql`

## Arch e Manjaro

Execute este comando em um terminal:

`sudo pacman -S postgresql`

# Fedora

Adicione o repositório ao seu sistema:

`sudo dnf install https://download.postgresql.org/pub/repos/yum/reporpms/F-31-x86_64/pgdg-fedora-repo-latest.noarch.rpm`

Instale o PostgreSQL no seu sistema:

`sudo dnf install postgresql11-server postgresql11`

Confirme a instalação:

`rpm -qi postgresql11-server`

Inicialize o PostgreSQL:

```
sudo /usr/pgsql-11/bin/postgresql-11-setup initdb
sudo systemctl start postgresql-11
sudo systemctl enable postgresql-11
```

Digite `createdb` no seu shell para criar um banco de dados para o seu usuário, permitindo o acesso ao PostgreSQL.

Vamos agora dar privilégios de superusuário ao usuário da sua máquina (seu login), dessa maneira, use `sudo su - postgres`, logo depois `psql` e por final:

```sql
ALTER ROLE [SEU USUÁRIO] WITH SUPERUSER;
```

Agora digite `psql` para entrar no shell do PostgreSQL e poder futuramente, fazer _CRUD_ dos dados, que é a criação, leitura, atualização e remoção dos dados.

---

Pronto! o PostgreSQL foi instalado no seu sistema!

## Proximo =>

[O que é um banco de dados?](../oque-bd/README.md)
