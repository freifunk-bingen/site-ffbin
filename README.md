# site-ffbin
Site-Config für das Freifunk-Bingen Image

Basierend auf der Config des Freifunk Mainz
https://github.com/freifunk-mwu/site-ffmwu

Anpassungen site.conf:

site_name = 'Freifunk Bingen'

ssid = 'Freifunk Bingen'

mirrors = { 'http://www.freifunk-bingen.de/firmware/stable/sysupgrade', -- combined (DNS) }

pubkeys = {

good-keys=1 # Es wird nur eine gültige Signatur gebraucht

...

'be8032ec4ddb4bbc0da9032dbec29372f24f7ca9af46186bceaccc2bcea9a93f', -- ffbin-stefan

...

}

Anpassungen site.mk:

Vorerst keine, später würde ich das Build-Datum aus dem Dateinamen herausnehmen und das Aktualisierungsintervall von 0 auf z.B. 3 Tage erhöhen
