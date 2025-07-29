#macos #dns #troubleshooting

# DNS Cache leeren unter macOS

## Befehl
```bash
sudo dscacheutil -flushcache
```

## Zusätzlich für mDNSResponder (empfohlen)
```bash
sudo killall -HUP mDNSResponder
```

## Kombinierter Befehl
```bash
sudo dscacheutil -flushcache && sudo killall -HUP mDNSResponder
```

## Wann nötig?
- DNS-Probleme beim Aufrufen von Websites
- Nach Änderungen an der hosts-Datei (`/etc/hosts`)
- Bei Netzwerkproblemen
- Nach DNS-Server Wechsel

## Überprüfung
Nach dem Leeren kann mit `nslookup domain.com` oder `dig domain.com` getestet werden, ob die DNS-Auflösung wieder funktioniert.