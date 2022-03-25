# pdih
Repositorio de la asignatura de perifericos y dispositivos de interfaz humana 
Trabajo realizado por Enrique Gonzalez y Aaron Rivet
-PRACTICA 1.
En esta primera practica hemos desarrollado las siguientes funciones
• gotoxy(int x, int y): coloca el cursor en una posición determinada
    Esta funcion recibe una x y una y, ambos enteros que determinan la posicion del cursor 
• setcursortype(int tipo_cursor): fijar el aspecto del cursor, debe admitir tres valores: INVISIBLE, NORMAL y GRUESO.
    Esta funcion recibe un entero que determina el tipo de cursor que se va a mostrar.
    Hemos realizado un switch de 0-2 en el cual cada una de las opciones nos coloca el cursor de dicho modo.
• setvideomode(BYTE modo): Fija el modo de video deseado. 
    Para ello recibe el parametro "modo" que es de tipo BYTE, que se pasa al registro al, 
    ocasionando asi el cambio en el modo de video.    
• getvideomode(): obtiene el modo de video actual
    Para conseguir esto creamos una variable int llamada modo_video en la cual se guardará
    el resultado de consultar el registro outregs.h.al donde se situa el modo de video que 
    se esta ejecutando actualmente
• textcolor(int color): modifica el color de primer plano con que se mostrarán los caracteres
    En esta funcion guardamos en los ultimos 4 bits mediante la variable color, el color de los caracteres.
    Los 4 bits restantes los ponemos a 0 para que no se modifique el color del fondo
• textbackground(int color): modifica el color de fondo con que se mostrarán los caracteres
    En esta funcion dejamos a 0 los 4 bits menos significativos del registro bl y modificamos los mas
    significativos desde la variable color, para modificar el color del fondo. 
• clrscr(): borra toda la pantalla
• cputchar(char letra, unsigned char cfondo, unsigned char cletra): escribe un carácter en pantalla con el color indicado actualmente
      Esta funcion hace uso de las funciones textcolor y textbackground con el añadido de introducir un parametro letra 
      que es el el caracter a modificar
• getche(): obtiene un carácter de teclado y lo muestra en pantalla 

Para la realizacion del main hemos creado un menú para la facil interpretacion de las funciones realizadas.
Para resolver el problema que nos apareció al castear de int a char lo que hemos hecho es restarle 48 a ciertas variables
para que a la hora de castearlas e introducirlas a las funciones no den error.
