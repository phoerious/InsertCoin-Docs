# Installationsanleitung

Bevor du anfängst, solltest du über ein paar Dinge Bescheid wissen. Diese sind
*S-OFF*, *CWM-Recovery*, *Schnellstart*, *ROMs* und *MD5-Summen*.

Worum handelt es sich dabei? Lass es mich kurz erklären:

S-ON ist eine Sicherheitsmaßnahme des Bootloaders, die verhindert, dass veränderte
Firmware geladen werden kann. Um InsertCoin ROM zu flashen, muss diese deaktiviert sein.
Dein Bootloader ist dann S-OFF.

CMW-Recovery ist ein Recovery-System, auch bekannt unter dem vollen Namen
*ClockworkMod Recovery*. Dieses ermöglicht es dir, die aktuelle Firmware zu sichern,
neue Firmware aus ZIP-Archiven aufzuspielen, die SD-Karte zu partitionieren,
Berechtigungen zu korrigieren, die Batterie-Statistiken zu löschen und
Ordner sowie USB-Geräte einzuhängen (d.h. zu mounten).

*Schnellstart* (Fast boot) ist eine Systemeinstellung, welche das Handy in eine Art
Schlafzustand versetzt anstatt es komplett auszuschalten. Dies beschleunigt den
Start des Gerätes, doch um InsertCoin flashen zu können, muss dies ausgestellt sein,
da du sonst nicht in den Bootloader gelangst.
Du findest die Einstellung unter *Einstellungen/Power/Schnellstart*.

ROM und MD5-Summe: Das ROM ist die Firmware, die auf deinem Gerät läuft (in diesem
Falle InsertCoin) und die MD5-Summe ist eine kryptographische Prüfsumme, die als eine
Art Fingerabdruck einer Datei fungiert. Damit kannst du sicherstellen, dass die Datei
beim Download nicht beschädigt wurde. Es ist eine gute Angewohnheit, nach jedem Download
die MD5-Summe auf Korrektheit zu überprüfen. Stimmt die Prüfsumme der heruntergeladenen
Datei nämlich nicht mit der zum Download veröffentlichten Summe überein, so kann
es sein, dass die Datei fehlerhaft ist oder sogar Schadsoftware enthält.
Um die MD5-Summe auf Korrektheit zu überprüfen, befolge diese Schritte: 

**Mac OS X:** Öffne ein Terminal und gebe folgendes ein: *openssl md5 /pfad/zur/datei.zip* 
(z.B. *openssl md5 /Users/ME/Downloads/InsertCoin_Sensation_Android_2.3.5_Stable_2_4.0.zip*)

**Linux:** Gib im Terminal diesen Befehl ein: *md5sum /pfad/zur/datei.zip*
(z.B. *md5sum /home/ME/Downloads/InsertCoin_Sensation_Android_2.3.5_Stable_2_4.0.zip*)

**Windows:** Downloade dir *md5sum.exe* und kopiere die Datei nach *C:\Windows*. Dann
öffne ein DOS-Befehlsfenster indem du im Startmenü auf „Ausführen“ klickst und dann
*cmd* eingibst. Im DOS-Problem kannst du dann das *cd*-Kommando verwenden,
um in das Verzeichnis zu navigieren, in dem die zu überprüfende Datei liegt.
Angenommen, die Datei liegt in *C:\Users\ME\My Documents\Downloads\*, so wäre das
Kommando folgendes: *cd C:\Users\ME\My Documents\Downloads\*. Anschließend tippe
*md5sum dateiname.zip*. Daraufhin wird dir die MD5-Summe der Datei angezeigt, die
du dann mit der beim Download publizierten Prüfsumme abgleichen kannst.

## Was ist ein Bootloader?
Jedes Android-Gerät hat einen Bootloader, der das Betriebssystem in den Speicher
lädt wenn das System hochgefahren wird. Jeder Hersteller benutzt dabei seinen
eigenen Bootloader, der speziell für die entsprechende Hardware optimiert wurde.

Standardmäßig sind die meisten Bootloader gesperrt und mit einer kryptographischen
Signatur geschützt. Bevor du dein eigenes ROM aufspielen kannst, musst du den
Bootloader in aller Regel also erst entsperren. Der folgende Abschnitt zeigt, wie es geht.

## Wie entsperre ich meinen Bootloader?
Es gibt im Großen und Ganzen zwei Wege, deinen Bootloader zu entsperren. Zunächst
ist da der offizielle von HTC bereitgestellte Weg, aber dies funktioniert nur auf
einigen Geräten und bringt dazu noch einige Einschränkungen mit sich (so erlaubt es dir
z.B. nur, eigene Firmware zu installieren, nicht jedoch eigene Recovery-Systeme oder
Kernel). Als zweiter Weg bietet sich „Revolutionary“ an und dies ist der einzig für
uns interessante Weg, den Bootloader zu entsperren. Das Entsperren kann schließlich
auch die Garantie erlöschen lassen und wenn du es mit dieser Variante machst, kannst
du das Handy auch wieder in den Ausgangszustand versetzen, wenn es einmal zur
Reparatur muss. Wenn du dein Handy jedoch über HTC entsperren lässt, dann weiß HTC
definitiv, dass dein Gerät schon einmal entsperrt wurde.
Mehr Informationen wie du deinen Bootloader mit „Revolutionary“ entsperrst,
findest du auf [http://revolutionary.io/](http://revolutionary.io/).

**WARNUNG: wir sind nicht verantwortlich für jedweden Schaden, der z.B. durch
das Entsperren des Boorloaders an deinem Handy entsteht. Den Bootloader zu entsperren
kann die Gerantie erlöschen lassen oder dein Gerät unbrauchbar machen. Wir können
hierfür in keiner Weise verantwortlich gemacht werden!**

## Installation
Sobald dein Bootloader entsperrt ist, können wir mit der Installation starten.
Zunächst benötigen wir die neuste ROM-Version, die du unter
[http://insertcoin-roms.org/](http://insertcoin-roms.org/) finden kannst.
Wie eigentlich überall ist es in der Regel eine gute Idee, sich die neuste Version
zu laden, da diese auch die neusten Bug-Fixes, Optimierungen etc. enthält.

Downloade die ZIP-Datei, überprüfe die MD5-Summe wie oben beschrieben und folge
achtsam den Anweisungen weier unten.

**Nochmals: wir sind nicht verantwortlich für entstandenen Schaden. Alles was du tust,
geschieht auf eigene Verantwortung!**

**Beachte außerdem, dass das „Wipen“ deines Handys ALLE Daten auf Selbigem löscht.
Mache also auf jeden Fall ein Backup bevor du fortfährst!**

### Wie flashe ich InsertCoin ROM?
 1. Stelle sicher, dass du das neuste FULL ROM hast und platziere es auf deiner SD-Karte.
 2. Boote ins Recovery-System indem du das Gerät aus- und wiedereinschaltest. Halte beim
    Wiedereinschalten die Leiser-Taste an der Seite des Geräts gedrückt (Volume down).
 3. Scrolle mit den Knöpfen der Lautstärke-Wippe zum Menü-Punkt „Recovery“ und drücke
    die Einschalttaste.
 4. Scrolle runter zu „wipe data/factory reset“ und drücke erneut den Einschaltknopf
    (alle anderen Caches werden automatisch gelöscht).
 5. Scrolle zu „install zip from your sdcard“ und drücke nochmals die Einschalttaste.
 7. Scrolle zur InsertCoin-ROM-ZIP-Dati (z.B. InsertCoin_Sensation_Android_x.x.x_Stable_x.x.x.zip)
    und drücke die Einschalttaste erneut.
 8. Warte bis die Installation beendet ist.
 9. Drücke die Zurück-Taste, wähle „reboot system now“ und drücke ein letztes Mal
    den Einschaltknopf.

Gratulation! Du hast nun erfolgreich InsertCoin ROM installiert.
 
### Wie upgrade ich von einer früheren Version?
Wenn du einen Custom-Kernel geflasht hast, dann musst du diesen nach einem InsertCoin-Upgrade
erneut flschen. Ansonsten könnte es sein, dass das Gerät anschließend nicht mehr
ordnugnsgemäß funktioniert. Downloade die ZIP-Datei deines Kernels und platziere sie
neben der InsertCoin-Datei auf der SD-Karte. Dann wiederhole die obengenannten Schritte
für beide Dateien, sofern nicht anderweitig angegeben in der Dokumentation deines Kernels.

Achtung! Ein erneuter Full-Wipe ist immer dann notwendig, wenn explizit zur jeweiligen
Version angegeben. Ansonsten ist er optional.

 1. Platziere das Update auf der SD-Karte
 2. Boote ins Recovery-System indem du das Handy ausschaltest und beim Wiedereinschalten
    die Leiser-Taste gedrückt hälst.
 3. Scrolle runter (Leiser-Taste) zum Eintrag „Recovery“ und drücke die Einschalttaste.
 4. Scolle zu „install zip from your sdcard“ und drücke die Einschalttaste.
 5. Scrolle zu „choose zip from sdcard“ und drücke erneut die Einschalttaste.
 6. Scrolle zur InsertCoin-Datei (z.B.  InsertCoin_Sensation_Android_x.x.x_Stable_x.x.x.zip)
    und drücke einmal mehr den Einschaltknopf.
 7. Warte bis die Installation beendet ist.
 8. Drücke den Zurück-Knopf, wähle „reboot system now“ und drücke ein letztes Mal
    den Power-Knopf.