编译静态库方法：

```shell
$ gcc -c bill.c fred.c
$ ls *.o
bill.o fred.o
$ gcc -c program.c
$ gcc -o program program.o bill.o
$ ./program
bill: we passed Hello World
$ 
```

```shell
$ gcc -c bill.c fred.c
$ ar crv libfoo.a bill.o fred.o
a - bill.o
a - fred.o
$ ranlib libfoo.a
$ gcc -c program.c
$ gcc -o program program.o libfoo.a
$ ./program
bill: we passed Hello World
$
```

```shell
$ gcc -c bill.c fred.c
$ ar crv libfoo.a bill.o fred.o
a - bill.o
a - fred.o
$ ranlib libfoo.a
$ gcc -c program.c
$ gcc -o program program.o -L. -lfoo
bill: we passed Hello World
$
```