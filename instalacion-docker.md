![Header](header-doc.png)


# Diálogo Legislativo - Instalación (Docker)

> ### ⚠️ NOTAS IMPORTANTES
> 
> El siguiente conjunto de sistemas requiere de:
> - Keycloak 4.4.x o 6.0.x
> 
> Keycloak es un sistema open source de identificación y gestión de acceso de usuarios. Es un sistema complejo y para fines de testing, en [Democracia en Red](https://democraciaenred.org) sabemos que la instalacion de Keycloak puede ser un bloqueo para intenciones de testing. Para eso, comunicate con nosotros y podemos ayudarte a hacer el setup y utilizar nuestro Keycloak de Democracia en Red. Envianos un correo electronico en [it@democraciaenred.org](mailto:it@democraciaenred.org) o contactanos a través de nuestro [Twitter](https://twitter.com/fundacionDER).
> 
> Para conocer más sobre keycloak lee nuestro [instructivo sobre el software](./sobre-keycloak.md)


En primer lugar, descargar el repositorio

En el mismo encontraras el siguiente [docker-compose.yml](docker-compose.yml)

Para comenzar, simplemente correr `docker-compose up` para descargar las imagenes, crear y correr los containers. Luego se puede acceder a la web desde [https://localhost:3000](https://localhost:3000)

Este comando correrá los cuatro contenedores de docker necesarios para el funcionamiento del sistema. Para verlos `docker ps`

```console
CONTAINER ID   IMAGE                                                        COMMAND                  CREATED          STATUS         PORTS                                                 NAMES
5b7caaac8f16   ghcr.io/democraciaenred/dialogo-legislativo-web:0.0.1        "docker-entrypoint.s…"   7 minutes ago    Up 5 seconds   0.0.0.0:3000->3000/tcp, :::3000->3000/tcp             dialogo-legislativo_web_1
ef338545f54f   ghcr.io/democraciaenred/dialogo-legislativo-notifier:0.0.1   "docker-entrypoint.s…"   7 minutes ago    Up 4 seconds   0.0.0.0:5000->3000/tcp, :::5000->3000/tcp             dialogo-legislativo_notifier_1
a61048d2bf93   ghcr.io/democraciaenred/dialogo-legislativo-core:0.0.1       "docker-entrypoint.s…"   7 minutes ago    Up 5 seconds   3000/tcp, 0.0.0.0:4000->4000/tcp, :::4000->4000/tcp   dialogo-legislativo_core_1
d9ecb0efa951   mongo:3.6                                                    "docker-entrypoint.s…"   10 minutes ago   Up 6 seconds   0.0.0.0:27017->27017/tcp, :::27017->27017/tcp         dialogo-legislativo_mongo_1

```
Para conocer el uso y los límites de recursos de los contenedores utilizar el comando `docker stats`

```console
CONTAINER ID   NAME                             CPU %     MEM USAGE / LIMIT     MEM %     NET I/O           BLOCK I/O         PIDS
09873da8bba0   dialogo-legislativo_web_1        13.97%    51.13MiB / 7.657GiB   0.65%     5.35kB / 0B       1.75MB / 0B       25
03ad81e15dbd   dialogo-legislativo_notifier_1   0.02%     112.6MiB / 7.657GiB   1.44%     8.48kB / 5.17kB   287kB / 0B        22
7da0edffd8a0   dialogo-legislativo_core_1       0.00%     99.13MiB / 7.657GiB   1.26%     16.9kB / 10.7kB   17.2MB / 0B       22
2b96a3a4cfc0   dialogo-legislativo_mongo_1      0.56%     132.2MiB / 7.657GiB   1.69%     21.7kB / 14.3kB   5.68MB / 45.1kB   30
```


Dejamos algunos comandos utiles y su descripción

```bash
# Levantar servicios. Se puede detener si se hace Ctrl+C
$ docker-compose up

# Si los containers siguen corriendo y se quieren detener:
$ docker-compose stop

# Si se quiere eliminar solo los containers
$ docker-compose rm

# Si se quiere eliminar todo lo que el comando "up" inicializo (containers, volumenes, imagenes, etc)
$ docker-compose down
```

