# Nintendo Switch Jailbreak Tutorial

# Was Du brauchst

- Nintendo Switch V1
- microSD-Karte (mindestens 64GB wird empfohlen)
- RCM Jig
- USB-C-Kabel
- PC/Laptop (oder ähnliches um Daten auf einer SD Karte zu bearbeiten)

# SD Karten Vorbereitung

*Wichtig: Man sollte nur Fat32 auf einer maximalen Partition von 64 GB nutzen, da man sonst nicht mehr Daten darauf schreiben kann.*

## Windows

1. Ladet euch [Fat32 Format](http://ridgecrop.co.uk/index.htm?guiformat.htm) herunter.
2. Startet die "guiformat.exe".
3. Wählt eure SD-Karte aus (z.B. "D:").
4. Falls eure SD-Karte 32 GB oder mehr hat, wählt "32768" bei "allocated unit size" aus, damit der 3DS die SD-Karte erkennen kann. (Manche SD-Karten, insbesondere ältere, könnten trotzdem nicht erkannt werden, wenn sie größer als 32 GB sind.)

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
2. Downloade das Clean RCM Pack [Clean RCM Pack](https://github.com/Nico-Shock/Clean-RCM-Pack/releases/)
3. Ziehe nun alle Daten auf das Startverzeichnis der SD-Karte.

# RCM Modus vorbereiten und starten

   1. Schiebe den RCM Jig in den rechten Joy-Con-Slot rein, bis er richtig sitzt.
   2. Halte die Lauter-Taste und den Power-Knopf gedrückt, um den RCM-Modus zu aktivieren (halte erst die Lautstärke-Taste und dann die Power-Taste gedrückt).

# Payload einfügen

   1. Lade TegraRcmGUI herunter von [TegraRcmGUI](https://github.com/eliboa/TegraRcmGUI/releases).
   2. Verbinde die Switch im RCM-Modus mit deinem PC über das USB-C-Kabel.
   3. Öffne TegraRcmGUI und wähle die Hekate Payload-Datei (es sollte eine ".bin" Datei sein).

# Hekate konfigurieren

## SD-Karte partitionieren und emuMMC erstellen

1. Wählt in Hekate `emuMMC` aus.
2. Geht dann auf `Create emuMMC`.
3. Wählt `SD Partition`.
4. Geht dann auf Continue und dann auf OK.
5. Wählt bei `emuMMC` die Balken auf "29 Full", Damit euer System komplett auf eine neue, separate Partition kopiert wird. (Man lässt es separat laufen, da es stabiler läuft und eine extreme Sicherheit bietet, da man seine "Main" Switch nicht direkt brickt. Zudem ist es sicherer, online zu spielen, wenn man im "Stock Mode" bootet.)
6. Ihr könnt auch für Android und Linux Speicher reservieren, falls ihr das installieren möchtet.
7. Geht dann auf `Next Step` und dann auf `Start` und bestätigt alles weitere, um fortzufahren. Die SD-Karte wird partitioniert.
8. Geht dann nochmal auf `Create emuMMC` und dann auf `SD Partition` und wählt Part 1 (falls ihr mehrere Parts auswählen könnt, wählt alle einmal aus. Der Vorgang kann pro Part etwa 10-15 Minuten dauern.)

## Backup der NAND

1. Geht dann oben auf Tools.
2. Wählt dann `Backup eMMC`.
3. Wenn ihr wollt, könnt ihr die Option anschalten mit `SD emuMMC Raw Partition` (ich lasse es hier aus).
4. Wählt dann die Option auf der linken Seite `eMMC BOOT0 & BOOT1` und wartet, bis es fertig ist.
5. Wählt dann darunter `eMMC RAW GPP` und wartet, bis es fertig ist (dies dauert je nach Menge der Daten auf eurem System unterschiedlich lange; Durchschnitt: 10-15 Minuten).
6. Schaltet dann die Switch aus und geht mit der SD-Karte an euren PC.
7. Kopiert alle gebackupten Daten in einen Ordner auf eurem PC (es müssten 15 rawnand.bin Dateien auf der SD-Karte sein (0-14) und die BOOT0 und BOOT1-Dateien).
8. Löscht dann diese Dateien von eurer SD-Karte.

## Wiederherstellung der NAND

1. Kopiert die gebackupten Dateien und packt sie in `restore` dann `emummc` auf der SD-Karte.
2. Wenn ihr dann in Hekate seid, könnt ihr unter Tools "Restore eMMC" wählen.
3. Wählt dann `eMMC BOOT0 & BOOT1` und `eMMC RAW GPP` aus, um die Wiederherstellung durchzuführen.

## Falls ihr Linux oder Android installieren wollt:
1. Ladet [Switchroot Ubuntu](https://download.switchroot.org/ubuntu-bionic/) oder [Switchroot Android](https://download.switchroot.org/android-11/) herunter (wählt dann die aktuelle `Switchroot Ubuntu.7z` oder `Switchroot Android.7z`) und zieht die Ordner `switchroot` und `bootloader` auf eure SD-Karte.
   
2. Geht dann in Hekate, nachdem ihr eure SD-Karte formatiert habt (wie im vorherigen Schritt), und wählt danach "Flash Linux" aus (ihr solltet noch im Formatierungsschritt sein, also das Fenster nicht geschlossen haben, sonst formatiert ihr einfach alles neu), um Linux zu installieren (euer SwitchOS wird nicht überschrieben).
Ihr könnt auch "SD UMS" wählen, um eure SD-Karte am PC zu bearbeiten, ohne sie aus eurer Switch herauszunehmen.

## Immer im RCM-Modus starten

1. In Hekate geht wieder auf Tools.
2. Geht dann ganz unten rechts auf irgendetwas mit "Arch Bit - RCM".
3. Und wählt ganz rechts oben AutoRCM aus. (Auto RCM wird nicht empfohlen, da ihr eure Switch nach dem Ausschalten NUR durch das Laden eines Custom Payloads wieder starten könnt.)

## Auto Boot konfigurieren

1. Geht oben rechts auf "Optionen" und wählt "Auto Boot" und wählt im besten Fall "Atmosphere (EmuNAND)" aus.
2. Ihr könnt das Boot-Logo in der Option darunter auch ausschalten (um wieder ins Hekate-Menü zu kommen, haltet die Lautstärke nach unten Taste gedrückt und sendet dann den Payload, bis ihr in Hekate startet).

# CFW Atmosphere Laden

1. Geht in Hekate unter Home auf "Launch" und wählt "Atmosphere emuMMC" aus, um dort hinein zu booten.

# Homebrew laden

   - Du kannst Homebrew über das Album starten oder R gedrückt halten und ein legitimes Spiel starten, um Homebrew mit Admin-Rechten zu starten und darüber eine App öffnen.
   - Du kannst über den Homebrew-Appstore auch neue Apps herunterladen und nutzen.

# Switch Ban (möglichst) vermeiden

1. Geht dann in das Album in der CFW, um Homebrew zu öffnen, und wählt "90dns setter" aus.
2. Drückt dann "X", um die DNS-Einstellungen für jedes Internet einzustellen, und wählt "Y", um neu zu starten.
3. Wählt dann im Homebrew-Menü "90dns testing utility" und prüft, ob die Nintendo-Services geblockt wurden.

# **WICHTIG!!!**

SPIELT NICHT ONLINE, LADET KEINE UPDATES HERUNTER UND INTERAGIERT GENERELL NICHT MIT DEN NINTENDO SERVERN WIE NINTENDO E-SHOP ODER NINTENDO SWITCH ONLINE, SONST WERDET IHR ONLINE GEBANNT ODER EURE KONSOLE WIRD KOMPLETT GEBANNT. UM ZUGANG ZU DEN NINTENDO SERVERN IN DER CFW ZU VERHINDERN, FOLGT DEM SCHRITT HIER ÜBER DIESEM TEXT.

BITTE LADET EUCH KEINE ROMS ONLINE RUNTER UND VERSTÖßT NICHT GEGEN PIRATERIE (Piracy) UND ERWIRBT DIE SPIELE ALLE LEGAL SELBST, INDEM IHR SIE EUCH KAUFT. ALLE SPIELE, DIE ICH SPIELE, BESITZE ICH SELBST UND HABE SIE MIR LEGAL ERWORBEN.
ICH UNTERSTÜTZE KEINE PIRATERIE (Piracy) UND MÖCHTE NICHT, DASS ANDERE HIERDURCH DAZU VERLEITET WERDEN, SPIELE ILLEGAL ZU BESITZEN UND ZU SPIELEN.
