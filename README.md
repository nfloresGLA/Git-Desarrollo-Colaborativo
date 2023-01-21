# Github - EducacionIT.

## Configuracion _inicial_ (__Unica vez__ post instalacion)

``` js
1. Configurar el nombre de usuario de manera global.
> git config --global user.name "nombre de usuario"

2. Configurar el email del usuario de manera global.
> git config --global user.email "mail@mail.com"

2.5 (Opcional) Verificacion de los datos anteriores.
> git config user.name 
> git config user.email

Esto nos mostrara el nombre / email asignados.
```
<hr>

## Configuracion _inicial_ en __cada repositorio__
``` js
1. En la carpeta que elijamos como Repositorio Local. *
> git init
> git remote add origin "Link del repositorio"

// *. Hay que realizarlos <una sola vez> por repositorio.
``` 

>_Link del repositorio - ejemplo._
![image](https://user-images.githubusercontent.com/120741890/213313015-c35d5f9f-74e9-4902-bad4-7d86ecedf53e.png)

<hr>

## Comandos __habituales__ de cada repositorio
``` js
1. Ver el estado de nuestros archivos. (Cargados y no cargados)
> git status (Working directory)

2.1 Agregar archivos al <Staging area>.
> git add <nombre archivo/s> *

2.2 Eliminar archivos del <Stagin Area>.
> git restore --staged <nombre archivo/s> *

// * Pueden usar el comodin . (all files)

3. Agregar archivo/s al tracked.
> git commit -m "Mensaje descriptivo del commit"

4. Guardar los archivos trackeados al repositorio remoto.
> git push origin rama
``` 
---
## Comandos __Branch__

``` js
1.  git branch // muestra las ramas del repositorio local 
1.1 git branch -a // muestra todas las ramas (local y remoto)
1.2 git branch nombre-rama // crea una nueva rama
1.3 git branch -d nombre-rama // elimina una rama
1.4 git branch -m nombre-rama // renombra una rama

2. Seleccionar una rama para trabajar en ella.
> git checkout nombre-rama
> git switch nombre-rama // a partir de la v 2.23

3. Crear y situarnos en dicha rama.
> git checkout -b nombre-rama
> git switch -c nombre-rama

4. Unir ramas
> git merge nombre-rama-fusionar *

// * Hay que estar en la rama en donde queremos
// <traer> los cambios de la otra rama "nombre-a-fusionar".
```
---
## Comandos utiles bajo _cierto_ __contexto__ (extras)
``` ts
1. Historial de confirmaciones (commits).
> git log // Muestra los commits confirmados (abundance *).
> git log --oneline // Muestra los commits de forma simple.
> git log --oneline --decorate --all --graph *

// *.1 Muestra mucha informacion en el log
// *.2 Muestra los commits simplificados de forma bella.

2. Eliminar un commit o mas ~numero*.
> git reset --soft HEAD~1 // soft: SIN borrar los cambios.
> git reset --hard HEAD~1 // hard: borrando todos los cambios.

// * el numero de commits que queremos retroceder.

3. Traer los cambios de la rama remota.
> git pull --rebase origin nombre-rama *

// Muy util cuando necesitamos traer nueva informacion
// a nuestro repositorio local (alguien agrego commits)
// o hayan aprobado un PR (pull request).

4. Seleccionar trozos del mismo archivo para commits.
> git add --patch

// Abrira en la consola opciones para manipular
// el archivo correspondiente para fragmentarlo.

5. Almacen temporal (Agregar).
> git stash // Almacena <solo> el WD (working directory).
> git stash -u // Almacena el WD y SA (staging area).
> git stash -m // Asigna un titulo al stash (similar commit).

5.1 Almacen temporal (Remover).
> git stash pop // Lo remueve del stash y lo borra.
> git stash apply stash@{numero} // Remueve pero NO lo borra. 

5.2 Almacen temporal (Ver / Traer).
> git stash list // Muestra la lista de stash
> git stash show stash@{numero} // Muestra un stash especifico.

5.3 Almacen temporal (Borrar).
> git stash drop // Borra el ultimo stash
> git stash drop stash@{numero} // Borra el stash seleccionado.
```
---
## Cambiar el nombre a la rama default

### Primera parte: Repositorio remoto (Navegador)

~~~ js
1. ir a las ramas del proyecto que queremos modificar.
~~~
![image](https://user-images.githubusercontent.com/120741890/213264779-61802ccd-b6ab-4fac-8c65-0ed345185172.png)

~~~ js
2. Click en 'View all Branches'.
~~~

![image](https://user-images.githubusercontent.com/120741890/213265648-34dd2291-c5cd-4489-89c2-2a2edfd91c2b.png)

~~~ js
3. Click en "editar el nombre de la rama"
En este caso queremos cambiar la rama default.
 
// Icono del lapiz - señalado con rojo.
~~~

![image](https://user-images.githubusercontent.com/120741890/213266713-8a149401-8035-412e-8d2e-ab8a1d2a38ca.png)

~~~ js
4. Renombrar la rama default por el 
nombre de preferencia y confirmar el cambio.

// Git chequea si el nombre de la rama esta disponible
// Aparecera el comentario en un pop-up inline
// validando o no el nombre

~~~

![image](https://user-images.githubusercontent.com/120741890/213267127-b660ed0f-6b2a-4f32-b287-395a94873ac4.png)

### Segunda parte: Repositorio Local (Consola)

~~~ js
5. Modificar la rama local con el nuevo nombre remoto.
> git branch -m vieja-rama nueva-rama *

// * nueva-rama: la que generamos en "rename branch".

6. Actualizacion del repositorio remoto. (primera parte)
> git fetch origin

7. Sincronizacion remota.
> git branch -u origin/nueva-rama nueva-rama

8. Setear la rama origin (nueva-rama) como principal.
> git remote set-head origin -a

// ¡Importante! Seguir los pasos al pie de la letra.
~~~