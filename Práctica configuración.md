# Práctica directivas Apache

## Configuración básica Apache 

1.	Realiza copias de seguridade dos ficheiros de configuración (apache2.conf, ports.conf, sites-available/000-default.conf).
2.	No directorio /var/www/html, crea os seguintes arquivos (co contido que prefiras, unicamente debe servir para distinguir uns arquivos de outros) e directorios:
–	index.php
–	persoal/alumnos/alumnos.html
–	persoal/profesores.html
Abre o navegador da máquina cliente e establece conexións con cada un dos arquivos (http://192.168.0.1/nomeArquivo). 
3.	Fai as modificacións adecuadas para que se sirva por defecto o arquivo indice.php e se non o encontra o fichero profesores.html 
4.	Fai as modificacións que sexan precisas para que no directorio persoal se amosen os enlaces simbólicos. 
5.	Crea unha páxina de error, no directorio persoal/erros/erro404.html.  Modifica a mensaxe de erro para o erro 404 de maneira que se amose dita páxina.  
6.	Crea o directorio /home/tunome/apuntes, (por exemplo /home/sabela/apuntes) que conterá un ficheiro calquera. Crea un alias para que este directorio sexa accesible desde http://ip/apuntes. 
7.	Crea unha redirección, de xeito que cando se faga unha petición a http://ip/sanclemente, se redirixa á páxina https://www.iessanclemente.net/
8.	Non esquezas restaurar os ficheiros ao seu estado orixinal (sobre todo no que respecta ao directorio no que se atopan os arquivos que vai servir Apache e ao porto de escoita). 
