- ¿Qué comando utilizaste en el paso 11? ¿Por qué?
    
    git reset --hard HEAD~1
    
    Para no guardar los cambios se emplea el modificador --hard y para retroceder un commit atrás de la posicion actual de HEAD se emplea HEAD~1 (el número detrás de la virgulilla indica el número de commits que se retrocede)

- ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?
    
    git reset --hard d7ae47a
    
    Se emplea el modificador --hard para que el working copy sea igual al commit al que nos movemos, en este caso el d7ae47a, que es el identificador corto del commit creado en el paso 10 para la rama styled, y accesible a través de git log.

- El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?
    
    Git muestra el mensaje 'Already up to date' y no sucede nada.
    
    No sucede nada, porque el commit de la rama styled es hijo directo del último commit de la rama master. Por lo tanto, ya contiene los cambios de ese commit de master y no tiene ningún cambio nuevo que absorber. Si la rama master continuase su curso con nuevos commits, entonces un merge de styled con master crearía un nuevo commit que combinaría los cambios de ambas ramas.

- El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?
    
    Sí, se produjo un conflicto.
    
    Porque se han realizado modificaciones en todas las líneas de ambos archivos, en una rama usando estilos markdown y en la otra estilos HTML. Git no puede decidir por nosotros que cambios son los que queremos, por lo que hemos resuelto el conflicto quedándonos con las líneas de la versión de la rama styled. Técnicamente hemos hecho un merge, pero en la práctica hemos descartado manualmente todos los cambios de la rama HTML como si no hubiera sucedido un merge.

- El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?
    
    No ha habido ningún conflicto.
    
    Porque ha sido un merge fast forward. Al encontrarse la rama master en el commit inicial, para absorber los cambios de la rama styled, no ha tenido más que mover su puntero hasta el commit final de styled y así absorber todo su trabajo sin necesidad de crear un commit adicional.

- ¿Qué comando o comandos utilizaste en el paso 25?
    
    git log --graph --decorate --pretty=oneline.
    
    El modificador --graph muestra el gráfico de lineas de las ramas, el modificador --decorate muestra los punteros, y el modificador --pretty=online muestra sólo la primera línea de información de cada commit.  
    Como el proyecto no es muy grande, se ve bien el diagrama sin eliminar toda la información extendida que oculta el modificador --pretty=oneline, por lo que se puede prescindir perfectamente de él en este caso. Por otro lado, he comprobado que Git admite también poner --oneline sin más para este modificador.

- El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?

    Si, podria serlo perfectamente, porque para que la rama master absorba los cambios de la rama title, le bastaría con mover su puntero al último commit de title, sin necesidad de crear un nuevo commit con un merge no fast forward.

- ¿Qué comando o comandos utilizaste en el paso 27?
    
    git reset --soft HEAD~1

    El modificador --soft mantiene los cambios en el working copy.

- ¿Qué comando o comandos utilizaste en el paso 28?
    
    git reset --hard HEAD

    El modificador --hard resetea el working copy al commit marcado por HEAD, es decir, el actual, lo cual descarta todo cambio.

- ¿Qué comando o comandos utilizaste en el paso 29?
    
    git branch -D title

    El modificador -D fuerza la eliminación de la rama title, ya que con -d Git no nos deja y muestra el error 'The branch 'title' is not fully merged'. Es decir, no deja borrar sin más una rama que no ha sido mergeada, ya que sin ese puntero no se puede hacer referencia a la rama en un merge, y hay que hacer el borrado a la fuerza.

- ¿Qué comando o comandos utilizaste en el paso 30?
    
    git reset --hard 39ef0fc

    Con el reset movemos los punteros HEAD y master al commit que se creó al hacer el merge, y cuyo hash es accesible mediente git reflog. Esto nos vuelve a dejar el proyecto con el merge rehecho.

- ¿Qué comando o comandos usaste en el paso 32?
    
    git checkout 2ceaf99

    Con el comando checkout movemos el puntero HEAD al primer commit, cuyo identificador corto es 2ceaf99, dato accesible a través de git log.

- ¿Qué comando o comandos usaste en el punto 33?
    
    git checkout master

    Con el comando checkout movemos el puntero HEAD a la rama master, cuyo último commit corresponde a la versión final del poema.

