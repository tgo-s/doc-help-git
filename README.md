# Dicas básicas de Git
Pequeno tutorial criado para auxiliar quem está começando a usar o git como repositório de códigos e optar por usar linha de comando

## Exemplo completo - a partir de um clone de projeto

Clona um projeto (este comando cria um diretorio novo com o nome do repositório)
```bash
 git clone [url-do-projeto-que-se-deseja-clonar]
 ```

Para clonar um repositório no diretório atual deve-se usar 
```bash
git clone [url-do-projeto-que-se-deseja-clonar] .
```

Em seguida, por garantia, deve-se atualizar o projeto com o comando
```bash
git pull origin master
```

Navegue até onde clonou o projeto
```bash
cd projeto/
```

Verificamos os branches que existem no projeto
```bash
git branch
```

Para começar a alterar seu projeto, recomenda-se criar um branch local. Para isso mudamos para o branch que queremos como ponto de partida 
```bash
git checkout branch-mais-atual
git branch novo-branch-para-trabalhar
```

Mudamos então para o novo branch
```bash
git checkout novo-branch-para-trabalhar
 ```

Após alterar o projeto, use o comando a seguir para ver o que mudou no projeto para que possa ser inserido ou deletado
```bash
git status
```

Com o comando abaixo é possivel verificar as diferenças gerais
```bash
git diff
```

Para verificar diferenças mais especificas pode-se usar:
```bash
git diff origin/master
git diff commit_id1 commit_id2
git diff nome-do-branch
git diff nome-do-branch /caminho/do/arquivo.txt
```

Informe quais alterações serão efetuadas, o que será inserido e o que será removido
```bash
git add arquivos_para_serem_commitados/
git add arquivo_para_ser_commitado.md
git rm arquivo_que_nao_precisa.txt
```

Mostra se os arquivos foram marcados para adicionar ou remover do projeto corretamente
```bash
git status
```

Informa as mudanças feitas no projeto e configura para fazer o "check in"
```bash
git commit -m "Descrição do que foi feito"
```

Após tudo finalizado, devemos fazer um merge entre a branch de desenvolvimento com a branch master ou a branch que se usou como ponto de partida
```bash
git checkout branch-usada-como-ponto-de-partida
git merge nome-da-branch-de-desenvolvimento
```

Envia as alterações para o servidor
```bash
git push origin master 
```

Se for o caso, deletamos a branch
```bash
git branch -d branch-usada-para-deletar
```

Verifica o status novamente pra saber se tudo deu certo e então executa o comando abaixo para efetivar as alterações
```bash
git push
```
Lembrando que no servidor geralmente terá uma branch master, com a versão release do sistema e também possui uma branch de desenvolvimento, onde os desenvolvedores concentram as alterações mais atuais (versão beta).

### Dicas adicionais

Se for preciso criar um branch e enviá-lo para o servidor 
```bash
git push origin nome-do-branch
git push --set-upstream origin nome-do-branch
```

Caso seja necessário, será possível voltar versão de um commit específico
```bash
git checkout [hash-do-commit] .
```

Se for necessário, é possível guardar temporariamente as modificações do projeto com os seguintes comandos:
```bash
git stash
```

Para ver a lista de arquivos modificados temporariamente guardados use:
```bash
git stash list
```

Para gravar as últimas alterações salvas
```bash
git stash pop
```

Para descartar as mudanças 
```bash
git stash drop
```

Referências:

* [GitHub - Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)
* [The most useful git commands](https://orga.cat/posts/most-useful-git-commands)
