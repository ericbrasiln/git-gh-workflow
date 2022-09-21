# Sugestão - jekyll: Issue Template

O modelo foi atualizado pela última vez em 2016 (Latest commit [4a8ad0f](https://github.com/programminghistorian/jekyll/commit/4a8ad0f3c4069221c5ea9af18ce36345588a9669) on 27 Jun 2016) e sua sintaxe está fora do padrão atual do GH.

O .md atual está assim:

```
If you are reporting a problem with a lesson, please try to provide us with the following information:  

- The full title of the lesson
- The system you are using (Mac, Linux, Windows)
- Version numbers of the relevant software you are using
- The exact steps you took that caused the problem  

If you'd like, you can delete this template text before posting your issue.
```

Minha sugestão de atualização:

```
---
name: Basic Template
about: Simple issue template
title: Name your issue
---

## If you are reporting a problem with a lesson, please try to provide us with the following information:  

- [ ] The full title of the lesson
- [ ] The system you are using (Mac, Linux, Windows)
- [ ] Version numbers of the relevant software you are using
- [ ] The exact steps you took that caused the problem.

## If you are reporting a technical problem in the Programming Historian site or in the repository, please try to provide us with the following information:

- [ ] Link and page title
- [ ] A brief description of the problem
- [ ] Expected behavior
- [ ] Proposed solution (if any)

*If you'd like, you can delete this template text before posting your issue.*
```