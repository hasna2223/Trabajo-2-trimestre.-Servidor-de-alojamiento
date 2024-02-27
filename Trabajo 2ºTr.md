                              **Práctica 2º trimestre**


Se pide las instalación, configuración y puesta en marcha de un servidor que ofrezca servicio de alojamiento web configurable:

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

• Se creará una base de datos además de un usuario con todos los permisos sobre dicha base de datos (ALL PRIVILEGES)

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

En el navigador ejecutamos el nombre del dominio/phpmyadmin:

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/e8e8db1c-29d6-4323-bf0d-2f74d00aa630)

4. creará una base de datos además de un usuario con todos los permisos sobre dicha base de datos (ALL PRIVILEGES)

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/db21e1d2-5b6c-4ce8-bd08-97c4917a7533)

5. Creación de usuario del sistema para acceso a ssh:
Primero instalaremos ssh y configurarlo:

Instalamos el servidor OpenSSH en el sistema:

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/f747b7db-3788-41b4-a9be-fabb368e92bc)

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/e7a5e033-f9b6-40ce-b7af-0424f53117fd)

Si está inactivo, podemos iniciarlo con el siguiente comando:

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/cc3b80a4-3183-4893-be57-79fb3d84c843)


Configuramos el servidor ssh para permitir la autenticación basada en contraseñas y la autenticación basada en claves públicas: 

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/6e6a3753-68b8-48c1-a937-c8cd520c9755)

Reiniciamos el servicio ssh para que los cambios surtan efectos:

sudo systemctl restartt ssh:

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/07866974-34f5-412a-bfb7-7ae1ef108c7f)

Ahora ejecutamos el shell script para crear usuario del sistema:
contraseña nueva: usuario

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/bd221f6e-5143-454b-9b75-ef442a05a12b)

Los clientes podrán acceder mediante ftp para la administración de archivos configurando 
adecuadamente TLS. Para ello seguimos los pasos siguientes:

Instalamos el servidor FTP y el módulo de autenticación TLS/SSL

sudo apt update:

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/44a091d1-d835-4713-9d4e-556bf9c0f6ee)

sudo apt install vsftpd libpam-pwdfille openssl:

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/3e451769-e388-4922-9047-04c76409b827)

Ahora, Crearemos un usuario de FTP y establecer su contraseña:

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/5044b55e-1987-4e66-96bf-7c5d7a9e6341)

Configuramos el servidor FTP para utilizar TLS. abrimos el editor de texto: /etc/vsftpd.conf

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/2602bab6-6c6c-4b6b-b65b-7526f27b39c9)

agregamos las lineas (En la captura siguiente) 

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/a1f75ffe-0d62-4514-9f36-7c0009e4040e)

Creamos una copia del archivo: /etc/vsftpd.chroot_list

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/b09bf463-a937-41a4-a022-a5749a63cfa3)

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/fec96340-50a2-429f-ba66-ef150254c040)

Creamos una copia del archivo con el siguiente comando:
/etc/vsftpd.chroot_list conpd.chroot_list.backup 

Agregar el nombre de usuario al archivo :/etc/vsftpd.chroot_list:

sudo echo "ftpuser" | sudo tee -a /etc/vsftpd.chroot_list

y al final reiniciamos el servidor FTP:

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/ae730ace-f0ad-4baa-904c-ce688a33987f)

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/2a062da1-ef8d-4bce-ac4b-e58bc32e7870)


sudo apt-get update :

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/87064235-e0df-4d3a-9e96-f7d55aaff0a1)

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/dd7ea1ca-7b13-4b7a-9817-16effb634666)

despues de instalar Filezilla, ejecutamos filezilla y nos sale en la pantalla como en la siguiente captura de pantalla:

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/5c9892db-6a93-4b3a-8f34-73ddb899cdc0)

Y para la configurar la conexion FTPES, siguimos loss siguientes pasos: 
En Filezilla:
  1- Hacemos clic en 'Archivo' en la barra del menu y seleccionamos 'Administrar sitios':

  ![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/e6500573-d7e8-4a6f-8609-87757cd4209c)


  2- Haceemos clic en el botton 'Nuevo sitio' y asignamos un nombre a el sitio:
  
![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/f9754e4a-56d6-4865-8f16-ca63315fb5f2)

  3- En el panel de derecho configuramos los siguienttes:
  
-En "Protocolo", selecciona "FTP - Protocolo de Transferencia de Archivos".

-En "Cifrado", selecciona "Usar FTP sobre TLS si está disponible (FTPES)".

-En "Host", introduce la dirección IP o nombre de dominio del servidor FTP.

-En "Puerto", introduce el número del puerto FTP (generalmente 21).

-En "Nombre de usuario", introduce el nombre de usuario FTP que creaste.

-En "Contraseña", introduce la contraseña del usuario FTP.

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/e363b49d-617e-40ac-a15a-8b27ec0a9457)

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/2e9a14d7-3b8e-491d-b819-20961c8515c2)

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/625a252d-1b51-49d5-abe6-fc0dc2969f00)

y como resultado ya lo tenemos hecho, Filezilla bien configurado como se ve en la siguiente captura de pantalla: 

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/8c19bdf2-4f4a-49c9-a793-5d5165e8464e)

2 parte:

Adicionalmente se podrá incluir:

Creación mediante mediante Docker de un contenedor DNS y al menos un contenedor que actuará como servidor (web, mysql, ssh,...) Se configurará la red, volúmenes y scripts necesarios para ponerlos en marcha. Este apartado se valorará con hasta el 20% de la nota de la práctica.

Primer paso: Instalacion de Docker:

sudo apt update:

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/b00c7b79-49aa-4b51-94ea-cd177ab5dd16)

sudo apt install docker.io:

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/23f38569-9dfd-4a80-8f57-fd967019a5b2)

sudo systemctl start docker
sudo systemctl enable docker

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/e4668ef9-f209-48fc-887f-136157c294e8)

Para verificar que Docker se ha instalado correctamente, ejecutamos el siguiente comando:

![image](https://github.com/hasna2223/Trabajo-2-trimestre.-Servidor-de-alojamiento/assets/119622209/760f8df4-9a93-4814-b578-58d4559febdf)

