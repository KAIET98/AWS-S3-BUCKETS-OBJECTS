# AWS-S3-BUCKETS-OBJECTS
El objetivo de este repositorio es construir un Bucket con sus respectivos objetos


# S3 (SIN VERSIONADO)

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


## Subida de archivos

Nos posicionamos en el bucket que acabamos de crear y le damos a 'Upload' y subimos un archivo cualqiera, puede ser desde un .txt a un .jpg. 

## Investigación de archivo: 

Una vez subido el archivo clickamos en el hiperlink del archivo mismo para que nos mande al archivo. 

1. ¿Qué pasa si queremos ver el archivo?

Por un lado òdemos ir al botón del 'Open' y este nos abrirta una ventana en el navegador con el archivo.
Por otro lado, podemos utilizar el 'Object Url', lo podemos copiar y pegarlo en una ventana del Chrome. SIn embargo, nos da un error de accesbilidad. Normal, porque el bucket en si no es público por lo que por URl no se puede acceder. 

Lo que pasa es que cuando hacemos el 'Open', estamos dando a AWS las crednciales temproales para que construya una URL por la que pme peuda acceder a la foto. 


## Creación de carpetas. 

Vamso a nuestro bucket recien creado y crearemos una carpeta: 
```
images
```
En  la misma carpeta creada también podemos subir archivos. Para ver los archios dentro de la carpeta tambien deberiamos de clickar en el hiperlink de la carpeta. 
La forma de abirr los archivos que están dentro de la carpeta es la misma qu econ los archivos normales. 

## Borrado de archivos/carpetas

Si borramos la carpeta teniendo unos archivos dentro nos posicionamos en la situación en la que vamos a borrar todos lso archivos que están dentro de la carpeta. 


# S3 (CON VERSIONADO)

Lo que haremos ahora va a ser activar el versionado del bucket que hemos creado.

1. Vamos al bucket
2. Properties
3. Bucket versioning > "Enable"

Nuestor bucket está listo para el versionado.

Vamos a nuestro Bucket y ahora veremos que tenemos una nueva característica que se llama "List Versions". Si activamos tendremos una nueva columna que se llama Version ID. El archivo viejo tendrá la caracter´sitica de "null".

Si subimos un nuevo fichero por ejempl, tendremos como dos caracterisitcas, un archivo previo al versionado con su respectiva version (null) y luego el archivo que acabamos d esubir con su version ( una string muy larga). Sin mebargo, si repetimos la subida del mismo segundo archivo otra vez y clicka mos en versiones, veremos que cuelga como una rama del primer archivo con una string muy larga. 

## Borrado de archivos versionados

Si borramos un archivo que tiene versionado, en si en si no nos borra el archivo, sino que nos marca un "Delete marker", con su id de versión. Es como que AWS le marca que estña como "borrado", pero sin estarlo. Para borrar de verdad, tenemos que seleccionarlo y borrarlo otra vez, es decir una estrategia de "permanently delete". Ahí sí que se borra.


## Quitado del versionado 

Si nos arrepentimos y queremos quitar el versionado. Los archivos viejos seguiran manteniendo sus versiones y tal pero en cuanto a los nuevos se hara un "overwrite". 



# Encryption

## Subiendo un archivo. 

Nos posicionamos en el bucket inicial y le damos a subir archivos. 

Al subir un nuevo archivo, antes de darle a "upload", vamos a ir a additional upload options, o algún lugar donde aparezca el encryption . 

Hay un apartado qued cie "Server-side encryption settings", por defecto aparecer aqu eno hay selecionado ningun encryption key, po rlo que le damos a "Specify an encryption key" y ya nos aparecen las opciones teóricas. Seleecionamos el 

```
Amazon S3-managed keys (SSE-S3)
```


Vamos a acceder al primer archivo que hemos subido, por ejemplo en mi caso va a ser coffee.jpg, ya sabemos que tenemos un hiperlink para acceder a ello. Entonces, como hagamos un "scroll- down", vamos a lelgar al encryption-side lo cual va a estar "disabled".

Por otro lado, vamos a asubir un segundo archivo pero en este caso, e nvez de seleccionar el 'Amazon S3-managed keys (SSE-S3)', seleccionaremos el: 

```
AWS Key Management Service key (SSE-KMS)
```

y seguidamente la opción de: 

```
AWS managed key (aws/s3)
```
Entonces, en este segundo archivo la encriptación sucedera cuando se le lalme por medio de la API. 

## El bucket entero

En vez de tener diferents tipos de ecnryptación para cada archivo lo que podemos hacer es desplegar uno entero para todo el bucket. Iriamos al "Properties" 
y en "Default encryption" elegiriamos el que quisieramos. 

:)
