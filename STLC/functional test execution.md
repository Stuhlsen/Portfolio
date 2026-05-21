# Testdurchführung – Market Mate (GroceryMate)

**Projekt:** Market Mate Webshop  
**URL:** https://grocerymate.masterschool.com/  
**Autor:** Alexander Müller  
**Datum:** 21.05.2026  
**Version:** 1.0

---

Dieses Dokument enthält die Testdurchführung für die drei neuen Features von Market Mate. Jedes Szenario basiert auf den Testfällen aus dem Testfallentwurf.

---

## Feature 3 – Versandkostenregel

### Szenario 1: Als Nutzer von Market Mate sehe ich die korrekten Versandkosten basierend auf meinem Warenkorbwert.

| Schritt | Aktion | Erwartetes Ergebnis | OK/NOK | URL | Link zum Issue |
|---|---|---|---|---|---|
| 1 | https://grocerymate.masterschool.com/store aufrufen | Shop-Seite wird angezeigt | OK | /store | |
| 2 | Einloggen | Nutzer ist eingeloggt | OK | /store | |
| 3 | 5x Gala Apples à €2,00 in den Warenkorb legen (Subtotal = €10,00) | Produkte werden in den Warenkorb gelegt | OK | /store | |
| 4 | Warenkorb aufrufen | Warenkorb wird angezeigt | OK | /checkout | |
| 5 | Versandkosten prüfen (Subtotal €10,00) | Versandkosten = €5,00 | OK | /checkout | |
| 6 | Warenkorb leeren und 15x Gala Apples à €2,00 hinzufügen (Subtotal = €30,00) | Produkte werden in den Warenkorb gelegt | OK | /store | |
| 7 | Warenkorb aufrufen | Warenkorb wird angezeigt | OK | /checkout | |
| 8 | Versandkosten prüfen (Subtotal €30,00) | Versandkosten = €0,00 | OK | /checkout | |
| 9 | Warenkorb leeren und 8x Gala Apples + 1x Birchwood Quarter Pounders + 1x Tenderstem Broccoli hinzufügen (Subtotal = €19,99) | Produkte werden in den Warenkorb gelegt | OK | /store | |
| 10 | Versandkosten prüfen (Subtotal €19,99) | Versandkosten = €5,00 | OK | /checkout | |
| 11 | Warenkorb leeren und 10x Gala Apples à €2,00 hinzufügen (Subtotal = €20,00) | Produkte werden in den Warenkorb gelegt | OK | /store | |
| 12 | Versandkosten prüfen (Subtotal €20,00) | Versandkosten = €0,00 | OK | /checkout | |
| 13 | Warenkorb leeren und 9x Gala Apples + 1x Taste of Microwaveable Rice + 1x Orlando Meaty Strips + 1x Easy Peelers hinzufügen (Subtotal = €20,01) | Produkte werden in den Warenkorb gelegt | OK | /store | |
| 14 | Versandkosten prüfen (Subtotal €20,01) | Versandkosten = €0,00 | OK | /checkout | |

_Screenshots vorhanden für alle Grenzwerte (€19,99, €20,00, €20,01)_

---

### Szenario 2: Als Nutzer von Market Mate aktualisieren sich die Versandkosten sofort wenn ich meinen Warenkorb ändere.

| Schritt | Aktion | Erwartetes Ergebnis | OK/NOK | URL | Link zum Issue |
|---|---|---|---|---|---|
| 1 | https://grocerymate.masterschool.com/store aufrufen | Shop-Seite wird angezeigt | OK | /store | |
| 2 | Einloggen | Nutzer ist eingeloggt | OK | /store | |
| 3 | 9x Gala Apples + 1x Birchwood British Beef Mince hinzufügen (Subtotal = €21,99) | Produkte werden in den Warenkorb gelegt | OK | /store | |
| 4 | Warenkorb aufrufen | Warenkorb wird angezeigt | OK | /checkout | |
| 5 | Versandkosten prüfen (Subtotal €21,99) | Versandkosten = €0,00 | OK | /checkout | |
| 6 | Birchwood British Beef Mince aus dem Warenkorb entfernen (Subtotal = €18,00) | Produkt wird entfernt | OK | /checkout | |
| 7 | Versandkosten ohne Seitenneuladung prüfen | Versandkosten wechseln sofort auf €5,00 | NOK | /checkout | #1 |

_Screenshots vorhanden (vor Neuladen: €0,00, nach Neuladen: €5,00)_

---
