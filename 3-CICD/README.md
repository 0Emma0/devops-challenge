#### Prueba 3 - CI/CD

Dockerizar un nginx con el index.html default.
Elaborar un pipeline que ante cada cambio realizado sobre el index.html buildee la nueva imagen y la actualize en la plataforma elegida.

#### Solución:

* Se elaboro el Dockerfile correspondiente para el container con nginx.
* Al realizar cambios en el archivo index.html alojado en /3-CICD/src/ y luego un push a la master branch, se dispara el workflow que realiza el build del container hosteado en Azure.
* Para la solución se utilizo GitHub Actions y Azure App Service.
* Link del site: https://nginx-web.azurewebsites.net/ 

#### Demo:

<img src="https://i.ibb.co/CwvhgP0/Untitled.png">

#### Para el desarrollo de esta prueba se tomo de base la documentación oficial y experiencias adquiridas.

* [NGINX Official Image](https://www.docker.com/blog/how-to-use-the-official-nginx-docker-image/).
* [Azure - GitHub Actions]( https://docs.microsoft.com/en-us/azure/app-service/deploy-container-github-action?tabs=publish-profile/).





