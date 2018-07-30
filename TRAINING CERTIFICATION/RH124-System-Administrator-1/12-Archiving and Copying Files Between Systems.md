
ADMINISTRACION DE COPIAS REMOTAS
---------------------------------

cmd scp
des copias remotas de archivos
cmd rsync
des copias incluso con diferencial

Para hacer backup en linux es el tar
Los backups pueden estar en doble nivel que el zipeado
 - 1er niver es tar
 - 2do nivel puede ser gzip bzip2 o xz que es el mejor

COMANDOS TAR
------------------------------------

opcion
c crea un archivo
v verbose que es tipo debug cuando va descomprimiendo
f para archivo o directorio

# tar -cvf etc.tar /etc
des esto es un primer nivel de comprencion

# tar -czvf etc.tar.gz /etc
des esto es un segundo nivel de comprencion, se le agrega la z
# tar -jzvf etc.tar.bz2 /etc
des esto es un segundo nivel de comprencion, se le agrega la j
# tar -Jzvf etc.tar.xz /etc
des esto es un segundo nivel de comprencion, se le agrega la J

Todo lo que sea z va a generat un *.tar.gz o *tgz
Todo lo que sea j va a generar un *.tar.bzip2
Todo lo que sea J va a generar un *.tar.xz

El que mas comprime es el xz y es el nativo por linux

opcion
t para listar el contenido de un archivo
f endica que es un archivo

# tar -tf etc.tar

opcion
x extrae un archivo

# tar -xzvf etc.tar.gz
# tar -xjvf etc.tar.bz2
# tar -xJvf etc.tar.xz

opcion
p Preserve the permissions of files and directories when extracting an archive, without subtracting the umask.

COMANDO MD%
--------------------------------------------
Sirve poara validar que el archivo esta correcto y el archivo no esta corrupto
Al bajarme el tar ellos deben de decirme como calcuraron la integridad de este archivo
Si usaron md5sum o sha512sum y el numero que genero
Yo uso ese mismo comando en mi maquina y veo si me genera el mismo numero

Yo tambien podria hacer el mismo procdimiento para poder compartir y verificar que sea integro.

# md5sum etc.tar 


