# Despregamento_configuracion_servidores_web

## Pasos previos a realizar

La primera vez que realicéis una práctica será necesario configurar el entorno del sistema en el que se ejecutará. Una vez hecho se usará para todas las demás. Para desplegar el sistema para las prácticas seguid las instrucciones en:

[REQUISITOS](REQUISITOS.md) 
Estos pasos ya están hechos en la máquina virtual que os paso
Lo único que tenéis que hacer es crearos una carpeta compartida en el virtual box para poder manipular los ficheros en vuestro ordenador local. 

## Escenario

El escenario es el conjunto de elementos necesarios para la realización de la práctica. Consistirá en un conjunto de contenedores docker, uno o más, con funciones bien establecidas y descritas en la práctica. Tendrás que realizar los pasos indicados en la práctica en ellos, es decir serán la base de trabajo.

Cada repositorio constará de una serie de escenarios de trabajo, estos escenarios disponen de un archivo de despliegue docker-compose.yml que genera toda la estructura del escenario.

### Creación del escenario de la práctica

Para crear el escenario de la práctica entramos en el directorio en el que se ubica el **docker-compose.yml** y dentro del mismo ejecutamos desde la terminal el comando:

`docker-compose up -d`

El comando anterior creará todos los container docker y los elementos necesarios para la práctica

### Detener y arrancar el escenario

Después de una sesión de trabajo con el escenario debemos de detener el mismo para poder retomarlo más adelante. Para ello ejecutamos desde el mismo directorio del apartado anterior

`docker-compose stop`

Más adelante cuando retomemos el trabajo levantamos de nuevo el escenario ejecutando desde el mismo directorio:

`docker-compose start`

### Acceder al container

Podemos acceder a un container de varios modos

#### Acceder mediante docker-compose exec

**docker-compose exec nombre_servicio bash**

donde nombre_servicio es el nombre del servicio dentro del archivo docker-compose para el container, los cuales se encuentran definidos dentro de la sección services en el archivo encabezando cada sección de creación de container. Por ejemplo si tengo en el docker-compose.yml:

`version: '3'`

`services:`

 `#Service lamp toma el Dockerfile de ./apache`
 
 `lamp:`
 
 etc.
 
 entonces podría acceder a ese container con el comando:
 
 `docker-compose exec lamp bash` 
 
#### Acceder mediante docker exec -it

También podría acceder directamente el container usando el nombre del container (no el del servicio docker-compose).
 
 Para ver los docker container en ejecución del escenario ejecutamos:

`docker ps`

Si el nombre del container es **lamp_lamp_1** accederemos a él con:

`docker exec -it lamp_lamp_1 bash`

#### Acceder mediante ssh

Otra opción sería usar la propia dirección IP del container y acceder por ssh, pues éste servicio está habilitado por defecto en el container. Si la dirección IP es por ejemplo **192.168.199.13**, ejecutaría:

`ssh root@192.168.199.13`

### Eliminar el escenario

Al terminar la práctica y entregar los resultados podéis eliminar el escenario, aunque es recomendable dejarlo durante un tiempo por si necesitáis repasar. Para eliminar los container del escenario y todos los elementos ejecutamos desde el mismo directorio:

`docker-compose down`

O si queremos eliminar también las imágenes docker

`docker-compose down --rmi all`

Si en el escenario se ha creado algún volumen de datos asociado al container y queremos que éstos se borren, deberíamos también añadir la opción -v, por ejemplo para borrar containers, networks, imaǵenes y volúmenes usaríamos:

`docker-compose down --rmi all -v`


## Referencias

### git

[introduccion a git](https://aulasoftwarelibre.github.io/taller-de-git/introduccion/)

### docker

[breve introduccion a docker](https://guiadev.com/introduccion-a-docker/)

### docker-compose

[docker compose de un vistazo](https://docs.docker.com/compose/)
