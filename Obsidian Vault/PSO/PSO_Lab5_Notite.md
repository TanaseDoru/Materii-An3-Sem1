RoData -> zona de date ReadOnly
000056387768f000      8K r---- /usr/bin/sleep   -> **RoData**
0000563877691000     16K r-x-- /usr/bin/sleep -> **Zona de cod**
0000563877695000      4K r---- /usr/bin/sleep -> **Probabil Rodata**
0000563877697000      4K r---- /usr/bin/sleep -> **Probabil la fel**
0000563877698000      4K rw--- /usr/bin/sleep -> **.Text**
0000563877834000    132K rw---   \[ anon \]       -> **Probabil zona HEAP** 
00007f7ccbc29000   8456K r---- /usr/lib/locale/locale-archive -> **IDK**
00007f7ccc46b000     12K rw---   \[ anon \] -> **Probabil Heap**
\---------
00007f7ccc46e000    160K r---- /usr/lib/x86_64-linux-gnu/libc.so.6 -> **Aici este mapata biblioteca libc.so.6**
00007f7ccc496000   1620K r-x-- /usr/lib/x86_64-linux-gnu/libc.so.6
00007f7ccc62b000    352K r---- /usr/lib/x86_64-linux-gnu/libc.so.6
00007f7ccc683000      4K ----- /usr/lib/x86_64-linux-gnu/libc.so.6
00007f7ccc684000     16K r---- /usr/lib/x86_64-linux-gnu/libc.so.6
00007f7ccc688000      8K rw--- /usr/lib/x86_64-linux-gnu/libc.so.6
\-------
00007f7ccc68a000     52K rw---   \[ anon \] -> **Probabil Heap**
00007f7ccc6ad000      8K rw---   \[ anon \]
\-----------
00007f7ccc6af000      8K r---- /usr/lib/x86_64-linux-gnu/ld-linux-x86-64.so.2 -> **link editor**
00007f7ccc6b1000    168K r-x-- /usr/lib/x86_64-linux-gnu/ld-linux-x86-64.so.2 -> **Biblioteca mapata ca mai sus**
00007f7ccc6db000     44K r---- /usr/lib/x86_64-linux-gnu/ld-linux-x86-64.so.2
00007f7ccc6e7000      8K r---- /usr/lib/x86_64-linux-gnu/ld-linux-x86-64.so.2
00007f7ccc6e9000      8K rw--- /usr/lib/x86_64-linux-gnu/ld-linux-x86-64.so.2
\--------------
00007ffcc11b3000    132K rw---   \[ stack ] ->**Stiva**
00007ffcc11de000     16K r----   \[ anon ]
00007ffcc11e2000      8K r-x--   \[ anon ]
ffffffffff600000      4K --x--   \[ anon ]
 total            11252K

