1.- Re-Instalacion de Sistema Operativo DEbian 9 GNU/Linux 

1.1 - Instalar todo en una particion con LVM
1.2 - El Equipo se compone de 2 discos seleccionar la instalacion del S.O. en 1 solo, dejar el otro libre
1.3 - Conectar el equipo a la red 192.168.200.0/24, puerta enlace 192.168.200.2, DNS 192.168.200.2

2.- Una vez dentro del equipo instalar las siguientes paquetes de software:

2.1 dcfld, autopsy, forensics-all, sleuthkit, foremost, afflib-tools, testdisk

3.- Montar en /mnt/disk la segunda unidad SSD que se encuentra en su equipo, para ello

3.1.- Identifique la unidad a trabajar
3.2.- Particione el disco con un tamaño de 2GB
3.3.- Crear un sistema de archivos
3.4.- Monte la unidad en el punto de montaje /mnt/disk
3.5.- Copie archivos con evidencia a analizar dentro del punto de montaje, elimine algunos archivos (anote el nombre y contenido)

4.-Trabajando con dcfldd

4.1.- crear un imagen del disco a analizar y tome un resumen md5 del mismo

dcfldd hash=md5 if=/dev/sdX of=image.dd

4.2 crear una imagen del disco a analizar y tome un resumen cada 1GB

dcfldd hash=sha1 hashwindow=1G if=/dev/sdX of=image.dd

4.3 Verificar la imagen tomada

dcfldd vf=image.dd if=/dev/sdX

5.- Extraer una imagen de disco y copiarla via red hacia otro equipo

dcfldd hash=sha1 if=/dev/sdX |ssh user@192.168.200.aaa dd of=/home/user/image.dd






