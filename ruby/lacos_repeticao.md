### Laço de repetição

Em algumas situações precisamos repetir uma operação em elementos de um conjunto de dados. Podemos realizar esta tarefa utilizando laços.

Imprimir 2 nomes de uma lista é fácil, certo? Mas imagina escrever 100 nomes! Utilizamos laços para nos poupar de escrever códigos duplicados.

Por exemplo, podemos imprimir todos os nomes em uma lista utilizando o `for`, percorrendo a lista, item a item:

```ruby
lista_de_nomes = ["Juliana", "Enzo", "Roberto"]

for nome in lista_de_nomes
  escrever_nome(nome)
end

# Note que estamos utilizando o método escrever_nome do exemplo anterior.
```

Podemos brincar com o inglês do código: ***for nome in lista_de_nomes*** poderíamos acrescentar o cada (em inglês fica each) para ficar em português: ***para cada nome em lista_de_nomes***

Ruby é uma linguagem muito boa nisso, em inglês faz sentido cada comando. Dá para aprender inglês e Ruby juntos :D
