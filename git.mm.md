# Git y GitHub
## Introducción
- **Git**
  - Software de control de versiones creado por **Linus Torvalds**.
  - Permite llevar el control de cambios en los archivos de un repositorio.
- **GitHub**
  - Servicio para alojar repositorios Git en un servidor remoto.
  - Facilita la colaboración y el almacenamiento en la nube.

## Instalación y Configuración
- **Instalación de Git**
  - Comando para instalar en distribuciones basadas en Debian:
    - `$ apt install git`
- **Configuración inicial**
  - Configurar nombre de usuario y correo:
    - `git config --global user.name "Nombre"`
    - `git config --global user.email "email@example.com"`

## Uso básico de Git
- **Crear un repositorio**
  - Crear un nuevo directorio:
    - `$ mkdir curso-de-git`
  - Inicializar el repositorio:
    - `$ git init`
    - Se crea el directorio `.git` donde se almacena la configuración del repositorio.
- **Añadir y confirmar cambios**
  - Crear un archivo y añadirlo al repositorio:
    - `echo "Esto es una prueba" > ejemplo.txt`
    - `git add ejemplo.txt`
  - Confirmar los cambios con un mensaje:
    - `git commit -m "He creado el archivo ejemplo.txt"`

## Operaciones comunes
- **Modificación de archivos**
  - Después de modificar un archivo, confirmar los cambios:
    - `git commit -am "He modificado el archivo ejemplo.txt"`
- **Renombrar o eliminar archivos**
  - Cambiar nombre:
    - `git mv ejemplo.txt ejemplo2.txt`
  - Eliminar un archivo:
    - `git rm ejemplo2.txt`
  - Confirmar los cambios:
    - `git commit -am "He renombrado/eliminado el archivo"`

## Volver a versiones anteriores
- **Revertir cambios**
  - Volver a un commit anterior sin perder cambios posteriores:
    - `git checkout <id del commit>`
  - Volver a la última versión:
    - `git switch -`
  - Eliminar los últimos 3 commits de manera irreversible:
    - `git reset --hard HEAD~3`

## Sincronización con GitHub
- **Subir cambios**
  - Subir cambios del repositorio local al remoto:
    - `git push`
- **Descargar cambios**
  - Descargar los últimos cambios del repositorio remoto al local:
    - `git pull`

## Trabajar con ramas
- **Crear y cambiar de rama**
  - Crear una nueva rama para trabajar en paralelo sin afectar la principal:
    - `git branch [rama]`
  - Cambiar a la nueva rama:
    - `git checkout [rama]`
- **Unir ramas**
  - Fusionar una rama con la principal (normalmente `main`):
    - `git merge [rama]`
- **Eliminar ramas**
  - Después de fusionar, se puede eliminar la rama:
    - `git branch -d [rama]`

## Conflictos
- **Cuándo ocurren los conflictos**
  - Los conflictos surgen cuando dos ramas modifican la misma parte de un archivo.
  - Git no puede decidir qué cambios mantener y necesita intervención manual.
- **Resolución de conflictos**
  - Git marca las diferencias en el archivo:
    - `<<<<<<< HEAD` (código actual)
    - `=======` (separador)
    - `>>>>>>> nuevo` (código de la otra rama)
  - El desarrollador debe resolver el conflicto editando el archivo.
  - Luego, se añaden y confirman los cambios:
    - `git add archivo_resuelto`
    - `git commit -m "Resuelto conflicto en archivo_resuelto"`

## Pull Request (PR)
- **Colaborar en proyectos**
  - Crear un fork (copia) de un repositorio de terceros en GitHub.
  - Hacer cambios en una rama y solicitar que el propietario los fusione.
  - Crear un PR desde GitHub para que el propietario revise los cambios.
  - El propietario decide si acepta o rechaza el PR.
