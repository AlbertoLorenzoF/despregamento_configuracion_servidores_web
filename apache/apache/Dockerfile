FROM debian:buster

MAINTAINER sabela <sabela@iessanclemente.net>

ENV TERM xterm
ENV PASS=abc123.
ENV PATH /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/sbin

LABEL distribucion="Debian 10"
LABEL descripcion="Imagen Debian para prácticas de DAW"
LABEL paquetes="vim, iputils-ping, nano, procps apache2"
LABEL acceso="usuario: root, password: abc123."

#Copiamos el entrypoint.sh al container
COPY entrypoint.sh /usr/bin/entrypoint.sh

#Damos permiso al entrypoint
RUN set -x; \
	chmod +x /usr/bin/entrypoint.sh

#Establecemos la password de root
RUN set -x; \
	echo "root:$PASS" | chpasswd

#Instalamos paquetes de utilidades
RUN set -x; \
	apt update && apt install -y vim iputils-ping nano procps apache2

#Limpiando
RUN set -x; \
	apt clean

#Comando para arrancar ssh y entrar en bucle de espera
ENTRYPOINT ["/usr/bin/entrypoint.sh"]
