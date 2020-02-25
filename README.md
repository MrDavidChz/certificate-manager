# certificate-manager
Docker Compose Project for Letsencrypt Certificate Manager 

## Requisitos
* Ejecutar el docker-compose desde un equipo con dirección IP Pública que pueda ser accedido desde Internet por los puertos 80 y 443
* Configurar en el DNS de su dominio para que el(los) dominio(s) a certificar apunten a la IP Pública mencionada en el punto anterior.

## Configuración
Edite el archivo `docker-compose.yaml` y reemplace los valores de las variables de entorno con sus respectivos valores:

* `DEFAULT_EMAIL=mail@yourdomain.tld` Configurar la dirección de correo electrónico para que Let's Encrypt pueda advertirle sobre los certificados que caducan y permitirle recuperar su cuenta.

* `VIRTUAL_HOST=subdomain.yourdomain.tld` y `LETSENCRYPT_HOST=subdomain.yourdomain.tld` Configurar en ambas variables el dominio(s) para el(los) que se desea crear o actualizar el certificado.

## Ejecución
En el directorio del proyecto ejecute el siguiente comando:
```
docker-compose up -d
```
Opcionamente puede verificar los log de los contenedores para realizar seguimiento con el comando:
```
docker-compose logs -f nginx-proxy-letsencrypt
```

## Validación y Resultados
* En el proyecto, en el directorio `certificates` encontrara los certificados generados y/o actualizados.
* Extraer los certificados, disponer de ellos y/o realizar las respectivas copias de seguridad de los mismos.
