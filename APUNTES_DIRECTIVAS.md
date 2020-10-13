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

## Directivas de configuración básica

### Listen 

Esta directiva indica a través de que portos e interfaces IP aceptará peticións. Por defecto, responde peticións en todas as as interfaces, no porto que se indique. Se encontra no ficheiro /etc/apache2/ports.conf
#### Exemplos
	Para facer que o servidor acepte conexións nos portos 80 e 8080:
    `Listen 80`
    `Listen 8080`

### ServerRoot 

Especifica a localización do directorio raíz onde ser atopa instalado Apache. Esta directiva non debería cambiar a non ser que se mova o cartafol de instalación de Apache a outra loca-lización. Encóntrase no ficheiro /etc/apache2/apache2.conf 

#### Exemplos
	ServerRoot /etc/apache2

### Include 

Permite que se inclúan outros arquivos de configuración en tempo de execución. A ruta a estes arquivos de configuración poden ser absolutas ou relativas con respecto ao directorio indicado en ServerRoot. Encóntrase no ficheiro /etc/apache2/apache2.conf 

#### Exemplos
    Include ports.conf
    
### DocumentRoot 

Indica o directorio desde o que Apache vai servir os arquivos. O servidor engade a ruta indi-cada na URL a este directorio.
Todos os directorios que vai servir Apache deben ter permisos de lectura e execución para todos os usuarios e todos os arquivos que serve deben ter permiso de lectura. Recordemos que os permisos de arquivos e directorios se cambian en Linux co comando chmod.

#### Exemplos
    Para un valor
    DocumentRoot /var/www/html
    Se a URL solicitada é http://www.meuservidor.com/proba/index.html Apache servirá o ficheiro index.html que se atopa en /var/www/html/proba

### ErrorLog 

Especifica a localización do ficheiro que contén o rexistro de erros. Se a ruta que se indica non é absoluta, considerarase relativa ao ServerRoot. Por defecto atópanse no cartafol logs dentro de ServerRoot.

#### Exemplos
    ErrorLog /var/log/httpd/error_log

### DirectoryIndex 

Especifica o ficheiro por defecto que se servirá para cada directorio, no caso de que non se especifique ningún na URL. Por defecto é index.html. 
Poden indicarse varios ficheiros. A orde co que se especifica o nome de ficheiro determinará a prioridade á hora de decidir que ficheiro é o que se amosa.

#### Exemplos
   DirectoryIndex index.html indice.html index.php

