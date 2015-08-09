# site-ffbin
Site-Config für das Freifunk-Bingen Image

Basierend auf der Config des Freifunk Mainz
https://github.com/freifunk-mwu/site-ffmwu

Anpassungen der site.conf:

site_name = 'Freifunk Bingen'
site_code = "ffbin'
ntp_servers = {
	'0.pool.ntp.org', --ntp.org
	'1.pool.ntp.org', --ntp.org
        '2.pool.ntp.org', --ntp.org
},


ssid = 'Freifunk Bingen'

mirrors = { 'http://firmware.freifunk-bingen.de/stable/sysupgrade', -- combined (DNS) }

pubkeys = {

good-keys=1 # Es wird nur eine gültige Signatur gebraucht

...

'be8032ec4ddb4bbc0da9032dbec29372f24f7ca9af46186bceaccc2bcea9a93f', -- ffbin-stefan

...

}

Anpassungen site.mk:

Aktualisierungs-Prioritaet auf 1 gesetzt (Updatre nicht sofort, sondern im Laufe eines Tages)
In der Stable-Variante Image-Dateiname ohne Build-Datum (wegen der Lesbarkeit)
