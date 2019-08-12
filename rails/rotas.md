# Procurando os posts


Agora vamos aprender algo novo do Rails: as `rotas`, que nada mais são do que caminhos que o Rails cria ao criarmos algo novo. Isso tudo acontece naquele primeiro comando que executamos para criar o Post (rails scaffold...), lembra?

As rotas, ficam num arquivos chamado `routes.rb`, você pode encontrar ele na pasta `config`, dentro da pasta do projeto. Vamos abrir esse arquivo, nele, deve haver uma linha com o conteúdo abaixo:

```
resources :posts
```

Ok, mas o que isso significa? O Rails já cria muitas coisas para a gente, e nessa linha, ele cria automático, todos os caminhos para criarmos, atualizarmos, vermos, e excluirmos um post.

Você pode aprender mais sobre rotas nos seguintes links:
- [https://www.caelum.com.br/apostila-ruby-on-rails/rotas/#8-7-exercicio-rotas](https://www.caelum.com.br/apostila-ruby-on-rails/rotas/#8-7-exercicio-rotas)

- [http://www.devmedia.com.br/introducao-a-rotas-e-responders-no-ruby-on-rails/33521](http://www.devmedia.com.br/introducao-a-rotas-e-responders-no-ruby-on-rails/33521)


Agora, se formos no navegador, naquele endereço que fomos antes, mas adicionando `/posts` no fim, como o exemplo:

```
https://railsgirls-carolinemoers694501.codeanyapp.com/posts
```

Vamos ver a imagem abaixo. Uhuul!! Podemos criar nossos posts agora :D

![Lista de Posts](../images/rails/lista_posts.png)

Mas calma! E se eu quiser que quando eu acessar o site, ele caia direto na tela dos posts ao invés daquela tela do Rails?

Podemos fazer isso também, vamos lá!

### Dizendo pro rails que a primeira tela é a de posts

Vamos abrir o arquivo `routes.rb` de novo. Lembra onde ele está? Em `config/routes.rb`.
Vamos mudar algo nele, agora, as duas primeiras linhas devem estar assim:

```ruby
Rails.application.routes.draw do
  resources :posts
```

Altere ele para que fique assim:

```ruby
Rails.application.routes.draw do
  root 'posts#index'
  resources :posts
```

Nós adicionamos a linha root `posts#index`, que diz ao Rails que ao acessarmos `https://railsgirls-carolinemoers694501.codeanyapp.com` (no seu caso essa url vai ser um pouco diferente) ele deve enviar para a tela dos posts na ação index (logo falaremos sobre ações :))

### E quando acessamos no navegador agora...

Acessando a url sem o `/post` no final, vamos ver a tela abaixo!

![Lista de Posts](../images/rails/lista_posts.png)

Lindo!! Agora o Rails entende que a primeira tela deve ser a de posts :D
