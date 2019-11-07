# Lista de comandos útiles git
Comando | Explicación
------- | -----------
git init | Permite abrir (inicializar) mi repositorio local
git add | Le digo al repositorio que este archivo existe. No es añadir, sino como un "poner a escuchar"
git commit | Envío los últimos cambios del archivos. Es recomendable siempre adjuntar un comentario con el comando -m "mensaje"
git status | Me permite saber como va mi base de datos, si por ejemplo me hace falta hacer commit o por el contrario todo está bien
git show | todos los cambios históricos realizados. La misma función se puede realizar con el comando *git log -nombre de archivo-*
git config --global user.name “pepito” | Configurar globalmente el nombre de usuario
git config --global user.email "pepito@gmail.com" | Configurar globalmente el email de usuario
git config --list | Ver la configuración actual
git config --list --show-origin | Ver en qué archivos está almacenada la configuración actual
git rm --cached | Borrar lo que está en el área de staging
git diff [commit file code] [another commit file code] | Ver diferencias de dos archivos. Si no se pasa ningún flag, lo compara del directorio actual y del staging area
git reset [commit code] [–hard] | Volver atrás en el tiempo :) Si se le pone --hard lo borra todo lo hecho hasta entonces
git checkout [branch] | Cambiar de rama
git commit -am "Mensaje" | Es como un git add y git commit para archivos modificados, no nuevos
git merge {nombre_rama} | Estando en la rama master, fusionamos los cambios de {nombre_rama} con master. Un merge es un commit
git remote add origin {url_repositorio} | Añadir repositorio remoto
git pull origin master --allow-unrelated-histories | Para solucionar el error que al traer el repositorio no nos deja porque los commit de local no son como los de remoto
git push origin master | Envía los cambios a la rama master del repositorio remoto
git log --all --graph | Muestra un log pero con unas rayitas que nos muestra el flujo de branches
git log --all --graph --decorate --oneline |Lo mismo que lo anterior pero más comprimido
git tag -a nombre-del-tag -m "Mensaje" id-del-commit | Para crear un tag (ej. git tag -a v0.1 -m "Primera versión" 6afd9ba)
git show-ref --tags | Para ver los tags
git push origin --tags | Para enviar los tags al repositorio remoto
git tag -d nombre-tag | Borrar un tag existente
git show-branch | Muestra información e historia de las ramas
git show-branch --all | Muestra información de las ramas más detallada
git remote add upstream {url_repositorio_original} | Crea una rama remota upstream. Válido cuando hacemos un fork de un proyecto
git rebase | Hacer cambios silenciosos en una rama y esa rama pegarla en la rama principal como si no hubiera existido la rama de los cambios. Se le hace rebase primero a la rama que cambia y luego a la rama final. 1. *git checkout master* 2. *git rebase esperiment* 3. *git checkout experiment* 4. *git rebase master*
git stash | Guarda cambios hechos en un espacio de memoria temporal
git stash list | Muestra lista de los cambios temporales que tenemos
git stash pop | Vuelve a abrir el stash que estaba guardado
git stash branch {nombre_rama} | Crea {nueva_rama} con los cambios que teníamos en el stash. Posteriormente hay que hacer un commit.
git stash drop | Borra los cambios guardados en stash
git clean | Borra archivos no deseados de nuestro proyecto. Los borra "físicamente"
git clean --dry-run | Hace una simulación y nos indica qué archivos se van a borrar
git cherry-pick {commit_hash} | Estando en la rama master traemos un commit antiguo de otra rama a master
git commit --amend | Agrega los cambios al commit anterior
git reflog | Ver todo el historial de nuestro repositorio
git reset --SOFT HEAD@{numero} | Vuelve al punto del hash del head puesto, dejando el staging como está
git reset --HARD HEAD@{numero} | Vuelve al punto del hash del head puesto, incluyendo el staging
git grep {palabra} | Busca, en el código, dónde se utiliza {palabra}
git grep -n {palabra} | Nos devuelve la búsqueda indicando la línea donde está {palabra}
git grep -c {palabra} | Devuelve el número de veces que se utiliza {palabra} por archivo
git log -s {palabra} | Busca {palabra} en los commits
git shortlog | Nos muestra un log por persona del equipo que ha hecho commits
git blame {archivo} | Muestra un historial de quién y cuándo se hicieron los cambios en ese archivo

