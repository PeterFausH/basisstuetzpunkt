# Basisstuetzpunkt

macht überwiegend Sinn im deutschsprachigen DACH-Raum, deshalb auch in deutsch beschrieben.

## Description
Ihr habt einen Starlink Internetzugang, notstromversorgt und mit einem Ethernet-Adapter? Dann habt ihr Internetzugang auch wenn der Rest der Nachbarschaft weder Telefon noch Mobilfunkt hat.
Mit dem optionalen Ethernet-Adapter könnt ihr einen Notfall-Treffpunkt oder Basis-Stützpunkt für eure Nachbarschaft zur Verfügung stellen.

Im Sommer braucht die Starlink Dish und das Modem etwas weniger als 40 Watt. Dazu der RaspberryPi mit etwa 5 Watt. Das alles könnt ihr an einer kleineren Powerstation absolut mobil und über einen längeren Zeitraum betreiben, selbst wenn eure Nachbarn noch das Handy an der Powerstation aufladen.

Meine Experimente zu Starlink könnt ihr auf Twitter einsehen: 

[Twitter-Profil von Peter](https://twitter.com/Alpensichtung "Twitter") und gebt im Suchfeld `from:@Alpensichtung starlink` ein.

Im Prinzip macht der RaspberryPi einen Access-Point an dem sich eure Nachbarn einloggen. Es gibt eine Startseite auf der die wichtigsten Links zu finden sind. Die Anfragen der im WLAN eingeloggten Nachbarn werden über den Ethernet-Port an den Starlink geroutet.
So seid Ihr Anlaufpunkt und Informationspunkt.
**Das fertige Image für einen RaspberryPi 4 könnt ihr hier downloaden:**

[Das RaspberryPi Image](http://www.fuerles.de/images/it/bunker/notfalltrefpkt_shrink.img.xz "Image zum Download")


## Visuals
Als Netzplan sieht das so aus:
![Netzplan](/media/Selbsthilfebasis_Schaltbild.png "das braucht ihr")

erstellt so eine Info-Seite zum einloggen:
![Hilfe zum einloggen](/media/Selbsthilfebasis_Beispiel_Layout.png "QR-Codes zum scannen")

eure Nachbarn mit Handy landen auf dieser Seite:
![Handy-Ansicht](/media/Selbsthilfebasis_HTML_responsive_mobile.png "die Startseite mit Links mobil")

eure Nachbarn mit Tablet oder Laptop landen auf dieser Seite:
![Laptop-Ansicht](/media/Selbsthilfebasis_Laptop.png "die Startseite mit Links Laptop")

## Modification
Das Image passt für einen 4er RaspberryPi mit integriertem WLAN und Ethernetbuchse. Wollt ihr einen 3er RaspberryPi verwenden, nehmt einen WLAN-Adapter für USB. Der ist dann meist WLAN1 statt WLAN0 und ihr müsst die nachfolgenden Dateien anpassen.

der RaspberryPi arbeitet ohne grafische Oberfläche:
![Terminal-View](/media/Selbsthilfebasis_boot_headless.png "achtet auf den User pf (nicht pi)")

das sind die wichtigsten Dateien:

![hier ist alles abgelegt](/media/Selbsthilfebasis_wichtige_Dateien.png "wollt ihr Hostname, SSID und Passwort anpassen?")

IP-Bereich festlegen:

![IP-Bereich](/media/Selbsthilfebsis_DHCPD_conf.png "voreingestellt ist 192.168.1.xxx")

welches WLAN Interface soll gelten und wie ist der DHCP-Bereich:

![DHCP Range und Interfaces](/media/Selbsthilfebasis_DNSMASQ_conf.png "WLAN-Interface anpassen und Startseite")

Ihr wollt die WLAN Zugangsdaten ändern:

![SSID und Passwort](/media/Selbsthilfebasis_HOSTAPD_conf.png "Zugangsdaten festlegen")

Mit diesem QR-Code konfiguriert ihr euer Handy fürs WLAN:
![QR-Code mit Netzwerkkonfiguration](/files/QR-Code_WLAN_Notfall-Treffpunkt.png "scannen und im WLAN einloggen")

Dieser QR-Code bringt euch auf die Startseite mit den Links:
![QR-Code zur Startseite](/files/QR-Code_Startseite_Notfall-Treffpunkt.png "scannen und ihr seid auf der Startseite")



## Installation
Spielt das vorbereitete Image auf eine neue SD-Karte für den RaspberryPi. Legt diese ein und startet den RaspberryPi erstmalig mit Monitor und Tastatur. 
Konfiguriert über `sudo raspi-config` den SSH-Zugang und expandiert das filesystem da das Image komprimiert ist und nicht die ganze SD-Karte nutzt.

## Usage
Starlink-Dish mit freier Sicht zum Himmel aufbauen, Ehternet-Adapter einschleifen. Patch-Kabel zum 4er RaspberryPi. Starlink und RaspberryPi mit Strom aus einer Powerbank versorgen. Bei mir ist es eine Bluetti EB55. Blatt mit Zugangsdaten auslegen, Nachbarschaft informieren, einloggen.  

## Support
for all your questions use `pf@nc-x.com`

## Roadmap
läuft erstmal, sammle weiter interessante Links

## Contributing
eure Mitarbeit und Kritik ist hochwillkommen.

## Authors and acknowledgment
Inspiriert von den Notfalltreffpunkten die in der Schweiz jedes Kaff hat und bei uns mit der Lupe gesucht werden müssen.

## License
MIT Lizenz.

## Project status
lauffähig aber ohne Feinheiten.
