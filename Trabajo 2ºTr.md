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

Crear un host virtual en Apache:
Para ello siguimos los siguientes pasos, ( tal como en el trabajo del 1º Trimestre):

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/3160d8a9-b4ab-46ee-8b0b-8068e33ecd14)
![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/2d500c45-1729-4aa4-83cc-ebbc79981c85)

sudo apt install apache2: 

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/8b0aee6b-01f1-4d1f-b694-a3942dc60ddb)

Verificar el estado de Apache 

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/261c60f2-ba08-4555-9b6c-a17726d3893b)

Habilitar el servicio para que inicie con el sistema

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/1db9dff3-f0e8-4828-9daf-62e738a401df)

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/f536713b-fa6d-4b28-a0e9-d9266c9ef0aa)

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/5f9bced5-edab-46d6-be8b-4798ec174c21)


creamos un directori donde guardamos el script : 

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/46de8647-192e-4041-8220-ed291a5fca5e)

nano script:

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/44f0eb2d-f393-4bdf-886f-30e89d247517)

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/af99f597-78be-4b3e-886f-509d835d8b6d)

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/2409c6d4-4ae4-4bfb-8b9e-d949f4ed1c8c)

crear host:

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/2a6d1c7e-fcdf-4586-9fae-80aa9685e124)

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/7412af3c-78b3-4e80-933c-6203e9ae76cc)

Para activar la nueva configuracion, ejecutamos : systemctl reload apache2

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/e73f13b8-7dcd-4dc3-833f-0d934414e753)


3. administrar con phpmyadmin
   
Para administrar una base de datos con phpmyadmin hay que seguir estos pasos:
a. Instalar PHP

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/f149a68f-c47a-46f1-ad24-12d3467b57db)

b. Instalar phpMyAdmin:

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/3a16988f-2f12-424f-b302-2e3135af7720)

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/27d764d0-47ad-44e8-aa25-55c3d3d32c6b)

Configurar Apache2: 
Para habilitar el acceso a phpMyAdmin desde el servidor web, debemos agregar una línea al archivo de configuración de Apache.

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/9cfea915-bd4c-49e2-8bfd-94d7a8e11401)
