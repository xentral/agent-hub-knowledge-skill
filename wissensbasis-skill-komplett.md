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


# Themen und Leitfragen

Aus der offiziellen Vorlage „Wissensdatenbank Template Xentral Agent Hub“ (September 2026). `Type` ist einer von `Unternehmen`, `Vorlagen`, `Fachwissen`. Die Leitfragen dienen dem Gespräch und werden nicht hochgeladen.

„Allgemein“ gilt für jedes Unternehmen. Die Branchen-Blöcke nur abfragen, wenn sie zutreffen. Eigene Themen sind erwünscht.

## Allgemein

| Type | Titel / Frage | Leitfragen |
|---|---|---|
| Unternehmen | Unternehmensprofil | Wie heißt dein Unternehmen, was verkaufst du, wer ist deine Zielgruppe (B2B, B2C oder beides)? Wie würdest du dein Geschäftsmodell in 2-3 Sätzen beschreiben? |
| Unternehmen | Standorte und Lager | Hast du mehrere Standorte oder Lager? Welche, und wofür sind sie jeweils zuständig? |
| Unternehmen | Produktkatalog | Was sind deine wichtigsten Produkte oder Produktkategorien? Falls du eine Produktliste oder einen Katalog-Link hast: separat bereithalten, kein Einfügen hier nötig. |
| Unternehmen | Website und Helpcenter | Link zu deiner Unternehmenswebsite und, falls vorhanden, zu deinem Helpcenter oder FAQ-Bereich. Das Helpcenter kannst du zusätzlich direkt verbinden, siehe Anleitung. |
| Vorlagen | Tone of Voice | Duzt oder siezt du deine Kund:innen? Wie klingt eine typische Antwort von dir? 2-3 Beispiel-E-Mails oder Textbausteine helfen am meisten. |
| Vorlagen | Begrüßung und Schlussformel | Wie sieht deine Standard-Anrede und Verabschiedung in E-Mails aus? |
| Vorlagen | Wörter, die wir vermeiden | Gibt es Formulierungen oder Begriffe, die bei euch bewusst nicht verwendet werden? |
| Vorlagen | Brand Guide | Falls vorhanden: kurze Zusammenfassung der wichtigsten Vorgaben. Die Datei selbst separat bereithalten. |
| Fachwissen | Retouren | Welche Rückgabewege bietest du an (Ersatz, Rückversand, Kunde behält Ware)? Gibt es Grenzwerte oder Fristen? Wie und wo wird zurückgesandte Ware gelagert oder entsorgt? Wer muss ab welchem Warenwert freigeben? |
| Fachwissen | Auftragsabwicklung | Wie gehst du mit Bestellungen um, die per PDF oder E-Mail eingehen? Gibt es Standard-Zahlungsziele, Rabatte für bestimmte Kund:innen oder einen Mindestbestellwert? |
| Fachwissen | Lieferstatus | Welche Versanddienstleister nutzt du? Was sind deine Standard-Lieferzeiten? Was kommunizierst du, wenn sich eine Lieferung verzögert? |
| Fachwissen | Häufige Fragen | Welche Fragen bekommst du von Kund:innen am häufigsten, unabhängig von Retouren oder Bestellungen? |
| Fachwissen | Verbindlichkeiten / Lieferantenrechnungen | Wie prüfst du eingehende Rechnungen gegen die zugehörige Bestellung? Auf welche Konten werden Verbindlichkeiten kontiert? Gibt es Freigabegrenzen oder wer muss ab welchem Betrag zustimmen? |
| Fachwissen | Zahlungsavise | Wie gleichst du eingehende Zahlungen mit offenen Rechnungen ab? Gibt es Besonderheiten bei Teilzahlungen oder Skonto? |

## B2B

| Type | Titel / Frage | Leitfragen |
|---|---|---|
| Fachwissen | Mindestbestellmengen und Staffelpreise | Gibt es Mindestbestellmengen je Artikel oder Kategorie? Wie sind die Staffelpreise aufgebaut, und ab welcher Menge greift welche Stufe? Gelten unterschiedliche Konditionen für Bestandskund:innen? |
| Fachwissen | Ersatzteil- und Kompatibilitätszuordnung | Wie ist ein Ersatzteil einer bestimmten Maschine oder Serie zugeordnet? Gibt es eine Teilenummern-Logik, die der Agent kennen sollte? Wie beantwortest du Anfragen wie "passt Teil X zu Maschine Y"? |
| Fachwissen | Lieferantenbezogene Lieferzeiten | Welche Artikel sind Eigenproduktion, welche Handelsware? Wie unterscheiden sich die Lieferzeiten je nach Lieferant? Was kommunizierst du bei bekannten Lieferantenverzögerungen proaktiv? |

## Lebensmittel-Branche

| Type | Titel / Frage | Leitfragen |
|---|---|---|
| Fachwissen | Rückgabe- und Reklamationspolitik | Nimmst du Ware grundsätzlich zurück oder nur bei Transportschaden/Fehllieferung? Gibt es Ausnahmen für ungeöffnete/original verpackte Ware? Wie gehst du mit Kühlware bei einer Reklamation um? |
| Fachwissen | Haltbarkeit und Lagerbedingungen | Welche Mindestrestlaufzeit muss bei Auslieferung noch gegeben sein? Welche Kühlkettenanforderungen gelten für welche Produktgruppen? Was passiert, wenn die Kühlkette unterbrochen wurde? |
| Fachwissen | Chargenrückverfolgung | Wie ist die Chargennummer mit Lieferung und Rechnung verknüpft? Wo wird sie im System hinterlegt? Was ist der Ablauf, wenn eine Charge zurückgerufen werden muss? Wer wird dabei informiert? |
| Fachwissen | Allergene und Kennzeichnung | Wo sind Allergeninformationen nach LMIV hinterlegt? Wie beantwortest du eine Kundenanfrage zu Allergenen konkret? Gibt es Produkte mit besonderem Hinweisbedarf (Spuren, Kreuzkontamination)? |
| Fachwissen | Losgrößen und Gewichtsware | Welche Produkte werden nach Gewicht statt nach Stück abgerechnet? Wie wird die Gewichtsabweichung beim Bestellabgleich (Liability-Case) behandelt? Gibt es Toleranzgrenzen? |

## Kosmetik-Branche

| Type | Titel / Frage | Leitfragen |
|---|---|---|
| Fachwissen | Rückgabe- und Reklamationspolitik | Ist geöffnete Ware grundsätzlich vom Widerruf ausgeschlossen? Wie prüfst du, ob eine Versiegelung intakt war? Gibt es Ausnahmen bei nachweislichem Mangel? |
| Fachwissen | Haltbarkeit und Lagerbedingungen | Welche PAO-Angabe (Period after Opening) gilt für welche Produkte? Gibt es Produkte mit besonderen Lager- oder Lichtschutzanforderungen (z. B. Naturkosmetik)? |
| Fachwissen | Chargenrückverfolgung | Wie ist die Chargennummer mit Lieferung und Rechnung verknüpft? Wo wird sie im System hinterlegt? Was ist der Ablauf, wenn eine Charge zurückgerufen werden muss? Wer wird dabei informiert? |
| Fachwissen | Allergene und Kennzeichnung | Wo ist die INCI-Liste je Produkt hinterlegt? Welche Duftstoffallergene sind deklarationspflichtig und wie beantwortest du Anfragen dazu? |
| Fachwissen | Sets und Bundles | Verkaufst du Produkte auch als Set oder Bundle? Wie werden diese im Bestellabgleich behandelt, wenn nur Teile eines Sets verfügbar sind? Gibt es eigene Rückgaberegeln für Sets? |

## Mode und Textil

| Type | Titel / Frage | Leitfragen |
|---|---|---|
| Fachwissen | Größen- und Passformberatung | Bietest du eine Größentabelle oder einen Größenrechner an? Gibt es markenspezifische Abweichungen bei der Passform (z. B. "fällt klein aus")? Wie beantwortest du Rückfragen zu Material und Tragegefühl? |
| Fachwissen | Retouren und Umtausch | Wie lange ist die Rückgabefrist, und weicht sie vom gesetzlichen Widerrufsrecht ab? Muss das Etikett noch dran sein? Wie gehst du mit sichtbaren Tragespuren um? Bietet ihr Umtausch in eine andere Größe an, oder nur Geld zurück? |
| Fachwissen | Saisonware und Abverkauf | Ab wann gilt ein Artikel als Auslaufware? Gibt es feste Rabattstufen zum Saisonende? Was passiert mit Restbeständen einzelner Größen, gibt es dafür eine andere Rückgaberegel? |
| Fachwissen | Materialpflege und Nachhaltigkeit | Wo sind Pflegehinweise je Artikel hinterlegt? Welche Materialangaben musst du laut Textilkennzeichnungsgesetz bereithalten? Gibt es Herkunfts- oder Zertifizierungsangaben (z. B. Bio-Baumwolle, GOTS), die häufig nachgefragt werden? |

## Möbel und Einrichtung

| Type | Titel / Frage | Leitfragen |
|---|---|---|
| Fachwissen | Lieferung und Aufbau | Läuft die Lieferung über Spedition oder Paketdienst? Bis wohin liefert ihr (Bordstein, Wohnung, Zimmer nach Wahl)? Bietet ihr einen Aufbauservice an, und ist er im Preis enthalten oder kostenpflichtig? |
| Fachwissen | Maßanfertigung und Sonderbestellungen | Welche Artikel sind individuell konfigurierbar? Ist die Rückgabe bei Sonderanfertigungen ausgeschlossen? Wie kommunizierst du die längere Lieferzeit bei Sonderbestellungen? |
| Fachwissen | Transportschäden | Wie prüft die Kundin oder der Kunde die Ware bei Anlieferung auf Transportschäden? Was ist der Meldeweg, wenn ein Schaden erst nach Auspacken auffällt? Gibt es eine Frist dafür? |

## Elektronik und Technik

| Type | Titel / Frage | Leitfragen |
|---|---|---|
| Fachwissen | Garantie und Gewährleistung | Wie lange läuft die gesetzliche Gewährleistung, und gibt es zusätzlich eine Herstellergarantie mit abweichender Laufzeit? Wie unterscheidest du beide Fälle in der Kommunikation? Wer ist im Garantiefall Ansprechpartner, du oder der Hersteller? |
| Fachwissen | Reparatur und Einsendeservice | Bietest du einen Reparaturservice an, und wie unterscheidet sich der Ablauf von einer normalen Retoure? Gibt es Kostenvoranschläge vor der Reparatur? Wie lange dauert eine typische Reparatur? |
| Fachwissen | Kompatibilität und technische Rückfragen | Welche Produkte werden am häufigsten zu Kompatibilität angefragt (z. B. Zubehör, Ersatzteile, Software-Versionen)? Wo sind technische Datenblätter hinterlegt? |
