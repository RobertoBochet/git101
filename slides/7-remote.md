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

![gitlab-logo](images/gitlab-logo-white-rgb.svg) <!-- .element: class="fragment" style="width: 300px;" -->

----

## Remote

### Possibile topologia con hosting

![topology_with_hosting](images/topology_hosting.svg) <!-- .element: style="width: 400px;" -->

----

## Remote

### Come "sincronizzo" due repository?

Prima di procedere al passaggio di dati tra repository é necessario dire a git come puó raggiungere il repository remoto

----

## Remote

### Come si aggiunge un repository remoto?


```bash
git remote add origin https://gitlab.org/path/repository.git
```
<!-- .element: class="fragment" -->

<p>Abbiamo cosi creato un riferimento ad un repository remoto che abbiamo soprannominato *origin*</p> <!-- .element: class="fragment" -->

<small>N.B. git per scambiare informazioni tra repository supporta sia *https* che *ssh*</small> <!-- .element: class="fragment" -->

----

## Remote

### Come posso vedere i repository remoti che ho aggiunto?

```bash
git remote -v
```
<!-- .element: class="fragment" -->

```shell
origin  https://gitlab.org/path/repository.git (fetch)
origin  https://gitlab.org/path/repository.git (push)
```
<!-- .element: class="fragment" -->