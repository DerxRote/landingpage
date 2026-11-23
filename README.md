# pfleger.work

Startseite für https://pfleger.work: kurzer Text zu den Hobbyprojekten und Kacheln zu den einzelnen Apps (z. B. [Darts Counter](https://darts.pfleger.work), Code in [DartsDerRote](https://github.com/DerxRote/DartsDerRote)). Läuft als kleiner Cloudflare Worker mit statischen Dateien. Keine Cookies, kein Tracking, kein JavaScript im Browser, Schriften lokal.

| Pfad | Zweck |
|---|---|
| `public/index.html` | Startseite. Neue Kachel: den markierten `<a class="tile">`-Block kopieren und Adresse, Bild, Titel, Text anpassen. Bild nach `public/icons/`. |
| `public/impressum.html`, `public/datenschutz.html` | Rechtstexte. Bei neuen Projekten, die Daten verarbeiten, Datenschutz prüfen. |
| `public/css/style.css` | Aussehen (hell/dunkel, grüner Akzent wie beim Darts Counter) |
| `public/fonts/` | Schriften Inter und Barlow Condensed, lokal ausgeliefert |
| `src/worker.js` | Leitet `www.pfleger.work` auf `pfleger.work` um |
| `wrangler.jsonc` | Cloudflare-Einstellungen, Domains `pfleger.work` und `www.pfleger.work` |

## Cloudflare einrichten (einmalig)

Workers & Pages → Create application → Import a repository → `landingpage`. Name `pfleger-work`, Build-Befehl leer, Deploy-Befehl `npx wrangler deploy`. Die Domains richtet `wrangler.jsonc` beim Deploy selbst ein. Gibt es für `pfleger.work` oder `www` schon einen DNS-Eintrag, muss der vorher gelöscht werden.

Lokal ansehen: `npm install`, dann `npx wrangler dev`.
