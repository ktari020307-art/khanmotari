# khanmotari — Motion Gallery

Eine Sammlung eigenständiger **Motion-Graphics-Studien**. Jedes Stück demonstriert
eine andere Animationstechnik in einem anderen visuellen Stil — komplett in
reinem **HTML, CSS, SVG und Canvas**. Kein Video, keine externen Bibliotheken,
keine Build-Tools.

## Schnellstart

Die Galerie ist eine statische Website. Einfach `index.html` im Browser öffnen:

```bash
# Direkt öffnen
open index.html          # macOS
xdg-open index.html      # Linux

# Oder über einen lokalen Server (empfohlen)
python3 -m http.server 8000
# → http://localhost:8000
```

## Die Stücke

| Nr. | Stück | Technik | Look |
|-----|-------|---------|------|
| 01 | [Motion Reel](pieces/01-motion-reel.html) | CSS · SVG · Canvas | Neon / dunkel |
| 02 | [Brand Reveal](pieces/02-brand-reveal.html) | Orchestrierte Ladesequenz | Warm / premium |
| 03 | [Self-Drawing Mark](pieces/03-logo-draw.html) | SVG `stroke-dashoffset` | Hell / Galerie |
| 04 | [Scroll Experience](pieces/04-scroll-experience.html) | IntersectionObserver · Sticky · Parallax | Editorial / Indigo |
| 05 | [Interactive Field](pieces/05-interactive-field.html) | Canvas · Feder-Physik | Interaktiv / Navy |
| 06 | [Animated Icons](pieces/06-icon-set.html) | SVG + CSS Micro-Interactions | Design-System / hell |
| 07 | [Particle Verse](pieces/07-particle-verse.html) ✦ | Canvas Flow-Field · Text-to-Particle | Kosmisch / interaktiv |

### 01 · Motion Reel
Acht kleine Effekte in einem Raster: Gradient-Orb, Audio-Equalizer, Sinus-Welle,
kinetischer Loader, Partikel-Konstellation, 3D-Würfel, Typewriter und ein
magnetischer Button. Oben ein „RGB-Split"-Glitch auf dem Wort *MOTION*.

### 02 · Brand Reveal
Ein cinematischer Marken-Auftritt: driftende Aurora-Lichtfelder, ein Schriftzug,
der Buchstabe für Buchstabe aus der Unschärfe auftaucht, eine wachsende
Trennlinie und ein wiederkehrender Light-Sweep. Mit Replay-Button.

### 03 · Self-Drawing Mark
Ein geometrisches **KM-Monogramm**, das sich selbst zeichnet. Jeder Pfad nutzt
`pathLength="1"` und animiert `stroke-dashoffset` von `1` auf `0` — dadurch
„malt" sich jede Linie unabhängig von ihrer echten Länge sauber ein.

### 04 · Scroll Experience
Eine scroll-getriebene Erzählung: ein Fortschrittsbalken, gestaffelte Reveals per
`IntersectionObserver`, ein **Sticky-Pinned-Kapitel** mit wechselnden Frames,
Parallax-Ebenen und hochzählende Statistiken.

### 05 · Interactive Field
Ein Canvas-Feld aus hunderten Punkten mit einem **Feder-Physik-Modell**. Die
Punkte weichen dem Cursor aus und federn zurück, färben sich nach Auslenkung
(Mint → Koral → Violett), und ein Klick löst eine ringförmige Schockwelle aus.
Umschaltbar zwischen Abstoßen und Anziehen.

### 06 · Animated Icons
Zwölf animierte SVG-Icons als **Micro-Interactions** — u. a. ein sich zeichnendes
Häkchen, ein schlagendes Herz, eine läutende Glocke, ein Spinner und ein
Menü, das per Hover zum X morpht. Alle Farben über CSS-Variablen anpassbar.

### 07 · Particle Verse ✦ (Flagship)
Das Herzstück: **tausende Partikel** strömen durch ein lebendiges Flow-Feld und
**sammeln sich zu Schriftzügen** (`khanmotari` → `MOTION` → `∞`), bevor sie
wieder ins Feld zerstäuben. Der Text wird zur Laufzeit gerendert, pixelweise
abgetastet und in Zielpunkte übersetzt (**Text-to-Particle**). Additives
Glow-Blending und Bewegungs-Trails erzeugen den kosmischen Look. Voll
interaktiv: die Maus stößt Partikel ab, ein Klick löst eine Explosion aus,
und die Steuerleiste schaltet zwischen *Form*, *Flow* und *Burst* um.
Die Partikelzahl skaliert automatisch mit der Bildschirmgröße.

## Struktur

```
khanmotari/
├── index.html            # Galerie-Startseite (verlinkt alle Stücke)
├── README.md
└── pieces/
    ├── 01-motion-reel.html
    ├── 02-brand-reveal.html
    ├── 03-logo-draw.html
    ├── 04-scroll-experience.html
    ├── 05-interactive-field.html
    └── 06-icon-set.html
```

## Prinzipien

- **Keine Abhängigkeiten** — jede Datei ist self-contained und läuft offline.
- **Barrierefrei** — alle Stücke respektieren `prefers-reduced-motion`.
- **Performant** — Animationen laufen über GPU-freundliche Eigenschaften
  (`transform`, `opacity`) und `requestAnimationFrame`.
- **Editierbar** — Farben liegen als CSS-Custom-Properties am Anfang jeder Datei.
