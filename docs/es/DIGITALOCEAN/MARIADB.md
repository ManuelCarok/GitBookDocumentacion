# MariaDB

## Acceso Remoto

1. Modificar el archivo de configuración de MySQL:

    ```bash
    $ sudo nano /etc/mysql/mariadb.conf.d/50-server.cnf
    ```

    o

    ```bash
    $ sudo nano /etc/mysql/mysql.conf.d/mysqld.cnf
    ```

    Buscaremos las siguientes líneas y se descomentarán en caso de estar comentadas:

    `skip-external-locking`

    `bind-address = 127.0.0.1` 

    La IP que le vamos a dar a bind-address será **0.0.0.0**. En caso de que tengáis una IP específica a la que queráis dar acceso, simplemente ponedla.

2. En este paso se reiniciará el servicio de MySQL para que se apliquen los cambios:

    ```bash
    $ sudo systemctl restart mariadb.service
    ```

3. Hay que dar permisos específicos de acceso al usuario de la base de datos. Yo para desarrollo siempre utilizo usuario root y contraseña root, pero cada uno que ponga el suyo. Antes de nada, hay que entrar a la consola de MySQL:

    ```bash
    $ sudo mysql –u root -p
    ```

    Tras esto, se le dan los privilegios al usuario en cuestión. En este caso root:

    ```bash
    $ GRANT ALL PRIVILEGES ON [name-database].* TO [user]@'%' IDENTIFIED BY '[your-password-database]';

    FLUSH PRIVILEGES;
    ```

4. Activar puerto UFW

    ```bash
    $ sudo ufw allow 3306/tcp
    ```

    Exclusivamente a una o varias ip.

    ```bash
    $ sudo ufw allow from 192.168.1.2 to any port 3306
    ```