installing and-updating-software-packages

rpm - redhat package management

Subscripcion:
 - permite registrarte
 - habilitar repositorios
 - reviciones de software
 - no soporte, porque el que te responde es un robot, su tiempo de respuesta es de 2 horas
 - el valor de la subscripcion es para mantener actualizado el software
 
 # subscription-manager
 
 Precio x año 799$ por año
 Paquetes x host fisicos o paquetes por maquinas virtuales ilimitadas
 
COMANDO YUM
-------------------------
 
administra los repositorios
 
httpd-tools-2.4.6-7.el7.x86_64.rpm
Todo separado por guion - 
 1.-nombre del paquete
 2.-version del paquete
 3.-release del paquete
 4.-arquitectuura del paquete
 
# yum repolist
des muestra que repositorios tiene configurado en el equipo

# yum list httpd
des lista de los repositorios a los que stoy consultando/avisa si esta instalado

# yum list | grep installed
des lista todos los paquetes instalados 

# yum grouplist
des muestra los grupos en resumen

# yum grouplist --hidden
des muestra los grupos tambien escondidos

En la Ruta /etc/pki/rpm-gpg/RPM-
muestra las llaves publicas con las que RHEL firma sus paquetes a las que da soporte

# yum search httpd
# yum info http
des muestra informacion de un paquete

# yum provide httpd
des preguta que librerias/rpm instala ese sow. puedes consultarle rutas por defecto (/etc/root/html)

# yum update
des actualiza el so

el yum no es disruptivo, acumula versiones

# uname -r 
des para ver el kernel que estamos usando

# yum list kernel
des @anaconda es de la instalacion
des ¬rhel es de la instalacion

# yum remove httpd
remueve un paquetye sin sus dependencias

# yum history
des muestra el historico de instalaciones/desinstalaciones

# yum history info 3
des puede decir que e instalado

# yun history undo 3
des borra ese pquete con sus dependencias, es el rollback que vende redhat



