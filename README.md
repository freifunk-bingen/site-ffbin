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

Aktualisierungs-Prioritaet auf 1 gesetzt Auto-(Update nicht sofort, sondern im Laufe eines Tages)
In der Stable-Variante Image-Dateiname ohne Build-Datum (wegen der Lesbarkeit)


Solltest Du noch ein Image mit alter (falscher) Auto-Update URL haben kannst Du von Hand aktualisieren:
Im Netz "Freifunk Bingen" via ssh auf den "Next Node" (Deinen Node) einloggen. Damit

ssh root@10.37.0.1

funktioniert, musst Du Deinen oeffentlichen SSH-Key auf dem Node hinterlegt haben, oder ein passwort fuer
root in der Gluon-Konfiguration vergeben haben.

auf der Konsole dann

uci delete autoupdater.stable.mirror

uci add_list autoupdater.stable.mirror="http:/firmware.freifunk-bingen.de/stable/sysupgrade"

uci commit

Danach sollte das Update funktionieren:

autoupdater -f


