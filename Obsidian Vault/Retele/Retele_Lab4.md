ICMP -> Layer 3; ARP -> Layer 2


ping PC2                                      echo req - type 8
-------------------------------------------------------->
PC1                                                                               PC2
    <---------------------------------------------------
						    echo reply type 0

Cele mai importante coduri:
	echo req -> type 8
	echo replay -> type 0
### Traceroute
traceroute -> limitat la 30 hop-uri
(tracert - pt WIN)
Mod functionare traceroute
(R -> Router)
PC1.......................R......................................R___\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_PC2
TTL =1         TTL=0(type 11)
 .                    *
 TTL=2          TTL=1                     TTL=0
 
1. Pleaca cu TTL = 1, cand TTL se face 0, transmite un mesaj la sursa astfel:
	   Mesaj cu informatii despre echipamentul la care s-a oprit(time exceded)
	   Sau trimite \* -> Fara informatii despre echipament

Destination unreachable -> type 3

## Protocolul ARP
RARP: Stiu adresa MAC, vreau sa aflu care este adresa IP
Mapare adrese IP cu arese MAC

1.
ping IP2
**IP1**                                                                IP2

Cazuri:
1.  IP1, IP2 (LAN)
	? MAC - IP2


2.
**IP1**.......................................R......................................IP2

(1) X
(2) IP1 - Default Gateway
(3)ARP

## ARP Probe
Trimite 3 Probe-uri ARP. Daca nu primeste raspuns da un **ARP ANNOUNCEMENT**. Si isi transmite adresa ip si mac pentru a folosi adresa ip respectiva.

Daca 2 echipamente au aceasi adresa IP, Ambele trebuie sa isi elibereze adresele. Doar ca cel mai vechi trebuie sa astepte sa se inchide socket-urile folosite si dupa o elibereaza.

## Gracious ARP
Un echipament isi transmite date despre el si se descrie tuturor echipamentelor. Ex: Gateway trebuie sa isi prezinte adresa de gatway tuturor echipamentelor.