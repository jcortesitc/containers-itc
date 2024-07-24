# Zabbix Docker

Esta es la documentación de la instalación de Zabbix usando Docker compose

* clonar el repositorio

```bash
git clone https://github.com/jcortes-itc/containers-itc.git
```

* Navegar al directorio de Zabbix:

```bash
cd containers-itc/zabbix
```

* Crear la red de Docker:

```bash
docker network create zabbix-net
```

* Construir la imagen de Docker:

```bash
docker-compose build
```

* Iniciar los contenedores:

```bash
docker-compose up -d
```

## Acceso

* Zabbix Server: <http://localhost:8080>
* Zabbix Agent: <http://localhost:10050>

## Configuración

* **Zabbix Server:**
  * **Base de datos:**
    * **Usuario:** zabbix
    * **Contraseña:** zabbix
    * **Base de datos:** zabbix
  * **Servidor web:**
    * **Puerto:** 8080
* **Zabbix Agent:**
  * **Servidor:** 127.0.0.1
  * **Puerto:** 10051
  * **Identificador:** 10050

## Notas

* La configuración de la base de datos se encuentra en el archivo `docker-compose.yml`.
* La configuración del servidor web se encuentra en el archivo `zabbix-server/conf/zabbix_server.conf`.
* La configuración del agente se encuentra en el archivo `zabbix-agent/conf/zabbix_agentd.conf`.
* Se recomienda usar un servidor web como Nginx o Apache para servir Zabbix.

## Desinstalación

* Detener los contenedores:

```bash
docker-compose down
```

* Eliminar los contenedores:

```bash
docker-compose rm -f
```

* Eliminar la red de Docker:

```bash
docker network rm zabbix-net
```

* Eliminar la imagen de Docker:

```bash
docker image prune -f
```

## Actualización

* Detener los contenedores:

```bash
docker-compose down
```

* Actualizar la imagen de Docker:

```bash
docker-compose pull
