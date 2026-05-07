# Testfallentwurf – Market Mate (GroceryMate)

**Projekt:** Market Mate Webshop  
**URL:** https://grocerymate.masterschool.com/  
**Autor:** Alexander Müller  
**Datum:** 06.05.2026  
**Version:** 1.0

---

## 1. Bewertungssystem für Produkte

**Testentwurfsverfahren:** Äquivalenzklassenbildung (EP), Grenzwertanalyse (BVA), Fehlerermessen (Error Guessing), Anwendungsfalltest (Use Case Testing)

### Testfälle:

1. **Anwendungsfalltest:**
   - **Testfall:** Überprüfen, ob ein eingeloggter Nutzer eine Bewertung abgeben kann.
     - **Eingabe:** Eingeloggter Nutzer wählt 4 Sterne und klickt auf „Bewertung abschicken".
     - **Erwartetes Ergebnis:** Bewertung wird erfolgreich gespeichert und die Durchschnittsbewertung auf der Produktkarte aktualisiert sich.

2. **Anwendungsfalltest:**
   - **Testfall:** Überprüfen, ob ein nicht eingeloggter Besucher eine Bewertung abgeben kann.
     - **Eingabe:** Nicht eingeloggter Nutzer versucht, das Bewertungsformular aufzurufen.
     - **Erwartetes Ergebnis:** Bewertungsformular ist nicht verfügbar oder ein Hinweis zum Einloggen wird angezeigt.

3. **Fehlerermessen:**
   - **Testfall:** Überprüfen, ob ein Nutzer dasselbe Produkt ein zweites Mal bewerten kann.
     - **Eingabe:** Eingeloggter Nutzer, der bereits eine Bewertung abgegeben hat, gibt erneut eine Bewertung (3 Sterne) ab.
     - **Erwartetes Ergebnis:** Die neue Bewertung überschreibt die vorherige; es existiert weiterhin nur eine Bewertung dieses Nutzers für das Produkt.

4. **Grenzwertanalyse:**
   - **Testfall:** Überprüfen des Systemverhaltens bei einem Feedback-Text mit genau 250 Zeichen.
     - **Eingabe:** Eingeloggter Nutzer gibt einen Text mit exakt 250 Zeichen ein und klickt auf „Abschicken".
     - **Erwartetes Ergebnis:** Bewertung wird erfolgreich gespeichert.

5. **Grenzwertanalyse:**
   - **Testfall:** Überprüfen des Systemverhaltens bei einem Feedback-Text mit 251 Zeichen.
     - **Eingabe:** Eingeloggter Nutzer gibt einen Text mit 251 Zeichen ein und klickt auf „Abschicken".
     - **Erwartetes Ergebnis:** Fehlermeldung wird angezeigt; Bewertung wird nicht gespeichert.

6. **Fehlerermessen:**
   - **Testfall:** Überprüfen des Systemverhaltens, wenn eine Bewertung ohne Sternauswahl abgeschickt wird.
     - **Eingabe:** Eingeloggter Nutzer lässt die Sternauswahl leer und klickt auf „Abschicken".
     - **Erwartetes Ergebnis:** Fehlermeldung „Bitte wähle eine Sternebewertung aus." Die Bewertung wird nicht gespeichert.

7. **Fehlerermessen:**
   - **Testfall:** Überprüfen, ob das Feedback-Feld leer gelassen werden kann.
     - **Eingabe:** Eingeloggter Nutzer wählt 5 Sterne, lässt das Textfeld leer und klickt auf „Abschicken".
     - **Erwartetes Ergebnis:** Bewertung wird erfolgreich gespeichert; kein Fehler wird angezeigt.

---

## 2. Altersverifikation für alkoholische Produkte

**Testentwurfsverfahren:** Anwendungsfalltest (Use Case Testing), Äquivalenzklassenbildung (EP), Fehlerermessen (Error Guessing)

### Testfälle:

1. **Anwendungsfalltest:**
   - **Testfall:** Überprüfen, ob das Altersverifikations-Modal beim Aufrufen der Alkohol-Kategorie erscheint.
     - **Eingabe:** Nutzer navigiert zur Produktkategorie „Alkohol".
     - **Erwartetes Ergebnis:** Modal erscheint mit der Frage, ob der Nutzer 18 Jahre oder älter ist.

2. **Äquivalenzklassenbildung:**
   - **Testfall:** Überprüfen, ob ein Nutzer nach Bestätigung der Volljährigkeit Zugang zur Alkohol-Kategorie erhält.
     - **Eingabe:** Nutzer klickt im Modal auf „Ja, ich bin 18 oder älter."
     - **Erwartetes Ergebnis:** Modal schließt sich; Nutzer erhält Zugang zur Alkohol-Kategorie und sieht die Produkte.

3. **Äquivalenzklassenbildung:**
   - **Testfall:** Überprüfen, ob ein Nutzer nach Ablehnung der Altersverifikation Zugang zur Alkohol-Kategorie erhält.
     - **Eingabe:** Nutzer klickt im Modal auf „Nein, ich bin unter 18."
     - **Erwartetes Ergebnis:** Nutzer wird zurück zur allgemeinen Produktübersicht weitergeleitet; kein Zugang zur Alkohol-Kategorie.

4. **Anwendungsfalltest:**
   - **Testfall:** Überprüfen, ob das Modal innerhalb derselben Session erneut erscheint, nachdem die Verifikation bereits bestätigt wurde.
     - **Eingabe:** Nutzer hat die Altersverifikation bereits bestätigt und navigiert erneut zur Alkohol-Kategorie.
     - **Erwartetes Ergebnis:** Modal erscheint nicht erneut; Nutzer erhält direkt Zugang.

5. **Fehlerermessen:**
   - **Testfall:** Überprüfen, ob ein Nutzer Zugang zur Alkohol-Kategorie erhält, wenn er das Modal ohne Auswahl schließt (z. B. per ESC oder X).
     - **Eingabe:** Nutzer schließt das Modal ohne Auswahl.
     - **Erwartetes Ergebnis:** Nutzer erhält keinen Zugang zur Alkohol-Kategorie; er wird zur allgemeinen Produktübersicht zurückgeleitet.

6. **Fehlerermessen:**
   - **Testfall:** Überprüfen, ob die Alkohol-Kategorie nach Ablehnung über direkte URL-Eingabe erreichbar ist.
     - **Eingabe:** Nutzer hat das Modal abgelehnt und versucht, die Alkohol-Kategorie über die direkte URL aufzurufen.
     - **Erwartetes Ergebnis:** Modal erscheint erneut; ohne erneute Bestätigung wird kein Zugang gewährt.

---

## 3. Versandkostenregel

**Testentwurfsverfahren:** Grenzwertanalyse (BVA), Äquivalenzklassenbildung (EP), Fehlerermessen (Error Guessing)

### Testfälle:

1. **Äquivalenzklassenbildung:**
   - **Testfall:** Überprüfen der Versandkostenberechnung bei einem Subtotal unter €20,00.
     - **Eingabe:** Warenkorb mit Produkten im Gesamtwert von €10,00.
     - **Erwartetes Ergebnis:** Versandkosten von €5,00 werden angezeigt; Gesamtbetrag = €15,00.

2. **Äquivalenzklassenbildung:**
   - **Testfall:** Überprüfen der Versandkostenberechnung bei einem Subtotal über €20,00.
     - **Eingabe:** Warenkorb mit Produkten im Gesamtwert von €30,00.
     - **Erwartetes Ergebnis:** Versandkosten = €0,00; Gesamtbetrag = €30,00.

3. **Grenzwertanalyse:**
   - **Testfall:** Überprüfen der Versandkostenberechnung bei einem Subtotal von genau €20,00.
     - **Eingabe:** Warenkorb mit Produkten im Gesamtwert von €20,00.
     - **Erwartetes Ergebnis:** Versandkosten = €0,00 (inklusiver Grenzwert); Gesamtbetrag = €20,00.

4. **Grenzwertanalyse:**
   - **Testfall:** Überprüfen der Versandkostenberechnung bei einem Subtotal von €19,99.
     - **Eingabe:** Warenkorb mit Produkten im Gesamtwert von €19,99.
     - **Erwartetes Ergebnis:** Versandkosten = €5,00; Gesamtbetrag = €24,99.

5. **Grenzwertanalyse:**
   - **Testfall:** Überprüfen der Versandkostenberechnung bei einem Subtotal von €20,01.
     - **Eingabe:** Warenkorb mit Produkten im Gesamtwert von €20,01.
     - **Erwartetes Ergebnis:** Versandkosten = €0,00; Gesamtbetrag = €20,01.

6. **Fehlerermessen:**
   - **Testfall:** Überprüfen, ob die Versandkostenanzeige sich dynamisch aktualisiert, wenn ein Produkt entfernt wird und der Subtotal unter €20,00 fällt.
     - **Eingabe:** Warenkorb mit Subtotal €25,00; Nutzer entfernt ein Produkt, sodass der Subtotal auf €15,00 sinkt.
     - **Erwartetes Ergebnis:** Versandkosten wechseln sofort von €0,00 auf €5,00 ohne Seitenneuladung.

---

## Automatisierungspotenzial

| # | Testfall | Automatisieren? | Begründung |
|---|---|---|---|
| 1.1 | Bewertung abgeben (eingeloggt) | ✅ Ja | Happy-Path-Test; mit Selenium Login + Formular + Ergebnis prüfen; wichtiger Regressionstest nach jedem Deployment |
| 1.2 | Bewertung abgeben (nicht eingeloggt) | ✅ Ja | Selenium prüft ob das Bewertungsformular im DOM vorhanden ist oder nicht; klarer Regressionstest für Zugriffsschutz |
| 1.4 | Feedback: genau 250 Zeichen | ✅ Ja | `send_keys` mit exakt 250 Zeichen, dann Submit; präzise reproduzierbar mit pytest |
| 1.5 | Feedback: 251 Zeichen | ✅ Ja | Oberer Grenzwert; zusammen mit 1.4 als Testsuite in pytest automatisierbar |
| 2.1 | Modal erscheint beim Kategorieaufruf | ✅ Ja | Selenium `WebDriverWait` wartet zuverlässig auf Modal-Erscheinen im DOM; stabil automatisierbar |
| 2.5 | Modal per ESC schließen | ✅ Ja | `send_keys(Keys.ESCAPE)` ist in Selenium eine einzelne Zeile; browserübergreifend stabil |
| 2.6 | Zugang per direkter URL nach Ablehnung | ❌ Nein | Selenium prüft nur das Frontend; der Test soll validieren ob der Schutz auch serverseitig greift – das erfordert manuelles Urteilsvermögen |
| 3.3 | Versandkosten bei €20,00 | ✅ Ja | Kritischer Grenzwert; DOM-Wert nach Warenkorbbestückung prüfen; regressionsrelevant nach jedem Release |
| 3.4 | Versandkosten bei €19,99 | ✅ Ja | Unterer Grenzwert; zusammen mit 3.3 und 3.5 als Testsuite in pytest automatisierbar |
| 3.5 | Versandkosten bei €20,01 | ✅ Ja | Oberer Grenzwert; gleiche Begründung wie 3.4 |
| 3.6 | Dynamische Aktualisierung der Versandkosten | ✅ Ja | Selenium prüft ob sich der angezeigte Wert ohne Seitenneuladung ändert; Automatisierung ist hier zuverlässiger als manuelle Beobachtung |
