# Nintendo Switch Jailbreak Tutorial

# Was Du brauchst

- Nintendo Switch V1
- MicroSD Karte (mindestens 64GB)
- RCM Jig
- USB-C Kabel 
- PC/Laptop (oder ein anderes Gerät, um Daten auf einer SD Karte zu bearbeiten)

![Benötigte Items](https://github.com/user-attachments/assets/ac79dfec-e526-4aed-b3bd-01d51bd5d0fe)

# SD Karten Vorbereitung

Wichtig: Man sollte nur FAT32 auf einer maximalen Partition von 64 GB nutzen, da man sonst nicht mehr Daten darauf schreiben kann. Nutzt ansonsten exFAT, das ihr ganz normal über den Windows Explorer formatieren könnt. In macOS und Linux wählt ihr exFAT statt Fat32 in den Schritten hier drunter als Dateisystem aus.

## Windows

1. Ladet euch [Fat32 Format](http://ridgecrop.co.uk/index.htm?guiformat.htm) herunter.
2. Startet die "guiformat.exe".
3. Wählt eure SD Karte aus (z.B. "D:").
4. Startet des prozess um eure SD Karte zu Formatieren.

## MacOS

1. Startet das "Festplattendienstprogramm".
2. Rechtsklickt auf die SD Karte und wählt dann "Löschen" aus. Formatiert sie als Fat32 (es wird eventuell als "MS-DOS-Dateisystem" angezeigt).
3. Wählt anschließend "Löschen".

## Linux

1. Öffnet die "Disk" App.
2. Wählt die Festplatte aus, klickt dann auf das Zahnradsymbol oder macht einen Rechtsklick und wählt "Formatieren".
3. Wählt beim Typ "Fat32" aus (eventuell müsst ihr unter "Other" oder "Weitere" nach Fat32 suchen).

# Seriennummer prüfen

Stelle sicher, dass man deine Switch jailbreaken kann. [IsMySwitchPatched](https://ismyswitchpatched.com/).

- Ihr könnt eure Seriennummer unter eurer Switch sehen, den ihr eingeben könnt.
  Falls ihr die Seriennummer dort nicht habt, geht auf "System Einstellungen", dann auf "Konsole" und dann auf "Seriennummer", und könnt sie dort sehen.

- Unpatched Switch bedeutet, dass ihr eure Switch zu 100% hacken könnt mit dieser Methode. Falls es später nicht funktioniert, habt IHR etwas falsch gemacht.

- Falls ihr eine Possible Patched Switch habt, könnte der Payload funktionieren, könnte aber auch nicht. Man kann es daran erkennen, dass man in TegraRCM das Fenster „RCM OK“ hat und wenn man den Payload einfügt, dass die Switch Schwarz bleibt.
  
- Falls ihr eine gepatchte Switch habt, wird es zu 100 % NICHT funktionieren. Ihr benötigt auf jeden Fall einen Modchip, der mit Mikrolöten und empfindlicher Hardware zu tun hat, was riskant ist und erweitertes Wissen mit sich bringt.

# SD Karten Setup

1. Schalte die Switch aus, indem du 3 Sekunden lang den "Power Knopf" gedrückt hältst und unter Power Optionen "Ausschalten" wählst.

![Ausschalten Screen](https://github.com/user-attachments/assets/f2b1c464-d09e-4aa9-8d71-36d20a983684)

2. Downloade das [Grey-NX Pack](https://github.com/Nico-Shock/Grey-NX-Pack)
3. Ziehe nun alle Daten auf das Startverzeichnis der SD Karte.

![SD Karten Dateien](https://github.com/user-attachments/assets/2a9ef113-15a3-4895-8704-bf9794347da5)

# RCM Modus vorbereiten und starten

   1. Schiebe den RCM Jig in den rechten Joy Con Slot rein, bis er richtig sitzt.
   2. Halte die Lauter Taste und den Power Knopf gedrückt, um den RCM Modus zu aktivieren (halte erst die Lautstärke Taste und dann die Power Taste gedrückt).

![RCM jig + USB](https://github.com/user-attachments/assets/88bd845c-6f84-468c-a589-5c16a89e4d9f)

# Payload einfügen

1. Lade TegraRcmGUI [hier](https://github.com/eliboa/TegraRcmGUI/releases/latest) herunter.
2. Verbinde die Switch im RCM Modus mit deinem PC über das USB-C Kabel.
3. Öffnet TegraRcmGUI.exe

![TegraRCM exe](https://github.com/user-attachments/assets/62bb7888-46cc-4c92-8776-6cab05ca9b8c)

4. Gehe unter "Tools" auf "Install Driver", um die APX Treiber zu installieren, damit dein PC die Switch erkennen kann. (Es sollte ein grünes Feld erscheinen mit "RCM OK", was bedeutet, dass die Switch erfolgreich im RCM Modus ist und von deinem PC erkannt wurde.)

![TegraSettings](https://github.com/user-attachments/assets/285bcd27-9818-4c15-85f0-7a64cef7ab83)

Ihr könnt unter "Tools" auch "Run App at Startup", "Minimize to Tray" und "Auto Inject Payload" aktivieren, damit man z.B. den Payload automatisch immer sendet oder die App beim Hochfahren automatisch startet.

5. Öffne TegraRcmGUI und mache einen Doppelklick auf die Datei "hekate_ctcaer_5.0.0.bin" oder neuer (oder wähle sie manuell über das kleine Ordnersymbol aus und klicke auf "Inject Payload"). Eure Switch sollte nun in Hekate booten.

![Hekate Boot](https://github.com/user-attachments/assets/9d6224e7-9919-43d9-aa2b-7b692702088c)

# Hekate konfigurieren

## SD Karte partitionieren und emuMMC erstellen

1. Wählt in Hekate "Tools" aus.
2. Wählt dann "Partition SD"
3. Wählt bei "emuMMC" den Balken auf "29 Full", damit euer System komplett auf eine neue, separate Partition kopiert wird. (Ihr könnt auch für Android und Linux eine Partition erstellen, falls ihr das installieren möchtet.)
4. Geht dann auf "Next Step" und dann auf "Start" und bestätigt alles weitere, um fortzufahren um die SD Karte zu partitionieren.
5. Geht dann nochmal auf "Create emuMMC" und dann auf "SD Partition" und wählt Part 1. (Falls ihr mehrere Partitionen habt, habt ihr über "29 FULL" ausgewählt und 2 Partitionen erstellt oder eure SD Karte hatte generell von Anfang an 2 Partitionen.)

Man erstellt eine EmuMMC Partition, da es sicherer ist, weil das "Switch-OS" separat läuft, z.B. wird es vor Bricks geschützt und man minimiert die Wahrscheinlichkeit, gebannt zu werden.

https://github.com/user-attachments/assets/321794e3-a51c-4480-b8a7-c803a664ec6d

https://github.com/user-attachments/assets/8f381c94-6d2b-4a11-b05e-087c4c25cbe0

## Backup der NAND

1. Geht oben auf Tools.
2. Wählt dann "Backup eMMC". (Ihr werdet eine Option finden, die "SD emuMMC Raw Partition" heißt. Wenn ihr diese aktiviert, wird die NAND statt aus dem SysNAND vom EmuNAND gebackupt, was normalerweise aber nicht nötig ist.)
3. Wählt dann die Option auf der linken Seite "eMMC BOOT0 & BOOT1" und wartet, bis es fertig ist.
4. Wählt dann darunter "eMMC RAW GPP" und wartet, bis es fertig ist (dieser Vorgang dauert durchschnittlich 10-15 Minuten, je nach der Menge an Daten auf eurer Switch.)
5. Schaltet dann die Switch aus und geht mit der SD Karte an euren PC.
6. Kopiert alle gebackupten Daten in einen Ordner auf eurem PC (Ihr habt vielleicht nur eine "rawnand.bin". Manchmal werden die Dateien gesplittet.)
7. Löscht dann diese Dateien von eurer SD Karte.

https://github.com/user-attachments/assets/519954b8-f653-460f-8a7c-23a3ad105ab2

![NAND backup](https://github.com/user-attachments/assets/a3070931-1c9b-4ae2-bd97-2a919b057b53)

## Wiederherstellung der NAND

1. Kopiert die zuvor gebackupten Dateien auf eure SD Karte in den "backup" Ordner unter "restore", wenn ihr euren SysNAND wiederherstellen wollt. Für den EmuNAND müsst ihr die Dateien dann in einen weiteren Unterordner "emummc" unter "restore" (nicht den "partitions" Ordner) kopieren.
2. Geht dann in Hekate und wählt unter "Tools" die Option "Restore eMMC" aus.
3. Wählt dann "eMMC BOOT0 & BOOT1" und "eMMC RAW GPP" aus, um die NAND wiederherzustellen.

Hier müsst ihr wieder "SD emuMMC Raw Partition" auswählen, falls ihr statt euren SysNAND euren EmuNAND wiederherstellen wollt.

## Falls ihr Linux oder Android installieren wollt:

1. Ladet [Switchroot Ubuntu](https://download.switchroot.org/ubuntu-bionic/) oder [Switchroot Android](https://download.switchroot.org/android-10/) herunter (wählt dann die aktuelle "Switchroot Ubuntu.7z" oder "Switchroot Android.7z") und kopiert alle Ordner aufs Startverzeichniss eurer SD Karte.
2. Geht dann in Hekate, unter "Tools" auf "Partition SD" und wählt anschließend "Flash Linux" und oder "Flash Android" aus (dies wird die Dateien auf die erstellte Linux oder Android Partition flashen).

## Immer im RCM Modus starten

1. In Hekate geht wieder auf Tools.
2. Geht dann ganz unten rechts auf die zweite Seite mit "Arch Bit - RCM - Touch - Pkg1/2".
3. Und wählt ganz rechts oben AutoRCM aus. (Auto RCM wird nicht empfohlen, da ihr eure Switch nach dem Ausschalten NUR durch das Laden eines Custom Payloads wieder starten könnt.)

## Auto Boot konfigurieren

1. Geht oben rechts auf "Optionen" und wählt "Auto Boot" und wählt im besten Fall "BootCFW (EmuNAND)" aus.
2. Ihr könnt das Boot Logo in der Option darunter auch ausschalten (um wieder ins Hekate Menü zu kommen, haltet die Lautstärke nach unten Taste gedrückt und sendet dann den Payload, bis ihr in Hekate startet).

https://github.com/user-attachments/assets/13d5aca0-f560-4f9b-9a5c-bb18d6ac723d

# CFW Atmosphere Laden

1. Geht in Hekate unter Home auf "Launch" und wählt "BootCFW (EmuNAND)" aus, um dort rein zu booten.

# Homebrew laden

- Du kannst das Homebrew Menü über das Album starten oder die R Taste gedrückt halten und ein legitimes Spiel starten, um das Homebrew Menü mit Admin Rechten zu starten und darüber deine Homebrew Apps zu starten.
- Du kannst über den Homebrew Appstore auch neue Apps herunterladen und installieren.
- Der Unterschied zwischen dem Applet Modus (Album) und der Application im Homebrew ist, dass es über ein Spiel (Application) vollen Zugriff auf die Systemressourcen hat und nur so manche Sachen nutzbar sind, wie z.B. RetroArch.

# Switch Ban möglichst vermeiden

1. Geht dann in das Album in der CFW, um Homebrew zu öffnen, und wählt "90dns setter" aus.
2. Drückt dann "X", um die DNS Einstellungen für jedes Internet einzustellen, und wählt "Y", um neu zu starten.
3. Wählt dann im Homebrew Menü "90dns testing utility" und prüft, ob die Nintendo Services geblockt wurden.
4. Ihr könnt auch unter den Systemeinstellungen auf "Konsole" gehen und die Option "Fehlerinformationen senden" ausschalten (im besten Fall auch im SysNand oder im Stock Modus).

*Wichtig: Man kann trotzdem immer gebannt werden, obwohl man alles richtig gemacht hat, z.B. die Server blockiert, keine Anwendungen ins Home Menü installiert hat usw. In dem Moment, wo man sich mit den Nintendo Servern verbindet, ohne CFW Daten, ohne installierte Dinge oder ohne SD Karte oder anderes, kann es trotzdem zu einem Bann kommen.*

https://github.com/user-attachments/assets/f7966fc4-e599-4ec1-8789-d0bbb2a133b3

# optionale NSPs/XCI Dateien installieren

1. Öffnet im Homebrew Menu "DBI" (oder andere Apps, die ähnlich oder genau so funktionieren wie z.B. Goldleaf oder Tinfoil).
2. Geht auf "Browse SD" und wählt dann in den Verzeichnissen die Dateien aus, die ihr installieren wollt.
3. Wenn ihr die Dateien ausgewählt habt, installiert ihr das auf die *"WICHTIG":* SD Karte und NICHT auf die NAND, da ihr später einen potenziellen Bann bekommen könnt. Wenn ihr wollt, könnt ihr die Datei danach löschen ihr braucht sie so oder so nicht mehr.

# **WICHTIG!!!**

### *SPIELT NICHT ONLINE, LADET KEINE UPDATES HERUNTER UND INTERAGIERT GENERELL NICHT MIT DEN NINTENDO SERVERN WIE NINTENDO E-SHOP ODER NINTENDO SWITCH ONLINE, SONST WERDET IHR ONLINE GEBANNT ODER EURE KONSOLE WIRD KOMPLETT GEBANNT. BITTE LADET EUCH KEINE ROMS ONLINE RUNTER UND VERSTÖßT NICHT GEGEN PIRATERIE (Piracy) UND ERWIRBT DIE SPIELE ALLE LEGAL SELBST, INDEM IHR SIE EUCH KAUFT. ALLE SPIELE, DIE ICH SPIELE, BESITZE ICH SELBST UND HABE SIE MIR LEGAL ERWORBEN. ICH UNTERSTÜTZE KEINE PIRATERIE (Piracy) UND MÖCHTE NICHT, DASS ANDERE HIERDURCH DAZU VERLEITET WERDEN, SPIELE ILLEGAL ZU BESITZEN UND ZU SPIELEN.*
