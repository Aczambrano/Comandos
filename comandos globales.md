# Comandos Linux

- `echo "hello there..." > test.txt`: Crear un archivo.
- `nano nombreArchivo`: Abrir editor de archivo.
- `cat nombreArchivo`: Ver contenido de archivo.
- `tar -xvf nombreZip -C rutaDirectorio`: Descomprimir un archivo en un directorio.
- `rm -r nombreCarpeta`: Eliminar carpeta.
- `mkdir nombreCarpeta`: Crear carpeta.
- `ls -l`: Listar con todos los permisos del archivo.
- `cd nombre_directorio`: Cambiar de directorio.
- `pwd`: Mostrar el directorio actual.
- `cp archivo_origen archivo_destino`: Copiar archivos y directorios.
- `mv archivo_origen archivo_destino`: Mover o renombrar archivos y directorios.
- `grep "texto_a_buscar" archivo`: Buscar texto dentro de archivos.
- `chmod permisos archivo_o_directorio`: Cambiar permisos de archivos y directorios.
- `chown usuario:grupo archivo_o_directorio`: Cambiar propietario y grupo de archivos y directorios.
- `sudo apt update`: Actualizar lista de paquetes.
- `sudo apt upgrade`: Actualizar los paquetes instalados a la última versión.
- `sudo apt install nombre_paquete`: Instalar paquete.
- `sudo apt remove nombre_paquete`: Eliminar paquete.
- `ps aux`: Mostrar todos los procesos en el sistema.
- `top`: Mostrar los procesos en ejecución y sus recursos utilizados en tiempo real.


# Comandos Windows

- `dir`: Ver los archivos de la ruta.
- `cd`: Moverse.
- `echo %cd%`: Ver la ruta donde estás.
- `mkdir`: Creación de carpetas.
- `echo`: Crear un archivo con algún contenido.
- `type nul>nombrearchivo.extension`: Crear archivo vacío.
- `cls`: Limpiar consola.

# Comandos Git

- `ls`: Ver archivos.
- `touch`: Crear archivos.
- `.gitignore`: Para poner archivos que no los tome en cuenta Git y no los suba.
- `git config --global user.name "aczambrano3"`: Configurar usuario.
- `git config --global user.email "zambranoanderson84@yahoo.es"`: Configurar correo.
- `git branch -m main`: Cambiar el nombre de la rama master por main.
- `git diff`: Compara ficheros o ramas.
- `git status`: Ver el estado del proyecto.
- `git checkout nombrearchivo`: Para volver al último commit hecho por el archivo.
- `git checkout codigohash`: Para volver a ese commit, pero todo debe estar guardado antes de hacer esto.
- `git log --graph`: Ver historial de cambios que se habían hecho hasta el commit en el que estás.
- `git log --graph --decorate --all`: Ver todos los commits sin importar donde estés.
- `git log --graph --decorate --all --oneline`: Todo en una línea.
- `git config --global alias.nombrealias "instrucción de código commit"`: Esto sirve para en vez de escribir códigos enteros puedas nombrarlos para no escribir todo.
- `**/nombrearchivo.extension`: Para ignorar un archivo en el gitignore.
- `git reset --hard codigohash`: Regresar a un commit determinado y borrar los que le seguían.
- `git reflog`: Historial de todos los cambios realizados.
- `git tag nombre_tag`: Seccionar commits.
- `git tag nombre_tag -m "comentario"`: Hacer un tag con un comentario.
- `git push --tags`: Subir tags a GitHub.
- `git checkout tags/nombre_tag`: Para mover el head a ese tag.
- `git branch nombre_rama`: Crear una rama.
- `git switch nombre_rama`: Cambiar a una rama.
- `git stash`: Hacer un semi commit mientras cambias de rama sin necesidad de hacer un commit innecesario.
- `git stash list`: Listar los stash.
- `git stash pop`: Volver a tener lo que tenías antes de hacer el stash.
- `git stash drop`: Elimina el stash y vuelves al último commit.
- `git branch -d nombre_rama`: Eliminar una rama.
- `git fetch`: Descargar historial de cambios del repositorio online.
- `git pull`: Descargar repositorio de repositorio online.
- `git commit -am "comentario"`: Sirve para hacer un git add . y el commit a la vez en un solo comando.


# Comandos Symfony

### Creación y manipulación de entidades

- `php app/console doctrine:generate:entity`: Genera una entidad mediante un wizard.
- `php app/console doctrine:schema:update --force`: Crea las tablas en base a partir de las entidades en PHP.
- `php app/console doctrine:mapping:import AppBundle annotation`: Ingeniería reversa, crea las entidades a partir de tablas creadas.
- `php app/console doctrine:generate:entities AppBundle`: Crea los getters y setters de las entidades creadas.
- `php app/console doctrine:generate:entities AppBundle:User`: Crea los getters y setters de la entidad específica.



# Comandos Docker

- `docker run`: Iniciar Docker.
- `docker stop <ID_del_contenedor>`: Parar Docker.
- `docker rm <ID_del_contenedor>`: Eliminar contenedores detenidos.
- `docker container prune`: Eliminar todos los contenedores detenidos.
- `docker ps`: Containers corriendo.
- `docker ps -a`: Containers en cualquier estado.
- `docker ps -a -q`: Los IDs de los containers.
- `docker ps -l`: Lista.
- `docker ps -a --no-trunc`: Información completa de los containers.
- `docker container run -it centos:7 bash`: `-it` es para ingresar a un contenedor.
- `docker container exec -it d96c246cd8f1 bash`: Ejecutar un comando en un contenedor.
- `docker ps -a --filter "exited=0"`: Muestra los contenedores que se levantaron y cerraron de manera natural.
- `docker ps -a --filter "exited=1"`: Muestra los contenedores que se levantaron y cerraron de manera inesperada o con algún error.
- `docker container logs 497928b543b8`: Ver logs.
- `docker rm nombre_contenedor`: Este subcomando se utiliza para eliminar un contenedor.
- `docker container diff idDocker`: Muestra los cambios que hemos hecho sobre una imagen base.

### Creación de Dockerfile en un SO 

- `sudo nano Dockerfile`  : en cualquier directorio se crea

``` dockerfile
FROM centos:7  

RUN yum update -y  
RUN yum install -y wget 
RUN yum install -y vim 
  ```

- `docker image build -t myimage .`  : Construye la imagen

- `docker image history myimage ` : historial de una imagen

### Subir un docker a Docker Hub
``` 
1. docker image tag centos:7 imagenDocker:dev: aquí haces un tag

2. docker image tag imagenDocker:dev usuarioDocker/imagenDocker:dev 

3. docker login

4. docker image push usuarioDocker/imagenDocker:dev
  ```

### Volumenes Docker

- `docker volume create --name nombreVolumen`: Crear un volumen.
- `docker container run -it -v nombreVolumen:/www/website nombreImagen bash`: ejecutar un docker poniendo el volumen.
- ` cd www/website/`: 
- `echo "hola test" > test.txt`: Crear un archivo
- `ctrl +p+q`: Cerrar docker

- `docker container commit 568b76548a33 test:1.0`: Crear un commit.
- `docker volume create --name nombreVolumen`: Crear un volumen.
- `docker volume inspect nombreVolumen`: inspeccionar volumen
- `sudo su cd /var/lib/docker/volumes/test1/_data/ `: ver contenido del volumen
- ` docker volume rm test1` : eliminar volumen
- `docker container run --name NOMBREIMAGEN -e POSTGRES_PASSWORD=mysecretpassword -v NOMBREVOLUMEN:/var/lib/postgresql/data -d postgres:9-alpine `: Corre el contenedor hecho en postgres
- ` docker container run -it --rm --link NOMBREIMAGEN:postgres postgres:9-alpine psql -h postgres -U postgres`: 
### Network Docker

- ` docker network create --driver bridge NOMBRERED` : crear una red en docker
- ` docker container run --name=NOMBRECONTAINER --network=NOMBRERED -dt centos:7` : asignar una red a un contenedor
- ` docker container run -d -P my_nginx`: crea un docker y le asigna el puerto automaticamente por el -P (primero se crea un dockerfile FROM nginx EXPOSE 80)

