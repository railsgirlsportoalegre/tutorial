### Listas de dados

As listas de dados são chamados de `Array` e serve para armazenarmos valores de
vários tipos:

Palvras ou frases:

```ruby
nomes_das_tutoras = ["Carol", "Bárbara"]
```

Números:

```ruby
idades_das_tutoras = [23, 20]
```

E tudo junto:

```ruby
dados = [10, true, "Carol"]
```

Formas para acessar os dados:

```ruby
(irb)> print nomes_das_tutoras[0]
# Carol
(irb)> dados.at(2)
(irb)> dados.fetch(10, "Não encontrado!")
(irb)> dados[-2]
(irb)> dados.values_at(1,3)
```

Inserindo dados:

```ruby
(irb)> dados << "qualquer coisa"
(irb)> dados.insert(-1,3)
(irb)> dados.push 7
```

Removendo dados:

```ruby
(irb)> dados.pop
(irb)> dados.shift
(irb)> dados.delete_at 4
(irb)> dados.delete 4
```

Outros métodos:

```ruby
(irb)> dados + ["abc"]
(irb)> dados * 2
(irb)> dados.join(", ")
```
