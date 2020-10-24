# Criptografia

Este conceito de segurança, pode ser aplicado em qualquer banco de dados, sendo PostgreSQL, MySQL, MariaDB, etc. Mas mesmo assim, é sempre importante termos uma palavra em nossa cabeça enquanto estamos fazendo bancos de dados (e aplicações no geral) que irão para a produção, que é a CRIPTOGRAFIA!

Vamos supor que o seu banco de dados atual é invadido (Como o banco de dados da Vakinha ou de até mesmo, do Linkedin). O invasor vai conseguir ver todos os dados, incluindo o nome, sobrenome e idade, que não são dados tão importantes, mas, e se lá estivesse um email com uma senha?

A maioria dos usuários, tem uma má prática de ter a mesma senha em vários serviços diferentes, assim, se o usuário da sua aplicação, ter a mesma senha para tudo, se o seu banco de dados vazar, o invasor pode roubar qualquer outra conta desse usuário que ter a mesma senha.

## Mas como podemos resolver esse problema?

Simples! Com criptografia simétrica e hasheada.

A criptografia é o ato de transformar uma mensagem, em uma outra mensagem, mas muito mais difícil de entender, ou que é impossível de entender se não tivermos a chave da criptografia, onde que se aplicarmos essa chave da criptografia na mensagem criptografada, iremos receber a mensagem original.

Exemplo, vamos usar a criptografia ROT13, ou Cifra de César, é uma criptografia extremamente fraca, mas ele vai servir como um bom exemplo.

A ROT13 pega cada letra da mensagem, e pula 13 caracteres, dessa maneira, deixando a mensagem mais difícil de entender, mas se retrocedermos 13 caracteres, a mensagem estará descriptografada.

Alfabeto Normal: `ABCDEFGHIJKLMNOPQRSTUVWXYZ`

Alfabeto ROT13: `NOPQRSTUVWXYZABCDEFGHIJKLM`

Agora vamos usando o ROT13, encriptar a mensagem `A He4rt manda bem demais!`.

Input: `A He4rt manda bem demais!`

Output: `N Ur4eg znaqn orz qrznvf!`

Como você pode ver, é ilegível a segunda mensagem, mas como você pode ter percebido, se fizermos o processo contrário, iremos pegar a mensagem de volta.

## Criptografia Simétrica

A Criptografia simétrica é exatamente este tipo de criptografia apresentada acima, onde podemos encriptar a mensagem e descriptografar ela depois, mas é claro, há algorítimos MUITO mais complexos que o ROT13. O mais conhecido é o AES, que recebe a mensagem, e dois parâmetros, um de 32 caracteres hexadecimais, e o outro de 64 caracteres hexadecimais.

Assim, em uma aplicação usando qualquer stack de programação web (Nodejs, PHP, Rails, etc), podemos enviar o dado normal do frontend (tela do usuário) para o backend (servidor), e ele cuidará de criptografar o dado e escrever no banco de dados. Depois disso, o frontend pode requisitar o dado novamente, e o backend pegará o dado criptografado, descriptografará ele e enviará para o frontend.

## Criptografia Hasheada

A criptografia hasheada, é uma criptografia muito mais forte que a criptografia simétrica, pois quando a mensagem é criptografada, não é possível descriptografar, apenas podemos pegar a mesma mensagem que foi usada, e comparar com a mensagem criptografada, que é chamada de **hash**. E se o resultado for verdadeiro, aquela é a mensagem original.

Um algorítimo de criptografia hasheada muito conhecido é o **Bcrypt**, que está disponível em diversas linguagens diferentes, ele é ótimo pois é muito prático, apenas precisamos definir a profundidade da criptografia, onde 10 já é um número ótimo e pronto, ele faz tudo para nós.

## Juntando as Duas

Podemos critografar a senha do usuário usando criptografias hashedas, pegando o email dele, fazendo uma query que busca qual é a senha de quem tem aquele email, depois pegar a senha que foi recebida e comparar com a que está no banco de dados, observe o pseudo-código abaixo:

```
senha = SELECT senha FROM usuarios WHERE email = [email_do_usuario]

resultado = bcript.comparar(senha_recebida_do_usuario, senha)

se (resultado = Verdadeiro){
  escreva('A senha está correta!')
}

senao{
  escreva('A senha está incorreta!')
}

```

---

E para criptografar, por exemplo, postagens privadas, podemos usar criptografia síncrona, pois precisaremos desse dado em texto puro novamente. Podemos fazer a query no banco de dados e descriptografar usando uma chave pública, e outra privada, que dependem de como é o seu projeto, quais campos tem,etc. No caso, apenas irei inventar duas variáveis para cada chave.

```
mensagem = SELECT mensagem FROM mensagens WHERE quem_mandou = [quem_mandou_a_mensagem]

resultado = aes.descriptografar(mensagem, chave_publica, chave_privada)

escreva('A mensagem é: ' + resultado)

```
