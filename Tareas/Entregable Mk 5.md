## Ensayo: Separación de colores:
El arte de la fotografía ha estado con nosotros una gran parte de nuestra historia, básicamente se empezó como una mejora a la pintura, pues ya no era necesario esperar tanto tiempo para tener una representación de algo, esto fue de gran ayuda, especialmente para la investigación y la documentación científica, las primeras fotografías fueron a blanco y negro y fue una verdadera revolución cuando se introdujo la fotografía a color. Los colores han sido lo mas importante en nuestra visión, nos ayudan a detectar elementos y de manera simple a ver el mundo.
Ya habíamos hablado en el ensayo pasado sobre las ventajas de la visión y aquellas técnicas que el hombre prehistórico tenia para poder identificar elementos. Esto sigue siendo de gran importancia y en este ensayo veremos otra cosa que es igual de interesante, nuestra capacidad de ver la hemos heredado a nuestra creación mas inteligente, la inteligencia artificial. 
Podemos empezar por la identificación de elementos, cuando se trata de realizar la búsqueda de un objeto, siempre usamos el color de este para distinguirlo de otros objetos que no estamos buscando, algunos animales tienen mas capacidad que nosotros para poder detectar colores, es bien sabido que algunos insectos tienen conos adicionales que les permiten percibir espectros infrarrojos y ultravioleta, esta es la habilidad que podemos darle a nuestro programa gracias a la implementación de conceptos que se denominan modos de color:

### ¿Pero qué diantres es un modo de color?
Un modo de color o formato de color es una representación del espectro de color visible, es decir, el espectro de color tal como lo perciben nuestros ojos. Entre los modos de color más famosos podemos encontrar RGB, CMYK, Hex, Escala de grises, 1-bit o LAB. 
Estos modos de color hacen posible que el color sea digitalizado en nuestro ordenador, y dependiendo de que modo se color se use, para el programa representara una tarea mas sencilla o descomunalmente mas difícil, de esto se hablara más adelante.
El espectro de color visible siempre depende del tono, la saturación y el brillo o la cantidad de luz que refleja que también se puede traducir como porcentaje de negro. Los colores claros reflejan más luz que los colores oscuros.
No debemos olvidar que los patrones de color son meras representaciones. Es por eso que ciertos colores pueden aparecer en algunos modos de color y no en otros.

### Características del modo RGB
Este modo de color, que dicho sea de paso es el preferido de Photoshop, asigna un valor de intensidad a cada pixel, en imágenes de ocho bits por canal, los valores de intensidad varían entre cero y doscientos cincuenta y cinco por cada componente de los colores que componen este modo de color, siendo rojo, verde y azul. Para fines prácticos en nuestro programa, esto es una tarea imposible, pues se tiene que despejar una gran parte de combinaciones de los tres colores, hablando en términos de gráficos, el color rojo se encuentra en un sector donde no se puede separar de una manera sencilla de los demás colores, pero todo esto es responsable del modo de color, por lo que este no es el apropiado para realizar la tarea

### Características del modo CMYK
Este modo de color es mas completo y se le atribuye la fama de ser el mejor modo para ocasiones donde es necesario realizar impresiones, pero, así como es más completo, también es mas complicado, puesto que se utilizan cuatro canales de colores en lugar de tres, se puede considerar una ventaja que únicamente varié en combinaciones de cero a cien, pero sigue siendo una combinación de colores impresionante y la tarea de realizar la separación de colores es aún más difícil.
Solución: HSV
En estos modos de color podemos representar a los colores como en una cuadricula, donde el centro es blanco y a los alrededores se encuentran todas las combinaciones de colores posible, separar este tipo de grafico no es una tarea nada fácil, además, requerirá una gran cantidad de poder computacional, cosa de la que no muchos disponemos. Pero existe una manera más fácil:
Dentro del modo de color HSV, podemos encontrar que los colores se dividen ya no en una cuadricula, si no en una tira que contiene todos los colores, esto permite que el programa haga un filtrado de colores con la información relacionada a este modo de color y a sus componentes, lo que hace posible que se haga un centrado en los colores que nosotros necesitamos y extraerlos a una imagen separada.

Lo que se necesita para nuestro programa, es primeramente la imagen, esta seguramente vendrá en un formato como jpg o png, mismos formatos que por defecto otros programas usan el modo RGB, de esta manera se necesita primero transformar el modo de color a HSV, de esta manera tendremos un solo canal por el que pasan todos los colores, y podremos realizar el filtrado de estos fácilmente, a continuación se presenta el programa realizado en clase que hace posible esto.

```python
import cv2 as cv
img = cv.imread('f1.png',1)
img2 = cv.cvtColor(img, cv.COLOR_BGR2RGB)
img3 = cv.cvtColor(img2, cv.COLOR_RGB2HSV)

umbralAlto=(0,80,80)
umbralBajo=(10,255,255)

mascara1 = cv.inRange(img3, umbralBajo, umbralAlto)

resultado = cv.bitwise_and(img, img, mask=mascara1)

cv.imshow('img3', img3)
cv.waitKey(0)
cv.destroyAllWindows()
```
