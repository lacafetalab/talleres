Taller: Git Intermedio
===

En este taller veremos como utilizar comandos de GIT para la resolución de problemas que suelen ocurrir en nuestro día a día.

## Requisitos

- PC o Laptop.
- Git.
- Editor de texto.
- Usuario Gitlab y Github.

CASOS
===

## Caso 1: Migrar un repositorio

1. Clonar el siguiente [repositorio](https://github.com/lacafetalab/receta-ceviche).
```
git clone git@github.com:lacafetalab/receta-ceviche.git
```
2. Cambia la *url* del repositorio.
```
git remote set-url origin enlace-del-repositorio
```
3. Haz un push a tu repositorio.
```
git push origin master
```
**Nota:** En caso de aparecer error intentar solucionarlo con el siguiente comando:
```
git merge --allow-unrelated-histories
```

## Caso 2: Resolver conflictos

1. Crear una rama temporal con tu nombre.
```
git checkout -b nombre
```
2. Agrega tus propios ingredientes y su preparacion. Haz un *commit*.
3. Agrega una imagen de tu ceviche. Haz un *commit*.
4. Mezcla tus cambios con la rama principal (master).
```
git merge --no-ff nombre
```
5. Elimina la rama temporal.

**Nota:** Conversa con tu companero y conserven los cambios correctos. Haz un *commit* y haz un *push*.

## Caso 3: Eliminar un archivo

1. Elimina la imagen que subiste en el ejercicio anterior. Haz un *commit*.
2. Elimina el archivo del historial de git.
```
git filter-branch --tree-filter 'rm -f archivo.png'
```

## Caso 4: Eliminar un commit

1. Escribe un texto y haz un nuevo commit.
2. Borra el commit conservando los cambios que contenia.
```
git reset HEAD~1
```
3. Vuelve a hacer un commit con los mismos cambios.
4. Elimina el commit y sus cambios.
```
git reset --hard HEAD~1
```

## Caso 5: Recuperar cambios de un commit eliminado

1. Verifica la lista de registros de git.
2. Entra y verifica que los cambios existen.
```
git checkout hash
```
3. Crea una nueva rama con el contenido del commit que deseas recuperar.
```
git checkout -b nueva-rama
```
4. Haz un merge con la rama principal (master).
```
git merge master
```
5. Elimina la rama temporal.

**Nota:** *git reflog* hace referencia a las actualizaciones, en ramas de git, que se realizaron en el repositorio local.

## Caso 6: Copiar y pegar cambios

1. Crea una rama temporal con tu nombre.
```
git branch nueva_rama
git checkout nueva_rama
```
2. Agrega cantidades al lado de los ingredientes.
3. Al final del archivo agrega el total del costo de tu ceviche.
4. Copia el *hash* del commit de las cantidades desde el log de git.
```
git log
```
5. Regresa a la rama principal (master).
```
git cherry-pick hash
```

## Caso 7: Etiqueta tu version

1. Crea una etiqueta para la primera version de tu receta.
```
git tag v1
```

## Caso 8: Visualizar logs de cambios

1. Visualiza los commits.
```
git log
```
2. Visualiza los commits y los cambios que se hicieron.
```
git log -p
```

3. Visualiza los commits por autor.
```
git log --author nombre
```

4. Visualiza los commits y sus modificaciones.
```
git log --stat
```

5. Visualiza los commits en una sola linea.
```
git log --oneline
```

6. Visualiza los commits de forma grafica.
```
git log --graph
```

7. Visualiza quien edito cada linea de tu archivo.
```
git blame archivo.txt
```