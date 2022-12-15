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

Nesse conjunto de diretórios e arquivos, o Git armazena as informações sobre o repositório: desde as alterações realizadas até os dados de configuração e fluxo de trabalho. O Git é um sistema de controle de versões distribuído, ou seja, cada cópia do repositório é uma cópia completa.

Após iniciar seu repositório com o comando `git init`, podemos criar um ficheiro no seu interior e iniciar o registro das alterações. Assim poderemos compreender com mais clareza o funcionamneto do programa.

Vamos criar um arquivo chamado `README.md`, com o conteúdo `# Exemplo para a lição` no interior de nosso diretório `projeto-de-pesquisa`. Você pode fazer isso de várias formas - com editores de texto, por exemplo. Aqui utilizarei o terminal e o comando `echo`.

```bash
~/Documentos/projeto-de-pesquisa$ echo "# Exemplo para a lição" > README.md
```

Se você executar o comando `ls`, verá que o arquivo foi criado com sucesso.

```bash
~/Documentos/projeto-de-pesquisa$ ls
README.md
```

Portanto, realizamos uma alteração em nosso repositório. Vamos verificar se o Git percebeu a mudança que fizemos? Para isso, executamos o comando `git status`.

```bash
~/Documentos/projeto-de-pesquisa$ git status
```

### Estágios de um arquivo

- Não monitorado (*untracked*)
- Modificado (*modified*) e não preparado (*not staged*)
- Preparado (*staged*) para ser submetido (*commited*)
- Comitado (*commited*)

[^terminal]: Ver a melhor forma de falar sobre ele. Indicar a lição sobre bash no PH.