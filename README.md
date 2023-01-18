# Github - EducacionIT.

## Configuracion __inicial__ (Primera vez post instalacion)

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

## Configuracion inicial de __cada repositorio__
``` js
1. En la carpeta que elijamos como Repositorio Local. *
> git init
> git remote add origin "link generado por git del repositorio"

// *. Hay que realizarlos <una sola vez> por repositorio
``` 

## Configuracion __continua__ de cada repositorio
``` js
1. Ver el estado de nuestros archivos. (Cargados y no cargados)
> git status (Working directory)

2. Agregar archivos al <Staging area>.
> git add <nombre archivo/s>

3. Agregar archivo/s al tracked.
> git commit -m "Mensaje descriptivo del commit"

4. Guardar los archivos trackeados al repositorio remoto.
> git push origin rama
``` 
---
## Cambiar el nombre a la rama default

### Primera parte: Repositorio remoto (Navegador)

~~~ js
1. ir a las ramas del proyecto que queremos modificar
~~~
![image](https://user-images.githubusercontent.com/120741890/213264779-61802ccd-b6ab-4fac-8c65-0ed345185172.png)

~~~ js
2. Click en View all Branches
~~~

![image](https://user-images.githubusercontent.com/120741890/213265648-34dd2291-c5cd-4489-89c2-2a2edfd91c2b.png)

~~~ js
3. Click en "editar el nombre de la rama"
En este caso queremos cambiar la rama default
 
// Icono del lapiz señalado con rojo
~~~

![image](https://user-images.githubusercontent.com/120741890/213266713-8a149401-8035-412e-8d2e-ab8a1d2a38ca.png)

~~~ js
4. Renombrar la rama default por el 
nombre de preferencia y confirmar el cambio

// Git chequea si el nombre de la rama esta disponible
// Aparecera el comentario en un pop-up inline
// validando o no el nombre

~~~

![image](https://user-images.githubusercontent.com/120741890/213267127-b660ed0f-6b2a-4f32-b287-395a94873ac4.png)

### Segunda parte: Repositorio Local (Consola)

~~~ js
5. Modificar la rama local con el nuevo nombre
> git branch -m viejaRama nuevaRama

6. Busca los cambios efectuados (la primera parte)
> git fetch origin

7. Sincronizacion remota (vinculacion)
> git branch -u origin/nuevaRama nuevaRama

8. Setear la rama origin como principal
> git remote set-head origin -a

// ¡Importante! Seguir los pasos al pie de la letra.
~~~