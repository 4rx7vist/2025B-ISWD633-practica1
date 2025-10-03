# Contenedores

### Crear un contenedor
Para crear un nuevo contenedor Docker a partir de una imagen específica, pero sin iniciarlo automáticamente. 

```
docker create --name <nombre contenedor> <nombre imagen>:<tag>
```
Crear el contenedor  **srv-web** usando la imagen nginx version alpine

para mi ejemplo he creado 

```
$ docker create --name srv-web nginx:stable-alpine
```
y para verificarlo para ver si se ha creado, lo hacemos con:

```
$ docker inspect nginx-altern
```

# COMPLETAR

Si creas un contenedor en Docker sin asignarle un nombre específico utilizando la opción --name, Docker asignará automáticamente un nombre aleatorio al contenedor. Este nombre suele consistir en una combinación de palabras y números.  

Crear el contenedor usando la imagen hello-world

```
$ docker create hello-world:stable
```
y asigna un nombre aleatorio para el contenedor

# COMPLETAR

### Listar los contenedores ejecutándose o no

```
docker ps -a
```

en el output sale:
```
CONTAINER ID   IMAGE                   COMMAND                  CREATED          STATUS                      PORTS     NAMES
880a03c3fc48   hello-world             "/hello"                 3 seconds ago    Created                               sweet_ellis
fe191f94b3fe   hello-world             "/hello"                 11 minutes ago   Exited (0) 11 minutes ago             amazing_diffie
0da04e707cec   hello-world             "/hello"                 12 minutes ago   Exited (0) 12 minutes ago             dazzling_elbakyan
```

### Para iniciar un contenedor

```
docker start <nombre contenedor o identificador>
```

Iniciar el contenedor srv-web 

```
$ docker start srv-web
```

# COMPLETAR

### Listar los contenedores ejecutándose
```
docker ps 
docker ps | grep <nombre contenedor>
```

### Para detener un contenedor

```
docker stop <nombre contenedor>
```
Obtiene el hash del incio del contenedor

### Para crear un contenedor y ejecutarlo inmediatamente

```
docker run --name <nombre contenedor> <nombre imagen>:<tag>
```
![Ecosistema de Docker](dockerRun.PNG)

Crear y ejecutar inmediatamente el contenedor **srv-web2** usando la imagen nginx:alpine

# COMPLETAR

**¿Qué sucede luego de la ejecución del comando?**

Se queda bloqueado porque ya esta en funcionamiento 

```
docker: Error response from daemon: Conflict. The container name "/srv-web3" is already in use by container
```
# COMPLETAR  

Cuando ejecutas un contenedor en primer plano sin la opción -d (modo detach), el contenedor captura la entrada estándar (stdin) del terminal, lo que significa que el terminal queda "atrapado" y no puedes introducir más comandos hasta que detengas el contenedor.

### Para crear un contenedor y ejecutarlo inmediatamente sin estar vinculados al mismo
-d: Es la opción que indica a Docker que ejecute el contenedor en segundo plano (en modo "detach").
Cuando un contenedor se ejecuta en segundo plano, Docker devuelve el control al terminal inmediatamente después de iniciar el contenedor, lo que permite al usuario seguir ejecutando otros comandos en el mismo terminal sin que el contenedor detenga la interacción.

```
docker run -d --name <nombre contenedor> <nombre imagen>:tag
```
Crear y ejecutar inmediatamente el contenedor **srv-web3** en modo detach usando la imagen nginx:alpine

<img width="1069" height="45" alt="image" src="https://github.com/user-attachments/assets/62660010-785e-4695-b917-13a6dde7af81" />

# COMPLETAR

### Para eliminar un contenedor

```
docker rm <nombre contenedor>
```

Eliminar el contenedor que se creó a partir de la imagen hello-world 
<img width="396" height="37" alt="image" src="https://github.com/user-attachments/assets/d84a0b4e-165d-4709-8786-b91b1a2078f4" />


# COMPLETAR

Verificar que el contenedor que se eliminó
# COMPLETAR

### Para eliminar un contenedor que esté ejecutándose

```
docker rm -f <nombre contenedor>
```

Eliminar el contenedor **srv-web3** 

```
$ docker rm -f srv-web3
```
se detuvo y se elimino al instante

# COMPLETAR

Verificar que el contenedor que se eliminó

> Si se elimino del registro

<img width="1215" height="56" alt="image" src="https://github.com/user-attachments/assets/7ef20944-99df-4610-9a06-f67eb1797bb2" />

# COMPLETAR

### Para inspecionar un contenedor 

Inspeccionar el contenedor **srv-web** 

>
```
 docker inspect srv-web
[]
Error: No such object: srv-web
```

# COMPLETAR
