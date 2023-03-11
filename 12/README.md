# maman 12
In this maman we we wrote the command `ps` to support containers on xv6 system using a custom syscall.
Following this [guide](https://github.com/raj-maurya/xv6-public_modifiedOS) 

## How to run?
```bash
make clean
make qemu
ps
pouch start c1
pouch connect c1
ps
```

## Expected Output:
```bash
init: starting sh 
$ ps 
main-loop: WARNING: I/O thread spun for 1000 iterations 
name pid state extpid ppid cputime 
init  1   SLEEPING  1 0     55965 
sh    2   SLEEPING  2 1     15027 ps 
ps    3   RUNNING   3 2     6978 
$ pouch start c1
Pouch: c1 starting 
$ ps 
name pid state extpid ppid cputime 
init 1 SLEEPING 1 0 55965 
sh 2 SLEEPING 2 1 26633 
ps 7 RUNNING 7 2 27202 
pouch 5 SLEEPING 5 1 12803 
sh 1 RUNNING 6 5 3771386 
$ pouch connect c1 
tty0 connected ps 

name pid state extpid ppid cputime 
init 1 SLEEPING 1 0 55965 
sh 2 RUNNING 2 1 5162115 
ps 2 RUNNING 9 1 6639 
pouch 5 SLEEPING 5 1 12803 
sh 1 SLEEPING 6 5 25363971 

```
