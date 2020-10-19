# Práctica directivas Apache

## Configuración básica Apache 

1. Realiza copias de seguridade dos ficheiros de configuración (apache2.conf, ports.conf, sites-available/000-default.conf).

2. No directorio /var/www/html, crea os seguintes arquivos (co contido que prefiras, unicamente debe servir para distinguir uns arquivos de outros) e directorios:
- index.html
- indice.html
- index.php 
- persoal/alumnos.html
- persoal/profesores.html

Abre o navegador da máquina cliente e establece conexións con cada un dos arquivos (http://192.168.0.1/nomeArquivo). 

3. Fai as modificacións adecuadas para que se sirva por defecto o arquivo indice.php 
4. Fai as modificacións que sexan precisas para que no directorio persoal se amose as ligazóns simbólicas deste directorio. 
5. Modifica a mensaxe de erro para o erro 404 para que mostre unha páxina html de erro. Crea unha carpeta /erros/erro404.html
6. Crea o directorio /home/tunome/paxinas (por exemplo /home/sabela/paxinas), que conterá un ficheiro calquera. Crea un alias para que este directorio sexa accesible desde http://ip/paxinas. 
7. Crea unha redirección, de xeito que cando se faga unha petición a http://192.168.0.1/correo, se redirixa á páxina https://www.edu.xunta.es/webmail/login.php. Na casa pode que non vos cargue a páxina por estar en modo puente. 
8. Modifica o directorio desde o que Apache vai servir os arquivos a /home/tunome (por exemplo /home/sabela), inclúe nese directorio un arquivo para que poidas comprobar que, efectivamente, son eses os ficheiros servidos.


 