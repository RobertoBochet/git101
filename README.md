# Slide per Intro GIT

## Informazioni generali

**Autore**: Lorenzo Prosseda *(Lero)*

Queste slide sono state ricavate adattando il template SlidesTemplatePOuL ([gtk-counter](https://gitlab.poul.org/corsi/linuxBase/gtk-counter)); esse hanno un riferimento a un'altra repository per una demo.

Le risorse grafiche sono tutte esportate in PDF, sotto la directory `img/`; questo sia per una migliore organizzazione, sia per evitare problemi con altri formati e il compilatore `pdflatex`.

Per compilare il documento è stato usato `LyX 2.1` e `pdflatex`, per conoscere o modificare le personalizzazioni effettuate, consultare il preambolo LaTeX.

___

## Demo ([gtk-counter](https://gitlab.poul.org/corsi/linuxBase/gtk-counter))
1) Creare un repository locale e aggiungere l'origine remota per condividerlo:
   - git init
   - git add .
   - git commit
   - git remote add *shortname* *url*
   - git push --set-upstream *shortname* *master*


2) Scaricare un repository remoto ed effettuare un commit
   - git clone *url*
   - git pull
   - git commit
   - git push

___

## Extra

A quanto pare nel sito dell'Accademia della Crusca compare il termine repository usato come nome maschile, questo è il motivo per il qule nelle slide ho trattato questo nome come maschile.