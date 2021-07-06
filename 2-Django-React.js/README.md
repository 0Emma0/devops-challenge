#### Prueba 2 - Despliegue de una aplicación Django y React.js

Elaborar el deployment dockerizado de una aplicación en django (backend) con frontend en React.js contenida en el repositorio. Es necesario desplegar todos los servicios en un solo docker-compose.

**Solución:**

* Se elaboraro el docker-compose.yml ubicado en el directorio raíz, en base a los Dockerfiles que se encuentran en /backend y /frontend respectivamente. 

**Deployment local**

Requisitos
* Tener instalado [Docker Desktop](https://www.docker.com/products/docker-desktop).
* Acceso a linea de comandos y permisos de ejecución.
* Descargar el repo devops-challenge

###### Desde la linea de comandos nos posicionamos donde hemos descargado el repo. Por ejemplo:
```
cd C:\GitHub\devops-challenge\2-Django-React.js
```

###### Ejecutar el siguiente comando:

```
docker-compose up -d
```
###### Comprobamos que los containers estén iniciados:

```
docker-compose ps
```
![image](https://user-images.githubusercontent.com/79091337/124633091-538be780-de5b-11eb-84a0-a5c1e6c65038.png)

###### Desde el explorador ingresamos al siguiente link http://127.0.0.1:8000

<img src="https://i.ibb.co/kxcXzRk/sd.png">

**Deployment en Google Cloud Platform**

Requisitos
* Tener una cuenta habilitada en [Google Cloud Platform](https://cloud.google.com/).
* Crea una nueva instancia de Compute Engine con la imagen estable de [Container-Optimized OS](https://cloud.google.com/container-optimized-os).
###### Dentro de la instancia clonamos el repo de GitHub:

```
git clone https://github.com/0Emma0/devops-challenge.git
cd devops-challenge
```
###### Descargar y ejecutar la imagen de Docker Compose:

```
docker run docker/compose:1.24.0 version
```

###### Ejecutar el comando Docker Compose.

Para que el contenedor de Docker Compose tenga acceso al demonio de Docker, monte el socket de Docker con la opción -v /var/run/docker.sock:/var/run/docker.sock.

Para que el directorio actual esté disponible para el contenedor, use la opción -v "$PWD:$PWD" para montarlo como un volumen y -w="$PWD"para cambiar el directorio de trabajo.:

```
docker run --rm \
    -v /var/run/docker.sock:/var/run/docker.sock \
    -v "$PWD:$PWD" \
    -w="$PWD" \
    docker/compose:1.24.0 up
```

Con el docker run aún ejecutándose, abrir la [página de instancias de Cloud Console](https://console.cloud.google.com/compute/instances?_ga=2.159796280.44682729.1625544919-1638129369.1625370557). Clic en el enlace a la dirección IP externa de su instancia y seleccione el puerto :8000.

Con la ventana SSH abierta, presione Control-C en su teclado para detener la aplicación.

#### Para el desarrollo de esta prueba se tomo de base la documentación oficial.

* [Docker - Build your Node image](https://docs.docker.com/language/nodejs/build-images/).
* [Compose and Django](https://docs.docker.com/samples/django/).
* [Docker-Compose for Django and React](https://saasitive.com/tutorial/docker-compose-django-react-nginx-let-s-encrypt).
* [npn](https://nodejs.org/en/knowledge/getting-started/npm/what-is-npm/).
* [GCP - Container optimized OS](https://cloud.google.com/container-optimized-os). 




