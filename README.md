Build scripts: Verwendung von npm als Build-Tool

- Das HTML/CSS Sass Bootstrap Boilerplate und wie man dependencies verwendet
- Untersuchung von package.json und Dependencies
- Dependencies installieren: `npm install`

Schreiben wir Scripts in package.json

- Laufen für die Entwicklung: `npm start`
- Aufbau für Veröffentlichung: `npm run build`

Dependencies (Abhängigkeiten)

- Befehl: `npm install packageName --save`

- boostrap

Development Dependencies

- Befehl: `npm install packageName --save-dev`

- @parcel/transformer-sass --> npm run start
- gh-pages --> npm run deploy
- parcel --> npm run build

## Reihenfolge:

1. Projekt Ordner erstellen
2. index.html erstellen und verlinken wir unsere style.scss Datei mit link
3. cd in den Projekt Ordner --> `npm init`

- Gib die nötige Infos hinein: Name, Beschreibung, Autor, usw

4. dependencies installieren

- normal dependencies
- dev dependencies

5. Erstelle eine src Ordner mit den folgenden uneteren Teilen:

```
- > src
  - > styles
    - style.scss
  - index.html
```

6. scripts in der package.json Datei geschrieben

Hinweis: mit verschiedenen Packages braucht man vielleicht verschiede Befehle in den Scripts

aber insofern brauchen wir nur:

```
"scripts": {
"start": "rm -rf dev-serve && parcel src/index.html --dist-dir dev-serve",
"build": "rm -rf build && parcel build src/index.html --dist-dir build --public-url ./",
"publish": "gh-pages -d build"
}
```

- bitte darauf achten was für Pfaden ihr habt
- src/index.html oder direkt eine index.html im Hauptordner? --> es kommt darauf an, wie man seine Struktur im Ordner zugeordnet hat

7. Live Anzeige --> dank der Packages können wir jetzt unsere Befehle verwenden, um unsere Webseite Live anzuzeigen

- `npm run start`

8. Ein Build von unserer Seite erstellen

- `npm run build`
