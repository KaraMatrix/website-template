# KaraMatrix Kundenseiten-Template

Wiederverwendbares Jekyll-Template für statische Kundenwebsites (200–500 €),
gehostet auf GitHub Pages. Optionales Add-on: CMS-Anbindung über
[pagescms.org](https://pagescms.org) (ab 249 €) und Blog (ab 149 €).

## Neuen Kunden aus diesem Template anlegen

1. **Repo erstellen:** Auf GitHub „Use this template" (oder Ordner in ein neues
   Repo kopieren, `git init`, push nach `github.com/<account>/<kunde>`).
2. **GitHub Pages aktivieren:** Repo → Settings → Pages → Source: `main` /
   `(root)`. Nach ein paar Minuten ist die Seite unter
   `https://<account>.github.io/<kunde>/` live.
3. **Inhalte anpassen:**
   - `_data/settings.yml` — Firmenname, Kontakt, Öffnungszeiten, Leistungen,
     Primärfarbe, Über-uns-Text.
   - `_data/navigation.yml` — Haupt-Navigation (Reihenfolge über `nav_order`).
   - `_pages/impressum.md`, `_pages/datenschutz.md` — Platzhalter durch echte
     Rechtstexte ersetzen (siehe eckige Klammern `[Platzhalter: …]`).
   - `_posts/2026-01-15-…md` — Beispiel-Blogpost vor dem Livegang löschen
     oder durch einen echten Beitrag ersetzen.
4. **Farbe setzen:** `farbe_primaer` in `settings.yml` als Hex-Code — steuert
   automatisch Buttons, Links und Akzente über die ganze Seite.

## CMS-Add-on verbinden (pagescms.org)

1. Auf [pagescms.org](https://pagescms.org) mit GitHub einloggen, das
   Kunden-Repo auswählen. `.pages.yml` ist bereits vorkonfiguriert
   (Webseiten-Einstellungen, Navigation, Unterseiten, Blog).
2. **Collaborator einladen:** GitHub-Repo → Settings → Collaborators →
   Kunden-E-Mail einladen (Rolle: Write reicht, kein Admin nötig).
   Der Kunde bekommt eine E-Mail, akzeptiert die Einladung und kann sich
   danach auf pagescms.org per Magic-Link/GitHub-Login anmelden und im
   CMS-Formular editieren — kein direkter Repo-/Code-Zugriff nötig.
3. Jede Änderung im CMS erzeugt automatisch einen Commit im Repo; GitHub
   Pages baut die Seite danach selbst neu (kein manueller Deploy-Schritt).

## Neue Unterseite anlegen (ohne CMS)

Markdown-Datei in `_pages/` anlegen mit Front Matter:

```yaml
---
title: Beispieltitel
nav_label: Kurzform für die Navigation
nav_order: 50
nav_location: header   # oder footer
published: true
---
Inhalt der Seite …
```

## Lokal testen

```bash
bundle install
bundle exec jekyll serve
```

## Blog (Add-on)

Neue Datei in `_posts/` als `YYYY-MM-DD-titel.md` mit Front Matter
`title` und `date`. Die Übersichtsseite `/aktuelles/` erscheint automatisch
in der Navigation, sobald mindestens ein Beitrag existiert.

**Hinweis SEO:** Die Meta-Description/JSON-LD kommt aus `_config.yml` (`description:`) und wird EINMALIG beim Kunden-Setup gesetzt — CMS-Änderungen am Slogan ändern nur die sichtbare Seite, nicht das Google-Snippet. Beim Setup beide konsistent setzen.
