### Listas de dados

As listas de dados são chamados de `Array`. Elas servem para armazenarmos uma lista de valores de vários tipos:

Palavras ou frases:

```ruby
coaches = ["Carol", "Dessa"]
```

Números:

```ruby
coaches_idades = [24, 23]
```

E tudo junto:

```ruby
dados = [10, true, "Carol"]
```

Formas para acessar os dados:

```ruby
(irb)> coaches[0]    # Carol
(irb)> coaches.at(0) # Carol
(irb)> coaches.fetch(10, "Não encontrado!") # Não encontrado!
(irb)> coaches[-2]   # Carol
(irb)> coaches.values_at(1,10) # ["Dessa", nil]
```

Inserindo dados:

```ruby
(irb)> coaches << "qualquer coisa" # ["Carol", "Dessa", "qualquer coisa"]
(irb)> coaches.insert(-2, "Andri") # ["Carol", "Dessa", "Andri", "qualquer coisa"]
(irb)> coaches.insert(0, 123)      # [123, "Carol", "Dessa", "Andri", "qualquer coisa"]
(irb)> coaches.push "Maria"        # ["Carol", "Dessa", "Andri", "qualquer coisa", "Maria"]
```

Removendo dados:

```ruby
(irb)> coaches.pop                     # "Maria"
(irb)> coaches.shift                   # "Carol"
(irb)> coaches.delete_at 2             # "Andri"
(irb)> coaches.delete "qualquer coisa" # qualquer coisa
```

Outros métodos:

```ruby
(irb)> coaches + ["abc"] # ["Carol", "Dessa", "abc"]
(irb)> coaches * 2       # ["Carol", "Dessa", "Carol", "Dessa"]
(irb)> coaches.join(", ") "Carol, Dessa"
```
