# SHK-Hennegriff – Recruiting Projekt

## Übersicht
Recruiting-Automatisierung für **Bad und Heizung Thilo Hennegriff**, Oberkessach (BaWü).
Bewerber kommen über Google Display Ads oder Kleinanzeigen auf die Landing Page, füllen ein eingebettetes Multi-Step-Formular aus und werden per E-Mail + Telegram-Ping an den Kunden weitergeleitet.

---

## Technischer Stack

| Komponente | Details |
|---|---|
| n8n Instanz | https://n8n.fons-tel.de |
| Workflow-ID | `Qt3CWYFEdujyrY55` |
| Formular Webhook | `https://n8n.fons-tel.de/webhook/hennegriff-tally` |
| Landing Page | `website/hennegriff-v5.html` (eingebettetes Multi-Step-Formular) |
| E-Mail Empfänger | chh@thilohennegriff.de |
| Telegram Gruppe | Hennegriff Bewerbungen (Chat-ID: -5219904041) |

### Credentials
| Typ | Name | ID | Status |
|---|---|---|---|
| SMTP | `SMTP Hennegriff` | `ph70OybRB9zxcJTz` | Platzhalter – echtes Postfach fehlt noch |
| Telegram | `HennegriffRecruiting` | `8IeT54UrfT4Qqaui` | Eingetragen |

---

## Status

- [x] n8n Workflow gebaut und aktiviert
- [x] Multi-Step-Formular direkt in Landing Page v5 eingebettet
- [x] Telegram auf datensparsamste Benachrichtigung reduziert (DSGVO)
- [x] DSGVO-Modal mit Datenschutz-Checkbox in v5 eingebaut
- [x] Projekt auf GitHub hochgeladen
- [ ] Eigenes Postfach anlegen (z.B. bewerbungen@badundheizung.de)
- [ ] SMTP-Credential mit echten Werten ersetzen
- [ ] Formular-Endtest durchführen (Bewerbung absenden → E-Mail + Telegram prüfen)
- [ ] Banner-Creative erstellen (1200×628px, Fachkraft + Quereinsteiger)
- [ ] Google Display Kampagne aufsetzen (Placement: Kleinanzeigen App)

---

## Nächste Schritte (Prio-Reihenfolge)

1. **Postfach klären** – Thilo fragen ob er ein bewerbungen@-Postfach einrichten kann
2. **SMTP aktualisieren** – Credential mit echten Zugangsdaten ersetzen
3. **Endtest** – Formular auf v5 ausfüllen, E-Mail + Telegram-Ping prüfen
4. **Banner-Creative** – 1200×628px für Fachkraft + Quereinsteiger (via NotebookLM + Canva)
5. **Google Display Kampagne** – CPC, Placement Kleinanzeigen App, 40km Radius

---

## Dateien

| Datei | Beschreibung |
|---|---|
| `website/hennegriff-v5.html` | Aktuelle Landing Page – eingebettetes Formular, DSGVO-Modal |
| `reference/recruiting-landingpage-standard.md` | Design- & Textstandards für alle Recruiting-Pages |
| `context/` | Business-Info, Strategie, aktuelle Daten |
