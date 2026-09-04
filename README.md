# Wissensbasis für den Xentral Agent Hub

Am 1. Oktober 2026 startet der Agent Hub. Die Agenten darin kennen deinen Betrieb erst,
wenn du ihnen sagst, wie er läuft: Retouren, Lieferzeiten, Tonfall, Zahlungsziele.
Dieser Skill fragt das ab und schreibt die Antworten in das Format, das der Agent Hub
beim Anlegen eines Wissenseintrags erwartet. Ergebnis ist eine CSV, die du ab dem 1. Oktober
importierst.

Dieselben Fragen stellt auch der [Gem in Google Gemini](https://gemini.google.com/gem/1Q_CbcWDfvratd4Cc9BKIRYs920YauQBZ?usp=sharing).
Wer lieber eine Tabelle ausfüllt, nimmt die [Vorlage in Google Sheets](https://docs.google.com/spreadsheets/d/1ghu4z7YS4n9LLHF4AUrwLdk0jjWzpzXHdh2xZSZIxXU/copy).

## Nutzung

Ohne Installation, auch mit kostenlosen Chat-Versionen: [`wissensbasis-skill-komplett.md`](https://raw.githubusercontent.com/xentral/agent-hub-knowledge-skill/main/wissensbasis-skill-komplett.md)
kopieren, als erste Nachricht in ChatGPT, Gemini oder Claude einfügen, darunter „Start“ schreiben.

Claude Code:

```
/plugin marketplace add xentral/agent-hub-knowledge-skill
/plugin install wissensbasis@xentral-agent-hub
```

Claude.ai und Claude Desktop: [ZIP herunterladen](https://github.com/xentral/agent-hub-knowledge-skill/releases/latest/download/xentral-agent-hub-wissensbasis.zip)
und unter Einstellungen als Skill hinzufügen.

Codex, Cursor und andere Agenten: den Ordner `skills/xentral-agent-hub-wissensbasis`
in das Skill-Verzeichnis des Werkzeugs kopieren.

## Ergebnis

```csv
Type,Titel / Frage,Inhalt / Antwort
Fachwissen,Retouren,"Wir bieten kostenlosen Ersatz bei Defekt. Die Kundin oder der Kunde behält die Ware, eine Rücksendung ist nicht nötig. Ab 50 EUR Warenwert holen wir per DHL ab."
```

`Type` ist einer von `Unternehmen`, `Vorlagen`, `Fachwissen`. Die drei Spalten entsprechen
den Feldern im Agent Hub. Import ab dem 1. Oktober: Zeile für Zeile oder als CSV.

## Hinweise

- Der Skill greift nicht auf Xentral zu. Deine Angaben bleiben in dem Chat, den du nutzt.
- Keine Kundendaten und keine Zugangsdaten in die Einträge. Der Skill prüft das am Ende mit.
- Das Helpcenter kannst du zusätzlich direkt mit dem Agent Hub verbinden. Produktwissen
  musst du dann nicht doppelt pflegen.
- Zugang zum Agent Hub: [account@xentral.com](mailto:account@xentral.com). Fehler oder
  Vorschläge zum Skill: Issue in diesem Repository.

## Dateien

```
skills/xentral-agent-hub-wissensbasis/
  SKILL.md                                Anleitung für den Assistenten
  reference/themen.md                     37 Themen mit Leitfragen, aus der offiziellen Vorlage
  templates/wissensdatenbank_vorlage.csv  leere Vorlage im Upload-Format
  templates/beispiel_export.csv           ausgefülltes Beispiel
wissensbasis-skill-komplett.md            Anleitung und Themen in einer Datei
.claude-plugin/                           Manifest für Claude Code
```

English: an agent skill that interviews you about your business and writes the answers
in the Xentral Agent Hub knowledge-entry format (`Type`, `Titel / Frage`, `Inhalt / Antwort`),
exported as CSV for the import on 1 October 2026. The interview is in German.
