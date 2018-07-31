accessing-linux-file-systems

ADMINISTRACION DE DISPOSITIVOS
-------------------------------------

Tipos de discos SCSI,PATA/SATA o USB

/dev/sda SCSI/SATA DEVICE
/dev/vda VIRTUAL DEVICE

# blkid /dev/sda
sirve para ver el UUID de un disco

# mount /dev/sda1 /mnt/data
Esto es reomentable para montar recursoss

# mount UUID="UUID del disco" /mnt/data
Esto es mas recomendable usarlo para configurarlo en el fstab porque algunas veces el elos reinicios los nombres se cambian de los discos.
Mayormente pasa cuando se dejan conectados usbs el sda puede cmabiar a sdb etc

# umount /mnt/data
Esto es para desmontar un disco, nadie debe de estar usandolo

# lsof /mnt/data
Esto sive para ver quien esta usandolo

ADMINISTRANDO ENLACES
--------------------------------------

Enlaces simbolicos
# ln -s /var/www/origen /etc/destino
si se borra el original se rompre el enlace

Enlaces duros
# ln /etc/passwdorigen passwd1
sirve para duplicar un archivo 
si se borra el original no se rompre porque hay una replica que tambien usa el espacio

Un inodo es un puntero dentro de los registro de discos que mantiene los registro de los archivos o directorios en un SO

Los inodos son limitados por disco
Los enlaces simbolicos ocupan un inodo
Los enlaces duros no consumen inodos

COMANDO LOCATE
---------------------------------------

busqueda rapida

# updatedb
actualiza los indices de busqueda del locate

# locate -i message
opcion
i ignora el CASE SENSITIVE


COMANDO FIND
----------------------------------------

busca con mas opciones

opciones
iname ignora el CASE SENSITIVE

# find / -iname message

# find / -user student1

# find / -uid 1001

# find / -guid 5000

# find /root/perm -perm 640
busca los archivos que tenga permiso 640
# find /root/perm -perm -644
busca que tengan desde 644 hasta 777
# find /root/perm -perm /001
busca que el tercer campo deba tener ejecucion
# find / -size +10G

 

