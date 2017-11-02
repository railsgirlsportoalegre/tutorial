### Métodos

São uma forma de agrupar um conjunto de instruções, como se fosse uma receita
que podemos executar utilizando seu nome. Podem receber e retornar valores.

```ruby
def escrever_nome(nome)
  "Seu nome é " + nome
end
```

Ok, mas o que significa tudo isso?

* `def` \- estamos dizendo que estamos definindo um método
* `escrever_nome` \- esse é o nome do nosso método. Note que nele subtituímos
  os espaços por traços (\_)
* `(nome)` \- é o parâmetro do nosso método, uma variável que mandamos para o
  método, para que ele faça algo com ela. Métodos podem receber nenhum, um ou
  mais paramêtros.
* `“Seu nome é #{nome}”` \- é o que o método vai retornar para a gente,
  note que usamos o paramêtro nome na frase
* `end` \- estamos dizendo que estamos finalizando o método

Agora utilizando nosso método:

```ruby
texto = escrever_nome("Carol")
```

Assim o método retornaria `"Seu nome é Carol"` e `texto` agora tem essa frase
como valor.

Podemos agora utilizar o método `print` já disponibilizado pelo Ruby para
"imprimir" a frase na linha de comando:

```ruby
texto = escrever_nome("Carol")
print(texto)
```
