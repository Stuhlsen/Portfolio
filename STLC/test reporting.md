# Testabschlussbericht – Market Mate (GroceryMate)

**Projekt:** Market Mate Webshop  
**URL:** https://grocerymate.masterschool.com/  
**Autor:** Alexander Müller  
**Datum:** 21.05.2026  
**Version:** 1.0  
**Testzeitraum:** 21.04.2026 – 21.05.2026

---

## 1. Zusammenfassung

Getestet wurden drei neue Features des Webshops: das Bewertungssystem, die Altersverifikation für alkoholische Produkte und die neue Versandkostenregel.

Von 19 durchgeführten Szenarien waren 14 erfolgreich. Es wurden **5 Fehler** gefunden und als GitHub Issues gemeldet.

**Empfehlung: keine Freigabe.** Die Abnahmekriterien aus dem Testplan sind nicht erfüllt. Vor allem kann die Altersverifikation über eine direkte Produkt-URL umgangen werden (#3).

---

## 2. Testergebnisse

| Feature | Szenarien | OK | NOK | Fehler |
|---|---|---|---|---|
| Bewertungssystem | 6 | 4 | 2 | #4, #5 |
| Altersverifikation | 7 | 5 | 2 | #2, #3 |
| Versandkostenregel | 6 | 5 | 1 | #1 |
| **Gesamt** | **19** | **14** | **5** | |

Bestehensquote: 14 von 19 = **73,7 %**

---

## 3. Gefundene Fehler

| Issue | Feature | Beschreibung | Schweregrad |
|---|---|---|---|
| [#3](https://github.com/Stuhlsen/Portfolio/issues/3) | Altersverifikation | Alkoholische Produkte sind über die direkte Produkt-URL ohne Altersverifikation erreichbar | Kritisch |
| [#2](https://github.com/Stuhlsen/Portfolio/issues/2) | Altersverifikation | Das Modal erscheint schon beim Aufruf des Shops statt beim Öffnen der Alkohol-Kategorie | Mittel |
| [#1](https://github.com/Stuhlsen/Portfolio/issues/1) | Versandkosten | Versandkosten aktualisieren sich nach dem Entfernen eines Produkts nicht ohne Neuladen der Seite | Hoch |
| [#4](https://github.com/Stuhlsen/Portfolio/issues/4) | Bewertungssystem | Durchschnittsbewertung aktualisiert sich nach dem Bearbeiten einer Bewertung nicht | Mittel |
| [#5](https://github.com/Stuhlsen/Portfolio/issues/5) | Bewertungssystem | Zeichenzähler zeigt 500/500 in Rot, obwohl Speichern erlaubt ist | Niedrig |

**Begründung der Schweregrade**
- **Kritisch (#3):** Minderjährige können alkoholische Produkte aufrufen. Damit verfehlt das Feature sein Hauptziel, ein rechtliches Risiko für den Shop.
- **Hoch (#1):** Der Kunde sieht im Checkout einen falschen Preis.
- **Mittel (#2, #4):** Funktion weicht von der Anforderung ab, aber kein Schaden für den Kunden und kein falscher Preis.
- **Niedrig (#5):** Rein optischer Fehler, die Funktion selbst arbeitet korrekt.

---

## 4. Abnahmekriterien

| Kriterium (aus dem Testplan) | Ergebnis | Erfüllt? |
|---|---|---|
| Mindestens 95 % der geplanten Testfälle ausgeführt | 18 von 18 Testfällen ausgeführt (100 %) | ✅ |
| Mindestens 90 % der ausgeführten Testfälle bestanden | 73,7 % bestanden | ❌ |
| Keine offenen Fehler mit Schweregrad „Kritisch" oder „Hoch" | #3 (Kritisch) und #1 (Hoch) offen | ❌ |
| Alle drei neuen Features vollständig getestet und freigegeben | Vollständig getestet, aber nicht freigegeben | ❌ |

---

## 5. Weitere Beobachtungen

- **Szenario 2.5 (Modal ohne Eingabe schließen):** Laut Anforderung soll der Nutzer zur Produktübersicht zurückgeleitet werden. Tatsächlich lässt sich das Modal gar nicht schließen. Der Zugang zu Alkohol bleibt gesperrt, das Sicherheitsziel ist also erreicht. Das Verhalten weicht aber von der Anforderung ab und sollte mit dem Product Owner geklärt werden.
- **Szenario 1.5 (501 Zeichen):** Das Eingabefeld blockiert bei 500 Zeichen. Die in der Anforderung beschriebene Fehlermeldung wird darum nie angezeigt. Das Ziel der Anforderung ist trotzdem erfüllt.
- **Zeitplan:** Die Durchführung fand am 21.05.2026 statt, später als im Testplan geplant (01.–05.05.2026).

---

## 6. Empfehlungen

1. **#3 zuerst beheben:** Die Altersprüfung muss auch beim direkten Aufruf einer Produktseite greifen, nicht nur auf der Kategorieseite.
2. **#1 beheben**, damit im Checkout immer der richtige Preis steht.
3. Nach den Fixes einen **Re-Test** der betroffenen Szenarien (1.3, 1.4, 2.1, 2.6, 3.6) und einen **Regressionstest** von Login, Warenkorb und Checkout durchführen.
4. Die Abweichung bei Szenario 2.5 mit dem Product Owner klären.
5. Die als automatisierbar bewerteten Testfälle (s. `test case design.md`) als Regressionssuite automatisieren, vor allem die Grenzwerttests für Versandkosten und Alter.

