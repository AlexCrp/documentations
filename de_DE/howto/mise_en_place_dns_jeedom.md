# Implementierung von Jeedom DNS

## Objectif

Richten Sie Jeedom DNS so ein, dass Sie extern über eine HTTPS-URL auf Ihr Jeedom zugreifen können

> **WICHTIG**
>
>Das Jeedom-DNS fungiert als Reverse-Proxy, sodass nur in https auf Ihr Jeedom zugegriffen werden kann. Daher ist es nicht möglich, mit dem Jeedom-DNS remote auf Ihr Jeedom in SSH zuzugreifen

## Voraussetzungen

Um auf Jeedom DNS zugreifen zu können, ist ein Service Pack oder mehr erforderlich.

## Principe

Das Prinzip von Jeedom DNS ist sehr einfach. Ihr Jeedom stellt eine Verbindung zu einem unserer VPN-Server her (verschlüsselte Verbindung)). Dann macht dieser fragliche Server bei uns während der Anfrage "Reverse Proxy" : Es nimmt Ihre Anfrage, sich mit Ihrem Jeedom zu verbinden, und überträgt sie an dieses.

Dieses Prinzip hat den Vorteil, dass Sie Ihr Jeedom nicht im Internet verfügbar machen und keine Portöffnung durchführen müssen.

> **WICHTIG**
>
> Damit dies funktioniert, muss Ihre Box eine ausgehende Verbindung an den Ports 1194,1195,1996,1997,1198,1199,2000 und 2001 in UDP zulassen. Insbesondere für die Huawei Livebox und den 4g-Router müssen Sie die Firewall-Ebene senken. Für freie Benutzer müssen Sie manchmal auch zu einer festen IP wechseln (andernfalls können Sie Ihre IP kostenlos zwischen mehreren Benutzern teilen, was Bedenken hinsichtlich DNS aufwirft) Freebox Delta müssen Sie die Kindersicherung deaktivieren 

## Einrichten

### Jeedom

Dort ist es super einfach, Sie müssen Ihr Jeedom mit dem Markt verbinden (siehe Dokumentation im ersten Schritt). 

Gehen Sie dann auf Ihrem Jeedom in seiner Verwaltung zur Registerkarte Netzwerke und aktivieren Sie "Jeedom DNS verwenden" und speichern Sie sie.

Jeedom startet das DNS und gibt Ihnen Ihre Zugangs-URL zu Ihrem Jeedom

> **WICHTIG**
>
> Sie können diese URL ändern, indem Sie auf die Seite mit Ihren Marktprofilen und dann auf die Registerkarte "Meine Dienste" klicken und unter "Einfacher Fernzugriff" auf Konfiguration klicken. Im DNS-Feld können Sie sie anpassen. Nach der Registrierung müssen Sie DNS in Jeedom neu starten (System -> Anpassung -> Konfiguration, dann die Registerkarte Netzwerke und im Abschnitt "DNS (Proxy) Market" neu starten"). Es ist ratsam, diese Manipulation mit lokalem Zugriff auf Ihre Box durchzuführen.

Hier ist Ihr Jeedom von außen in https zugänglich

## FAQ

> **Muss ich Ports an meiner Box öffnen?**
>
> Nein, es ist nicht erforderlich, einen Port von Ihrer Internetbox zu Ihrem Jeedom zu öffnen. Die Verbindung befindet sich in Richtung Jeedom -> VPN, es handelt sich also um eine ausgehende Verbindung (an den Ports 1194, 1195, 1996, 1997, 1198, 1199, 2000 und 2001) und nicht um eine eingehende Verbindung.

> **Warum Jeedom DNS meinen Zugriff darauf schützt**
>
> Mit Jeedom DNS können Sie einen sehr wichtigen HTTPS-Zugriff einrichten. Dies garantiert, dass die Verbindung zwischen Ihrem Browser und Ihrem Jeedom verschlüsselt ist. Außerdem ist das gültige Zertifikat niemand in der Lage, sich als Ihr Jeedom auszugeben. Schließlich wird auch die VPN-Verbindung in Ihrem Jeedom und unseren Servern verschlüsselt.

> **Ich habe den internen Listening-Port meines Jeedom geändert und der Jeedom-DNS funktioniert nicht mehr**
>
> In der Tat funktioniert der Jeedom DNS nur, wenn Ihr Jeedom den lokalen Port 80 überwacht (alle anderen Ports auf der VPN-Schnittstelle sind beim Herstellen einer Verbindung geschlossen). Dies wirft keine Sicherheitsbedenken auf, da das VPN einen verschlüsselten Tunnel erstellt. Selbst wenn der Fluss an Port 80 frei ist, wird er im VPN-Tunnel verschlüsselt.

> **Ich habe keine Anmeldeseite, kann mich aber nicht anmelden**
>
> Stellen Sie sicher, dass Sie die Standardanmeldeinformationen für jeedom (admin / admin) geändert haben und dass Ihr Benutzer nicht nur lokal eingeschränkt ist.

> **Meine Konfiguration ist gut, aber es ist unmöglich, eine Seite zu haben, die endlos umblättert**
>
> Wenn Ihre Konfiguration korrekt ist (Initialisierungssequenz im Protokoll openvpn_DNS_Jeedom abgeschlossen), Sie jedoch nicht die Anmeldeseite erhalten können, die zufällig mit der mobilen Anwendung funktioniert, und Sie sich in 4g oder am Ende der ADSL-Zeile befinden. In diesem Fall müssen Sie das Kontrollkästchen in der Jeedom-Netzwerkkonfiguration wie in 4g aktivieren und die DNS neu starten, damit Jeedom die MTU Ihrer Verbindung ändert, um die Größe der Pakete zu verringern. Abhängig von den Versionen von Jeedom wird diese Option automatisch vom Core verwaltet (und wird daher nicht angezeigt). Starten Sie einfach den DNS neu.

> **Ich habe den Fehler "ERROR: TUN / TAP dev / dev / net / tun kann nicht geöffnet werden: Keine solche Datei oder kein solches Verzeichnis (errno = 2)"**
>
> Dieser Fehler tritt normalerweise bei Docker-Installationen auf, wie in der Dokumentation für angegeben [Kompatibilität](https://doc.jeedom.com/de_DE/compatibility/) Docker-Unterstützung ist Beta gerade wegen dieser Art von Problem. Die Lösung besteht normalerweise darin, openvpn auf dem Host zu installieren (wenn möglich))
