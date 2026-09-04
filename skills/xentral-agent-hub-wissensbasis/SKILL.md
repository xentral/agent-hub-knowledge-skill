---
name: xentral-agent-hub-wissensbasis
description: >
  Interview zur Wissensbasis für den Xentral Agent Hub. Fragt Unternehmen, Vorlagen und
  Fachwissen ab, schreibt die Antworten als Wissenseinträge im Upload-Format des Agent Hub
  (Type, Titel / Frage, Inhalt / Antwort) und gibt eine CSV aus. Einsetzen, wenn jemand
  seine Xentral-Agenten mit Firmenwissen versorgen oder die Vorlage „Wissensdatenbank
  Template Xentral Agent Hub“ ausfüllen will.
---

# Wissensbasis für den Xentral Agent Hub

## Ziel

Am Ende steht eine Liste von Wissenseinträgen, die die Person ab dem 1. Oktober 2026 in
den Agent Hub importiert. Jeder Eintrag hat drei Felder:

| Feld | Inhalt | Erlaubt |
|---|---|---|
| `Type` | Art des Eintrags | genau eines von `Unternehmen`, `Vorlagen`, `Fachwissen` |
| `Titel / Frage` | Thema | 2 bis 6 Wörter, innerhalb der Liste eindeutig |
| `Inhalt / Antwort` | das Wissen selbst | vollständige Sätze, 2 bis 8 pro Eintrag |

Die Themen mit Leitfragen stehen in `reference/themen.md`. Lies die Datei, bevor du fragst.

## Regeln

- Deutsch, Du-Form. Eine Frage pro Nachricht, höchstens zwei, wenn sie zusammengehören.
- Nichts erfinden. In einen Eintrag kommt nur, was die Person gesagt oder als Datei gegeben
  hat. Fehlt eine Frist, ein Betrag oder eine Zuständigkeit, frag nach.
- Konkret. „Rückgabe innerhalb von 30 Tagen, Etikett muss dran sein, Erstattung auf das
  ursprüngliche Zahlungsmittel“ ist ein Eintrag. „Wir sind kulant“ ist keiner.
- Ein Satz ist zu wenig. Frag weiter, bis der Eintrag einen Fall ohne Rückfrage löst.
- Themen, die nicht zutreffen, fallen weg.
- Dateien (Preisliste, Brand Guide, AGB) werden im Eintrag in zwei bis drei Sätzen
  zusammengefasst, mit dem Hinweis, dass die Datei beim Onboarding hochgeladen wird.
  Keine ganzen Dokumente in einen Eintrag kopieren.
- Keine Daten einzelner Kund:innen, keine Passwörter, keine Zugangsdaten.

## Ablauf

1. Sag in zwei Sätzen, was ihr baut und dass es 20 bis 40 Minuten dauert. Frag, was das
   Unternehmen verkauft und an wen (B2B, B2C, beides). Wähle danach die Branchen-Blöcke aus
   `reference/themen.md`, die zusätzlich zu „Allgemein“ passen, nenne sie und lass sie
   bestätigen.
2. Arbeite „Allgemein“ ab, in der Reihenfolge Unternehmen, Vorlagen, Fachwissen. Dann die
   Branchen-Blöcke. Die Leitfragen sind der rote Faden, kein Formular: Ist ein Thema schon
   beantwortet, frag nicht erneut. Eigene Themen der Person werden zusätzliche Einträge.
3. Nach jedem Thema formulierst du den Eintrag aus und zeigst ihn: Type, Titel, Inhalt.
   Die Person bestätigt oder korrigiert. Erst dann weiter.
4. Nach jedem Block zeigst du alle bisherigen Einträge als Tabelle.
5. Zum Schluss lieferst du die vollständige Tabelle, dieselben Einträge als CSV und eine
   Liste offener Punkte.

## CSV

Drei Spalten in dieser Reihenfolge und Schreibweise, Komma als Trennzeichen, UTF-8, Felder
mit Komma oder Zeilenumbruch in doppelten Anführungszeichen:

```csv
Type,Titel / Frage,Inhalt / Antwort
Fachwissen,Retouren,"Wir bieten kostenlosen Ersatz bei Defekt. Die Kundin oder der Kunde behält die Ware, eine Rücksendung ist nicht nötig. Ab 50 EUR Warenwert holen wir per DHL ab."
```

Beispiel: `templates/beispiel_export.csv`. Leere Vorlage mit den Standardthemen:
`templates/wissensdatenbank_vorlage.csv`. Kannst du Dateien schreiben, speichere die CSV als
`wissensbasis-agent-hub.csv` und nenne den Pfad. Sonst gib den CSV-Block so aus, dass er sich
in eine Datei kopieren lässt.

## Nach dem Interview

Ab dem 1. Oktober 2026 legt die Person die Einträge im Agent Hub an, einzeln oder per
CSV-Import. Bei mehr als einer Handvoll Einträgen ist der Import schneller. Das Helpcenter
lässt sich zusätzlich direkt verbinden, dann kennt der Agent das Produktwissen ohne doppelte
Pflege.

## Prüfung vor der Ausgabe

- `Type` ist einer der drei erlaubten Werte, exakt geschrieben.
- Jeder Titel kommt nur einmal vor.
- Jeder Inhalt enthält Zahlen, Fristen, Zuständigkeiten oder Beispiele, wo es sie gibt.
- Keine Platzhalter wie „TBD“, „siehe Anhang“ oder eckige Klammern.
- Keine Daten einzelner Kund:innen.
- Die Anrede in den Vorlagen-Einträgen (du oder Sie) ist überall gleich.
