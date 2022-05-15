# desafio4BorbotonesEDA

El código fue escrito en python 3.9.6 por lo que se recomienda ejecutar el notebook con esa versión.

Descripción del problema: Se eligió el dataset "League of Legends Ranked Games" que comprende 61 columnas que representan datos usados al interior de partidas del juego con una extensión de 51490 filas obtenidas de partidas reales a través de la API de Riot games junto con herramientas de terceros para obtener valores faltantes. Se decidió cortas columnas del dataset por considerarlas no tan relevantes de manera que se pudiera reducir la dimensionalidad de los datos y acotar el poder de procesamiento necesario para la clasificación. En este último aspecto se busca poder clasificar la columna "winner" que representa el equipo ganador de la partida, de manera que se pueda saber anticipadamente el equipo ganador de la partida dados las features relevantes extraídas.
De esta forma la cantidad de columnas utilizadas se reducen a las siguientes:
![image](https://user-images.githubusercontent.com/82004309/168493319-0c245b01-b03f-4e72-90df-8723cbdcfa9e.png)

Descripción del algoritmo: Para abordar la clasificación antes mencionada sobre el dataset se implementar dos redes neuronales. En primer lugar se tiene una red hecha con la biblioteca keras. En segundo lugar una red en forma matricial para sacar provecho de la multiplicación de matrices de la biblioteca Numpy. Ambas tienen una topología de 4 capas ocultas, con una cantidad de 20, 30, 20 y 12 neuronas respectivamente. Las redes fueron alimentadas con una fracción del set de datos original (4%) que previamente fueron separados en sets de entrenamiento y de prueba en proporción 70/30 respectivamente y ambos grupos fueron normalizados respecto del set de entrenamiento.
Una vez los modelos son creados a partir del set de datos de entrenamiento se prueban con el set de prueba para mejorar su eficacia a través de la modificación de los pesos de las neuronas dado el error cuadrático medio obtenido al final de la red entre los resultados esperados y los resultados obtenidos. El proceso anterior se realiza un número arbitrario de veces buscando mejorar el error cuadrático medio obtenido mientras que la red aprende de los valores esperados.
En última instancia se hace una prueba final del modelo creado y entrenado para cuantificar la medidad de precisión de la red a la hora de clasificar tuplas nuevas de datos.
Se creó tambien un modelo de clasificación de perceptrón multicapa de la biblioteca scikit learn con una estructura similar a la de los dos anteriores (todo dentro de lo que el modelo permite ser ajustado) para tener una idea de los resultados en otro tipo de instancias de redes neuronales. 


#un link a la presentación en video.
https://www.youtube.com/watch?v=muwTMlCuBzQ 
