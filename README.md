## Nintendo Switch Jailbreak-Anleitung

### Vorbereitung:
**Benötigte Materialien:**

- Nintendo Switch (V1)
- microSD-Karte (mindestens 64GB)
- RCM Jig oder ein Werkzeug zum Eingeben des RCM-Modus (z.B. eine Büroklammer)
- USB-C-Kabel

### Schritte:
1. Überprüfen der Seriennummer:

   Stelle sicher, dass deine Switch jailbreakbar ist. Besuche [ismyswitchpatched.com](https://ismyswitchpatched.com/)

2. RCM-Modus aktivieren:

   - Schalte die Switch aus.
   - Platziere den RCM Jig in der rechten Joy-Con-Schiene.
   - Halte die Volume Up-Taste und den Power-Knopf gedrückt, um den RCM-Modus zu aktivieren.

3. Payload senden:

   - Lade TegraRcmGUI herunter von [github.com/eliboa/TegraRcmGUI/releases](https://github.com/eliboa/TegraRcmGUI/releases).
   - Verbinde die Switch im RCM-Modus mit deinem PC.
   - Öffne TegraRcmGUI und wähle die Hekate Payload.

4. Custom Firmware installieren:

   - Lade die neueste Version von Atmosphère herunter von [github.com/Atmosphere-NX/Atmosphere/releases](https://github.com/Atmosphere-NX/Atmosphere/releases).
   - Entpacke die Atmosphère-Dateien auf die microSD-Karte.
   - Kopiere die Dateien (z.B. bootloader und atmosphere Ordner) auf die microSD-Karte.
   - Starte die Switch mit der Hekate Payload und folge den Bildschirmanweisungen zur Installation der Custom Firmware.

5. Homebrew-Apps installieren:

   - Lade den Homebrew App Store herunter von [github.com/fortheusers/hb-appstore/releases](https://github.com/fortheusers/hb-appstore/releases).
   - Kopiere die Homebrew-App (.nro Datei) in den `/switch` Ordner auf der microSD-Karte.
   - Starte die Switch im CFW-Modus und öffne die Homebrew-App über das Homebrew-Menü.
