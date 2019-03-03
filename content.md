# Introduzione a GIT


---


## Di cosa parleremo oggi:

 - Cosa è Git? <!-- .element: class="fragment" -->
 - Perché mi serve? <!-- .element: class="fragment" -->
 - Da dove inizio ad usare Git? <!-- .element: class="fragment" -->
 - Demo! <!-- .element: class="fragment" -->

---

# Cosa è Git?

![XKCD GIT](https://imgs.xkcd.com/comics/git.png) 


----

## Cosa è Git?

Un Sistema di Versionamento del Codice Distribuito (DVCS):

- Ogni sviluppatore ha l'intera history del progetto in locale <!-- .element: class="fragment" -->
- E' possibile creare delle "istantanee" dello stato dei file <!-- .element: class="fragment" -->
- E' possibile avere delle modifiche locali senza pubblicarle <!-- .element: class="fragment" -->

---

## Perché mi serve?

- A volte fare CTRL+Z non basta <!-- .element: class="fragment" -->
- Voglio collaborare assieme ad altre persone per scrivere il mio codice <!-- .element: class="fragment" -->
- Voglio avere una history, visibile e navigabile, delle modifiche eseguite <!-- .element: class="fragment" -->

---

# Come installarlo?

[Guida da git-scm](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) 

----

# N.B.

Tutti gli esempi verrranno fatti da shell su sistema GNU/Linux

---

# Pronti? Ok, iniziamo!

![In and out git](https://media.giphy.com/media/8gWrk3QZrjF1C/giphy.gif ) 

---

# Git Init

----

## Git init

Creiamo il nostro repository git

```bash
$ mkdir git_project
$ cd git_project
$ git init .

```

----

## Git Init

`git init` è il comando per dire a git che dovrà gestire tutti i file al di sotto di quella directory.

----

## Git Init

`git init` andrà a creare la directory `.git` contenente:

```bash
$ tree .git/
.git/
├── config
├── description
├── HEAD
├── hooks
├── info
├── objects
└── refs

```

----

## Gitignore

Non è detto che vogliamo che vengano gestiti **tutti** i file all'interno di un repository.

----

## Gitignore

Per far questo ci basta definire un file `.gitignore` e specifiare, anche tramite espressioni regolari, quali file "nascondere" a git.

----

## Gitignore

Un esempio:

```bash
$ cat .gitignore
# Tutti i file che finiscono per .log
*.log
# Tutti i file che si chiamano test[numero].c
test[0-9].c
# Non i file che si chiamano test10.c
!test10.c
```

---

## Git config

Per dire a git con quali informazioni registrare le nostre modifiche dobbiamo usare `git config`

----

## Git config

Aggiungiamo la nostra email:

```bash
$ git config --local user.email "mia@email.com"
```

Aggiungiamo il nostro nome

```bash
$ git config --local user.name "Il Mio Nome"
```

---
