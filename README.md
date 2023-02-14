# Tutorial de Docker WSL para MYSQL Vitrinia

Requerimientos:
Docker Desktop de Windows

WSL2 con Integración a Docker

## Explicación

Para ahorrar tiempo y explicación, este repositorio cumple la función de facilitar y acelerar el proceso de instalación de MySQL de Docker en WSL.

Solo clona este repositorio y ejecuta:

`docker-compose -f docker-compose.yaml up -d`

Luego, accede a la terminal bash del contenedor docker creado con:

`docker exec -it mysql-db mysql -uroot -proot`

Crea un usuario, este te servirá para poder acceder al mysql con un cliente
```
create user 'vitrinia'@'%' identified by 'vitrinia';
grant all privileges on vitrinia.* to 'vitrinia'@'%';
flush privileges;
```

Accede con un cliente al servidor ya sea con mysql-client o con MySQL Workbench con las credenciales y configuraciones creadas.

Host: 127.0.0.1

Port: 3306

User: vitrinia

Password: vitrinia

Disfruta

### Comandos utiles
Consumir database

docker exec mysql-db /usr/bin/mysqldump --no-tablespaces --opt -u vitrinia -p vitrinia > vitrinia_prod.sql

