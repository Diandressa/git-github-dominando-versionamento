<!-- 
# Título  

## Descrição
O que faz o app
Com o que ele foi construído 
Por que foi construído

## Pré requisitos
  instalaçao node, git...

## Instrução de instalação
```bash
  npm install
```

## Instrução de uso
  Como utilizar o projeto em passos ou em bash. Podemos usar prints ou gifs

## Licença

### Permissão para uso comercial
### se inspirar
### Educacional
### Não comercial

## Contribuição

## Gitflow 
Quais padrões os dev podem seguir para contribuir

## badges

[![Licence](https://img.shields.io/github/license/Ileriayo/markdown-badges?style=for-the-badge)](./LICENSE) <br>
https://github.com/Ileriayo/markdown-badges/blob/master/README.md

## Contruibuidores  ou Owner (donos do projeto)
  reconhecimentos

Podemos usar templates de README
https://github.com/Fernanda-Kipper/Readme-Templates?tab=readme-ov-file 
-->

# [Curso Git e GitHub: dominando controle de versão de código - Alura](https://cursos.alura.com.br/course/git-github-dominando-controle-versao-codigo)

![Imagem do curso](/img/img.jpg)


## Descrição
Anotações das aulas e comandos relevantes.

## Pré requisitos
  * git
  * github

## Comandos 

### Status dos Commits

Comandos               | Descrição
---------              | ------
git log --oneline      | Para ver somente os títulos e hashs dos commits
git log -p             | Exibe em formato diff as alterações dos commits --- linhas removidas e +++ linhas adicionadas -p. Para visualizar as alterações em cada arquivo modificado;
git status | Qual branch estamos e se tem alterações para comitar
git diff | Mostra a diferença entre o último commit e as alterações feitas (não comitadas)

Posso comparar um commit específico com outro.

`git diff {hashcommit}..{hashcommit}`

*compara só as alterações que não adicionei para o commit ainda. 

Se informarmos apenas uma hash específica ele compara esse hash com o último comitado por padrão.


### Status dos Commits - menos usados
Comandos               | Descrição
---------              | ------
git log --graph        | Mostra a linha do tempo dos commits
git log -- pretty ou git log --format 
git log --help         | Abre o manual do git, podemos procurar pelos formats no arquivo.
git show {hash do commit} | É o git log -p para o commit específico -> mostra as alterações
git show | Sem a hash o default será o HEAD, mostra os detalhes do último commit

> HEAD é o commit mais recente da branch atual

### Branch

Comandos                 | Descrição
---------                | ------
git branch               | Mostra as ramificações existentes no projeto
git branch nomebranch    | Criar uma nova branch
git branch -m nomeatual novonome | Renomeia a branch
git branch -d nomebranch | Remover a branch
git checkout nomebranch  | Modifica a branch atual para a branch informada
git checkout -b nomenovabranch | Cria nova branch e alterna para ela = b de branch
git switch -c nomenovabranch | Cria nova branch e alterna para ela = c de create (mais atual)
git switch nomedabranch | Volta para branch desejada
git push origin novabranch | push na branch desejada

*checkout é um comando antigo, atualmente é utilizado o git switch
*posso unir dois comando em um só

### Unir Branch

Comandos                 | Descrição
---------                | ------
git merge novabranch     | Uni a branch atual com a branch informada
git branch -d branchobsoleta | Remove branch no repositório local
git push origin :branchobsoleta | Remove a branch no repositório remoto

#### Antes da unir as branchs (merge)
![Antes da merge](./img/merge1.jpg)

#### Depois de unir as branchs

*mudar para branch master e unir com a atual

![Depois do merge](./img/merge2.jpg)

Isso é o fast-foward (move adiante)

>commit merge:

Ao unir branch com estados diferentes (alterções diferentes), eles vai comitar as diferenças, posso dar push e depois deletar a branch não mais utilizada

### Anotações

#### Branch

Branch/Ramificação

Para visualizar como as branchs funcionam
https://git-school.github.io/visualizing-git/

![exemplo de branch](./img/branch.jpg)

A branch padrão é a Main (antigamente se chamava Master)

Ao criar uma nova branch preciso modificar a branch atual para essa nova

Normalmente, a branch main é o projeto final que irá para produção

#### Pull request

  Um Fork é um cópia de um repositório para nossa conta

  Ao clonar o fork e fazer o git push na branch, o seguinte aviso é dado no repositório do github

  ```This branch is 1 commit ahead of Fernanda-Kipper/Readme-Templates:main.```

  ![Pullrequest](./img/pullrequest.jpg)

  Podemos contribuir e abrir um pull request

#### Atualizando a branch (Reescrevendo a branch)

A main pode ter recebido outros commits de outros colaborados. 
Criamos a branch novafunc após a main já ser atualizada. 
No entanto, quero que a branch seja recriada em cima da versão mais atual na main.
Quero que meus commits fiquem depois da main atualizada.
Para isso podemos usar o comando
`git rebase`


![Atualizando a branch](./img/atualizando_branch.jpg)

Comandos                 | Descrição
---------                | ------
git rebase               | Reescreve a branch depois da main atualizada

Após o `git rebase main`

![Após o git rebase main](./img/atualizando_branch2.jpg)
Observe que ao realocar commit a commit na main atualizado, ele commit novamente essas alterações, por isso as hash são diferentes ao inserir-las na main.

* Preciso dar o push origin main e push origin novafunc, para atualizar as duas branchs.
* Após isso posso dar o merge em novafunc para main. para unir as duas branchs, como já fiz o rebase não dá o commit de merge. 
* Posteriormente, dou git push origin main.

Quando os merge precisam de fast-foward (tudo alinhado, sem ramificação), significa que precisa ser feito o git rebase antes do git merge.

![fast-foward](https://atlassianblog.wpengine.com/wp-content/uploads/2024/11/what-is-a-fast-forward.gif)

#### Diferença entre **git merge** x **git rebase**
O rebase uni a branch que estou trabalhando para a main, somando meus commit depois da main atualizada. Deixa tudo na mesma linha do tempo.
Já o merge mistura/mescla as branchs, no qual, preciso revisar os conflitos.

O merge junta os trabalhos de duas branches, podendo gerar um merge commit. Já o rebase aplica os commits de outra branch na branch atual.

![diferença entre merge e rebase](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2022/01/fig13.png)

## Licença
[![Licence](https://img.shields.io/github/license/Ileriayo/markdown-badges?style=for-the-badge)](./LICENSE) 
