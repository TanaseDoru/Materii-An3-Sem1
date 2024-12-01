# Rutare
In router se afla tabela de rutare pentru forwarding(ca in switch tabela `CAM`)

## Exemplu Tabela Rutare
***Tabela Rutare R1***
C - stie sa ajunga in LanA, prrin interfata G0/0
L - IP1/32 (Cel mai lung prefix dintr-o tabela de rutare 32 de biti), interfata G0/0
C - Link G0/1
L - Ip2/32 - g0/1
S - LanB \[AD/Metrica] via Ip3 (Stie sa ajunga in LanB prin Ip3)
AD -> Distanta Administrativa (C -> 0; S -> 1)
Metrica -> Este calculata prin diferite metode(este 0 pt ca e rutare statica)

***Tabela R2***
C Link
L Ip3/32
C LanB
L Ip4/32

C -> Connected
L -> Local
S -> Static

Topografie:
![[Pasted image 20241108091329.png]]

Vrem sa ajungem din :
PC1 -> Server **NU**
PC1 -> D Gw(IP1) **DA**
MAC<sub>pc1</sub> -> MAC g0/0 **NU**


### Configurare rutare:
**Pentru a trece din LanA in LaB trebuie configurat:**
(config)\# ip route LanB SubnetMask IP3
## Moduri de rutare
1. Rutare Statica
2. Rutare Dinamica
