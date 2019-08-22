## Limpando

Não queremos deixar uma bagunça, então vamos remover tudo o que fizemos até agora.

Primeiro precisamos voltar para a pasta projects:

```
$ cd ..
```

Fazendo cd para .. nós mudaremos do diretório atual para o diretório pai (que significa o diretório que contém o diretório atual).

Veja se você se encontra na pasta projects:

```
$ pwd
/projects
```

Se não está, continue digitando o comando cd .. até chegar na pasta.

Agora é hora de excluir o diretório **umapasta**.

**Atenção:** A exclusão de arquivos usando del, rmdir ou rm é irrecuperável, significando _Arquivos excluídos vão embora para sempre!_

Então, tenha cuidado com este comando.

```
$ rm -r umapasta
```

Pronto! Para ter certeza que a pasta foi excluída, vamos checar:

```
$ ls
```

Se não houver retorno, é por que foi removida com sucesso. É possível notar também na parte acima do terminal, que não haverá mais informações do seu projeto e do seu arquivo criado anteriormente.
Por enquanto é isso! 
