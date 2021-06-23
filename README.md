# it-4-kids.github.io
Webseite für http://it4kids.info/


## Einrichtung Jekyll

Wir verwenden aktuell die Version Jekyll 4.2.0.

Jekyll kann nativ installiert oder über Docker gestartet werden.

### Nativ

Je nach Betriebssystem muss man die entsprechend Anleitung auswählen:

https://jekyllrb.com/docs/installation/

### Docker

https://github.com/envygeeks/jekyll-docker/blob/master/README.md

#### Performance: bundle Verzeichnis mounten

    docker run --rm --volume="$PWD:/srv/jekyll" --volume="$PWD/vendor/bundle:/usr/local/bundle" -p 4000:4000 -it jekyll/jekyll:3.8 jekyll serve --force_polling

#### Polling aktivieren

ggf. jekyll serve --force_polling verwenden, wenn es Probleme beim Nachladen von Änderungen gibt

#### Docker auf Windows (Powershell)

Befehl zur Ausführung im Verzeichnis des Repos

    docker run --rm `
      --volume="${pwd}:/srv/jekyll" `
      --volume="${pwd}/vendor/bundle:/usr/local/bundle" `
      -p 4000:4000 `
      -it jekyll/jekyll:4.2.0 `
      jekyll serve --force_polling
