# Práctica directivas Apache

## Configuración básica Apache 

### Realiza copias de seguridade dos ficheiros de configuración (apache2.conf, ports.conf, sites-available/000-default.conf).

cd /etc/apache2/

sudo cp ports.conf ports.conf.copia

cd sites-available/

sudo cp 000-default.conf 000-default.conf.copia



### No directorio /var/www/html, crea os seguintes arquivos (co contido que prefiras, unicamente debe servir para distinguir uns arquivos de outros) e directorios:
–	principal.html
–	clase/proba1.html
–	clase/proba2.html

Abre o navegador da máquina cliente e establece conexións con cada un dos arquivos (http://192.168.0.1/nomeArquivo). 

### Fai as modificacións adecuadas para que se sirva por defecto o arquivo clase/proba1.html

DirectoryIndex principal.html

### Fai as modificacións que sexan precisas para que no directorio clase non se amose o listado de arquivos cando se pide o raíz do mesmo.

	<Directory /var/www/html/clase>
	   Options -Indexes
	</Directory>

### Modifica a mensaxe de erro para o erro 404.

ErrorDocument 404 "Este ficheiro non está dispoñible"

### Crea o directorio /home/claseDaw/apuntes, que conterá un ficheiro calquera. Crea un alias para que este directorio sexa accesible desde http://ip/clase. 

Alias “/clase”  “/home/claseDaw/apuntes”

### Crea unha redirección, de xeito que cando se faga unha petición a http://192.168.0.1/portal, se redirixa á páxina http://edu.xunta.gal

	Redirect "/portal" "http://edu.xunta.gal"

### Modifica o directorio desde o que Apache vai servir os arquivos a /home/administrador/web, inclúe nese directorio un arquivo para que poidas comprobar que, efectivamente, son eses os ficheiros servidos.

    DocumentRoot /home/administrador/web