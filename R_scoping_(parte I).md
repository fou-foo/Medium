Hace un par de semanas platicaba con una colega sobre el concepto de scopes en R, y en general en los lenguajes de programación, llegamos a este punto debido a que la documentación del package *bigrquery* hace mención explicita del concepto, pero se refiere a sus características de manera implícita, ósea que la doc. no es autocontenida en este punto y si se desconoce el concepto pudimos haber perdido horas entendiendo la doc. o, peor aun, usar la función solo como caja negra. __XD__

En su momento no pudimos definir el concepto de *scope* sin hacer mención explicita de los enviroments, y recientemente me encontré con la sección 6.2 del libro de __Advanced R__ donde tocan el mismo tema y sin recurrir a conceptos ‘avanzados’ como el uso de los enviroments en __R__ (aquí una paráfrasis):

Lexical scoping:

*Scoping* es el conjunto de reglas que gobierna como el lenguaje __R__ ‘busca’ el valor de un símbolo. En el siguiente ejemplo, el *scoping* es el conjunto de reglas que __R__ aplica para ir del símbolo <code> x</code> a su valor <code> 20</code>:
<code> 
X <- 10
X

> [1] 10
</code>

Comprender el concepto de scoping nos permite:

- Construir herramientas por composición de funciones
- Cancelar o sobrescribir las reglas de evaluación usuales y efectuar evaluación no estándar (en un futuro escribiremos sobre este concepto)

__R__ tiene dos tipos de scoping: __lexical scoping__, implementado automáticamente a nivel de lenguaje y __Dynamic scoping__ (otro concepto sobre el que escribiremos en un futuro), usado en la selección de funciones que se guarda al tipear o digitar en el teclado de manera interactiva en la consola.

El *lexical scoping* busca los valores asociados a símbolos basado en como las funciones son necesitadas cuando son creadas, __no considera solamente como se necesitan cuando son llamadas__. Con *lexical scoping*, no necesitamos conocer como es llamada la función para averiguar cuando el valor de la variable será buscado, solo requerimos de mirar la definición de la función.

El termino ‘lexical’ en el nombre *lexical scoping* no se refiere a su traducción literal relacionado a las palabras o vocabulario de un lenguaje o su diferencia gramática y construcción, pero proviene del término ‘lexing’ de las ciencias de la computación, lo cual es parte de un proceso que convierte codigo representado como texto a piezas con significado que un lenguaje de programación puede entender.

Hay algunos principios básicos detrás de la implementación del *lexical scoping* en __R__ como:

- Enmascaramiento de nombre de funciones y variables

- Comienzo nuevo

- Búsqueda dinámica

Los siguientes post trataran sobre estos tres últimos puntos.