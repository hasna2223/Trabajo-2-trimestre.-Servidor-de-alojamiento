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

