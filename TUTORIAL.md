# TUTORIAL

## Comandos Git básicos

### Crear un nuevo repositorio: init

Crea un nuevo repositorio localmente. <br>
Ejecute el siguiente comando para crear un directorio vacío llamado `tutorial` y colóquelo bajo control Git.<br>
Seguiremos utilizando este directorio en tutoriales posteriores.
```
$ mkdir ~/tutorial
```

Para poner el directorio `tutorial` bajo el control de Git, vaya a ese directorio y utilice el comando `init`.
```
$ cd ~/tutorial
$ git init
Initialized empty Git repository
in /Users/yourname/Desktop/tutorial/.git/
```
___
##### Consejo
El comando `init` crea el directorio `.git`. El directorio `.git` contiene los archivos necesarios para que Git funcione.<br>

```
koyno@LAPTOP-J1K1E58T MINGW64 ~/tutorial (master)
$ ls -la
total 33
drwxr-xr-x 1 koyno 197609  0 Apr  2 11:40 ./
drwxr-xr-x 1 koyno 197609  0 Apr 24 14:56 ../
drwxr-xr-x 1 koyno 197609  0 Apr  9 15:23 .git/
```
___

### Guardar los Cambios en el Repositorio: status, add, commit, log, diff

Cree un fichero de texto llamado `sample.txt` en el directorio `tutorial`. 
```
$ nano sample.txt
```

En el contenido del archivo, introduzca el siguiente texto.
```
Comandos Git básicos
```

Utiliza el comando `status` para comprobar el árbol de trabajo y el estado de los índices de los directorios bajo control Git.<br>
Ejecuta el comando `status` para comprobar el estado del directorio `tutorial`.
```
$ git status
# On branch master
#
# Initial commit
#
# Untracked files:
#   (use "git add <file>..." to include in what will be committed)
#
#     sample.txt
nothing added to commit but untracked files present (use "git add" to track)
```

Utilice el comando `add` para registrar ficheros en el índice. <br>
El `<archivo>` especifica el archivo que se registrará en el índice. Se pueden especificar varios ficheros, separados por espacios.
```
$ git add <archivo>..
```

En realidad, ejecute el siguiente comando para añadir `sample.txt` al índice y compruébelo.<br>
El archivo `sample.txt` ha sido añadido al índice y está listo para ser commit.

```
$ git add sample.txt
$ git status
# On branch master
#
# Initial commit
#
# Changes to be committed:
#   (use "git rm --cached <file>..." to unstage)
#
#     new file:   sample.txt
#
```

El siguiente paso es confirmar ejecutando el comando `commit`. El formato del comando `commit` es.
```
$ git commit -m "<Comentario>"
```

Ejecute el comando `commit` antes de comprobar el estado, como se indica a continuación.
```
$ git commit -m "initial commit"
[master (root-commit) 116a286] initial commit
0 files changed, 0 insertions(+), 0 deletions(-)
create mode 100644 sample.txt

$ git status
# On branch master
nothing to commit (working directory clean)
```

Compruebe el historial de cambios del repositorio. Utilice el comando `log` para ver el historial de cambios del repositorio.
```
$ git log
commit ac56e474afbbe1eab9ebce5b3ab48ac4c73ad60e
Author: eguchi <eguchi@nulab.co.jp>
Date:   Thu Jul 12 18:00:21 2012 +0900
    initial commit
```

A continuación, editamos `sample.txt` y hacemos commit de nuevo.

Añade `sample.txt` al siguiente texto.
```
start a working area (see also: git help tutorial)
   init      Create an empty Git repository or reinitialize an existing one

work on the current change (see also: git help everyday)
   add       Add file contents to the index

examine the history and state (see also: git help revisions)
   log       Show commit logs
   status    Show the working tree status

grow, mark and tweak your common history
   commit    Record changes to the repository
```

En realidad, ejecute el siguiente comando para añadir `sample.txt` al índice y compruébelo.<br>
El comando `diff` también puede utilizarse para revisar los cambios.<br>
El archivo `sample.txt` ha sido añadido al índice y está listo para ser commit.
```
$ git status
～contenidos de salida～
$ git diff
～contenidos de salida～
$ git add sample.txt
$ git status
～contenidos de salida～
```

Ejecute el comando `commit` antes de comprobar el estado, como se indica a continuación.
```
$ git commit -m "Descripción adicional del comando"
～contenidos de salida～
$ git status
～contenidos de salida～
```

Compruebe el historial de cambios del repositorio.
```
$ git log
```

Resultado de la ejecución del comando：
![image](https://github.com/kkk-commit/ITCHA-tutorial-basico/assets/83223664/1d798219-56c5-4b72-80f6-52e86548320a)

![image](https://github.com/kkk-commit/ITCHA-tutorial-basico/assets/83223664/969b6c1f-9d9e-4de2-a576-1881116f046d)

