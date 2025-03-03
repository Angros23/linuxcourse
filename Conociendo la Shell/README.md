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
 
## Commandos

<details>
<summary>Comandos de información sobre de los mismos help, man, info, whatis y aprops</summary>

1. <details>
    <summary>Help</summary>

    ## Comando help

    Si queremos obtener la información de un comando así como cuales son sus parámetros o para que sirve.  

    Para esto ejecutaremos algunos de los comandos que Linux nos ofrece a la hora de querer obtener estas informaciones de los comandos, el primero de ellos es el `help` la manera de ejecutar este comando es simplemente ejecutando `help`  y luego el comando que queremos saber información un ejemplo para saber como se utiliza el `type`  deberíamos de ejecutar algo como

    ```bash
    user@machine-name:~$ help type
    type: type [-afptP] name [name ...]
    For each NAME, indicate how it would be interpreted if used as a
        command name.
        
        Options:
        -a        display all locations containing an executable named NAME;
                    includes aliases, builtins, and functions, if and only if
                    the `-p' option is not also used
        -f        suppress shell function lookup
        -P        force a PATH search for each NAME, even if it is an alias,
                    builtin, or function, and returns the name of the disk file
                    that would be executed
        -p        returns either the name of the disk file that would be executed,
                    or nothing if `type -t NAME' would not return `file'
        -t        output a single word which is one of `alias', `keyword',
                    `function', `builtin', `file' or `', if NAME is an alias,
                    shell reserved word, shell function, shell builtin, disk file,
                    or not found, respectively
        
        Arguments:
        NAME      Command name to be interpreted.
        
        Exit Status:
        Returns success if all of the NAMEs are found; fails if any are not found.

    user@machine-name:~$ █
    ```

    **[-afptP]:** Siempre que vemos estos corchetes nos indica que estos parametros son opcionales

    **name:** Luego en donde nos coloca name nos indica que tenemos que colocar un nombre, haciendo alusión a que debemos de colocar el comando deseado.

    **[name ...]**: Esto nos indica que podemos colocar de manera opcional mas de un nombre de comandos para procesar. 

    Ojo 👀: El comando `help` solo nos da información de comandos que se encuentran y forman parte de la misma shell/terminal, si queremos información sobre los comandos que no pertenecen a estos pues ejecutamos el parámetro `--help` la mayoría (por no decir todos) tienen este parametro y con esto obtenemos la información del comando que deseamos ejecutar un ejemplo sería. 

    ```bash
    user@machine-name:~$ ls --help
    Modo de empleo: ls [OPCIÓN]... [FICHERO]...
    Muestra información acerca de los FICHEROs (del directorio actual por defecto).
    Ordena las entradas alfabéticamente si no se especifica ninguna de las
    opciones -cftuvSUX ni --sort.

    Los argumentos obligatorios para las opciones largas son también obligatorios
    para las opciones cortas.
    -a, --all                  no oculta las entradas que comienzan con .
    -A, --almost-all           no muestra las entradas . y .. implícitas
        --author               con -l, imprime el autor de cada fichero
    -b, --escape               imprime escapes en estilo C para los caracteres no
                                gráficos
        --block-size=SIZE      with -l, scale sizes by SIZE when printing them;
                                e.g., '--block-size=M'; see SIZE format below
    -B, --ignore-backups       do not list implied entries ending with ~
    -c                         with -lt: sort by, and show, ctime (time of last
                                modification of file status information);
                                with -l: show ctime and sort by name;
                                otherwise: sort by ctime, newest first
    -C                         list entries by columns
        --color[=WHEN]         colorize the output; WHEN can be 'always' (default
                                if omitted), 'auto', or 'never'; more info below
    -d, --directory            list directories themselves, not their contents
    -D, --dired                generate output designed for Emacs' dired mode
    -f                         no ordena, utiliza -aU, no utiliza -ls --color
    -F, --classify             añade un indicador (uno de */=@|) a las entradas
        --file-type            similar, pero no añade '*'
        --format=PALABRA       across -x, commas -m, horizontal -x, long -l,
                                single-column -1, verbose -l, vertical -C
        --full-time            como -l --time-style=full-iso
    -g                         como -l, pero no lista el propietario
        --group-directories-first
                                agrupa directorios antes que los ficheros;
                                se puede añadir una opción --sort, pero cualquier
                                uso de --sort=none (-U) desactiva la agrupación
    -G, --no-group             in a long listing, don't print group names
    -h, --human-readable       with -l and -s, print sizes like 1K 234M 2G etc.
        --si                   likewise, but use powers of 1000 not 1024
    -H, --dereference-command-line
                                sigue los enlaces simbólicos en la línea de
                                órdenes
        --dereference-command-line-symlink-to-dir
                                sigue cada enlace simbólico en la línea de
                                órdenes que apunte a un directorio
        --hide=PATRÓN          no lista las entradas implícitas que coinciden
                                con el patrón de shell PATRÓN
                                (las opciones -a o -A tienen prioridad)
        --hyperlink[=WHEN]     hyperlink file names; WHEN can be 'always'
                                (default if omitted), 'auto', or 'never'
        --indicator-style=WORD  append indicator with style WORD to entry names:
                                none (default), slash (-p),
                                file-type (--file-type), classify (-F)
    -i, --inode                print the index number of each file
    -I, --ignore=PATTERN       do not list implied entries matching shell PATTERN
    -k, --kibibytes            default to 1024-byte blocks for disk usage;
                                used only with -s and per directory totals
    -l                         utiliza un formato de listado largo
    -L, --dereference          al mostrar la información de un fichero para un
                                enlace simbólico, muestra la información del
                                fichero al que apunta el enlace en lugar de la
                                del propio enlace
    -m                         rellena el ancho con una lista de entradas
                                separadas por comas
    -n, --numeric-uid-gid      like -l, but list numeric user and group IDs
    -N, --literal              print entry names without quoting
    -o                         like -l, but do not list group information
    -p, --indicator-style=slash
                                append / indicator to directories
    -q, --hide-control-chars   print ? instead of nongraphic characters
        --show-control-chars   show nongraphic characters as-is (the default,
                                unless program is 'ls' and output is a terminal)
    -Q, --quote-name           enclose entry names in double quotes
        --quoting-style=WORD   use quoting style WORD for entry names:
                                literal, locale, shell, shell-always,
                                shell-escape, shell-escape-always, c, escape
                                (overrides QUOTING_STYLE environment variable)
    -r, --reverse              invierte el orden, en su caso
    -R, --recursive            muestra los subdirectorios recursivamente
    -s, --size                 muestra el tamaño de cada fichero, en bloques
    -S                         sort by file size, largest first
        --sort=WORD            sort by WORD instead of name: none (-U), size (-S),
                                time (-t), version (-v), extension (-X)
        --time=WORD            with -l, show time as WORD instead of default
                                modification time: atime or access or use (-u);
                                ctime or status (-c); also use specified time
                                as sort key if --sort=time (newest first)
        --time-style=TIME_STYLE  time/date format with -l; see TIME_STYLE below
    -t                         ordena por la fecha de modificación, el más
                                reciente primero
    -T, --tabsize=COLS         establece los topes de tabulación a cada COLS
                                en lugar de 8
    -u                         with -lt: sort by, and show, access time;
                                with -l: show access time and sort by name;
                                otherwise: sort by access time, newest first
    -U                         do not sort; list entries in directory order
    -v                         natural sort of (version) numbers within text
    -w, --width=COLS           set output width to COLS.  0 means no limit
    -x                         list entries by lines instead of by columns
    -X                         sort alphabetically by entry extension
    -Z, --context              print any security context of each file
    -1                         list one file per line.  Avoid '\n' with -q or -b
        --help     muestra esta ayuda y finaliza
        --version  informa de la versión y finaliza

    El argumento TAM es un entero y una unidad opcional (ejemplo: 10M es 10*1024*1024).
    Las unidades son K,M,G,T,P,E,Z,Y (potencias de 1024) o KB,MB, ... (potencias de 1000).

    The TIME_STYLE argument can be full-iso, long-iso, iso, locale, or +FORMAT.
    FORMAT is interpreted like in date(1).  If FORMAT is FORMAT1<newline>FORMAT2,
    then FORMAT1 applies to non-recent files and FORMAT2 to recent files.
    TIME_STYLE prefixed with 'posix-' takes effect only outside the POSIX locale.
    Also the TIME_STYLE environment variable sets the default style to use.

    El uso de color para distinguir los tipos de ficheros está desactivado
    por omisión y cuando se usa --color=never. Con --color=auto, ls produce
    códigos de color solamente cuando la salida estándar está conectada a una
    terminal. La variable de entorno LS_COLORS puede cambiar las opciones.
    Utilice la orden dircolors para establecerla.

    Estado de salida:
    0  si todo fue bien
    1  si hubo problemas menores (p. ej., no poder acceder a un subdirectorio),
    2  si hubo un serio problema (p. ej., no se puede acceder al argumento de la
                                    línea de órdenes)

    ayuda en línea sobre GNU coreutils: <https://www.gnu.org/software/coreutils/>
    Report ls translation bugs to <https://translationproject.org/team/>
    Full documentation at: <https://www.gnu.org/software/coreutils/ls>
    or available locally via: info '(coreutils) ls invocation'

    user@machine-name:~$ █
    ```
    </details>

2. <details>
    <summary>Man</summary>
    Con el comando `man` podrÍamos obtener la información de `ls` como vemos en el siguiente caso, este es muy parecido al mismo help.

    ```bash
    user@machine-name:~$ man ls
    NAME
        ls - list directory contents

    SYNOPSIS
        ls [OPTION]... [FILE]...

    DESCRIPTION
        List information about the FILEs (the current directory by default).  Sort entries alphabetically if none of -cftuvSUX nor --sort is specified.

        Mandatory arguments to long options are mandatory for short options too.

        -a, --all
                do not ignore entries starting with .

        -A, --almost-all
                do not list implied . and ..

        --author
                with -l, print the author of each file

        -b, --escape
                print C-style escapes for nongraphic characters

        --block-size=SIZE
                with -l, scale sizes by SIZE when printing them; e.g., '--block-size=M'; see SIZE format below

        -B, --ignore-backups
                do not list implied entries ending with ~

        -c     with -lt: sort by, and show, ctime (time of last modification of file status information); with -l: show ctime and sort by name; otherwise:
                sort by ctime, newest first

        -C     list entries by columns

        --color[=WHEN]
                colorize the output; WHEN can be 'always' (default if omitted), 'auto', or 'never'; more info below

        -d, --directory
        
        -D, --dired
                generate output designed for Emacs' dired mode

        -f     do not sort, enable -aU, disable -ls --color

        -F, --classify
                append indicator (one of */=>@|) to entries

        --file-type
                likewise, except do not append '*'

        --format=WORD
                across -x, commas -m, horizontal -x, long -l, single-column -1, verbose -l, vertical -C

        --full-time
                like -l --time-style=full-iso

        -g     like -l, but do not list owner

        --group-directories-first
                group directories before files;

                can be augmented with a --sort option, but any use of --sort=none (-U) disables grouping

        -G, --no-group
                in a long listing, don't print group names

        -h, --human-readable
                with -l and -s, print sizes like 1K 234M 2G etc.

        --si   likewise, but use powers of 1000 not 1024

        -H, --dereference-command-line
                follow symbolic links listed on the command line

        --dereference-command-line-symlink-to-dir
                follow each command line symbolic link

                that points to a directory
        
        --hide=PATTERN
                do not list implied entries matching shell PATTERN (overridden by -a or -A)

        --hyperlink[=WHEN]
                hyperlink file names; WHEN can be 'always' (default if omitted), 'auto', or 'never'

        --indicator-style=WORD
                append indicator with style WORD to entry names: none (default), slash (-p), file-type (--file-type), classify (-F)

        -i, --inode
                print the index number of each file

        -I, --ignore=PATTERN
                do not list implied entries matching shell PATTERN

        -k, --kibibytes
                default to 1024-byte blocks for disk usage; used only with -s and per directory totals

        -l     use a long listing format

        -L, --dereference
                when showing file information for a symbolic link, show information for the file the link references rather than for the link itself

        -m     fill width with a comma separated list of entries

        -n, --numeric-uid-gid
                like -l, but list numeric user and group IDs

        -N, --literal
                print entry names without quoting

        -o     like -l, but do not list group information

        -p, --indicator-style=slash
                append / indicator to directories

        -q, --hide-control-chars
                print ? instead of nongraphic characters
        
        --show-control-chars
                show nongraphic characters as-is (the default, unless program is 'ls' and output is a terminal)

        -Q, --quote-name
                enclose entry names in double quotes

        --quoting-style=WORD
                use quoting style WORD for entry names: literal, locale, shell, shell-always, shell-escape, shell-escape-always, c, escape (overrides QUOT‐
                ING_STYLE environment variable)

        -r, --reverse
                reverse order while sorting

        -R, --recursive
                list subdirectories recursively

        -s, --size
                print the allocated size of each file, in blocks

        -S     sort by file size, largest first

        --sort=WORD
                sort by WORD instead of name: none (-U), size (-S), time (-t), version (-v), extension (-X)

        --time=WORD
                with -l, show time as WORD instead of default modification time: atime or access or use (-u); ctime or status (-c); also use specified time
                as sort key if --sort=time (newest first)

        --time-style=TIME_STYLE
                time/date format with -l; see TIME_STYLE below

        -t     sort by modification time, newest first

        -T, --tabsize=COLS
                assume tab stops at each COLS instead of 8

        -u     with -lt: sort by, and show, access time; with -l: show access time and sort by name; otherwise: sort by access time, newest first

        -U     do not sort; list entries in directory order
        
        -v     natural sort of (version) numbers within text

        -w, --width=COLS
                set output width to COLS.  0 means no limit

        -x     list entries by lines instead of by columns

        -X     sort alphabetically by entry extension

        -Z, --context
                print any security context of each file

        -1     list one file per line.  Avoid '\n' with -q or -b

        --help display this help and exit

        --version
                output version information and exit

        The SIZE argument is an integer and optional unit (example: 10K is 10*1024).  Units are K,M,G,T,P,E,Z,Y (powers of 1024) or KB,MB,...  (powers  of
        1000).

        The  TIME_STYLE  argument  can  be full-iso, long-iso, iso, locale, or +FORMAT.  FORMAT is interpreted like in date(1).  If FORMAT is FORMAT1<new‐
        line>FORMAT2, then FORMAT1 applies to non-recent files and FORMAT2 to recent files.  TIME_STYLE prefixed with 'posix-' takes effect  only  outside
        the POSIX locale.  Also the TIME_STYLE environment variable sets the default style to use.

        Using color to distinguish file types is disabled both by default and with --color=never.  With --color=auto, ls emits color codes only when stan‐
        dard output is connected to a terminal.  The LS_COLORS environment variable can change the settings.  Use the dircolors command to set it.

    Exit status:
        0      if OK,

        1      if minor problems (e.g., cannot access subdirectory),

        2      if serious trouble (e.g., cannot access command-line argument).

    AUTHOR
        Written by Richard M. Stallman and David MacKenzie.

    REPORTING BUGS
        GNU coreutils online help: <https://www.gnu.org/software/coreutils/>
        Report ls translation bugs to <https://translationproject.org/team/>

    COPYRIGHT
        Copyright © 2018 Free Software Foundation, Inc.  License GPLv3+: GNU GPL version 3 or later <https://gnu.org/licenses/gpl.html>.
        This is free software: you are free to change and redistribute it.  There is NO WARRANTY, to the extent permitted by law.

    SEE ALSO
        Full documentation at: <https://www.gnu.org/software/coreutils/ls>
        or available locally via: info '(coreutils) ls invocation'
    user@machine-name:~$ █
    ```
    </details>

3. <details>
    <summary>Whatis</summary>
    Con el comando `whatis` podremos obtener una pequeña descripción de que realiza o en que se emplea el comando, por ejemplo si usamos `whatis ls` veremos que nos indica que es para listar directorios. Ahora bien, sabiendo esto veremos que no siempre el comando `whatis` funciona, para esos casos veremos el siguiente commando llamado `info`

    ```bash
    user@machine-name:~$ whatis ls
    ls (1)                  - list directory contents
    ```
   </details>

</details>