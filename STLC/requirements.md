# Anforderungsanalyse – Market Mate (GroceryMate)

**Projekt:** Market Mate Webshop  
**URL:** https://grocerymate.masterschool.com/  
**Autor:** Alexander Müller  
**Datum:** 28.04.2026

---

## Die Applikation

Webshop mit folgenden bestehenden Grundfunktionen:

- Registrierung und Login
- Produktsuche mit Sortierfunktion (z. B. nach Preis) und Kategorisierung von Produkten
- Produkte zu Favoriten hinzufügen
- Produkte in den Warenkorb legen
- Bestellabschluss: Eingabe von Rechnungs- und Versandinformationen, Auswahl der Zahlungsmethode, Preisberechnung (Gesamtsumme)

---

## Neue Features

### 1. Bewertungssystem für Produkte

**Unklare Anforderung:**

Nutzer sollen Produkte mit einem 5-Sterne-System bewerten und zusätzlich schriftliches Feedback hinterlassen können.

**Fragen:**

1. Müssen Nutzer eingeloggt sein, um eine Bewertung abzugeben, oder können auch anonyme Besucher bewerten?
2. Kann ein Nutzer dasselbe Produkt mehrmals bewerten, oder ist nur eine Bewertung pro Nutzer und Produkt erlaubt?
3. Ist das schriftliche Feedback ein Pflichtfeld oder optional?
4. Gibt es ein Zeichenlimit für den Feedback-Text?
5. Wie wird die angezeigte Durchschnittsbewertung berechnet, und wie viele Nachkommastellen werden angezeigt?

**Detaillierte Anforderung:**

Nur eingeloggte Nutzer können eine Produktbewertung abgeben. Pro Nutzer ist eine Bewertung pro Produkt erlaubt; eine erneute Abgabe überschreibt die vorherige. Die Bewertung erfolgt durch Auswahl von 1 bis 5 Sternen, wobei die Sternauswahl ein Pflichtfeld ist. Das schriftliche Feedback ist optional und auf maximal 250 Zeichen begrenzt. Das System zeigt bei Überschreitung des Zeichenlimits eine Fehlermeldung an und verhindert das Speichern. Die angezeigte Durchschnittsbewertung auf der Produktkarte wird als arithmetisches Mittel aller abgegebenen Bewertungen berechnet und auf eine Nachkommastelle gerundet.

---

### 2. Altersverifikation für alkoholische Produkte

**Unklare Anforderung:**

Alkoholische Produkte erfordern eine Altersverifikation. Beim Aufrufen der Kategorie soll ein Fenster erscheinen, in dem Nutzer ihr Alter angeben müssen (18+), bevor sie Zugriff erhalten.

**Fragen:**

1. Zu welchem genauen Zeitpunkt erscheint das Verifikationsfenster – beim Öffnen der Alkohol-Kategorie, beim Klick auf ein einzelnes Produkt oder beides?
2. Was passiert, wenn ein Nutzer angibt, unter 18 zu sein oder die Verifikation ablehnt?
3. Bleibt die Verifikation innerhalb einer Session bestehen, oder erscheint das Fenster bei jedem erneuten Besuch der Kategorie?
4. Welche Eingabemethode soll zur Altersangabe verwendet werden – eine Ja/Nein-Bestätigung oder die Eingabe des Geburtsdatums?

**Detaillierte Anforderung:**

Das Altersverifikations-Modal erscheint, wenn ein Nutzer die Produktkategorie für alkoholische Produkte aufruft. Das Modal enthält eine Bestätigungsfrage, ob der Nutzer 18 Jahre oder älter ist. Bestätigt der Nutzer dies, erhält er Zugang zur Kategorie. Verneint er oder schließt das Modal, wird er zurück zur allgemeinen Produktübersicht weitergeleitet und erhält keinen Zugang zu alkoholischen Produkten. Die Verifikation gilt für die gesamte Session; das Modal erscheint erst bei einer neuen Session erneut. Die Verifikation wird ausschließlich auf der Kategorieseite ausgelöst, nicht erneut auf den einzelnen Produktdetailseiten.

---

### 3. Änderungen bei den Versandkosten

**Unklare Anforderung:**

Versandkosten entfallen ab einem bestimmten Bestellwert. Darunter fallen Versandkosten an.

**Fragen:**

1. Wie hoch ist der genaue Bestellwert, ab dem der Versand kostenlos ist?
2. Wie hoch sind die Versandkosten, wenn der Schwellenwert nicht erreicht wird?
3. Bezieht sich der Schwellenwert auf den Produktsubtotal vor oder nach Abzug von Rabatten oder Gutscheinen?
4. Wird die Versandkostenberechnung dynamisch im Warenkorb aktualisiert, wenn Artikel hinzugefügt oder entfernt werden?

**Detaillierte Anforderung:**

Ab einem Produktsubtotal von genau €20,00 oder mehr ist der Versand kostenlos. Liegt der Subtotal unter €20,00, werden Versandkosten in Höhe von €5,00 erhoben. Der Schwellenwert bezieht sich auf den Subtotal nach Abzug etwaiger Rabatte oder Gutscheincodes. Die Versandkostenanzeige im Warenkorb und im Checkout aktualisiert sich dynamisch, sobald der Subtotal den Schwellenwert über- oder unterschreitet – ohne Seitenneuladung. Bei einem Subtotal von genau €20,00 entfallen die Versandkosten (inklusiver Grenzwert).
