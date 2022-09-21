# Análise bibliográfica sobre o Programming Historian (2008-2022)

Como parte do plano de trabalho que visa compreender os fluxos e estruturas de trabalho do *Programming Historian*, foi realizado um levantamento bibliográfico sobre o mesmo. Este levantamento foi organizado e analisado buscando avaliar como as publicações do *Programming Historian* (doravante *PH*) tem sido utilizadas em artigos científicos.

## Levantamento bibliográfico

Buscando mapear as publicações que utilizaram as publicações do *PH*, estruturamos o levantamento bibliográfico em duas etapas:


### Etapa 1: Publicações que citam o *PH* em suas referências bibliográficas

Buscamos publicações que contenham as palavras "programming historian" nas referências bibliográficas através do Scopus. A seguir, listamos os parâmetros da busca e os resultados obtidos.

1. site: https://www.scopus.com
2. Logado com a conta de estudante da NOVA
3. data da busca: 2022-08-16
4. parâmetro: `REF ( "programming Historian" )`
5. Resultado: 130 documentos - todos podem ser consultados [aqui](scopus.bib)
    1. journal: 86
    2. conference proceedings: 25
    3. Book: 13
    4. book series: 6 

### Etapa 2: Publicações sobre o *PH*

Buscamos publicações que contenham as palavras "programming historian" em seu título, através do Google Scholar. A seguir, listamos os parâmetros da busca e os resultados obtidos.

1. site: https://scholar.google.com.br
2. data da busca: 2022-08-04
3. parâmetro utilizado: `allintitle:"programming historian"`
4. Exclusão de citações
5. Resultados: 15 documentos - todos podem ser consultados [aqui](scholar.bib)

Todos as publicações encontradas foram armazenadas em formato `.bib` e também foram incluídas em uma coleção específica no *Zotero*. A coleção, assim como toda bibliografia restante que será utilizada nesse plano de trabalho, formará uma biblioteca pública de referências disponível para consulta on-line.

## Analisando os resultados

Devido ao caráter distinto das etapas e de suas publicações, estruturamos análises distintas para cada conjunto de publicações.

### Análise 1: Publicações que citam o *PH* em suas referências bibliográficas

Esse conjunto de publicações e seus dados foram gerados pelo *Scopus*, e nos possibilitou analisar os dados através de uma ferramenta de tratamento de dados bibliográficos chamada `bibliometrix`[^1].

[^1]: Aria, Massimo, e Corrado Cuccurullo. “Bibliometrix: An R-Tool for Comprehensive Science Mapping Analysis”. *Journal of Informetrics 11*, nº 4 (1º de novembro de 2017): 959–75. https://doi.org/10.1016/j.joi.2017.08.007.

A ferramenta é de código aberto e desenvolvida como um pacote para a linguagem de programação R. Segundo os autores,

>The bibliometrix R-package (http://www.bibliometrix.org) provides a set of tools for quantitative research in bibliometrics and scientometrics. It is written in the R language, which is an open-source environment and ecosystem. The existence of substantial, effective statistical algorithms, access to high-quality numerical routines, and integrated data visualization tools are perhaps the strongest qualities to prefer R to other languages for scientific computation. (Aria e Cuccurullo, 2017, p. 963)

Através dela é possível percorrer as três etapas do fluxo de trabalho do mapeamento científico: *data collection*, *data analysis* e *data visualization*.

Inserimos os dados obtidos pelo *Scopus* em um *dataframe* e analisamos os dados com o *bibliometrix*, através da função `biblioshiny()`.

```{r}
library(bibliometrix)
biblioshiny()
```

Com essa função, podemos analisar os dados em um app de visualização em um browser. Segundo a página oficial do *bibliometrix*:

>It supports scholars in easy use of the main features of bibliometrix:
>
>Data importing and conversion to data frame collection
>
>Data gathering using Dimensions, PubMed and Scopus APIs  collection
>
>Data filtering
>
>Analytics and Plots for four different level metrics:
>
>    - Sources  
>    - Authors  
>    - Documents   
>    - Clustering by Coupling
>
> Analysis of three structures of Knowledge (K-structures):  
>
>    - Conceptual Structure  
>    - Intellectual Structure  
>    - Social Strucutre (sic)
>
> K-SYNTH. “Biblioshiny”. Bibliometrix. Acessado 17 de agosto de 2022. https://www.bibliometrix.org/home/index.php/layout/biblioshiny.

Buscamos gerar visualizações dos dados - assim como os dados tabulares, arquivados em formato `.csv` - para cada uma das categorias supracitadas.

Os resultados das visualizações podem ser encontrados [aqui](bibliometrix/visualizations/) e os dados tabulares podem ser encontrados [aqui](bibliometrix/csvs).

### Análise 2: Publicações sobre o *PH*

Esse conjunto de publicações gerado pela busca no Google Scholar será analisado através de leitura próxima e servirão de base para as reflexões posteriores sobre o *PH*.

Utilizaremos o *QualCoder* para analisar as publicações [^2].

[^2]: Curtain, C. (2022). QualCoder (3.0) [Python]. https://github.com/ccbogel/QualCoder/releases/tag/3.0 (Original work published 2019)


### Resultados

Após as análises de ambas as etapas, será produzido um relatório com os resultados obtidos, que futuramente darão origem a um paper acerca dos usos do *PH*.
