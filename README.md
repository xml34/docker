# Docker
Docker es un proyecto de código abierto que automatiza el despliegue de aplicaciones dentro de contenedores de software, proporcionando una capa adicional de abstracción y automatización de virtualización de aplicaciones en múltiples sistemas operativos. `hola`
## Docker engine 
<img src="./images/DockerEngine.png" style="height: 270px; width:400px;"/>

#### Docker deamon
This is the heart of docker, this part manages of the entities and basicaly allow us to user the containers we gonna use, create, delete etc

#### Rest API
we can communicate from our machine with the docker deamon throuth the default docker API with HTTP

#### Docker CLi 
it is the client with user to use, create, delete etc images containers etc
it uses the docker Rest API to communicate with the docker deamon

#### Containers
Que es un contenedor ?

* Es una agrupación de procesos.

* Es una entidad lógica, no tiene el limite estricto de las máquinas virtuales, emulación del sistema operativo simulado por otra más abajo.

* Ejecuta sus procesos de forma nativa.

* Los procesos que se ejecutan adentro de los contenedores ven su universo como el contenedor lo define, no pueden ver mas allá del contenedor, a pesar de estar corriendo en una maquina más grande.

* No tienen forma de consumir más recursos que los que se les permite. Si esta restringido en memoria ram por ejemplo, es la única que pueden usar.

* A fines prácticos los podemos imaginar cómo maquinas virtuales, pero NO lo son. Máquinas virtuales livianas.

* Docker corre de forma nativa solo en Linux.

* Sector del disco: Cuando un contenedor es ejecutado, el daemon de docker le dice, a partir de acá para arriba este disco es tuyo, pero no puedes subir mas arriba.

* Docker hace que los procesos adentro de un contenedor este aislados del resto del sistema, no le permite ver más allá.

* Cada contenedor tiene un ID único, también tiene un nombre.
#### Images
actifacts that docker uses to crated the containers
#### Data Volumes
... no data yet
#### Network 
... no data yet

---
## Architecture
<img src="./images/architecture.png" style="height: 270px; width:400px;"/>

---
## FU Commands


<details close>
<summary><span style="color:red">run</span></summary>

`docker run <image-name> <command|>`, corre la imagen para "instanciar" el contenedor

    --name <alias-name> # asing our alias name
    -it
    --detach | -d  # run in background of the terminal, other ways blocs the term when continuos daemon
        <command|>  # expl: sudo docker run -d ubuntu tail -f /dev/null
    -p <port maq>:<port contdr> # to specify the port ur gonna export and wich port (-p 8080:80)
        # docker run --name proxy -d -p 8080:80 nginx then -> localhost:8080
    -v <machine_path:cont_path>  
        # 4 syncronizing and bind folders, ejem: sudo docker run -d --name db -v /home/dev-daniel/mongodata:/data/db mongo
    --mount src=<volumen>,dst=<folder-path>  
        # exam: sudo docker run -d --name db --mount src=dbdata,dst=/data/db mongo
</details>


<details close>
<summary><span style="color:red">rename</span></summary> 

`docker rename <old-name> <new-name>`, rename an existing container's alias name
</details>


<details close>
<summary><span style="color:red">ps</span></summary> 

`docker ps` list all runing containers

    -a # for all, shutted down included
</details>


<details close>
<summary><span style="color:red">inspect</span></summary> 

`docker inspect <id/alias>`, all description and container configuration

    --format '<filtering-query>'  # inspect --format '{{.State.Pid}}' 
</details>


<details close>
<summary><span style="color:red">rm</span></summary> 

`docker rm <id/alias>`, delete a container
</details>


<details close>
<summary><span style="color:red">prune</span></summary> 

`docker container prune <id/alias>`, delete all stoped containers
</details>


<details close>
<summary><span style="color:red">exec</span></summary> 

`docker exec <id/alias> <command-to-exec>`, ejecutar un comando dentro de a running container

    -it  # modo interactivo (sudo docker exec -it always_up bash)

</details>


<details close>
<summary><span style="color:red">logs</span></summary> 

`docker logs <id/alias>`, in order to see the container logs

    -f  # ver constantemente ejem: docker logs -f proxy
    --tail <#>: to see las # of logs ejem: docker logs --tail 10 -f proxy

</details>


<details close>
<summary><span style="color:red">stop</span></summary> 

`docker stop <id/alias>`, stops the running container

</details>


<details close>
<summary><span style="color:red">volume</span></summary> 

`docker volume <action>`, stops the running container

    * create <name>, create a volume
    * ls, list volumes

</details>