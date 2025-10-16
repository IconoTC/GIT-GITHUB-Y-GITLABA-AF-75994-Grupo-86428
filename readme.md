# Curso de Git

- GIT, GITHUB Y GITLAB AF 75994 – Grupo 86428
- Duración: 25 horas
- Modalidad: On-line
- Fechas: 13, 14 , 15, 16 y 17 de Octubre 2025
- Horario 9:00 – 14:00 hs

Formador: Alejandro Cerezo
<alce65@hotmail.es>

## Contenidos

- Introducción
  - Instalación y configuración de git
  - Gestión de un repositorio
    - Quick Start
    - Aprendiendo a referenciar revisiones y paths
    - Herramientas para preparar un buen commit en cualquier situación
  - GUI’s (Integración con otras herramientas y entornos)
    - Github
    - GitLab
  - Reescribiendo la historia
- Ramas (Trabajando en paralelo)
  - Ramificación
  - Fusión de Ramas
  - Resolviendo Problemas
  - Tipos de Ramas
  - Tags
- Buenas prácticas
  - Reorganización
  - Regla de Oro
  - Forzar subida
- Colaboración en Github
  - Ramas remotas
  - Publicando
  - Tags
  - Pull Request
  - Liberaciones (releases)
- GitFlow
  - Introducción
  - Features
  - Releases
  - Hotfix
- Git hooks
- Github Actions
  - Introducción
  - Workflow. Partes y sintaxis
  - Configuración y ejecución de un workflow
  - Construir la imagen con Docker
  - Secretos
- GitLab
  - Introducción
  - Versiones
  - Funcionalidades
  - Arquitectura
  - Usuarios
  - Repositorios
  - Ramas
  - Merge Request
  - Pipelines

Desarrollo del curso en la carpeta Oficial -> [repo](https://github.com/IconoTC/GIT-GITHUB-Y-GITLABA-AF-75994-Grupo-86428)

## Desarrollo del curso

### Día 1 (Lunes 13 Octubre 2025)

- Presentación profesor / alumnos
- Introducción: Qué es un SCV y qué un SCV distribuido
- IDE / Editor de código: Visual Studio Code (VSC)
- Instalación de Git
- Terminales
  Configuración inicial
- Primeros pasos con Git
  - Primer repo (init), primer commit
  - Anatomía de un repositorio git: working directory, staging area (index o cache) y repositorio (.git)
  - Estados de un archivo: untracked (U), tracked (modified (M), staged (A), committed)
  - add/commit/reset y status/log/show
  - Mensajes de commit
- Anatomía de comandos típicos, referencias VS paths

  - HEAD, master, HEAD~1 y otras referencias útiles
  - Referencias por mensaje de commit (:/cadena)

- [Descanso]

- Integración con otras herramientas y entornos
  - Clientes gráficos
  - Entornos de desarrollo
  - Repositorios remotos: GitHub, GitLab, Bitbucket
    - remotes -> push / pull
    - Clonar un repositorio: clone
- Comprobar el repositorio.
  - git log
  - git show
  - git diff
- Aliases
  - Qué son
  - Cómo crearlos desde el CLI: `git config --global alias.co checkout`
  - Crearlos editando el fichero de configuración: `git config --global -e`
- Ficheros Markdown
  - Qué son
  - Sintaxis básica
  - Vista previa en VSC / GitHub / GitLab

### Día 2 (Martes 14 Octubre 2025)

- Git internals
  - Estructura de un repositorio git: .git
  - Objetos git: blobs, trees, commits (y tags)
    - Creación y lectura de objetos
    - Creación del árbol de objetos en un primer commit
    - Modificación del árbol de objetos en commits sucesivos
  - Referencias: heads, ramas (tags y remotes)
  - Taller: creación de un repositorio git "a mano"
- Herramientas para preparar un buen commit en cualquier situación

  - Operaciones en la Staging Area (Index)
    - Añadir ficheros
    - Eliminar de la Staging Area (Index)
  - Eliminar ficheros: git rm
    - Problemas con .gitignore
  - Cambiar nombre de ficheros: git mv
  - git blame
  - Recapitulando: Git básico

- [Descanso]

- Reescribiendo la historia
  - Advertencia
  - git command --amend
    - Ref logs
  - git checkout
  - git reset
  - Evolución de git checkout: Nuevos comandos git switch y git restore
  - git checkout a nivel de archivo (restore)
  - git reset a nivel de archivo

### Día 3 (Miércoles 15 Octubre 2025)

- Reescribiendo la historia (2)
  - rebase interactivo
    - edit: modificando un commit
    - squash y fixup: fusionando commits
    - drop: eliminando un commit
- Otros comandos

  - git clean
  - git revert
  - git bisect

- Trabajando en paralelo

  - Ramas
    - Crear y seleccionar
      - Crear desde referencia
    - Ver ramas
    - Borrar ramas
    - Mover y renombrar ramas
  - Combinación de ramas: Merge y Rebase
    - git merge
      - fast-forward
      - three-way merge
    - git rebase

- [Descanso]

- Trabajando en paralelo (2)

  - git stash
  - Resolución de conflictos
  - git cherry-pick

- Etiquetas (tags)
  - Tags anotadas y tags ligeros
  - Crear, listar, eliminar
- Worktrees
- Patches
  - Creación
  - Aplicación

### Día 4 (Jueves 16 Octubre 2025)

- Repositorios remotos

  - Repositorios "bare"
  - Clonar repositorios: git clone
  - git remote
  - git push
    - push tags
  - git pull

    - git fetch
    - git merge / git rebase
    - Conflictos

  - Ramas remotas
    - Seguimiento de ramas remotas (tracking branches)
    - Crear ramas locales a partir de ramas remotas: fetch + checkout / switch -c
    - Subir ramas locales a ramas remotas
    - Eliminar ramas remotas
  - Pull requests (GitHub) / Merge requests (GitLab)
    - Flujo de trabajo típico
    - Revisión de código
    - Resolución de conflictos en remoto
    - Buenas prácticas:
      - Actualizar la rama con la rama main antes de hacer el merge
      - Resolución de conflictos en local
      - Eliminar la rama una vez hecho el merge

- [Descanso]

- Flujos de trabajo (workflows)

  - Git Flow
  - GitLab Flow
  - GitHub Flow
    - Ship-Show-Ask
  
- Buenas prácticas

<!--
- GitHub
  - Hosting de Repositorios
    - repositorios públicos y privados; ramas y remotos: push y pull (v.s.)
    - forks
  - Colaboración
    - pull requests: revisión de código y comentarios (v.s.)
    - PR desde ramas y forks
    - Proyectos
      - Tableros (Boards)
      - issues y proyectos; milestones
    - Wikis
    - Gists
  -->

<!-- ### Día 5 (Jueves 17 Octubre 2025)

- GitHub (continuación)
  - Integración continua / Entrega continua (CI/CD)
    - GitHub Pages
    - GitHub Actions
      - Introducción
      - Workflow. Partes y sintaxis
      - Configuración y ejecución de un workflow
      - Secretos
    - tags y releases
- GitLab
  - Similitudes y diferencias con GitHub
  - Merge Request
  - CI/CD en GitLab
    - Introducción a CI/CD
    - Configuración de un pipeline: stages y jobs
    - Artefactos
    - Variables -->
