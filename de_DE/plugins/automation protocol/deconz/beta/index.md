# Deconz Plugin

Mit diesem Plugin können Sie über einen Conbee-Schlüssel (1 oder 2) das Dekonz-Tool steuern, mit dem Sie Zigbee (Xiaomi-Modul, Philips-Farbton, Ikea) ausführen können...).

Dieses Plugin ist vollständig Cloud-frei, stellt also keine Kommunikation nach außen (Drittanbieter-Server) her und funktioniert zu 100% lokal !!!!

Achtung, der Zigbee funktioniert überhaupt nicht wie der Zwave, die Liste der enthaltenen Module wird überhaupt nicht im Schlüssel gespeichert (nichts wird im Schlüssel gespeichert). So ist es einfach, den Schlüssel zu ersetzen (durch Sichern / Wiederherstellen kann das Backup aus Jeedom wiederhergestellt, aber nicht aus Jeedom wiederhergestellt werden. Für die Wiederherstellung muss Deconz ausgeführt werden. Wenn Sie sich in einer lokalen Installation befinden, handelt es sich um IP_JEEDOM:8484). Im Falle des Verschiebens des Schlüssels von einem System auf ein anderes ist es auch erforderlich, eine Sicherung / Wiederherstellung durchzuführen.

>****
>
> Dieses Plugin benötigt einen USB-Stick [](http://bit.ly/2n4VyWc)

>****
>
> Debian Strech (Debian 9) oder höher ist unbedingt erforderlich, damit das Plugin funktioniert

>****
>
> Das Plugin ist nicht mit einer 32-Bit-Architektur (alte Hardware) kompatibel). Das Modul ist mit allen Raspberry Pi kompatibel

>****
>
> Bei RPI müssen die seriellen Optionen deaktiviert werden, damit der Conbee-Schlüssel ordnungsgemäß funktioniert (dies geschieht in ssh in raspi-config)

# Kompatibles Modul

Hier finden Sie die Liste der deconz-kompatiblen Module [](https://phoscon.de/en/conbee/compatible)

>****
>
> Das Hinzufügen eines Moduls wird nicht direkt von Jeedom SAS verwaltet, sondern vom Herausgeber des Deconz-Gataways. Wir können daher nicht garantieren, dass eine Supportanfrage für ein neues Modul erfolgreich ist. Es wird daher dringend empfohlen, ein kompatibles Modul zu kaufen

>****
>
> Im Falle eines sogenannten kompatiblen Moduls, das nicht oder nur teilweise unterstützt wird, kann das Unternehmen Jeedom SAS nicht verantwortlich gemacht werden und ist nicht verpflichtet, bei der Korrektur von Bedenken Ergebnisse zu erzielen

# Plugins Konfiguration

Das Plugin unterstützt mehrere Deconz-Gateways (1 Conbee-Schlüssel pro Gateway). Ein Conbee-Gateway kann installiert werden :

- jeedom selbst (smart, rpi und x64_86 unterstützt)
- eine entfernte RPI
- oder jede andere mit deconz kompatible Karte.

Für die Remote-Installation ist hier die [](https://phoscon.de/en/conbee/install)

Für die Installation auf jeedom müssen Sie nur auf die Schaltfläche klicken, um deconz lokal zu installieren.

>****
>
> Sie dürfen die beiden Installationsmethoden NICHT auf demselben System ausführen, es ist die eine oder andere

>****
>
>Um Local Deconz zu aktualisieren, klicken Sie einfach auf die Schaltfläche Local Deconz Installation

## Hinzufügen von Gateways

Um dem Plugin neue Gateways hinzuzufügen, klicken Sie entweder auf der Plugin-Konfigurationsseite (Plugin -&gt; Plugin-Verwaltung, dann dekonzieren) auf Erkennung (es funktioniert nicht immer) oder fügen Sie von Hand mindestens die IP-Adresse von hinzu das Gateway und der Port.

Dann in deconz (Phoscon, wenn Sie es lokal installiert haben, müssen Sie zu IPJEEDOM gehen:8484) Dann müssen Sie im Menü oben links (die 3 kleinen Zeilen) zu "Gateway" und dann zu "Erweitert" gehen und auf "App authentifizieren" klicken. Schließlich müssen Sie in den 60er Jahren zur Konfiguration des Plugins in Jeedom gehen und das speichern Liste der Gateways, wenn Sie sie geändert haben, klicken Sie auf "API-Schlüssel wiederherstellen"".

# Deconz-Netzwerke

Achtung oben rechts haben Sie eine Auswahlschaltfläche, mit der Sie das zu betrachtende Gateway auswählen können

## Zusammenfassung

Hier finden Sie die wichtigsten Informationen Ihrer Deconz-Netzwerke (insbesondere die Version von Deconz und Firmware).

## Action

Dort wirst du in der Lage sein :

- Aktualisieren Sie die Firmware (funktioniert nur, wenn kein anderer USB-Stick an das Gerät angeschlossen ist)
- Führen Sie einen Reset durch (Vorsicht, es ist erforderlich, alles neu zuzuordnen)
- Ändern Sie die Quelle des Firmware-Updates (es wird nicht empfohlen, es zu berühren)
- Kanal wechseln

## Noeuds

Hier haben Sie eine Zusammenfassung der bekannten Knoten des Schlüssels mit dem Datum der letzten Kommunikation, der Firmware-Version, dem Akkuladestand und durch Klicken auf die Info-Schaltfläche die Details des Knotens.

>****
>
>Hier werden die Knoten nach Typ geschnitten, sodass ein Modul je nach Anzahl der Typen mehrmals angezeigt werden kann

# Inclusion

Für die Aufnahme müssen Sie nur auf die Schaltfläche &quot;Aufnahme&quot; klicken. Das System fragt nach dem Gateway, sobald die Überprüfung abgeschlossen ist. Sie haben 3 Minuten Zeit, dies zu tun.

Um das Modul in den Einschlussmodus zu schalten, müssen Sie die Dokumentation für das betreffende Modul aufrufen

>****
>
> Das ZigBee-Netzwerk unterscheidet sich stark vom Zwave-Netzwerk. Das ZigBee-Netzwerk kann einen Repeater durchlaufen, dies muss jedoch bei der Aufnahme der Fall sein. Wenn Sie das Modul einschließen, ist es daher erforderlich, dies so nah wie möglich am Schlüssel zu tun, wenn die Kommunikation nicht über einen Repeater erfolgen soll (achten Sie darauf, dass maximal 32 Module auf dem Conbee-Schlüssel leben können).Oder so nah wie möglich am Repeater (jedes angetriebene Modul kann ein Repeater sein).

# Synchronisation

Sobald die Aufnahme erfolgt ist, sollte Jeedom Sie direkt zur Seite des neuen Moduls senden. Wenn die Erkennung nicht funktioniert hat, klicken Sie einfach auf Synchronisieren

# Equipement

Auf der ersten Registerkarte finden Sie die gesamte Konfiguration Ihrer Geräte :

- Name der Ausrüstung : Name Ihrer Simulationsausrüstung,
- Übergeordnetes Objekt : Gibt das übergeordnete Objekt an, zu dem das Gerät gehört,
-  : macht Ihre Ausrüstung aktiv,
-  : macht Ihre Ausrüstung auf dem Armaturenbrett sichtbar.
- Eine Konfigurationsschaltfläche, die Ihnen je nach Modul die möglichen Optionen bietet (seien Sie vorsichtig, hier zeigt Jeedom die Optionen an, wie sie das Modul manchmal bietet. Je nach Modul ist dies nicht sehr sinnvoll)
- Allgemeine Informationen zum Modul
- die Wahl der visuellen

>****
>
> Hier ist die Auftragsverwaltung überhaupt nicht wie die zwave. Beim Einfügen eines Moduls gibt es mehrere mögliche Fälle :
> - Das Modul hat eine bestimmte Konfiguration : In diesem Fall haben Sie das Bild des Moduls sowie eine angepasste Konfiguration (dies ist selten der Fall, da dies im Zickzack erforderlich sein kann)
> - Das Modul hat je nach Typ eine generische Konfiguration  : Sie haben eine allgemeine Grafik und die Befehle, die den Modultypen entsprechen (dies ist der häufigste Fall)
> - Modul und Typen sind aus jeedom unbekannt : In diesem Fall müssen Sie eine Support-Anfrage öffnen, um sie beim nächsten Plugin-Update hinzuzufügen

# Sauvegarde

Das Plugin führt eine Sicherung des im Schlüssel enthaltenen Netzwerks in einer lokalen Datei durch. Sie können es von der Konfigurationsseite herunterladen.

# Restauration

Wenn Sie ein Jeedom-Backup wiederherstellen, wird das Gerät wiederhergestellt, aber nicht an den Schlüssel angeschlossen. Möglicherweise müssen Sie den Schlüssel neu installieren. Dazu benötigen Sie das oben erwähnte Backup.  ``plugins/deconz/data``  ``.tar.gz``  ``.dat``. 

Gehen Sie dann zur Phoscon-Oberfläche. Menü => Gateway => Sicherungsoption => Sicherung laden.

Sie müssen nur eine API-Schlüsselerkennung, Speichern und schließlich eine Synchronisierung über die Plugin-Seite durchführen.

# Firmware-Update

## 

Sie können dies direkt von jeedom aus tun, wenn der Schlüssel in der Plugin-Konfiguration eingesteckt ist. Es wird jedoch mehr als dringend empfohlen, dies unter Windows zu tun, indem Sie der offiziellen Deconz-Dokumentation folgen

## Conbee

Mach weiter [](https://www.dresden-elektronik.de/rpi/deconz-firmware/?C=M;O=D) und prüfen Sie, ob es eine neue Firmware gibt, wenn ja, holen Sie sie zurück

````
wget https://www.dresden-elektronik.de/rpi/deconz-firmware/deCONZ_Rpi_0x26300500.bin.GCF
sudo GCFFlasher_internal -d 0 -f deCONZ_Rpi_0x26300500.bin.GCF
````

>****
>
>Um blinken zu können, müssen unbedingt alle Dämonen auf einem USb-Schlüssel (zwave, enocean, rfxcom ...) abgeschnitten und überprüft werden, ob der Schlüssel tatsächlich 0 ist ``GCFFlasher_internal -l``. Es ist ratsam, die anderen Schlüssel zu trennen

# FAQ

>**Der Dämon startet und schneidet sich nach einer Minute ab**
>
>Wenn Sie unter RPI sind, sollte die Seriennummer nicht abgeschnitten worden sein (dies geschieht in raspi-config)

>**Ich habe eine Tageslichtausrüstung in der Knotenliste, aber nicht in Jeedom**
>
>Normalerweise handelt es sich um ein nicht entfernbares virtuelles Gerät, das von Deconz erstellt wurde. Da es sich nicht um ein &quot;echtes&quot; Jeedom-Gerät handelt, wird es nicht wieder zusammengebaut

>**Ich habe den Fehler &quot;Fehler während der Anfrage : .1:8484 / api / 931559A482 / Sensoren (POST), Daten : Null Fehler : 1 => nicht autorisierter Benutzer"**
>
>Sie haben Jeedom nicht autorisiert, eine Verbindung zu Deconz herzustellen. Sie müssen in deconz (Phoscon, wenn Sie es lokal installiert haben, müssen Sie zu IPJEEDOM gehen:8484) Dann müssen Sie im Menü oben links (die 3 kleinen Zeilen) zu "Gateway" und dann zu "Erweitert" gehen und auf "App authentifizieren" klicken. Schließlich müssen Sie in den 60er Jahren zur Konfiguration des Plugins in Jeedom gehen und die Liste von speichern Wenn Sie das Gateway geändert haben, klicken Sie auf "API-Schlüssel wiederherstellen""

>**Mein RPI (4) sieht den Dekonz-Schlüssel nicht**
>
>Sie müssen die Key-Firmware mit einem anderen System (Windows) aktualisieren)

>**Es gelingt mir, meine Ausrüstung zu kontrollieren, aber ich habe kein Feedback zu Informationsbestellungen**
>
>Dies ist wahrscheinlich auf ein Problem mit Zeitzonen zurückzuführen (deconz ist oben sehr wählerisch). Du musst :
>- Überprüfen Sie in "Deconz Networks", ob die Zeitzone und die Zeit korrekt sind. Wenn nicht, können Sie sie entweder in deconz konfigurieren oder das Kontrollkästchen "Zeitzonen" auf dem Gateway in der Konfiguration des deconz-Plugins aktivieren (wenn Sie diese letzte Methode ausführen, müssen Sie dies tun Warten Sie 1 Stunde, bevor die Korrektur wirksam wird)
>- Überprüfen Sie die Zeitzone Ihres Betriebssystems (insbesondere auf dem RPI), die unbedingt gut sein muss
