---
title: Analysis of the `ph-submissions` folder structure
author: Eric Brasil
date: 2022-09-09
abstract: "As part of my work as a visiting researcher at NOVA-FCHS's DH_Lab, I am reviewing the Programming Historian guidelines, structure, and workflow, both on the website and in the organization's GitHub repository. Daniel Alves asked me to look closely at the structure of the language folders in the ph-submissions repository. So I wrote a brief report with my analysis and some proposals for standardizing the repository. I'm also writing a set of proposals regarding issues: creation of issue templates in four languages, with different options (new proposals, translations, errors). In this document I present the structure and analyze the folders of the `ph-submissions` repository. The analysis is focused on the following folders: `pt`, `es`, `en`, `fr` e `lesson`."
---

## Structure of the 4 language folders

### Portuguese - `pt/`

Present structure:

```
pt
├── licoes
│   ├── originaes
│   ├── publicadas
│   ├── traducoes
│   ├── README.md
├── README.md
```

#### Proposals


The `pt/licoes/traducoes` folder has 8 subfolders with images of translated lessons. These images should not be located here, even if they are new images produced for the translations. If these images were already placed in the `programminghistorian/jekyll/images` folder, they must be deleted.

For example, the folder `pt/licoes/traducoes/Sonificacap-dos-dados` has identical images to the folder `programminghistorian/jekyll/images/sonification`. And in the .md file of the Portuguese lesson, the image links refer to the original English images. That is, the folder `pt/licoes/traducoes/Sonificacap-dos-dados` should not exist.

The `pt/licoes/publicadas` folder was last updated 14 months ago. Therefore, many lessons in Portuguese that have already been published are not listed there.

I suggest updating the `README.md` of the `pt/` folder with the link to the editorial team page and the urls as in the Spanish file.

Seeking to standardize the folders of the four languages, I suggest moving the folders `pt/licoes/originais`, `pt/licoes/publicadas` and `pt/licoes/traducoes` to the folder `pt/`, and then delete the folder `licoes/ `. It would also be interesting to include a `lista-de-traducoes.md` (translation-list) file (as in the es and fr folders).

### Spanish - `es/`

Present structure:

```
es
├── borradores
│   ├── originales
│   ├── traducciones
├── publicadas
│   ├── originales
│   ├── traducciones
├── README.md
├── lista-de-traducciones.md
├── PLANTILLA-LECCION.md
├── PLANTILLA-PROPUESTA-LECCION.md
├── PLANTILLA-TRADUCCION.md
```

#### Proposals


I suggest excluding the files that start with `PLANTILLA...`, as they are actually issue templates, which should be in the `.github/ISSUE_TEMPLATE/` folder (see my proposal for creating issue templates for multiple languages).

### French - `fr/`

Present structure:

```
fr
├── documentation
│   ├── gabarit-texte-relecture.md
│   ├── liste-traductions.md
├── en-cours
│   ├── originales
│   ├── traductions
├── publiees
│   ├── originales
│   ├── traductions
├── README.md
```

#### Proposals


I suggest deleting the `documentation/gabarit-texte-relecture.md` file, as it must be included in the `.github/ISSUE_TEMPLATE/` folder (see proposal for creating issue templates for multiple languages). And move the `documentation/liste-traductions.md` file to `fr/`. So the `documentation/` folder can be deleted.

### English - `en/`

Present structure:

```
en
├── drafts
│   ├── originals
│   ├── translations
├── published
│   ├── originals
│   ├── translations
├── sample-lesson.md
├──.gitignore
```

#### Proposals


I suggest creating a README.md in the same pattern as other languages; excluding `.gitignore`, which is empty, and `sample-lesson.md` (unless you want to include it in all other languages).

### Structure proposal for all language folders

```
en/es/fr/pt
├── drafts/borradores/en-cours/rascunhos
│   ├── originals/originales/originales/originais
│   ├── translations/traducciones/traductions/traducoes
├── published/publicadas/publiees/publicadas
│   ├── originals/originales/originales/originais
│   ├── translations/traducciones/traductions/traducoes
├── README.md
├── translation-list.md/lista-de-traducciones.md/liste-traductions.md/lista-de-traducoes.md
```

## `lessons/` folder

Present structure:

```
lessons
├── portuguese
│   ├── propostas
├── published
├── spanish
│   ├── lecciones
│   ├── readme.md
├── enron_network_with_communities.png
├── lavorato-j.zip
├── out.html
├── sample-lesson.md
```

That folder doesn't make much sense, as it gathers varied and inconsistent files. Just by looking at its structure and files it is not possible to know what it is about. I believe it was created by mistake at some point and other files were added to it over time.

My suggestion is that the folder be deleted, after evaluation by the language teams.
