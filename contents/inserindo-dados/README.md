# Inserindo dados na tabela

Para inserir dados na tabela, iremos usar o comando `INSERT INTO`, que serve exatamente para isso, seguido do nome da tabela, e se caso iremos completar TODOS os campos da tabela, a palavra `VALUES` seguido dos valores, dessa maneira:

```sql
INSERT INTO usuarios VALUES (
    1,
    'Pedro',
    'Cardoso',
    21
);
```

Como você pode ver acima, não precisamos escrever id, nome, sobrenome, etc. Apenas precisamos colocar na ordem dos valores da tabela, sendo o primeiro o id, depois o nome, sobrenome e a idade no final.

Como nome e sobrenome são varchar, precisamos colocar um `'` no começo e outro `'` (podemos apenas usar as aspas simples, aspas duplas não são aceitas), para determinar o começo e o final do texto ou da string, essa regra também se aplica ao char.

Caso quisermos especificar quais campos iremos preencher, podemos colocar eles entre parênteses após o nome da tabela, agora iremos colocar apenas a id, nome e o sobrenome, sem colocar a idade.

```sql
INSERT INTO usuarios (id, nome, sobrenome) VALUES (
    2,
    'Felipe',
    'Crespo'
)
```

Agora dentro da tabela, há a idade do Pedro, mas não tem a idade do Felipe, pois a idade é um campo opcional, enquanto todo o resto é obrigatório, pois usamos o `NOT NULL` neles.

## Proximo =>

[Selecionando dados na tabela](../selecionando/README.md)