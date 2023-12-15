## Josephus Intelligenthus
Para resolver este problema, debemos determinar la posición en la que Josephus debería colocarse previo al ritual para ser el último superviviente, el proceso de selección a víctima consiste en un recorrido de saltos, cada vez que un salto coincide con una persona, este es eliminado, el patron continua hasta terminar con el total de personas excepto una.
Existe una formula que determina la posición del único superviviente, que se expresa de la siguiente manera:
```python
def lone_survivor(n):
	if n == 1:
		return 1
	else:
		return (lone_survivor(n - 1) + 1) % n + 1
```


Existe un problema específico de esta función, consiste en que toma en cuenta únicamente un numero plano de saltos, si bien el problema especifica que los saltos dados es únicamente de 1, podrían haber variaciones al problema que puedan arruinar el espacio de la vida.
