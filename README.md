Recursos obtenidos de [Git Odoo Docker](https://github.com/odoo/docker) para las imágenes oficiales de [Docker Odoo](https://hub.docker.com/_/odoo/)

## Requisitos recomendados
- Docker (>=20.10.2)
- docker-compose (>=1.27.4)

## Build de Dockerfile
Moverse a la ubicación del archivo Dockerfile y ejecutar
```
docker build -t odoo:x.x .
```
```
docker run  odoo:x.x
```

## Build con docker-compose
Moverse a la ubicación del archivo docker-compose.yml y ejecutar
```
docker-compose up -d
```

## Ejecutar comandos dentro del contenedor
```
docker exec -it <nombre_contenedor> /bin/bash
# o si bash está en el PATH
docker exec -it <nombre_contenedor> bash
...
exit
```