# Installation auf einer physischen Maschine

In dieser Dokumentation wird die Installation von jeedom auf einem physischen x86-64-Computer (Typ Intel NUC) beschrieben)

# Automatische Installation

Laden Sie die Jeedom ISO herunter [hier](https://images.jeedom.com/x86-64/).

## Brennen auf USB-Stick

Sie können das UNetbootin-Tool verwenden (herunterladbar [hier](https://unetbootin.github.io/) ).

Einmal starten : 

- Wählen Sie "Diskimage" (unten))
- Klicken Sie auf ... und wählen Sie die im vorherigen Schritt heruntergeladene Jeedom-ISO-Datei aus
- Wählen Sie Ihren USB-Stick unter "Reader""
- Klicken Sie auf OK

Dann musst du nur noch ``booter`` auf dem USB-Stick. Motherboards haben im Allgemeinen 2 Startmodi : UEFI (aktuell, Standardauswahl) und BIOS (Verlauf)). Wir empfehlen, dass Sie das BIOS verwenden (die Option, die je nach Motherboard geändert werden kann und nicht immer leicht zu finden ist, daher können wir Ihnen kein allgemeines Verfahren geben)

## Installation im BIOS-Modus (empfohlen)

- Wählen Sie "Jeedom installieren""
- Und schließlich "Ja"

## Installation im UEFI-Modus (nicht empfohlen)

- Wählen Sie "Erweiterte Optionen""
- Und schließlich "Im Textmodus installieren"

>**Notiz**
>
>Alle anderen Optionen führen nur zu dem in dieser Dokumentation beschriebenen und gültigen Fehler

Warten Sie, bis die Installation von selbst bis zum Ende erfolgt

>**Notiz**
>
>Während der Installation benötigen Sie unbedingt eine Internetverbindung

Dann können Sie der Dokumentation folgen [Erster Schritt mit Jeedom](https://doc.jeedom.com/de_DE/premiers-pas/index)

# Manuelle Installation

Sobald das Betriebssystem installiert ist (neueste Version von Debian bevorzugt), befolgen Sie diese Anweisungen [Dokumentation](https://doc.jeedom.com/de_DE/installation/cli)



