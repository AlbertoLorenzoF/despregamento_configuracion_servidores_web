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
