# Deletando Dados

Agora vamos aprender a última operação principal do PostgreSQL, a operação de remoção, ou delete.

Essa operação também é muito importante, pois com ela, poderemos remover dados que não são mais úteis para nós. Mas em aplicações reais, não devemos deletar nenhum dado sem guardar ele em outro lugar, pois, para termos registro de tudo que já passou no banco de dados precisamos deletar o dado da tabela comum, e enviar para uma outra tabela apenas para os itens deletados.

Para deletarmos um dado no PostgreSQL, precisamos usar o comando `DELETE`, especificar a tabela que queremos entrar e usar o `WHERE` para especificarmos quem queremos deletar (uma ou mais linhas). Exemplo:

```sql
DELETE FROM usuarios WHERE idade >= 23;
```

Na query acima, deletamos todos os usuários, ONDE a idade é maior ou igual á 23, deletando apenas o Felipe do banco de dados, apenas ele pois a idade do Pedro é 22, e 22 não é maior que 23.

Também podemos deletar vários dados de uma vez só, por exemplo, colocando `idade >= 20`, onde tanto o Felipe quanto o Pedro seriam deletados.

## Proximo =>

[Criptografia](../criptografia/README.md)
