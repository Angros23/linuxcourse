# Conocimientos

<details>
    <summary>Shell de Linux</summary>

## Shell de Linux

Esta herramienta nos permite interactuar con el sistema operativo, es decir este es un software  que nos va a servir de interfaz con el sistema operativo, con la peculiaridad de que no tendremos una interfaz gráfica como en otros sistemas operativos (Windows), de igual forma si tienes un Linux que estas usando con interfaz gráfica la forma de ejecutar el mismo es ir a la barra de tareas → abrir la herramienta de aplicaciones y por ultimo abrir el software llamado **Terminal**, el cual se encarga de emular la Shell de Linux. 

Al momento de abrirlo tendrás una ventana que debe de mostrar lo siguiente

```bash
user@machine-name:~$ █
# user: Este es el nombre de usuario con el que hemos iniciado sesión en el equipo.
# machine-name: Este es el nombre que se ha colocado para el équipo.
# ~: Este nos indica que hemos iniciado en la carpeta home 📁
# █: Este símbolo, nos indica en donde estamos ubicados para la escritura de nuestros comandos o interacciones con el sistema, llamado (prompt).
# $: Este símbolo nos indica que estamos con nuestro usuario sin privilegios de administrador.
```

Tenemos varios tipos de shell las cuales son (bash, ssh, zsh), pero ya mas adelante entenderemos que son y para que.

Dentro de la shell o nuestra terminal, podemos ejecutar comandos para comunicarnos con el sistema o realizar alguna tarea, por ejemplo un comando que podríamos utilizar para limpiar nuestra shell/terminal es `clear` otro que es bien basico pero tambíen muy utilizado es `history` este nos permite ver los comandos que hemos realizado en nuestro sistema, una vez ejecutado estos comandos si es la primera vez usando la shell/terminal deberíamos de ver algo como

```bash
user@machine-name:~$ history
		1  clear
		2  history
user@machine-name:~$ █
```

Hasta este punto si estas utilizando la interfaz gráfica, olvídate de ella, solo vamos a utilizar la shell/terminal para poder realizar tareas y otras cosas mas interesantes dentro del sistema operativo, ya en este punto tenemos una pequeña comprensión de en que consiste la misma, aquí todo lo realizaremos por comandos, pero que es un comando ? 

- Que es un comando ?
    - Es una palabra clave que introduciremos en la Shell para realizar una tarea en la misma shell/terminal o en el sistema operativo, ejemplo `history` que ya vimos que nos da un listado de los comandos que hemos escrito

Concretamente hay 4 tipos de comandos para la shell/terminal el primero son los comandos de la propia shell/terminal, es decir el código fuente de la utilidad o comando, forma parte del codifo fuente de la shell/terminal. 

Como podemos saber que tipo es cada uno ? pues para eso utilizaremos el comando `type` si por ejemplo quiero saber que tipo de comando es el mismo comando `type` entonces ejecuto lo siguiente 

```bash
user@machine-name:~$ type type
type is a shell builtin
# aqui nos indica que el comando type es un comando implementado dentro de la misma shell
user@machine-name:~$ █
```

Ahora si intentamos ejecutar el mismo `type` pero esta vez al comando `cp` nos daremos cuenta que este nos retornara algo 

```bash
user@machine-name:~$ type cp
cp is /usr/bin/cp
# Esto nos indica que el comando es ejecutable externo, pero forma parte del sistema operativo
user@machine-name:~$ █
```

Bien, aparte de estos dos, tenemos uno llamado **Shell Funtions** que no son mas que utilidades escritas por un lenguaje de programación que se denomina **ShellScript** el cual es un lenguaje propio de la shell, un punto a tener en cuenta es que tambien puede estar escrito en algún otro lenguaje de programación como por ejemplo `python` 

Por ultimo un tipo de comando que tenemos es el `alias`esto no es mas que una referencia, o un tipo de shortcut para ejecutar una combinacion de comando que queremos que se ejecute simultáneamente, un ejemplo seria el comando `ls` si ejecutamos el siguiente comando veremos que `ls` es un alias

```bash
user@machine-name:~$ type ls
ls is aliased to `ls --color=auto'
# Esto nos indica que el comando es ejecutable externo, pero forma parte del sistema operativo
user@machine-name:~$ █
```

Hasta ahora esto es lo que tenemos que saber de los comandos de Linux, ya sabemos que son programas que van a realizar diferentes tareas, pero los comandos que hemos vistos al introducirlos realizan ya una acción de por si, como lo son el `ls, clear, history` pero si nos fijamos en que al momento de ejecutar `type` este no realiza ninguna acción, esto suscede porque `type` necesita un argumento para poder ejecutarse, por lo general y casi siempre vamos a ver que le podremos pasar parámetros a cada comando que ejecutemos, un ejemplo para el `ls` sería el siguiente `ls -l`  esto nos permitirá organizar el directorio en el que nos encontremos pero con un poco mas de información sobre los archivos o carpetas que se encuentren ahí. 

Hasta este punto, ya hemos entendido en que consisten los comandos y un poco de como utilizarlos, a partir de ahora te estaras preguntando si tengo que saberme de memoria todos estos comandos y la respuesta es **No** no tienes por que saberte de memoria todos los comandos, a continuación daremos inicio a la parte de comandos, y a partir de ahí podrás ver la forma en que podemos conocer sus argumentos que reciben y para que sirven. 
</details>
 
