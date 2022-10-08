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