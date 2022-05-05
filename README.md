# gitlab-docker-compose
Gitlab CE - Docker Compose IaC

## Requisitos
- Docker
- Docker Compose
```
apt-get install docker docker-compose -y
```
- Puertos 80 y 443 de la máquina accesibles desde Inet
- Registro DNS apuntando a la IP pública de la máquina
- Indicar DNS en el fichero .yml
- Establecer contraseña (generar un hash para no ponerla en plano en el fichero, o, mejor aun, utilizar un secreto)

## Ejecución

Nos situamos en el directorio en el que hayamos colocado el fichero docker-compose.yml y ejecutamos:
```
docker-compose up -d
```

## Primer acceso

En el mismo directorio, podemos ejecutar lo siguiente para ver el estado del entorno:
```
docker-compose ps
```

Cuando esté todo healthy, ya podemos acceder.

Para obtener la pass del usuario root:
```
sudo docker exec -it gitlab grep 'Password:' /etc/gitlab/initial_root_password
```
