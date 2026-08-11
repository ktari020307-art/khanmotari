# khanmotari

Die **persönliche Marke / Portfolio-Seite** von khanmotari. Die Startseite
(`index.html`) ist eine One-Page-Site mit Hero (WebGL-Shader-Hintergrund),
Über-mich, Fokus, ausgewählten Arbeiten und Kontakt. Die „Arbeiten" sind
neun eigenständige **Motion-Graphics-Studien** — jede demonstriert eine
andere Animationstechnik, komplett in reinem **HTML, CSS, SVG, Canvas und
WebGL**. Kein Video, keine externen Bibliotheken, keine Build-Tools.

> **To-do:** Die Platzhalter in `index.html` (in eckigen Klammern `[...]`)
> mit echten Angaben ersetzen — Name, Rolle, Über-mich-Text, Schwerpunkte,
> E-Mail und Social-Links.

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
| 08 | [Aurora Engine](pieces/08-aurora-engine.html) ✦ | WebGL Fragment-Shader (GLSL) | GPU-Plasma / interaktiv |
| 09 | [Hyperspace](pieces/09-hyperspace.html) ✦ | WebGL Raymarching · Gyroid SDF | 3D-Flug / interaktiv |

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

### 08 · Aurora Engine ✦ (Flagship · WebGL)
Die höchste Stufe: ein **WebGL-Fragment-Shader**, der pro Frame **jeden Pixel
auf der GPU** berechnet. Ein fließendes Plasma-/Aurora-Feld entsteht aus
**domain-warped Fractal Brownian Motion** (mehrfach ineinander verschachteltes
Noise), angereichert mit leuchtenden Filamenten und einer Vignette. Die Maus
verzerrt das Feld in Echtzeit über eine Ripple-Welle. Läuft mit einem
Full-Screen-Triangle und drei Uniforms (`u_time`, `u_res`, `u_mouse`); bei
fehlender WebGL-Unterstützung greift ein sauberer Fallback.

### 09 · Hyperspace ✦ (Flagship · Raymarching)
Der Gipfel: **echtes 3D ohne ein einziges Polygon**. Ein Raymarching-Shader
schießt von jedem Pixel einen Strahl und nähert sich per **Signed Distance
Field** (einer unendlich wiederholten, sich verdrehenden **Gyroid-Struktur**)
Schritt für Schritt an die Oberfläche an. Entlang des Strahls wird
**volumetrisches Glühen** aufsummiert, dazu Tiefen-Nebel, eine Cosinus-Palette
und eine Vignette. Die Kamera fliegt endlos vorwärts, die Maus steuert die
Blickrichtung. Dieselbe Technik wie in der Shader-Demoscene — 78 March-Schritte
pro Pixel, jeden Frame, auf der GPU.

## Struktur

```
khanmotari/
├── index.html            # Portfolio-Startseite (Hero, Über-mich, Studio, Arbeiten, Connect)
├── studio.html           # Brand-Kit Studio: Namen-Generator mit Palette, Fonts & Bild-Export
├── tools/
│   ├── brand-cockpit.html # Personal-Brand-Cockpit: Deep-Research-Wissen → personalisiertes Strategie-Dossier
│   ├── blueprint.html    # Drehplan-Generator: Thema → fertiger, sekundengenauer Drehplan
│   ├── kreativ-engine.html # Kreativ-Engine: generiert Video-Konzepte aus 6 Bausteinen + Kreativ-Zwang
│   ├── monogram.html     # Monogramm-Generator: Initialen → Logo (PNG + SVG)
│   ├── wallpaper.html    # Wallpaper-Generator: WebGL-Kunst als Wallpaper (PNG, versch. Formate)
│   └── icons.html        # Icon-Kit: 12 SVG-Icons in eigener Farbe/Größe (Copy + Download)
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
