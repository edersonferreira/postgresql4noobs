# Tipos primitivos no PostgreSQL

Em tabelas de bancos de dados, precisamos definir o tipo primitivo de cada coluna, como sendo um número, texto, lógico (verdadeiro ou falso), etc. Para isso, o PostgreSQL oferece inúmeros tipos para serem usados, alguns dos tipos mais usados serão mostrados aqui, caso queira saber mais, pesquise na [documentação oficial](https://www.postgresql.org/docs/12/datatype.html).

## Números

Temos 2 tipos para números (mais usados), que é o `int` e o `double`, `int` é usado para números inteiros, como 5, enquanto `double` é usado para números "quebrados", ou decimais, como 5.3, também pode ser usado o `real` para isso.

Lembrando que iremos usar esses tipos primitivos na criação de tabelas no próximo tópico.

## Textos

Temos 3 tipos primitivos úteis para textos, `varchar`, `char` e `text`.

`varchar` funciona da seguinte forma:

Se usarmos `varchar(30)` iremos determinar que este campo terá **no máximo** 30 caracteres (incluindo espaços), caso este campo receber menos que 30 caracteres, como 10, este campo irá apenas armazenar estes 10 caracteres.

O `char(30)` faz uma função parecida com o `varchar`, mas caso ele receba menos que 30 caracteres, o restante será completado com espaços.

O `text` se diferencia dos outros dois, pois ele aceita um texto com qualquer número de caracteres.

## Boolean (lógico)

Para um campo conter um valor sendo verdeiro ou falso (true ou false) podemos usar o `boolean`, alguns estados válidos para verdadeiro são:

TRUE
't'
'true'
'y'
'yes'
'on'
'1'

E alguns estados válidos para falso são:

FALSE
'f'
'false'
'n'
'no'
'off'
'0'

## Proximo =>

[Criando Tabelas](../tabelas/README.md)