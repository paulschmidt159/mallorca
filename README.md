# 🌴 Mallorca 2026

Kleine Urlaubs-Seite für unseren Trip nach Cala Pi: Live-Countdown, wer wann landet,
die Crew, die Hausregeln und eine Packliste zum Abhaken.

**Live:** https://paulschmidt159.github.io/mallorca/

## Was wo geändert wird

Alles steckt in einer einzigen Datei: [`index.html`](index.html).

| Was | Wo |
| --- | --- |
| Landezeiten & Namen | `const PEOPLE = [...]` ganz unten im `<script>` |
| Packliste | `const PACKLISTE = [...]` direkt darunter |
| Farben der Personen | `--c-name` Variablen oben im `:root` |
| Crew-Sprüche & Missionen | Abschnitt `<!-- CREW -->` im HTML |
| Hausregeln | Abschnitt `<!-- REGELN -->` im HTML |
| Portraits | `img/<name>.webp` |

### Portraits austauschen

Die Bilder liegen als quadratische WebP mit 320 × 320 px in `img/`, damit die
Seite auf dem Handy schnell lädt (jeweils ~25 KB). Neues Bild einfach unter
gleichem Namen ablegen – am besten vorher quadratisch aufs Gesicht zuschneiden.

### Landezeiten

```js
{ name:"Paul", color:"c-paul", target:"2026-09-01T18:10:00+02:00", meta:"landet Di, 18:10 Uhr" }
```

`target` ist die Landezeit in Mallorca-Zeit (`+02:00` = Sommerzeit).
Optional geht noch `arrivedMsg:"..."` für einen eigenen Text nach der Landung.

Ist die Zeit erreicht, wird die Person automatisch als „gelandet“ markiert.
Sind alle da, erscheint stattdessen der Gute-Laune-Banner.

## Deployen

Push auf `main` reicht – GitHub Pages baut automatisch neu (dauert ~1 Minute).

```bash
git add -A && git commit -m "Update Landezeiten" && git push
```
