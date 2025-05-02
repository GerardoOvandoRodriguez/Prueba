# Flujo de trabajo en Git

# Paso 1 - Clonar repositorio desde GitHub
Para clonar un repositorio debemos dar clic en el botón verde con la palabra "< > Code"" </br></br> ![image](https://github.com/user-attachments/assets/264bd18d-7f8e-46a7-b135-00620209cd54)</br>
Posteriormente nos mostrara un cuadro desplegable en el cual podemos encontrar la URL para poder clonar nuestro repositorio la cual debemos copiar: 

</br></br> ![image](https://github.com/user-attachments/assets/e935c1c3-faf9-45da-9731-28b2337fb768) </br>
## Navegar entre directorios con git
Dentro de nuestra terminal o bash de git tendremos que acceder a la ubición donde deseamos crear nuestro repositorio utilizando los comandos de navegación:</br>
</br>**pwd** => para imprimir la ubicación o directorio actual en el que nos encontramos.
</br> **cd** + {la ruta o directorio al que nos queremos mover} => para movernos a una dirección de nuestros directorios.
</br> **cd ..** => nos devuelve un nivel más arriba del directorio en el que actualmente nos encontramos.
</br> **ls** => para listar los elementos que tenemos dentro de ese directorio.</br>
</br> Una vez ubicados dentro del directorio donde queremos clonar nuestro repositorio podemos crear un nuevo directorio para poder separar nuestro directorio de los demás y tener nuestros archivos más organizados. Para esto utilizaremos el comando **mkdir** + {nombre que le daremos a nuestro directorio}.
```
$ mkdir Prueba
```
Con esto ya tenemos nuestro directorio donde clonaremos nuestro repositorio, debemos acceder a el utilizando el comando **cd** + {El nombre del directorio que acabamos de crear}.
```
$ cd Prueba/
```
Una vez dentro del directorio podemos comenzar a clonar nuestro repositorio, para esto utilizaremos el comando **git clone** + {URL que copiamos desde GitHub del repositorio a clonar}.
```
$ git clone https://github.com/GerardoOvandoRodriguez/Prueba.git
```
# Paso 2 - Crear una nueva rama en git
Para poder crear una nueva rama dentro de nuestro repositorio local primero debemos ver en que rama nos encontramos con el comando **git branch**.
```
$ git branch
output => *main
```
La salida nos indica que nos encontramos en la rama **main** de nuestro repositorio, que quiere decir que nos encontramos en la rama principal.

Para crear una nueva rama donde llevaremos a cabo nuestro desarrollo utilizaremos el comando **$ git branch -M {nombre de la rama}**.
```
$ git branch -b dev_Gerardo
```
Una vez creada la rama en automático git nos cambia a la nueva rama que hemos creado, utilizando el comando **git brach** podemos comprobar que se ha creado la rama de manera correcta.

# Paso 3 - agregar cambios
Una vez realizado algún cambio en alguno de nuestros archivos de nuestro repositorio comprobaremos cuales son los cambios que tenemos sin agregar con el comando **git status**.
```
$ git status
```
Output: </br>
![image](https://github.com/user-attachments/assets/bc1b2135-44c6-4441-88e9-5dd6567e9d11)</br></br>
Las letras en rojo nos indican que hay un archivo el cual fue modificado y no se han agregado los cambios.

Con el comando **git add .** podemos agregar los cambios que hemos realizado en nuestros archivos a un area que almacena de forma temporal los cambios antes de integralos a nuestra ultima versión de nuestro código principal.
```
$ git add .
```

Con el comando **git status** podemos comprobar que los cambios han sido agregados de forma correcta.

![image](https://github.com/user-attachments/assets/fa1d4ab1-cd42-40dc-914c-526b8a59216b)
# Paso 4 - agregar cambios a nuestra área de respositorio
Cuando queremos agregar los cambios que tenemos a nuestra área de respositorio local esta es un área antes de subir los cambios a nuestro repositorio remoto y ser parte de nuestra versión final, debemos utilizar el comando **git commit -m "{mensaje con una breve descripción de los cambios que se han realizado}"**.
```
$ git commit -m "Se agrego nueva línea de código para comprobar cambios"
```
Output:</br>
![image](https://github.com/user-attachments/assets/48a5b91a-b059-415d-b7d8-ea83e531e3c1) </br>

Con el comando **git status** podemos comprobar que ya no tenemos ningún archivo esperando por ser movido al área de repositorio local.

![image](https://github.com/user-attachments/assets/21ab2b5e-bece-4750-9f3e-39587858385d)

# Paso 5 - comprobar si no hay cambios nuevos en el respositorio Remoto
Utilizando el comando **git pull** podemos validar si existe algún cambio reciente en el repositorio remoto, esto se hace escensialmente para ver si otra persona no a agregado un nuevo modulo igual al nuestro antes de subir nuestros cambios.
```
$ git pull
```
Output: </br>
![image](https://github.com/user-attachments/assets/eaf3fc64-48b7-4bdd-bdd1-c1ac961120ae)

# Paso 6 - cambiar de ramas antes de actualizar cambios

Utilizaremos el comando ** git checkout {nombre de la rama a la que nos moveremos}**, esto con el fin de movernos a la rama de donde vamos a actualizar los cambios.
```
$ git checkout dev_Gerardo
```
# Paso 7 - Comprometer los cambios en nuestro repositorio local
Una vez que hemos cambiado de rama y nos encontramos en la rama donde queremos comprometer los cambios, debemos utilizar el comando ** git merge {nombre de la rama donde queremos combinar la rama actual en la que nos encontramos}**.
```
$ git merge main
```
# Paso 8 - Cambiar nuevamente a la rama donde comprometeremos nuestro codigo a nuestro repositorio Remoto
Utilizaremos nuevamente el comando ** git checkout {nombre de la rama a cambiar}** para poder ubicarnos en la rama que utilizaremos para convinarla a la rama principal que se encuentra en nuestro respositorio Remoto.
```
$ git checkout dev_gerardo
```
# Paso 9 - Actualizar nuestro repositorio remoto con los cambios finales
Cuando hemos completado un modulo de manera correcta podemos proceder a actualizar nuestro respositorio remoto para que los cambios surtan efecto en nuestro código principal para esto utilizaremos el comando **git push**.
```
$ git push
```
Output: </br>
![image](https://github.com/user-attachments/assets/cba8643f-ebd3-4180-9030-fb51def67ace)</br></br>
Podremos comprobar que los cambios se han realizado de manera correcta actualizando la página de nuestro respositorio remoto, observaremos que se han agregado nuevos commits a este.

![image](https://github.com/user-attachments/assets/5277a0c5-ccaf-44f5-93af-ee6d2d96c608)</br></br>

Dando clic en la palabra *"Commits"* prodremos revisar con mayor detalle todos y cada uno de los commits que se han subido al repositorio remoto.

![image](https://github.com/user-attachments/assets/bcd8b2e4-d5b6-4a4a-acb7-8e4b12d1e118)





