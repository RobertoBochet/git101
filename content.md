## (Alcuni) Casi d'uso

- Tenere traccia delle modifiche a un progetto <!-- .element: class="fragment" -->
- Gestire un progetto a piú mani <!-- .element: class="fragment" -->
- Versionare files di configurazione <!-- .element: class="fragment" -->

----

## Come fare?

![gitlab-logo](/images/git-logo.svg) <!-- .element: class="fragment" style="width: 400px;" -->

---

## Cos'é?

git é un sistema di *controllo versione distribuito* 

---

## Distribuito o centralizzato?

----

## Distribuito o centralizzato?

![topology_with_hosting](/images/distribuited_centralized.svg) <!-- .element: style="width: 800px;" -->

----

## Distribuito o centralizzato?

### Perché usare un sistema distribuito?

- I files non sono fisicamente in un solo luogo <!-- .element: class="fragment" --><br/><small>Rischio perdita dati (quasi) nullo</small> <!-- .element: class="fragment" -->
- I files sono disponibili offline <!-- .element: class="fragment" --><br/><small>posso lavorare anche senza accesso ad internet</small> <!-- .element: class="fragment" -->

----

## Distribuito o centralizzato?

### Criticitá di un sistema distribuito

- Posso lavorare su file non aggiornati... <!-- .element: class="fragment" --><br/><small>Non posso o mi dimentico di "scaricare" gli aggiornamenti dei files</small> <!-- .element: class="fragment" -->
- ...con rischio di creare conflitti <!-- .element: class="fragment" --><br/>**Che vanno gestiti!** <!-- .element: class="fragment" style="color:red;" -->

---

## Repository

----

## Repository

### Cos'é?

É 

----

## Repository

### Creiamone uno

Da terminale portiamoci nella cartella che vogliamo versionare e eseguiamo il comando

```bash
$ git init
```
```shell
Initialized empty Git repository in /path/project/.git/
```

Abbiamo creato il nostro primo repository

<small>N.B. La directory in cui creaiamo il nostro repository non deve essere per forza vuota!</small>

----

## Repository

### Cosa é cambiato?

```bash
$ ls -al
```
```shell
total 0
drwxr-xr-x 1 user users  60 31 ago 01.16 .
drwxr-xr-x 1 user users 460 31 ago 01.16 ..
drwxr-xr-x 1 user users 200 31 ago 01.16 .git
```

Git ha creato una directory denominata `.git` che contiene tutti i dati che necessitá per funzionare

**Compresa tutta la storia del progetto**


---

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

Git ha copiato i files nella *stage area*

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

⥥

Modifiche a vecchi commit sono (generalmente) proibite e facilmente individuabili

---

## Remote

----

## Remote

### Come interagiscono repo su macchine diverse?

Piú repository, presenti su macchine diverse, possono condividere lo stesso progetto. <!-- .element: class="fragment" -->

Git fornisce gli strumenti per mantenere questi repository sincronizzati tra loro. <!-- .element: class="fragment" -->


----

## Remote

### Come posso rendere i miei commit disponibili a tutti?

Anche se possibile, la sincronizzazione diretta tra due personal computer non é generalmente utilizzata <!-- .element: class="fragment" -->

Solitamente si fa affidamento a uno o piú hosting di repositories per fare da nodi comuni tra piú personal computer <!-- .element: class="fragment" -->

![gitlab-logo](/images/gitlab-logo-white-rgb.svg) <!-- .element: class="fragment" style="width: 300px;" -->

----

## Remote

### Possibile topologia con hosting

![topology_with_hosting](/images/topology_hosting.svg) <!-- .element: style="width: 400px;" -->


