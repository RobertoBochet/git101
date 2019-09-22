## Configurarazione

----

## Configurarazione

Git supporta una moltitudine di customizzazioni

<p class="fragment" data-fragment-index="1">Per impostare un parametro</p>

```bash
git config --{scope} {name} {value}
```
<!-- .element: class="fragment" data-fragment-index="1" -->

<p class="fragment" data-fragment-index="2">Per leggere un parametro</p>

```bash
git config [--{scope}] {name} {value}
```
<!-- .element: class="fragment" data-fragment-index="2" -->

<p class="fragment" data-fragment-index="3">Per ottenere tutti i parametri</p>

```bash
git config [--{scope}] --list
```
<!-- .element: class="fragment" data-fragment-index="3" -->

----

<!-- .element: data-section-title="Configurazione" -->

## Configurarazione

### Scope

<p class="fragment">Git permette di definire 3 livelli di gerarchia per le configurazioni</p>

<ul>
    <li class="fragment">*local*: relativo al solo progetto corrente</li>
    <li class="fragment">*global*: relativo al utente che sta eseguento git</li>
    <li class="fragment">*system*: valida per tutti gli utenti del sistema</li>
</ul>

<small class="fragment">N.B. la gerarchia impone che le impostazioni *local* sovrascrivino quelle *global*,<br/> le *global* quelle *system*</small>

----

## Configurarazione

### Configurazione minima

<p class="fragment">Git per funzionare richiede che almeno i parametri *user.name* e *user.email* siano definiti

```bash
git config --global user.name il_mio_nome
```
<!-- .element: class="fragment" -->
```bash
git config --global user.name mia_mail@poul.org
```
<!-- .element: class="fragment" -->

#### Siamo pronti per usare git <!-- .element: class="fragment" -->