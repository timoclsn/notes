## Todos

✅ Done
📝 Erster Schritt
⏳ Zweiter Schritt
### UI
- Task Listenelement
	- Icon Variante anstatt Emoji anzeigen ✅
- Task Chat
	- Icon Variante in Navbar anzeigen ✅
- Completed Tasks Sheet
	- Reduced Stickers in Summary anzeigen ✅
- Transition Screen
	- Sticker anzeigen ✅
	- Wie rein animieren? ⏳ 
		- Initial wackeln, das man sieht, das man sie bewegen kann
	- CTA Button truncaten, da Task Namen jetzt sehr lange sind📝
- Bereit für die Abgabe Screen⏳ 
	- Neue Card zur Zusammenfassung
	- Alle Sticker anzeigen, die man bekommen hat
- Übersicht Screen⏳ 
	- Wenn man aus dem Chat in die Übersicht kommt, sollen alle Sticker, die man in dieser Session bekommen hat "erscheinen" und in die Completed Tasks Leiste animieren.
### Code
- Zod einführen um Sticker JSON zu parsen ✅
- Assets anders benennen ✅
- Types und Layer anders benennen? 📝
	- Aktuell mit Skia im Name - hinterfragen ob das passt, da Konfig ja auch später im Web ohne Skia benutzt wird
- Wo brauchen wir error handling? 📝
	- Bisher: Wenn Sticker Config nicht validiert werden kann wird default Sticker angezeigt (lokaler Bot Sticker)
	- Kriegen alle Jahre die die Tasks habe die Sticker Config oder müssen wir noch nen Fallback auf die Emojis behalten?
- Wo logging? ⏳ 
- Backend anbinden und Mock entfernen ✅
	- Mock in yearsApi und mockserver in root
- Aufräumen
	- Code grundstätzlich aufräumen (ist alles da im Projekt wo es hin soll) 
	- Task Counter Komponente entfernen wenn irgends mehr benutzt
	- Sticker Assets bis auf Bot entfernen ⏳
	- Effekt Assets aussortieren  ⏳

### Tooling
- stickerConfig in Editor editierbar machen ⏳
- Sticker Konfigurator als externen Tool ⏳ 
### Design
- Sticker Effekte erstellen und JSONs generieren und hinterlegen 📝
- Assets final exportieren und in S3 hinterlegen 📝


## Übergabe David
- Lokale Sticker in Design System um besser importieren zu können
- mobile sticker feature angelegt
- useSticker Hook
- yearsApi gemocked und sticker assets mit node server gemocked 
- Sticker Assets etwas umbenannt
- Sticker in Task Liste, Completed Tasks und Task Transition Screen angezeigt