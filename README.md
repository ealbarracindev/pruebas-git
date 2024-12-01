# pruebas-git
Distintas pruebas para el manejo de un repo
## Configuración Básica

Configurar Nombre que salen en los commits
```ssh
	git config --global user.name "dasdo"
```
Configurar Email
```ssh	
	git config --global user.email dasdo1@gmail.com
```
Marco de colores para los comando
```ssh
	git config --global color.ui true
```

## Iniciando repositorio

Iniciamos GIT en la carpeta donde esta el proyecto
```ssh
	git init
```
Clonamos el repositorio de github o bitbucket
```ssh
	git clone <url>
```
Añadimos todos los archivos para el commit
```ssh
	git add .
```
Hacemos el primer commit
```ssh
	git commit -m "Texto que identifique por que se hizo el commit"
```
subimos al repositorio
```ssh
	git push origin master
```

## GIT CLONE


Clonamos el repositorio de github o bitbucket
```ssh
	git clone <url>
```
Clonamos el repositorio de github o bitbucket ?????
```ssh
	git clone <url> git-demo
```

## GIT ADD


Añadimos todos los archivos para el commit
```ssh
	git add .
```
Añadimos el archivo para el commit
```ssh
	git add <archivo>
```
Añadimos todos los archivos para el commit omitiendo los nuevos
```ssh
	git add --all 
```
Añadimos todos los archivos con la extensión especificada
```ssh
	git add *.txt
```
Añadimos todos los archivos dentro de un directorio y de una extensión especifica
```ssh
	git add docs/*.txt
```
Añadimos todos los archivos dentro de un directorios
```ssh
	git add docs/
```
## GIT COMMIT

Cargar en el HEAD los cambios realizados
```ssh
	git commit -m "Texto que identifique por que se hizo el commit"
```
Agregar y Cargar en el HEAD los cambios realizados
```ssh
	git commit -a -m "Texto que identifique por que se hizo el commit"
```
De haber conflictos los muestra
```ssh
	git commit -a 
```
Agregar al ultimo commit, este no se muestra como un nuevo commit en los logs. Se puede especificar un nuevo mensaje
```ssh
	git commit --amend -m "Texto que identifique por que se hizo el commit"
```
## GIT PUSH

Subimos al repositorio
```ssh
	git push <origien> <branch>
```
Subimos un tag
```ssh
	git push --tags
```
## GIT LOG

Muestra los logs de los commits
```ssh
	git log
```
Muestras los cambios en los commits
```ssh
	git log --oneline --stat
```
Muestra graficos de los commits
```ssh
	git log --oneline --graph
```
## GIT DIFF

Muestra los cambios realizados a un archivo
```ssh
	git diff
	git diff --staged
```
## GIT HEAD

Saca un archivo del commit
```ssh
	git reset HEAD <archivo>
```
Devuelve el ultimo commit que se hizo y pone los cambios en staging
```ssh
	git reset --soft HEAD^
```
Devuelve el ultimo commit y todos los cambios
```ssh
	git reset --hard HEAD^
```
Devuelve los 2 ultimo commit y todos los cambios
```ssh
	git reset --hard HEAD^^
```
Rollback merge/commit
```ssh
	git log
	git reset --hard <commit_sha>
```
## GIT REMOTE

Agregar repositorio remoto
```ssh
	git remote add origin <url>
```
Cambiar de remote
```ssh
	git remote set-url origin <url>
```
Remover repositorio
```ssh
	git remote rm <name/origin>
```
Muestra lista repositorios
```ssh
	git remote -v
```
Muestra los branches remotos
```ssh	
	git remote show origin
```
Limpiar todos los branches eliminados
```ssh
	git remote prune origin 
```
## GIT BRANCH

Crea un branch
```ssh
	git branch <nameBranch>
```
Lista los branches
```ssh
	git branch
```
Comando -d elimina el branch y lo une al master
```ssh
	git branch -d <nameBranch>
```
Elimina sin preguntar
```ssh
	git branch -D <nameBranch>
```
## GIT TAG

Muestra una lista de todos los tags
```ssh
	git tag
```
Crea un nuevo tags
```ssh
	git tag -a <verison> - m "esta es la versión x"
```
## GIT REBASE

Los rebase se usan cuando trabajamos con branches esto hace que los branches se pongan al día con el master sin afectar al mismo

Une el branch actual con el mastar, esto no se puede ver como un merge
```ssh
	git rebase
```
Cuando se produce un conflicto no das las siguientes opciones:

cuando resolvemos los conflictos --continue continua la secuencia del rebase donde se pauso
```ssh	
	git rebase --continue 
```
Omite el conflicto y sigue su camino
```ssh
	git rebase --skip
```
Devuelve todo al principio del rebase
```ssh
	git reabse --abort
```
Para hacer un rebase a un branch en especifico
```ssh	
	git rebase <nameBranch>
```
## OTROS COMANDOS

Lista un estado actual del repositorio con lista de archivos modificados o agregados
```ssh
	git status
```
Quita del HEAD un archivo y le pone el estado de no trabajado
```ssh
	git checkout -- <file>
```
Crea un branch en base a uno online
```ssh
	git checkout -b newlocalbranchname origin/branch-name
```
Busca los cambios nuevos y actualiza el repositorio
```ssh
	git pull origin <nameBranch>
```
Cambiar de branch
```ssh
	git checkout <nameBranch/tagname>
```
Une el branch actual con el especificado
```ssh
	git merge <nameBranch>
```
Verifica cambios en el repositorio online con el local
```ssh
	git fetch
```
Borrar un archivo del repositorio
```ssh
	git rm <archivo> 
```

## Fork

Descargar remote de un fork
```
	git remote add upstream <url>
```

Merge con master de un fork
```
	git fetch upstream
	git merge upstream/master
```

## Patch
```
El comando git patch es una herramienta poderosa en Git que te permite crear y aplicar parches a tu código. Un parche, en este contexto, es un conjunto de cambios específicos que se pueden aplicar a un proyecto de manera aislada.

Principales usos:

Compartir cambios específicos: Si quieres compartir solo una parte de tus cambios con alguien más, puedes crear un parche y enviárselo.
Revisar cambios antes de integrarlos: Puedes aplicar un parche de forma experimental para ver cómo afecta a tu código antes de fusionarlo.
Revertir cambios: Puedes crear un parche para revertir cambios específicos y luego aplicarlo.
Integrar cambios de otros: Si alguien te envía un parche, puedes aplicarlo a tu repositorio para incorporar sus cambios.
¿Cómo se utiliza git patch?
Crear un parche:

Identifica los cambios: Decide qué cambios quieres incluir en el parche. Puedes usar git diff para ver las diferencias entre dos commits o entre tu directorio de trabajo y el último commit.

### Ejemplo de uso

git format-patch <commit_inicial>..<commit_final>

El comando anterior creará uno o más archivos .patch que contienen las diferencias entre los commits especificados.
Aplicar un parche:

1. Ubicar el parche: Asegúrate de tener el archivo .patch en el directorio donde quieres aplicar los cambios.
2. Aplicar el parche:
git apply <nombre_del_parche.patch>

Este comando aplicará los cambios del parche a tu directorio de trabajo.
Ejemplo:

Supongamos que quieres crear un parche para los cambios realizados entre los commits HEAD~2 y HEAD. Luego, quieres aplicar ese parche a una rama diferente:
# Crear el parche
git format-patch HEAD~2..HEAD

# Cambiar a la otra rama
git checkout otra_rama

# Aplicar el parche
git apply 0001-mis-cambios.patch

¿Para qué sirve el comando git patch?
El comando git patch es una herramienta poderosa en Git que te permite crear y aplicar parches a tu código. Un parche, en este contexto, es un conjunto de cambios específicos que se pueden aplicar a un proyecto de manera aislada.

Principales usos:

Compartir cambios específicos: Si quieres compartir solo una parte de tus cambios con alguien más, puedes crear un parche y enviárselo.
Revisar cambios antes de integrarlos: Puedes aplicar un parche de forma experimental para ver cómo afecta a tu código antes de fusionarlo.
Revertir cambios: Puedes crear un parche para revertir cambios específicos y luego aplicarlo.
Integrar cambios de otros: Si alguien te envía un parche, puedes aplicarlo a tu repositorio para incorporar sus cambios.
¿Cómo se utiliza git patch?
Crear un parche:

Identifica los cambios: Decide qué cambios quieres incluir en el parche. Puedes usar git diff para ver las diferencias entre dos commits o entre tu directorio de trabajo y el último commit.
Crea el parche:
Bash
git format-patch <commit_inicial>..<commit_final>
Usa el código con precaución.

Este comando creará uno o más archivos .patch que contienen las diferencias entre los commits especificados.
Aplicar un parche:

Ubicar el parche: Asegúrate de tener el archivo .patch en el directorio donde quieres aplicar los cambios.
Aplicar el parche:
Bash
git apply <nombre_del_parche.patch>
Usa el código con precaución.

Este comando aplicará los cambios del parche a tu directorio de trabajo.
Ejemplo:

Supongamos que quieres crear un parche para los cambios realizados entre los commits HEAD~2 y HEAD. Luego, quieres aplicar ese parche a una rama diferente:

Bash
# Crear el parche
git format-patch HEAD~2..HEAD

# Cambiar a la otra rama
git checkout otra_rama

# Aplicar el parche
git apply 0001-mis-cambios.patch
Usa el código con precaución.

Opciones adicionales:

git am: Este comando es similar a git apply, pero está diseñado para aplicar parches creados con git format-patch. Ofrece más opciones de manejo de conflictos y registro de los cambios aplicados.
git diff: Puedes usar git diff con la opción -p para generar un parche en formato unificado, que es más compatible con otras herramientas.
git apply --check: Esta opción te permite verificar si un parche se puede aplicar sin realizar cambios en tu directorio de trabajo.
Consideraciones importantes:

Conflictos: Si los cambios en el parche entran en conflicto con los cambios existentes en tu directorio de trabajo, git apply se detendrá y tendrás que resolver los conflictos manualmente.
Formatos de parche: Existen diferentes formatos de parche (unificado, contexto, etc.). Asegúrate de utilizar el formato correcto al crear y aplicar parches.
Herramientas de terceros: Existen herramientas de terceros que facilitan la creación y aplicación de parches, como patch.
En resumen:

El comando git patch es una herramienta versátil que te permite trabajar con cambios de manera granular. Ya sea para compartir código, revisar cambios o revertir modificaciones, los parches son una parte fundamental del flujo de trabajo de Git.


```

