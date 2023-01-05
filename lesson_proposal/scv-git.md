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

>Version control is a system that records changes to a file or set of files over time so that you can recall specific versions later.  

Como se você possuísse uma máquina do tempo, capaz de te levar de volta a qualquer ponto na história de mudanças de uma ficheiro.

### Centralizado X Distribuído


[explicar]

## O que é o Git?

> “Git manages the evolution of a set of files – called a repository or repo – in a sane, highly structured way.” (Bryan, 2018, p. 2)
> 
- Sistema de controle de versões
- Distribuído
- Repositório Local
- Livre e gratuito
### História

### Fluxo de trabalho

### Vantagens

- Controle de histórico
- Trabalho em equipe
- Ramificações (Branches)
- Segurança
- Organização
- Integração com repositórios remotos (como o GitHub)

### Limitações

- Curva de aprendizagem mais elevada
- Maior dificuldade de lidar com arquivos zippados/compactados
- Pode gerar históricos muito pesados
- Repositório Local

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

[main (root-commit) 861b527] Commit inicial
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
[main 93a5660] Criação de README.md
 Date: Thu Jan 5 11:47:12 2023 +0000
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
[main 48f3c9d] Criação do ficheiro para o resumo do tutorial
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

Para submeter essas mudanças é preciso utilizar o comando *commit*. Podemos fazer um único commit para as mudanças em todos os ficheiros e escrever uma mensagem detalhada. Por exemplo:

```bash
~/Documentos/projeto-de-pesquisa$ git commit
# o editor de texto padrão do sistema operacional será aberto e você poderá escrever a mensagem
```

```vim
Atualização dos dados da lição

- Inclusão de autoria no README.md
- Atualização do texto em resumos.txt

# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
#
# No ramo main
# Mudanças a serem submetidas:
#       modified:   README.md
#       modified:   resumo.txt
#
``` 
[Salvar  e fechar o editor]

```bash
[main 572f33f] Atualização dos dados da lição
 2 files changed, 2 insertions(+)
```

Resumindo: toda vez que um novo ficheiro for criado ele precisa ser preparado (`git add`) e submetido (`git commit`), as submissões devem vir acompanhadas de uma mensagem explicativa sobre o que foi feito. Cada alterações realizada em qualquer ficheiro presente no diretório de trabalho deve ser também preparada e submetida com uma mensagem clara e explicativa. É possível consultar a condição do diretório de trabalho com o `git status`, o que nos possibilita perceber com clareza quais ficheiros são novos, estão modificados ou ainda precisam ser preparados e submetidos.

## Como escrever uma mensagem de commit eficiente?

Parte significativa do nosso trabalho de pesquisa, escrita e ensino atualmente é mediado por ferramentas digitais, ao mesmo tempo que dados digitais se tornam cada vez mais centrais para as Ciências Sociais e Humanas. Sejam buscas on-line em repositórios, trocas de mensagens por aplicativos, leitura de informações com editores de texto e planilhas, seja a aplicação de linguagem de programação para análise textual, visualização de dados entrou tantas outras possibilidades. A seleção, coleta, organização e tratamento dos dados que pretendemos utilizar em pesquisa, artigos ou aulas nos demanda atualmente cuidados diferentes e adicionais daqueles para os quais fomos treinados em nossa formação anterior à virada digital. Nas palavras de Fridlunnd, Oiva e Paju:

>Os métodos de pesquisa digital criam demandas novas e às vezes mais rigorosas de precisão, pensamento metodológico, auto-organização e colaboração do que a pesquisa histórica tradicional" (FRIDLUND; OIVA; PAJU, 2020, pos. 543).

Um caminho importante na busca de sanar essas novas demandas, é a transparência metodológica. Nas palavras de Gibbs e Owens:

>novos métodos usados para explorar e interpretar dados históricos exigem um novo nível de transparência metodológica na escrita histórica. Exemplos incluem discussões de consultas de dados, fluxos de trabalho com ferramentas específicas e a produção e interpretação de visualizações de dados. No mínimo, as publicações de pesquisa dos historiadores precisam refletir novas prioridades que explicam o processo de interfacear, explorar e, em seguida, compreender as fontes históricas de uma forma fundamentalmente digital - ou seja, a hermenêutica dos dados. (Gibbs e Owens, 2013: 159)

É fundamental criar um plano para organização, documentação, preservação e compartilhamento dos dados, métodos e resultados da pequisa.

Veja essa lição de James Backer sobre preservação dos dados de investigação para outras estratégias e referências.

- Metadados (como você descreve seus dados, tanto internamente quanto externamente)
- Documentação (uma descrição narrativa do projeto)
- Preservação (como os dados podem ser mantidos para uso no futuro)

Podemos enfrentar boa parte desses desafios utilizando programas de controle de versões, como o git.

- Controle de versões (o que fazer se você fizer uma  lambança no processo)

Encarar o processo de documentação como um processo público, mesmo que não seja publicado.

Baker: https://programminghistorian.org/pt/licoes/preservar-os-seus-dados-de-investigacao

>- Fazer documentação que capture de maneira precisa e consistente o conhecimento tácito em torno do processo de pesquisa, seja em relação às notas, geração de dados ou acumulação de evidências visuais.
>-Simplificar o processo de documentar, usando formatos de ficheiro e práticas de notação independentes da plataforma e legíveis por máquina.
>- Criar tempo para atualizar e documentar o fluxo de trabalho sem permitir que o trabalho de documentação se torne um fardo.
>- Investir para deixar um rasto de papel agora e economizar tempo na tentativa de reconstruí-lo no futuro.

Ao escrever uma mensagem de *commit* lembre-se que ela servirá como documentação do seu processo de pesquisa/escrita. Cada alteração ou conjunto de alterações realizada nos ficheiros de seu diretório deve vir acompanhada de uma mensagem que registre as mudanças efetuadas. Essas informações são registradas pela Git com um conjunto de metadados importantes para o acompanhamento metodológico de seu trabalho: nome do autor da mudança, data e hora, mensagem e uma identificação única - uma *hash* de 40 caracteres - que permite a identificação da versão do arquivo.

A melhor forma de escrever a mensagem de *commit* é utilizar `git commit` sem a opção `-m`, pois nos permite escrever mensagens mais  longas do que 50 caracteres (limite da opção `-m`) e incluir quebras de linha e um título para nossa mensagem. Como descrito anteriormente, o `git commit` abre o editor de texto padrão do seus sistema operacional - ou o editor que você configurou no git - para que você possa escrever a mensagem de *commit*.

No meu caso, o editor é o vim, e a mensagem de *commit* ficaria assim:

```vim
Título da mensagem de commit

Descrição da mensagem de commit
# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
#
# No ramo main
# Mudanças a serem submetidas:
#    modified:   resumo.txt
#
```

Após escrever a mensagem, salve o arquivo e feche o editor. A mensagem de *commit* será registrada no repositório local.

### Recuperando informações

[Importância para o processo metodológico]
#### git log

Para recuperarmos as informações submetidas ao repositório local, podemos utilizar o comando `git log`. Esse comando será muito útil para acessarmos as informações sobre o histórico de alterações em nossos ficheiros e avaliarmos o progresso do trabalho.

```bash
~/Documentos/projeto-de-pesquisa$ git log
commit 572f33fbe94ee6612b29be5bbee81d6672c162fa (HEAD -> main)
Author: Edward Palmer Thompson <epthompson@hist.com>
Date:   Thu Jan 5 12:01:16 2023 +0000

    Atualização dos dados da lição
    
    - Inclusão de autoria no README.md
    - Atualização do texto em resumos.txt

commit 48f3c9d3e7e419de8f29a58211dc7e97957c7b2f
Author: Edward Palmer Thompson <epthompson@hist.com>
Date:   Thu Jan 5 11:50:41 2023 +0000

    Criação do ficheiro para o resumo do tutorial

commit 93a56606662ee3f37846d9623fb03d29b2f21135
Author: Edward Palmer Thompson <epthompson@hist.com>
Date:   Thu Jan 5 11:47:12 2023 +0000

    Criação de README.md
    
    Este commit cria o arquivo README.md com o objetivo de explicar o funcionamento do Git.
```

Podemos perceber que o `git log` nos retorna a lista de commits realizados no repositório local. Os nossos três commits estão detalhados com várias informações importantes. A primeira coisa a se notar é que os commits são listados do mais recente para o mais antigo. Assim, o último commit realizado é o primeiro da lista. Vamos analisá-lo com mais atenção.

Em sua primeira linha, temos a seguinte informação:

```bash
commit 572f33fbe94ee6612b29be5bbee81d6672c162fa (HEAD -> main)
```

Encontramos o número de identificação do commit com 40 caracteres. Não se assuste, não há necessidade de ler esse número nem entender como ele é gerado para utilizar o Git. O importante é saber que cada commit possui um identificador único, possibilitando seu acesso e recuperação dentro do banco de dados do sistema de controle de versões. Na verdade, é possível utilizar os 7 primeiros caracteres para encontrar e referenciar commits específicos. Por exemplo, esse commit pode ser identificado por `572f33f` e o Git será capaz de encontrá-lo. A importância dessa identificação única para cada alteração reside justamente na posibilidade de se acessar cada mudança a qualquer momento e, inclusive, retornar o repositório para a condição que se encontrava naquele momento do tempo.

A informação que se segue também é importante, mas fará mais sentido adiante. `(HEAD -> main)` está indicando que o commit mais recente está apontando para o ramo (*branch*) *main*.  Ou seja, você está trabalhando atualmente em uma linha do tempo chamada main, e todas as mudanças que realizar incidirão sobre ela. Mais a frente veremos que é possível criar outras linhas de trabalho ou ramificações, criar alterações nos ficheiros e não afetar as informações contidas em outros ramos.

Nas duas linhas seguintes, temos a autoria e data relativa ao *commit*:

```bash
Author: Edward Palmer Thompson <epthompson@hist.com>
Date:   Thu Jan 5 12:01:16 2023 +0000
```

Os dados do autor - nome e email -  são retirados da configuração que realizamos no início da lição com o comado `git config user.name` e `git config user.mail`. A data e a hora estão no padrão do Git, mas também podem ser configuradas[^config-date].

Em seguida, podemos ler a mensagem do *commit*, sendo a primeira linha entendida pelo Git como seu título:

```bash
    Atualização dos dados da lição
    
    - Inclusão de autoria no README.md
    - Atualização do texto em resumos.txt
```

O comando `git log` possui várias opções que são úteis para acompanharmos e recuperarmos dados sobre o processo metodológico do nosso trabalho. Abaixo, veremos algumas, mas a lista completo pode ser acessada na [página de documentação do Git](https://git-scm.com/docs/git-log/pt_BR).

Podemos ver todos os commits listados em apenas uma linhas, acrescentando a opção `--oneline` ao comando `git log`, o que pode ser útil para uma leitura mais rápida e concisa das alterações:

```bash
~/Documentos/projeto-de-pesquisa$ git log --oneline
572f33f (HEAD -> main) Atualização dos dados da lição
48f3c9d Criação do ficheiro para o resumo do tutorial
93a5660 Criação de README.md
```


Com essa opção, a lista de commits do atual ao mais antigo, apresenta os sete caracteres iniciais da identificação e o título da mensagem.

Também é possível acessarmos um commit específico dessa lista, informando os sete caracteres iniciais:

```bash
~/Documentos/projeto-de-pesquisa$ git log 93a5660
commit 93a56606662ee3f37846d9623fb03d29b2f21135
Author: Edward Palmer Thompson <epthompson@hist.com>
Date:   Thu Jan 5 11:47:12 2023 +0000

    Criação de README.md
    
    Este commit cria o arquivo README.md com o objetivo de explicar o funcionamento do Git.
```

Podemos acessar o histórico de um ficheiro ou diretório específico, incluindo as diferenças, com opção `-p` ou `--path`:

```bash
~/Documentos/projeto-de-pesquisa$ git log -p resumo.txt
commit 572f33fbe94ee6612b29be5bbee81d6672c162fa (HEAD -> main)
Author: Edward Palmer Thompson <epthompson@hist.com>
Date:   Thu Jan 5 12:01:16 2023 +0000

    Atualização dos dados da lição
    
    - Inclusão de autoria no README.md
    - Atualização do texto em resumos.txt

diff --git a/resumo.txt b/resumo.txt
index e69de29..bd25a49 100644
--- a/resumo.txt
+++ b/resumo.txt
@@ -0,0 +1 @@
+Resumo: Esse tutorial pretende apresentar as funções básicas do Git.

commit 48f3c9d3e7e419de8f29a58211dc7e97957c7b2f
Author: Edward Palmer Thompson <epthompson@hist.com>
Date:   Thu Jan 5 11:50:41 2023 +0000

    Criação do ficheiro para o resumo do tutorial

diff --git a/resumo.txt b/resumo.txt
new file mode 100644
index 0000000..e69de29

- oneline
- path
- grep
- graph
- pretty-formats
- to csv

### Fluxo de trabalho com Branches

[explicar o que é um branch]
[falar sobre o merge]

# Leituras adicionais

Eric Brasil. (2022, May 20). Criação, manutenção e divulgação de projetos de História em meios digitais: git, GitHub e o Programming Historian. Zenodo. https://doi.org/10.5281/zenodo.6566754

James Baker, "Preservar os seus dados de investigação", traduzido por Márcia T. Cavalcanti, Programming Historian em português 1 (2021), https://doi.org/10.46430/phpt0001.

Bird, Christian, Peter C. Rigby, Earl T. Barr, David J. Hamilton, Daniel M. German, e Prem Devanbu. “The promises and perils of mining git”. Em 2009 6th IEEE International Working Conference on Mining Software Repositories, 1–10, 2009. https://doi.org/10.1109/MSR.2009.5069475.

Bryan, Jennifer. “Excuse Me, Do You Have a Moment to Talk About Version Control?” The American Statistician 72, nº 1 (2 de janeiro de 2018): 20–27. https://doi.org/10.1080/00031305.2017.1399928.

Chacon, Scott, e Ben Straub. Pro Git. 2º edição. Apress, 2014.

Loeliger, Jon, e Matthew McCullough. Version Control with Git: Powerful tools and techniques for collaborative software development. 2º edição. Sebastopol, CA: O’Reilly Media, 2012.

Ram, Karthik. “Git can facilitate greater reproducibility and increased transparency in science”. Source Code for Biology and Medicine 8, nº 1 (28 de fevereiro de 2013): 7. https://doi.org/10.1186/1751-0473-8-7.

---

[^terminal]: Ver a melhor forma de falar sobre ele. Indicar a lição sobre bash no PH.
[^echo]: Explorar melhor o comando echo.
[^vim]: Ver a lição sobre o editor de texto vim.
[^config-date]: falar sobre configuração de data e hora ou linkar manual do git