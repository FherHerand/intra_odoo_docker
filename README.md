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

O para ver los logs en la consola, ejecutar
```
docker-compose up
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

## Definir timezone de postgresql
Dentro del contenedor de postgres
```
psql -U odoo -d <base de datos de odoo>
```

```
\l+
\dt+
SHOW TIMEZONE;
SELECT * FROM pg_timezone_names WHERE name LIKE '%Guatemala';

SET TIMEZONE='America/Guatemala';
SHOW TIMEZONE;
```

## Ejecutar comandos dentro del contenedor como ROOT
```
docker exec -u root <nombre_contenedor> <comando>
```

Por ejemplo
```
docker exec -u root 80aa2d3be335 pip install XlsxWriter==2.0.0
```