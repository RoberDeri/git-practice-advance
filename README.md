## EJERCICIO 1

Muestro el historial de cambio de repositorios.

```
git log
```

Creo la carpeta capítulos y crear dentro de ella el fichero capitulo1.txt 
```
mkdir capitulos
cat > capitulos/capitulo1.txt
```
Inserto el siguiente texto:<br>

> <strong><i>Git es un sistema de control de versiones ideado por Linus Torvalds.</i></strong>

Añado los cambios a la zona de intercambio temporal y creo un commit con el mensaje “Añado capítulo 1”.
```
Ctrl+D
git add .
git commit -m "Añadido capítulo 1."
```

Compruebo de nuevo el historial de cambios de repositorio.
```
git log
```

## EJERCICIO 2

Creo el fichero capitulo2.txt en la carpeta capítulos con el siguiente texto.

```
cat > capitulos/capitulo2.txt
```

> El flujo de trabajo básico con Git consiste en:<br>
> 1- Hacer cambios en el repositorio.<br>
> 2- Añadir los cambios a la zona de intercambio temporal.<br>
> 3- Hacer un commit de los cambios.<br>

Añado los cambios a la zona de intercambio temporal y creo un commit de los cambios con el mensaje ”Añadido capítulo 2”.
```
Ctrl+D
git add .
git commit -m "Añadido capítulo 2."
``` 
Muestro las diferencias entre la última versión y las dos versiones anteriores con git diff.
```
git diff HEAD~2..HEAD
```

## EJERCICIO 3

Creo el fichero “capitulo3.txt” en la carpeta “capitulos”:
```
cat > capitulos/capitulo3.txt
```
Añado el siguiente texto: 

> Git permite la creación de ramas lo que permite tener distintas <br>versiones del mismo proyecto y trabajar de manera simultánea en ellas.

Añado los cambios a la zona de intercambio temporal y creo un commit de los cambios con el mensaje ”Añadido capítulo 3”.
```
git add .
git commit -m "Añadido capítulo 3."
```
Compruebo las diferencias entre la primera y última versión del repositorio usando el método diff y añadiendo como inicio el código hash de la primera versión (en imagen la última versión registrada).

```
git diff <codigo hash de la primera versión>..HEAD
```

## EJERCICIO 4

Creo un fichero “indice.txt”  y registro una línea de texto.
```
cat > indice.txt
```
Añado los cambios a la zona de intercambio temporal y creo un commit de los cambios con el mensaje ”Índice de los capítulos con conceptos avanzados de Git”.

```
git add .
git commit -m "Índice de los capítulos con conceptos avanzados de Git."
```

Con git log muestro el autor del cambio.
```
git log
```

## EJERCICIO 5

Creo una nueva rama bibliografía y compruebo las ramas del repositorio.
```
git branch bibliografia
git branch -av
```
## EJERCICIO 6

Creo el fichero “capitulos/capitulo4.txt”:
```
cat > capitulos/capitulo3.txt
```
Añado el siguiente texto:
>  En este capítulo veremos cómo usar GitHub para alojar repositorios en remoto.

Añado los cambios a la zona de intercambio temporal y creo un commit de los cambios con el mensaje ”Añadido capítulo 4”.
```
git add .
git commit -m "Añadido capítulo 4."
```

Mediante git log muestro la historia del repositorio, incluyendo todas las ramas.

```
git log --graph --all --oneline
``` 


## EJERCICIO 7

Cambio de la rama “master”  a la rama “bibliografía”.
```
git checkout bibliografia
```
Creo el fichero “bibliografia.txt” y añadir la siguiente referencia:
```
cat > bibliografia.txt
```
> Chacon, S. and Straub, B. Pro Git. Apress.

Añado los cambios a la zona de intercambio temporal y creo un commit de los cambios con el mensaje ”Añadida primera referencia bibliográfica”.
```
Ctrl+D
git add .
git commit -m "Añadida primera referencia bibliográfica."
```

Compruebo la historia del repositorio, incluyendo todas las ramas.
```
git log --graph --all --oneline
```

## EJERCICIO 8

Cambio a la rama “Master” y fusiono con ella la rama “bibliografía”. Al hacerlo, el editor de texto me da la opción de justificar esta acción dejando un mensaje.
```
git checkout main
git merge bibliografia
``` 

Compruebo la historia del repositorio, incluyendo todas las ramas.
```
git log --graph --all --oneline
```

Eliminar la rama “bibliografía”.
```
git branch -d bibliografia
```

Repito el comando de muestra de historia del repositorio, incluyendo todas las ramas.
```
git log --graph --all --oneline
```

## EJERCICIO 9

Creo la rama ‘’bibliografia” y cambio a ella desde ‘’master”.
```
git branch bibliografia
git checkout bibliografia
```

Cambio el fichero bibliografia.txt para que contenga las siguientes referencias:
```
cat > bibliografia.txt
```
> Scott Chacon and Ben Straub. Pro Git. Apress.
> Ryan Hodson. Ry's Git Tutorial. Smashwords (2014)

Añado los cambios a la zona de intercambio temporal y creo un commit de los cambios con el mensaje ”Añadida nueva ref. biblio”.
```
Ctrl+D
git commit -a -m "Añadida nueva referencia bibliográfica."
```

Cambio a la rama “master” y modifico el fichero .txt previamente importado:
```
git checkout main
cat > bibliografia.txt
```
> Chacon, S. and Straub, B. Pro Git. Apress.
> Loeliger, J. and McCullough, M. Version control with Git. O'Reilly.

Añado los cambios a la zona de intercambio temporal y creo un commit de los cambios con el mensaje ”Añadida nueva ref. biblio”.
```
Ctrl+D
git commit -a -m "Añadida nueva referencia bibliográfica."
````
Intento fusionar la rama “master” con “bibliografia”. Se presenta un conflicto, pues ambas ramas designadas igual contienen datos diferentes. Abro el editor de texto para hacer una corrección.
```
git merge bibliografia
git nano bibliografia
# Hacer los cambios indicados en el fichero
```

Añado los cambios a la zona de intercambio temporal y hacer un commit con el mensaje: 

> Resuelto conflicto de bibliografía.
```
git commit -a -m "Solucionado conflicto bibliografía."
```
Compruebo mediante git log que la fusión ha sido exitosa.
```
git log --graph --all --oneline
```

