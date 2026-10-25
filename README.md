# dvk-website-github-pages

Website des Dartverein Kaiserslautern e.V. – https://www.dartverein-kaiserslautern.de/

Statische Jekyll-Seite, gehostet über GitHub Pages (Deploy aus Branch `main`, Ordner `/`).

## Inhalte pflegen

| Was | Wo |
|---|---|
| Texte der Seiten | `*.md` / `*.html` im Repo-Root (`verein.md`, `liga.md`, …) |
| Menü | `_data/navigation.yml` |
| Downloads | Datei nach `dokumente/<ordner>/` legen und Eintrag in `_data/downloads.yml` ergänzen |
| Archiv | Dateien nach `archiv/dateien/…` legen und Eintrag in `_data/archiv.yml` ergänzen |
| Bilder | `assets/img/` |
| Link zum Ligabetrieb, Kontakt-Mail | `_config.yml` (`liga_url`, `kontakt_mail`) |

Dateinamen bitte ohne Leerzeichen und Umlaute (z. B. `2026-03-18-protokoll-delegiertensitzung.pdf`).
Einzelne Dateien dürfen max. 100 MB groß sein.

## Lokale Vorschau

Voraussetzung: Ruby (Windows: RubyInstaller mit DevKit).

```sh
bundle install
bundle exec jekyll serve
```

Danach http://localhost:4000 öffnen.

## Umzug der Domain

1. Repo → Settings → Pages: Source „Deploy from a branch“, `main` / `/ (root)`.
2. Seite unter `https://<user>.github.io/dvk-website-github-pages/` prüfen.
3. Account → Settings → Pages: Domain `dartverein-kaiserslautern.de` verifizieren (TXT-Record).
4. Beim Domain-Anbieter DNS setzen (MX-Records für E-Mail **nicht** ändern):
   - `www` → CNAME `<user>.github.io`
   - `@` → A-Records `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
5. Repo → Settings → Pages: Custom domain `www.dartverein-kaiserslautern.de` eintragen, „Enforce HTTPS“ aktivieren.
6. Alte Hosting-Seite erst kündigen, wenn die neue Seite unter HTTPS erreichbar ist.
