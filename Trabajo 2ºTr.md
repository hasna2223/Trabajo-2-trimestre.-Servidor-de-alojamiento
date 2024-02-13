                              **Práctica 2º trimestre**


Se pide las instalación, configuración y puesta en marcha de un servidor que ofrezca servicio de 
alojamiento web configurable:
• Se dará alojamiento a páginas web tanto estáticas como dinámicas con “php”
• Los clientes dispondrán de un directorio de usuario con una página web por defecto. 
• Además contarán con una base de datos sql que podrán administrar con phpmyadmin
• Los clientes podrán acceder mediante ftp para la administración de archivos configurando 
adecuadamente TLS
• Se habilitará el acceso mediante ssh y sftp. 
• Se configura de forma adecuada postfix y dovecot imap y pop3
• Se automatizará mediante el uso de scripts: 
• La creación de usuarios y del directorio correspondiente para el alojamiento web
• Host virtual en apache
• Creación de usuario del sistema para acceso a ftp, ssh, smtp, …
• Se creará un subdominio en el servidor DNS con las resolución directa e inversa
• Se creará una base de datos además de un usuario con todos los permisos sobre 
dicha base de datos (ALL PRIVILEGES)
• Se habilitará la ejecución de aplicaciones Python con el servidor web

Crear un subdominio en el servidor DNS con las resolución directa e inversa
Para ello, update apt-get, instalar y configurar bind9:

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/712aca5c-bc74-491d-a34b-fc72fd3bbe04)

Instalacion de bind:

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/8bd5aca2-e23d-4cae-b2d5-50a9fa704540)
![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/36eb4152-7d89-4afa-b18e-d1f90e5d6f55)

Abrimos el archivo /etc/bind/named.conf.options para editarlo de la manera siguiente:

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/08dd6fab-c509-491b-91e5-08c56396a8eb)

Ahor abrimos el archivo /etc/bind/named.conf.local para editarlo de la manera siguiente:

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/37986bf2-b69b-4c9b-9ed2-5101ce5e5a7b)

guardar y cerrar.

Crear un derectorio zone y dentro de este directorio crea dos ficheros uno para la zona dericta y otro para zona inversa.

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/7631f989-8d3e-4a39-92bb-0123bb0eaac5)

Fichero de zona inversa:

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/20919897-0307-4b3c-a174-6e13eb277267)

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/bc06fca9-ab6e-44a6-a9f1-2dd0375a0c15)


