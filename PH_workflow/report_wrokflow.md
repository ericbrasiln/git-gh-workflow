---
title: Relatório da Análise do Workflow, Estrutura e Diretrizes do Programming Historian
author: Eric Brasil
date: 2022-09-26
abstract: Este relatório apresenta as etapas da pesquisa e seus resultados entre 20 de julho de 23 de setembro de 2022. Ao longo desses dois meses de trabalho foi realizado levantamento bibliográfico sobre o Programming Historian, análise das estruturas e workflow, assim como das diretrizes que formam o projeto. A pesquisa esteve centrada na versão em português do PH, porém não esteve restrita a ela. Como resultados apresento uma série de relatórios que mapearam erros e apontam possíveis soluções - com destaque para a análise da estrutura de pastas dos quatro idiomas no repositório ph-submissions,  a proposta de Projeto Kanban para a versão em português, o conjunto de templates para issues e correções de erros e incoerências no site do PH - e uma breve análise do levantamento bibliográfico realizado.
---

# Relatório referente à fase 2

Uma representação gráfica e textual de todas as alterações realizadas no repositório `git-gh_workflow` entre 20 de julho de 23 de setembro de 2022 pode ser acessada [aqui](git_log_full_graph.txt). Nesse arquivo estão registrados todos os commits realizados. O arquivo foi gerado através do seguinte comando no Git:

```bash
$ git log --pretty=full --graph > git_log_full_graph.txt
```

Também é possível acessar uma versão em csv dos dados, clicando [aqui](git_log_oneline.csv). Essa versão mostra a *hash* abreviada do *commit*, o nome do autor, a data e o assunto. Esse arquivo foi gerado com o seguinte comando:

```bash
$ git log --date=format:'%Y-%m-%d %H:%M:%S' --pretty=format:"%h,%an,%ad,%s" > git_log_oneline.csv
```
