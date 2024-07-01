# Nintendo Switch Jailbreak Totorial

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

Falls du eine SD-Karte hast, die größer als 32 GB ist und dein 3DS sie nicht erkennt, lade das Programm "Fat32 Format" herunter (von beliebiger Quelle). Wähle deine SD-Karte aus und setze die Größe auf 32768, um sie auf 32 GB zu begrenzen.

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


## Was Du brauchst

- Nintendo Switch V1
- microSD-Karte (mindestens 64GB wird empfohlen)
- RCM Jig
- USB-C-Kabel

## Seriennummer prüfen

Stelle sicher, dass man die Switch jailbreaken kann. Besuche [IsMySwitchPatched](https://ismyswitchpatched.com/).

## RCM-Modus vorbereiten und starten

1. Schalte die Switch aus, indem du 3 Sekunden lang den Power-Knopf gedrückt hältst und "Ausschalten" wählst.
2. Schiebe den RCM Jig in den rechten Joy-Con-Slot, bis er richtig sitzt.
3. Halte die Lautstärke-Hoch-Taste und den Power-Knopf gedrückt, um den RCM-Modus zu aktivieren (halte erst die Lautstärke-Taste und dann die Power-Taste gedrückt).

## Payload einspielen

1. Lade TegraRcmGUI herunter von [TegraRcmGUI](https://github.com/eliboa/TegraRcmGUI/releases).
2. Verbinde die Switch im RCM-Modus mit deinem PC über das USB-C-Kabel.
3. Öffne TegraRcmGUI und wähle die Hekate Payload-Datei (es sollte eine ".bin"-Datei sein).

## CFW (Custom Firmware) installieren:

1. Lade die neueste Version von Atmosphère CFW herunter von [Atmosphere CFW](https://github.com/Atmosphere-NX/Atmosphere/releases).
2. Entpacke die Atmosphère-Dateien und kopiere sie auf deine SD-Karte.
3. Du müsstest nun in der CFW starten.

## HB-Store installieren, um Apps zu installieren

1. Lade den Homebrew App Store herunter von [HB-Store](https://github.com/fortheusers/hb-appstore/releases).
2. Kopiere die `.nro` Datei in den `/switch` Ordner auf der microSD-Karte.
3. Du kannst den Homebrew über das Album starten oder du kannst auch R gedrückt halten und ein legitimes Spiel starten, um Homebrew mit Admin-Rechten zu öffnen und darüber den HB-Store zu öffnen.

