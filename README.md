# AWS-S3-BUCKETS-OBJECTS
El objetivo de este repositorio es construir un Bucket con sus respectivos objetos


# S3

Nos posicionamos dentro de S3 y le damos a "Create bucket". 


1. Nombre: 

Debe ser un nombre único en todo AWS: 

```
demo-kaiet-s3-bucket-2022
```
2. Región: 

Lo suyo es escoger una región que está cerca de tí en nuesro caso
```
eu-west-1
```
Dejamos todas las demás configuraciones como tal. 


# Subida de archivos

Nos posicionamos en el bucket que acabamos de crear y le damos a 'Upload' y subimos un archivo cualqiera, puede ser desde un .txt a un .jpg. 

# Investigación de archivo: 

Una vez subido el archivo clickamos en el hiperlink del archivo mismo para que nos mande al archivo. 

1. ¿Qué pasa si queremos ver el archivo?

Por un lado òdemos ir al botón del 'Open' y este nos abrirta una ventana en el navegador con el archivo.
Por otro lado, podemos utilizar el 'Object Url', lo podemos copiar y pegarlo en una ventana del Chrome. SIn embargo, nos da un error de accesbilidad. Normal, porque el bucket en si no es público por lo que por URl no se puede acceder. 

Lo que pasa es que cuando hacemos el 'Open', estamos dando a AWS las crednciales temproales para que construya una URL por la que pme peuda acceder a la foto. 


# Creación de carpetas. 

Vamso a nuestro bucket recien creado y crearemos una carpeta: 
```
images
```
En  la misma carpeta creada también podemos subir archivos. Para ver los archios dentro de la carpeta tambien deberiamos de clickar en el hiperlink de la carpeta. 
La forma de abirr los archivos que están dentro de la carpeta es la misma qu econ los archivos normales. 

# Borrado de archivos/carpetas

Si borramos la carpeta teniendo unos archivos dentro nos posicionamos en la situación en la que vamos a borrar todos lso archivos que están dentro de la carpeta. 


:)
