# Ejercicios básicos de MS-DOS

## Ejercicio 1

#### 1. Crea la siguiente estructura de carpetas
El comando que utilizaremos para crear la carpeta raíz será ``md carp_d``, ligeramente diferente para los subdirectorios, que se hará a partir de la ruta, 
``md carp_d\apli`` por ejemplo

<img width="146" alt="2022-03-23" src="https://user-images.githubusercontent.com/91699247/160212135-c2e9a9db-3acf-4210-9b28-cf34717c2e53.png">


#### 2. Sitúate en la carpeta TABLAS
```
cd apli\excel\tablas  
```


#### 3. Vuelve a la carpeta raíz
```
cd ..\..\..
```


#### 4. Muestra el contenido de la carpeta PROG
```
tree prog
```


#### 5. Borra la carpeta PASCAL
```
rd prog\pascal
```


#### 6. Sitúate en la carpeta VARIOS y desde allí crea una nueva carpeta dentro de WORD llamado PRACT
```
cd varios
md ..\apli\word\pract
```


#### 7. Sitúate en PRACT y desde allí muestra el contenido de la carpeta EXCEL
```
cd apli\word\pract
tree ..\..\excel
```


#### 8. Desde TABLAS muestra el listado de archivos y carpetas de la carpeta raíz
```
cd apli\excel\tablas
tree ..\..\..
```


#### 9. Sitúate en la carpeta APLI y desde allí crea una subcarpeta llamada AGENDA dentro de VARIOS
```
cd apli
md ..\varios\agenda
```


#### 10. Borra la carpeta EXCEL
```
rd apli\excel
```


#### 11. Desde la carpeta raíz, crea en ella una subcarpeta llamada NUEVO
```
md nuevo
```


#### 12. Desde PRACT muestra el contenido de WORD
```
cd apli\word\pract
tree ..\
```




## Ejercicio 2

#### 1. Utilizando el editor de textos de MS-DOS, crea un archivo de texto denominado EJER.TXT, con el siguiente contenido, y almacénalo dentro de la carpeta TEXTOS
Abrimos el editor con el comando ``edit``, se pega el  contenido y se guarda como ejer.txt.

Para almacenarlo en TEXTOS utilizaremos 
```
move ejer.txt apli\word\textos
```


#### 2. Copia el archivo EJER.TXT en AGENDA
```
copy apli\word\textos\ejer.txt varios\agenda
```


#### 3. Borra el archivo almacenado en la carpeta TEXTOS
```
del apli\word\textos\ejer.txt
```


#### 4. Añade el siguiente párrafo al archivo EJER.TXT
Abrimos el archivo en el editor situándonos previamente en la ruta donde se encuentra el ejer.txt `` cd varios\agenda`` 
```
edit ejer.txt
```   
Añadimos el párrafo y lo guardamos.


#### 5. Copia el archivo EJER.TXT en la carpeta BASIC
```
copy varios\agenda\ejer.txt basic
```


#### 6. Cambia el nombre del archivo almacenado en AGENDA por FICHERO.TXT
```
ren varios\agenda\ejer.txt
NewName:fichero.txt
```


#### 7. Mueve el archivo FICHERO.TXT a la carpeta BASIC
```
move varios\agenda\fichero.txt basic
```


#### 8. Abre el archivo EJER.TXT y borra la primera frase; almacena el nuevo archivo con el nombre NUEVO.TXT dentro de la carpeta BASIC
Para abrirlo, nos situamos en la ruta donde se encuentra `` cd apli\word\textos`` , borramos la primera frase, lo guardamos como nuevo.txt y lo almacenamos en la carpeta basic mediante el comando 
```
mv nuevo.txt ..\..\..\prog/basic
```

#### 9. Copia el archivo NUEVO.TXT en la carpeta NOTAS
```
copy basic\nuevo.txt apli\word\notas
```


#### 10. ¿Cuántos archivos hay en la carpeta BASIC? ¿Y en NOTAS?
Para ver cuantos archivos hay en estas carpetas, podemos ver el árbol de la carpeta raíz con un ``tree`` y veremos que basic tiene 3 archivos y notas 1.



## Ejercicio 3

#### 1. Borra la carpeta ACCESS y en su lugar crea una nueva carpeta llamada ASTRO
```
rd apli\access
md apli\astro
```


#### 2. Crea la siguiente estructura de subcarpetas dentro de la carpeta ASTRO
Una vez situados en la ruta indicada ``cd apli\astro`` , el comando necesario es ``md`` , ya sea para la creación del directorio ``md historia`` o para la de los subdirectorios ``md historia\datos1``  
<img width="132" alt="2022-03-25" src="https://user-images.githubusercontent.com/91699247/160212789-0ebc6d31-872c-43f9-a4ce-98cfe674884f.png">



#### 3. Sitúate en la carpeta CIENCIA y desde allí muestra el listado de archivos y subcarpetas de la carpeta HISTORIA
```
cd apli\astro\ciencia
tree ..\historia
```


#### 4. Utilizando el editor de MS-DOS crea el siguiente archivo de texto y guárdalo con el nombre TYCHO.TXT dentro de la carpeta DATOS1
Nos situamos en la ruta especificada ``cd apli\astro\historia\datos1 `` , abrimos el editor con el comando ``edit``, insertamos el texto y lo guardamos como tycho.txt


#### 5. Utilizando de nuevo el editor de textos de MS-DOS crea el siguiente archivo de texto, y guárdalo con el nombre KEPLER.TXT dentro de la carpeta DATOS2
Siguiendo el proceso del apartado anterior, nos dirigmos a la ruta ``cd apli\astro\historia\datos2 `` , abrimos el editor y guardamos el archivo con el texto como kepler.txt .


#### 6. Copia los archivos TYCHO.TXT y KEPLER.TXT en la carpeta CIENCIA

```
copy apli\astro\historia\datos1\tycho.txt apli\astro\ciencia
copy apli\astro\historia\datos2\kepler.txt apli\astro\ciencia
```


#### 7. Cambia de lugar los archivos almacenados en DATOS1 y DATOS2 de forma que TYCHO.TXT quede guardado dentro DATOS2 y KEPLER.TXT en DATOS1
```
move apli\astro\historia\datos1\tycho.txt apli\astro\historia\datos2
move apli\astro\historia\datos2\kepler.txt apli\astro\historia\datos1
```


#### 8. Crea un nuevo archivo formado por la unión de los dos anteriores (sin volver a escribir el texto) y guárdalo dentro de la carpeta HISTORIA con el nombre TOTAL.TXT
```
for %f in (*.txt) do type "%f" >> total.txt
move total.txt ../apli/astro/historia
```


#### 9. Abre el archivo KEPLER.TXT almacenado en la carpeta CIENCIA y añade el siguiente texto
Vamos a la ruta donde se encuentra el archivo ``cd\apli\astro\ciencia``, ahora abrimos el archivo con ``edit kepler.txt`` y guardamos el archivo con el texto añadido.


#### 10. Cambia el nombre del archivo anterior por el de GALILEO.TXT
```
ren apli\astro\ciencia\kepler.txt
NewName: galileo.txt
```





## Ejercicio 4

#### 1. Crea en la carpeta raíz de la unidad A: una carpeta denominada TECINFO
Despúes de cambiarnos a la unidad A, para crear la carpeta ejecutaremos
```
md tecinfo
```

#### 2. Crea dentro de TECINFO el siguiente archivo de texto y llámalo HARD.TXT
Abrimos el editor con el comando ``edit``, insertamos el texto y lo guardamos como hard.txt

#### 3. Crea dentro de TECINFO el siguiente archivo de texto y llámalo SOFT.TXT
Igual que en el apartado anterior, abrimos el editor y guardamos el fichero como soft.txt con este texto.

#### 4. Mueve el contenido de TECINFO a la carpeta APLI del disquete A utilizado para realizar los ejercicios anteriores

#### 5. Crea un nuevo archivo formado por la unión de HARD.TXT y SOFT.TXT, sin volver a escribir el texto, y guárdalo en la carpeta AGENDA con el nombre ORDER.TXT

#### 6. Elimina la carpeta TECINFO
```
rd tecinfo
```

#### 7. Copia a la vez los archivos HARD.TXT y SOFT.TXT en la carpeta VARIOS

#### 8. Cambia la extensión de los archivos contenidos en AGENDA por .TYP
```
ren varios\agenda\*.* *.typ
```

#### 9. Cambia la primera letra del nombre de todos los archivos del directorio APLI que empiecen por la letra C y tengan extensión DOC de forma que empiecen con la letra S

#### 10. Copia los archivos contenidos en la carpeta APLI que tengan extensión DOC en la carpeta AGENDA
```
copy apli\*.doc varios\agenda
```
