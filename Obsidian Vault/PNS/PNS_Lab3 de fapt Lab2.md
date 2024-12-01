# Suport din curs
## Intarziere si Avans
**Intarzierea** reprezinta mutarea semnalului mai la dreapta(deplasarea la dreapta)
Formula: x<sub>d</sub> (t) = x(t - T<sub>0</sub>)
**Avans** reprezinta mutarea semnalului mai la stanga(deplasarea la stanga)
Formula: y<sub>f</sub>(t) = x(t + T<sub>0</sub>)

## Semnale elementare
### 1. Semnal Treapta unitate
![[Pasted image 20241021084356.png]]
### 2. Semnalul Impuls Dirac
![[Pasted image 20241021084459.png]]
Clasa L2 -> Modulul la patrat este integrabil => Ii putem masura energia
#### Reprezentare Grafica:
![[Pasted image 20241021084630.png]]
### 3. Semnalul impuls unitar
![[Pasted image 20241021084704.png]]

### 3. Semnalul rampa
![[Pasted image 20241021084837.png]]
# Lucru Laborator
t=0:0.1:10
unitstep=t>=0; ->
unistep este un vector ce rezulta din functia t >= 0;
Astfel, unistep va fi un vector cu valori de 1(100 de valori de logical 1) si trebuie facut double


```matlab
unitstep_T3=t>=3;
ramp_T3 = (t-3).*unitstep_T3;
.* -> face inmultire element cu element
ramp_T3 -> face inmultire de la 3 in colo cu finctia t - 3
Prin functia asta face o functie r_T3(x) = t - 3 adica o dreapta la 45 de grade care incepe la secunda 3
```
# Tema
Sa luam exercitiile de la 3 si sa le punem in interfata grafica si sa avem butoane radio prin care vom afisa graficele

# Alte notite
Pentru generarea odei bucuriei folosind concatenare de sinusuir
s[n] = sin(2pi\*f<sub>n</sub> \*n)
f<sub>n</sub> = f<sub>s</sub> / f<sub>e</sub> <= 1/2


Melodia creeata fara sa se auda sunete de **poc** ( cu acumulatori de faza )
n -> s\[n\] = sin(2pi\*f<sub>n</sub> \* n)
n+1 -> s\[n + 1\] = sin(2pi\*f<sub>n</sub> \* n + 2pi\*f<sub>n</sub>)
n + 2 -> s\[n + 2\] = sin(2pi\*f<sub>n</sub>\*n + 2pi\*f<sub>n</sub> + 2pi\*f<sub>n</sub>)
Am creat o continuitate de faza si nu se mai percepe senzatia de **poc**

