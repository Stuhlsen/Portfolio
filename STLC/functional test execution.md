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

_Screenshots vorhanden_

---

### Szenario 1.2: Als Nutzer der ein Produkt nicht gekauft hat kann ich keine Bewertung abgeben.

| Schritt | Aktion | Erwartetes Ergebnis | OK/NOK | URL | Link zum Issue |
|---|---|---|---|---|---|
| 1 | https://grocerymate.masterschool.com/ aufrufen | Startseite wird angezeigt | OK | / | |
| 2 | Ohne Login zur Produktdetailseite navigieren | Produktdetailseite wird angezeigt | OK | /product/66b3a57b3fd5048eacb4798f | |
| 3 | Bereich für Bewertungen prüfen | Bewertungsformular ist nicht sichtbar; Hinweis erscheint dass das Produkt zuerst gekauft werden muss | OK | /product/66b3a57b3fd5048eacb4798f | |
<img width="1025" height="269" alt="image" src="https://github.com/user-attachments/assets/42ddd7be-438c-4d7f-8cc7-320b4e25b2d2" />

_Screenshots vorhanden_

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
| 7 | Durchschnittsbewertung prüfen | Durchschnittsbewertung hat sich entsprechend geändert | NOK | /product/66b3a57b3fd5048eacb4798f | #4 |
<img width="779" height="342" alt="image" src="https://github.com/user-attachments/assets/9570fe52-88f8-4939-bd9d-8a7abb6ef885" />
<img width="1006" height="344" alt="image" src="https://github.com/user-attachments/assets/b3aa302c-6f41-4856-a9fe-4aa7c7b1b3d3" />


_Screenshots vorhanden (Durchschnitt vor und nach dem Edit)_

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
| 7 | Zeichenzähler und Farbe prüfen | Zeichenzähler zeigt 500/500 in neutraler Farbe | NOK | /product/66b3a57b3fd5048eacb4798f | #5 |
<img width="584" height="343" alt="image" src="https://github.com/user-attachments/assets/c12ffcc4-077a-43d1-bb54-9c12cf991605" />

_Screenshots vorhanden (roter Zeichenzähler bei 500/500)_

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

_Screenshots vorhanden_

---
