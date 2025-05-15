# Recuperar imagen de un VPS
Vamos a crear un VPS en la plataforma que prefieras, accede al mismo y haz lo siguiente:

Crea un usuario, con el nombre que prefieras.
Establece una contraseña para el mismo.
Accede con el usuario que acabas de crear y haz las siguientes acciones:
 3a. Crea un archivo flag con una palabra o frase en un directorio relativamente escondido, el archivo debe estar visible. ~/pepe/flag
 3b. Crea un archivo .secret con una palabra o frase en un directorio relativamente escondido.
 ~/pepe/secreto/.secret
 3c. Crea un directorio "trabajo" en la carpeta del usuario.
 3d. Crea un directorio "pruebas" en la carpeta del usuario.
 3e. Descarga, al menos, 10 archivos en la carpeta "pruebas", incluye varios formatos, video, imagen, pdf, texto plano...
 3f. Copia los archivos a la carpeta trabajo.
 3g. Elimina al menos 5 archivos de la carpeta trabajo.

Vuelve a root 
Instala, al menos, 10 programas en el VPS y ejecuta algunos.
Crea 2 usuarios mas, invitado y dev.
Da permisos de sudo al usuario dev y borra multiples archivos del sistema, al azar, sin pensar.
Extrae la memoria del VPS usando dd a tu host con el siguiente comando:

>Asegúrate de cambiar el nombre del archivo de salida por otro diferente y unico.

VAMOS POR AQUI

ssh root@167.172.181.44 "sudo dd if=/dev/vda bs=4M | gzip -c" > vpsito_backup.img.gz

Firma la imagen resultante, subela a limewire y comparte el enlace en tu rama del repositorio.
