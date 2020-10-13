FROM debian:buster

MAINTAINER javierfp <javierfp@iessanclemente.net>

ENV TERM xterm
ENV PASS=abc123.
ENV PATH /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/sbin

LABEL distribucion="Debian 10"
LABEL descripcion="Imagen Debian para prácticas de DAW"
LABEL paquetes="vim, iputils-ping, nano, procps apache2 mariadb-server mariadb-client php libapache2-mod-php php-gd php-mysql php-curl php-mbstring php-xml php-xmlrpc php-soap php-intl php-zip"
LABEL acceso="usuario: root, password: abc123."

#Copiamos la página de info de php a la raíz del servidor web
COPY index.php /var/www/html/index.php

#Copiamos el entrypoint.sh al container
COPY entrypoint.sh /usr/bin/entrypoint.sh

#Damos permiso al entrypoint
RUN set -x; \
	chmod +x /usr/bin/entrypoint.sh

#Establecemos la password de root
RUN set -x; \
	echo "root:$PASS" | chpasswd

#Instalamos paquetes necesarios
RUN set -x; \
	apt update && apt install -y vim iputils-ping nano procps \
	apache2 mariadb-server mariadb-client php libapache2-mod-php php-gd php-mysql php-curl php-mbstring php-xml php-xmlrpc php-soap php-intl php-zip

#Limpiando
RUN set -x; \
	apt clean

#Comando para arrancar ssh y entrar en bucle de espera
ENTRYPOINT ["/usr/bin/entrypoint.sh"]
