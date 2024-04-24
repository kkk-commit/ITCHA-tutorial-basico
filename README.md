# git-tutorial-básico

## Concepto básico de Git

### Control de versiones mediante Git

Git te permite guardar el estado de un archivo como un historial de actualizaciones siempre que quieras.<br>
Esto te permite revertir un archivo una vez editado a un estado anterior y ver las diferencias en las partes editadas del archivo.

Además, si intentas sobrescribir el último archivo editado por otra persona con un archivo editado a partir de un archivo anterior, recibirás una advertencia cuando subas el archivo al servidor.<br>
Por lo tanto, no se producirán errores como sobrescribir sin saberlo las ediciones de otra persona.

* Muchos de nosotros hemos utilizado en algún momento de nuestras vidas la versión de control de versiones de añadir una fecha a un nombre de archivo.

![image](https://github.com/itcha-organization/git-tutorial-basico/assets/83223664/0b2f40f0-5401-49fc-b75d-f3579acaf4a0)

### Repositorios para la gestión del historial

Un repositorio es el elemento más básico de Git. Es más fácil imaginarlos como una carpeta del proyecto.<br>
Un repositorio contiene todos los archivos del proyecto (incluida la documentación) y almacena el historial de revisión de cada archivo.

Los repositorios Git pueden dividirse en dos tipos: repositorios remotos y repositorios locales.

* Repositorios remotos<br>
  Se trata de repositorios ubicados en un servidor dedicado y compartido por varios usuarios.
* Repositorios locales<br>
  Son repositorios que se colocan en tu propia máquina para el uso de usuarios individuales.

Al dividir el repositorio en dos tipos, remoto y local, puedes utilizar el repositorio local para tus cambios del código en la máquina que tengas a mano.

![image](https://github.com/itcha-organization/git-tutorial-basico/assets/83223664/7200aabb-4f1d-4707-9d32-57a98b1b75d2)

### commit de los cambios (Commit)

Para registrar adiciones y cambios a ficheros y directorios en el repositorio, se realiza una operación llamada commit.

Cuando realiza una commit, se crea una commit (o revisión) en el repositorio, que registra la diferencia entre la última commit y el estado actual.

Estos commits se almacenan en el repositorio en orden cronológico, como se muestra en el siguiente diagrama.<br>
Rastreando estos commits desde el último, puedes ver la historia de los cambios pasados y su contenido.

* HEAD<br>
  Puntero que indica dónde está trabajando actualmente, normalmente la commit más reciente en el extremo.

![image](https://github.com/itcha-organization/git-tutorial-basico/assets/83223664/9c570bff-cd35-4df7-820a-cd7a91fed114)

### Árbol de trabajo y staging (o índice)

En Git, el directorio en el que estás trabajando, que está bajo el control de Git, se llama árbol de trabajo.

Con el comando `git add` enviamos los cambios a staging (o índice), que es un estado intermedio en el que se van almacenando los archivos a enviar en el commit.<br>
Finalmente con `git commit` lo enviamos al repositorio local.

Si queremos colaborar con otros, con `git push` subimos los archivos a un repo remoto y mediante `git pull` podríamos traer los cambios realizados por otros en remoto hacia nuestro directorio de trabajo.

Si comenzamos trabajando en remoto, lo primero que hacemos es un clon de la información en el directorio local.

![image](https://github.com/itcha-organization/git-tutorial-basico/assets/83223664/e73ab163-252f-4083-9ae4-2d7e9b46ed75)

## Configuración

Si ya ha completado la configuración, puede practicar los comandos en siguiente pagina.<br>
https://learngitbranching.js.org/?locale=es_AR
___

### Instalación y configuración inicial de Git en Windows

Siga los pasos del siguiente artículo para instalarlo.<br>
https://www.neoguias.com/instalar-git-windows/

Una vez instalado, inicia Menú Inicio > Todos los programas > Git > Git Bash.

La configuración de git se registra en un archivo .gitconfig que se crea en el directorio home del usuario. Puedes editar el archivo directamente, pero aquí usaremos el comando config para configurar los ajustes. <br>
Establecer el nombre de usuario y la dirección de correo electrónico, que se registran en commit.
```
$ git config --global user.name "<Nombre de usuario>"
$ git config --global user.email "<Dirección de correo electrónico de ITCHA>"
```
![image](https://github.com/itcha-organization/git-tutorial-basico/assets/83223664/696064d0-b5d3-40e6-b5ed-de30fc42d89e)

### Creación de una cuenta en GitHub

Siga los pasos del siguiente artículo para creala.<br>
※Más adelante, podrá vincular su dirección de correo electrónico ITCHA a su cuenta. Por lo tanto, puede utilizar la dirección de cualquier correo electrónico.<br>
https://docs.github.com/es/get-started/start-your-journey/creating-an-account-on-github#signing-up-for-a-new-personal-account

### Cómo generar una clave SSH y agregarla a GitHub

##### Cómo generar una nueva clave SSH

Ejecute el siguiente comando, reemplazando el parámetro de segundo opcion por tu dirección de correo.<br>
```
$ ssh-keygen -t ed25519 -C "<Dirección de correo electrónico de ITCHA>"
```

Reaccione a la commit pulsando Intro.
![image](https://github.com/itcha-organization/git-tutorial-basico/assets/83223664/41a3c6c4-67ac-40dd-8a1b-f534c2eaf782)

Si aparece la siguiente commit, seleccione `No` e inténtelo con una clave existente.
```
/c/Users/oonumakyou/.ssh/id_ed25519 already exists.
Overwrite (y/n)?
```
![image](https://github.com/itcha-organization/git-tutorial-basico/assets/83223664/f15ae475-fe0e-4e1b-8f94-ea5b71a17dfc)

#### Cómo agregar una clave SSH a tu cuenta de GitHub

Ejecute el siguiente comando para copiar la clave
```
$ clip < ~/.ssh/id_ed25519.pub
```

Seguidamente, accede a tu cuenta de GitHub mediante tu navegador y accede a la configuración de tu cuenta haciendo clic en la foto de perfil de la parte superior derecha del menú y luego en Configuración (Settings).
![image](https://github.com/itcha-organization/git-tutorial-basico/assets/83223664/8d49183f-7233-4cb1-b976-41430e3f10ee)

Haz clic en la opción Claves SSH y GPC (SSH and GPC keys) que verás en la sección Acceso (Access) del menú de la izquierda.
![image](https://github.com/itcha-organization/git-tutorial-basico/assets/83223664/b6bffcc3-1211-4fdb-8f0f-0d10c4efb003)


Haz clic en Nueva clave SSH (New SSH Key) e introduce un nombre para la clave en el campo Título (Title). Luego pega la clave SSH que has copiado anteriormente en el campo Key, dejando seleccionada la opción Key type.
Finalmente haz clic en el botón Agregar clave SSH (Add SSH key). Si se te solicita la contraseña de tu cuenta, introdúcela.
![image](https://github.com/itcha-organization/git-tutorial-basico/assets/83223664/40fa1974-bf51-46e5-9ff2-cbcbd5b9490e)


Ejecute el siguiente comando para comprobar la conexión
```
$ ssh -T git@github.com
```
![image](https://github.com/itcha-organization/git-tutorial-basico/assets/83223664/16ba4f58-92f1-426a-a1ce-16907b565bf7)

###### Página de referencia.
[Documentación de GitHub:Conectar a GitHub con SSH](https://docs.github.com/es/authentication/connecting-to-github-with-ssh)<br>
[Cómo generar una clave SSH y agregarla a GitHub](https://www.neoguias.com/generar-clave-ssh-agregar-github/)


