# GitBookDocumentacion

> ⚠️ leer documentación official [documentación](https://www.npmjs.com/package/gitbook)

## Cómo usarlo:

GitBook se puede instalar desde NPM usando:

```bash
$ npm install gitbook-cli -g
```

Cree los directorios y archivos para un libro desde su archivo **SUMMMARY.md** (si existe) usando

```bash
$ gitbook init
```

Puede servir un repositorio como libro usando:

```bash
$ gitbook serve
```

O simplemente construya el sitio web estático usando:

```bash
$ gitbook build
```

## Formatos de salida

GitBook puede generar su libro en los siguientes formatos:

* **Sitio web estático:** este es el formato predeterminado. Genera un sitio web estático interactivo completo que puede, por ejemplo, alojarse en páginas GitHub.
  
* **eBook:** necesita tener instalado ebook-convert. Puede especificar el nombre de archivo del libro electrónico como segundo argumento; de lo contrario, se utilizará el libro.
  
    * Genere un PDF usando: `gitbook pdf ./myrepo ./mybook.pdf`
    * Genere un ePub usando: `gitbook epub ./myrepo ./mybook.epub`
    * Genere un MOBI usando: `gitbook mobi ./myrepo ./mybook.mobi`
    * 
* **JSON:** este formato se utiliza para depurar o extraer metadatos de un libro. Genere este formato usando: `gitbook build ./myrepo --format = json`

## Formato de libro

Un libro es un repositorio de Git que contiene al menos 2 archivos: README.md y SUMMARY.md.

### README.md

Por lo general, esta debería ser la introducción de su libro. Se agregará automáticamente al resumen final.

### SUMMARY.md

SUMMARY.md define la estructura de su libro. Debe contener una lista de capítulos, con enlaces a sus respectivas páginas.

Ejemplo:

```markdown
### Summary
 
This is the summary of my book.
 
* [section 1](section1/README.md)
    * [example 1](section1/example1.md)
    * [example 2](section1/example2.md)
* [section 2](section2/README.md)
    * [example 1](section2/example1.md)
```

Los archivos que no están incluidos en SUMMARY.md no serán procesados por gitbook.

### Múltiples lenguajes

GitBook admite la creación de libros escritos en varios idiomas. Cada idioma debe ser un subdirectorio que siga el formato normal de GitBook, y un archivo llamado LANGS.md debe estar presente en la raíz del repositorio con el siguiente formato:

```markdown
* [English](en/)
* [French](fr/)
* [Español](es/)
```

### Cover

Se puede establecer una imagen de portada creando un archivo: **/cover.jpg**. La mejor resolución es **1800x2360**. La generación de la portada se puede hacer automáticamente usando el complemento **autocover**.

También se puede establecer una versión pequeña de la portada creando un archivo: **/cover_small.jpg**.