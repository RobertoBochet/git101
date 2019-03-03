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

# Git Add

----

## Git Add

Ok, siamo pronti:

- Abbiamo settato le nostre informazioni <!-- .element: class="fragment" -->
- Abbiamo creato i nostri file <!-- .element: class="fragment" -->
- Vogliamo aggiungere i file a git. <!-- .element: class="fragment" -->

----

## Git Add

Per aggiungere i file, ci basta usare `git add`

```bash
$ git add nome_file

```

----

## Git Add

Se vogliamo aggiungere solo una parte dei file modificati (e.g alcune linee, un blocco di codice, ecc) possiamo usiare:

```bash
$ git add --patch nome_file

```

---

# Git Commit

----

## Git commit

Abbiamo aggiunto i nostri file a git.

Abbiamo finito? <!-- .element: class="fragment" -->

No! <!-- .element: class="fragment" -->

----

## Git commit

Per salvarne effettivamente lo stato su git dobbiamo eseguire un'operazione chiamata **commit**

`git add` dice a git solo di tener traccia di quel file o di quelle modiche 

----

## Git commit

Per farlo ci basta eseguire:

```bash
$ git commit
```

Questa operazione ci chiederà anche un commento per dare maggiori informazioni sulle nostre modifiche. <!-- .element: class="fragment" -->

----

## Git commit

Questo commento può essere anche passato da cli:

```bash
$ git commit -m "Questo è il mio commento"

```

Una buona pratica è avere dei messaggi brevi e significativi <!-- .element: class="fragment" -->

---

Perché abbiamo dovuto usare **due** comandi per aggiungere i file a git?

Dove aggiunge i file  `git add` se non al repository git?

---

# Staging Area

----

## Staging Area

Quando esguiamo `git add` i file vengo "mossi" dalla nostra area di lavor ad una **Staging Area**.

Qui, le modifiche, sono pronte per essere salvate ma non lo sono ancora. <!-- .element: class="fragment" -->

----

## Staging Area

In realtà un file può essere in 4 stati per git:

- **Untracked**: Git sa che esiste ma non sa cosa farci 
- **Modified**: Git sa che esiste e sa che è stato modificato, ma non sa che farci 
- **Unmodified**: Git sa che esiste e che non ha subito modifiche 
- **Staged**: Git sa che esiste e che è stato modificato e sa che verrà aggiunto a breve 

----

## Uno schema per visualizzare il tutto

![File Status](https://git-scm.com/book/en/v2/images/lifecycle.png) 

---

Come faccio a sapere in che stato sono i miei file allora?

---

# Git status

----

## Git status

Il comando `git status` ci permette di sapere in che stato siamo e in che stato sono i nostri file

----

## Git status

Un esempio:

```bash
$ git status

Sul branch master
File non tracciati:
  (usa "git add <file>..." per includere l'elemento fra quelli di cui verrà eseguito il commit)

	content.md

non è stato aggiunto nulla al commit ma sono presenti file non tracciati (usa "git add" per tracciarli)
```

---

## Cosa sappiamo ora?

- Ora sappiamo dove siamo e cosa dovremmo andare a fare. <!-- .element: class="fragment" -->
- Coma facciamo a sapere cosa è stato già fatto?  <!-- .element: class="fragment" -->

---

# Git log

----

## Git log

Eseguendo `git log` possiamo vedere la lista dei commit salvati in precedenza:


```bash
$ git log -1 # -1 ci permette di vedere solo l'ultimo commit

commit 28a648a2a12b7dc8f24ea99aa5a41d290cd332a2 (HEAD -> master)
Author: Il mio nome <mia@email.com>
Date:   Thu Oct 25 12:19:29 2018 +0200

	Questo è il mio commento
```

----

## Git Log

Le informazioni che abbiamo sono:

- Il **messaggio** con cui è stato creato il commit
- La **data** di creazione del commit
- L'**identità** di chi ha creato il commit
- L'**hash** (sha1) identificativo del commit

----

## Git log

La hisotry, in realtà, può essere vista in maniera grafica con:

```bash

$ git log --graph

```

Questo ci andrà a mostrare i commit in formato grafico, con eventuali diramazioni rispetto all'albero principale.

---

## Albero?

Git gestice le modifiche con una struttura ad albero in cui i vari nodi sono i commit (snapshot delle modifiche).

Posso avere delle diramazioni come negli alberi?  <!-- .element: class="fragment" -->

---

# I Branch

----

## I Branch

I **branch** sono diramazioni nel nostro albero delle modifiche.

Queste diramazioni potranno essere unite (merge) a quella principale in futuro.

----

## I Branch

Git ha, di default, ha il branch principale chiamato `master`

----

## I Branch

Per creare un branch:

```bash
$ git branch nuovo_branch
```

Per eliminare un branch:

```bash
$ git branch -D nuovo_branch
```

---

# Ok, ed ora?

Come faccio a muovermi all'interno di questo albero e dei suoi branch?

---

# Git Checkout

----

## Git checkout

Per muoverci tra un branch e l'altro possiamo usare:

```bash
$ git checkout nuovo_branch
Si è passati al branch 'nuovo_branch'
```

----

## Git checkout

Possiamo usarlo anche per muoverci all'interno della history:

```bash
$ git checkout <sha_hash>
```

----

## Git checkout

Se eseguiamo ora `git log` vediamo che la dicitura di fianco al commit è cambiata.

```bash
$ git log -1 

commit 28a648a2a12b7dc8f24ea99aa5a41d290cd332a2 (HEAD -> nuovo_branch, master)
Author: Il mio nome <mia@email.com>
Date:   Thu Oct 25 12:19:29 2018 +0200

	Questo è il mio commento
```

---

Cosa vuol dire quel `HEAD -> nuovo_branch`?

---

# HEAD

----

## HEAD

La **HEAD** è un segnaposto che indica a git (e a noi) su quale commit ci troviamo.

Quando la **HEAD** punta ad un commit non assiociato con il nome del branch si è nello stato di **detached HEAD** 

---

# TL;DR

- `git add` per tracciare un file
- `git commit` per salvarne lo stato
- **HEAD** puntatore all'ultimo commit
- **branch** ramo delle modifiche
- **master** nostro branch principale

---

# Demo!


