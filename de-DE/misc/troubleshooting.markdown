# Fehlerbehebung
Diese Seite gibt Anleitung zur Lösung bekannter Probleme mit InsertCoin.

## Market-Probleme

* **Problem:** App-Downloads aus dem Market werfen den Fehler
  „Error downloading <application name>. There insufficient space on the device.“
  (TODO: Fehlermeldung übersetzen)
  
  **Fix:** Boote ins Recovery-System, scrolle zu „wipe cache partition“ und dann zu
  „advanced“. Führe den Wipe aus, dann scrolle runter zu „wipe dalvik cache“,
  führe auch dies aus, dann gehe zurück und wähle “reboot system” .
  
* **Problem:** Fehlermeldung „Insufficient storage space“ beim Downloaden oder der
  Installation einer App (TODO: Fehlermeldung übersetzen)
  
  **Fix:** Gehe in die Einstellungen und klicke auf „Anwendungen verwalten“.
  Dann wähle den Tab „Alle“ aus, scrolle runter zum Download-Manager, öffne ihn
  und tippe auf „Daten löschen“. Diese Anwendungsdaten sollten nur ein paar hundert KB sein.
  Das Löschen dieser Daten hat keine Auswirkungen auf andere Apps. Sollte dies das
  Problem nicht lösen, so probiere den Fix #1.
  
* **Problem:** Der Market hängt bei „Authourizing Purchase” (TODO: Meldung übersetzen).
  
  **Fix:** Dies ist nicht wirklich ein InsertCoin-Problem, sondern mehr eines des Google-Backends.
  Es gibt nichts, was wir da tun könnten. Der Market scheint nicht gut mit parallelen
  App-Downloads zurechtzukommen. Wenn du mehr als 5 oder 6 Apps auf einmal lädtst,
  kann dieses Problem auftreten. Versuche, weniger Apps auf einmal zu laden.


## Probleme mit WIFI

* **Problem:** Ich kann im Flugmodus kein Wifi anstellen
  
  **Fix:** Hierfür gibt es keinen offiziellen Fix, da dies exakt das ist, wofür der
  Flugmodus kreiert wurde, nämlich alle Drahtlosdienste (Funk-/Datenverbindung, Bluetooth
  und Wifi) auszuschalten.
  Du kannst allerdings eine App wie „Airplane Edit“ aus dem
  [Market](https://market.android.com/details?id=net.cenkalti.airplane&feature=search_result)
  nutzen. Das könnte dein Problem lösen.


## SD-Karten-Probleme:

* **Problem:** Ich habe eine neue SD-Karte gekauft, aber das Gerät erkennt diese nicht.
  Ich habe sie unter Windows formatiert und am PC funktioniert sie. Hilfe!
  
  **Fix:** Überprüfe bitte, dass die gekaufte SD-Karte mit deinem Handy kompatibel ist.
  Prüfe außerdem, dass sie als FAT32 formatiert wurde. Windows formatiert gern
  standardmäßig als NTFS. Dies funktioniert jedoch nicht mit Android und das ist meist
  auch der Grund, warum die Karte am PC funktioniert, auf dem Handy aber nicht.
  Dein Handy funktioniert nur mit FAT32-formatierten Karten.
  Anmerkung: kaufe dir am besten immer die schnellste SD-Karte, die du dir leisten kannst.
  Alles über „Class 6“ sollte in Ordnung sein. Je höher die Klasse, desto besser.


## Weitere Probleme

* **Problem:** In der Nachrichten-App werden keine Kontaktbilder angezeigt.
  
  **Fix:** Dieses Problem tritt häufiger auf und kann verschiedene Ursachen haben.
  Nicht selten ist Titanium Backup Schuld. Das Problem lässt sich jedoch recht einfach
  beheben, indem du die Rechte für das Kontakte-Verzeichnis korrigierst.
  Dazu installiere einen [Terminal-Emulator]((https://market.android.com/details?id=jackpal.androidterm)),
  öffne ihn und tippe folgenden Befehl ein:
  **su; chmod 666 /data/data/com.android.providers.contacts/files/*; exit** (tippe ihn
  *exakt* so ein, wie er hier steht, Groß- und Kleinschreibung sowie Interpunktion sind
  wichtig!). Sobald du Enter tippst, wird dich die Superuser-App fragen, ob du der
  Terminal-App root-Rechte gewähren willst. Bestätige dies, schließe den Terminal-Emulator
  und starte die Nachrichten-App neu. Du solltest nun wieder die gewohnten Kontaktbilder
  sehen.