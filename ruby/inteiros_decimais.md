### Números inteiros e decimais

**Integers** são números inteiros:

```ruby
paginas = 100
```

**Floats** são números decimais:

```ruby
preco = 4.5
```

Sendo `4,5` o valor no exemplo, pois o Ruby representa esses valores com ponto.

**Obs**: Um ponto importante pra citar aqui, é sobre o nome que damos às
variáveis: elas não devem conter espaços, como podemos ver nas variáveis criadas
aqui o espaço foi substituído por *underline* (\_).

Experimente no **irb** algumas operações com números:

```ruby
(irb)> preco + 2      # 6.5
(irb)> 10 - 4 / - 2   # 12
(irb)> (10 - 4) / - 2 # -3
(irb)> 35 % 6         # 5
```

E também alguns métodos:

```ruby
(irb)> 0.zero?         # serious?
(irb)> 2.even?         # true
(irb)> 0.odd?          # false
(irb)> (1+2).next.next # 5
```

Falaremos mais sobre mais métodos ainda neste capítulo.
