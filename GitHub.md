# GitHub

- **Website**: [https://github.com](https://github.com/about)
- **Documentación**: [https://docs.github.com/en](https://docs.github.com/es)

## Introducción. ¿Qué es GitHub?

GitHub es un servicio en línea que permite a los desarrolladores colaborar en el código. A menudo se le conoce como un sitio web de programación social. Aquí tienes algunos puntos clave:

- **Hosting de Control de versiones** (Cloud Repository): GitHub se integra con Git, lo que le permite configurar repositorios remotos, enviar cambios y obtener actualizaciones.
- **Colaboración** (Collaborative Development): GitHub proporciona herramientas para rastrear cambios, asignar problemas e implementar código, lo que facilita que los equipos trabajen juntos.
- **Gestión de proyectos** (Project Management): incluye herramientas de gestión de proyectos como tableros Kanban para organizar proyectos de desarrollo.

Esto hace de GitHub una plataforma poderosa para administrar y colaborar en proyectos de desarrollo.

- Hosting de Control de versiones[^1]

  - Setup de repositorios remotos / Clonar (Clone)
  - Publicando (Push): Enviar cambios
  - Obteniendo (Pull): Obtener actualizaciones = fetch + merge
    - Ramas remotas
  - Tags
    - Enviar/recibir Tags al/del remoto
  - Forks

- Colaboración en Github

  - Pull Request
    - Configuración de las rama main: Protección de ramas
    - Revisión de código
    - Actualización desde las ramas feature
  - Pull request desde forks
  - Pull request desde GitHub
  - Tags y Releases
  - Markdown + Markdown GitHub Addons (GFM = GitHub Flavored Markdown)

- Gestión de proyectos en GitHub

  - Issues
    - Etiquetas (Labels)
    - Asignación (Assignees)
    - Milestones
    - Templates
  - Proyectos (Projects)
    - Tableros Kanban
    - Automatización
  - Repository Insights
    - Pulse
    - Contributors
    - Commits
    - Code frequency
    - Dependency graph
    - Network
    - Forks

- GitHub social

  - Seguidores (Followers)
  - Estrellas (Stars)
  - Discusiones (Discussions)
  - Watchers - Notificaciones (Notifications)
  - Gists
  - Wikis
  - Pages

- Github Actions
  - Introducción
  - Workflow. Partes y sintaxis
  - Configuración y ejecución de un workflow
  - Construir la imagen con Docker
  - Secretos

[^1]: GitHub utiliza Git como sistema de control de versiones, pero también soporta otros sistemas como Subversion (SVN) a través de una capa de compatibilidad.

## Archivos esenciales del repositorio

- Archivo README : Funciona como la página principal de tu repositorio, explicando la función del proyecto y su utilidad. Puede ubicarse en la raíz, en la carpeta docs o en .github.
- Archivo de licencia : Define cómo los desarrolladores pueden usar, modificar y distribuir el software. Debe estar en la carpeta raíz.
  Código de conducta : Establece el comportamiento esperado de los colaboradores. GitHub proporciona plantillas para ello.
- Política de seguridad : Especifica el soporte de seguridad y dónde reportar vulnerabilidades. Puede ubicarse en la raíz, en la carpeta docs o en .github.
- Contributing.md : proporciona pautas sobre cómo contribuir al proyecto, incluidas las contribuciones aceptadas y los pasos para crear problemas.
- Support.md : Informa a los usuarios sobre cómo obtener soporte para el proyecto. Puede ubicarse en la raíz, en la carpeta de documentación o en la carpeta .github.
- Archivo CODEOWNERS : enumera a los individuos responsables de un código específico en el repositorio, garantizando que sean notificados de los cambios y las solicitudes de extracción.

Estos archivos ayudan a organizar y administrar su repositorio de manera efectiva, lo que hace que sea más fácil para otros comprender, contribuir y usar su proyecto.

## GitHub CLI

- **Website**: [https://cli.github.com/](https://cli.github.com/)
- **Documentación**: [https://cli.github.com/manual/](https://cli.github

Instalamos la aplicación descargada desde la web oficial y comprobamos la instalación con el comando

```shell
gh --version
```

Si estaba abierto Visual Studio Code, es necesario reiniciarlo para que detecte el nuevo comando gh en el path del sistema.

Ejecutamos el comando `gh auth login`, para iniciar sesión con nuestra cuenta en GitHub, y seguimos las instrucciones directamente desde la aplicación de consola, donde nos preguntará

- si queremos utilizar nuestro GitHub.com o
- cuál es nuestro protocolo preferido para las operaciones de Git, HTTPS o SSH
- si queremos autenticar Git con nuestras credenciales de GitHub.
- cómo queremos autenticar GitHub CLI, con el navegador o con un token de acceso personal.

```shell
gh auth login
? Where do you use GitHub?  [Use arrows to move, type to filter]
> GitHub.com
  Other
? What is your preferred protocol for Git operations?  [Use arrows to move, type to filter]
> HTTPS
  SSH
? Authenticate Git with your GitHub credentials?  [Use arrows to move, type to filter]
> Yes
  No
? How would you like to authenticate GitHub CLI?  [Use arrows to move, type to filter]

```

Si Elegimos iniciar sesión con el navegador, nos proporcionará una URL para abrir en el navegador y un código de dispositivo de un solo uso que debemos copiar. Abrimos el navegador en la URL proporcionada y luego pegamos el código que copiamos anteriormente y presionamos continuar.
Si aún no lo habíamos hecho, iniciaremos sesión con nuestro nombre de usuario y contraseña de GitHub y autorizaremos a GitHub CLI para acceder a nuestra cuenta de GitHub.

Ahora que hemos hecho eso, volveremos a la aplicación de consola, donde después de un tiempo, recibirás la confirmación de que has iniciado sesión correctamente.

Solo para probar que todo funcionó, ejecuta el comando `gh repo list`. Deberías ver la lista de tus propios repositorios de GitHub, y si tienes muchos, puedes limitar el número de resultados con la opción --limit, por ejemplo:

```shell
gh repo list --limit 5
```

(Por defecto el valor de --limit es 30 )

### Crear un repositorio

Eel comando `gh repo create` permite crear un nuevo repositorio en GitHub. Puedes seguir un asistente interactivo para configurar el repositorio con la configuración que desees.

- Asistente interactivo : Al ejecutar gh repo create sin argumentos, se inicia un asistente que te guía a través de las opciones para crear el repositorio, como el nombre, la visibilidad (público o privado) y si deseas clonarlo localmente.

Las opciones de comando permiten hacerlo de forma no interactiva, indicando los valores deseados directamente en la línea de comandos. Por ejemplo, puedes usar --public o --private para establecer la visibilidad del repositorio, y --clone para clonarlo localmente después de crearlo.

- Ejemplo de creación rápida : Para crear un repositorio público llamado my-new-repo y clonarlo localmente, puedes usar el siguiente comando:

```shell
gh repo create my-new-repo --public --clone
```

Comandos alternativos : También puedes crear un repositorio desde tu directorio local usando comandos como `gh repo create another-project --private --source=.`

Esto creará un repositorio privado llamado another-project en GitHub y lo vinculará al directorio actual.

Entre los comandos del CLI de GitHub para manejar repositorios, también están los siguientes:

- `gh repo clone <repository>` : Clona un repositorio existente de GitHub a tu máquina local.
- `gh repo fork <repository>` : Crea un fork de un repositorio existente en tu cuenta de GitHub.
- `gh repo view <repository>` : Muestra información detallada sobre un repositorio específico
- `gh repo delete <repository>` : Elimina un repositorio existente de tu cuenta de GitHub.
- `gh repo list [<owner>]` : Lista los repositorios de un usuario u organización específica.
- `gh repo rename <repository> <new-name>` : Cambia el nombre de un repositorio existente en tu cuenta de GitHub.
- `gh repo archive <repository>` : Archiva un repositorio existente en tu cuenta de GitHub, haciéndolo de solo lectura.
- `gh repo unarchive <repository>` : Desarchiva un repositorio previamente archivado en tu cuenta de GitHub, restaurando su estado activo.
- `gh repo transfer <repository> <new-owner>` : Transfiere la propiedad de un repositorio a otro usuario u organización en GitHub.
- `gh repo list --visibility <visibility>` : Filtra los repositorios listados por su visibilidad (público, privado o interno).

## Otros comandos

CORE COMMANDS

- browse: Open repositories, issues, pull requests, and more in the browser
- codespace: Connect to and manage codespaces
- gist: Manage gists
- issue: Manage issues
- org: Manage organizations
- pr: Manage pull requests
- project: Work with GitHub Projects.
- release: Manage releases

GITHUB ACTIONS COMMANDS

- cache: Manage GitHub Actions caches
- run: View details about workflow runs
- workflow: View details about GitHub Actions workflows

## GITHUB PAGES

GitHub Pages es un servicio de alojamiento web estático que ofrece GitHub para publicar sitios web directamente desde un repositorio de GitHub. Es una forma sencilla y gratuita de alojar páginas web personales, blogs, documentación de proyectos y sitios web de organizaciones.

Podemos encontrar muchos ejemplos de sitios web creados con GitHub Pages en la [página de ejemplos](https://github.com/collections/github-pages-examples) de GitHub.

### Características principales de GitHub Pages

- **Fácil de usar**: Puedes crear y publicar un sitio web con solo unos pocos clics desde la interfaz de GitHub.
- **Integración con GitHub**: Los sitios web se generan directamente desde los archivos en tu repositorio, lo que facilita la actualización y el mantenimiento del contenido.
- **Soporte para Jekyll**: GitHub Pages tiene soporte integrado para Jekyll, un generador de sitios estáticos que permite crear sitios web a partir de archivos Markdown y plantillas.
- **Personalización de dominios**: Puedes usar un dominio personalizado para tu sitio web de GitHub Pages.
- **HTTPS**: GitHub Pages ofrece soporte para HTTPS, lo que garantiza que tu sitio web sea seguro.
- **Gratuito**: GitHub Pages es un servicio gratuito, lo que lo hace accesible para desarrolladores y proyectos de código abierto.

### Cómo crear un sitio web con GitHub Pages

1. **Crear un repositorio**: Crea un nuevo repositorio en GitHub o usa uno existente.
2. **Agregar contenido**: Agrega los archivos HTML, CSS, JavaScript o Markdown que deseas publicar en tu sitio web. Si usas Jekyll, puedes agregar archivos Markdown y plantillas. Puedes incluir el contenido en una rama especifica, en la raíz del repositorio (root) o en una carpeta llamada `docs`.
3. **Configurar GitHub Pages**: Ve a la configuración del repositorio, desplázate hacia abajo hasta la sección "GitHub Pages" y selecciona la rama y la carpeta desde la que deseas publicar tu sitio web (por ejemplo, la rama `main` y la carpeta `/root` o `/docs`). Otra alternativa que aparece en la configuración en utilizar una gitHub Action para publicar el sitio web. Por defecto aparece la action de Jekyll o la apropiada según el contenido del repositorio (Next.js, Gatsby, Astro...).
4. **Publicar el sitio web**: Una vez que hayas configurado GitHub Pages, GitHub generará automáticamente tu sitio web y te proporcionará una URL para acceder a él (por ejemplo, `https://tu-usuario.github.io/tu-repositorio`).
5. **Personalizar el dominio (opcional)**: Si deseas usar un dominio personalizado, puedes configurar un archivo `CNAME` en tu repositorio con el nombre de tu dominio y actualizar la configuración de DNS en tu proveedor de dominio.
6. **Actualizar el contenido**: Para actualizar tu sitio web, simplemente realiza cambios en los archivos de tu repositorio y haz un commit. GitHub Pages regenerará automáticamente tu sitio web con los cambios.

### Sitios Web y GitHub Pages

Los generadores de sitios web estáticos como Jekyll, Hugo, Gatsby, Next.js y otros pueden integrarse fácilmente con GitHub Pages para publicar sitios web. Aquí hay algunos ejemplos:

- **Jekyll**: Jekyll es el generador de sitios estáticos predeterminado para GitHub Pages. Puedes crear un sitio web con Jekyll y publicarlo directamente desde tu repositorio de GitHub.
- **Hugo**: Hugo es otro generador de sitios estáticos popular que puedes usar para crear sitios web y publicarlos en GitHub Pages.
- **Gatsby**: Gatsby es un generador de sitios web basado en React que también puede integrarse con GitHub Pages para publicar sitios web.
- **Next.js**: Next.js es un framework de React que permite la generación de sitios estáticos y puede usarse para crear sitios web que se publiquen en GitHub Pages.
- **Astro**: Astro es un moderno generador de sitios estáticos que soporta múltiples frameworks y puede integrarse con GitHub Pages para publicar sitios web.
- **Otros generadores**: Otros generadores de sitios estáticos como Eleventy, VuePress, Docusaurus y más también pueden integrarse con GitHub Pages para publicar sitios web.

Para crear un sitio con Astro y publicarlo en GitHub Pages, puedes seguir estos pasos:

1. **Crear un nuevo proyecto Astro**: Si no tienes Astro instalado, primero instala Node.js y luego ejecuta el siguiente comando para crear un nuevo proyecto Astro:

   ```bash
   npm create astro@latest
   ```

   Sigue las instrucciones para configurar tu proyecto.

2. **Desarrollar tu sitio web**: Navega al directorio de tu proyecto y comienza a desarrollar tu sitio web utilizando Astro. Puedes agregar páginas, componentes y estilos según tus necesidades.

   ```bash
   cd nombre-de-tu-proyecto (e.g. demo-astro-indra)
   npm install
   npm run dev
   ```

   Esto iniciará un servidor de desarrollo y podrás ver tu sitio web en `http://localhost:3000`.

3. **Configurar la publicación en GitHub Pages**: Para publicar tu sitio web en GitHub Pages, necesitas configurar tu proyecto Astro para que genere los archivos estáticos en una carpeta específica. Abre el archivo `astro.config.mjs` y agrega o modifica la configuración de salida:

   ```javascript
   export default {
     output: "static",
     site: "https://alce65.github.io",
     base: "/demo-astro-indra",
     outDir: "./docs",
     build: {
       assets: "assets", // Cambia _astro por assets para GitHub Pages
     },
     // Otras configuraciones...
   };
   ```

    Así la carpeta de salida esté configurada correctamente. Por defecto, Astro genera los archivos estáticos en la carpeta `dist`, pero lo hemos cambiado a `docs` para que GitHub Pages pueda servirlos directamente desde allí.

    Luego, construye tu proyecto para generar los archivos estáticos:

    ```bash
    npm run build
    ```

    Esto generará los archivos estáticos en la carpeta `docs`.

    Dentro de la aplicación, los url a las páginas y recursos deben ser relativos, para que funcionen correctamente cuando se publiquen en GitHub Pages, incluyendo la base URL. Para ello podemos usar la variable `import.meta.env.BASE_URL` que Astro proporciona para manejar la base URL. Asegúrate de que todos los enlaces y rutas en tu sitio web sean relativos y no absolutos.

    Por ejemplo, si tienes una página llamada `about.astro`, el enlace a esa página debería ser `${import.meta.env.BASE_URL}/about` en lugar de una ruta absoluta.

4. **Crear un repositorio en GitHub**: Crea un nuevo repositorio en GitHub donde alojarás tu sitio web. Puedes hacerlo desde la interfaz web de GitHub.

5. **Agregar tu proyecto al repositorio**: Inicializa un repositorio Git en tu proyecto Astro, agrega los archivos y haz un commit:

   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   ```

   Luego, agrega el repositorio remoto de GitHub y empuja tus cambios:

   ```bash
   git remote add origin <URL_DEL_REPOSITORIO>
   git branch -M main
   git push -u origin main
   ```

6. **Configurar GitHub Pages**: Ve a la configuración de tu repositorio en GitHub, desplázate hasta la sección "GitHub Pages" y selecciona la rama `main` y la carpeta `/docs` como fuente para GitHub Pages. Guarda los cambios.

7. **Publicar el sitio web**: GitHub generará automáticamente tu sitio web y te proporcionará una URL para acceder a él (por ejemplo, `https://tu-usuario.github.io/tu-repositorio`).


Para más información sobre el despliegue de Astro en GitHub Pages, puedes consultar la [documentación oficial de Astro](https://docs.astro.build/en/guides/deploy/github/).
