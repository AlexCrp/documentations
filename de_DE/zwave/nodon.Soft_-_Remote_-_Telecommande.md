# Nodon Fernbedienung - Soft Remote

**Das Modul**

![module](images/nodon.softremote/module.jpg)

**Das Jeedom Visual**

![vuedefaut1](images/nodon.softremote/vuedefaut1.png)

## Zusammenfassung

Die Soft Remote NodOn® kann jedes Z-Wave®- oder Z-Wave Plus®-kompatible Gerät wie den NodOn® Smart Plug direkt steuern.

Es kann auch Szenen über ein kompatibles Hausautomationszentrum auslösen.

## Fonctions

-   Steuern Sie jedes Z-Wave-kompatible Gerät
-   Schlag- und spritzwassergeschützt
-   Wird dank des integrierten Magneten überall angebracht
-   6 Farben erhältlich

## Technische Daten

-   Versorgung : CR2032 Batterie - Autonomie 1,5 - 2 Jahre
-   4 Tasten
-   Integrierter Magnet zur Befestigung an der Metalloberfläche
-   Schlag- und spritzwassergeschützt
-   Betriebstemperatur : 0 ° C bis 40 ° C - Höhe : 2000m
-   Z-Wave®-Funkprotokoll : 868.4MHz - 500 Series - Kompatibles Z-Wave Plus® SDK 06.51.06
-   Geltungsbereich : 40 m drinnen / 80 m draußen
-   Abmessungen 56 \*56 \*20mm
-   2 Jahre Garantie

## Moduldaten

-   Machen Sie : Nodon
-   Name : CRC-3-6-0x Soft Remote
-   Hersteller ID : 357
-   Produkttyp : 2
-   Produkt-ID : 2

## Configuration

Informationen zum Konfigurieren des OpenZwave-Plugins und zum Einfügen von Jeedom finden Sie hier [Dokumentation](https://doc.jeedom.com/de_DE/plugins/automation%20protocol/openzwave/).

> **Wichtig**
>
> Um dieses Modul in den Einschlussmodus zu versetzen, drücken Sie die beiden Tasten (+ und 0 voll), bis das Licht rosa wird, und drücken Sie dann die Taste + gemäß der Papierdokumentation.

![inclusion](images/nodon.softremote/inclusion.jpg)

Einmal enthalten, sollten Sie dies erhalten :

![Plugin Zwave](images/nodon.softremote/information.png)

### Commandes

Sobald das Modul erkannt wurde, sind die dem Modul zugeordneten Befehle verfügbar.

![Befehle](images/nodon.softremote/commandes.png)

Hier ist die Liste der Befehle :

-   Tasten : Es ist der Befehl, der den Knopf nach oben drückt

+ ---------------- + ---------------- + --------------- - + ---------------- + ---------------- +
| Tasten        | Unterstützung          | Lange drücken     | Entspannung    | Doppelte Unterstützung   |
+ =============== + =============== + ================ = + =============== + ================= +
| **1 (0         | 10             | 12             | 11             | 13             |
| plein)**       |                |                |                |                |
+ ---------------- + ---------------- + --------------- - + ---------------- + ---------------- +
| **2 (+)**      | 20             | 22             | 21             | 23             |
+ ---------------- + ---------------- + --------------- - + ---------------- + ---------------- +
| **3 (0 leer)** | 30             | 32             | 31             | 33             |
+ ---------------- + ---------------- + --------------- - + ---------------- + ---------------- +
| **4 (-)**      | 40             | 42             | 41             | 43             |
+ ---------------- + ---------------- + --------------- - + ---------------- + ---------------- +

-   Batterie : Es ist der Befehl, der den Füllstand der Batterien erhöht

### Konfiguration des Moduls

> **Wichtig**
>
> Wecken Sie das Modul bei einer ersten Aufnahme immer unmittelbar nach der Aufnahme auf.

Wenn Sie das Modul dann entsprechend Ihrer Installation konfigurieren möchten, müssen Sie die Schaltfläche "Konfiguration" des OpenZwave-Plugins von Jeedom aufrufen.

![Konfiguration plugin Zwave](images/plugin/bouton_configuration.jpg)

Sie gelangen auf diese Seite (nachdem Sie auf die Registerkarte Parameter geklickt haben)

![Config1](images/nodon.softremote/config1.png)

Parameterdetails :

-   1-2 : Ermöglicht die Auswahl des Profils der Schaltflächen bei zentraler Verwendung (für die Verwendung in Jeedom unbrauchbar))
-   3 : Wichtiger Parameter, um anzugeben, ob der Schalter im Szenen- oder zentralen Szenenmodus arbeiten soll (Szene absolut einstellen)
-   4-7 : Wählen Sie die Tastenbetriebsart (bei Gruppenzuordnungen)
-   8 : Hier können Sie den Betriebsmodus der LED auswählen

### Groupes

Dieses Modul hat 7 Zuordnungsgruppen.

![Groupe](images/nodon.softremote/groupe.png)

-   Gruppe 1 - Rettungsleine : Diese Gruppe wird im Allgemeinen verwendet, um Informationen vom Smart Plug an den Hauptnetzwerkcontroller zu melden.
-   Gruppe 2 bis 5 - Die Geräte in diesen Gruppen werden über die entsprechende Schaltfläche entsprechend dem MONO-Profil gesteuert
-   Gruppe 6 bis 7 - Die Geräte in diesen Gruppen werden über die entsprechenden Tasten entsprechend dem DUO-Profil gesteuert

> **Wichtig**
>
> Zumindest sollte Jeedom in Gruppe 1 landen

## Gut zu wissen

### Besonderheiten

-   Dieses Modul kann bei der Aufnahme schwierig sein. Zögern Sie nicht, es 1 oder 2 Mal nach der Aufnahme aufzuwecken. Überprüfen Sie die Assoziationsgruppe.

## Wakeup

Um dieses Modul zu aktivieren, drücken Sie einfach eine der Tasten

## Wichtiger Hinweis

> **Wichtig**
>
> Sie müssen das Modul aufwecken : nach seiner Aufnahme, nach einer Änderung der Konfiguration, nach einer Änderung des Aufweckens, nach einer Änderung der Assoziationsgruppen
