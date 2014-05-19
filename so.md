#Sistemas Operacionais

##Projeto - Fase 1:

###Comandos Úteis

Assumindo:
	- nome do programa init: test.c

- Descompactar .tar.bz2: `sudo tar xjf <nome-do-arquivo>.tar.bz2`

- Descompactar .tar.gz: `sudo tar xf <nome-do-arquivo>.tar.gz`

- Transformar o "init" binário no sistema de arquivos do linux: `echo test | cpio -o --format=newc > rootfs`

- Compilar o init.c: `arm-linux-gnueabi-gcc -static test.c -o test`

- Iniciar o linux para modo debug: `qemu-system-arm -M versatilepb -m 128M -kernel zImage -initrd rootfs -append "root=/dev/ram rdinit=/test" -S -s` (basta remover as flags -s e -S para rodar direto)

- Rodar o debugger: `/usr/local/arm-2011.03/bin/arm-none-eabi-gdb vmlinux`
