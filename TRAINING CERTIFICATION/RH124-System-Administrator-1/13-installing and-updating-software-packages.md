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

CONFIGURANDO REPOSITORIOS
---------------------------------

# yum repolist 
des muestra repositorios que tengo

# yum clean all
des borra la cache de yum que es como a vinculado los erepositorios

En la ruta /etc/yum.repos.d/
Aqui se encuentran los archivos .repo que tiene los repositorios

En archivo /etc/yum.conf
opciones globales del yum

Una forma
si te dan una url asi puedes agregar un repositorio
# yum-config-manager add-repo="http://classroom.examble/content/rhel7.0/x86_64/rht/"

Otra forma:
# vi /etc/yum.repo.d/errata.repo

[errata-kernel]
name=Repo Kernel Nuevo
baseurl=http://classroom.examble/content/rhel7.0/x86_64/errata/
enabled=1
gpgcheck=1 (se puede deshabilitar si se confia totalmente en el repositorio, si esta habilitado no permitira la instalacion de los paquedes que jo estan firmados
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-redhat-release

# yum list kernel
muestra el kernel instalado y te muestra los que otros qye hay disponibles

# yum install kernel
instala el nuevo kernel, es lo mismo que haber lanzado # yum update kernel, para que SO tome el nuevo kernel hay que reiniciar.
si se desa iniciar con el anterior, se debe interrumpir el boteo y seleccionar el anterior.


COMANDO RPM
--------------------------------------

opcion
q query
a all
f archivo
i informacion del paquete
l todos los archivos que instala el paquete
c todos los archivos de configuracion que utiliza el paquete
--scripts para ver los postscripts que corre el paquete en su instalacion
-q --changelog: list change information for the package
p package que aun no estan instalados, se puede usar con las opcones anteriopres 

# rpm -qa
muestra los rpm instalados en so SO

# rpm -qaf /etc/ssh/sshd_config
muestra que rpm trabaja con ese archivo

# rpm -qi httpd
# rpm -qpi httpd

# rpm -ql httpd
# rpm -qpl httpd

# rpm -qc httpd
# rpm -qpc httpd

# rpm -qc httpd
# rpm -qpc httpd

# rpm -q --scripts httpd

INSTALAR RPM
--------------------------

desde el yum
yum intall /etc/wonder-wigets-1.0-4.x86_64.rpm

desde el rpm
rpm -ivh wonder-wigets-1.0-4.x86_64.rpm


