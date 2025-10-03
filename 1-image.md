<img width="787" height="23" alt="image" src="https://github.com/user-attachments/assets/d6b21e13-095a-419c-91ca-9d965bcc0389" /># Imagen
### Descargar imagen
Descarga la última versión de la imagen disponible en el registro de Docker.

```
docker pull <nombre imagen> 
```

Descarga una versión específica de la imagen, cada imagen tiene etiquetas (tags) para diferentes versiones.
Una imagen puede tener la etiqueta latest para representar la última versión, si no se especifica una etiqueta se hará referencia a la versión latest.

```
docker pull <nombre imagen>:<tag>
```

Descargar la imagen **hello-world**
# COMPLETAR

salida de comando tras realizar la descarga de la imagen hello-world

```
17eec7bbc9d7: Pull complete
Digest: sha256:54e66cc1dd1fcb1c3c58bd8017914dbed87001e2d8c72d9262e26bd9cc1642d31
Status: Downloaded newer image for hello-world:latest
docker.io/library/hello-world:latest
```


**¿Qué es nginx**
# COMPLETAR 

Es un servidor web HTTP, un proxy inverso, un caché de contenido, un equilibrador de carga, un servidor proxy TCP/UDP y un servidor proxy de correo.

Es conocido por su alto rendimiento, bajo consumo de recursos y arquitectura asíncrona, que le permite manejar muchas conexiones con eficiencia. NGINX se utiliza comúnmente para acelerar la entrega de sitios web, optimizar la carga de aplicaciones y asegurar la estabilidad de servicios con alto tráfico


Descargar la imagen  **nginx** en la versión **alpine**

```
$ docker pull nginx:stable-alpine
```
una ves descargada la imagen de nginx en su version stable alpine

por consola se muestra lo siguiente:

```
Status: Downloaded newer image for nginx:stable-alpine
docker.io/library/nginx:stable-alpine
```


# COMPLETAR

### Listar imágenes

```
docker images
```
Se muestra el siguiente output:

Se litas los siguientes campos Repository, Tag, ImageID, Created y el tamaño de la imagen.
```
REPOSITORY                     TAG             IMAGE ID       CREATED         SIZE
hello-world                    latest          54e66cc1dd1f   8 weeks ago     20.3kB
nginx                          stable-alpine   8f2bcf97c473   5 months ago    73.5MB
```

# COLOCAR UNA CAPTURA DE PANTALLA DEL RESULTADO 

**Identificadores**

En Docker, se utilizan varios identificadores para diferenciar de manera única los elementos del sistema, como imágenes, contenedores, volúmenes y redes. Estos identificadores son generados automáticamente por Docker y son únicos dentro del contexto del sistema Docker en el que se encuentran. 

### Inspeccionar una imagen
El comando docker inspect se utiliza para obtener información detallada sobre un objeto de Docker específico, como un contenedor, una imagen, un volumen o una red.  Proporciona información en formato JSON sobre el objeto especificado.

```
docker inspect <nombre imagen>
docker inspect <nombre imagen>:<tag>
```
<img width="846" height="314" alt="image" src="https://github.com/user-attachments/assets/481e195c-568c-457d-80e0-6df92304e739" />


Inspeccionar la imagen hello-world 
# COMPLETAR

**¿Con qué algoritmo se está generando el ID de la imagen**
Se genera con el algoritmo de sha256 para los identificadores 

```
{
  id: "sha256:...."
}
```


# COMPLETAR

### Filtrar imágenes


```
docker images | grep <termino a buscar>
```
<img width="788" height="53" alt="image" src="https://github.com/user-attachments/assets/523eb89b-113a-4339-ada7-a884b3cddb68" />
<img width="787" height="23" alt="image" src="https://github.com/user-attachments/assets/22d5aaf6-2620-483c-b2a5-6315feee58db" />


### Para eliminar una imagen
Eliminar permanentemente la imagen de tu sistema Docker.

```
docker rmi <nombre imagen>:<tag>
```

<img width="768" height="57" alt="image" src="https://github.com/user-attachments/assets/a10f8bbe-758f-4916-979a-b495d1aa5426" />


Eliminar la imagen hello-world 
# COMPLETAR

-f: Es la opción para forzar la eliminación de la imagen incluso si hay contenedores en ejecución que utilizan esa imagen.
Cuando eliminas una imagen Docker, Docker no elimina automáticamente los contenedores que se han creado a partir de esa imagen. Esto significa que, aunque hayas eliminado la imagen, el contenedor seguirá ejecutándose normalmente.  

**Considerar**
Eliminar una imagen no afecta a los contenedores que se han creado a partir de esa imagen, a menos que esos contenedores dependan de archivos o configuraciones específicas de la imagen eliminada. En ese caso, es posible que los contenedores se comporten de manera inesperada después de eliminar la imagen.
Es una buena práctica detener y eliminar todos los contenedores que dependan de una imagen antes de eliminar la imagen en sí.

```
docker rmi -f <nombre imagen>:<tag>
```

Al elimianr la imagen de hello-world envio como output:

```
Untagged: hello-world:latest
Deleted: sha256:54e66cc1dd1fcb1c3c58bd8017914dbed8701e2d8c74d9262e26bd9cc1642d31
```
