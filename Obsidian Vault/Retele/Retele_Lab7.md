# Continuare Rutare

Router# Show Ip Route


Configurare Ruta Default
*Router(config#) ip route 0.0.0.0 0.0.0.0 \[IP]*
\[IP\] -> Cel mai indepartat Ip cunoscut de router


s* 0.0.0.0/0 via \[IP\] -> Ruta default
Prin \[IP\] se poate ajunge in orice retea

S-a folosit topologia:
Lab_7_Rutare

172.16.30.0/24
Lan A - 30 IP
Lan B - 46 IP
Lan C - 13 IP


- **Lan B** 172.16.30.0 255.255.255.192
	- 2^n - 2 => 46 => n = 6 biti
	- F Addr: 172.16.30.1 /26
	- L Addr: 172.16.30.\[00| 11 1110] = 62
	- Brd: 172.16.30.63 /26
USD: 172.16.30.64/26
- **Lan A**  172.16.30.64 255.255.255.224
	- 2^n - 2 => 30 => n = 5
	- F Addr: 172.16.30.65 / 27
	- L Addr: 172.16.30.\[010|1 1110] = 94 / 27
	- BRD: 172.16.30.95/27
USD: 172.16.30.96/27
- **Lan C** 172.16.30.96 255.255.255.240
	- 2^n - 2 => 13 => n = 4 biti
	- F Addr => 172.16.30.97/28
	- L Addr => 172.16.30.\[0110| 1110] = 110 / 28
	- Brd => 172.16.30.111 / 28
USD: 172.16.30.112 /28
- **Link** 172.16.30.112 255.255.255.252
	- F Addr: 172.16.30.113/30
	- L Addr: 172.16.30.\[0111 00| 10] = 114/30
	- Brd: 172.16.30.115/30


![[WhatsApp Image 2024-11-20 at 10.03.00.jpeg]]
## Rute Flotante

- Mai intai face ruta statica Catre LanC si LanA din R3
- Pute, seta ruta de la R1 la R2 prin R3 dar va trebui sa facem AD mai mare. AD este mai mare pentru ca va fi pastrat in fisierul de configurare dar nu in tabela de rutare. Dupa ce se incheie ruta R1 ---- R2 de abia atunci se va folosi ruta prin R3
## Comanda Rute Flotante
*Router(config)#  ip route IP_Lan MASK IP_Via AD*
IP_Lan -> Lan-ul prin care se poate ajunge
MASK -> Masca IP_Lan
IP_Via -> adresa ip cea mai indepartata(adresa pe care o vede router-ul si prin care va comunica)
AD -> distanta administrativa

> [!WARNING]
> TEMA: MAI FACEM O TOPOLOGIE CONFORM POZA
> Putem pune DHCP
> Facem doar **adresare**
> Sa scoatem DHCP de pe ruter-ul R2.



![[WhatsApp Image 2024-11-20 at 10.50.04.jpeg]]


192.168.15.0/24

LanA 60 IP
LanB 16IP

##### LanA 192.168.15.0 255.255.255.192 /26
- 2^n -2 >= 60 => n = 6 biti 
- *F Addr*: 192.168.15.1/26
- *L Addr*: 192.168.15.62 /26
- *Brd*: 192.168.15.63/26
**USD**: 192.168.15.64/26

##### LanB 192.168.15.64 255.255.255.255.224
- 2^n - 2 >= 16 => n = 5 biti
- *F Addr*: 192.168.15.65 / 27
- *L Addr*: 192.168.15.94 / 27
- *Brd*: 192.168.15.95 / 27
**USD**: 192.168.15.96

##### Link **R1 R2**: 192.168.15.96 255.255.255.252
##### Link **R1 R3**: 192.168.15.100 255.255.255.252
##### Link **R2 R3**: 192.168.15.104 255.255.255.252




