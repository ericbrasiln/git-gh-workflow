---
title: Proposal to create a set of issues templates in multiple languages
author: Eric Brasil
date: 2022-09-16
abstract: "As part of my work as a visiting researcher at NOVA-FCHS's DH_Lab, I am reviewing the Programming Historian guidelines, structure, and workflow, both on the website and in the organization's GitHub repository. After talking with Daniel Alves and Anisa Hawes, I present here a proposal to create a set of issue templates in four languages, with different options (new proposals, translations, errors)."
---

In GitHub is possible to set up issue templates, which are pre-formatted text that users can fill out when creating a new issue. This is a very useful tool for standardizing the creation of issues, and also for encouraging users to provide the necessary information for the issue to be resolved.

## Proposal

I suggest creating a set of issue templates in four languages, with different options (new proposals, translations, errors). The templates should be located in the `.github/ISSUE_TEMPLATE/` folder of the `programminghistorian/ph-submissions` repository. The templates should be in the following languages:

- English
- French
- Spanish
- Portuguese

## YAML front matter

```yaml
---
name: Template Title
about: Template description
title: ''
labels: ''
assignees: ''

---

Add template content here.
```

## English template

### New proposal

```yaml
---
name: EN - New lesson proposal
about: Suggest a new lesson for the Programming Historian
title: New lesson proposal for the Programming Historian
labels: 1. Submission, English
assignees: 

---

The Programming Historian has received the following proposal for a lesson on 'PROVISIONAL LESSON TITLE' by AUTHOR(S) NAME(S). The proposed learning outcomes of the lesson are:
     
- key learning outcome 1
- key learning outcome 2
- key learning outcome 3 (add as needed)
 	
In order to promote speedy publication of this important topic, we have agreed to a submission date of no later than [90 DAYS BY DEFAULT BY LONGER IF AGREED WITH EDITOR]. The author(s) agree to contact the editor in advance if they need to revise the deadline.
 
If the lesson is not submitted by [THE AGREED DATE], the editor will attempt to contact the author(s). If they do not receive an update, this ticket will be closed. The ticket can be reopened at a future date at the request of the author(s).
 
The main editorial contact for this lesson is [EDITOR USERNAME].

Our dedicated Ombudsperson is (Ian Milligan - http://programminghistorian.org/en/project-team). Please feel free to contact him at any time if you have concerns that you would like addressed by an impartial observer. Contacting the ombudsperson will have no impact on the outcome of any peer review.

```

### Peer review process

#### Original

```yaml
---
name: EN - Peer review process - Original lesson
about: Begin the peer review process for an original lesson
title: Review of lesson [TITLE]
labels: 2. Initial Edit, English
assignees: 

---

The Programming Historian has received the following tutorial on [TITLE] by [INSERT GITHUB HANDLE OF AUTHOR HERE]. This lesson is now under review and can be read at:

http://programminghistorian.github.io/ph-submissions/en/lessons/LESSON-SLUG-HERE

Please feel free to use the line numbers provided on the preview if that helps with anchoring your comments, although you can structure your review as you see fit.

I will act as editor for the review process. My role is to solicit two reviews from the community and to manage the discussions, which should be held here on this forum. I have already read through the lesson and provided feedback, to which the author has responded.

Members of the wider community are also invited to offer constructive feedback which should post to this message thread, but they are asked to first read our Reviewer Guidelines (http://programminghistorian.org/reviewer-guidelines) and to adhere to our anti-harassment policy (below). We ask that all reviews stop after the second formal review has been submitted so that the author can focus on any revisions. I will make an announcement on this thread when that has occurred.

I will endeavor to keep the conversation open here on Github. If anyone feels the need to discuss anything privately, you are welcome to email me. 

Our dedicated Ombudsperson is (Ian Milligan - http://programminghistorian.org/en/project-team). Please feel free to contact him at any time if you have concerns that you would like addressed by an impartial observer. Contacting the ombudsperson will have no impact on the outcome of any peer review.

## Anti-Harassment Policy

This is a statement of the Programming Historian's principles and sets expectations for the tone and style of all correspondence between reviewers, authors, editors, and contributors to our public forums.

> The Programming Historian is dedicated to providing an open scholarly environment that offers community participants the freedom to thoroughly scrutinize ideas, to ask questions, make suggestions, or to requests for clarification, but also provides a harassment-free space for all contributors to the project, regardless of gender, gender identity and expression, sexual orientation, disability, physical appearance, body size, race, age or religion, or technical experience. We do not tolerate harassment or ad hominem attacks of community participants in any form. Participants violating these rules may be expelled from the community at the discretion of the editorial board. Thank you for helping us to create a safe space.
    
```

#### Translation

```yaml
---
name: EN - Peer review process - Translation
about: Begin the peer review process for a translation
title: Review of translation of [TITLE]
labels: 2. Initial Edit, English, Translation
assignees: 

---

The Programming Historian has received the following translation proposal [TRANSLATION TITLE] on the lesson [TITLE] by [INSERT GITHUB HANDLE OF AUTHOR HERE]. This translation is now under review and can be read at:

http://programminghistorian.github.io/ph-submissions/en/lessons/LESSON-SLUG-HERE

Please feel free to use the line numbers provided on the preview if that helps with anchoring your comments, although you can structure your review as you see fit.

I will act as editor for the review process. My role is to solicit two reviews from the community and to manage the discussions, which should be held here on this forum. I have already read through the lesson and provided feedback, to which the author has responded.

Members of the wider community are also invited to offer constructive feedback which should post to this message thread, but they are asked to first read our Reviewer Guidelines (http://programminghistorian.org/reviewer-guidelines) and to adhere to our anti-harassment policy (below). We ask that all reviews stop after the second formal review has been submitted so that the author can focus on any revisions. I will make an announcement on this thread when that has occurred.

I will endeavor to keep the conversation open here on Github. If anyone feels the need to discuss anything privately, you are welcome to email me. 

Our dedicated Ombudsperson is (Ian Milligan - http://programminghistorian.org/en/project-team). Please feel free to contact him at any time if you have concerns that you would like addressed by an impartial observer. Contacting the ombudsperson will have no impact on the outcome of any peer review.

## Anti-Harassment Policy

This is a statement of the Programming Historian's principles and sets expectations for the tone and style of all correspondence between reviewers, authors, editors, and contributors to our public forums.

> The Programming Historian is dedicated to providing an open scholarly environment that offers community participants the freedom to thoroughly scrutinize ideas, to ask questions, make suggestions, or to requests for clarification, but also provides a harassment-free space for all contributors to the project, regardless of gender, gender identity and expression, sexual orientation, disability, physical appearance, body size, race, age or religion, or technical experience. We do not tolerate harassment or ad hominem attacks of community participants in any form. Participants violating these rules may be expelled from the community at the discretion of the editorial board. Thank you for helping us to create a safe space.
    
```

## Portuguese templates

### New lesson proposal

```yaml
---
name: PT - Lição proposta
about: Nova lição proposta para o Programming Historian em Português
title: Proposta de lição original [TÍTULO]
labels: 1.Submission, Portuguese
assignees:

---

O Programming Historian em português recebeu a seguinte proposta de lição sobre 'TÍTULO PROVISÓRIO DA LIÇÃO' pelo(s) NOME(S) DO AUTOR(ES). Os objectivos de aprendizagem propostos são:

- objectivo de aprendizagem 1
- objectivo de aprendizagem 2
- objectivo de aprendizagem 3 (adicionar conforme necessário)

Para promover uma publicação rápida deste importante tópico, foi acordada a data de submissão para o mais tardar em [90 DIAS POR DEFEITO, MAS PODE SER MAIS TEMPO, SE ACORDADO COM O EDITOR]. O(s) autor(es) concordam em entrar em contato com o editor com antecedência se precisarem de ajustar o prazo.

Se a lição não for enviada até [DATA ACORDADA], o editor tentará entrar em contato com o(s) autor(es). Se não for recebida uma atualização, a issue será encerrada. Mas poderá ser reaberta no futuro, a pedido do(s) autor(es).

O contato editorial principal desta lição é [USERNAME DO EDITOR]. Se houver alguma preocupação dos autores, eles podem entrar em contato com o nosso mediador independente.
```

### Peer review process

#### Original lesson

```yaml
---
name: PT - Processo de revisão por pares - Lição original
about: Iniciar o processo de revisão por pares para uma lição proposta
title: Revisão da lição original [TÍTULO DA LIÇÃO]
labels: 2. Initial Edit, Portuguese
assignees:

---

O Programming Historian em português recebeu a proposta sobre '[TÍTULO DA LIÇÃO]' do autor [USERNAME NO GITHUB DO AUTOR]. Esta lição está agora em revisão e pode ser lida em:

http://programminghistorian.github.io/ph-submissions/pt/licoes/originais/[NOME-DO-FICHEIRO-AQUI]

Eu serei o editor no processo de revisão. O meu papel é solicitar duas revisões da comunidade e gerir as discussões, que devem ser realizadas aqui neste fórum. Eu já li a lição e forneci feedback, ao qual o autor respondeu.

Os membros da comunidade em geral também são convidados a oferecer feedback construtivo que deve ser publicado neste canal, mas é solicitado que leiam primeiro as diretrizes para revisores (/directrizes-revisor) e sigam a nossa política anti-assédio (abaixo). Pedimos que todas as revisões parem após o envio da segunda revisão formal para que o autor possa concentrar-se no ajuste da lição. Eu farei um anúncio neste tópico quando isso ocorrer.

Vou me esforçar para manter a conversa aberta aqui no GitHub, mas se alguém sentir a necessidade de discutir algo em particular, pode entrar em contato comigo, ou pode sempre recorrer para o nosso mediador independente se achar necessário.

Política anti-assédio
_

Esta é uma declaração de princípios do *Programming Historian em português* e define o tom e estilo de toda a comunicação entre revisores, autores, editores e participantes.

O *Programming Historian em português* dedica-se a criar um ambiente académico aberto em que os membros da comunidade podem examinar em liberdade e detalhadamente ideias, fazer perguntas, sugestões ou pedir esclarecimentos. Este espaço tem que ser livre de assédio para todos no projeto, independentemente do género, identidade e expressão de género, orientação sexual, deficiência, aparência física, raça, idade, religião ou experiência técnica. Não é tolerado qualquer assédio ou ataque *ad hominem* a membros da comunidade de nenhuma forma. Os membros que violarem estas regras podem ser expulsos da comunidade, por avaliação do conselho editorial. Se alguém testemunhar ou sentir que foi vítima das atividades descritas acima, entre em contato com o nosso mediador independente. Obrigado por nos ajudar a criar um espaço seguro.
```

#### Translation

```yaml
---
name: PT - Processo de revisão por pares - Tradução
about: Iniciar o processo de revisão por pares para uma tradução proposta
title: Revisão da tradução de [TÍTULO DA LIÇÃO]
labels: 2. Initial Edit, Portuguese, Translation
assignees: 

---

O Programming Historian em português recebeu a proposta de tradução da lição '[TÍTULO DA LIÇÃO]' do autor [USERNAME NO GITHUB DO AUTOR]. Esta lição está agora em revisão e pode ser lida em:

http://programminghistorian.github.io/ph-submissions/pt/licoes/traducoes/[NOME-DO-FICHEIRO-AQUI]

Eu serei o editor no processo de revisão. O meu papel é solicitar duas revisões da comunidade e gerir as discussões, que devem ser realizadas aqui neste fórum. Eu já li a lição e forneci feedback, ao qual o autor respondeu.

Os membros da comunidade em geral também são convidados a oferecer feedback construtivo que deve ser publicado neste canal, mas é solicitado que leiam primeiro as diretrizes para revisores (/directrizes-revisor) e sigam a nossa política anti-assédio (abaixo). Pedimos que todas as revisões parem após o envio da segunda revisão formal para que o autor possa concentrar-se no ajuste da lição. Eu farei um anúncio neste tópico quando isso ocorrer.

Vou me esforçar para manter a conversa aberta aqui no GitHub, mas se alguém sentir a necessidade de discutir algo em particular, pode entrar em contato comigo, ou pode sempre recorrer para o nosso mediador independente se achar necessário.

Política anti-assédio
_

Esta é uma declaração de princípios do *Programming Historian em português* e define o tom e estilo de toda a comunicação entre revisores, autores, editores e participantes.

O *Programming Historian em português* dedica-se a criar um ambiente académico aberto em que os membros da comunidade podem examinar em liberdade e detalhadamente ideias, fazer perguntas, sugestões ou pedir esclarecimentos. Este espaço tem que ser livre de assédio para todos no projeto, independentemente do género, identidade e expressão de género, orientação sexual, deficiência, aparência física, raça, idade, religião ou experiência técnica. Não é tolerado qualquer assédio ou ataque *ad hominem* a membros da comunidade de nenhuma forma. Os membros que violarem estas regras podem ser expulsos da comunidade, por avaliação do conselho editorial. Se alguém testemunhar ou sentir que foi vítima das atividades descritas acima, entre em contato com o nosso mediador independente. Obrigado por nos ajudar a criar um espaço seguro.
```

## Spanish templates

### Lesson proposal

```yaml
---
name: ES - Propuesta de lección
about: Propor una lección para el Programming Historian en español
title: Propuesta de lección [TÍTULO]
labels: 1. Submission, Spanish
assignees: 

---

*The Programming historian* ha recibido una propuesta de lección con el título provisional ‘Título provisional de la lección’ por parte de ‘Nombre del autor o autores’. Los objetivos de la lección son:

	- objetivo nº1
	- objetivo nº2
	- objetivo nº3

A fin de promover una publicación a tiempo, se ha acordado que la lección se entregará en un plazo de [90 days por defecto o más tarde si se ha establecido así con el autor]. El autor o autores contactará con antelación con el editor si no puede cumplir con la fecha de entrega y necesita una ampliación.

Si la lección no es entregada en la [fecha acordada], el editor intentará contactar con el autor o autores de la lección. Si no recibe noticias, el ticket se cerrará. Éste podrá abrirse en el futuro a petición del autor o autores.

El principal contacto para esta lección es [nombre del editor]. Si se produce algún problema, el autor puede contactar con nuestra ’ombudsperson' (Silvia Gutiérrez de la Torre - http://programminghistorian.org/es/equipo-de-proyecto).

```

### Peer review process

#### Original lesson

```yaml
---
name: ES - Proceso de revisión por pares - Lección original
about: Iniciar el proceso de revisión por pares para una lección original
title: Revisión de la lección [TÍTULO DE LA LECCIÓN]
labels: 2. Initial edit, Spanish
assignees: 

---

*The Programming Historian en español* ha recibido la siguiente propuesta de lección [TÍTULO DE LA LECCIÓN] por parte de [NOMBRE DE USUARIO GITHUB]. Esta lección se encuentra en estos momentos en fase de revisión y puede leerse en:

### Texto
https://github.com/programminghistorian/ph-submissions/tree/gh-pages/es/traducciones/URL-a-la-traducción

### Imágenes
[Link a las imágenes, si es necesario]

Por favor, utiliza los números de línea proporcionados en la vista previa, si eso ayuda a señalar mejor tus comentarios. Pero puedes estructurar tu revisión como mejor te parezca.

En adelante, intervendré como editor durante el proceso de revisión. Tras haber leído la lección y haber enviado mis comentarios al traductor, mi rol consistirá en solicitar otra revisión por parte de uno de los miembros de nuestro comité editorial y gestionar las conversaciones que se produzcan en este foro. 

Otros miembros de nuestra comunidad también están invitados a ofrecer sus comentarios de una manera constructiva; los comentarios deberán publicarse en este hilo de conversación, por lo que se recomienda haber leído nuestra guía para revisores (http://programminghistorian.org/es/guia-para-revisores) y tener en cuenta nuestra política contra el acoso (ver más abajo). No se aceptarán más comentarios por parte de la comunidad tras la publicación de la segunda revisión formal a fin de que el traductor pueda empezar a trabajar en los cambios solicitados. Cuando esto ocurra, publicaré un anuncio aquí.

Asimismo, me comprometo a mantener la conversación abierta a todo el mundo en GitHub. Pero si alguno de los participantes quiere ponerse en contacto en privado conmigo, puede escribirme un correo electrónico. También es posible contactar con nuestros 'ombudpersons'.

## Política contra el acoso

Esta es una declaración de los principios de *Programming Historian en español* y establece las expectativas para el tono y el estilo de toda la correspondencia entre los revisores, autores, editores y colaboradores de nuestros foros públicos.

>El objetivo de *The Programming Historian en español* es ofrecer un entorno abierto en el que la comunidad de participantes sean libres para analizar ideas, realizar preguntas, sugerir cambios, y pedir aclaraciones; también queremos que sea un espacio libre de acoso y hostigamento para todo el mundo con independencia de su género, identidad, orientación sexual, diversidad funcional, apariencia física, tamaño corporal, raza, edad, religión o conocimientos informáticos. No se tolerará ningún tipo de acoso o ataque *ad hominem*. Los participantes que violen esta regla podrán ser expulsados del proceso editorial a discreción del equipo editorial. Si presencias o sientes que has sido víctima de algún tipo de acoso, por favor, contacta con nuestra 'ombudsperson' (Silvia Gutiérrez de la Torre - http://programminghistorian.org/es/equipo-de-proyecto).

```

#### Translation

```yaml
---
name: ES - Proceso de revisión por pares - Traducción
about: Iniciar el proceso de revisión por pares para una traducción
title: Revisión de la traducción [TÍTULO DE LA LECCIÓN]
labels: 2. Initial edit, Spanish, Translation
assignees:

---

*The Programming Historian en español* ha recibido la siguiente propuesta de traducción [TÍTULO DE LA TRADUCCIÓN] de la lección [TÍTULO DE LA LECCIÓN] por parte de [NOMBRE DE USUARIO GITHUB DEL TRADUCTOR]. Esta traducción se encuentra en estos momentos en fase de revisión y puede leerse en:

### Texto
https://github.com/programminghistorian/ph-submissions/tree/gh-pages/es/traducciones/URL-a-la-traducción.md

### Imágenes
[link a la carpeta que contiene las imágenes si han sido adaptadas]

Por favor, utiliza los números de línea proporcionados en la vista previa, si eso ayuda a señalar mejor tus comentarios. Pero puedes estructurar tu revisión como mejor te parezca.

En adelante, intervendré como editor durante el proceso de revisión. Tras haber leído la lección y haber enviado mis comentarios al traductor, mi rol consistirá en solicitar otra revisión por parte de uno de los miembros de nuestro comité editorial y gestionar las conversaciones que se produzcan en este foro. 

Otros miembros de nuestra comunidad también están invitados a ofrecer sus comentarios de una manera constructiva; los comentarios deberán publicarse en este hilo de conversación, por lo que se recomienda haber leído nuestra [guía para revisores](http://programminghistorian.org/es/guia-para-revisores) y tener en cuenta nuestra política contra el acoso (ver más abajo). No se aceptarán más comentarios por parte de la comunidad tras la publicación de la segunda revisión formal a fin de que el traductor pueda empezar a trabajar en los cambios solicitados. Cuando esto ocurra, publicaré un anuncio aquí.

Asimismo, me comprometo a mantener la conversación abierta a todo el mundo en GitHub. Pero si alguno de los participantes quiere ponerse en contacto en privado conmigo, puede escribirme un correo electrónico. También es posible contactar con nuestros *ombudpersons*.

## Política contra el acoso

Esta es una declaración de los principios de *Programming Historian en español* y establece las expectativas para el tono y el estilo de toda la correspondencia entre los revisores, autores, editores y colaboradores de nuestros foros públicos.

>El objetivo de *The Programming Historian en español* es ofrecer un entorno abierto en el que la comunidad de participantes sean libres para analizar ideas, realizar preguntas, sugerir cambios, y pedir aclaraciones; también queremos que sea un espacio libre de acoso y hostigamento para todo el mundo con independencia de su género, identidad, orientación sexual, diversidad funcional, apariencia física, tamaño corporal, raza, edad, religión o conocimientos informáticos. No se tolerará ningún tipo de acoso o ataque *ad hominem*. Los participantes que violen esta regla podrán ser expulsados del proceso editorial a discreción del equipo editorial. Si presencias o sientes que has sido víctima de algún tipo de acoso, por favor, contacta con nuestros *ombudsperson* [Silvia Gutiérrez De la Torre](http://programminghistorian.org/es/equipo-de-proyecto).
```

## French templates [^1]

### Peer review process

#### Original

```yaml
---
name: FR - Examen par les pairs - Original
about: Gabarit de texte pour le ticket de relecture de leçon originale
title: Proposition de leçon [TITRE DE LA LEÇON]
labels: 2. Initial Edit, French
assignees: 

---

Le Programming Historian en français a reçu la leçon  "[TITRE ORIGINAL]" de [NOM D'UTILISATEUR GITHUB] Cette leçon est maintenant en cours d'évaluation. Une prévisualisation est disponible ici: 

http://programminghistorian.github.io/ph-submissions/fr/lecons/[SLUG-DE-LEÇON]

Vous pouvez utiliser la numérotation des lignes fournie dans l'aperçu pour organiser vos commentaires, si cela vous convient. Toutefois, sentez-vous libre de présenter votre évaluation comme vous le jugez mieux. 

J'assume le rôle de rédacteur|rédactrice en charge du suivi du processus de l'évaluation. Dans ce cadre, je vais solliciter deux relectures auprès de la communauté et coordonnerai les échanges qui auront lieu dans cet espace. J'ai déjà relu de mon côté la leçon et j'ai fait part de mes commentaires à l'auteur(e), auxquels ils ont su réagir. 

Tout membre de la communauté peut faire un retour constructif sur ce fil de commentaires, après avoir pris connaissance de nos consignes aux évaluateurs et évaluatrices (https://programminghistorian.org/fr/consignes-evaluateurs) et accepté notre politique contre le harcèlement (voir ci-dessous). Nous demandons que toutes les relectures cessent après réception de la seconde évaluation formelle, pour que l'auteur(e) puisse travailler sur la révision de son texte. Je l'annoncerai sur ce fil quand cette étape aura été atteinte.

J'essaierai de maintenir la discussion au niveau de Github. Si quelqu'un préfère de discuter de manière privée, merci de m'envoyer un message électronique. Vous avez toujours la possibilité de vous tourner vers notre médiatrice [Hélène Huet](mailto:hhuet@ufl.edu) si vous avez le sentiment qu'une médiation est nécessaire.        

## Politique contre le harcèlement

Vous trouverez ci-dessous les principes du Programming Historian en français qui doivent inspirer les échanges entre évaluateurs et évaluatrices, auteur(e)s, rédacteurs et rédactrices, ainsi que toute personne contribuant à nos forums publics.

Le Programming Historian en français tient à garantir un environnement académique ouvert à la communauté, qui offre la pleine liberté d’explorer minutieusement des idées, poser des questions, faire des suggestions ou demander des clarifications. Il fournit aussi un espace libre de toute discrimination envers les personnes contribuant au projet indépendamment du genre, de l’orientation sexuelle, des situations d’handicap, de l’apparence physique, de la masse corporelle, de l’origine, de l’âge, de la religion ou de l’expérience technique. Nous ne tolérons aucune forme d’harcèlement ou d’attaque personnelle contre les membres de la communauté. Les personnes qui violent ces règles sont susceptibles d’être expulsées de la communauté à la discrétion du conseil éditorial. Toute personne en mesure de témoigner de tels comportements ou qui en est la victime peut contacter notre dispositif de médiation ([Hélène Huet](mailto:hhuet@ufl.edu)). Merci de nous aider à créer un espace d’échange et de discussion sûr.  

```

#### Translation

```yaml
---
name: FR - Examen par les pairs - Traduction
about: Gabarit de texte pour le ticket de relecture de traduction
title: Proposition de traduction [TITRE DE LA LEÇON]
labels: 2. Initial Edit, French, Translation
assignees: 

---

Le Programming Historian en français a reçu la traduction du tutoriel "[TITRE ORIGINAL]" de [NOM D'UTILISATEUR GITHUB] sous le titre [TITRE TRADUIT] préparée par les soins de [NOM D'UTILISATEUR GITHUB]. Cettre traduction est en cours de relecture et elle est accessible en suivant ce lien:   

http://programminghistorian.github.io/ph-submissions/fr/traduction/[SLUG-DE-LEÇON]

Vous pouvez utiliser la numérotation des lignes fournie dans l'aperçu pour insérer vos commentaires, si cela vous convient. Toutefois, sentez-vous libre de présenter votre relecture comme vous le jugez mieux. 

J'assume le rôle de rédactrice en charge du suivi de la procédure de relecture. Dans ce cadre, je vais solliciter deux relectures auprès de la communauté et coordonnerai les échanges qui auront lieu dans cet espace. J'ai déjà relu de mon côté la traduction et j'ai fait part de mes commentaires à la personne qui l'a préparée, auxquels elle a su réagir. 

Tout membre de la communauté peut faire un retour constructif sur ce fil de commentaires, après avoir pris connaissance de nos [consignes aux évaluateurs et évaluatrices](https://programminghistorian.org/fr/consignes-evaluateurs) et accepté notre politique contre le harcèlement (voir ci-dessous). Nous demandons que toutes les relectures cessent après réception de la seconde évaluation formelle, pour que l'auteur(e) puisse travailler sur la révision de son texte. Je l'annoncerai sur ce fil quand cette étape aura été atteinte.

J'essaierai de maintenir la discussion au niveau de Github. Si quelqu'un préfère de discuter de manière privée, merci de m'envoyer un message électronique. Vous avez toujours la possibilité de vous tourner vers notre médiatrice [Hélène Huet](mailto:hhuet@ufl.edu) si vous avez le sentiment qu'une médiation est nécessaire.        

## Politique contre le harcèlement

Vous trouverez ci-dessous les principes du Programming Historian en français qui doivent inspirer les échanges entre évaluateurs et évaluatrices, auteur(e)s, rédacteurs et rédactrices, ainsi que toute personne contribuant à nos forums publics.

Le Programming Historian en français tient à garantir un environnement académique ouvert à la communauté, qui offre la pleine liberté d’explorer minutieusement des idées, poser des questions, faire des suggestions ou demander des clarifications. Il fournit aussi un espace libre de toute discrimination envers les personnes contribuant au projet indépendamment du genre, de l’orientation sexuelle, des situations d’handicap, de l’apparence physique, de la masse corporelle, de l’origine, de l’âge, de la religion ou de l’expérience technique. Nous ne tolérons aucune forme d’harcélement ou d’attaque personnelle contre les membres de la communauté. Les personnes qui violent ces règles sont susceptibles d’être expulsées de la communauté à la discrétion du conseil éditorial. Toute personne en mesure de témoigner de tels comportements ou qui en est la victime peut contacter notre médiatrice [Hélène Huet](http://programminghistorian.org/fr/equipe-projet). Merci de nous aider à créer un espace d’échange et de discussion sûr.

```

[1^]: I coudn't find the issue template for new lessons in French. Maybe it's better to simplify the templates and have only the text for peer review.