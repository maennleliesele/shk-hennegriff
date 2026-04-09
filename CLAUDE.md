# SHK-Hennegriff – Recruiting Projekt

Diese Datei gibt Claude Code Anweisungen für die Arbeit in diesem Projekt.

---

## Was das hier ist

Recruiting-Automatisierung für **Bad und Heizung Thilo Hennegriff**, Oberkessach (BaWü). Bewerber kommen über Google Display Ads oder Kleinanzeigen auf die Landing Page, füllen ein eingebettetes Multi-Step-Formular aus und werden per E-Mail + Telegram-Ping an den Kunden weitergeleitet.

**Wichtig:** Starte jede Session mit `/prime` um den vollständigen Kontext zu laden.

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

## Workspace-Struktur

```
.
├── CLAUDE.md              # Diese Datei — immer geladen
├── projekt.md             # Projektstatus und Nächste Schritte
├── .claude/
│   └── commands/
│       ├── prime.md       # /prime — Session-Start
│       ├── create-plan.md # /create-plan — Implementierungspläne erstellen
│       ├── implement.md   # /implement — Pläne umsetzen
│       └── shutdown.md    # /shutdown — Session sauber beenden
├── context/               # Hintergrund-Kontext über das Projekt
├── briefing/              # Projekt-Briefing Dokumente
├── website/               # Landing Page Entwürfe
├── plans/                 # Implementierungspläne
├── outputs/               # Arbeitsergebnisse
├── reference/             # Vorlagen und Patterns
└── scripts/               # Automatisierungsskripte
```

---

## Commands

### /prime
Session-Start: Kontext laden, Projektstatus verstehen, bereit machen.

### /create-plan [anforderung]
Detaillierten Implementierungsplan erstellen, bevor Änderungen gemacht werden.

### /implement [plan-pfad]
Einen mit /create-plan erstellten Plan umsetzen.

### /shutdown
Session sauber beenden: aufräumen, CLAUDE.md aktualisieren, zusammenfassen.

---

## Session-Workflow

1. **Start**: `/prime` ausführen
2. **Arbeiten**: Commands nutzen oder Claude direkt beauftragen
3. **Größere Änderungen**: erst `/create-plan`, dann `/implement`
4. **Ende**: `/shutdown` ausführen

---

## Regeln

- n8n-mcp Tool für alle n8n-Änderungen nutzen
- Workflows nie ohne Sticky Note mit Dokumentation anlegen
- Workflows nie publizieren
- Telegram läuft immer parallel zur E-Mail — nie als Switch dahinter
