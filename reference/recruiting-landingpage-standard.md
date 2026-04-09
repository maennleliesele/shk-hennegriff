# Recruiting Landingpage — Standard & Mindestanspruch

> Erarbeitet im April 2026 auf Basis der Hennegriff-Recruiting-Seite.
> Gilt als Mindestanspruch für alle zukünftigen Recruiting-Landingpages.

---

## 1. Inhalt & Sprache

### Pflicht
- **Duzen** — konsequent, keine Ausnahmen. Nie „Sie".
- **Keine Gedankenstriche** (–) im Fließtext. Alternativen: Punkt, Komma, neuer Satz.
- **Keine Doppelpunkte** (:) im Fließtext. Satz umformulieren.
- **Konsistente Schreibweise**: „3 min" nicht „3min", Umlaute korrekt (ä ö ü ß).
- **Konkrete Benefits** statt Floskeln:
  - Nicht: „Attraktive Vergütung"
  - Sondern: „30 Tage Urlaub + Weihnachtsgeld — Mehr als der Standard"
- **Echte Namen & Fotos** statt Platzhalter/Initialen. Initialen nur als absolute Ausweichlösung.
- **Persönliches Zitat** der Führungsperson — kein Unternehmenstext, kein PR-Sprech. Authentisch, kurz, ich-Form.

### Qualitätsmerkmale guter Copy
- Schlüsselphrasen mit `<strong>` hervorheben — zieht den Blick und strukturiert den Text
- Zwei kurze Absätze statt einem langen Block
- Kein Slide-Text länger als 4 Sätze
- Regionale Identität einbauen wo sinnvoll (Beispiel: „Badische Gelassenheit, echte Bodenständigkeit.")
- Slogans wie HWK: kurz, doppeldeutig, einprägsam (Beispiel: „Gemacht, nicht generiert.")

---

## 2. Design & UI

### Icons
- **Keine Emojis** als UI-Elemente — immer SVG-Icons (Lucide/Feather-Stil, stroke-based)
- Einheitliche Icon-Größe pro Kontext (18px in Cards, 28px in Positionskarten)
- Icon-Farbe: weiß auf dunklem Grund, `var(--teal)` auf hellem Grund

### Farben
- Farbpalette immer aus dem Kunden-Branding ableiten (Logo, bestehende Website)
- Dunkle Hero-Hintergründe nie als Vollton — immer als Gradient (Beispiel: `linear-gradient(160deg, #0c2a40, #173f5f, #0c2a40)`)
- Grautöne für Subtexte: mindestens `#8fa4b4` (nicht zu dunkel)
- Akzentfarbe für Badges/CTAs: solide Fläche, nicht transparent

### Badge „Wir suchen Verstärkung"
- Ca. 1.5× größer als Standard-Badges
- Solide Hintergrundfarbe (nicht transparent/outline)
- Weißer Puls-Punkt für Lebendigkeit

### Logo
- SVG bevorzugen, kein base64 PNG
- Auf dunklem Hintergrund: `filter: brightness(0) invert(1)` für weiße Version
- Mindestgröße im Nav: 48–52px Höhe

---

## 3. Interaktion & Animationen

### Kultur-Carousel (rotierende Slides)
- Min. 4–5 Slides mit unterschiedlichen Aspekten der Unternehmenskultur
- Wechselintervall: 12–15 Sekunden (nicht zu schnell)
- Fade-Übergang: `opacity 0.7s ease`
- Dots als manuelle Navigation, aktiver Dot als längliches Pill
- Container-Mindesthöhe so setzen dass Dots nie in den Text ragen
- Textstruktur: immer 2 Absätze pro Slide, max. 4 Sätze gesamt
- Kein Gedankenstrich, kein Doppelpunkt

### Marken-Banner (laufend)
- Endloser Loop ohne sichtbaren Neustart
- Pixel-genaue Breite per JS berechnen (`getBoundingClientRect`)
- `will-change: transform` + `translateZ(0)` für GPU-Beschleunigung
- `margin-right` statt `gap` damit letztes Item im Set korrekt abschließt
- Logos: graustufen im Ruhezustand, Farbe bei Hover
- Pause bei Hover (`animation-play-state: paused`)
- Fade-Masken links/rechts (`mask-image: linear-gradient(...)`)

### Allgemein
- Animationen GPU-beschleunigt wo möglich
- Hover-Effekte auf allen klickbaren Elementen
- Smooth Scroll auf der Seite

---

## 4. Struktur & Sektionen (Mindest-Aufbau)

```
NAV          — Logo + direkter Bewerbungs-CTA
HERO         — Headline, Subline, Statistiken, Benefit-Card + CTA
KULTUR       — Rotierendes Carousel (5 Slides)
MARKEN       — Laufender Banner mit Hersteller-Logos
POSITIONEN   — Stellenkarten (Azubi / Quereinsteiger / Fachkraft)
WARUM WIR    — 4 Punkte + Zitat der Führungsperson (mit Foto)
PROZESS      — 4 Schritte zum Job
FINAL CTA    — Nochmal Bewerbung, minimal, klar
FOOTER       — Impressum, Datenschutz, Website-Link
```

### CTA-Prinzip
- Mindestens 3× auf der Seite platziert (Hero, Positionen, Final)
- Immer mit Zeit-Angabe: „dauert 3 min"
- Immer mit Hürden-Abbau: „Kein Anschreiben · Kein Lebenslauf"

---

## 5. Technisches

- Alle Dateien lokal referenziert (keine base64-Einbettung von Logos)
- Relative Pfade zu Asset-Ordner (`../Dateien/`)
- Google Fonts: Cabinet Grotesk + Lora (keine Display-Fonts die das Layout zerschießen können)
- Vanilla JS — kein Framework, kein jQuery
- Kein `console.log` im finalen Code
- Mobile-Responsive mit definierten Breakpoints (`@media max-width: 760px`)

---

## 6. Learnings aus dieser Session

| Was schiefgelaufen ist | Lösung |
|---|---|
| Bebas Neue hat Layout zerschossen | Display-Fonts nur testen wenn sicher — Cabinet Grotesk ist stabiler |
| Dots lagen mitten im Text | `min-height` groß genug setzen + `position: absolute` auf Slides |
| Marken-Banner sprang beim Loop | `getBoundingClientRect` für pixelgenaue Berechnung statt `translateX(-50%)` |
| Zitat noch generisch nach erster Version | Führungsperson konkret fragen: Familienkontext, eigene Worte |
| „3min" statt „3 min" | Konsistenz-Check am Ende jeder Session |
| Gedankenstriche und Doppelpunkte im Text | Globaler Sweep vor Finalisierung |
| Marken-Banner stoppt nach Verschiebung | Banner-JS erst bei `window.load` ausführen, nicht beim Script-Parse |
| Python-Script mit Apostrophen crasht im Heredoc | Script immer als `.py` Datei schreiben, dann `python3 datei.py` |
| HTML dupliziert durch mehrfaches `</body>`-Replace | Jedes Insert-Script nur einmal ausführen, vorher auf Vorhandensein prüfen |
| Doppeltes `class=""` durch Regex-Replace | Regex-Replacements auf Links immer mit exaktem Muster, nie blind global |
| Kaputte Positionskarten durch class-Duplikat | Nach jedem globalen Regex-Replace alle `class=` Attribute prüfen |
| Flip-Rückgängig komplex durch zu viele Änderungen | Ab sofort: neue Versionsdatei (v5, v6...) statt bestehende überschreiben |
| `rfind('</script>')` gibt -1 wenn keine Script-Tags in Datei → Datei verdoppelt | JS nie per `rfind` einfügen — immer `content.replace('</body>', '<script>...' + js + '</script>\n</body>', 1)` |
| Card-Wrap: nur `hero-right` ersetzen lässt inneres `<div class="card">` stehen → doppelte Verschachtelung | Exaktes 2-Zeilen-Replace für Open (`hero-right + card`) UND Close (`card-foot + </div></div>`) |
| Bedingte Formular-Schritte zeigen falsches Maximum vor Interesse-Auswahl (`1 von 3` statt `1 von 6`) | Fallback-Maximum hardcoden: `var total = ans.interesse ? active.length : MAX_STEPS` |
| Zwei CSS-Blöcke in der Datei → `replace()` trifft nur ersten | Bei doppelten Style-Blöcken immer `replace_all: true` verwenden |
| Button-Inhalte verschwinden hinter `::before` Teal-Overlay | Alle Kinder-Elemente brauchen `position: relative; z-index: 1` wenn `::before` genutzt wird |
| Font-Smoothing in der Card-Back fehlte → Schrift wirkte rau | `-webkit-font-smoothing: antialiased; -moz-osx-font-smoothing: grayscale` auf `.card-back` und Frage-Elementen setzen |

---

## 8. Formular-Integration (ab v5)

### Prinzip
- Kein Tally-Redirect — eigenes HTML-Formular direkt in die Landing Page
- Kein Medienbruch: Bewerber bleibt auf der Seite
- CTA-Klick → Scroll nach oben → Hero-Card dreht sich (3D-Flip) → Formular sichtbar
- Formular sendet per `fetch()` POST an n8n-Webhook

### Pflichtfelder (Minimum)
1. Vor- und Nachname
2. Telefonnummer
3. Interesse (Ausbildung / Quereinstieg / Fachkraft) — Radio
4. Wann kannst du anfangen? — Radio
5. Schulabschluss — Radio
6. Berufserfahrung (Jahre) — Radio (bedingt: nur bei Fachkraft/Quereinstieg)
7. Aktuell berufstätig? — Radio (bedingt)

### Card-Flip Technik
```css
.card-flip-wrap { perspective: 1200px; }
.card-flipper {
  position: relative;
  transform-style: preserve-3d;
  transition: transform 0.75s cubic-bezier(0.4, 0.2, 0.2, 1);
}
.card-flipper.flipped { transform: rotateY(180deg); }
.card-front, .card-back { backface-visibility: hidden; }
.card-back { position: absolute; inset: 0; transform: rotateY(180deg); }
```
- `card-flipper` braucht explizite Mindesthöhe oder `card-back` wird unsichtbar
- Scroll to top vor Flip: `window.scrollTo({ top: 0, behavior: 'smooth' })` dann `setTimeout(flip, 500)`
- Zurück-Button auf der Rückseite nicht vergessen

### Formular-Design-Regeln
- Inputs: `var(--off)` Hintergrund, Border `var(--border)`, Focus → `var(--teal)`
- Radio-Optionen als klickbare Cards, nicht native Radio-Buttons
- Submit-Button: `var(--teal)`, `box-shadow` für Tiefe
- Danke-State direkt in der Card (kein Redirect)

---

## 7. Slogan-Pool (Hennegriff / SHK)

Für künftige Einsätze:

**SHK-spezifisch:**
- „Wo andere frieren, wärmst du."
- „Warmes Wasser läuft nicht von selbst."
- „Du machst heiß, was andere kalt lässt."
- „Zukunft hat Rohre."

**Selbstbewusst / zeitgeistig:**
- „Gemacht, nicht generiert."
- „Andere scrollen. Du gestaltest."
- „Nicht im Trend. Im Fundament."
- „Energiewende braucht deine Hände."
- „Handwerk 2.0."

**Team / Kultur:**
- „Klein genug, dass jeder zählt. Groß genug, dass es Sinn macht."
- „Du rettest nicht nur Heizungen. Du rettest Abende."
- „Wir bauen, was bleibt."
