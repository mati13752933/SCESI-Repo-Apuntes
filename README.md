# Trabajo Individual - Apuntes GIT
Matias Marcelo Revollo Cornejo
## Clase 1 Lunes - 20/04/2026
### ¿Qué es GIT ? 
Es como un checkpoint, crea puntos de guardado para nuestros archivos y que podamos volver atrás + poder ver el historial de lo que hemos hecho, no es una herramienta individual, se puede usar con otras personas también
### ¿Cómo nació GIT?
El creador de Linux (Linus Torvalds, nuestro dios)
Él usaba email para recibir distribuciones y era bastante cansador, entonces él con su comunidad decidieron usar BitKeeper. Estos eran privativos, por asi decirlo celosos y solo debias usarlos a ellos "ni tu ni tus colaboradores usaran otro además de mi", pero alguien rompió la regla, bitkeeper los descubrió y les quito el acceso a su repo.
Linus Torvalds se molestó y creó git, luego de 2 o 3 semanas de la rabia de Linus Torvalds.
### ¿Cómo instalar GIT?
#### Para Linux: 
Nos dirigimos a la terminal
Ponemos el comando
```
sudo apt-get install git
```
Nos muestra la instalación
Le damos a
```
S
```
Para comprobar que todo haya salido bien, ponemos el comando "git --version" si nos sale la versión que tenemos, entonces pudimos instalarlo
#### Para Windows : 
Buscamos "git" en Chrome (https://git-scm.com/install/)
Entramos a "Install"
Lo descargamos para Windows
Le damos next a todo hasta las ramas y seleccionamos Override
Al final le damos a Install
Para comprobar que todo haya salido bien, ponemos el comando:
```
git --version
```
Si nos sale la versión que tenemos, entonces pudimos instalarlo
### Configuraciones para poder usarlo
En la terminal
```
git config --global user.name "Nombre Completo"
git config --global user.email "Correo Electronico"
git config --global core.autocrlf true
```
### Sistema de Puntuación:
Examen             -> 50 pts
Trabajo Grupal     -> 30 pts
Trabajo Individual -> 10 pts
Asistencia         -> 9 pts
Formulario         -> 1 pt
EXTRA              -> 10 pts
### DETALLES DE CADA AREA:
#### Examen:
Entrará TODO lo visto en clase(comandos, teoría, practica....)
###### Pregunta de examen
Linus Torvals de la pura rabia creo git jsjajsa
#### Trabajo Grupal:
Grupos de a 4
Proyecto libre (Lenguaje y tema libre)
Fecha de entrega 2 de Mayo a las 21:00
La nota es grupal
Cosas a Calificar en el trabajo grupal
Todos tienen que hacer lo mismo(en cantidad)
Usar GitFlow
Uso de buenas practicas(en comits,ramas,etc)
Un README.md -> nombre del equipo y de los integrantes, descripción de proyecto, instrucciones para que el auxi pueda ejecutarlo
Se empieza desde 28 de Abril
#### Trabajo Individual:
Debemos tener nuestros apuntes de cada día(hacer diariamente, no todo a ultima hora)
Debe ser en un README.md
No usar IA y usar el formato markdown
Si tenemos imágenes, poner en una carpeta llamada "Imágenes"
Si faltamos a una clase, hablar al auxi y avisarle
#### Asistencia:
La asistencia se va a llenar en cualquier momento de la clase, durante 10 minutos estará habilitado
Puntos Extra
Correcciones en clase
Ayuda con la FLISOL
Máximo 10
Aprobación
La nota mínima de aprobación es 65 sobre 100

### Avance de clase:
```
" # " es para titulo
" ## " es para subtitulo
" ### " es para subsubtitulo
" ``` " para poner codigo
```
Se inicializa con:
```
git init
```
Tenemos que añadir el README.md con:
```
git add README.md
```
Ahora el siguiente comando va a reconocer el README.md
```
git status
```
Y hacemos el commit con:
```
git commit -m "Nombre Commit"
```
Para poder ver la hora del commit es:
```
git log
```
### Archivos de nuestros repositorios
#### README.md
El README.md es donde se describe el proyecto, lo primero que ve cualquiera que entra al repo, tiene que explicar bien de qué trata y cómo usarlo.

#### .gitignore
El .gitignore le dice a GIT qué archivos ignorar, por ejemplo carpetas con contraseñas o archivos que no deberían subirse nunca.

## Clase 2 Martes - 21/04/2026
### States y Commits
#### Estados de Git
##### Directorio de Trabajo (Modificado)
Es la carpeta en la que ponemos nuestro codigo, viene despues del "git init" y git ya ve todo lo que estamos haciendo (nuestros cambios), pero no los guarda

Git clasifica tus archivos en 2 grupos:
###### Untracked:
Un archivo que acabas de crear, que no ha pasado por las 3 fases antes, es decir que no le ha hecho seguimiento
###### Modified:
Cuando estas haciendo cambios en un archivo el cual ya existia y ya paso por las 3 fases, que ya tenga una version previa y lo estes modificando

Con un comando podemos ver varias de estas cosas, tambien nos dice si es que el archivo modificado esta en seguimiento o no:
```
git status
```
Si queremos volver a un estado anterior, usamos el siguiente comando, tambien sirve por si borramos un archivo en seguimiento
```
git restore "Nombre archivo"
```
El .gitignore nos permite ocultar los archivos que no queremos que se puedan subir o que sean visibles, simplemente añadimos el archivo al .gitignore, de esta forma tampoco va a salir cuando hagamos el status

##### Stage Area (Preparado)
Aqui es donde guardamos todos los cambios que hicimos y git hace su punto de guardado, para asi grabarlos en el repositorio local
Para prepararse a guardar cambios de un archivo usamos:
```
git add nombreArchivo
```
Para volver y no mandarlo a stage aun, usamos:
```
git restore --staged nombreArchivo
```
###### Pregunta de examen -> ¿Qué hace el --staged?

##### Repositorio Local (Committed)
Una vez que le hayamos dicho que estamos cambiando y guardando, git crea en base a los archivos el punto de guardado, y se van a los logs

En este punto yo ya se en que archivos quiero que se guarden los cambios y uso el siguiente comando:
```
git commit -m "mensajeDescriptivo"
```
Ahora en logs nos va a decir el ultimo punto de guardado en HEAD
```
git log
```
El siguiente comando nos lo muestra mas resumido
```
git log --oneline
```
Para resetear un commit usamos:
```
git reset --soft HEAD~1
```
#### Buenas Practicas
##### 1 ¿Cada cuánto hacer un commit?
Usamos commits atómicos, se hacen cuando terminemos de hacer una modificacion que cambie la funcionalidad, no debe haber un gran cambio entre commits (menos de 1000 lineas), es mejor hacer cambios cortos y simples
#### 2 ¿Escribe buenos commits
##### 1 Verbos Imperativos(Add, Change, Fix, Remove)
Un ejemplo cuando hemos añadido una funcion de suma:
```
git commit -m "Add plus function"
```
##### 2 No uses puntos finales ni puntos suspensivos en tus commits
Son innecesarios
##### 3 No hagas un commit con más de 50 caracteres
Tus commits no pueden tener mas de 50 caracteres, pueden haber mayusculas y minusculas
##### 4 Usa prefujos para tus commits
```
git commit -m "feat: Add new search feature"
```
Prefijos:
feat: para una nueva característica para el usuario.
fix: para un bug que afecta al usuario.
perf: para cambios que mejoran el rendimiento del sitio.
build: para cambios en el sistema de build, tareas de despliegue o instalación.
ci: para cambios en la integración continua.
docs: para cambios en la documentación.
refactor: para refactorización del código como cambios de nombre de variables o funciones.
style: para cambios de formato, tabulaciones, espacios o puntos y coma, etc; no afectan al
usuario.
test: para tests o refactorización de uno ya existente.
###### Pregunta de examen ^
###### 5 Añade todo el contexto que se necesario en el cuerpo del commit
Si añadimos algo que es realmente complejo y grande, tal que los 50 caracteres del punto 3 no son suficientes, te vas al cuerpo del commit
```
git commit
```
En este como titulo puedes poner algo corto, como lo harias antes (aunque no sea muy descriptivo) y en el cuerpo pones por puntos una descripcion mas detallada


## Clase 3 Miercoles - 22/04/2026
### ¿Cómo tener cuenta en GITHUB?
Ingresamos a la página (githum.com), llenamos nuestros datos, como en cualquier página, NO usar la cuenta institucional, ya que cuando terminamos la carrera perdemos el acceso a ella y por lo tanto perdemos nuestra cuenta
### ¿Cómo crear un repositorio?
Nos vamos a la parte de Repositorio y le damos a New,  en el nombre del repo podemos ponerle el nombre que querramos, preferimos dejarlo en publico para que el auxi pueda revisarlo, en el add README.md lo dejamos en off, ya que deberiamos tener este, seleccionamos SSH
### Conectar el GIT con GITHUB
Abrimos nuestra terminal de git bash para Windows
y ponemos el siguiente comando
```
ssh-keygen -t ed25519 -C "correoDeLaCuentaDeGitHub"
```
nos saldrá un código secreto por asi decirlo
hacemos un
```
cat /rutaSecreta/
```
y luego de darle a enter, copiamos el codigo, volvemos a ir a GITHUB y pegamos el codigo que nos dio el git bash, creamos nuestra llave y para prbar si todo salio bien ponemos este comando
```
ssh -T git@github.com
```
le damos a 
```
yes
```
y nos deberia saludar con nuestro usuario de github en git
### Conectar nuestro README.md con el repo creado
Ejecutamos los siguientes comandos
```
git remote add origin git@github.com usuario/nombreRepo.git
git branch -M main
git push -u origin main
```
Ahora ya tenemos nuestro repo de forma remota
###### PREGUNTA DE EXAMEN 
comando para generar el secreto:
```
ssh-keygen -t ed25519 -C "correoDeLaCuentaDeGitHub"
```

En el resto de la clase hacemos algunas cosas con https, pero nos terminamos dando cuenta que pide el usuario de github, la contra.... y al final ni poniendo todo bien nos funciona, entonces por eso usamos ssh.

### Bonita descripcion de perfil
Si hacemos una buena descripcion de perfil nos ganamos 5 puntos, y si esta en ingles, vale 6, que super.

![alt text](image.png)
Aqui esta una imagen de por que falte ese dia auxi, soy el del problema del ojo :c