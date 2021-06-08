Recursos obtenidos de [Git Odoo Docker](https://github.com/odoo/docker) para las imágenes oficiales de [Docker Hub Odoo](https://hub.docker.com/_/odoo/)

## Versiones
- 12.0
- 13.0
- 14.0

## Requisitos recomendados
- Docker (>=20.10.2)
- docker-compose (>=1.27.4)

## Build de odoo
### Build con Dockerfile
Moverse a la ubicación del archivo Dockerfile y ejecutar
```
docker build -t odoo:x.x .
```
```
docker run odoo:x.x
```

### Build con docker-compose
Moverse a la ubicación del archivo docker-compose.yml y ejecutar
```
docker-compose up -d
```

## Crear un módulo con odoo docker
```
docker exec -it <nombre_contenedor> /usr/bin/odoo scaffold <nombre_modulo> /mnt/extra-addons/
```

## Reiniciar odoo con odoo docker
```
docker exec -it <nombre_contenedor> /etc/init.d/odoo restart
```

## Ver log odoo con odoo docker
```
docker exec -it <nombre_contenedor> tail -100 /var/log/odoo/odoo-server.log
```

## Ejecutar comandos dentro del contenedor
```
docker exec -it <nombre_contenedor> /bin/bash
# o si bash está en el PATH
docker exec -it <nombre_contenedor> bash
...
exit
```