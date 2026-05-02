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
###### Pregunta de examen 
¿Qué hace el --staged?

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

###### Razon de Falta
![alt text](image.png)
Aqui esta una imagen de por que falte ese dia auxi, soy el del problema del ojo :c

## Clase 4 Jueves - 23/04/2026
### Git Remote
Es el comando que le dice a nuestro la direccion de la que nuestra nube de traer/enviar informacion
El siguiente comando nos permite ver donde apunta nuestro repo
```
git remote -v
```
Por ejemplo a donde se va a subir algo con push, o donde bajar con fetch
El siguiente comando vincula nuestro repo con la nube
```
git remote add <apodo>"url"
```
Y este ultimo cambia la url donde apunta nuestro repo
```
git remote set-url <apodo>"url"
```
Si lo quiero setear y cambiar la url es seguir lo del codigo y en "url" poner la ruta a la que quiero cambiarlo
### Multiples SSH
Una llave ssh lo que hace es conectar tu compu con el github, en este caso cada cuente necesita su tunel, podemos verlo como puertas y que una llave abre cada puerta, no puede haber una llave para dos puertas
Creamos llaves como ya sabiamos en otras clases, la diferencia es añadir al final:
```
-f ~/.ssh/nombreLlave
```
si hacemos un
```
ls -a
```
podemos ver ambas llaves
nos creamos un archivo llamado config
```
touch config
nano config
```
dentro ponemos
```
# Cuenta Personal (la de siempre)
Host github.com
HostName github.com
User git
IdentityFile ~/.ssh/id_ed25519
# Cuenta del otro correo
Host github-otroNombre
HostName github.com
User git
IdentityFile ~/.ssh/id_micorreo
```
Si no cambiamos los host, solo va a detectar el primero
El host es el apodo/alias que le ponemos a nuestra conexion
El hostName es el que usamos, si fuera gitLab ese seria el hostName
El User git no se toca
El IdentifyFile es mi llave

Tenemos que probar si es que funciona la segunda con
```
cat nombreLlave
```
Copiamos el codigo secreto y vamos a la cuenta de github
Hacemos el proceso que ya sabemos de añadir la llave con nuestra cuenta de github
Luego nos va a saludar en git con el nombre de github y listo, voy a poder usar mis dos cuentas
Si me voy a mi repositorio y subo un cambio, va a fallar, porque la key que esta usando es la otra, entonces lo unico que tenemos que hacer es
```
git remote set-url origin git@github-nombreUsuario/urlAlRepo
```
asi lo cambiamos, entonces, lo subimos y evitamos errores
### Configuraciones locales
En la primera clase hicimos configuraciones globales, que las vemos con
```
git config --global
```
Las configuraciones tienen jerarquias, son Sistema, global, local
Si quiero que en un repo haya otro autor, hago lo mismo que antes, pero le quito el global, asi esta confi solo es para tu repo
```
git config user.name"nuevoNombre"
git config user.email"nuevoCorreo"
```
Y esas serian mis locales
Por si acaso, si hacemos un push, tiene prioridad el local
##### Pregunta de examen:
¿Cual es la diferencia entre usar o no --global en esta parte?
### Git Checkout
Es un comando que nos permite desplazarnos hacia atras, ver los puntos de guardado
```
git log --oneline
```
para ver los commits que hemos hecho
En cada commit los primeros 7 numeros son como un codigo que hay que copiarlos
```
git checkout coigoDeCommit
```
### Detached HEAD
Es cuando en lugar de apuntar a una rama, estamos apuntando a un commit, estamos en un punto de guradado, se ve mejor con
```
git log --oneline
```
Es mejor si no tocamos nada, ya que podemos alterar el resto de commits que pasaron luego de este
Para volver a la rama principal hacemos
```
git checkout main
```
Y podemos verlo con
```
git log --oneline
```
#### ¿Qué pasa si hacemos un cambio?
Ok, hicimos un commit cuando nos movimos y dejamos de estar en el main, de momento parece no pasar nada.
Si ahora volvemos a nuestro 
```
git checkout rama
```
Nos dice que el commit que hicimos se esta quedando al aire, si queremos conservarlo, debemos crear una nueva rama
Para crear una rama hacemos
```
git checkout -b feature/experimental-change
```
Ahora volvemos a nuestra rama main con
```
git checkout main 
```
Y ahora con 
```
git log --graph --oneline --all
```
Por ser ramas, veremos como una separacion entre ellas, pero sera notorio nuestro cambio en el tiempo
### Buenas Pracicas del Checkout
#### No trabajes mucho tiempo en 'Detached HEAD'
Si quiero cambiarlo, mejor si lo del commit me lo llevo al inicio y trabajo desde ahi, trata de no volver desde atras
#### Limpia tu Directorio de trabajo
Para hacer 
```
git checkout
```
Debemos tener añadido y commiteado todo, si algo sigue en stage, no nos va a dejar, primero tenemos que guardar esas cosas.
#### Úsalo para aprender
Deberiamos usarlo solo para ver los proyectos de alguien bueno o nosotros, es como para poder dar una vista atras y ver como fue cambiando todo, no es muy recomendable cambiar algo con esto
###### Pregunta examen
SSH sí va a entrar al examen, esto del checkout no tanto

###### Razon de Falta
![alt text](image-1.png)
Aqui esta una imagen de por que falte ese dia, aqui ya empece a ir a la u auxi, soy el del problema del ojo :c

## Clase 5 Lunes - 27/04/2026
Clase super importante para el trabajo grupal
### Ramas
#### ¿Qué son las ramas?
Son bifurcaciones de una rama principal, crean nuevos caminos del codigo, paralelos a otras ramas que se pueden generar.
Trabajamos todo en nuestro main, pero es en teoria una mala practica, porque nso motiva a no tocar el codigo.
Nos permiten trabajar en equipo, cada persona trabaja en su codigo sin necesidad de chocar entre ellos
#### ¿Cómo crear una rama?
El siguiente comando nos enlista las ramas que tenemos
```
git branch
```
Tambien nos muestra en que rama nos encontramos
El siguiente comando nos crea una rama
```
git brunch nombreRama 
```
Contiene todo el codigo que hasta ese momento tenia el main
El siguiente comando elimina una rama
```
git brunch -D nombreRama
```
Los de windows pueden usar 
```
git brunch *
```
para ver en que rama estan
Si creamos una rama dentro de otra es cuando estamos hacienco ramas alternas...
##### Checkout vs Switch
Antes, le estaban dando mil funcionalidades a git checkout, servia para cambiar de ramas, crearlas, volver en el tiempo en commits, trabaja con ramas, commits, archivos, aunque puede provocar algunos erorres al moverte en el tiempo
Switch solo servia para crear ramas y para cambiar entre ellas, es mas seguro que checkout a la hora de evitar errores
### ¿Qué es GITFLOW?
Es un flujo de trabajo,basicamente nos permite trabajar en forma ordenada, para que quien sea vea sus logs en el proceso.
El proposito de main, es guardar el codigo que funciona, nos podemos crear una rama develop
```
git checkout -b develop
```
Aqui estan nuestro codigo en produccion
### ¿Cómo funciona GITFLOW?
#### Main
Es la rama principal que renemos por defecto al crear un repositorio, su proposito es contener el codigo que se encuenntra en produccion
#### Develop
Es una rama de preproduccion, su proposito es tener codigo que aun se esta probando, incluso algunas que no hayan sido probadas aun, pero que las mandaras a main en algun momento.
#### Ramas de apoyo
Pueden ser de tipo feature,release y hotfix
##### Feature
Si queremos declarar una funcion, debemos crearnos una rama y hacerlo en ella.
```
git checkout -n feature/algunaFuncionaldad
```
Es una buena practica
##### Release
Queremos poner a prueba a nuestra funcion y la vamos a testear con casos
```
git checkout -n release/algunaFuncionaldad
```
##### Hotfix
Son ramas que usamos si es que vemos que hay un error en main, como llego ese error a main ? seguro no probamos lo suficiente en release, pero podemos crearla en main y se encarga de resolver el problema rapido
```
git checkout -n hotfix/algunaFuncionaldad
```
### Reumen de GITFLOW que el auxi dio al final
Creas tu rama main que inicializa todo, luego te creas una rama develop, y para cada feature nueva que hagas,te creas una rama feature que decriba tu funcionalidad nueva, a la hora de mergear eliminamos la rama feature. En la siguiente clase veremos mejor el merge.

###### Razon de Falta
![alt text](image-2.png)
Aqui esta una imagen de por que falte ese dia, aqui ya iba a la u sin el parche auxi, soy el del problema del ojo :c

## Clase 6 Martes - 28/04/2026
### ¿Qué es git merge?
Nos permite fusionar nuestras ramas en una sola para que las dos tengan tengan los commits hechos
Podemos usar 
```
git merge -no-ff nombreRama
```
que evita que se pierda el historial y te fuerce a hacer las ramas sin que estas se pierdan, aun si las eliminas
### ¿Qué es git fetch?
Nos sirve para poder trabajar en equipo
Lo tenemos que ejecutar al inicio, antes de trabajar y de subir cambios, mira ramas y mira los cambios.
```
Este puede ser un buen orden
git checkout develop
git fetch
git pull origin develop
```
### ¿Qué es git pull?
Trae todos los cambios de la rama o repo... Al repositorio local, te lo actualiza, y si no trabajas con eso se pueden generar conflictos
Para usarlo con rama es
```
git pull origin rama
```
Git nos reporta un error cuando hay un conflicto, que es cuando 2 personas editan algo y pues git no sabe que hacer, cual guardar... entonces le da la responsabilidad al usuario
Para poder solucionarlo entramos en el archivo del conclicto y con nano vamos viendo lo que queremos y no
### ¿Qué es git push?
Este comando que sube tus cambios al repositorio remoto de esa rama. Se usa también con origin y el nombre de la rama asi evitamos problemas

#### Git fetch vs Git pull
Mientras que fetch solo te avisa si hay novedades en el servidor, pull descarga y aplica esos cambios directamente en tu rama local.
#### Limpieza
Después de subir los cambios finales con push, se recomienda borrar la rama local con git branch -D para mantener el proyecto ordenado

Lo que hicimos en esta clase fue mas pratico, por eso mis apnutes de este dia no son muy largos, tmabien pq recien estaba volviendo de la operacion, soy el del ojo auxi.

## Clase 7 Miercoles - 29/04/2026
### ¿Qué es un Pull Request?
Es la forma profesional de trabajar. No es un comando de Git, sino una solicitud en GitHub para que el equipo revise tu código antes de que este se una a la rama principal (código base).
### ¿Cómo crear un pull request?

Tenemos que hacer 
```
git push origin rama
```
Y debes dirigirte a github.com y seguir los pasos del siguiente tutorial
(https://youtu.be/4CeMKqloOJc)

### El Flujo de Trabajo Profesional 

```
git checkout develop
git fetch
git pull origin develop
git checkout rama # Agregas -b si estás creando la rama
git merge develop # Solo si hubo cambios en develop
# Trabajas en tu rama
git push origin rama # Agregas -u si es la primera vez que subes cambios al repositorio remoto
git checkout develop
git fetch
git checkout rama
git merge develop # Solo si hubo cambios en develop antes de hacer la PR
# Resuelves manualmente los archivos fallidos y sus conflictos
git add .
git commit
[Ctrl + O, Enter, Ctrl + X](depende si usan nano)
git push origin rama
# Sigues el flujo mostrado en “¿Cómo crear un PR?
```
### ¿Por qué usamos los PRs sí ya podemos trabajar normalmente sin ellos?
Aunque es técnicamente posible trabajar sin ellos, los PRs se utilizan principalmente por seguridad y control de calidad.  

#### Gestión de Riesgos: 
Evita que cualquier colaborador fusione código (merge) sin supervisión, lo que previene errores accidentales o la introducción de código malicioso.  

#### Seguridad ante Amenazas:
Actúa como un filtro contra posibles ataques externos o usuarios que intenten comprometer el repositorio ganándose la confianza del equipo.  

#### Debate y Deliberación: 
Obliga al equipo a revisar los cambios, permitiendo que todos entiendan qué se está implementando, quién lo hace y dando la oportunidad de presentar opiniones u oposiciones antes de unirlo al código base.

### Protección del Repositorio
Saber que los PRs son importantes no es suficiente si no se aplican restricciones técnicas.  

#### Limitación Real: 
Aunque se confíe en los colaboradores, es necesario configurar el repositorio para limitar su capacidad de unir código directamente.  

#### Reglas de Colaboración:
Se deben implementar medidas técnicas (como se detalla en el video de la clase) para asegurar que nadie pueda saltarse el proceso de revisión y aprobación.

### Colaboración Externa sin invitacin
Es posible contribuir a un proyecto incluso si no eres un colaborador invitado oficialmente al repositorio.  

#### Contribuciones Abiertas 
Como demostró el postulante Andre durante la clase, existen mecanismos (como el flujo de Fork y PR externo) que permiten a cualquier persona proponer mejoras o cambios.  

## Clase 8 Jueves - 30/04/2026
Apuntes de esta clase solo sera de los comandos, ya que esl la ultima
Pese a que borremos las ramas de forma loca, no se borran de forma remota, un ejemplo es
git switch develop
Si hacemos un cambio en una rama, y nos queremos cambiar a otra, nos dice que no hemos guradado los cambios
Nos dice que hagamos un commit para salirnos de esaa rama
```
git stash -m "cambioInnecesario"
```
Si hago 
```
git status
```
no saldra el stash
un stash funciona como una pequeña lista que lo guarda
Guarda sin hacer commits
```
git stash list
```
Y ahora si nos sale lo que hicimos
Con 
```
git stash pop
```
Para llevar todo
Con 
```
git diff nombreRama
```
Podemos ver los cambios, nos los muestra con rojito y verde
Y si hago
```
git diff rama1 rama2
```
Nos sale la diferencia entre las ramas

Git diff --staged
```
git diff --staged .
```
Ver los cambios que ya agregaste al staging (git add) en todos los archivos del directorio actual (.).

Git diff --staged archivo
```
git diff --staged archivo
```
Ver los cambios de un archivo específico que ya están en staging (listos para commit).
