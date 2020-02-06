# SSH

## ¿Que es SSH?

SSH es el nombre de un protocolo y del programa que lo implementa cuya principal función es el acceso remoto a un servidor por medio de un canal seguro en el que toda la información está cifrada.

## Generar una llave SSH

### Para Windows

Usar PowerShell usar el siguiente comando.

```bash
$ ssh-keygen
```

Respuesta:

1. Se agrega la ruta donde se va crear las llaves SSH.

    ```bash
    Generating public/private rsa key pair.
    Enter file in which to save the key (C:\Users\[nombre-de-usuario]/.ssh/id_rsa): C:\Users\[nombre-de-usuario]/.ssh/[nombre-de-archivo]
    ```

2. Si deseas colocarle una contraseña (Si no deseas con contraseña <kbd>Enter</kbd>)

    ```
    Enter passphrase (empty for no passphrase):
    Enter same passphrase again:
    ```

### Conexión con SSH (Opciones)

1. Opión 1:

    ```bash
    $ ssh [user]@[dominio o ip] -i C:\Users\[nombre-de-usuario]\.ssh\[nombre-de-archivo]

    ```

2. Opcion 2: (Configuración)

    - Configuración
        En el directorio **C:\\Users\\[nombre-de-usuario]\\.ssh\\** se crea un archivo **config** (Sin extensión)

        Se agrega la siguiente configuración:

        ```
        ServerAliveInterval 120
        ServerAliveCountMax 3

        Host [NombreComando]
            HostName [IPAddress]
            User [Usuario]
            IdentityFile C:\Users\[nombre-de-usuario]\.ssh\[nombre-de-archivo] (sin extensión)
        ```

    - Conexión

    ```
    $ ssh [NombreComando]
    ```




