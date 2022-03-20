# Instrucciones para realizar el ejercicio denominado "Identificación de patrones en la distribución de la biodiversidad en Andalucía"


> + **_Versión_**: 2019-2020
> + **_Asignatura (grado)_**: Ecología (CCAA)
> + **_Autor_**: Curro Bonet-García (fjbonet@uco.es)
> + **_Nombre release en Github_**: tarea_mapa_biodiv_v1_2019_2020_CCAA



## Objetivos

Este ejercicio tiene los siguientes objetivos competenciales y operacionales:

 + Competenciales: Se refiere al conjunto de habilidades o conocimientos que se espera que adquieran los estudiantes durante el desarollo de esta actividad.
   +    Reflexionar sobr los patrones espaciales que rigen la distribución de la biodiversidad en una zona conocida por parte de los estudiantes: Andalucía.
   +    Comprender que los descriptores de los ecosistemas se pueden aplicar a distintas escalas espaciales.
   +    Fijar los conceptos de diversidad (índice de Shannon) y riqueza (número de especies)
 + Operacionales: Son los objetivos que nos planteamos satisfacer durante el desarrollo de la actividad. En este caso, los objetivos de este ejercicio son:
    +    Observar con detalle cómo se distribuyen la diversidad (índice de Shannon) y la riqueza de especies en Andalucía usando dos escalas espaciales: malla regular de 250 m de lado y mapa de la Red Natura 2000.
    +    Buscar razones que expliquen la existencia de ciertos patrones espaciales en la distribución de la diversidad en Andalucía.

Antes de detallar en qué consiste el ejercicio, lee el siguiente apartado en el que se describe el contexto ecológico planteado.



## Contextualización ecológica

Como sabemos, la cantidad de especies que hay en una comunidad ecológica es importante para entender muchas características estructurales y funcionales de los ecosistemas. En concreto hay dos descriptores importantes: riqueza de especies y diversidad. La riqueza de especies es fácil de entender: es la cantidad de especies que hay en una comunidad dada. Es un descriptor importante, pero tiene varios problemas para ser usado de manera estándar. Uno de ellos es que depende del esfuerzo de muestreo de especies. Es posible que lugares con muchas especies den valores bajos en este parámetro si no han sido suficientemente muestreados. Para minimizar este problema se usan otros indicadores de diversidad. En nuestro caso trabajamos con el[ índice de Shannon](https://es.wikipedia.org/wiki/%C3%8Dndice_de_Shannon), que tiene en cuenta tanto el número de especies como su abundancia relativa. 

La diversidad biológica se distribuye por la Tierra según una serie de patrones espaciales que vimos en las sesiones teóricas correspondientes. Dichos patrones ponen de manifiesto cómo se comporta la diversidad frente a ciertos factores ambientales. Por ejemplo:

+ Hay un patrón de distribución de la diversidad en función de la latitud. En el Ecuador hay más diversidad que en los polos. 
+ Heterogeneidad ambiental. Se ha comprobado que los lugares más heterogéneos desde un punto de vista ambiental (más cambios en las condiciones climáticas, por ejemplo), albergan más diversidad.
+ Dureza ambiental. En multitud de ocasiones se ha comprobado que los lugares sometidos a más perturbaciones o más fuentes de estrés, tienen menos diversidad biológica.

[Este](https://github.com/fjbonet/teaching_task_biodiversity_map/raw/master/biblio/biodiversity_patterns.pdf) artículo describe con detalle estos patrones y algunos más. 

Este ejercicio está relacionado con la identificación de alguno de estos patrones en Andalucía.



## Contextualización en la asignatura

Como recordarás, tuvimos una sesion de prácticas en la que elaboramos un mapa del índice Shannon de Sierra Nevada a partir de los datos de un inventario forestal. [Aquí](https://moodle.uco.es/m1920/course/view.php?id=2140#section-15) tienes toda la información, así como la grabación de las sesiones. En dicha práctica aprendimos a usar bases de datos relacionales y esto nos permitió calcular los términos de la ecuación que permite calcular el índice de Shannon. El esquema inferior resume cómo hacer estos cálculos. El término sector en dicho esquema equivale a cada una de las parcelas del inventario con el que trabajamos en clase.



<img src="https://raw.githubusercontent.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_ecologia_ccaa/2019_2020/images/esquema_consultas_diversidad.png" alt="Shannon" style="zoom:27%;" />



Durante la práctica anterior alguien preguntó algo así: "*Con esto que hemos visto podemos obtener un mapa del índice de Shannon de cada punto de inventario en Sierra Nevada. Pero, ¿cómo se calcularía el índice de Shannon de todo el espacio protegido?, ¿se calcularía haciendo el promedio de todos los puntos o habría que calcular desde el principio el índice de Shannon considerando que todos los puntos pertenecieran al mismo punto?*" Esta interesante pregunta es la que ha dado origen a este trabajo que os propongo... , aunque no tengo una respuesta buena para la pregunta planteada.

La respuesta que obtuve después de hacer los cálculos en las dos escalas espaciales mencionadas son:

+ *Cálculo directo a escala de todo el espacio protegido*: **5.018**
+ *Cálculo promediando los puntos existentes dentro del espacio protegido*: 
  + **Media: 1.1760**
  + **Mediana: 1.228**
  + **Mínimo: 0**
  + **Máximo: 7.188**
  + **Desviación estándar: 0.785**

En definitiva, la escala espacial a la que se realice el cálculo del índice de Shannon condiciona los resultados obtenidos. Es decir, no es lo mismo calcular el índice de Shannon de un territorio haciendo el promedio de los índices asociados a cada uno de los puntos en los que hay inventarios, que usar dichos puntos para calcular el índice. Suena un poco trabalenguas, pero no temáis, este ejercicio no va de esto.



## Generación de un mapa de biodiversidad en Andalucía

En esta tarea tienes que trabajar con un mapa de biodiversidad de toda Andalucía que se ha generado aplicando la misma técnica que usamos en prácticas (consultas SQL en una base de datos). La única diferencia es que, en lugar de usar un inventario forestal de Sierra Nevada con 600 parcelas, hemos usado todos los datos que tiene [GBIF](https://www.gbif.org/) para Andalucía. Esto supone trabajar con una base de datos de 11.448.644 registros.

La imagen inferior muestra el mapa del índice de Shannon que obtuvimos en la práctica.

![Shannon sinfonevada](https://raw.githubusercontent.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_ecologia_ccaa/2019_2020/images/shannon_snev_sinfonevada.png)

Tenemos pocos puntos para identificar patrones espaciales en la distribución de la biodiversidad. Únicamente se observa que en las zonas ocupadas por pinares de repoblación (zona norte) hay menos diversidad. Eso se debe a que dichas formaciones vegetales albergan pocas especies por lo general.



Sin embargo GBIF tiene miles de puntos de ocurrencia de especies (de fauna y flora) en Sierra Nevada. GBIF es una infraestructura de investigación que se encarga de digitalizar y representar en un mapa cuando es posible la información contenida en colecciones biológicas de todo el mundo. En la actualidad tienen miles de millones de registros y se han convertido en una referencia para los investigadores que trabajan con biodiversidad. A través de la web de esta infraestructura se pueden descargar libremente los datos. Para hacer este ejercicio usé datos de toda Andalucía. Los puntos con presencia de especies se pueden ver en la siguiente imagen (son 11.4 millones de registros). Hay tantos, que apenas se distinguen.

![Puntos GBIF](https://raw.githubusercontent.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_ecologia_ccaa/2019_2020/images/occurrences_gbif.png)



El mapa de biodiversidad que usaremos en este ejercicio se ha obtenido a partir de esta capa de puntos. Cada punto representa la presencia de una especie, así que para calcular el índice de Shannon se necesita un marco espacial determinado. En esta ocasión se ha usado una malla regular de 250 m de lado. La imagen inferior muestra unas cuantas de estas celdas, así como los puntos de ocurrencia de especies que contienen.

![grid](https://raw.githubusercontent.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_ecologia_ccaa/2019_2020/images/grid.png)



Tras aplicar las instrucciones SQL que vimos en prácticas, se obtiene un mapa de biodiversidad de toda Andalucía a escala de 250 m que puedes descargar [aquí](https://github.com/fjbonet/teaching_task_biodiversity_map/raw/master/geoinfo/H_250.tif). La imagen de abajo muestra la distribución espacial de la biodiversidad en Andalucía según este mapa.

![shannon 250m](https://raw.githubusercontent.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_ecologia_ccaa/2019_2020/images/shannon_250.png)

## Tareas a realizar

Una vez repasada la metodología que usamos para generar el mapa de biodiversidad, repasemos los objetivos de esta tarea.

La idea es que los estudiantes aúnen lo aprendido en teoría sobre biodiversidad (y sobre los patrones que explican su distribución) con el conocimiento que tienen de la geografía de Andalucía para tratar de interpretar las siguientes situaciones:



#### Diferencias de diversidad entre los espacios protegidos de Sierra Morena y los de las Sierras Béticas



Observa con atención el mapa que ves abajo. Muestra el índice Shannon de todos los espacios pertenecientes a la Red Natura 2000 en Andalucía. Todos tienen un índice de Shannon alto, aunque hay diferencias importantes entre unos y otros. En la zona marcada como A en el mapa están los espacios situados en Sierra Morena. En la zona B están aquellas zonas protegidas ubicadas en las montañas Béticas. Se observa que la zona A parece tener una diversidad menor que la B. Se trata solo de una apreciación visual. Para constatarlo numéricamente deberíamos de aplicar un test estadístico. Pero supongamos que esta apreciación es correcta. ¿A qué crees que se debe este patrón espacial de distribución de la diversidad?, ¿Por qué los espacios protegidos de Sierra Morena parecen tener menos diversidad que los de las montañas Béticas?. Reflexiona sobre ello y responde las preguntas. Piensa en los patrones espaciales que determinan la distribución de la biodiversidad que comentamos en teoría (y que se comentan en el apartado de contextualización ecológica de este documento). A modo de pista, te sugiero que pienses en las diferencias de relieve que hay entre ambas zonas. 

![natura Shannon](https://raw.githubusercontent.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_ecologia_ccaa/2019_2020/images/shannon_natura_label.png)

#### ¿Gradiente de diversidad de oeste a este en Andalucía oriental?

Ahora observa con detenimiento la siguiente imagen. Representa la distribución del índice de Shannon en Andalucía oriental. A la izquierda del mapa puedes ver a Sierra Nevada. Almería y el Cabo de Gata están al este. A medio camino observamos el llamado "Desierto de Tabernas". Al igual que en el caso anterior, podemos observar visualmente un patrón espacial en la diversidad. Aparentemente la diversidad disminuye conforme nos movemos hacia el este. ¿Por qué crees que ocurre esto? ¿Qué variable ambiental podría explicar el patrón de distribución observado en la diversidad?. 



![shannon sureste](https://raw.githubusercontent.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_ecologia_ccaa/2019_2020/images/shannon_sureste_250_label.png)

Glups, [aquí](https://raw.githubusercontent.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_ecologia_ccaa/2019_2020/images/precipitacion_sureste_label.png) he dejado olvidada una pista.



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



