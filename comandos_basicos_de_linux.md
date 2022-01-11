# Comandos básicos de Linux

Una de las mayores ventajas de **GNU/Linux** con respecto a otros Sistemas Operativos es su terminal, ya que permite realizar fácilmente ciertas operaciones sin tener que recurrir a herramientas gráficas. Para aprender a dar nuestros primeros pasos por ella vamos a explicar algunos comandos imprescindibles imprescindible para la terminal que todo usuario de Linux debe saber.

## Sudo, para ejecutar comandos con permisos de administrador

Viene de _super user do_ o _el super usuario hace_, y es posiblemente el comando más importante, ya que lo tenemos que utilizar para acompañar a todos aquellos otros comandos con los que queramos hacer cualquier tipo de cambio sensible en el sistema, desde gestionar paquetes hasta editar archivos: es decir, aquellos que requieran permisos de administrador.

Debido a la seguridad de Linux no podremos realizar cambios en el sistema a no ser que seamos super usuarios o administradores, por lo que la primera vez que 
compongamos un comando que lo contenga tendremos que escribir nuestra contraseña de administrador.

### Ejemplos de uso del comando _sudo_:

Resincronizar las fuentes de los paquetes del repositorio:

```bash
sudo apt-get update
```

Editar la configuración de un servidor web Nginx:

```bash
sudo nano /etc/nginx/nginx.conf
```

Si no añadimos el comando _sudo_ a aquellos comandos que requieren permisos de administrador para poder ejecutarse, obtendremos un error como este:

```bash
apt-get update
E: Could not open lock file /var/lib/apt/lists/lock - open (13: Permission denied)
E: Unable to lock directory /var/lib/apt/lists/
E: Could not open lock file /var/lib/dpkg/lock - open (13: Permission denied)
E: Unable to lock the administration directory (/var/lib/dpkg/), are you root?
```


## Apt-Get, para la gestión de paquetes

**Apt**, que significa _Advanced Packaging Tool_, es un comando que nos permite instalar paquetes del repositorio del sistema sin necesidad de usar ninguna herramienta gráfica.

A partir de _Ubuntu 16.04_ Canonical ha querido simplificar el comando reduciéndolo a _apt_, aunque de momento apt-get también sigue funcionando.

Este comando sirve para instalar aplicaciones con el terminal, eliminarlas, actualizar tu sistema operativo y realizar diferentes acciones con los paquetes. 

### Ejemplos de uso del comando Apt-Get

Instalar el servidor NGinX en el sistema:

```bash
sudo apt-get install nginx  # Opción 1
sudo apt install nginx      # Opción 2
```
   
Eliminar el servidor NGinX del sistema:

```bash
sudo apt-get remove nginx  # Opción 1
sudo apt remove nginx      # Opción 2    
```

Buscar el paquete NGinX:

```bash
apt-cache search nginx
```

Actualizar el listado de paquetes del repositorio (recomendable antes de actualizar el sistema):

```bash
sudo apt update
```

Actualizar los paquetes instalados en el sistema:

```bash
sudo apt upgrade
```

## Cd, para navegar por el sistema de directorios

El comando **cd** son las siglas de _change directory_ y sirve para navegar y movernos por el sistema de directorios de nuestro sistema.

### Ejemplos de uso del comando Cd


Ir a la raíz de nuestro directorio personal, la carpeta Home:

```bash
cd
```

Acceder a la carpeta Descargas:

```bash
cd Descargas
```

Retroceder al directorio anterior:

```bash
cd ..
```

Acceder al directorio Descargas utilizando la ruta absoluta desde la raíz del sistema, si mi usuario es 'alumno': 

```bash    
cd /home/user/Descargas
```

Acceder a la carpeta raíz del sistema:

```bash
cd \
```

## Cat, monstrar el contenido de un archivo

Sirve para ver el contenido de un fichero sin utilizar un editor de texto.

### Ejemplos de uso del comando Cat


Mostrar el contenido de un fichero en el terminal

```bash
cat documento.txt
```

Mostrar el contenido de un fichero en el terminal, monstrando el número de cada línea:

```bash
cat -n documento.txt
```

## Ls, listando archivos y carpetas

Si estamos buscando un archivo determinado en una carpeta a través del terminal es bastante importante saber en primer lugar si está donde lo estamos buscando. Y ahí es precisamente donde entra en juego el comando **ls** o _list_, con el que se nos mostrará una lista con los directorios y archivos de la carpeta en la que estemos. Aquí unos ejemplos:

### Ejemplos de uso del comando Ls

Listar las carpetas y archivos dentro del directorio en el que estamos actualemnte:

```bash
ls
```

Listar las carpetas y archivos, incluyendo archivos y carpetas ocultos en el sistema (aquellos que comienzan por un '.'):

```bash
ls -a
```

Muestra información adicional de los archivos y carpetas (propietario, grupo, tamaño, permisos, fecha de modificación):

```bash
ls -l
```

Listar las carpetas y archivos, incluyendo los archivos y carpetas que están dentro de los subdirectorios:

```bash
 ls -r
```

## Find, permite buscar archivos

El comando find permite buscar archivos en nuestro sistema

### Ejemplos de uso del comando Find

Buscar el archivo _fichero.txt_ en la carpeta actual (sin tener en cuenta mayúsculas y minúsculas)


```bash
find . -iname fichero.txt
```

* .: hace referencia al directorio actual en el que estamos.
* -iname: busca el fichero fichero.txt sin tener en cuenta mayúsculas y minúsculas.

Buscar archivos con extensión _pkt_ en la carpeta Home del usuario _usuario_:

```bash
find /home/usuario -iname *.pkt
```

## Tree, lista los archivos y directorios en formato árbol

El comando **Tree** lista los arhivos y directorios en formato árbol.

### Ejemplos de uso del comando Tree

Instalar el paquete _tree_:

```bash
sudo apt install tree
```

Listar los archivos en formato árbol:

```bash
tree
```

