# Testdurchführung – Market Mate (GroceryMate)

**Projekt:** Market Mate Webshop  
**URL:** https://grocerymate.masterschool.com/  
**Autor:** Alexander Müller  
**Datum:** 21.05.2026  
**Version:** 1.0

---

Dieses Dokument enthält die Testdurchführung für die drei neuen Features von Market Mate. Jedes Szenario basiert auf den Testfällen aus dem Testfallentwurf.

---

## Feature 1 – Bewertungssystem für Produkte

### Szenario 1.1: Als eingeloggter Nutzer der ein Produkt gekauft hat kann ich eine Bewertung abgeben.

| Schritt | Aktion | Erwartetes Ergebnis | OK/NOK | URL | Link zum Issue |
|---|---|---|---|---|---|
| 1 | https://grocerymate.masterschool.com/ aufrufen | Startseite wird angezeigt | OK | / | |
| 2 | Einloggen | Nutzer ist eingeloggt | OK | / | |
| 3 | Produktdetailseite aufrufen | Produktdetailseite wird angezeigt | OK | /product/66b3a57b3fd5048eacb4798f | |
| 4 | Bewertungsformular aufrufen | Bewertungsformular ist sichtbar | OK | /product/66b3a57b3fd5048eacb4798f | |
| 5 | 4 Sterne auswählen | 4 Sterne sind ausgewählt | OK | /product/66b3a57b3fd5048eacb4798f | |
| 6 | Bewertung abschicken | Bewertung wird gespeichert | OK | /product/66b3a57b3fd5048eacb4798f | |
| 7 | Durchschnittsbewertung auf der Produktkarte prüfen | Durchschnittsbewertung hat sich aktualisiert | OK | /product/66b3a57b3fd5048eacb4798f | |
<img width="558" height="344" alt="image" src="https://github.com/user-attachments/assets/a0841651-12c4-4f49-ba1b-080ff458ecdb" />


---

### Szenario 1.2: Als Nutzer der ein Produkt nicht gekauft hat kann ich keine Bewertung abgeben.

| Schritt | Aktion | Erwartetes Ergebnis | OK/NOK | URL | Link zum Issue |
|---|---|---|---|---|---|
| 1 | https://grocerymate.masterschool.com/ aufrufen | Startseite wird angezeigt | OK | / | |
| 2 | Ohne Login zur Produktdetailseite navigieren | Produktdetailseite wird angezeigt | OK | /product/66b3a57b3fd5048eacb4798f | |
| 3 | Bereich für Bewertungen prüfen | Bewertungsformular ist nicht sichtbar; Hinweis erscheint dass das Produkt zuerst gekauft werden muss | OK | /product/66b3a57b3fd5048eacb4798f | |
<img width="1025" height="269" alt="image" src="https://github.com/user-attachments/assets/42ddd7be-438c-4d7f-8cc7-320b4e25b2d2" />


---

### Szenario 1.3: Als eingeloggter Nutzer kann ich eine bestehende Bewertung bearbeiten und der Durchschnitt aktualisiert sich.

| Schritt | Aktion | Erwartetes Ergebnis | OK/NOK | URL | Link zum Issue |
|---|---|---|---|---|---|
| 1 | https://grocerymate.masterschool.com/ aufrufen | Startseite wird angezeigt | OK | / | |
| 2 | Einloggen | Nutzer ist eingeloggt | OK | / | |
| 3 | Produktdetailseite aufrufen | Produktdetailseite wird angezeigt | OK | /product/66b3a57b3fd5048eacb4798f | |
| 4 | Aktuellen Durchschnitt notieren | Durchschnittsbewertung ist sichtbar | OK | /product/66b3a57b3fd5048eacb4798f | |
| 5 | Auf „Edit" klicken | Bearbeitungsformular öffnet sich | OK | /product/66b3a57b3fd5048eacb4798f | |
| 6 | Bewertung auf 3 Sterne ändern und speichern | Bewertung wird auf 3 Sterne aktualisiert | OK | /product/66b3a57b3fd5048eacb4798f | |
| 7 | Durchschnittsbewertung prüfen | Durchschnittsbewertung hat sich entsprechend geändert | NOK | /product/66b3a57b3fd5048eacb4798f | [#4](https://github.com/Stuhlsen/Portfolio/issues/4) |
<img width="779" height="342" alt="image" src="https://github.com/user-attachments/assets/9570fe52-88f8-4939-bd9d-8a7abb6ef885" />
<img width="1006" height="344" alt="image" src="https://github.com/user-attachments/assets/b3aa302c-6f41-4856-a9fe-4aa7c7b1b3d3" />



---

### Szenario 1.4: Als eingeloggter Nutzer kann ich eine Bewertung mit genau 500 Zeichen abgeben.

| Schritt | Aktion | Erwartetes Ergebnis | OK/NOK | URL | Link zum Issue |
|---|---|---|---|---|---|
| 1 | https://grocerymate.masterschool.com/ aufrufen | Startseite wird angezeigt | OK | / | |
| 2 | Einloggen | Nutzer ist eingeloggt | OK | / | |
| 3 | Produktdetailseite aufrufen | Produktdetailseite wird angezeigt | OK | /product/66b3a57b3fd5048eacb4798f | |
| 4 | Bewertungsformular aufrufen | Bewertungsformular ist sichtbar | OK | /product/66b3a57b3fd5048eacb4798f | |
| 5 | Text mit exakt 500 Zeichen in das Feedback-Feld eingeben | Text wird eingegeben; Zeichenzähler zeigt 500/500 | OK | /product/66b3a57b3fd5048eacb4798f | |
| 6 | Bewertung abschicken | Bewertung wird erfolgreich gespeichert | OK | /product/66b3a57b3fd5048eacb4798f | |
| 7 | Zeichenzähler und Farbe prüfen | Zeichenzähler zeigt 500/500 in neutraler Farbe | NOK | /product/66b3a57b3fd5048eacb4798f | [#5](https://github.com/Stuhlsen/Portfolio/issues/5) |
<img width="584" height="343" alt="image" src="https://github.com/user-attachments/assets/c12ffcc4-077a-43d1-bb54-9c12cf991605" />


---

### Szenario 1.5: Als eingeloggter Nutzer kann ich keine Bewertung mit mehr als 500 Zeichen abgeben.

| Schritt | Aktion | Erwartetes Ergebnis | OK/NOK | URL | Link zum Issue |
|---|---|---|---|---|---|
| 1 | https://grocerymate.masterschool.com/ aufrufen | Startseite wird angezeigt | OK | / | |
| 2 | Einloggen | Nutzer ist eingeloggt | OK | / | |
| 3 | Produktdetailseite aufrufen | Produktdetailseite wird angezeigt | OK | /product/66b3a57b3fd5048eacb4798f | |
| 4 | Bewertungsformular aufrufen | Bewertungsformular ist sichtbar | OK | /product/66b3a57b3fd5048eacb4798f | |
| 5 | Versuch 501 Zeichen in das Feedback-Feld einzugeben | Eingabe wird bei 500 Zeichen blockiert; 501 Zeichen können nicht eingegeben werden | OK | /product/66b3a57b3fd5048eacb4798f | |


---

### Szenario 1.6: Als eingeloggter Nutzer kann ich keine Bewertung ohne Sternauswahl abschicken.

| Schritt | Aktion | Erwartetes Ergebnis | OK/NOK | URL | Link zum Issue |
|---|---|---|---|---|---|
| 1 | https://grocerymate.masterschool.com/ aufrufen | Startseite wird angezeigt | OK | / | |
| 2 | Einloggen | Nutzer ist eingeloggt | OK | / | |
| 3 | Produktdetailseite aufrufen | Produktdetailseite wird angezeigt | OK | /product/66b3a57b3fd5048eacb4798f | |
| 4 | Bewertungsformular aufrufen | Bewertungsformular ist sichtbar | OK | /product/66b3a57b3fd5048eacb4798f | |
| 5 | Ohne Sternauswahl auf „Abschicken" klicken | Fehlermeldung erscheint; Bewertung wird nicht gespeichert | OK | /product/66b3a57b3fd5048eacb4798f | |
<img width="653" height="344" alt="image" src="https://github.com/user-attachments/assets/930f5154-2432-437f-89c8-17d1ad6e85e8" />
<img width="404" height="67" alt="image" src="https://github.com/user-attachments/assets/807bd527-de98-422d-8dc6-3a8e299b331c" />


---

## Feature 2 – Altersverifikation für alkoholische Produkte
 
### Szenario 2.1: Als Nutzer sehe ich ein Altersverifikations-Modal wenn ich die Alkohol-Kategorie aufrufe.
 
| Schritt | Aktion | Erwartetes Ergebnis | OK/NOK | URL | Link zum Issue |
|---|---|---|---|---|---|
| 1 | https://grocerymate.masterschool.com/store aufrufen | Shop-Seite wird angezeigt | OK | /store | |
| 2 | Neue Browser-Session starten (vorheriger Cache geleert) | Neue Session ist aktiv | OK | /store | |
| 3 | Auf die Kategorie „Alocohol" klicken | Modal erscheint mit Eingabefeld für das Geburtsdatum | NOK | /store | [#2](https://github.com/Stuhlsen/Portfolio/issues/2) |
 
<img width="268" height="110" alt="image" src="https://github.com/user-attachments/assets/d207bce6-5b0d-411b-bcbe-d33be1f5f12a" />

 
---
 
### Szenario 2.2: Als Nutzer unter 18 Jahren erhalte ich keinen Zugang zur Alkohol-Kategorie.
 
| Schritt | Aktion | Erwartetes Ergebnis | OK/NOK | URL | Link zum Issue |
|---|---|---|---|---|---|
| 1 | https://grocerymate.masterschool.com/store aufrufen | Shop-Seite wird angezeigt | OK | /store | |
| 2 | Neue Browser-Session starten | Neue Session ist aktiv; Modal erscheint | OK | /store | |
| 3 | Geburtsdatum 22.05.2008 (einen Tag zu jung) eingeben | Zugang wird verweigert; Fehlermeldung erscheint | OK | /store | |
| 4 | Fehlermeldung prüfen | „You are underage. You can still browse the site, but you will not be able to view alcohol products" | OK | /store | |

<img width="764" height="205" alt="image" src="https://github.com/user-attachments/assets/d1aecfdb-24b9-4fa5-af2d-a299b3325b88" />

<img width="458" height="119" alt="image" src="https://github.com/user-attachments/assets/a5cb71c8-f10c-4f82-a151-9671d9fd3edd" />

 
---
 
### Szenario 2.3: Als Nutzer der genau 18 Jahre alt ist erhalte ich Zugang zur Alkohol-Kategorie.
 
| Schritt | Aktion | Erwartetes Ergebnis | OK/NOK | URL | Link zum Issue |
|---|---|---|---|---|---|
| 1 | https://grocerymate.masterschool.com/store aufrufen | Shop-Seite wird angezeigt | OK | /store | |
| 2 | Neue Browser-Session starten | Neue Session ist aktiv; Modal erscheint | OK | /store | |
| 3 | Geburtsdatum 21.05.2008 (genau 18 Jahre) eingeben | Zugang zur Alkohol-Kategorie wird gewährt | OK | /store | |
| 4 | Bestätigungsmeldung prüfen | „You are of age. You can now view all products, even alcohol products" | OK | /store | |
 
<img width="637" height="116" alt="image" src="https://github.com/user-attachments/assets/fea5cf5c-bb55-4459-ae25-81bb2389b8c6" />

 
---
 
### Szenario 2.3b: Als Nutzer der einen Tag älter als 18 Jahre ist erhalte ich Zugang zur Alkohol-Kategorie.
 
| Schritt | Aktion | Erwartetes Ergebnis | OK/NOK | URL | Link zum Issue |
|---|---|---|---|---|---|
| 1 | https://grocerymate.masterschool.com/store aufrufen | Shop-Seite wird angezeigt | OK | /store | |
| 2 | Neue Browser-Session starten | Neue Session ist aktiv; Modal erscheint | OK | /store | |
| 3 | Geburtsdatum 20.05.2008 (einen Tag älter als 18) eingeben | Zugang zur Alkohol-Kategorie wird gewährt | OK | /store | |
| 4 | Bestätigungsmeldung prüfen | „You are of age. You can now view all products, even alcohol products" | OK | /store | |
 
<img width="637" height="116" alt="image" src="https://github.com/user-attachments/assets/824c67ac-938a-476b-9923-4c3a3f0ccca8" />

 
---
 
### Szenario 2.4: Als Nutzer der die Altersverifikation bereits bestätigt hat muss ich das Modal nicht erneut ausfüllen.
 
| Schritt | Aktion | Erwartetes Ergebnis | OK/NOK | URL | Link zum Issue |
|---|---|---|---|---|---|
| 1 | https://grocerymate.masterschool.com/store aufrufen | Shop-Seite wird angezeigt | OK | /store | |
| 2 | Altersverifikation mit gültigem Datum bestätigen | Zugang zur Alkohol-Kategorie wird gewährt | OK | /store | |
| 3 | Zur Startseite navigieren | Startseite wird angezeigt | OK | / | |
| 4 | Erneut zur Kategorie „Alocohol" navigieren | Modal erscheint nicht erneut; direkter Zugang | OK | /store | |
 
 
---
 
### Szenario 2.5: Als Nutzer der das Modal ohne Eingabe schließt erhalte ich keinen Zugang zur Alkohol-Kategorie.
 
| Schritt | Aktion | Erwartetes Ergebnis | OK/NOK | URL | Link zum Issue |
|---|---|---|---|---|---|
| 1 | https://grocerymate.masterschool.com/store aufrufen | Shop-Seite wird angezeigt | OK | /store | |
| 2 | Neue Browser-Session starten | Neue Session ist aktiv; Modal erscheint | OK | /store | |
| 3 | Modal per ESC oder X ohne Datumseingabe schließen | Modal kann nicht ohne Eingabe geschlossen werden; Nutzer ist blockiert | OK | /store | |
 
 
---
 
### Szenario 2.6: Als Nutzer unter 18 Jahren kann ich alkoholische Produkte nicht über eine direkte URL aufrufen.
 
| Schritt | Aktion | Erwartetes Ergebnis | OK/NOK | URL | Link zum Issue |
|---|---|---|---|---|---|
| 1 | https://grocerymate.masterschool.com/store aufrufen | Shop-Seite wird angezeigt | OK | /store | |
| 2 | Neue Browser-Session starten | Neue Session ist aktiv; Modal erscheint | OK | /store | |
| 3 | Geburtsdatum 22.05.2008 (unter 18) eingeben | Zugang verweigert | OK | /store | |
| 4 | Direkte URL eines alkoholischen Produkts aufrufen: https://grocerymate.masterschool.com/product/66b3a57b3fd5048eacb47a76 | Modal erscheint erneut; kein Zugang ohne Verifikation | NOK | /product/66b3a57b3fd5048eacb47a76 | [#3](https://github.com/Stuhlsen/Portfolio/issues/3) |
 
 
## Feature 3 – Versandkostenregel
 
### Szenario 3.1: Als Nutzer mit einem Warenkorbwert unter €20,00 sehe ich Versandkosten von €5,00.
 
| Schritt | Aktion | Erwartetes Ergebnis | OK/NOK | URL | Link zum Issue |
|---|---|---|---|---|---|
| 1 | https://grocerymate.masterschool.com/store aufrufen | Shop-Seite wird angezeigt | OK | /store | |
| 2 | Einloggen | Nutzer ist eingeloggt | OK | / | |
| 3 | 5x Gala Apples à €2,00 in den Warenkorb legen (Subtotal = €10,00) | Produkte werden in den Warenkorb gelegt | OK | /store | |
| 4 | Warenkorb aufrufen | Warenkorb wird angezeigt | OK | /checkout | |
| 5 | Versandkosten prüfen | Versandkosten = €5,00 | OK | /checkout | |
 
<img width="406" height="352" alt="image" src="https://github.com/user-attachments/assets/e9ee7213-08cf-49a4-8cae-5a67429f43c7" />

 
---
 
### Szenario 3.2: Als Nutzer mit einem Warenkorbwert über €20,00 sehe ich keine Versandkosten.
 
| Schritt | Aktion | Erwartetes Ergebnis | OK/NOK | URL | Link zum Issue |
|---|---|---|---|---|---|
| 1 | https://grocerymate.masterschool.com/store aufrufen | Shop-Seite wird angezeigt | OK | /store | |
| 2 | Einloggen | Nutzer ist eingeloggt | OK | / | |
| 3 | 15x Gala Apples à €2,00 in den Warenkorb legen (Subtotal = €30,00) | Produkte werden in den Warenkorb gelegt | OK | /store | |
| 4 | Warenkorb aufrufen | Warenkorb wird angezeigt | OK | /checkout | |
| 5 | Versandkosten prüfen | Versandkosten = €0,00 | OK | /checkout | |
 
<img width="425" height="376" alt="image" src="https://github.com/user-attachments/assets/0b721d02-5f9d-43a8-a64a-02105ae07c91" />

 
---
 
### Szenario 3.3: Als Nutzer mit einem Warenkorbwert von €19,99 sehe ich Versandkosten von €5,00.
 
| Schritt | Aktion | Erwartetes Ergebnis | OK/NOK | URL | Link zum Issue |
|---|---|---|---|---|---|
| 1 | https://grocerymate.masterschool.com/store aufrufen | Shop-Seite wird angezeigt | OK | /store | |
| 2 | Einloggen | Nutzer ist eingeloggt | OK | / | |
| 3 | 8x Gala Apples à €2,00 + 1x Birchwood Quarter Pounders à €2,49 + 1x Tenderstem Broccoli à €1,50 in den Warenkorb legen (Subtotal = €19,99) | Produkte werden in den Warenkorb gelegt | OK | /store | |
| 4 | Warenkorb aufrufen | Warenkorb wird angezeigt | OK | /checkout | |
| 5 | Versandkosten prüfen | Versandkosten = €5,00; Gesamtbetrag = €24,99 | OK | /checkout | |
 
<img width="412" height="458" alt="image" src="https://github.com/user-attachments/assets/692d3bfa-ea6a-460e-bfef-d94c20334d81" />

 
---
 
### Szenario 3.4: Als Nutzer mit einem Warenkorbwert von genau €20,00 sehe ich keine Versandkosten.
 
| Schritt | Aktion | Erwartetes Ergebnis | OK/NOK | URL | Link zum Issue |
|---|---|---|---|---|---|
| 1 | https://grocerymate.masterschool.com/store aufrufen | Shop-Seite wird angezeigt | OK | /store | |
| 2 | Einloggen | Nutzer ist eingeloggt | OK | / | |
| 3 | 10x Gala Apples à €2,00 in den Warenkorb legen (Subtotal = €20,00) | Produkte werden in den Warenkorb gelegt | OK | /store | |
| 4 | Warenkorb aufrufen | Warenkorb wird angezeigt | OK | /checkout | |
| 5 | Versandkosten prüfen | Versandkosten = €0,00; Gesamtbetrag = €20,00 | OK | /checkout | |
 
<img width="419" height="370" alt="image" src="https://github.com/user-attachments/assets/4d5f2517-3c44-47e3-b76b-63fc6dd911f1" />

 
---
 
### Szenario 3.5: Als Nutzer mit einem Warenkorbwert von €20,01 sehe ich keine Versandkosten.
 
| Schritt | Aktion | Erwartetes Ergebnis | OK/NOK | URL | Link zum Issue |
|---|---|---|---|---|---|
| 1 | https://grocerymate.masterschool.com/store aufrufen | Shop-Seite wird angezeigt | OK | /store | |
| 2 | Einloggen | Nutzer ist eingeloggt | OK | / | |
| 3 | 9x Gala Apples à €2,00 + 1x Taste of Microwaveable Rice à €0,42 + 1x Orlando Meaty Strips à €0,49 + 1x Easy Peelers à €1,10 in den Warenkorb legen (Subtotal = €20,01) | Produkte werden in den Warenkorb gelegt | OK | /store | |
| 4 | Warenkorb aufrufen | Warenkorb wird angezeigt | OK | /checkout | |
| 5 | Versandkosten prüfen | Versandkosten = €0,00; Gesamtbetrag = €20,01 | OK | /checkout | |
 
<img width="412" height="460" alt="image" src="https://github.com/user-attachments/assets/5cec1c5a-6a18-406f-8a1b-140958d28e74" />

 
---
 
### Szenario 3.6: Als Nutzer aktualisieren sich die Versandkosten sofort wenn mein Warenkorbwert unter €20,00 fällt.
 
| Schritt | Aktion | Erwartetes Ergebnis | OK/NOK | URL | Link zum Issue |
|---|---|---|---|---|---|
| 1 | https://grocerymate.masterschool.com/store aufrufen | Shop-Seite wird angezeigt | OK | /store | |
| 2 | Einloggen | Nutzer ist eingeloggt | OK | / | |
| 3 | 9x Gala Apples à €2,00 + 1x Birchwood British Beef Mince à €4,19 in den Warenkorb legen (Subtotal = €22,19) | Produkte werden in den Warenkorb gelegt | OK | /store | |
| 4 | Warenkorb aufrufen | Warenkorb wird angezeigt | OK | /checkout | |
| 5 | Versandkosten prüfen (Subtotal €22,19) | Versandkosten = €0,00 | OK | /checkout | |
| 6 | Birchwood British Beef Mince aus dem Warenkorb entfernen (Subtotal = €18,00) | Produkt wird entfernt | OK | /checkout | |
| 7 | Versandkosten ohne Seitenneuladung prüfen | Versandkosten wechseln sofort auf €5,00 | NOK | /checkout | [#1](https://github.com/Stuhlsen/Portfolio/issues/1) |
 
<img width="410" height="459" alt="image" src="https://github.com/user-attachments/assets/03b47748-ab64-4c17-b00a-985fd5370f26" />
<img width="446" height="386" alt="image" src="https://github.com/user-attachments/assets/dd9d2f34-fd8b-4f22-97dc-fc54c36f8feb" />


 
