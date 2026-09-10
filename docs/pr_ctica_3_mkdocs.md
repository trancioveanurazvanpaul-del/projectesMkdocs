# Práctica 3: MkDocs

## Aplicaciones Web

### 1. Modificación del fichero `index.md`

Modificamos el archivo `index.md` agregando nuestro contenido personalizado:

```markdown
# Pagin de razvan 2 asix
MkDocs
For full documentation visit [mkdocs.org](https://www.mkdocs.org).

## 2 asix

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs -h` - Print help message and exit.

## Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.
```

### 2. Edición del archivo de configuración `mkdocs.yml`

Editamos el archivo `mkdocs.yml` estableciendo nuestro nombre como nombre del sitio (`site_name`):

```yaml
site_name: Razavn TRancioveanu Paul
```

### 3. Previsualización con `mkdocs serve`

Ejecutamos el comando `mkdocs serve` para verificar que la página se visualiza correctamente de forma local desde la dirección que genera (ejemplo: `http://127.0.0.1:8000/`).

### 4. Generación de los archivos estáticos

Generamos los archivos estáticos del sitio web dentro de la carpeta `/site`:

```bash
(entornopython) razvan@razvan-VirtualBox:~/projecte$ mkdocs build
INFO    -  Cleaning site directory
INFO    -  Building documentation to directory: /home/razvan/projecte/site
INFO    -  Documentation built in 0.09 seconds
```

### 5. Configuración e Inicialización de Git

Configuramos el archivo `.gitignore` para omitir las carpetas generadas e inicializamos el repositorio Git:

```bash
(entornopython) razvan@razvan-VirtualBox:~/projecte$ echo -e ".venv/\nsite/" > .gitignore
(entornopython) razvan@razvan-VirtualBox:~/projecte$ git init
Inicializado repositorio Git vacío en /home/razvan/projecte/.git/
```

### 6. Despliegue en GitHub Pages

Lanzamos el comando `mkdocs gh-deploy` para publicar la documentación en GitHub:

```bash
(entornopython) razvan@razvan-VirtualBox:~/projecte$ mkdocs gh-deploy
INFO    -  Cleaning site directory
INFO    -  Building documentation to directory: /home/razvan/projecte/site
INFO    -  Documentation built in 0.45 seconds
```

Una vez completado el despliegue, el repositorio queda creado y publicado en GitHub (`trancioveanurazvanpaul-del / projectesMkdocs`).