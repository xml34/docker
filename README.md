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
<span style="color:red">run</span> `docker run`, corre la imagen para "instanciar" el contenedor

<span style="color:red">ps</span> `docker ps -a` list containers
