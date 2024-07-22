<!-- Instructivo so/bre como desplegar y usar los contenedores docker de los servicios ITC -->
<!--  -->

# Instructivo de contenedores docker

Este es el instructivo oficial de contenedores docker para ITConsultants. Este material contiene, especialmente en los archivos de configuración, claves y nombres de usuario genéricos que deben ser cambiados a la hora de realizar un despliegue

<!-- créditos -->

> Versión 0.1
> </br>
> 18/7/2024
> </br>
> <jcortes@itconsultants.cl>
></br>
> ITConsultants

<!-- links de MD individuales -->

</br>

## Módos de uso

> Linux (Máquina virtual, VPS o SO Principal) o WSL
> </br>
> en el presente tutorial se abordará el uso de Docker y Docker-compose
> </br> sólo desde la consola en Linux, particularmente Debian 12
> </br> la forma de uso para otros sistemas GNU/Linux es similar pero con cambios
> </br> en algunos de los comandoss

### Requisitos

> sudo apt-get install docker docker-compose tmux zsh git
> </br> ohMyZsh para control de rama git desde la terminal
> </br> [ohMyZsh](https://ohmyz.sh/)

</br>

### Documentación individual de aplicaciones

[Zabbix](./zabbix/README.md)
</br>
[Odoo](./odoo/README.md)
</br>
[Duplicati](./duplicati/README.md)
</br>
[Grafana](./grafana/README.md)
</br>
[Neesus](./neesus/README.md)
</br>
[Wazuh](./wazuh/README.md)

</br>

## Introducción

Documentación

Usar Docker Compose es un proceso de tres pasos:
Definir el ambiente de tu aplicación con un Dockerfile para que se pueda reproducir en cualquier parte.
Definir los servicios que componen tu app en el yaml para que puedan correr juntos en un ambiente aislado.
Finalmente, correr docker compose y Compose empezará a correr tu app completa.
Un archivo docker-compose se ve así:

```yaml
version: "2.1"
services:
  heimdall:
    image: linuxserver/heimdall
    container_name: heimdall
    volumes:
      - /home/user/appdata/heimdall:/config
    environment:
      - PUID=1000
      - PGID=1000
      - TZ=Europe/London
    ports:
      - 80:80
      - 443:443
    restart: unless-stopped
```

</br>

## Documentación adicional

[Debian](https://www.debian.org/index.es.html)
</br>[Docker](https://docs.docker.com/)
</br>[Docker Compose](https://docs.docker.com/compose/compose-file)
</br>[Tmux](https://github.com/tmux/tmux/wiki)
</br>[Zsh](https://www.zsh.org/)
