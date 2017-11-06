### Palavras/frases ou strings

Sempre estarão entre aspas, podendo ser duplas:

```ruby
evento = "Rails Girls"
```

Ou aspas simples:

```ruby
evento = 'Rails Girls'
```

Esse tipo é chamado **String**.

Formas de trabalhar com **Strings**:

```ruby
(irb)> "O resultado é #{5 + 2}"
"O resultado é 7"
(irb)> "Estou no " + evento
# "Estou no Rails Girls"
(irb)> '1' * 5
# 11111
(irb)> 'Ê!' * 5
# Ê!Ê!Ê!Ê!Ê!
```

```ruby
(irb)> "casa".include? "asa"  # true
(irb)> "casa".length          # 4
(irb)> "casa".gsub("a","A")   # "cAsA"
(irb)> "  casa  ".rstrip      # "  casa"
(irb)> "casa".count("a")      # 2
(irb)> "2".to_i               # 2
(irb)> 2.to_s                 # "2"
(irb)> "2".to_f               # 2.0
(irb)> "2".rjust(5,"0")       # 00002
```
