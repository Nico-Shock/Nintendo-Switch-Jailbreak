# Nintendo Switch Jailbreak Tutorial

# Was Du brauchst

- Nintendo Switch V1
- microSD-Karte (mindestens 64GB wird empfohlen)
- RCM Jig
- USB-C-Kabel 
- PC/Laptop (oder ähnliches um Daten auf einer SD Karte zu bearbeiten)

![Benötigte Items](https://github.com/user-attachments/assets/ac79dfec-e526-4aed-b3bd-01d51bd5d0fe)

# SD Karten Vorbereitung

*Wichtig: Man sollte nur Fat32 auf einer maximalen Partition von 64 GB nutzen, da man sonst nicht mehr Daten darauf schreiben kann. Nutzt ansonsten exFAT, das ihr mit einem Rechtsklick unter Windows auf "Formatieren" formatieren könnt. Unter macOS und Linux wählt einfach nur exFAT als Dateisystem bei den folgenden Schritten hier drunter aus.*

## Windows

1. Ladet euch [Fat32 Format](http://ridgecrop.co.uk/index.htm?guiformat.htm) herunter.
2. Startet die "guiformat.exe".
3. Wählt eure SD-Karte aus (z.B. "D:").

## MacOS

1. Startet das "Festplattendienstprogramm".
2. Rechtsklickt auf die SD-Karte und wählt dann "Löschen" aus. Formatiert sie als Fat32 (es wird eventuell als "MS-DOS-Dateisystem" angezeigt).
3. Wählt anschließend "Löschen".

## Linux

1. Öffnet die "Disk" App.
2. Wählt die Festplatte aus, klickt dann auf das Zahnradsymbol oder macht einen Rechtsklick und wählt "Formatieren".
3. Wählt beim Typ "Fat32" aus (eventuell müsst ihr unter "Other" oder "Weitere" nach Fat32 suchen).

# Seriennummer prüfen

Stelle sicher, dass man deine Switch jailbreaken kann. [IsMySwitchPatched](https://ismyswitchpatched.com/).

- Ihr könnt eure Seriennummer unter eurer Switch auf einem Zettel sehen, den ihr eingeben könnt.
  Falls ihr die Seriennummer dort nicht habt, geht auf System-Einstellungen, dann auf "Konsole" und dann auf "Seriennummer", und könnt sie dort sehen.

- Unpatched Switch bedeutet, dass ihr eure Switch zu 100% hacken könnt mit dieser Methode. Falls es später nicht funktioniert, habt IHR etwas falsch gemacht.

- Falls ihr eine Possible Patched Switch habt, könnte der Payload funktionieren, könnte aber auch nicht. Man kann es daran erkennen, dass man in TegraRCM das Fenster „RCM OK“ hat und wenn man den Payload einfügt, dass die Switch Schwarz bleibt.
  
- Falls ihr eine Patched Switch habt, wird es zu 100% NICHT funktionieren. Ihr benötigt aufjedenfall einen Modchip, den ihr in die Switch verlötet, was erweitertes Wissen und Risiko mit sich bringt. Wenn ihr einen Modchip installiert, benötigt ihr nur eine SD-Karte mit den Daten vom „Clean RCM Pack“. Aber nur Switch V1 werden funktionieren mit den Daten, also unpatched Switches. Für andere Modelle (Switch V2, OLED oder LITE) benötigt ihr andere Daten.

# SD Karten Setup

1. Schalte die Switch aus, indem du 3 Sekunden lang den Power-Knopf gedrückt hältst und unter Power Optionen "Ausschalten" wählst.

![Ausschalten Screen](https://github.com/user-attachments/assets/f2b1c464-d09e-4aa9-8d71-36d20a983684)

2. Downloade das Clean RCM Pack [Clean RCM Pack](https://github.com/Nico-Shock/Clean-RCM-Pack/releases/)
3. Ziehe nun alle Daten auf das Startverzeichnis der SD-Karte.

![SD Karten Dateien](https://github.com/user-attachments/assets/2a9ef113-15a3-4895-8704-bf9794347da5)

# RCM Modus vorbereiten und starten

   1. Schiebe den RCM Jig in den rechten Joy-Con-Slot rein, bis er richtig sitzt.
   2. Halte die Lauter-Taste und den Power-Knopf gedrückt, um den RCM-Modus zu aktivieren (halte erst die Lautstärke-Taste und dann die Power-Taste gedrückt).

![RCM jig + USB](https://github.com/user-attachments/assets/88bd845c-6f84-468c-a589-5c16a89e4d9f)

# Payload einfügen

1. Lade TegraRcmGUI herunter von [TegraRcmGUI](https://github.com/eliboa/TegraRcmGUI/releases).
2. Verbinde die Switch im RCM-Modus mit deinem PC über das USB-C-Kabel.
3. Öffnet TegraRcmGUI.exe

![TegraRCM exe](https://github.com/user-attachments/assets/62bb7888-46cc-4c92-8776-6cab05ca9b8c)

4. Gehe unter "Tools" auf "Install Driver", um die APX-Treiber zu installieren, damit dein PC die Switch erkennen kann. (Es sollte ein grünes Feld erscheinen mit "RCM OK", was bedeutet, dass die Switch erfolgreich im RCM-Modus ist und von deinem PC erkannt wurde.)

![TegraSettings](https://github.com/user-attachments/assets/285bcd27-9818-4c15-85f0-7a64cef7ab83)

Ihr könnt unter "Tools" auch "Auto Boot at startup", "Minimize to Tray" und "Auto Inject Payload" aktivieren, damit der Payload automatisch gesendet wird, sobald ihr eure Switch mit dem USB-C Kabel verbindet.

5. Öffne TegraRcmGUI und mache ein doppelklick die Datei "hekate_ctcaer_5.0.0.bin" (oder wählt sie manuell aus und wählt "Inject Payload") Eure Switch sollte nun in Hekate Booten.

![Hekate Boot](https://github.com/user-attachments/assets/9d6224e7-9919-43d9-aa2b-7b692702088c)

# Hekate konfigurieren

## SD-Karte partitionieren und emuMMC erstellen

1. Wählt in Hekate `Tools` aus.
2. Wählt dann `Partition SD` (Ihr müsst die heruntergeladenen Daten nochmal auf eure SD-Karte ziehen, WENN ihr ein größeres Pack heruntergeladen habt, da beim Partitionieren nicht mehr als 1 GB an Daten gebackupt werden können und alles von eurer SD Karte gelöscht wird.)
3. Wählt bei `emuMMC` die Balken auf "29 Full", Damit euer System komplett auf eine neue, separate Partition kopiert wird. (Man lässt es separat laufen, da es stabiler läuft und eine extreme Sicherheit bietet, da man seine "Main" Switch nicht direkt brickt. Zudem ist es sicherer, online zu spielen, wenn man im "Stock Mode" bootet.)
4. Ihr könnt auch für Android und Linux eine Partition erstellen, falls ihr das installieren möchtet.
5. Geht dann auf `Next Step` und dann auf `Start` und bestätigt alles weitere, um fortzufahren. Die SD-Karte wird partitioniert.
6. Geht dann nochmal auf `Create emuMMC` und dann auf `SD Partition` und wählt Part 1 (falls ihr mehrere Parts auswählen könnt, wählt alle einmal aus. Der Vorgang kann pro Part etwa 10-15 Minuten dauern.)

https://github.com/user-attachments/assets/321794e3-a51c-4480-b8a7-c803a664ec6d

https://github.com/user-attachments/assets/8f381c94-6d2b-4a11-b05e-087c4c25cbe0

## Backup der NAND

1. Geht dann oben auf Tools.
2. Wählt dann `Backup eMMC`.
3. Wenn ihr wollt, könnt ihr die Option anschalten mit `SD emuMMC Raw Partition` (ich lasse es hier aus).
4. Wählt dann die Option auf der linken Seite `eMMC BOOT0 & BOOT1` und wartet, bis es fertig ist.
5. Wählt dann darunter `eMMC RAW GPP` und wartet, bis es fertig ist (dies dauert je nach Menge der Daten auf eurem System unterschiedlich lange; Durchschnitt: 10-15 Minuten).
6. Schaltet dann die Switch aus und geht mit der SD-Karte an euren PC.
7. Kopiert alle gebackupten Daten in einen Ordner auf eurem PC (es müssten 15 rawnand.bin Dateien auf der SD-Karte sein (0-14) und die BOOT0 und BOOT1-Dateien).
8. Löscht dann diese Dateien von eurer SD-Karte.

https://github.com/user-attachments/assets/519954b8-f653-460f-8a7c-23a3ad105ab2

![NAND backup](https://github.com/user-attachments/assets/a3070931-1c9b-4ae2-bd97-2a919b057b53)

## Wiederherstellung der NAND

1. Kopiert die gebackupten Dateien und packt sie in `restore` dann `emummc` auf der SD-Karte.
2. Wenn ihr dann in Hekate seid, könnt ihr unter Tools "Restore eMMC" wählen.
3. Wählt dann `eMMC BOOT0 & BOOT1` und `eMMC RAW GPP` aus, um NAND wiederherzustellen.

## Falls ihr Linux oder Android installieren wollt:

1. Ladet [Switchroot Ubuntu](https://download.switchroot.org/ubuntu-bionic/) oder [Switchroot Android](https://download.switchroot.org/android-11/) herunter (wählt dann die aktuelle `Switchroot Ubuntu.7z` oder `Switchroot Android.7z`) und kopiert die Ordner `switchroot` und `bootloader` auf eure SD-Karte.
2. Geht dann in Hekate, unter "Tools" auf "Partition SD" und wählt anschließend "Flash Linux" oder "Flash Android" aus (dies wird die Dateien auf die erstellte Linux- oder Android-Partition flashen).

Falls ihr die Partitionen noch nicht habt, sichert die Daten eurer SD-Karte und partitioniert eure SD-Karte neu (durch das Partitionieren werden alle Daten außer den Bootloader Daten gelöscht, oder bis zu 1 GB Daten können gesichert werden).

## Immer im RCM-Modus starten

1. In Hekate geht wieder auf Tools.
2. Geht dann ganz unten rechts auf irgendetwas mit "Arch Bit - RCM".
3. Und wählt ganz rechts oben AutoRCM aus. (Auto RCM wird nicht empfohlen, da ihr eure Switch nach dem Ausschalten NUR durch das Laden eines Custom Payloads wieder starten könnt.)

## Auto Boot konfigurieren

1. Geht oben rechts auf "Optionen" und wählt "Auto Boot" und wählt im besten Fall "Atmosphere (EmuNAND)" aus.
2. Ihr könnt das Boot-Logo in der Option darunter auch ausschalten (um wieder ins Hekate-Menü zu kommen, haltet die Lautstärke nach unten Taste gedrückt und sendet dann den Payload, bis ihr in Hekate startet).

https://github.com/user-attachments/assets/13d5aca0-f560-4f9b-9a5c-bb18d6ac723d

# CFW Atmosphere Laden

1. Geht in Hekate unter Home auf "Launch" und wählt "Atmosphere (EmuNAND)" aus, um dort rein zu booten.

# Homebrew laden

   - Du kannst Homebrew über das Album starten oder R gedrückt halten und ein legitimes Spiel starten, um Homebrew mit Admin-Rechten zu starten und darüber eine App öffnen.
   - Du kannst über den Homebrew-Appstore auch neue Apps herunterladen und nutzen.

# Switch Ban vermeiden

1. Geht dann in das Album in der CFW, um Homebrew zu öffnen, und wählt "90dns setter" aus.
2. Drückt dann "X", um die DNS-Einstellungen für jedes Internet einzustellen, und wählt "Y", um neu zu starten.
3. Wählt dann im Homebrew-Menü "90dns testing utility" und prüft, ob die Nintendo-Services geblockt wurden.
4. Ihr könnt auch unter den Systemeinstellungen auf "Konsole" gehen und die Option "Fehlerinformationen senden" ausschalten (im besten Fall auch im SysNand oder im Stock-Modus).

https://github.com/user-attachments/assets/f7966fc4-e599-4ec1-8789-d0bbb2a133b3

# **WICHTIG!!!**

SPIELT NICHT ONLINE, LADET KEINE UPDATES HERUNTER UND INTERAGIERT GENERELL NICHT MIT DEN NINTENDO SERVERN WIE NINTENDO E-SHOP ODER NINTENDO SWITCH ONLINE, SONST WERDET IHR ONLINE GEBANNT ODER EURE KONSOLE WIRD KOMPLETT GEBANNT. UM ZUGANG ZU DEN NINTENDO SERVERN IN DER CFW ZU VERHINDERN, FOLGT DEM SCHRITT HIER ÜBER DIESEM TEXT.

BITTE LADET EUCH KEINE ROMS ONLINE RUNTER UND VERSTÖßT NICHT GEGEN PIRATERIE (Piracy) UND ERWIRBT DIE SPIELE ALLE LEGAL SELBST, INDEM IHR SIE EUCH KAUFT. ALLE SPIELE, DIE ICH SPIELE, BESITZE ICH SELBST UND HABE SIE MIR LEGAL ERWORBEN.
ICH UNTERSTÜTZE KEINE PIRATERIE (Piracy) UND MÖCHTE NICHT, DASS ANDERE HIERDURCH DAZU VERLEITET WERDEN, SPIELE ILLEGAL ZU BESITZEN UND ZU SPIELEN.
