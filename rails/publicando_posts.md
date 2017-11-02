# Publicando posts

Pra começar, vamos criar um método para atualizar a data de publicação do nosso post para a data atual. Novamente no arquivo `posts_controller.rb`, vamos adicionar as linhas de código abaixo:

```ruby
def publicar
    @post.published_date = DateTime.now

    respond_to do |format|
      if @post.save
        format.html { redirect_to posts_url, notice: 'Post publicado com sucesso.' }
        format.json { render :show, status: :ok, location: @post }
      else
          format.html { redirect_to posts_url, notice: 'Algum erro aconteceu ao tentar publicar o post :(' }
	        format.json { head :no_content }
      end
    end
  end
```

**Obs:** Você pode adicionar essa parte do código logo depois do método destroy, logo vamos explicar o que esse método faz.

Antes de explicarmos o código, temos que adicionar só mais uma coisa no arquivo `post_controller.rb`, você deve ter uma linha parecida com a abaixo no seu arquivo:

```ruby
before_action :set_post, only: [:show, :edit, :update, :destroy]
```

Substitua ela pela linha abaixo:

```ruby
before_action :set_post, only: [:show, :edit, :update, :destroy, :publicar]
```

Com essa alteração, estamos dizendo que antes de chamar o método `publicar`, vamos chamar o método `set_post`, como mostra abaixo:

```ruby
def set_post
  @post = Post.find(params[:id])
end
```

Esse método, vai sempre procurar um post com o _identificador(params[:id])_ que mandamos para ele, e colocar dentro da variável _@post_

### Agora vamos olhar de novo o método que criamos:

Então, antes de chamarmos esse métodos, já vimos que o método `set_post` será chamado, que colocará um Post na variável _@post_, que podemos ver na primeira linha do método.
Nessa linha, estamos alterando o valor do atributo `published_datedo` do post, ou seja a data de publicação. Aqui temos algo novo:

```ruby
 @post.published_date = DateTime.now
```

Estamos dizendo que `@post.published_date` vai receber o valor do dia de hoje, que com ruby usamos `DateTime.now`.

Após alterarmos o valor de `@post.published_date`, já iniciamos o código para retornar para o html. Isso fazemos com a linha `respond_to do |format|`, depois testamos se o post foi salvo com o valor novo, isso com a linha `if @post.save`, caso isso ocorra, direcionamos para a tela principal dos posts: `posts_url` (para o Rails):

```ruby
format.html { redirect_to posts_url, notice: 'Post publicado com sucesso.' }
```

Caso não dê certo, direcionamos para a tela inicial também, com uma mensagem de erro:

```ruby
format.html { redirect_to posts_url, notice: 'Algum erro aconteceu ao tentar publicar o post :(' }
```

O método completo deve ficar assim:

```ruby
def publicar
    @post.published_date = DateTime.now

    respond_to do |format|
      if @post.save
        format.html { redirect_to posts_url, notice: 'Post publicado com sucesso.' }
        format.json { render :show, status: :ok, location: @post }
      else
          format.html { redirect_to posts_url, notice: 'Algum erro aconteceu ao tentar publicar o post :(' }
	        format.json { head :no_content }
      end
    end
  end
```

### Com o método criado, vamos criar o link!

Assim para quando queremos excluir e atualizar, devemos criar um link para podermos publicar nosso post. Primeiro, vamos criar uma rota nova. Você lembra do `routes.rb`?
Vamos adiconar a linha abaixo nele, pode ser bem abaixo de `resources :posts`

```ruby
get 'publicar-post/:id' => 'posts#publicar', as: 'publicar'
```

Essa linha cria uma nova rota, para podermos chegar no método `publicar` que criamos em `posts_controller.rb`.

Estamos dizendo que vamos chamar o controller `PostsController`, na ação `publicar`, enviando um `id`, a identificação do post no banco de dados.

Depois de criar a rota, vamos criar o link no html. Agora vamos ver mais uma coisa nova do Rails, as `Views`.

As views são basicamente o html onde vamos mostrar nossos dados, ou seja, o que o controller mandar para nós, é nas views que iremos mostrar.
Vamos abrir o arquivo `app/views/posts/index.html.erb`:

```html
<h1>Listing posts</h1>

<table>
  <thead>
    <tr>
      <th>Title</th>
      <th>Text</th>
      <th>Author</th>
      <th>Created date</th>
      <th>Published date</th>
      <th colspan="3"></th>
    </tr>
  </thead>

  <tbody>
    <% @posts.each do |post| %>
      <tr>
        <td><%= post.title %></td>
        <td><%= post.text %></td>
        <td><%= post.author %></td>
        <td><%= post.created_date %></td>
        <td><%= post.published_date %></td>
        <td><%= link_to 'Show', post %></td>
        <td><%= link_to 'Edit', edit_post_path(post) %></td>
        <td><%= link_to 'Destroy', post, method: :delete, data: { confirm: 'Are you sure?' } %></td>
      </tr>
    <% end %>
  </tbody>
</table>

<br>

<%= link_to 'New Post', new_post_path %>
```

#### Mas antes de criar o link… vamos entender umas coisinhas

Note que o arquivo não é total html, ele termina com extensão erb, que serve para que ele entenda código ruby. ,e para fazermos isso, usamos os seguintes sinais:

* `<%` \- que mostra que código ruby está começando
* `%>` \- que mostra que código ruby está terminando
* `<%= … %>` \- contém um código ruby que vai só mostrar algo, não executar

Temos algo no `index.html.erb`, são os laços de repetição em ruby, podemos ver ele sendo iniciado no seguinte linha:

```html
<% @posts.each do |post| %>
  <tr>
    <td><%= post.title %></td>
    <td><%= post.text %></td>
    <td><%= post.author %></td>
    <td><%= post.created_date %></td>
    <td><%= post.published_date %></td>
    <td><%= link_to 'Show', post %></td>
    <td><%= link_to 'Edit', edit_post_path(post) %></td>
    <td><%= link_to 'Destroy', post, method: :delete, data: { confirm: 'Are you sure?' } %></td>
  </tr>
<% end %>
```

Note que nessa linha usamos o **<%** para iniciar o laço de repetição. Mas então, o que isso faz?
**@posts** é uma lista, então estamos iterando cada item da lista e criando uma nova variável, chamada post, após, dentro da **<tr>**, estamos mostrando os dados desse post, e criando os links para atualizar, excluir, e mostrar ele. Finalizando o laço de repetição com a linha **<% end %>**

#### Agora sim, vamos criar o link!

Agora que já vimos como usar código ruby dentro do html, e como funciona o laço de repetição, vamos criar o link para atualizar o estado do nosso post! Voltando ao laço de repetição, vamos adicionar uma linha nova:

```html
<% @posts.each do |post| %>
  <tr>
    <td><%= post.title %></td>
    <td><%= post.text %></td>
    <td><%= post.author %></td>
    <td><%= post.created_date %></td>
    <td><%= post.published_date %></td>
    <td><%= link_to 'Show', post %></td>
    <td><%= link_to 'Edit', edit_post_path(post) %></td>
    <td><%= link_to 'Publicar', publicar_path(post) %></td>
    <td><%= link_to 'Destroy', post, method: :delete, data: { confirm: 'Are you sure?' } %></td>
  </tr>
<% end %>
```

Podemos adicionar a linha destacada no nosso arquivo `index.html.rb`, essa linha criará o link para o método que criamos na controller, e retornará para a mesma tela, com o post atualizado :D

## Último passo

Precisamos adicionar somente mais uma linha para mostrar corretamente as nossas mensagens de sucesso ou erro depois que publicamos um post, para isso no inicio do `index.html.erb` adicione a linha:

```html
<p id="notice"><%= notice %></p>
```

Nessa linha temos um parágrafo em html, que irá mostrar a mensagem (variável notice) que vem da controller, lembra?

Agora, seu `index.html.erb` deve estar assim:

```html
<h1>Listing posts</h1>

<p id="notice"><%= notice %></p>

<table>
  <thead>
    <tr>
      <th>Title</th>
      <th>Text</th>
      <th>Author</th>
      <th>Created date</th>
      <th>Published date</th>
      <th colspan="4"></th>
    </tr>
  </thead>

  <tbody>
    <% @posts.each do |post| %>
      <tr>
        <td><%= post.title %></td>
        <td><%= post.text %></td>
        <td><%= post.author %></td>
        <td><%= post.created_date %></td>
        <td><%= post.published_date %></td>
        <td><%= link_to 'Show', post %></td>
        <td><%= link_to 'Edit', edit_post_path(post) %></td>
        <td><%= link_to 'Publicar', publicar_path(post) %></td>
        <td><%= link_to 'Destroy', post, method: :delete, data: { confirm: 'Are you sure?' } %></td>
      </tr>
    <% end %>
  </tbody>
</table>

<br>

<%= link_to 'New Post', new_post_path %>
```

### Vamos testar?
No terminal digite o comando abaixo para iniciar a aplicação, caso esteja rodando já, lembre de parar, teclando CTRL+C e iniciando de novo:

```sh
rails server
```

E abra o blog no navegador com a mesma url já utilizada :)

![Publicando um post link](../images/rails/publicando_post_link.png)

Uhuul, o link novo está aparecendo! E o que acontece se clicarmos nele?

![Post publicado](../images/rails/post_publicado.png)

Uhuul, o post é publicado! E a mensagem aparece!
