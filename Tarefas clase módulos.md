# Práctica directivas Apache

## Habilitación/deshabilitación Módulos 

### Lista os módulos estáticos do servidor Apache.
	sudo apache2ctl –l 
### Lista os módulos cargados dinamicamente.
	ls /etc/apache2/mods-enabled/
### Consulta os módulos dinámicos dispoñibles instalados.
	ls /usr/lib/apache2/modules/
### Consulta os módulos dinámicos dispoñibles non instalados.
	sudo apt-cache search libapache2-moda2
### Habilita o módulo userdir.
	sudo a2enmod userdir
### Amosa o contido do arquivo de configuración do módulo e interpreta as directivas propias deste módulo.
	more /etc/apache2/mods-enabled/userdir.conf
### Crea algún ficheiro no directorio correspondente para o teu usuario e comproba que se pode acceder desde a máquina cliente.
	http://ip/~usuario
### Deshabilita o módulo userdir.
	sudo a2dismod userdir