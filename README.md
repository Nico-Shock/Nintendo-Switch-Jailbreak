# Nintendo Switch Jailbreak Totorial

## Updates
- Ich werde noch Bilder hinzufügen wenn ich meine Switch V1 habe
- ich versuche den text möglich genau anzupassen bzw. ich werde ihn verbessern

# Was Du brauchst

- Nintendo Switch V1
- microSD-Karte (mindestens 64GB wird empfohlen)
- RCM Jig
- USB-C-Kabel
- PC/Laptop (oder ähnliches um Daten auf einer SD Karte zu bearbeiten)

# SD Karten Vorbereitung

## Windows:

Um die SD-Karte auf `Fat32` zu formatieren, führe die folgenden Schritte aus:

1. Rechtsklicke auf die SD-Karte und wähle `Formatieren`.
2. Wähle als Dateisystem `Fat32` aus und klicke auf `Formatieren`. 
   
   **Hinweis:** Wenn "Fat32" nicht als Option angezeigt wird, öffne die Eingabeaufforderung (cmd) als Administrator und führe die folgenden Befehle aus:

   ```sh
   diskpart
   list disk
   sel disk 2   // Wähle die Nummer der SD-Karte, z.B. Disk 2
   format fs=fat32 quick

## Linux:

Um die SD-Karte in Linux zu formatieren, führe diese Schritte aus:

1. Öffne das Terminal und führe `lsblk` aus, um die Disk-Informationen zu erhalten.
2. Wähle die SD-Karte aus, indem du `sudo fdisk /dev/disk1` eingibst (ersetze `disk1` durch den tatsächlichen Namen der SD-Karte)
3. Führe diesen Befehl aus, um die Partition in FAT32 zu formatieren:

   ```bash
   sudo mkfs.vfat -F 32 /dev/disk1

## MacOS:

Um in MacOS die SD-Karte in FAT32 zu formatieren, führe diese Schritte aus:

1. Öffne das Terminal und schreibe `diskutil list`, um die Infos für die Disk zu bekommen.
2. Unmounte die SD-Karte zuerst mit `diskutil unmountDisk /dev/disk1` (ersetze `disk1` durch den tatsächlichen Namen der SD-Karte).
3. Führe dann den Befehl aus, um die SD-Karte in FAT32 zu formatieren: `diskutil eraseDisk FAT32 namedersdkarte MBRFormat /dev/disk1`.

# Seriennummer prüfen

Stelle sicher, dass man deine Switch jailbreaken kann. [IsMySwitchPatched](https://ismyswitchpatched.com/).

# SD Karten Setup

1. Downloade das Blue Edition RCM Pack [Blue Edition RCM Pack](https://github.com/glitched-nx/Blue_Edition_2__RCM_V1/releases).
2. Ziehe nun alle Daten auf das Startverzeichnis der SD-Karte.

# RCM Modus vorbereiten und starten

   1. Schalte die Switch aus, indem du 3 Sekunden lang den Power-Knopf gedrückt hältst und unter Power Optionen "Ausschalten" wählst.
   2. Schiebe den RCM Jig in den rechten Joy-Con-Slot rein, bis er richtig sitzt.
   3. Halte die Lauter-Taste und den Power-Knopf gedrückt, um den RCM-Modus zu aktivieren (halte erst die Lautstärke-Taste und dann die Power-Taste gedrückt).

# Payload einfügen

   1. Lade TegraRcmGUI herunter von [TegraRcmGUI](https://github.com/eliboa/TegraRcmGUI/releases).
   2. Verbinde die Switch im RCM-Modus mit deinem PC über das USB-C-Kabel.
   3. Öffne TegraRcmGUI und wähle die Hekate Payload-Datei (es sollte eine ".bin" Datei sein).

# Hekate konfigurieren

## Backup der NAND

1. Schließt oben rechts das Launch-Fenster, nachdem ihr das Datum eingestellt habt.
2. Geht dann oben rechts auf Tools.
3. Wählt dann `Backup eMMC`.
4. Wenn ihr wollt, könnt ihr die Option anschalten mit `SD emuMMC Raw Partition` (ich lasse es hier aus).
5. Wählt dann die Option auf der linken Seite `eMMC BOOT0 & BOOT1` und wartet, bis es fertig ist.
6. Wählt dann darunter `eMMC RAW GPP` und wartet, bis es fertig ist (dies dauert je nach Menge der Daten auf eurem System unterschiedlich lange).
7. Schaltet dann die Switch aus und geht mit der SD-Karte an euren PC.
8. Kopiert alle gebackupten Daten in einen Ordner (es müssten 15 rawnand.bin-Dateien auf der SD-Karte sein und die BOOT0 und BOOT1-Dateien).
9. Löscht dann diese Dateien von eurer SD-Karte.

## Wiederherstellung der NAND

1. Kopiert die gebackupten Dateien und packt sie in `restore` dann `emummc` auf der SD-Karte.
2. Wenn ihr dann in Hekate seid, könnt ihr unter Tools "Restore eMMC" wählen.
3. Wählt dann `eMMC BOOT0 & BOOT1` und `eMMC RAW GPP` aus, um die Wiederherstellung durchzuführen.

## SD-Karte partitionieren und sysMMC auf emuMMC kopieren

1. Wählt in Hekate `emuMMC` aus.
2. Geht dann auf `Create emuMMC`.
3. Wählt `SD Partition`.
4. Geht dann auf Continue und dann auf OK.
5. Wählt bei `emuMMC` die Balken auf Full, damit euer System komplett darauf kopiert wird (da CFW separat vom normalen System läuft).
6. Ihr könnt auch für Android und Linux Speicher reservieren, falls ihr das installieren möchtet.
7. Geht dann auf `Next Step` und dann auf `Start` und bestätigt alles weitere, um fortzufahren. Die SD-Karte wird partitioniert.
8. Geht dann nochmal auf `Create emuMMC` und dann auf `SD Partition` und wählt Part 1.

## Falls ihr Linux installieren wollt:
1. Downloadet [Switchroot Ubuntu](https://download.switchroot.org/ubuntu-bionic/) (wählt dann die aktuelle `Switchroot Ubuntu.7z`) und zieht die Ordner `switchroot` und `bootloader` auf eure SD-Karte.

2. Geht dann in Hekate, nachdem ihr eure SD-Karte formatiert habt (wie im vorherigen Schritt), und wählt danach "Flash Linux" aus (ihr solltet noch im Formatierungsschritt sein, also das Fenster nicht geschlossen haben, sonst formatiert ihr einfach alles neu), um Linux zu installieren (euer SwitchOS wird nicht überschrieben).
Ihr könnt auch "SD UMS" wählen, um eure SD-Karte am PC zu bearbeiten, ohne sie aus eurer Switch herauszunehmen.

## Immer im RCM-Modus starten

1. In Hekate geht wieder auf Tools.
2. Geht dann ganz unten rechts auf irgendetwas mit "Arch Bit - RCM".
3. Und wählt ganz rechts oben AutoRCM aus.

Hiermit müsst ihr dann nicht immer den RCM-Jig und das USB-C-Kabel verbinden und den Payload neu laden, wenn ihr die Switch neu startet, sondern startet immer in Hekate rein.

# CFW Atmosphere Laden

1. Geht in Hekate unter Home auf "Launch" und wählt "Atmosphere emuMMC" aus, um dort hinein zu booten.

# HB-Store installieren, um Apps zu installieren

   1. Schalte deine Switch komplett aus.
   2. Downloade den Homebrew App Store [HB-App Store](https://github.com/fortheusers/hb-appstore/releases).
   3. Ziehe die `.nro` Datei in den `/switch` Ordner auf die microSD-Karte.
   4. Du kannst den Homebrew über das Album starten oder du kannst auch R gedrückt halten und ein legitimes Spiel starten, um Homebrew mit Admin-Rechten zu starten und darüber den HB-Store zu öffnen.

# WICHTIG!!!

SPIELT NICHT ONLINE, LADET KEINE UPDATES HERUNTER UND INTERAGIERT NICHT MIT DEN NINTENDO-SERVERN, SOLANGE IHR IN DER CFW SEID, SONST WERDET IHR ONLINE GEBANNT ODER EURE KONSOLE WIRD KOMPLETT GEBANNT.

