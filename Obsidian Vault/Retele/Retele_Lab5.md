# DHCP

DHCP:
- Layer 7(Application)
- Layer 4(UDP) -> 67 \[server\]
		    -> 68  \[client\]


## Etape DHCP

1. DHCP Discovery ----------------------> 255.255.255.255
2. DHCP OFFER <--------------------------(oferta prima venita prima servita) 1 IP1; 2 IP2
3. DHCP REQUET--------------------------->255.255.255.255 (IP1)
4. Serverul se poate afla in: 
	1. DHCP ACK <---------------------------- 255.255.255.255
			Daca pe tabela BIND nu are adresa IP1 - MAC atunci imi da IP1
	2. DHCP DECLINE
			Daca pe tabela BIND are adresa IP1

>[!WARNING]
>DHCP Trimite mereu broadcast pentru ca echipamentul nu are adresa ip

Dupa ce primesc adresa IP se fac 3 probe de ARP si un ARP Announcement


## Exercitiu
![[Pasted image 20241106083119.png]]

192.168.14.0 /24
26 Adrese: 255.255.255.224
- F. addr -> 192.168.14.65/27
- L. addr -> 192.168.14.94/27
- Broad -> 192.168.14.95/27

44 Adrese: 255.255.255.192
- F. addr -> 192.168.14.1/26
- L. addr -> 192.168.14.62/26
- Broad -> 192.168.14.64/26

13 Adrese: 255.255.255.240
- F. addr -> 192.168.14.97/28
- L. addr -> 192.168.14.111/28
- Broad -> 192.168.14.112/28

## Configurare Router pentru DHCP
Router(config)\#ip dhcp pool \<NAME\>
Router(dhcp-config)\#default-router \<IP_ADDR\>
Router(dhcp-config)\#network \<IP_NETWORK\> \<MASK\>
Router(dhcp-config)\#dns-server \<IP\>
Router(dhcp-config)\#domain-naim \<NAME\>
Router(config)\#ip dhcp excluded-address \<IP\>(aici de obicei se pune prima adresa)

## Configurare Ip switch folosind dhcp
Switch(config)# interface vlan1
Switch(config-if)# ip address dhcp

## Afisare tabela dhcp binding
Router\# show ip dhcp binding

## Configurare server DHCP individual(nu Router)
Setare Adresa Ip statica a server-ului
Setare din Services-> DHCP -> Configurare ip si masca
>[!IMPORTANT]
>Se va creea un nou pool cu numele setat de mine. Pool-ul vechi trebuie sa fie configurar astfel incat sa aiba toate datele pe 0 0 0 0. Apoi se da save la Pool-ul vechi si la pool-ul nou creat

# Exercitiu tema
Adresa: 172.16.40.128 / 25
Lan B 255.255.255.192
	2^n >= 33 => n = 6 biti
	F. addr = 172.16.40.\[10|00 0001\] = 172.16.40.129/26
	L. addr = 172.16.40.\[10|11 1110\] = 172.16.40.190/26
	Broad = 172.16.40.191/26
USD = 172.16.40.192/26

Lan C 255.255.255.240
	2^n >= 10 => n=4 biti
	F.addr = 172.16.40.\[1100| 0001\]=172.16.40.193/28
	L.addr = 172.16.40.\[1100| 1110\]= 172.16.40.206/28
	Broad = 172.16.40.207/28
USD=172.16.40.208/28

Lan A 255.255.255.248
	2^n => 6 => n = 3 biti
	F.addr = 172.16.40.209/29
	L.addr = 172.16.40.\[1101 0|110] = 172.16.40.214/29
	Broad = 172.16.40.215/29
USD = 172.16.40.216/29