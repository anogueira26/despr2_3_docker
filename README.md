## Descripción del proyecto:

En esta práctica vamos a replicar las prácticas 2.1 (Apache) y 2.2 (nginx) usando contenedores Docker

- Apache: Servir un sitio estático desde la imagen oficial httpd:2.4, mapeando puertos y montando el sitio como bind mount.
- Nginx: Servir el mismo sitio estático montándolo como bind mount y usando un server block propio.

## Pasos seguidos para la instalación y despliegue. Capturas de pantalla del proceso: configuración, comprobaciones, estructura de archivos, página cargada y navegación. 

1. Actualizar la maquina virtual:

    - sudo apt update:
    ![update](img/update.png)

2. Instalación de Docker:

    - sudo apt install docker.io -y:
    ![docker.io](img/installdockerio.png)

    - sudo systemctl start docker:
    ![startdocker](img/iniciardocker.png)

    - sudo systemctl enable docker y sudo usermod -aG docker $USER:
    ![habilitaryañadirdocker](img/habilitaryañadirgrupodocker.png)

    - sudo apt install docker-compose -y:
    ![installdockercompose](img/installdockercompose.png)

3. Levantar Apache y Nginx con Docker:

    - Apache:
    ![levantarapachecondocker](img/levantarapachecondocker.png)

    - Nginx:
    ![levantarnginxcondocker](img/levantarnginxcondocker.png)

4. Verificar:

    - Apache Logs:
    ![logsapache](img/logsapache.png)

    - Nginx Logs:
    ![logsnginx](img/logsnginx.png)

5. Alternativamente, usar Docker Compose.

    - Crea docker-compose.yml:
    ![docker-compose.yml](img/creardocker-compose.png)

    - Verificar:
    ![ejecutarcomposeyestadoporarchivo](img/ejecutarcomposeyestadoporarchivo.png)

## Incluye captura de los contenedores en ejecución, del contenido del sitio servido tanto dentro de la VM (comando curl o wget) como desde el host (navegador).

Contenedores en ejecución: 
    ![ejecutarcomposeyestadoporarchivo](img/ejecutarcomposeyestadoporarchivo.png)

Curl:
- En la maquina virtual:
![curl83virtual](img/curl83virtual.png)
![curl84virtual](img/curl84virtual.png)


- En el host:
![curl83host](img/curl83host.png)
![curl84host](img/curl84host.png)



Wget:
- En la maquina virtual:
![wgetvirtual](img/wgetvirtual.png)
- En el host:
![wgethost](img/wgethost.png)


- Desde el navegador:
    - apache:
    ![webapache](img/web%20apache.png)

    - nginx:
    ![webnginx](img/webnginx.png)



## Problemas encontrados durante la configuración y despliegue, y cómo los solucionaste. 

El problemas fue que no me cargaban las páginas desde el navegador del host. La solución fue crear reglas para apache y nginx para acceder a las páginas.

![webnginx](img/configpuertos.png)

