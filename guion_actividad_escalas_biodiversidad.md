# Instrucciones para realizar el ejercicio denominado "el efecto de la escala espacial en el significado del concepto de diversidad biológica en una comunidad"


> + **_Versión_**: 2021-2022
> + **_Asignatura (grado)_**: Ecología (CCAA)
> + **_Autor_**: Curro Bonet-García (fjbonet@uco.es)



## Objetivos

Esta actividad tiene como finalidad última la aplicación del concepto de diversidad (a través del índice de Shannon) a una escala espacial diferente a la que vimos en la [práctica 3](https://rawcdn.githack.com/aprendiendo-cosas/P_shannon_ecologia_ccaa/2021_2022/guion_practica_mapa_biodiversidad.html). Desde un punto de vista docente este tipo de ejercicios son muy útiles porque nos permiten entrenar habilidades cognitivas superiores (trasferir conocimiento de un ámbito a otro, investigar, reflexionar, tomar conciencia del avance en el razonamiento, etc.). Como siempre, los objetivos concretos son de dos tipos:

 + Disciplinares (tienen que ver con la ecología): Se muestran a continuación en orden de complejidad creciente:
   + Fijar los conceptos de diversidad (índice de Shannon) y riqueza (número de especies).
   + Reflexionar sobre los patrones de distribución espaciales de la diversidad en un territorio concreto (Andalucía).
   + Afianzar la conexión entre la identificación del patrón espacial (ej. hay más diversidad al oeste) y las causas que explican dicho patrón (ej. esto se debe a que hacia el oeste llueve más).
   + Comprender que el concepto de diversidad tiene significados diferentes dependiendo de su escala espacial de aplicación.
   + Descubrir un "nuevo" tipo de diversidad a partir de la observación de patrones de aplicación del índice de Shannon a dos escalas: escala de "comunidad pequeña" (polígonos mapa de vegetación) y a escala de "paisaje" (espacios protegidos de Andalucía)
 + Instrumentales (tienen que ver con el manejo de herramientas de uso común):
    + Entrenar la capacidad de reflexión ante un problema nuevo partiendo de información incompleta.
    + Poner en práctica lo ya aprendido sobre búsqueda de bibliografía científica.
    + Mejorar las habilidades de redacción en un contexto con incertidumbre. 


Antes de detallar en qué consiste el ejercicio, lee el siguiente apartado en el que se describe el contexto ecológico planteado.



## Contextualización ecológica

Como sabemos, la cantidad de especies que hay en una comunidad ecológica es importante para entender muchas características estructurales y funcionales de los ecosistemas. En concreto hay dos descriptores importantes en una comunidad ecológica: riqueza de especies y diversidad. La riqueza de especies es fácil de entender: es la cantidad de especies que hay en una comunidad dada. Es un descriptor importante, pero tiene varios problemas para ser usado de manera estándar. Uno de ellos es que depende del esfuerzo de muestreo de especies. Es posible que lugares con muchas especies den valores bajos en este parámetro si no han sido suficientemente muestreados. Para minimizar este problema se usan otros indicadores de diversidad. En nuestro caso trabajamos con el[ índice de Shannon](https://es.wikipedia.org/wiki/%C3%8Dndice_de_Shannon), que tiene en cuenta tanto el número de especies como su abundancia relativa. 

La diversidad biológica se distribuye por la Tierra según una serie de patrones espaciales que vimos en la [práctica 3](ttps://rawcdn.githack.com/aprendiendo-cosas/P_shannon_ecologia_ccaa/2021_2022/guion_practica_mapa_biodiversidad.html). Dichos patrones ponen de manifiesto cómo se comporta la diversidad frente a ciertos factores ambientales. Por ejemplo:

+ Hay un patrón de distribución de la diversidad en función de la latitud. En el Ecuador hay más diversidad que en los polos. 
+ Heterogeneidad ambiental. Se ha comprobado que los lugares más heterogéneos desde un punto de vista ambiental (más cambios en las condiciones climáticas, por ejemplo), albergan más diversidad.
+ Dureza ambiental. En multitud de ocasiones se ha comprobado que los lugares sometidos a más perturbaciones o más fuentes de estrés, tienen menos diversidad biológica.

[Este](https://github.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_ecologia_ccaa/raw/2019_2020/biblio/biodiversity_patterns.pdf) artículo describe con detalle estos patrones y algunos más. El foco de esta actividad es que, si bien los factores anteriores explican la distribución de la diversidad, lo hacen de forma distinta dependiendo de la escala espacial a la que "observamos". 



## Planteamiento del problema

En el curso 2019-2020, al terminar la práctica sobre el mapa de biodiversidad ([práctica 3](ttps://rawcdn.githack.com/aprendiendo-cosas/P_shannon_ecologia_ccaa/2021_2022/guion_practica_mapa_biodiversidad.html)), una estudiante me hizo la siguiente pregunta: "*Con esto que hemos visto podemos obtener un mapa del índice de Shannon de cada comunidad de Sierra Nevada. Pero, ¿cómo se calcularía el índice de Shannon de todo el espacio protegido?, ¿se calcularía haciendo el promedio de todos los puntos o habría que calcular desde el principio el índice de Shannon considerando que todos los puntos pertenecieran a la misma comunidad?*" No supe contestar en ese momento, pero me comprometí a darle una respuesta más tarde.

Me puse a trabajar y calculé el índice de Shannon para toda Sierra Nevada (a este índice le llamaremos "Shannon a escala de paisaje"), así como el valor promedio del índice de Shannon de todas las comunidades del espacio protegido ("Shannon a escala de comunidad"). Como sospechaba, los valores eran diferentes. Aunque sospeché que había algo "escondido" potencialmente interesante, no supe qué era hasta que repetí el proceso con todos los espacios protegidos de Andalucía:

Primero descargué de GBIF todos los datos de presencia de especies de Andalucía.  Esto supone trabajar con una base de datos de 11.448.644 registros. Abajo puedes ver la densidad de puntos de presencia de especies según GBIF en nuestra región.

![Puntos GBIF](https://github.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_ecologia_ccaa/raw/2019_2020/imagenes/occurrences_gbif.png)

A partir de estos datos obtuve dos mapas de distribución del índice de Shannon. En cada uno de ellos la referencia espacial era diferente:
***
#### Mapa de diversidad a escala de comunidad
Consideré que el tamaño medio de una comunidad ecológica en Andalucía eran unos 250 m. Dividí todo el territorio en cuadrículas de ese tamaño y apliqué el script (programa) de R que vimos en la práctica.  La siguiente imagen muestra la malla anterior y los puntos de presencia de especies. 

![grid](https://github.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_ecologia_ccaa/raw/2019_2020/imagenes/grid.png)

El resultado (tras dos días de procesamiento) se puede ver en la imagen de abajo. Y [aquí](https://github.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_ecologia_ccaa/raw/2019_2020/geoinfo/H_250.tif) puedes descargar la capa en formato raster (para que ocupe menos espacio)

![shannon 250m](https://github.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_ecologia_ccaa/raw/2019_2020/imagenes/shannon_250.png)

#### Mapa de diversidad a escala de paisaje

También apliqué el script de R anterior a la red de espacios protegidos de Andalucía. Es decir, calculé la diversidad de cada espacio protegido: diversidad a escala de paisaje. En este caso cada espacio protegido recibe un único valor del índice de Shannon. Se calcula computando las abundancias relativas de todas las especies presentes en ese espacio protegido.

A continuación puedes ver el resultado. También puedes descargarlo [aquí](https://github.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_ecologia_ccaa/raw/2019_2020/geoinfo/H_natura.tif) en formato raster:

![natura Shannon](https://github.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_ecologia_ccaa/raw/2019_2020/imagenes/shannon_natura_label.png)

***

Los mapas anteriores muestran diferentes patrones en la distribución espacial de la diversidad. Ahí van algunos ejemplos:

+ Fíjate, por ejemplo, en los espacios de Sierra Morena (parte norte de Andalucía. Zona etiquetada como A en el mapa anterior). En esos espacios hay alta diversidad (tonos azules) a escala de comunidad, pero baja a escala de paisaje (tonos anaranjados y rojos). 
+ Otro buen ejemplo de esta discrepancia entre el significado de la diversidad a las dos escalas consideradas es el Parque Natural de Cabo de Gata (extremo suroriental de Andalucía, en la costa). Observa cómo las comunidades de esa zona tienen una diversidad baja (es una zona semidesértica donde la vida es dura...). Sin embargo, la diversidad del espacio en su conjunto es muy alta (aparece coloreado de azul en el mapa).
+ Las impresiones anteriores se pueden cuantificar fácilmente. Podemos comparar la diversidad promedio de las comunidades de cada espacio protegido con el índice de Shannon que recibe dicho espacio si lo calculamos a escala de paisaje. Los resultados se pueden ver en la siguiente tabla:

![tabla_diversidad](https://github.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_ecologia_ccaa/raw/main/imagenes/tabla_diversidades.jpg)

En definitiva, la escala espacial a la que se realice el cálculo del índice de Shannon condiciona los resultados obtenidos. Es decir, no es lo mismo calcular el índice de Shannon a escala de comunidad que hacerlo a escala de paisaje. De hecho, en los ejemplos que hemos visto los resultados son opuestos. Los lugares que tienen comunidades muy diversas suelen tener baja diversidad a escala de paisaje... ¿por qué ocurrirá esto?


## Tareas a realizar





#### Diferencias de diversidad entre los espacios protegidos de Sierra Morena y los de las Sierras Béticas



Observa con atención el mapa que ves abajo. Muestra el índice Shannon de todos los espacios pertenecientes a la Red Natura 2000 en Andalucía. Todos tienen un índice de Shannon alto, aunque hay diferencias importantes entre unos y otros. En la zona marcada como A en el mapa están los espacios situados en Sierra Morena. En la zona B están aquellas zonas protegidas ubicadas en las montañas Béticas. Se observa que la zona A parece tener una diversidad menor que la B. Se trata solo de una apreciación visual. Para constatarlo numéricamente deberíamos de aplicar un test estadístico. Pero supongamos que esta apreciación es correcta. ¿A qué crees que se debe este patrón espacial de distribución de la diversidad?, ¿Por qué los espacios protegidos de Sierra Morena parecen tener menos diversidad que los de las montañas Béticas?. Reflexiona sobre ello y responde las preguntas. Piensa en los patrones espaciales que determinan la distribución de la biodiversidad que comentamos en teoría (y que se comentan en el apartado de contextualización ecológica de este documento). A modo de pista, te sugiero que pienses en las diferencias de relieve que hay entre ambas zonas. 

![natura Shannon](https://github.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_ecologia_ccaa/raw/2019_2020/imagenes/shannon_natura_label.png)

#### ¿Gradiente de diversidad de oeste a este en Andalucía oriental?

Ahora observa con detenimiento la siguiente imagen. Representa la distribución del índice de Shannon en Andalucía oriental. A la izquierda del mapa puedes ver a Sierra Nevada. Almería y el Cabo de Gata están al este. A medio camino observamos el llamado "Desierto de Tabernas". Al igual que en el caso anterior, podemos observar visualmente un patrón espacial en la diversidad. Aparentemente la diversidad disminuye conforme nos movemos hacia el este. ¿Por qué crees que ocurre esto? ¿Qué variable ambiental podría explicar el patrón de distribución observado en la diversidad?. 



![shannon sureste](https://github.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_ecologia_ccaa/raw/2019_2020/imagenes/shannon_sureste_250_label.png)

Glups, [aquí](https://github.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_ecologia_ccaa/raw/2019_2020/imagenes/precipitacion_sureste_label.png) he dejado olvidada una pista.



## Material a entregar

Contesta a las preguntas anteriores razonando todo lo que puedas. El objetivo es que reflexiones y uses argumentos convincentes. No hay una solución única a las preguntas, así que no te obsesiones buscando lo que yo quiero que me digas. Se trata de que aprendas mientas haces el ejercicio. 

Deberás subir las respuestas al moodle en formato **word**, **libre office** o equivalente. No en formato **pdf**, por favor.



## Criterios de evaluación

En el moodle hay una rúbrica (pincha [aquí](https://es.wikipedia.org/wiki/R%C3%BAbrica_(docencia)) si no sabes lo que es una rúbrica) que describe de manera detallada los criterios de calificación. También puedes verlos en la siguiente tabla:


| Criterio de evaluación                                       | 0 puntos        | 1 punto                                           | 2 puntos                                                     | 3 puntos                                                     | 4 puntos                                                     | 5 puntos                                                     |
| ------------------------------------------------------------ | --------------- | ------------------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| **Justificación de las respuestas**: Se refiere a el grado de justificación de tus respuestas, a la luz de la ecología. | No entrega nada | No justifica en ningún caso las respuestas.       | La justificación no se alinéa con nada conocido (por este humilde profesor) | Buena parte de las respuestas están correctamente justificadas. | Las justificaciones aportadas son coherentes.                | Lo que dices está tan bien justificado que me convencería si no estuviera de acuerdo con lo que dices. |
| **Adecuación**: Este criterio evalúa en qué medida los conceptos mostrados en la tarea se alinean con la idea de diversidad. | No entrega nada | No se observa nada relacionado con la diversidad. | Los conceptos teóricos en los que se basa el ejercicio aparecen tangencialmente. | Incorpora adecuadamente los conceptos de diversidad.         | Además de lo anterior, mencionas adecuadamente variables ambientales que pudieran explicar el patrón observado. | Excelente integración de marcos conceptuales diferentes. Además de los requeridos has incluido otros. |
| **Legibilidad:** hace referencia a lo bien escrito que está el texto y a su legibilidad | No entrega nada | Apenas entiendo lo que has escrito                | He tenido que reinterpretar casi cada frase para entenderlo  | Se entiende bien todo, pero el texto no es fluido            | Muy buena redacción. La lectura fluye fácilmente, cual novela. | Impecable estilo de escritura.                               |



