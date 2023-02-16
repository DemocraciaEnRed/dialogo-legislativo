![Header](header-doc.png)


# Diálogo Legislativo - Instalación (Docker)

> ### ⚠️ NOTAS IMPORTANTES
> 
> El siguiente conjunto de sistemas requiere de:
> - Keycloak 4.4.x o 6.0.x
> 
> Keycloak es un sistema open source de identificación y gestión de acceso de usuarios. Es un sistema complejo y para fines de testing, en [Democracia en Red](https://democraciaenred.org) sabemos que la instalacion de Keycloak puede ser un bloqueo para intenciones de testing. Para eso, comunicate con nosotros y podemos ayudarte a hacer el setup y utilizar nuestro Keycloak de Democracia en Red. Envianos un correo electronico en [it@democraciaenred.org](mailto:it@democraciaenred.org) o contactanos a través de nuestro [Twitter](https://twitter.com/fundacionDER).


En primer lugar, descargar el repositorio

En el mismo encontraras el siguiente [docker-compose.yml](docker-compose.yml)

Para comenzar, simplemente correr `docker-compose up` para descargar las imagenes, crear y correr los containers. Luego se puede acceder a la web desde [https://localhost:3000](https://localhost:3000)


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

