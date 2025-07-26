**Direkt verbinden**
1. Mit Box Wlan verbinden
2. IP: [http://10.13.37.1](http://10.13.37.1) 
Box = Router

**Box in Wlan einbinden NEU**
1. Per SSH mit Box verbinden
2. cd /data/etc/
3. vi wlan.cfg
4. ssid, passphrase und Modus client ändern
5. (i to insert. Esc to go back to command mode, :wq to save and quit)
6. /etc/init.d/S41WLAN restart

**Ports**
- Websockets Port: :7681

**Box updaten**
1. Box per USB Kabel mit Mac verbinden 
2. File auf homee Laufwerk laden
3. Warten! Muss ca. 30 sek dauern
4. Box kurz von Strom trennen
5. Box startet neu und führt Update durch

**SSH auf Box einschalten und verbinden wireless**
1. Knopf kurz drücken, bis LED für eine Minute orange blinkt
2. In Dev App "startSSH" eingeben oder drücken
3. Im Terminal ssh root@ip  eingeben ← ip = ip-Adresse von Box
4. Jetzt cube root Passwort aus 1PW eingeben/einfügen

**Per Netzwerkkabel und ssh mit Box verbinden**
1. Netzwerkkabel anschließen
2. In Netzwerkeinstellungen: IPv4 konfigurieren auf manuell schalten
3. IP-Adresse z.B. 192.168.1.3
4. Teilnetzmarke 255.255.255.0
5. Im Terminal: root@ipadresse (z.b. 192.168.1.2)
6. Jetzt cube root Passwort aus 1PW eingeben/einfügen

**Box soll ohne Login funktionieren**
Es muss Datei DONT_CHECK_FOR_PERMISSION angelegt werden.
1. Per SSH mit Box verbinden
2. Filesystem schreibbar machen mount -o remount,rw /
3. Datei anlegen touch /var/homee/DONT_CHECK_FOR_PERMISSION
4. Wieder read only machen mount -o remount,ro /

**Dev App einschalten (ist bei Produktions Built ausgeschalten)**
Es muss Datei ALLOW_DEVAPP angelegt werden
1. Per ssh mit Box verbinden
2. Filesystem schreibbar machen mount -o remount,rw /
3. Datei anlegen touch /var/homee/ALLOW_DEVAPP
4. Wieder read only machen mount -o remount,ro /

**Box soll auch HTTP anstatt (HTTPS)Verbindungen zulassen**
Es muss die Datei ALLOW_HTTP_CONNECTION angelegt werden
1. Per ssh mit Box verbinden
2. Filesystem schreibbar machen mount -o remount,rw /
3. Datei anlegen touch /var/homee/ALLOW_HTTP_CONNECTION
4. homee neu starten mit killall homee
5. Wieder read only machen mount -o remount,ro /

**Datenbank löschen**
1. Per ssh mit Box verbinden
2. killall homie_starter
3. killall homee
4. rm /var/homee/rw/homie_encrypted.db
5. /etc/init.d/S92homee start

**Neueste homee Version Bauen**
1. Per SSH mit homee@192.168.178.4 verbinden
2. PW in 1PW Buildmaschine
3. cd Desktop
4. ./buildscript.sh develop koala developer (<branch> <board> <webapp branch>)

**WLAN auf Box neu starten**
1. Per SSH mit Box verbinden
2. /etc/init.d/S41WLAN restart

**Von außen auf buildmaschine**
- IP: [git.kickass.net](http://git.kickass.net)
- Port: 4022

**Box per SSH updaten**
1. Per SSH mit Board verbinden
2. cd /export
3. rm export.img
4. wget {Link auf homee aus Slack}
5. Nach Download reboot

**Koala Version tauschen um Modem updates zu triggern**
1. Per SSH mit hom.ee verbinden
2. ssh homee@hom.ee
3. cd docs/homee/update/hager/test/
4. Dateien müssen "homee_cube_2.2.2.tar.gz" und "homee_cube_2.2.1.tar.gz" heißen
5. In "version_2.2.2" muss Dateigröße mit "homee_cube_2.2.2.tar.gz" Dateigröße übereinstimmen
6. cat version zeigt aktuelle Version
7. `cp version_2.2.2 version ← andere Version als in "version" steht hier einsetzten (ersetzt den Inhalt vom Zweiten mit dem Ersten)

**Live Log**
1. Per SSH mit Box verbinden
2. cd /var/homee/
3. tail -f logs/spdhomee.log

**KoalaBox ohne Inova starten**
1. Per SSH mit Box verbinden
2. Falls homee noch läuft killall homie_starter
3. killall homee
4. Danach: cd /var/homee/
5. ./homee noInova` 

**Eine Zeile aus Datei im Terminal löschen**
sed -i '' '86d' /Users/Timo/.ssh/known_hosts

**homee Datenbank speichern**
1. scp root@homee-ip-addresss:/var/homee/rw/homie_encrypted.db /Users/*deinUserName*/Desktop/homie_encrypted.db

**Datenbank Version ändern 1**
1. Per SSH mit Box verbinden
2. killall homie_starter
3. killall homee
4. sqlcipher /data/homie_encrypted.db
5. pragma key='<db key>';
6. UPDATE Info SET DBVersion=„2.6.1“;
7. .q
8. /etc/init.d/S92homee start

**Datenbank Version ändern 2**
1. Per WS Connection setHomeeVersion?version=2.0.0 schicken

**SSH dauerhaft einschalten**
- File anlegen: vi /data/debug.sh
- Mit Inhalt:

#!/bin/sh

/etc/default/S50sshd start

- Ausführbar machen: sudo chmod +x /data/debug.sh

**FesteBüro IP**
- IP-Adresse: 80.153.231.117
- `tobias [16:48] 

IPv6-Adresse: 2003:a:87f:e70e:3631:c4ff:fe0c:fa36, Gültigkeit: 14370/1770s

IPv6-Präfix: 2003:a:867:e00::/56, Gültigkeit: 14331/14331

  

**couchdb**
- sudo /etc/init.d/couchdb status
- sudo /etc/init.d/couchdb stop
- sudo /etc/init.d/couchdb start

**zip Alexa Skill**
- zip -r skill.zip skill -x skill/descriptions/\*

**homee Proxy URL**
- proxy01.hom.ee

**Update von PC auf homee laden**
- Per SSH export.img löschen
- scp localedatei [root@192.168.178.XX](mailto:root@192.168.178.XX):/export/
- Per SSH homee rebooten

**Community start/stop/restart/rebuild**
- Per SSH auf [homee@hom.ee](mailto:homee@hom.ee)
- cd /var/discourse
- ./launcher start app
- ./launcher stop app
- ./launcher restart app
- ./launcher rebuild app
- ./launcher logs app

**SSH dauerhaft aktivieren und SSH Key hintelegen**
- /data/debug.sh erstellen:

#!/bin/sh
mount -o remount,rw /

# add SSH key

mkdir /root/.ssh

cp /data/authorized_keys /root/.ssh/authorized_keys

mount -o remount,ro /

# start SSH
/etc/default/S50sshd start
- debug.sh ausführbar machen: chmod +x /data/debug.sh
- Public SSH key in /data/autorized_key speichern

**Board name herausfinden**
- cat /sys/bdinfo/board_name

**Würfel zurücksetzen**
- PUT:settings/cubes/1?reset=1
- Z-Wave = 1, ZigBee = 2, EnOcean = 3

**Board Types**
typedef enum

{

  CABoardTypeUNKNOWN    = 0,

  CABoardTypeCubeA5     = 1,

  CABoardTypeAfrisoHome = 2,

  CABoardTypeHagerKoala = 3,

  CABoardTypeCube2      = 4

} CABoardType;

**SSH ohne Known Hosts**
- ssh root@10.11.1.2 -o UserKnownHostsFile=/dev/null -o StrictHostKeyChecking=no