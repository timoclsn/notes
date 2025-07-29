#work #steuerbot #app 

## Todos
- Translations prüfen
- Lastschrift Kleingedrucktes basierend auf Methode anzeigen ✅
- Flag ob Client Abillify unterstützt mitschicken ✅
- Bezahlen Screen
	- Status + Texte
	- Infos
	- Überweisung Hinweis
	- Rechnung herunterladen
	- Zu sofort bezahlen wechseln (Wenn Pay Later und Wechsel möglich)
	- UsedMedthod entfernen?
- in switchPaymentTime getPaymentStatus handeln (web vs. mobile)
- SepaInfos für Abillify ergänzen

## Besprechung mit Marc
- 

## Mit Matthias besprechen
- Wir schicken Provider mit beim initialen Bezahlen?
	- Jain - wir kriegen Provider in offer und schleifen den dann durch. ✅
- Beim Anzeigen lesen wir Provider aus und zeigen dann basierend darauf Sachen an? ✅

- Können wir wissen, wann das Konto belastet wird?
 
### Infos von Matthias 
 - failed gibt es nicht mehr
 - pay later ready gibt es nicht mehr
 - Vor Bezahlung bekommt man eine Offer, hier steht dann schon der Provider mit. Anhand von dem kann dann beim Bezahlen der richtige Provider gesetzt werden

## Mit Nadja abstimmen
- Wie sieht die Kontoauswahl im neuen Design aus? ✅


## Änderungen
### Sofort bezahlen
- Auflistung der Konten
### Später bezahlen
- Lastschrift auch hier schon vorher holen
### Zahlung
- Neues Design von Zahlungsdetails
- Rechnung herunterladen Button hinzufügen
- Status anders als bisher
- Screens fallen weg
### Deeplinks?
- Prüfen
### Translations
- Lastschriftmandat





## Web App
### Relevante Pages
- /jetzt-bezahlen
	- PayNow Komponente


## Später schauen
- schauen ob SteuerbotAccount am Ende noch gebraucht wird
- Translations prüfen (SepaDetails)
- Sepalastschriftmandat Text anpassen



## Screens die wir nicht mehr brauchen?
- Überweisung
- Sepa-bezahlung
