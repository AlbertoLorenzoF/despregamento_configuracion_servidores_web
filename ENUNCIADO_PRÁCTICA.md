# Práctica directivas Apache

## Configuración básica Apache 

*	Realiza copias de seguridade dos ficheiros de configuración (apache2.conf, ports.conf, sites-available/000-default.conf).
*	No directorio /var/www/html, crea os seguintes arquivos (co contido que prefiras, unicamente debe servir para distinguir uns arquivos de outros) e directorios:
–	index.html
–	indice.html
–	persoal/alumnos.html
–	persoal/profesores.html
*	Abre o navegador da máquina cliente e establece conexións con cada un dos arquivos (http://192.168.0.1/nomeArquivo). Proba tamén a acceder á IP do servidor sen indicar ningún arquivo (http://192.168.0.1/).
*	Fai as modificacións adecuadas para que se sirva por defecto o arquivo indice.html.
*	Fai as modificacións que sexan precisas para que no directorio persoal non se amose o listado de arquivos cando se pide o raíz do mesmo.
*	Modifica a mensaxe de erro para o erro 404.
Crea o directorio /home/administrador/apuntes, que conterá un ficheiro calquera. Crea un alias para que este directorio sexa accesible desde http://192.168.0.1/apuntes. Como aínda non se estudaron as directivas de acceso, non esquezas, polo momento, copiar a configuración para o directorio /var/www no arquivo apache2.conf para este novo directorio.
*	Crea unha redirección, de xeito que cando se faga unha petición a http://192.168.0.1/portal, se redirixa á páxina http://edu.xunta.gal 
*	Modifica o porto no que escoitará o servidor Apache a 8080
*	Modifica o directorio desde o que Apache vai servir os arquivos a /home/administrador/web, inclúe nese directorio un arquivo para que poidas comprobar que, efectivamente, son eses os ficheiros servidos.
*	Non esquezas restaurar os ficheiros ao seu estado orixinal (sobre todo no que respecta ao directorio no que se atopan os arquivos que vai servir Apache e ao porto de escoita).

