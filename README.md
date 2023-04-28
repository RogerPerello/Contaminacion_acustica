# Contaminacion acústica

## Objetivo:
Predecir los barrios de Madrid que, en los próximos meses, tendrán una contaminación acústica excesiva. Esto se hace por dos razones:
1. Decidir dónde poner los patinetes, pues una mayor contaminación supone más tráfico, y, por tanto, una necesidad creciente de un transporte alternativo.
2. Conseguir que el Ayuntamiento nos permita ubicar nuestra flota en cerca de los puntos señalados. La legislación en esta materia es volátil e impredecible. A finales de 2022, el número de licencias se redujo un 40%. Por tanto, es bueno disponer de argumentos como este, que nos ayuden a justificar nuestra presencia y ganarnos el favor de las autoridades.

## Fuentes:
- [Histórico de contaminación acústica](https://datos.madrid.es/portal/site/egob/menuitem.c05c1f754a33a9fbe4b2e4b284f1a5a0/?vgnextoid=2ec892874870b410VgnVCM1000000b205a0aRCRD&vgnextchannel=374512b9ace9f310VgnVCM100000171f5a0aRCRD&vgnextfmt=default)

- [Información sobre las estaciones de medida](https://datos.gob.es/en/catalogo/l01280796-contaminacion-acustica-estaciones-de-medida)

- [Límites de contaminación acústica, según la Organización Mundial de la Salud (OMS)](https://madridsalud.es/el-ruido-el-intruso-silencioso/)

## Proceso:
-	Se obtienen datos mensuales de contaminación acústica de Madrid, de 2012 a febrero de 2023, en 31 zonas.
-	De los datos obtenidos, se elige el número de decibelios que superan los barrios el 50% del tiempo. Eso nos permite decir que tal o cual barrio normalmente supera dicha cantidad de decibelios.
-	Se toman los datos como una serie temporal y se hace una primera predicción con suavizado Holt-Winters y un modelo ARIMA, que no es buena.
-	Se transforman los datos con tal de que puedan pasarse a modelos de machine learning.
-	Se codifica una selección automática de modelos para cada uno de los barrios y se obtiene una predicción de los próximos 6 meses buena para 21 de ellos (r2 positiva y error medio absoluto menor a un decibelio). Esta es la predicción de prueba con los últimos meses conocidos:
-	Estas son las predicciones a futuro de los 21 barrios si se observa el período completo:
-	A continuación, se obtiene una predicción buena de los próximos 3 meses para otros tres barrios. Esta es la predicción de prueba con los últimos meses conocidos:
-	Estas son las predicciones a futuro de los 3 barrios si se observa el período completo:
-	Según el estándar de la OMS, una contaminación mayor de 60 decibelios causa molestias a las personas, y más de 65 se traducen en trastornos de personalidad. Por tanto, podemos decir que entre 60 y 65 habría molestias serias. De los barrios predichos, 14 entran en esa categoría. Esta son sus ubicaciones:
