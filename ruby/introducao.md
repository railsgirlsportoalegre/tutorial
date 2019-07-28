# Vamos falar sobre ruby?

Vamos entender algumas coisas básicas do Ruby como variáveis, arrays, métodos, etc. Vamos dar uma olhada em o que são cada um desses nomes e o que podemos criar com eles :)

Mas antes de continuarmos vamos conhecer o **irb**. Vamos lá?

##irb

O **irb** é um ambiente interativo para execução de código Ruby, nele conseguimos executar código Ruby de maneira instantânea e ver o resultado do nosso código. Todos os exemplos a seguir podem executados no **irb**.

Para entrar no **irb** você executa o comando:

```sh
$ irb
```

E ele se parece com isso:

```sh
irb(main):001:0>
```

Para sair do **irb** você precisa digitar `exit` e pressionar Enter.

As variáveis e comandos que veremos a seguir podem ser testadas no **ibr**. MAS... o que são variáveis????? :O Calma, calma, é o que conversaremos a seguir <3 :

## Variáveis
Variáveis são espaços na memória do computador que utilizamos para guardar dados. Imagina que são caixinhas, no qual colocamos o dado dentro e um nome fora dela, que utilizamos para acessar esse valor. Mas existem tipos de caixa, conforme o tamanho que os dados dentro dela podem ter e o que eles são.

Vamos criar a variável e acessá-la, no **ibr**:

```sh
irb(main):001:0> meu_nome = "Maria"
=> "Maria"
irb(main):002:0> meu_nome
=> "Maria"
irb(main):003:0>
```

## Tipos básicos no Ruby

Nas variáveis que guardamos nossos dados e eles podem ser de vários tipos:

* Números inteiros: **Integer**
* Números decimais: **Float**
* Palavras ou frases: **String**
* Valores lógicos (verdadeiro ou falso): **True** e **False**
* Lista de valores: **Array**

Nós vamos falar um pouquinho sobre cada um tipos nas próximas sessões :)
