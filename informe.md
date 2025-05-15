# Informe de extraccion
cyber1@Mercedarias
## Información General

- Fecha y hora de la extracción 14/05/25 
- Responsable de la extracción alvaro
- Motivo de la extracción extraccion recuperacion wasap fiscal general

## Descripción del VPS

- IP pública 167.172.181.44
- IP privada 10.114.0.2
- Sistema Operativo y version Ubuntu 24.10 x64
- Recursos asignados 512 MB Memory / 10 GB Disk 
- Aplicaciones o servicios en ejecucion 


## Metodología

- Herramientas utilizadas
dd y gzip
- Comandos y parametros usados
ssh root@167.172.170.34 "sudo dd if=/dev/vda bs=4M | gzip -c" > vps_backup_alvaro.img.gz

## Integridad de la imagen

- Hash de la extracción: openssl dgst -sha256 vpsito_backup.img

SHA2-256(vpsito_backup.img)= 62e1a4d69b43e4c40bb3833104373422e86ddbd12da83b4d08a938826dabf9a6


## Firma de la imagen

- Algoritmo de hash usado SHA-256 
- Metodo de firma digital RSA con hash SHA-256
- Clave publica del firmante publica.pem




- Comandos usados para la firma

Generar clave privada RSA:
openssl genpkey -algorithm RSA -out privada.pem -pkeyopt rsa_keygen_bits:4096

Obtener clave pública:
openssl rsa -pubout -in privada.pem -out publica.pem


Firmar archivo de imagen:
openssl dgst -sha256 -sign privada.pem -out firma.bin vpsito_backup.img
Verificar la firma:

openssl dgst -sha256 -verify publica.pem -signature firma.bin vpsito_backup.img

(Opcional) Ver contenido de la firma:
openssl asn1parse -inform DER -in firma.bin

![alt text](image.png)

LA OTRA PERSONA PARA COMPROBARLO QUE NO ESTA CAMBIADO NI ALTERADO NECESITARIA:

vpsito_backup.img → el archivo original firmado.

firma.bin → el archivo de la firma digital.

publica.pem → la clave pública del firmante.

EJECUTARIA ESTE COMANDO:

openssl dgst -sha256 -verify publica.pem -signature firma.bin vpsito_backup.img



Y LE SALDRIA:

Verified OK


Y SI SE HA MODIFICADO SERIA

Verification Failure
