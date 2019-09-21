
## Commit

----

## Commit

### Cos'é?

Un *commit* é un istantanea (snapshot) dello stato di un repository in un determinato momento

Un *repository* é quindi un insieme di *commit* in ordine temporale

----

## Commit

### Come posso creare un commit?

Per prima cosa é necessario dire a git quali file includere in questo commit

```bash
$ git add file1.txt file2.json
```

----

## Commit

### Cosa é successo?

Git ha copiato i files nella *stageing area*

```bash
$ git status
```
```shell
On branch master

No commits yet

Changes to be committed:
(use "git rm --cached <file>..." to unstage)
	new file:   file1.txt
	new file:   file2.json
```

Ora i files sono pronti per essere inclusi in un commit

<small>N.B. I files sono stati copiati altrove, se gli modifico ulteriormente<br/> dovró riaggiungerli alla stage area ripetendo il comando *git add*</small>

----

## Commit

### Creiamo il commit

```bash
$ git commit
```

Si aprirá cosi il nostro editor di testo predefinito nel quale dovremo scrivere un breve messagio da associare al *commit* nella prima riga

----

## Commit

### Posso includere il messaggio nella linea di comando?

```bash
$ git commit -m "Questo é il mio primo commit"
```

Con questa sintassi preverremmo l'apertura del editor di testo, fornendo il messaggio via linea di comando

**Attenzione: un messaggio di commit<br/>non dovrebbe superare i 50 caratteri**

----

## Commit

### Cosa é successo?

```bash
$ git log
```
```shell
commit aa581d11d4caed7084cd8114d2454d9380acd869 (HEAD -> master)
Author: Roberto Bochet <robertobochet@gmail.com>
Date:   Sat Aug 31 01:56:49 2019 +0200

Questo é il mio primo commit
```

----

## Commit

### Da cosa é composto un commit?

- I files modificati (ovviamente) <!-- .element: class="fragment" -->
- L'autore del commit <!-- .element: class="fragment" -->
- La data di creazione del commit <!-- .element: class="fragment" -->
- L'hash del commit precedente <!-- .element: class="fragment" -->

Tutti questi elementi concorrono nella creazione della firma (hash) del commit <!-- .element: class="fragment" -->

----

## Commit

### (Altri) punti di forza

Ogni commit contiene l'hash di quello precedente

⇓ <!-- .element: class="fragment" data-fragment-index="2"-->

Modifiche a vecchi commit sono (generalmente) proibite e facilmente individuabili <!-- .element: class="fragment" data-fragment-index="2"-->

