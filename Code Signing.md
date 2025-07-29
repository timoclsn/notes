#work #steuerbot #app 

codesign -s "Zert Name" --entitlements "Pfad zu entitlements" "Pfad zu App" // Sign App
codesign -v --entitlements - Steuerbot.app // Codesigning prüfen 
codesign -d --entitlements - Steuerbot.app // Entitlements prüfen
security find-identity -v -p codesigning // Schauen welche Zerts. zu codesigning verfügbar sind
