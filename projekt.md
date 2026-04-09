# SHK-Hennegriff – Recruiting Projekt

## Übersicht
Recruiting-Automatisierung für **Bad und Heizung Thilo Hennegriff**, Oberkessach (BaWü).
Bewerber kommen über Meta Lead Ads oder Jobportale, werden per n8n-Formular erfasst und per E-Mail + Telegram an den Kunden weitergeleitet.

---

## Technischer Stack

| Komponente | Details |
|---|---|
| n8n Instanz | https://n8n.fons-tel.de |
| Workflow-ID | `Qt3CWYFEdujyrY55` |
| Form-Pfad | `/form/hennegriff-recruiting` |
| Tally Webhook | `https://n8n.fons-tel.de/webhook/hennegriff-tally` |
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
- [x] Tally.so Formular erstellt und Webhook verbunden
- [x] Telegram parallel zur E-Mail geschaltet
- [ ] Telegram-Eingang nach Tally-Einreichung bestätigen
- [ ] Eigenes Postfach anlegen (z.B. bewerbungen@badundheizung.de)
- [ ] SMTP-Credential mit echten Werten ersetzen
- [ ] Anzeigentexte erstellen
- [ ] Bilder für Meta-Anzeigen erstellen
- [ ] Meta-Kampagne aufsetzen

---

## Nächste Schritte (Prio-Reihenfolge)

1. **Telegram testen** – Tally-Formular einreichen und prüfen ob Telegram-Nachricht ankommt
2. **Postfach klären** – Thilo fragen ob er ein bewerbungen@-Postfach einrichten kann
3. **SMTP aktualisieren** – Credential mit echten Zugangsdaten ersetzen
4. **E-Mail testen** – Kompletten Durchlauf mit echter E-Mail testen
5. **Anzeigentexte** – Texte für Meta Ads erstellen (Azubi / Fachkraft / Quereinsteiger)
6. **Meta-Kampagne** – Aufsetzen sobald Texte und Bilder stehen

---

## Dateien

| Datei | Beschreibung |
|---|---|
| `website/hennegriff-recruiting.html` | Recruiting-Landingpage Entwurf v1 |
| `website/hennegriff-recruiting-v2.html` | Recruiting-Landingpage Entwurf v2 |
| `website/index.html` | Mustermann Haustechnik Website-Template |
| `briefing/claude-code-briefing.html` | Projekt-Briefing Dokument |
