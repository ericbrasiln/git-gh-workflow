---
title: Sistema de Controle de Versões Git como ferramenta metodológica em projetos de História  
collection: lessons  
layout: lesson  
authors:
- Eric Brasil
---
# Índice

{% include toc.html %}

# Introdução

A lição pretende caracterizar sistemas de controle de versões, tendo o Git como exemplo, e analisar as possibilidades de seu uso para a pesquisa em História. Para tanto, pretende-se apresentar detalhadamente as principais funções e recursos do Git para o controle de versões localmente, desde a configuração inicial do programa até sua aplicação em um exemplo prático. Buscamos refletir sobre como seu uso pode consolidar práticas conscientes de registo, controle e recuperação das operações metodológicas de uma pesquisa. Pretendemos demonstrar que o fluxo de trabalho em ramos (branches), o histórico de alterações e as mensagens relacionadas a cada mudança (commits) constituem um conjunto de funcionalidades profundamente alinhadas com um procedimento metodológico rigoroso e sofisticado, fundamental para o desenvolvimento de pesquisas em humanidades que lidam com qualquer tipo de dado - especialmente os dados digitais.

Para essa lição, vamos criar um repositório local intitulado `projeto-de-pesquisa/`. Nesse repositório serão criados os ficheiros necessários para o controle de versões com Git. Buscando analisar os recursos, possibilidades e limitações do Git, criaremos exemplos variados de ficheiros de texto simples (.csv, .txt, .md) e ficheiros compactados (.docx, .pdf, xlsx, .png), além de diretórios aninhados no interior do repositório.

# Pré-requisitos

Computador ligado à internet. Terminal (Linux e Mac) ou Git Bash (Windows).

# Objectivos de aprendizagem

No final deste tutorial os participantes devem estar aptos a:
	- Compreender os sistemas de controle de versões e suas implicações metodológicas para a pesquisa;
	- Aplicar as funcionalidades básicas do fluxo de trabalho do Git a ficheiros variados;
	- Desenvolver metodologia consistente de registo e documentação das etapas da pesquisa através do Git.

# Sistema de Controle de Versões (SCV) como ferramenta metodológica

Quem nunca passou por isso?

{% include figure.html filename="phdcomics-final-doc" caption="Figura 1: Cham, Jorge. ['PHD Comics: notFinal.doc'](https://phdcomics.com/comics/archive/phd101212s.gif). Acessado 26 de setembro de 2022." %}

## O que é um sistema de controle de versões?

[explicar]

## O que é o Git?

### História

### Fluxo de trabalho

### vantagens e limitações

## Usando o Git

### Instalação

### Configuração Global

É importante configurar o Git com os dados de autoria e e-mail. Com essas informações, o Git é capaz de registrar quem realizou as alterações em dado momento. Neste tutorial, aprenderemos como definir essas informações globalmente para o computador utilizado. O git possui um arquivo de configuração intitulado `.gitconfig`. Ele armazena uma série de configurações importantes e pode ser acessado através do comando `git config --global --edit`. Para definir o nome do autor e o e-mail, é necessário executar os seguintes comandos:

- Autor

```bash
~$ git.config --global user.name "Edward Palmer Thompson"
```

- Email

```bash
~$ git.config --global user.email "epthompson@hist.com"
```

Esses comandos estão solicitando que o Git acesse o arquivo de configuração global (`git.config`), em seguida passamos a opção `--global`, definindo que as configurações valem para todos que utilizarem esse computador; por fim indicamos qual parâmetro queremos alterar, nesse caso, nome e email do autor: `user.name` e `user.email`.

- Configurar o editor de texto

```bash
~$ git.config --global core.editor "vim"
```
Você pode listar todas as configurações globais com o comando `git config --global --list`.

A seguinte saída deve ser exibida em no terminal:

```bash
user.name=Edward Palmer Thompson
user.email=epthompson@hist.com
init.defaultbranch=main
core.editor=vim
```

### Iniciar um repositório

Nesse tutorial, vamos criar um diretório vazio chamado `projeto-de-pesquisa`. É nele que você vai testar os comandos do Git e acompanhar seu fluxo de trabalho. Para isso, você deve abrir o seu Terminal[^terminal] e criar o diretório no caminho que escolher. Por exemplo, se você pretende criar o diretório `projeto-de-pesquisa` no interior do diretório `Documentos`, você deve utilizar o comando `cd` (*change directory*) e especificar esse caminho.

```bash
~$ cd ~/Documentos/
```

Em seguida, você pode executar o comando para criar um diretório: `mkdir` (*make directory*).

```bash
~/Documentos$ mkdir projeto-de-pesquisa
```

Agora você pode entrar no diretório recém-criado e verificar se ele está vazio, utilizando o comando `ls` (*list*).

```bash
~/Documentos$ cd projeto-de-pesquisa
~/Documentos/projeto-de-pesquisa$ ls
```

Nada deve aparecer em sua tela, pois o diretório ainda está vazio.

Para iniciar esse diretório como um repositório Git, você deve executar o comando para inicialização: `git init`.

<div class="alert alert-warning">
 Lembrando que todos os comandos devem ser executados no interior do diretório `projeto-de-pesquisa`.
</div>

```bash
~/Documentos/projeto-de-pesquisa$ git init
Repositório vazio Git inicializado em /home/usuario/Documentos/projeto-de-pesquisa/.git/
```

A partir de agora, o seu diretório `projeto-de-pesquisa` será um repositório submetido ao controle de versões do Git. Para verificar isso, você pode executar o comando `ls -a` (*list all*), que lista todos os arquivos e diretórios, inclusive os ocultos.

```bash
~/Documentos/projeto-de-pesquisa$ ls -a  
```

O resultado deve ser o seguinte:
    
```bash
. ..  .git
```

O comando `git init` solicitou ao Git que o diretório `projeto-de-pesquisa` recebesse uma série de arquivos e diretórios específicos para o registro e controle de alterações. Esses arquivos são ocultos, alocados no interior do diretório `.git` e tem a função de garantir que todas as modificações ocorridas no interior do diretório sejam percebidas, registradas e apresentadas a você. O Git reúne uma série de recursos para que você possa não apenas registrar esse histórico de alterações, mas também analisá-lo, recuperá-lo, e trabalhar de forma mais coesa e segura.

A estrutura de diretórios criada pelo Git é complexa e não será abordada a fundo nesse tutorial. Se listarmos os ficheiros presentas na recém-criada pasta `.git`, com o comando `ls -a .git`, obteremos o seguinte resultado:

```bash
.  ..  branches  config  description  HEAD  hooks  info  objects  refs
```

Nesse conjunto de diretórios e arquivos o Git armazena as informações sobre o repositório: desde as alterações realizadas até os dados de configuração e fluxo de trabalho. O Git é um sistema de controle de versões distribuído, ou seja, cada cópia do repositório é uma cópia completa.

### Comandos básicos

Após iniciar seu repositório com o comando `git init`, podemos criar um novo ficheiro e iniciar o registro das alterações. Assim poderemos compreender com mais clareza o funcionamento do programa.

Vamos criar um arquivo chamado `README.md`, com o conteúdo `# Exemplo para a lição` no interior de nosso diretório `projeto-de-pesquisa`. Você pode fazer isso de várias formas - com editores de texto, por exemplo. Aqui utilizarei o terminal e o comando `echo`. [^echo]

```bash
~/Documentos/projeto-de-pesquisa$ echo "# Exemplo para a lição" > README.md
```

Se você executar o comando `ls`, verá que o arquivo foi criado com sucesso.

```bash
~/Documentos/projeto-de-pesquisa$ ls
README.md
```

#### Git Status

Portanto, realizamos uma alteração em nosso repositório. Vamos verificar se o Git percebeu a mudança? Para isso, executamos o comando `git status`.

```bash
~/Documentos/projeto-de-pesquisa$ git status
```

A mensagem retornada pelo Git é a seguinte:

```bash
No ramo main

No commits yet

Arquivos não monitorados:
  (utilize "git add <arquivo>..." para incluir o que será submetido)
	README.md

nada adicionado ao envio mas arquivos não registrados estão presentes (use "git add" to registrar)
```

Vamos entender o que o Git está nos dizendo. Ao passarmos o comando `status` para o Git, ele nos informa a situação atual do repositório. Nesse momento, o Git nos informa que estamos no ramo (ou *branch*) `main`: `No ramo main`. Em seguida nos informa que não existem submissões (*commits*) ainda: `No commits yet`. Mais abaixo veremos o que são *commits* e sua importância metodológica para nossas pesquisas.

Em seguida temos a mensagem: 

```bash
Arquivos não monitorados: (utilize "git add <arquivo>..." para incluir o que será submetido)
	README.md
nada adicionado ao envio mas arquivos não registrados estão presentes (use "git add" to registrar)	
```

#### Git Add
O Git nos informa que existe um ficheiro chamado `README.md` dentro do nosso diretório que ainda não está sendo monitorado pelo sistema de controle de versões. Ou seja, o ficheiro ainda precisa ser adicionado ao repositório Git para que as alterações efetuadas nele sejam registradas.

O próprio Git nos informa o comando que devemos utilizar para registrar o ficheiro: `git add <arquivo>`. No nosso caso, devemos executar o seguinte:

``` bash
~/Documentos/projeto-de-pesquisa$ git add README.md
```

Ao solicitarmos o status do repositório agora, receberemos uma mensagem diferente:

```bash
~/Documentos/projeto-de-pesquisa$ git status
No ramo main

No commits yet

Mudanças a serem submetidas:
  (utilize "git rm --cached <arquivo>..." para não apresentar)
	new file:   README.md
```

Mais uma vez percebemos que estamos no ramo `main` e ainda não realizamos nenhuma submissão (*commits*) para esse ramo. Entretanto, não existem mais ficheiros/arquivos no estágio *não monitorados*. Nosso ficheiro `README.md`mudou de status, agora está como um novo ficheiro (*new file*) estágio `Mudanças a serem submetidas`.

[Explicar: `git rm --cached <arquivo>`. remove do index do git, mas mantém o arquivo no seu diretório de trabalho.]

#### Git Commit

Agora, as alterações que realizamos estão preparadas para serem submetidas (*commited*) ao repositório. Para isso, usamos o comando `git commit`. É importante destacar a necessidade de incluir uma mensagem para cada *commit*. [Apontar isso como elemento central para essa lição]. Existem duas formas de incluir uma mensagem ao commit. A primeira delas é mais simples e é realizada diretamente no comando `commit`:

```bash
~/Documentos/projeto-de-pesquisa$ git commit -m "Commit inicial"

[main (root-commit) 28bc6b6] Commit inicial
 1 file changed, 1 insertion(+)
 create mode 100644 README.md

```

Nesse caso, adicionamos a opção `-m` ao comando `commit` e em seguida passado o conteúdo da mensagem entre `"`. Essa opção é mais prática, mas possui limitações, como a impossibilidade de criar mensagens mais detalhadas e com quebras de linha.

Se desejarmos elaborar uma mensagem mais detalhada, utilizamos o comando `git commit`, sem a inclusão da opção `-m`. Nesse caso, o Git abrirá o editor de texto definido em suas configurações para que possamos escrever a mensagem. 

Como já havíamos realizado o commit das alterações, o Git nos informa que não há nada a ser submetido:

```bash
~/Documentos/projeto-de-pesquisa$ git commit

nothing to commit, working tree clean
```

Mas se ainda assim quisermos corrigir a mensagem do último commit, podemos utilizar a opção `--amend`:

```bash
~/Documentos/projeto-de-pesquisa$ git commit --amend
```

O Git abrirá o editor de texto para que possamos editar a mensagem do último commit. Após a edição, basta salvar e fechar o editor. No meu caso, o editor é o `vim`. Para sair do editor, basta digitar `:wq` e pressionar a tecla `Enter`.[^vim] É importante destacas que ao configurar a mensagem de commit com o editor de texto, é possível definir o título e o corpo da mensagem. 

O git considera a primeira linha da mensagem como título, e ele deve ter no máximo 50 caracteres. O restante da mensagem é considerado o corpo da mensagem e deve ser separado do título por uma linha em branco. Como no exemplo abaixo:

```bash
Criação de README.md

Este commit cria o arquivo README.md com o objetivo de explicar o funcionamento do Git.
```

Após salvar e fechar o editor, o Git nos informa que o commit foi realizado com sucesso:

```bash
[main 3588e34] Criação de README.md
 Date: Tue Dec 20 11:14:04 2022 +0000
 1 file changed, 1 insertion(+)
 create mode 100644 README.md
```

Pronto, criamos nosso ficheiro `README.md` e o adicionamos ao repositório Git com sucesso. Para isso, utilizamos o comando `git add` para adicionar o ficheiro ao *index* do Git [^git-index], e o comando `git commit` para submeter as alterações ao repositório. Vimos também como incluir a mensagem de commit diretamente na linha de comando (`git commit -m "mensagem"`) e como editar a mensagem do último commit (`git commit --amend`).

Se executarmos git status novamente, veremos que não há mais nada a ser submetido:

```bash
~/Documentos/projeto-de-pesquisa$ git status

No ramo main

nothing to commit, working tree clean
```

### Estágios de um arquivo

Agora que já sabemos como adicionar um ficheiro ao repositório Git e como submeter alterações acompanhadas de mensagens, vamos detalhar e analisar os diferentes estágios de um arquivo no Git. Para isso vamos criar um arquivo novo chamado `resumo.txt` e salvá-lo no diretório `projeto-de-pesquisa`. 

```bash
~/Documentos/projeto-de-pesquisa$ touch resumo.txt
```

A ferramenta `touch` permite criar um ficheiro com o nome especificado, mas você pode criar esse ficheiro utilizando qualquer outro método. 

Se listarmos o conteúdo do diretório `projeto-de-pesquisa` veremos que agora existem dois ficheiros:

```bash
~/Documentos/projeto-de-pesquisa$ ls
README.md  resumo.txt
```

Como vimos anteriormente, um ficheiro recém criado em nosso diretório de trabalho se encontra no estágio **não monitorado** (*untracked*) e precisa ser **preparado** (*staged*) para ser **submetido** (*commited*). Podemos ver sua situação com um `git status`.

```bash
~/Documentos/projeto-de-pesquisa$ git status
No ramo main
Arquivos não monitorados:
  (utilize "git add <arquivo>..." para incluir o que será submetido)
	resumo.txt

nada adicionado ao envio mas arquivos não registrados estão presentes (use "git add" to registrar)

```

Para preparar o ficheiro, utilizamos `git add <nome do ficheiro>`.

```bash
~/Documentos/projeto-de-pesquisa$ git add resumo.txt
```

A partir do momento que o ficheiro foi registrado (*staged*) no Git, ele muda de estágio e está pronto para ser submetido (*commit*), como podemos ver executando um `git status`.

```bash
~/Documentos/projeto-de-pesquisa$ git status
No ramo main
Mudanças a serem submetidas:
  (use "git restore --staged <file>..." to unstage)
	new file:   resumo.txt
```

Ou seja, `resumo.txt` é um novo ficheiro que está pronto para ser submetido ao index do Git. 

```bash
~/Documentos/projeto-de-pesquisa$ git commit -m "Criação do ficheiro para o resumo do tutorial"
[main 3b9a93d] Criação do ficheiro para o resumo do tutorial
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 resumo.txt
```

A mensagem retornada nos informa que um ficheiro foi criado, sem nenhuma inserção ou exclusão de conteúdos.

A partir de agora, o ficheiro `resumo.txt`, assim como o `README.md`, está inserido no repositório Git que realizado o controle de versões, ou seja, registra e avalia todas as mudanças que são realizadas. 

Vamos alterar o conteúdo dos dois ficheiros para entendermos esse processo.

Primeiro vamos inserir uma frase no ficheiro `resumo.txt`. Para isso você pode abri-lo em qualquer editor de texto, escrever a frase "Resumo: Esse tutorial pretende apresentar as funções básicas do Git." e salvá-lo. Depois, abra o ficheiro `README.md` e inclua a frase "Lição para o Programming Historian", salvando em seguida. Realizamos alterações em dois ficheiros do nosso diretório de trabalho, ambos registrado e monitorados pelo Git. Vejamos quais informações o comando status nos apresenta:

```bash
~/Documentos/projeto-de-pesquisa$ git status
No ramo main
Changes not staged for commit:
  (utilize "git add <arquivo>..." para atualizar o que será submetido)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   README.md
	modified:   resumo.txt

nenhuma modificação adicionada à submissão (utilize "git add" e/ou "git commit -a")
```

A mensagem informa que dois ficheiros foram modificados e ainda não foram preparados para submissão (*changes not staged for commit*). Para inserir essas mudanças e prepará-las para o *commit*, devemos utilizar o comando `git add <nome do ficheiro>`. É possível incluir mais de um ficheiro no mesmo comando, por exemplo:

```bash
~/Documentos/projeto-de-pesquisa$ git add README.md resumo.txt
```

É possível especificar que todos os ficheiros presentes no diretório de trabalho sejam preparados ao mesmo tempo, utilizando `git add .`.

Agora que preparamos as mudanças para submissão, os ficheiros aparecem com o status **modificados** (*modified*):

```bash
~/Documentos/projeto-de-pesquisa$ git status
No ramo main
Mudanças a serem submetidas:
  (use "git restore --staged <file>..." to unstage)
	modified:   README.md
	modified:   resumo.txt
```

Para submeter essas mudanças é preciso utilizar o comando *commit*. Podemos fazer um único commit para as mudanças em todos os ficheiros, ou especificar um commit para cada um deles. Por exemplo:

```bash
~/Documentos/projeto-de-pesquisa$ git commit README.md -m "Atualização dos dados da lição"
[main 4fdb7f7] Atualização dos dados da lição
 1 file changed, 2 insertions(+)
```

```bash
~/Documentos/projeto-de-pesquisa$ git commit resumo.txt -m "Inclusão do resumo"
[main 6cc74b6] Inclusão do resumo
 1 file changed, 1 insertion(+)
``` 

Resumindo: toda vez que um novo ficheiro for criado ele precisa ser preparado (`git add`) e submetido (`git commit`), as submissões devem vir acompanhadas de uma mensagem explicativa sobre o que foi feito. Cada alterações realizada em qualquer ficheiro presente no diretório de trabalho deve ser também preparada e submetida com uma mensagem clara e explicativa. É possível consultar a condição do diretório de trabalho com o `git status`, o que nos possibilita perceber com clareza quais ficheiros são novos, estão modificados ou ainda precisam ser preparados e submetidos.

## Como escrever uma mensagem de commit eficiente?

[explicar]

### Recuperando informações

[Importância para o processo metodológico]
#### git log

- oneline
- graph
- to csv

### Fluxo de trabalho com Branches

[explicar o que é um branch]
[falar sobre o merge]

---

[^terminal]: Ver a melhor forma de falar sobre ele. Indicar a lição sobre bash no PH.
[^echo]: Explorar melhor o comando echo.
[^vim]: Ver a lição sobre o editor de texto vim.