-Contenidos Sobre Git

1-Uso Básico
2-Convenciones
3-Diff
4-Commit

1-Uso Basico 
Los cuatro comandos de arriba copian archivos entre el directorio de trabajo, el stage (también llamado index), y la historia (en la forma de commits).

git add archivos copia archivos (en su estado actual) al stage.
git commit guarda una snapshot del stage como un commit.
git reset -- archivos quita archivos de stage; esto es, que copia archivos del último commit al stage. Usá este comando para "deshacer" un git add archivos. También podés usar git reset para quitar de stage todo lo que hayas agregado.
git checkout -- archivos copia archivos desde el stage al directorio de trabajo. Usá esto para descartar los cambios locales.
Podés usar git reset -p, git checkout -p, o git add -p en lugar de (o en combinación con) especificar archivos particulares para elegir interactivamente qué partes copiar.

También es posible, además, saltarse el stage y hacer check-out de los archivos directamente desde los archivos de commit sin hacer primero el staging.

2-Convenciones
Los commits se muestran en verde como identificadores de 5 caracteres, y apuntan a sus padres. Los branch se muestran en naranja, y apuntan a un commit en particular. El branch actual se identifica por medio de una referencia especial HEAD, que es "adjuntada" al branch. En esta imagen, se muestran los cinco últimos commits, con ed489 siendo el más reciente. main (el branch actual) apunta a este commit, mientras que stable (otro branch) apunta a un antecesor del commit de main.

3-Diff
Hay varias formas de ver las diferencias entre commits. Debajo están algunos ejemplos comunes. Cualquiera de esos comandos pueden tomar opcionalmente como argumento nombres de archivos que limiten las diferencias a los archivos nombrados.

4-Commit
Cuando commiteás, git crea un nuevo objeto de commit utilizando los archivos del stage y establece el padre al commit actual. Entonces apunta el presente branch a este nuevo commit. En la imagen debajo, el branch actual es main. Antes de que se ejecutase el comando, main apuntaba a ed489. Luego, un nuevo commit, f0cec, se crea, con el padre ed489, y luego main se mueve al nuevo commit.

--Glosario de terminos--
Git config
 sirve para definir valores de configuración de Git a nivel de un proyecto global o local. Ejemplo; Git config --global user.name<nombre de usuario>
 
 Git init
 Este comando inicializa un nuevo repositorio en el repositorio local. Ejemplo: git init <nombre_repositorio>

 Git clone 
 Este comando inicializa un nuevo repositorio en el repositorio local clonando íntegramente el contenido de un repositorio remoto que le indiquemos mediante una URL.Ejemplo: git clone<URl_repositorio>

 Git add 
 para comenzar la confirmación de dichos cambios, es necesario pasar todos los archivos que queramos confirmar al área de preparación Ejemplo: git add(opciones)(<archivo_1>)....

 Git commit
 para confirmar dichos archivos y crear una confirmación de cambios la sentencia Ejemplo: git commit(opciones)(<archivo_1>)(<archivo_2>)...(-m<"mensaje de confirmacion">)

 Git log

El comando para ver todas las confirmaciones realizadas en nuestro repositorio Ejemplo : git log

Git diff
Este comando permite ver las diferencias que existen entre las confirmaciones que determinemos.Ejemplo: git diff<hash commit 1><hash commit 2>

Git reset
Puede descartar confirmaciones que ya no necesita usar utilizando el comando git reset Ejemplo: Git reset hash_commit_al_que_volvemos

Git revert
Puede utilizar dicho comando para deshacer de forma segura una confirmación que ya se haya enviado. Ejemplo:Git revert hash_commit

Git tag
se utiliza para etiquetar y marcar una confirmación específica en el historial. Ejemplo: git tg (opciones )(<Nombre_etiqueta>) (<hash_commit>)(<mensaje_etiqueta>)

Git remote
Para conectar al repositorio remoto con el cual nos comunicaremos entre nuestro repositorio local Ejemplo : Git remote add<nombre repositorio> <URL remoto> git remote show <Nombre repositorio>

git branch 
sirve para, cuando se realicen todos los cambios necesarios en el área de trabajo, confirmar una nueva versión y poder sincronizarla con el repositorio remoto. Ejemplo:Git branch (Opciones)(<nombre rama>)(<Commit de comenzo>)

Get checkout 
Para moverse entre las ramas creadas y realizar los cambios necesarios sobre dichas ramas Ejemplo: $ git checkout nombre_rama

Git status 
Podemos comprobar en cualquier momento el estado de la rama en la que nos encontramos para comprobar si existen archivos (o directorios) que tienen cambios que deben de ser confirmados o rechazados.Ejemplo: git status

Git merge
Si se desea conservar todos los cambios e historiales de la rama combinada ejemplo: git merge <nombre_rma>(--no--commit)