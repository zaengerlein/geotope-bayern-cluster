# Geotop Cluster Bayern

Statische GitHub-Pages-Seite zur Clusterung von **Bayerns schönsten Geotopen** auf Basis der Datei `bsg_koordinaten.xlsx`.

## Inhalt

- `index.html` – Hauptseite
- `data/geotope.json` – importierte Datengrundlage für die Weboberfläche

## Lokal testen

Da die Seite Daten per `fetch('./data/geotope.json')` lädt, sollte sie über einen lokalen Webserver geöffnet werden.

### Mit Python

```bash
python3 -m http.server 8000
```

Dann im Browser öffnen:

```text
http://localhost:8000
```

## Auf GitHub Pages veröffentlichen

### Variante A – neues Repository im Root veröffentlichen

1. Neues Repository bei GitHub anlegen, z. B. `geotope-cluster-bayern`
2. Diese Dateien in das Repository kopieren:
   - `index.html`
   - Ordner `data/`
3. Commit und Push ausführen:

```bash
git init
git add .
git commit -m "Initial GitHub Pages version"
git branch -M main
git remote add origin https://github.com/DEIN-USERNAME/geotope-cluster-bayern.git
git push -u origin main
```

4. In GitHub öffnen: `Settings` → `Pages`
5. Unter **Build and deployment** wählen:
   - **Source**: `Deploy from a branch`
   - **Branch**: `main`
   - **Folder**: `/ (root)`
6. Speichern
7. Nach kurzer Zeit ist die Seite erreichbar unter:

```text
https://DEIN-USERNAME.github.io/geotope-cluster-bayern/
```

### Variante B – bestehendes Repository mit `/docs`

Wenn du die Seite in ein vorhandenes Repository legen willst:

1. Lege die Dateien in den Ordner `docs/`
2. Aktiviere in GitHub Pages als Quelle:
   - Branch `main`
   - Folder `/docs`

Dann lautet die URL typischerweise:

```text
https://DEIN-USERNAME.github.io/REPO-NAME/
```

## Daten aktualisieren

Wenn sich die Clusterung ändert, muss nur `data/geotope.json` ersetzt werden. Das HTML bleibt unverändert, solange die JSON-Struktur gleich bleibt.

## Hinweise

- Die aktuelle Clusterung ist eine erste automatische Zuordnung aus Namen und Kurzbeschreibung.
- Für eine fachlich präzisere Version kann `geotope.json` später um Felder wie `hauptprozess`, `gesteinstyp`, `region` oder `morphologie` erweitert werden.
