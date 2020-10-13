# Directivas Apache

## Lanzar e parar de Apache 

Cada vez que se modifican os ficheiros de configuración, para que os cambios teñan lugar, é preciso que se reinicie o servidor.
Para parar o servizo, emprégase o comando:
`sudo service apache2 stop`
Para lanzar o servizo, emprégase o comando:
`sudo service apache2 start`
Se queremos parar e relanzar o servizo:
`sudo service apache2 restart`
Para ver si el servicio está activo podemos ejecutar:  
`sudo systemctl | grep apache`

## Directivas de configuración básica del fichero de apache2.conf

### ServerRoot 

Especifica a localización do directorio raíz onde ser atopa instalado Apache. Esta directiva non debería cambiar a non ser que se mova o cartafol de instalación de Apache a outra localización.

#### Exemplos
	ServerRoot /etc/apache2

### Include 

Permite que se inclúan outros arquivos de configuración en tempo de execución. A ruta a estes arquivos de configuración poden ser absolutas ou relativas con respecto ao directorio indicado en ServerRoot. 

#### Exemplos
    Include ports.conf

###  Timeout
Define, en segundos, el tiempo que el servidor esperará por recibir y transmitir durante la comunicación. Timeout está configurado por defecto a 300 segundos, lo cual es apropiado para la mayoría de las situaciones. El usuario puede realizar una única petición pero esa petición puede generar más de una petición. 
#### Ejemplos
	Timeout 300 

###  KeepAlive
 Define si las conexiones persistentes están activadas. Por defecto están activadas. En una misma conexión TCP podemos generar varias solicitudes y varias respuestas HTTP. 
#### Ejemplos
	KeepAlive On  

### MaxKeepAliveRequests
Establece el número máximo de peticiones permitidas por cada conexión persistente. Por defecto está establecido como 100. Si el cliente solicita más de 100 peticiones HTTP se cierra la conexión TCP y se vuelve a abrir. 

#### Ejemplos
	MaxKeepAliveRequests 100

###  KeepAliveTimeout
Establece el número de segundos que el servidor esperará tras haber dado servicio a una petición, antes de cerrar la conexión. Por defecto 5 segundos. Una vez que se abre la conexión TCP tiene 5 segundos para realizar peticiones, sino se cerrará. Esto tiene que ver con el rendimiento del sistema, para que no tener procesos ocupados esperanod a que le envíen peticiones. 
#### Ejemplos
	KeepAliveTimeout 5
###  User
 Define el usuario que ejecuta los procesos de Apache2. Por defecto wwwdata. Se define en una variable de entorno definida en el fichero /etc/apache2/envvars. 
 #### Ejemplo
    User ${APACHE_RUN_USER}
###  Group
 Define el grupo al que corresponde el usuario.
  #### Ejemplo
    User ${APACHE_RUN_GROUP}

### ErrorLog 

Especifica a localización do ficheiro que contén o rexistro de erros. 
#### Exemplos
    ErrorLog /var/log/apache2/error_log
###  LogLevel
 Controla el nivel de información que se guarda en los ficheros de registro o logs. Apache tiene distintos ficheros de log, aquí definimos el nivel de información que queremos guardar. 
   #### Ejemplo
    loglevel warn
###  LogFormat
 Controla el formato de información que se va a guardar en los ficheros logs.
   #### Ejemplo
    logformat "%v:%p ..."
###  Directory o DirectoryMatch 
 Declara un contexto para un directorio y todos sus directorios. DirectoryMatch es para utilizar un expresión regular para indicar los directorios. Son las opciones que le vamos a dar a un directorio y a todos sus subdirectorios. 
   #### Ejemplo
    <Directory />
        Options FollowSymLinks
        AllowOverride None
        Require all denied 
    </Directory>
###  Files o FilesMatch
Declara un contexto para un conjunto de ficheros. Son las opciones que le vamos a dar a un Fichero o a un conjunto de ficheros. 
  #### Ejemplo
    <FilesMatch "^/.ht>
      Require all denied 
    </Directory>



No todas las directivas de configuración se encuentran en este documento también se encuentran en los ficheros .conf en las carpetas enabled.  

