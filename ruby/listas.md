### Listas de dados

As listas de dados são chamados de `Array` e serve para armazenarmos valores de
vários tipos:

Palavras ou frases:

```ruby
coachs = ["Carol", "Dessa"]
```

Números:

```ruby
coachs_idades = [24, 23]
```

E tudo junto:

```ruby
dados = [10, true, "Carol"]
```

Formas para acessar os dados:

```ruby
(irb)> coachs[0]    # Carol
(irb)> coachs.at(0) # Carol
(irb)> coachs.fetch(10, "Não encontrado!") # Não encontrado!
(irb)> coachs[-2]   # Carol
(irb)> coachs.values_at(1,10) # ["Dessa", nil]
```

Inserindo dados:

```ruby
(irb)> coachs << "qualquer coisa" # ["Carol", "Dessa", "qualquer coisa"]
(irb)> coachs.insert(-2, "Andri") # ["Carol", "Dessa", "Andri", "qualquer coisa"]
(irb)> coachs.insert(0, 123)      # [123, "Carol", "Dessa", "Andri", "qualquer coisa"]
(irb)> coachs.push "Maria"        # ["Carol", "Dessa", "Andri", "qualquer coisa", "Maria"]
```

Removendo dados:

```ruby
(irb)> coachs.pop                     # "Maria"
(irb)> coachs.shift                   # "Carol"
(irb)> coachs.delete_at 2             # "Andri"
(irb)> coachs.delete "qualquer coisa" # qualquer coisa
```

Outros métodos:

```ruby
(irb)> coachs + ["abc"] # ["Carol", "Dessa", "abc"]
(irb)> coachs * 2       # ["Carol", "Dessa", "Carol", "Dessa"]
(irb)> coachs.join(", ") "Carol, Dessa"
```
