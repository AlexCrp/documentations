# Everspring Miniplug Dimmer - AD147-6

 **Das Modul**

![module](images/everspring.AD147-6/module.jpg)

 **Das Jeedom Visual**

![vuedefaut1](images/everspring.AD147-6/vuedefaut1.jpg)

## Zusammenfassung

Der Mini-Dimmerstecker dient zum Steuern des Ein- und Ausschaltens von Lichtern und elektrischen Geräten in Ihrem Haus. Es ermöglicht auch eine Dimmerfunktion, die nur mit Glühbirnen kompatibel ist. Mit einer Spannung von 220 - 240 V kann dieser Dimmerstecker eine Last von 6 W bis 250 W tragen.

Der Mini Dimmer Plug ist ein Z-Wave ™ -kompatibles Gerät, das für alle Z-Wave ™ -kompatiblen Netzwerke geeignet ist. Es kann von einer Fernbedienung, einer PC-Software oder einem beliebigen Z-Wave-Controller in Ihrem Netzwerk gesteuert werden.

## Fonctions

-   Steuern Sie eine Lampe fern
-   Steckermodul, das direkt zwischen einer Steckdose und der zu steuernden Last integriert ist
-   EIN / AUS und Dimmerfunktion zur Steuerung der Lampen
-   Lokale Ladesteuerung über integrierte Taste
-   Z-Wave Plus-Technologie
-   Reduzierte Abmessungen bleiben fast unbemerkt
-   Status-LED an der integrierten Taste
-   Z-Wave-Repeater-Funktion

## Technische Daten

-   Modultyp : Z-Wave Empfänger
-   Versorgung : 230 V, 50 Hz
-   Verbrauch : 0,6 W.
-   Maximale Leistung : Widerstandslast : 250W, Glühlampe : 250W, LED-Lampe (nicht dimmbar) : 6W
-   Frequenz : 868,42 MHz
-   Geltungsbereich : bis zu 70 m im Freien, bis zu 30 m in Gebäuden
-   Affichage: LED auf der Taste
-   Abmessungen : Länge (Stecker enthalten) : 74mm Durchmesser : 52mm

## Moduldaten

-   Machen Sie : Everspring
-   Name : Miniplug Dimmer
-   Hersteller ID : 96
-   Produkttyp : 3
-   Produkt-ID : 3

## Configuration

Informationen zum Konfigurieren des OpenZwave-Plugins und zum Einfügen von Jeedom finden Sie hier [Dokumentation](https://doc.jeedom.com/de_DE/plugins/automation%20protocol/openzwave/).

> **Wichtig**
>
> Um dieses Modul in den Einschlussmodus zu versetzen, drücken Sie die Taste gemäß der Papierdokumentation dreimal. Es ist wichtig zu beachten, dass dieses Modul direkt aufgenommen wird, wenn es zu keinem Netzwerk gehört und mit Strom versorgt wird

![inclusion](images/everspring.AD147-6/inclusion.jpg)

Einmal enthalten, sollten Sie dies erhalten :

![Plugin Zwave](images/everspring.AD147-6/information.jpg)

### Commandes

Sobald das Modul erkannt wurde, sind die dem Modul zugeordneten Befehle verfügbar.

![Befehle](images/everspring.AD147-6/commandes.jpg)

Hier ist die Liste der Befehle :

-   Intensität : Es ist der Befehl, mit dem die Intensität des Fangs reguliert werden kann
-   Ein : Dies ist der Befehl, der die Steckdose einschaltet
-   Aus : Es ist der Befehl, der es ermöglicht, den Fang zu löschen
-   Zustand : Es ist der Befehl, mit dem der Status des Sockets ermittelt werden kann

Beachten Sie, dass im Dashboard die Informationen zu Status, EIN / AUS und Intensität auf demselben Symbol angezeigt werden.

### Konfiguration des Moduls

Sie können das Modul entsprechend Ihrer Installation konfigurieren. Gehen Sie dazu auf die Schaltfläche "Konfiguration" des OpenZwave-Plugins von Jeedom.

![Konfiguration plugin Zwave](images/plugin/bouton_configuration.jpg)

Sie gelangen auf diese Seite (nachdem Sie auf die Registerkarte Einstellungen geklickt haben)

![Config1](images/everspring.AD147-6/config1.jpg)

Parameterdetails :

-   1 : Dieser Parameter definiert den Statuswertbefehl. Es ist nicht ratsam, diesen Wert zu ändern.
-   2 : Dieser Parameter definiert die Verzögerung für das Senden der Statusänderung an Gruppe 1 (Wert zwischen 3 und 25 Sekunden)
-   3 : Mit diesem Parameter wird festgelegt, ob die Steckdose nach einer Wiederherstellung der Stromversorgung ihren Status (EIN oder AUS) wieder einnimmt.
-   4 : Mit diesem Parameter können Sie festlegen, ob die Steckdose im Dimmmodus oder im Ein / Aus-Modus betrieben werden soll

### Groupes

Dieses Modul hat 2 Zuordnungsgruppen.
![Groupe](images/everspring.AD147-6/groupe.jpg)

> **Wichtig**
>
> Zumindest sollte Jeedom in Gruppe 1 landen

## Gut zu wissen

### Besonderheiten

-   Die Statusrückmeldung kann nicht innerhalb von 3 Sekunden konfiguriert werden.

## Wakeup

Keine Vorstellung von Aufwecken auf diesem Modul.
