# So veröffentlichen Sie das Plugin auf dem Markt

## Voraussetzungen

- Registrieren Sie sich als Entwickler, siehe [hier](https://www.jeedom.com/site/fr/dev.html)
- Warten auf die Validierung des Marktkontos als Entwickler
- Haben Sie Ihr Plugin auf Github (private Einzahlung oder nicht)

## Configuration

Sobald Sie mit Ihrem Dev-Konto auf dem Markt verbunden sind, müssen Sie : 

- Klicken Sie auf Markt und fügen Sie hinzu
- Füllen Sie die Informationen auf Ihrem Plugin aus : 
  - Allgemein : 
    - Prix
    - ID (die in der Datei info.json)
    - Nom
    - Kategorie
    - Ob es privat ist oder nicht
  - Dokumentation und Links
    - die Beschreibung (gut gesagt, die meisten Benutzer werden die Dokumentation vor dem Kauf nicht sehen)
    - Sprachen
    - kompatible Hardware
    - ggf. einen Hinweis zur Verwendung
  - Github : Hier legen Sie die Informationen zwischen dem Markt und Github ab
    - das Token (nur um es zu setzen, wenn sich Ihr Plugin auf einer privaten Einzahlung befindet)
    - Ihr Github-Benutzername
    - Der Name des Repositorys auf Github
    - Aktivieren Sie das Kontrollkästchen für den Markt, um die Übersetzung Ihres Plugins und Ihrer Dokumentation zu verwalten (achten Sie in diesem Fall darauf, dem Benutzer zoic21 von github alle Rechte in Ihrem Github-Repository zu erteilen)
    
   Nach dem Speichern durch Zurückkehren zur Registerkarte Github haben Sie 3-4 Felder, um die Zweige anzuzeigen : 
   
   - beta
   - stable
   - pro (ist in 99% der Fälle nutzlos)
   - Stablev3 (kommt bald)
   
   Die Synchronisierung erfolgt entweder automatisch jeden Tag um 12.10 Uhr (Vorsicht angesichts der Anzahl der Plugins und der Anrufbeschränkungen). Das Update beginnt um 12.10 Uhr, dauert jedoch mehrere zehn Stunden). Sie können auch eine manuelle Synchronisierung eines Zweigs über die Plugin-Datei starten
