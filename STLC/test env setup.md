# Testumgebung – Market Mate (GroceryMate)

**Projekt:** Market Mate Webshop  
**URL:** https://grocerymate.masterschool.com/  
**Autor:** Alexander Müller  
**Datum:** 21.05.2026  
**Version:** 1.0

---

## 1. Umgebung

| Bereich | Einrichtung |
|---|---|
| Testinstanz | Öffentliche Instanz https://grocerymate.masterschool.com/ (produktionsnah) |
| Umgebungsstufen | Keine getrennten DEV/TEST/ACC-Umgebungen verfügbar – alle Tests laufen in der öffentlichen Instanz |
| Zugriff | Über den Browser, keine Installation nötig |

---

## 2. Hardware und Software

| Komponente | Version / Details |
|---|---|
| Gerät | Laptop |
| Betriebssystem | Windows 11 |
| Browser (primär) | Google Chrome |
| Browser (sekundär) | Mozilla Firefox |
| Werkzeuge | Browser DevTools (Netzwerk, Konsole, Elemente), Screenshot-Tool |
| Dokumentation | GitHub (Markdown-Dokumente, Issues für Fehlerberichte) |

---

## 3. Testkonten

| Konto | Zweck |
|---|---|
| Registrierter Nutzer mit abgeschlossenem Kauf | Bewertungen abgeben und bearbeiten, Warenkorb und Checkout |
| Kein Login (Gastbesucher) | Prüfen, dass Gäste keine Bewertung abgeben können |

Zugangsdaten werden aus Sicherheitsgründen nicht im Repository abgelegt.

---

## 4. Testdaten

**Bewertungssystem**

| Testdaten | Wert |
|---|---|
| Testprodukt | `/product/66b3a57b3fd5048eacb4798f` |
| Feedback-Text, gültiger Grenzwert | genau 500 Zeichen |
| Feedback-Text, ungültiger Grenzwert | 501 Zeichen |

**Altersverifikation** (Stichtag der Durchführung: 21.05.2026)

| Fall | Geburtsdatum |
|---|---|
| Einen Tag zu jung | 22.05.2008 |
| Genau 18 Jahre | 21.05.2008 |
| Einen Tag älter als 18 | 20.05.2008 |
| Alkoholisches Produkt für den URL-Test | `/product/66b3a57b3fd5048eacb47a76` |

Die Geburtsdaten hängen vom Testtag ab und müssen bei jeder neuen Durchführung neu berechnet werden.

**Versandkosten**

| Subtotal | Warenkorb |
|---|---|
| €10,00 | 5× Gala Apples à €2,00 |
| €19,99 | 8× Gala Apples + 1× Birchwood Quarter Pounders (€2,49) + 1× Tenderstem Broccoli (€1,50) |
| €20,00 | 10× Gala Apples |
| €20,01 | 9× Gala Apples + 1× Taste of Microwaveable Rice (€0,42) + 1× Orlando Meaty Strips (€0,49) + 1× Easy Peelers (€1,10) |
| €22,19 → €18,00 | 9× Gala Apples + 1× Birchwood British Beef Mince (€4,19), danach Beef Mince entfernen |
| €30,00 | 15× Gala Apples |

Die Preise gelten zum Zeitpunkt der Durchführung. Ändern sich Preise im Shop, müssen die Warenkörbe neu zusammengestellt werden.

---

## 5. Vorbereitung vor jedem Testlauf

1. Neue Browser-Session starten (Cache und Cookies leeren), damit keine frühere Altersverifikation übernommen wird.
2. Warenkorb des Testkontos leeren.
3. Preise der Testprodukte kurz prüfen.
4. Prüfen, ob die Testinstanz erreichbar ist. Ist sie es nicht, gilt das Aussetzungskriterium aus dem Testplan.

---

## 6. Einschränkungen

- Keine eigene Testumgebung: Andere Nutzer können gleichzeitig Daten verändern, z. B. die Durchschnittsbewertung eines Produkts.
- Keine Zahlungen mit echten Zahlungsmitteln (außerhalb des Testumfangs).
- Keine Lasttests (außerhalb des Testumfangs).
