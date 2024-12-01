# Threading

Resursele impartite intre thread-uri:
- Zona de cod
- Zona de data
- FIsierele

Resursele separate pe fiecare thread:
- Registrii
- Stiva

Unitatea de pe procesor este thread-ul

Context switching intre thread-uri sunt mult mai scurte decat context switching intre procese diferite

<a href=https://en.wikipedia.org/wiki/Translation_lookaside_buffer>Translation lookaside buffer</a> (important de stiut) (TLB)
Adresele din TLB sunt aferente procesului de pe procesor (relativ la proces)

La context switching TLB nu este salvat pentru ca este o memorie cache

# Mutex
Mutex-urile se foloseste pentru un race condition in thread-uri.
**pthread_mutex_lock** blocheaza o portiune sa fie executata pana cand o variabila *pthread_mutex_t* sa se faca unlock prin **pthread_mutex_unlock**


