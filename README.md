# AREP-MODULARIZACION-VIRTUALIZACION


# Descripción
En el **Taller de Modularización con Virtualización e Introducción a Docker y a AWS** se realizó primero el aprendizaje del manejo de contenedores en Docker, el cual se desplegó la primera instancia en Docker. Después, se realizó el respectivo aprendizaje de AWS para poder con el contenedor creado en Docker, desplegarlo en AWS en la máquina virtual, para así tener base para poder iniciar la tarea la cual consiste en una implementación de una arquitectura la cual consiste en un balanceador de carga en donde se usa el método de RoundRobin. Este balanceador de carga se encarga de realizar las respectivas peticiones a los LogService, los cuales se encargan de realizar la conexión con las bases de datos montada en MongoDB, que almacena todos los mensajes entrantes. En la arquitectura del programa se encuentran en total cinco contenedores, uno para el RoundRobin, tres para el LogService y uno para las bases de datos en Mongo.

## Prerrequisitos
Para la realización y ejecución tanto del programa como de las pruebas de este, se requieren ser instalados los siguientes programas:
* [Maven](https://maven.apache.org/). Herramienta que se encarga de estandarizar la estructura física de los proyectos de software, maneja dependencias (librerías) automáticamente desde repositorios y administra el flujo de vida de construcción de un software.
* [GIT](https://git-scm.com/). Sistema de control de versiones que almacena cambios sobre un archivo o un conjunto de archivos, permite recuperar versiones previas de esos archivos y permite otras cosas como el manejo de ramas (branches).
* [Docker](https://www.docker.com/). Programa encargado de crear contenedores ligeros y portables para las aplicaciones software que puedan ejecutarse en cualquier máquina con Docker instalado, independientemente del sistema operativo que la máquina tenga por debajo, facilitando así también los despliegues.

Para asegurar que el usuario cumple con todos los prerrequisitos para poder ejecutar el programa, es necesario disponer de un Shell o Símbolo del Sistema para ejecutar los siguientes comandos para comprobar que todos los programas están instalados correctamente, para así compilar y ejecutar tanto las pruebas como el programa correctamente.

```
mvn -version
git --version
java -version
docker version
```

## Instalación
Para descargar el proyecto de GitHub, primero debemos clonar este repositorio, ejecutando la siguiente línea de comando en GIT.

```
git clone https://github.com/DavidRiveraRvD/AREP-MODULARIZACION-VIRTUALIZACION
```

## Ejecución
Para compilar el proyecto utilizando la herramienta Maven, nos dirigimos al directorio donde se encuentra alojado el proyecto, y dentro de este ejecutamos en un Shell o Símbolo del Sistema el siguiente comando:

```
mvn package
```
## Pruebas
Para realizar las pruebas correspondientes del proyecto utilizando la herramienta Maven, nos dirigimos al directorio donde se encuentra alojado el proyecto, y dentro de este ejecutamos en un Shell o Símbolo del Sistema el siguiente comando:

```
mvn test
```

Pruebas compiladas correctamente para el código fuente **RoundRobin**.

![img](https://github.com/DavidRiveraRvD/AREP-MODULARIZACION-VIRTUALIZACION/blob/main/resources/robin.png)

Pruebas compiladas correctamente para el código fuente **LogService**.

![img](https://github.com/DavidRiveraRvD/AREP-MODULARIZACION-VIRTUALIZACION/blob/main/resources/log.png)

----------

### Localhost

Para probar ahora el correcto funcionamiento del Docker de manera local o localhost del programa **RoundRobin**, primero ejecutamos los siguientes comandos en orden.
```
docker build --tag arep-lab5/roundrobin .
docker images
docker run -d -p 8000:6000 --name balanceadordecarga arep-lab5/roundrobin
```


## Construido con
* [Maven](https://maven.apache.org/). Herramienta que se encarga de estandarizar la estructura física de los proyectos de software, maneja dependencias (librerías) automáticamente desde repositorios y administra el flujo de vida de construcción de un software.
* [GIT](https://git-scm.com/). Sistema de control de versiones que almacena cambios sobre un archivo o un conjunto de archivos, permite recuperar versiones previas de esos archivos y permite otras cosas como el manejo de ramas (branches).
* [JUnit](https://junit.org/junit5/). Framework de Java que permite la realización de la ejecución de clases de manera controlada, para poder comprobar que los métodos realizan su cometido de forma correcta.
* [Eclipse](https://www.eclipse.org/ide/). Entorno de desarrollo integrado (IDE) utilizado en programación de computadoras. Contiene un espacio de trabajo básico y un sistema de complementos extensible para personalizar el entorno. Eclipse está escrito principalmente en Java y su uso principal es para desarrollar aplicaciones Java, pero también se puede usar para desarrollar aplicaciones en otros lenguajes de programación a través de complementos (plug-ins).
* [Java](https://www.oracle.com/java/). Lenguaje de programación de propósito general, es decir, que sirve para muchas cosas, para web, servidores, aplicaciones móviles, entre otros. Java también es un lenguaje orientado a objetos, y con un fuerte tipado de variables.
* [Docker](https://www.docker.com/). Programa encargado de crear contenedores ligeros y portables para las aplicaciones software que puedan ejecutarse en cualquier máquina con Docker instalado, independientemente del sistema operativo que la máquina tenga por debajo, facilitando así también los despliegues.
* [AWS](https://aws.amazon.com/es/). Conjunto de herramientas y servicios de cloud computing de Amazon, que engloba una gran cantidad de servicios para poder realizar distintos tipos de actividades en la nube. Desde almacenamiento a la gestión de instancias, imágenes virtuales, desarrollo de aplicaciones móviles, etc.
* [CircleCI](https://circleci.com/). Plataforma moderna de integración continua y entrega continua (CI / CD) que se encarga de automatizar la construcción, pruebas e implementación de software.



## Autor
[David Rivera](https://github.com/DavidRiveraRvD)
