# Testplan – Market Mate (GroceryMate)

**Projekt:** Market Mate Webshop  
**URL:** https://grocerymate.masterschool.com/  
**Autor:** Alexander Müller  
**Datum:** 28.04.2026  
**Version:** 1.0

---

## 1. Produktanalyse

**Zielsetzung:**  
Das Hauptziel ist die Erweiterung des bestehenden Webshops um drei neue Funktionen sowie die Sicherstellung, dass vorhandene Features durch diese Änderungen nicht beeinträchtigt werden.

**Zielgruppe:**  
Der Webshop richtet sich an Privatkunden ab 18 Jahren, die online Lebensmittel einkaufen möchten. Dazu zählen registrierte Nutzer, die Produkte bewerten oder alkoholische Produkte kaufen möchten, sowie Gastbesucher, die den Shop ohne Konto durchsuchen.

**Hardware- und Software-Spezifikationen:**

- **Hardwareanforderungen:**
  - Geräte: PCs, Laptops, Smartphones, Tablets
  - Mindestanforderungen: 4 GB RAM, stabile Internetverbindung
- **Softwareanforderungen:**
  - Betriebssysteme: Windows, macOS, Android, iOS
  - Browser: Chrome, Firefox, Safari, Edge
  - Abhängigkeiten: Backend-Dienste, Zahlungsschnittstellen, Session-Management

**Funktionalitäten:**

- Registrierung und Login
- Produktsuche mit Sortier- und Filterfunktion
- Produkte zu Favoriten hinzufügen
- Produkte in den Warenkorb legen
- Checkout mit Adress- und Zahlungseingabe
- **Neu:** Bewertungssystem für Produkte (5 Sterne + schriftliches Feedback)
- **Neu:** Altersverifikation für alkoholische Produkte (Modal, 18+)
- **Neu:** Geänderte Versandkostenregel (kostenlos ab €20,00, sonst €5,00)

---

## 2. Teststrategie entwerfen

**Testumfang:**

- **Im Umfang enthalten:**
  - Bewertungssystem: Abgabe, Validierung, Durchschnittsanzeige
  - Altersverifikation: Modal-Verhalten, Zugangskontrolle, Session-Persistenz
  - Versandkostenberechnung: Grenzwerte, dynamische Aktualisierung im Warenkorb
  - Regressionstests: Login, Produktsuche, Warenkorb, Checkout

- **Außerhalb des Umfangs:**
  - Backend-Datenbankoperationen ohne UI-Einfluss
  - Zahlungsabwicklung mit echten Zahlungsmitteln
  - Performance unter hoher Last (außerhalb dieses Projekts)

**Testarten:**

- Funktionstests
- Negative Tests
- Boundary Value Tests (Grenzwertanalyse)
- Regressionstests
- Usability-Tests (explorativ)

**Risiken und Probleme:**

- **Keine separate Testumgebung verfügbar**
  - Maßnahme: Tests in der öffentlichen Instanz, keine echten Bestellungen abschließen
- **Fehlende oder unvollständige Anforderungen**
  - Maßnahme: Offene Punkte vorab mit dem Product Owner klären
- **Ressourcenengpass (Einzeltester)**
  - Maßnahme: Priorisierung der Testfälle nach Risiko und Priorität

**Testlogistik:**

- QA Engineer (Funktion & Regression): Alexander Müller
- Ansprechpartner Entwicklung: Zuständiges Entwicklungsteam
- Endnutzer für explorative Tests: Alexander Müller (Testerrolle)

---

## 3. Testziele definieren

**Ziele:**

- **Funktionalität:** Alle drei neuen Features funktionieren gemäß der detaillierten Anforderungen
- **GUI:** Die Benutzeroberfläche ist verständlich, konsistent und gibt korrekte Rückmeldungen
- **Sicherheit:** Der Zugang zu alkoholischen Produkten ist zuverlässig durch die Altersverifikation geschützt
- **Datenintegrität:** Bewertungen werden korrekt gespeichert und berechnet; Versandkosten werden korrekt kalkuliert
- **Regression:** Bestehende Funktionen werden durch die neuen Features nicht beeinträchtigt

**Erwartete Ergebnisse:**

- Registrierte Nutzer können Produkte bewerten; nicht-registrierte Nutzer nicht
- Das Altersverifikations-Modal erscheint korrekt und verweigert bei Ablehnung den Zugang
- Die Versandkostenberechnung wechselt korrekt bei Über- und Unterschreitung des Schwellenwerts von €20,00
- Fehlermeldungen sind verständlich und werden an der richtigen Stelle angezeigt
- Keine Regressionen in bestehenden Funktionen

---

## 4. Testkriterien definieren

**Aussetzungskriterien:**

- Kritische Fehler, die die weitere Testdurchführung blockieren (z. B. Login nicht funktionsfähig)
- Testumgebung nicht erreichbar oder instabil

**Abnahmekriterien (Exit Criteria):**

- Mindestens 95 % der geplanten Testfälle wurden ausgeführt
- Mindestens 90 % der ausgeführten Testfälle haben den Status „Bestanden"
- Keine offenen Fehler mit Schweregrad „Kritisch" oder „Hoch"
- Alle drei neuen Features wurden vollständig getestet und freigegeben

---

## 5. Ressourcenplanung

- **Personal:** Alexander Müller (QA), Entwicklungsteam (Bugfixes)
- **Hardware:** Laptop (Windows 11), Smartphone (Android, iOS – sekundär)
- **Software:** Browser Chrome und Firefox (aktuell), Browser DevTools
- **Infrastruktur:** Öffentliche Testinstanz von Market Mate, Notion/GitHub für Dokumentation

---

## 6. Testumgebung planen

- Realgeräte mit echten Betriebssystemen und Browsern
- Primäre Umgebung: https://grocerymate.masterschool.com/ (produktionsnahe Umgebung)
- Sekundär: Mobiler Browser auf Smartphone
- Umgebungsstufen: Da keine DEV/TEST/ACC-Umgebungen verfügbar, erfolgen alle Tests in der öffentlichen Instanz

---

## 7. Zeitplan und Aufwandsschätzung

| Aktivität | Start | Ende | Umgebung | Verantwortlich | Aufwand |
|---|---|---|---|---|---|
| Anforderungsanalyse | 21.04.2026 | 22.04.2026 | – | Alexander Müller | 3 Std. |
| Testplanung | 28.04.2026 | 28.04.2026 | – | Alexander Müller | 2 Std. |
| Testfalldesign | 29.04.2026 | 30.04.2026 | – | Alexander Müller | 3 Std. |
| Funktionstest (neue Features) | 01.05.2026 | 03.05.2026 | PROD | Alexander Müller | 4 Std. |
| Regressionstest | 04.05.2026 | 05.05.2026 | PROD | Alexander Müller | 2 Std. |
| Usability-Test (explorativ) | 05.05.2026 | 05.05.2026 | PROD | Alexander Müller | 1 Std. |
| Testbericht & Dokumentation | 06.05.2026 | 06.05.2026 | – | Alexander Müller | 2 Std. |

---

## 8. Testartefakte (Test-Deliverables)

- Anforderungsanalyse (`requirements.md`) ✅
- Testplandokument (`test plan.md`) ✅
- Testfälle und Testdesign (`test case design.md`)
- Testdurchführungsprotokoll (`functional test execution.md`)
- Fehlerbericht (Bug Reports)
- Abschlussbericht (`test reporting.md`)
