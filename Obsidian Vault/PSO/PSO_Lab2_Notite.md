## Tabela de fisiere pentru exercitiu

```c
#include <unistd.h>

#include <fcntl.h>

#include <stdio.h>

int main() {

    int fd1, fd2;

    close(2);

    fd1 = open("/home/student/file1.txt", O_WRONLY);

    fd2 = open("/home/student/file2.txt", O_WRONLY | O_CREAT, 0644);

    close(0);

    printf("%d\n", fd2);

    return 0;

}
```

### Initial: 
 0 -> /dev/pts
 1 -> /dev/pts
 2 -> /dev/pts

#### Close(2)
Stergem 2
#### fd = open
2 -> file1.txt

#### fd = open
3 -> file2.txt

#### close(0)
Stergem 0

#### daca aveam open file3.txt
0 -> file3.txt
### Concluzie

Orice citire va fi din file3.txt (file descriptor 0)


## Alt exemplu

`$ ./myscript > results.log 2>$1

Vom avea: 
0 -> tty
1 -> tyy -> results.log
		 ^
2 -> tty ---|

1 va fi results.log, la fel si 2

#### Cum ar functiona codul:
```c
close(1);
fd = open("results.log", ...);
dup2(fd, STDOUT_FILENO);
```



