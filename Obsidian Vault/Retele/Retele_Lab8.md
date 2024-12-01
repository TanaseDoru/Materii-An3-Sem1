# Protocolul RIP - Routing Information Protocol
Protocol de rutare dinamic. Cuantificam distanta pe baza de hop-uri
## RIP are:
- **AD** = 120 (**D**istanta **A**dministrativa)
- **Metrica** = Nr Hop-uri
RIP este limitat la ***15*** hop-uri
# Algoritmul Bellman-Ford
![[Pasted image 20241122081544.png]]

Distanta de la 1 la 4 este INF. Pentru RIP va face metrica de **16** Ca sa il considere infinit

# Cont.
RIP are
- L_7 - Aici lucreaza
- L_4 UDP - 520
- L_3 224.0.0.9 -> adresa multicast(orice dispozitiv care cunoaste RIP este introdus in multicast)

RIP are 2 versiuni:
V1 - LSM
V2 - VLSM

RIP transmite adresa sa de rutare la fiecare **30s**
Rutere invatate sunt considerate invalide dupa **180s**
Iar dupa inca **60s**(In total dupa **240s**) se sterge intrarea din tabelul din rutare

# Configurare RIP
- Router(config)# *router rip*
	- Router(config-router)# *version 2*
	- Router(config-router)# *no auto-summary*
	- Router(config-router)# *network \<ID Retea1>*
	- Router(config-router)# *network \<ID Retea...>*
	- Router(config-router)# *network \<ID ReteaN>*

- Comanda pentru a opri transmiterea de pachete de tip RIP pe o interfata
- Router(config-router)# *passive-interface \<INTERFACE\>*

Prin comanda *do show ip protocol*  se afiseaza interfetele pe care stie sa faca rip. Prin aceasta comanda se verifica ca am setat bine adresele de retea

# Configurare IP-Helper
IP-Helper ajuta un ruter sa comunice un un alt ruter pentru a primi IP de la DHCP
- Router(config)# *interface \<INTERFACE\>* 
- Router(config-if)# *ip helper-address \<IP\>*
Unde \<INTERFACE\> este interfata pe care se primeste cereri de dhcp de la calculatoare(ex Gigabit 0/0)
SI \<IP\> este adresa ip al celui mai indepartat punct pe care stie ruter-ul ca se afla DHCP-ul. Adica adresa ip de la ruter-ul opus de pe LINK

# Setare iesire din Retea in ISP
Trebuie setat in ainte o ruta statica de tip default
Router(config)# *ip route 0.0.0.0 0.0.0.0 \<IP\>*
Router(config)# *router rip*
Router(config-router)# *default-information*

>[!INFO]
>Se lucreaza in proiectul *Lab_8_Topo Tanase Doru*

Pe lincurile seriale nu se foloseste protocolul **Ethernet** si un protocol **HDLC**(Cred)

# Lucru
Poza Urmatoare se gaseste si pe **WIKI** la laboratorul de **Rutare**
![[Pasted image 20241122092658.png]]
![[Pasted image 20241122111517.png]]

>[!IMPORTANT]
>De configurat RIP si iesire default pe R2


>[!INFO]
> Lucrul este efectuat in *Lab_8_Tema*

