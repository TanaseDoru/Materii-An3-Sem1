
# Memorie Virtuala

![[Pasted image 20241121121827.png]]


In **CR3*** se afla adresa de unde se face paginarea

- `MAP_PRIVATE` - Private mapping, folosind _copy-on-write_ Se copiaza o zona de memorie in loc sa o acceseze tot pe aceea
![[Pasted image 20241121123210.png]]


- - `MAP_SHARED` - Shared mapping, modificările sunt actualizate imediat în toate mapările existente -> Un nou proces lucreaza efectiv cu zona de memorie pe care o foloseste cel original

![[Pasted image 20241121123402.png]]



-  `MAP_ANONYMOUS` - Se mapează memorie RAM (argumentele `fd` și `offset` sunt ignorate) -> Se creeaza o zona de memorie virtuala si nu e salvata disc

![[Pasted image 20241121124032.png]]

**IPC** -> Memorie partajata: O zona de memorie prin care se face comunicare interprocese. Fara pipe etc. O zona de memorie prin care se partajeaza date





