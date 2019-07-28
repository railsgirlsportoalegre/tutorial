
# HTML

Antes de continuarmos com nossos posts... vamos falar um pouco sobre **HTML**?? :D :D :D :D

Na base da estrutura de uma página da Web está o HTML (HyperText Markup Language ou, em português, Linguagem de Marcação de HiperTexto). HTML é o que o navegador (Chrome, Internet Explorer, Firefox, etc) "lê" para apresentar a página ao usuário em frente ao computador. Para o navegador conseguir ler o arquivo, é preciso criá-lo com extensão ".html" ou “.htm”, caso contrário o navegador não irá renderizar (mostrar) o conteúdo corretamente.


### Tags HTML

As **tags** são _rótulos_ usados para informar ao navegador como deverá apresentar o site. Ou seja, quando escrevemos HTML estamos escrevendo **tags** que serão interpretadas pelo navegador, resultando no visual do site.

Exemplo: A tag `<h1>` serve para escrever um título, ao inseri-la em um arquivo HTML o browser irá exibir um texto com a formatação de um título.


![Imagem de exemplo da tag h1](../images/rails/exemplo_h1.png)

### Estrutura de uma tag

Todas as tags possuem um formato que deve ser utilizado pelos desenvolvedores web na hora de codificar. As tags começam com um sinal de `<` e terminam com um sinal de `>`.

**Tag de abertura**, inicia a marcação do código: `<nomedatag>`.

**Tag de fechamento**, finaliza com uma barra a marcação do código: `</nomedatag>`.

O conteúdo que deverá ser exibido na página deve estar entre as tags de abertura e fechamento. Exemplo:

```html
<h1>Título da página</h1>
```


Alguns casos não precisam de duas tags, uma de abertura e outra para fechamento, pois o fechamento ocorre dentro da própria tag. Exemplo:

Tag para adicionar nova linha em branco: `<br />`

### Algumas regras das tags HTML

As tags podem ser escritas tanto em maiúsculas como em minúsculas:
`<h1>` ou `<H1>` (o mais utilizado é em minúsculo)

Não pode haver espaços na declaração das tags:`< h1 >`
Todas as tags devem ser fechadas: `<h1>`Sub título`</h1>` ou `<br />`

### Tags encadeadas

É possível encadear várias tags para que tenhamos uma estrutura de conteúdos inseridos um dentro do outro. Exemplo:

```html
<tag>
  <tag1>conteudo</tag1>
  <tag2>
    <tag3>conteudo</tag3>
  </tag2>
  <tag />
</tag>
```

**Dica:**
Para conseguir adicionar estes espaços antes de uma tag, é só apertar a tecla `tab` do seu computador que o editor de texto adiciona com o espaçamento correto. Estes espaços antes das tags são importantes, pois facilitam a leitura do código e deixam clara a hierarquia dos elementos.

### Principais tags HTML

O HTML possui diversas tags, aqui estão algumas e para que servem:

```html
<body></body> corpo da página, onde colocamos outras tags
<p></p> parágrafos
<a></a> links
<h3></h3> títulos, de 1 a 6
<ul> lista não ordenada
  <li></li> itens de listas
</ul>
<div></div> para dividir a página em seções
<table></table> tabelas
<td></td> colunas de tabelas
<tr></tr> linha na tabela
<form> para agrupar entradas de um formulário
  <input /> campos de formulário
  <select> para agrupar opções para seleção
    <option></option> opções
  </select>
</form>
```
Exemplo:

```html
<div>
  <p>Sou um parágrafo dentro de uma div</p>
  <table>
    <tr>
      <td>Coluna 1 - Linha 1</td>
      <td>Coluna 2 - Linha 1</td>
    </tr>
    <tr>
      <td>Coluna 1 - Linha 2</td>
      <td>Coluna 2 - Linha 2</td>
    </tr>
  </table>
</div>
```

Resultado:

<div>
  <p>Sou um parágrafo dentro de uma div</p>
  <table>
    <tr>
      <td>Coluna 1 - Linha 1</td>
      <td>Coluna 2 - Linha 1</td>
    </tr>
    <tr>
      <td>Coluna 1 - Linha 2</td>
      <td>Coluna 2 - Linha 2</td>
    </tr>
  </table>
</div>

Tá bom, agora vamos voltar ao nosso amado **Rails**? :D

### Próximo !!!

Ok, agora nós já temos uma aplicação que nos permite criar, atualizar e excluir nossos posts. Mas ainda falta algo. Nós ainda não podemos dizer que um post está publicado, vamos fazer isso?
