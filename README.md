# sanitaer-heizungstechnik-ahrens.de

Neuauflage der Webseite für **Thorsten Ahrens Sanitär- und Heizungstechnik**, Meisterbetrieb aus Kisdorf.

---

## Prototyp live ansehen

### → **<https://tilloh-dev.github.io/sanitaer-heizungstechnik-ahrens.de/>**

Der aktuelle Stand ist über GitHub Pages erreichbar und wird bei jedem Push auf `main` automatisch aktualisiert.

---

## Über das Projekt

Modernisierung des bestehenden Online-Auftritts unter <http://www.sanitaer-heizungstechnik-ahrens.de>.
Ziel ist eine zeitgemäße, mobile-freundliche Single-Page-Website, die alle Inhalte der alten Seite übernimmt und in einer ruhigen, bodenständigen Tonalität präsentiert.

### Inhalte

- Hero mit Einführung und Kennzahlen
- Über uns inkl. Team
- Leistungen: Sanitär · Heizung · Lüftung · Solar
- Projekt-Galerie mit Lightbox und Vorher/Nachher-Vergleich
- Kontakt mit Karte (OpenStreetMap)
- Impressum & Datenschutz nach DSGVO

### Markenzeichen

Der Frosch ist als ruhiges, wiederkehrendes Element im Logo (Navbar & Footer) sowie als dezente Maskottchen-Illustration im Hero eingebunden. Außerdem dient er als Favicon in mehreren Auflösungen.

## Technik

- Statische Single-Page-Site: **HTML**, **CSS** (Custom Properties, kein Framework), **Vanilla JS**
- Schriften via Google Fonts (Inter, Playfair Display)
- Karten-Embed über OpenStreetMap
- Hosting: **GitHub Pages** (Branch `main`)

Keine Build-Schritte – die `index.html` ist direkt lauffähig. Einzige Dev-Abhängigkeit ist `html-validate` für `pnpm lint`.

## Lokale Vorschau

```bash
# einfach im Browser öffnen
xdg-open index.html

# oder mit lokalem Webserver (empfohlen für relative Pfade)
python3 -m http.server 8080
# → http://localhost:8080
```

## Struktur

```
.
├── index.html                 # komplette Seite (HTML/CSS/JS inline)
├── static/
│   └── images/
│       ├── favicon.png        # freigestellte Favicons (32/64/180 px)
│       ├── Frosch-Logo.png    # transparentes Markenzeichen
│       ├── gallery/           # Projektbilder
│       ├── profile/           # Teamfotos
│       └── services/          # Leistungs-Header
└── README.md
```

## Kontakt (Betrieb)

**Thorsten Ahrens Sanitär- und Heizungstechnik**
Ton Hogenbargen 45 · 24629 Kisdorf
Telefon: [04193 968674](tel:04193968674)
E-Mail: <ahrens.sanheitec@t-online.de>
