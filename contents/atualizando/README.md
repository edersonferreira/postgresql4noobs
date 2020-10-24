# Atualizando Dados

Atualizar dados é algo importante que precisamos ter quando criamos aplicações como redes sociais, onde os usuários podem atualizar o seu nome de usuário, senha, dados pessoais, etc. Isso inclusive irá se tornar uma lei (ou já é, dependendo de quando você está lendo isso) pela LGPD (Lei Geral de Proteção de Dados).

Para atualizarmos um dado no PostgreSQL, precisaremos usar uma palavra especial, chamada `UPDATE`, que irá fazer esta exata função para nós, logo depois passaremos a tabela, o dado que queremos mudar, o novo valor dele e pra qual linha queremos aplicar. Veja o exemplo:

```sql
UPDATE usuarios SET idade = 24 WHERE nome = 'Felipe';
```

No comando acima, usamos o `SET idade = 24` para determinar que a idade irá mudar, e se tornará 24, `WHERE` (onde) o nome for igual á 'Felipe'. O UPDATE é um comando bem simples como você pode ver.

Podemos ainda passar para o WHERE mais condições, como o sobrenome, veja abaixo.

---

```sql
UPDATE usuarios SET idade = 22 WHERE nome = 'Pedro' AND sobrenome = 'Cardoso';
```

Acima, dentro o WHERE, apenas iremos mudar a idade, onde o nome é Pedro AND (E) o sobrenome é Cardoso.

Há várias possibilidades de condições, como `idade > 23`, brinque por você mesmo e aprenda como manipular essas condições

## Aviso

SEMPRE que estiver usando o update, se garanta que está passando o SET, que define o novo valor, e principalmente o WHERE, que define onde esse valor vai mudar, pois, sem o WHERE, a alteração é aplicada para TODAS as linhas da tabela, enquanto você estiver aprendendo, isso será um problema, mas se algum dia, por algum motivo, você estiver mexendo com a tabela direto no terminal do servidor, isso é algo muito ruim, que se o banco não tiver nenhum backup, todos os dados estarão danificados.

## Proximo =>

[Deletando dados da tabela](../deletando/README.md)
