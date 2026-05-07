# Testfallentwurf – Market Mate (GroceryMate)

**Projekt:** Market Mate Webshop  
**URL:** https://grocerymate.masterschool.com/  
**Autor:** Alexander Müller  
**Datum:** 06.05.2026  
**Version:** 1.0

---

## 1. Bewertungssystem für Produkte

**Testentwurfsverfahren:** Anwendungsfalltest (Use Case Testing), Fehlerermessen (Error Guessing), Grenzwertanalyse (BVA)

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
   - **Testfall:** Überprüfen des Systemverhaltens bei Feedback-Texten an der Zeichengrenze.
     - **Eingabe 1:** Text mit 499 Zeichen → **Erwartetes Ergebnis:** Bewertung wird erfolgreich gespeichert.
     - **Eingabe 2:** Text mit 500 Zeichen → **Erwartetes Ergebnis:** Bewertung wird erfolgreich gespeichert.
     - **Eingabe 3:** Text mit 501 Zeichen → **Erwartetes Ergebnis:** Fehlermeldung wird angezeigt; Bewertung wird nicht gespeichert.

5. **Fehlerermessen:**
   - **Testfall:** Überprüfen des Systemverhaltens, wenn eine Bewertung ohne Sternauswahl abgeschickt wird.
     - **Eingabe:** Eingeloggter Nutzer lässt die Sternauswahl leer und klickt auf „Abschicken".
     - **Erwartetes Ergebnis:** Fehlermeldung „Bitte wähle eine Sternebewertung aus." Die Bewertung wird nicht gespeichert.

6. **Fehlerermessen:**
   - **Testfall:** Überprüfen, ob das Feedback-Feld leer gelassen werden kann.
     - **Eingabe:** Eingeloggter Nutzer wählt 5 Sterne, lässt das Textfeld leer und klickt auf „Abschicken".
     - **Erwartetes Ergebnis:** Bewertung wird erfolgreich gespeichert; kein Fehler wird angezeigt.

---

## 2. Altersverifikation für alkoholische Produkte

**Testentwurfsverfahren:** Anwendungsfalltest (Use Case Testing), Grenzwertanalyse (BVA), Äquivalenzklassenbildung (EP), Fehlerermessen (Error Guessing)

### Testfälle:

1. **Anwendungsfalltest:**
   - **Testfall:** Überprüfen, ob das Altersverifikations-Modal beim Aufrufen der Alkohol-Kategorie erscheint.
     - **Eingabe:** Nutzer navigiert zur Produktkategorie „Alkohol".
     - **Erwartetes Ergebnis:** Modal erscheint mit einem Eingabefeld für das Geburtsdatum.

2. **Grenzwertanalyse:**
   - **Testfall:** Überprüfen, ob ein Nutzer an der Altersgrenze von 18 Jahren Zugang zur Alkohol-Kategorie erhält.
     - **Eingabe 1:** Geburtsdatum = heute − 18 Jahre + 1 Tag (einen Tag zu jung) → **Erwartetes Ergebnis:** Zugang verweigert; Fehlermeldung wird angezeigt.
     - **Eingabe 2:** Geburtsdatum = heute − 18 Jahre (genau 18 Jahre alt) → **Erwartetes Ergebnis:** Zugang zur Alkohol-Kategorie wird gewährt.
     - **Eingabe 3:** Geburtsdatum = heute − 18 Jahre − 1 Tag (einen Tag älter als 18) → **Erwartetes Ergebnis:** Zugang zur Alkohol-Kategorie wird gewährt.

3. **Äquivalenzklassenbildung:**
   - **Testfall:** Überprüfen, ob ein Nutzer mit einem Alter deutlich unter 18 Jahren Zugang zur Alkohol-Kategorie erhält.
     - **Eingabe:** Geburtsdatum = heute − 15 Jahre.
     - **Erwartetes Ergebnis:** Zugang verweigert; Nutzer wird zur allgemeinen Produktübersicht weitergeleitet.

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
   - **Testfall:** Überprüfen der Versandkostenberechnung an der Grenze von €20,00.
     - **Eingabe 1:** Subtotal €19,99 → **Erwartetes Ergebnis:** Versandkosten = €5,00; Gesamtbetrag = €24,99.
     - **Eingabe 2:** Subtotal €20,00 → **Erwartetes Ergebnis:** Versandkosten = €0,00; Gesamtbetrag = €20,00.
     - **Eingabe 3:** Subtotal €20,01 → **Erwartetes Ergebnis:** Versandkosten = €0,00; Gesamtbetrag = €20,01.

4. **Fehlerermessen:**
   - **Testfall:** Überprüfen, ob die Versandkostenanzeige sich dynamisch aktualisiert, wenn ein Produkt entfernt wird und der Subtotal unter €20,00 fällt.
     - **Eingabe:** Warenkorb mit Subtotal €25,00; Nutzer entfernt ein Produkt, sodass der Subtotal auf €15,00 sinkt.
     - **Erwartetes Ergebnis:** Versandkosten wechseln sofort von €0,00 auf €5,00 ohne Seitenneuladung.

---

## Automatisierungspotenzial

| # | Testfall | Automatisieren? | Begründung |
|---|---|---|---|
| 1.1 | Bewertung abgeben (eingeloggt) | ✅ Ja | Happy-Path-Test; mit Selenium Login + Formular + Ergebnis prüfen; wichtiger Regressionstest nach jedem Deployment |
| 1.2 | Bewertung abgeben (nicht eingeloggt) | ✅ Ja | Selenium prüft ob das Bewertungsformular im DOM vorhanden ist oder nicht; klarer Regressionstest für Zugriffsschutz |
| 1.4 | Feedback: Grenzwertanalyse (499/500/501 Zeichen) | ✅ Ja | `send_keys` mit drei definierten Eingaben in einer pytest Testsuite; präzise und vollständig automatisierbar |
| 2.1 | Modal erscheint beim Kategorieaufruf | ✅ Ja | Selenium `WebDriverWait` wartet zuverlässig auf Modal-Erscheinen im DOM |
| 2.2 | Grenzwertanalyse Geburtsdatum (−18J+1T / −18J / −18J−1T) | ✅ Ja | Drei definierte Datumseingaben in einer pytest Testsuite; präzise reproduzierbar |
| 2.5 | Modal per ESC schließen (ohne Eingabe) | ✅ Ja | `send_keys(Keys.ESCAPE)` ist in Selenium eine einzelne Zeile; browserübergreifend stabil |
| 2.6 | Zugang per direkter URL nach verweigertem Zugang | ❌ Nein | Selenium prüft nur das Frontend; der Test soll validieren ob der Schutz auch serverseitig greift – das erfordert manuelles Urteilsvermögen |
| 3.3 | Versandkosten Grenzwertanalyse (€19,99/€20,00/€20,01) | ✅ Ja | Drei Eingaben in einer pytest Testsuite; DOM-Wert nach Warenkorbbestückung prüfen; regressionsrelevant nach jedem Release |
| 3.4 | Dynamische Aktualisierung der Versandkosten | ✅ Ja | Selenium prüft ob sich der angezeigte Wert ohne Seitenneuladung ändert; Automatisierung ist hier zuverlässiger als manuelle Beobachtung |
