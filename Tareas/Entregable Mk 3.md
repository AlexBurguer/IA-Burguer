# Ensayo los 8 alfiles
Para poder resolver este problema, primero necesitamos entender el problema:
Se colocan ocho alfiles, cuatro de los cuales son blancos y los otros cuatro negros, en un tablero de ajedrez reducido, en la figura se muestra una cuadricula de cuatro por cinco casillas. El problema consiste en hacer que los alfiles negros intercambien posiciones con los blancos, ningún alfil podrá atacar al del color opuesto. Se deben alternar los movimientos, primero uno blanco y luego uno negro, luego uno blanco y así sucesivamente. ¿Cuál es el mínimo numero de movimientos en que se puede conseguir?
Lo primero que debemos hacer es analizar la situación, no todos los alfiles pueden caber en el mismo cuadrante, esto es, por que cuatro de ellos se mueven únicamente por casillas blancas, mientras que los restantes se mueven únicamente por casillas negras, además, debemos definir el conteo de movimientos, pues no es lo mismo realizar la cuenta por pieza que por par, si bien la definición formal de un movimiento es el cambio de posición de una pieza, se podría decir que un movimiento corresponde a pieza por pieza y no por turno, ya que turno toma en cuenta los movimientos de dos piezas intercaladas, esto es, al movimiento de una pieza negra y el movimiento seguido de una pieza blanca se considera que es un turno, para fines prácticos se realizara el conteo de movimientos pieza por pieza, pues es lo que mas se asemeja al concepto deseado.
Para obtener la cantidad mínima de movimientos debemos saber como resolver el problema, crear un proceso y a partir de la información particular de cada turno, llevarlo a la mayor escala, que en definitiva es la completitud de todas las piezas. Para esto se necesitan de ciertas directivas, por ejemplo, es totalmente imposible que con un solo movimiento una pieza pueda ser cambiada de lugar, por lo que la cantidad mínima de movimientos es de por lo menos dos y en los casos donde mas movimientos se necesita es de tres. Ahora, cada alfil deberá corresponder al color sobre la casilla en la que se encuentra y realizar el movimiento para el intercambio en una casilla del mismo color que el de salida, esto significa que si un alfil sale de una casilla negra, deberá cambiar de posición con un alfil blanco que este posicionado en otra casilla negra, de modo que pueden efectuar un cambio exitoso, pues, un alfil que parte de casillas negras, siempre se moverá por casillas de ese mismo color. Esto provocaría que tuviéramos dos alfiles negros en la fila centra, y sin que existan alfiles del otro color en la misma fila, permitiría realizar los mismos movimientos con los elementos del otro color, de manera que podríamos colocar los alfiles del lado opuesto, este mismo proceso se repite con los alfiles restantes, lo que permite dar una cantidad de turnos total de nueve turnos, esto debido a que un par de alfiles terminaran por usar un turno extra para poder acomodarse de una manera exitosa, lo que al finalizar tendremos un total de 18 movimientos.
El problema, a diferencia de otros, se puede resolver de una manera mas intuitiva, y el hecho de que este tablero este reducido significa que se usa como referencia para otros problemas o el mismo que tienen una cantidad infinita de casillas, pues, no fueron raros los resultados en la red de como el problema de los ocho alfiles es usado también para representar el problema de las reinas o de las torres.


Estos problemas nos pueden parecer un sin sentido, pues tan solo podemos pensar en cosas como ¿Quién querría saber esto?, la existencia de este tipo de problemas tiene impregnada ciertas esencias de lo que es nuestra forma de pensar y de hecho para una computadora que realiza el proceso a prueba y error o de la manera mas bruta posible, llegara a la conclusión de una manera fácil y rápida, primero que nada, debemos de tomar en cuenta que los equipos de hoy en día tienen una capacidad de computo impresionante, y que el problema es resoluble únicamente identificando los posibles lugares en los que los alfiles pueden intercambiar lugares, y aunque para nosotros la visión de un espacio relativamente grande es difícil, para nuestro ordenador no lo es.
Este tipo de problemas ayudo de gran manera a la generación de conocimiento sobre la resolución de problemas en las inteligencias artificiales, además, nos dio la oportunidad de ver el potencial de estas tecnologías, significando que habíamos podido presenciar como lo resolvía y que tan rápido lograba hacerlo, además, como también aprende los procesos relacionados a dichos juegos, adquieren la capacidad de usar este tipo de algoritmos para problemas mas complejos. 
A través de este tipo de instrucciones es como las inteligencias artificiales son entrenadas, este tipo de problemas no son más que meras analogías para la resolución de problemas mas complejos, su experimentación y resultados han ayudado a los expertos a entender un poco mas el modelo de aprendizaje tanto de las inteligencias artificiales como del propio hombre. Este tipo de juegos tiene sus propias reglas y sus propios movimientos que pueden llegar que a generar situaciones verdaderamente difíciles para aquello que los intenta resolver y como la cantidad de datos a analizar puede ser enorme, supone un gran esfuerzo para nosotros pero las inteligencias artificiales no tienen problema alguno en la resolución de estos, aunque, no necesariamente, la capacidad de estas tecnologías para la resolución de problemas es determinada de acuerdo a las entradas y salidas que se le asignen y allí es donde debemos de tomar en cuanta todas las variables que un entorno practico tiene, si se trata de jugar un juego real, debe de tener en cuenta aspectos como la forma, iluminación y materiales de los objetos que vaya a manipular y con esta información establecer la estrategia mas eficiente para resolver el problema, lo ideal es que lo hiciera pero en este campo siempre esta presente la mejora continua, por lo que siempre habrá lugar para aprender de errores o de hacer recálculos para encontrar las mejores soluciones ante problemas que se vayan presentando.
Si bien puede no parecer lo suficientemente importante, este tipo de problemas nos ayuda a comprender tanto a las inteligencias artificiales como a nosotros mismos, lo que nos da paso a un mejor análisis que puedan llevar a la resolución de problemas reales.







## Solución
Para visualizar este problema de una mejor perspectiva, debemos enumerar las casillas del tablero en filas, de izquierda a derecha y de arriba hacia abajo, el tablero es de veinte casillas por lo que la esquina superior izquierda tendrá el numero uno y la esquina inferior derecha tendrá el numero veinte, ahora, de acuerdo a internet y por razones de agotamiento físico y mental, los movimientos vienen dados por:

Pieza en 18 mueve a 15 y Pieza en 3 mueve a 6.

Pieza en 17 mueve a 8 y Pieza en 4 mueve a 13.

Pieza en 19 mueve a 14 y Pieza en 2 mueve a 7.

Pieza en 15 mueve a 5 y Pieza en 6 mueve a 16.

Pieza en 8 mueve a 3 y Pieza en 13 mueve a 18.

Pieza en 14 mueve a 9 y Pieza en 7 mueve a 12.

Pieza en 5 mueve a 10 y Pieza en 16 mueve a 11.

Pieza en 9 mueve a 19 y Pieza en 12 mueve a 2.

Pieza en 10 mueve a 4 y Pieza en 11 mueve a 7.

Pieza en 20 mueve a 10 y Pieza en 1 mueve a 11.

Pieza en 3 mueve a 9 y Pieza en 18 mueve a 12.

Pieza en 10 mueve a 13 y Pieza en 11 mueve a 8.

Pieza en 19 mueve a 16 y Pieza en 2 mueve a 5.

Pieza en 16 mueve a 1 y Pieza en 5 mueve a 20.

Pieza en 9 mueve a 6 y Pieza en 12 mueve a 15.

Pieza en 13 mueve a 7 y Pieza en 8 mueve a 14.

Pieza en 6 mueve a 3 y Pieza en 15 mueve a 18.

Pieza en 7 mueve a 2 y Pieza en 14 mueve a 19.
