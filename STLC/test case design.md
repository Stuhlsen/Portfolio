# Testfallentwurf – Market Mate (GroceryMate)

**Projekt:** Market Mate Webshop  
**URL:** https://grocerymate.masterschool.com/  
**Autor:** Alexander Müller  
**Datum:** 06.05.2026  
**Version:** 1.1

---

## 1. Bewertungssystem für Produkte

**Testentwurfsverfahren:** Anwendungsfalltest (Use Case Testing), Fehlerermessen (Error Guessing), Grenzwertanalyse (BVA)

### Testfälle:

1. **Anwendungsfalltest:**
   - **Vorbedingung:** Nutzer ist eingeloggt und hat das Produkt zuvor gekauft.
   - **Testfall:** Überprüfen, ob ein eingeloggter Nutzer eine Bewertung abgeben kann.
     - **Eingabe:** Nutzer wählt 4 Sterne und klickt auf „Bewertung abschicken".
     - **Erwartetes Ergebnis:** Bewertung wird erfolgreich gespeichert und die Durchschnittsbewertung auf der Produktkarte aktualisiert sich.

2. **Anwendungsfalltest:**
   - **Vorbedingung:** Nutzer ist nicht eingeloggt.
   - **Testfall:** Überprüfen, ob ein nicht eingeloggter Besucher eine Bewertung abgeben kann.
     - **Eingabe:** Nicht eingeloggter Nutzer versucht, das Bewertungsformular aufzurufen.
     - **Erwartetes Ergebnis:** Bewertungsformular ist nicht verfügbar oder ein Hinweis zum Einloggen wird angezeigt.

3. **Anwendungsfalltest:**
   - **Vorbedingung:** Nutzer ist eingeloggt, hat das Produkt gekauft und bereits eine Bewertung abgegeben.
   - **Testfall:** Überprüfen, ob ein Nutzer eine bestehende Bewertung bearbeiten kann und sich der Durchschnitt aktualisiert.
     - **Eingabe:** Nutzer klickt auf „Edit", ändert die Bewertung auf 3 Sterne und speichert.
     - **Erwartetes Ergebnis:** Die Bewertung wird aktualisiert; die Durchschnittsbewertung auf der Produktkarte ändert sich entsprechend.

4. **Grenzwertanalyse:**
   - **Vorbedingung:** Nutzer ist eingeloggt und hat das Produkt gekauft.
   - **Testfall:** Überprüfen des Systemverhaltens bei einem Feedback-Text mit genau 500 Zeichen.
     - **Eingabe:** Nutzer gibt einen Text mit exakt 500 Zeichen ein und klickt auf „Abschicken".
     - **Erwartetes Ergebnis:** Bewertung wird erfolgreich gespeichert.

5. **Grenzwertanalyse:**
   - **Vorbedingung:** Nutzer ist eingeloggt und hat das Produkt gekauft.
   - **Testfall:** Überprüfen des Systemverhaltens bei einem Feedback-Text mit 501 Zeichen.
     - **Eingabe:** Nutzer gibt einen Text mit 501 Zeichen ein und klickt auf „Abschicken".
     - **Erwartetes Ergebnis:** Fehlermeldung wird angezeigt; Bewertung wird nicht gespeichert.

6. **Fehlerermessen:**
   - **Vorbedingung:** Nutzer ist eingeloggt und hat das Produkt gekauft.
   - **Testfall:** Überprüfen des Systemverhaltens, wenn eine Bewertung ohne Sternauswahl abgeschickt wird.
     - **Eingabe:** Nutzer lässt die Sternauswahl leer und klickt auf „Abschicken".
     - **Erwartetes Ergebnis:** Fehlermeldung „Bitte wähle eine Sternebewertung aus." Die Bewertung wird nicht gespeichert.

---

## 2. Altersverifikation für alkoholische Produkte

**Testentwurfsverfahren:** Anwendungsfalltest (Use Case Testing), Grenzwertanalyse (BVA), Äquivalenzklassenbildung (EP), Fehlerermessen (Error Guessing)

**Priorität:** Hoch — das Hauptziel ist sicherzustellen, dass Minderjährige keinen Zugang zu alkoholischen Produkten erhalten.

### Testfälle:

1. **Anwendungsfalltest:**
   - **Testfall:** Überprüfen, ob das Altersverifikations-Modal beim Aufrufen der Alkohol-Kategorie erscheint.
     - **Eingabe:** Nutzer navigiert zur Produktkategorie „Alkohol".
     - **Erwartetes Ergebnis:** Modal erscheint mit einem Eingabefeld für das Geburtsdatum.

2. **Grenzwertanalyse + Äquivalenzklassenbildung:**
   - **Testfall:** Überprüfen, ob ein Nutzer knapp unter 18 Jahren Zugang zur Alkohol-Kategorie erhält.
     - **Eingabe:** Geburtsdatum = heute − 18 Jahre + 1 Tag (einen Tag zu jung).
     - **Erwartetes Ergebnis:** Zugang verweigert; Fehlermeldung wird angezeigt.

3. **Grenzwertanalyse:**
   - **Testfall:** Überprüfen, ob ein Nutzer an der Altersgrenze von genau 18 Jahren und einen Tag darüber Zugang zur Alkohol-Kategorie erhält.
     - **Eingabe 1:** Geburtsdatum = heute − 18 Jahre (genau 18 Jahre alt) → **Erwartetes Ergebnis:** Zugang zur Alkohol-Kategorie wird gewährt.
     - **Eingabe 2:** Geburtsdatum = heute − 18 Jahre − 1 Tag (einen Tag älter als 18) → **Erwartetes Ergebnis:** Zugang zur Alkohol-Kategorie wird gewährt.

4. **Anwendungsfalltest:**
   - **Testfall:** Überprüfen, ob das Modal innerhalb derselben Session erneut erscheint, nachdem die Verifikation bereits bestätigt wurde.
     - **Eingabe:** Nutzer hat die Altersverifikation bereits bestätigt und navigiert erneut zur Alkohol-Kategorie.
     - **Erwartetes Ergebnis:** Modal erscheint nicht erneut; Nutzer erhält direkt Zugang.

5. **Fehlerermessen:**
   - **Testfall:** Überprüfen, ob ein Nutzer Zugang zur Alkohol-Kategorie erhält, wenn er das Modal ohne Datumseingabe schließt (z. B. per ESC oder X).
     - **Eingabe:** Nutzer schließt das Modal ohne Eingabe.
     - **Erwartetes Ergebnis:** Nutzer erhält keinen Zugang zur Alkohol-Kategorie; er wird zur allgemeinen Produktübersicht zurückgeleitet.

6. **Fehlerermessen:**
   - **Testfall:** Überprüfen, ob die Alkohol-Kategorie nach verweigertem Zugang über direkte URL-Eingabe erreichbar ist.
     - **Eingabe:** Nutzer hat das Modal mit einem Alter unter 18 ausgefüllt und versucht anschließend, die Alkohol-Kategorie über die direkte URL aufzurufen.
     - **Erwartetes Ergebnis:** Modal erscheint erneut; ohne gültige Altersverifikation wird kein Zugang gewährt.

---

## 3. Versandkostenregel

**Testentwurfsverfahren:** Äquivalenzklassenbildung (EP), Grenzwertanalyse (BVA), Fehlerermessen (Error Guessing)

**Hinweis:** Vor der Testdurchführung muss sichergestellt werden, dass mit den vorhandenen Produkten im Shop ein Subtotal von exakt €19,99 erreichbar ist. Falls nicht, wird der nächstmögliche Wert dokumentiert.

### Testfälle:

1. **Äquivalenzklassenbildung:**
   - **Testfall:** Überprüfen der Versandkostenberechnung bei einem Subtotal unter €20,00.
     - **Eingabe:** Warenkorb mit Produkten im Gesamtwert von ca. €10,00.
     - **Erwartetes Ergebnis:** Versandkosten von €5,00 werden angezeigt.

2. **Äquivalenzklassenbildung:**
   - **Testfall:** Überprüfen der Versandkostenberechnung bei einem Subtotal über €20,00.
     - **Eingabe:** Warenkorb mit Produkten im Gesamtwert von ca. €30,00.
     - **Erwartetes Ergebnis:** Versandkosten = €0,00.

3. **Grenzwertanalyse:**
   - **Testfall:** Überprüfen der Versandkostenberechnung bei einem Subtotal von €19,99.
     - **Eingabe:** Warenkorb mit Produkten im Gesamtwert von €19,99.
     - **Erwartetes Ergebnis:** Versandkosten = €5,00; Gesamtbetrag = €24,99.

4. **Grenzwertanalyse:**
   - **Testfall:** Überprüfen der Versandkostenberechnung bei einem Subtotal von genau €20,00.
     - **Eingabe:** Warenkorb mit Produkten im Gesamtwert von €20,00.
     - **Erwartetes Ergebnis:** Versandkosten = €0,00; Gesamtbetrag = €20,00.

5. **Grenzwertanalyse:**
   - **Testfall:** Überprüfen der Versandkostenberechnung bei einem Subtotal von €20,01.
     - **Eingabe:** Warenkorb mit Produkten im Gesamtwert von €20,01.
     - **Erwartetes Ergebnis:** Versandkosten = €0,00; Gesamtbetrag = €20,01.

6. **Fehlerermessen:**
   - **Testfall:** Überprüfen, ob die Versandkostenanzeige sich dynamisch aktualisiert, wenn ein Produkt entfernt wird und der Subtotal unter €20,00 fällt.
     - **Eingabe:** Warenkorb mit Subtotal über €20,00; Nutzer entfernt ein Produkt sodass der Subtotal unter €20,00 sinkt.
     - **Erwartetes Ergebnis:** Versandkosten wechseln sofort von €0,00 auf €5,00 ohne Seitenneuladung.

---

## Automatisierungspotenzial

| # | Testfall | Automatisieren? | Begründung |
|---|---|---|---|
| 1.1 | Bewertung abgeben (eingeloggt) | ✅ Ja | Klar definierter Ablauf mit Login, Formulareingabe und Ergebnisprüfung; wichtiger Regressionstest nach jeder Änderung |
| 1.2 | Bewertung abgeben (nicht eingeloggt) | ✅ Ja | Selenium prüft ob das Bewertungsformular auf der Seite angezeigt wird; klarer Regressionstest für Zugriffsschutz |
| 1.4 | Feedback: 500 Zeichen (Grenzwert gültig) | ✅ Ja | Exakt definierte Texteingabe; wiederholbar und präzise automatisierbar |
| 1.5 | Feedback: 501 Zeichen (Grenzwert ungültig) | ✅ Ja | Exakt definierte Texteingabe; zusammen mit 1.4 als Testsuite automatisierbar |
| 2.1 | Modal erscheint beim Kategorieaufruf | ✅ Ja | Selenium kann zuverlässig prüfen ob das Modal auf der Seite erscheint |
| 2.2 | Grenzwertanalyse Geburtsdatum (zu jung) | ✅ Ja | Exakt definierte Datumseingabe; wiederholbar automatisierbar |
| 2.3 | Grenzwertanalyse Geburtsdatum (genau 18J / 18J−1T) | ✅ Ja | Zwei exakt definierte Datumseingaben; wiederholbar automatisierbar |
| 2.5 | Modal per ESC schließen (ohne Eingabe) | ✅ Ja | Selenium kann Tastatureingaben simulieren; einfach und stabil automatisierbar |
| 2.6 | Zugang per direkter URL nach verweigertem Zugang | ✅ Ja | Selenium navigiert direkt zur URL und prüft ob das Modal erneut erscheint; vollständig automatisierbar |
| 3.3 | Versandkosten bei €19,99 | ✅ Ja | Exakt definierter Warenkorbwert; Selenium prüft den angezeigten Betrag |
| 3.4 | Versandkosten bei €20,00 | ✅ Ja | Kritischer Grenzwert; regressionsrelevant nach jeder Änderung |
| 3.5 | Versandkosten bei €20,01 | ✅ Ja | Oberer Grenzwert; zusammen mit 3.3 und 3.4 als Testsuite automatisierbar |
| 3.6 | Dynamische Aktualisierung der Versandkosten | ✅ Ja | Selenium kann prüfen ob sich der angezeigte Betrag sofort nach einer Warenkorbänderung aktualisiert |
