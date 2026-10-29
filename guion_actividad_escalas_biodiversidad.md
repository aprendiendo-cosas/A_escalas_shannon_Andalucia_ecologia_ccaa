# El efecto de la escala espacial en el significado del concepto de diversidad biológica en una comunidad

> + **_Tipo de material_**: <span style="display: inline-block; font-size: 12px; color: white; background-color: #8D26F5; border-radius: 5px; padding: 5px; font-weight: bold;"> Tarea</span>
> + **_Versión_**: 2026-2027
> + **_Asignatura (grado)_**: Ecología (CCAA)
> + **_Autor_**: Curro Bonet-García (fjbonet@uco.es)

![portada](https://raw.githubusercontent.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_ecologia_ccaa/main/imagenes/portada.jpg)

[TOC]

## 1. Objetivos

Esta actividad tiene como finalidad última la aplicación del concepto de diversidad (a través del índice de Shannon) a una escala espacial diferente a la que vemos en la práctica que permite generar un mapa de diversidad de Sierra Nevada. Desde un punto de vista docente este tipo de ejercicios son muy útiles porque nos permiten entrenar habilidades cognitivas superiores (trasferir conocimiento de un ámbito a otro, investigar, reflexionar, tomar conciencia del avance en el razonamiento, etc.). Como siempre, los objetivos concretos son de dos tipos:

 + Disciplinares (tienen que ver con la ecología): Se muestran a continuación en orden de complejidad creciente:
   + Fijar los conceptos de diversidad (índice de Shannon) y riqueza (número de especies).
   + Reflexionar sobre los patrones de distribución espaciales de la diversidad en un territorio concreto (Andalucía).
   + Afianzar la conexión entre la identificación del patrón espacial (ej. hay más diversidad al oeste) y las causas que explican dicho patrón (ej. esto se debe a que hacia el oeste llueve más).
   + Comprender que el concepto de diversidad tiene significados diferentes dependiendo de su escala espacial de aplicación.
   + Descubrir un "nuevo" tipo de diversidad a partir de la observación de patrones de aplicación del índice de Shannon a dos escalas: escala de "comunidad pequeña" (polígonos mapa de vegetación) y a escala de "paisaje" (espacios protegidos de Andalucía)
 + Instrumentales (tienen que ver con el manejo de herramientas de uso común):
    + Entrenar la capacidad de reflexión ante un problema nuevo partiendo de información incompleta.
    + Mejorar nuestra capacidad de usar la IA como copiloto de aprendizaje. 


Antes de detallar en qué consiste el ejercicio, lee el siguiente apartado en el que se describe el contexto ecológico planteado.



## 2. Contextualización ecológica

Como sabemos, la cantidad de especies que hay en una comunidad ecológica es importante para entender muchas características estructurales y funcionales de los ecosistemas. En concreto hay dos descriptores importantes en una comunidad ecológica: riqueza de especies y diversidad. La riqueza de especies es fácil de entender: es la cantidad de especies que hay en una comunidad dada. Es un descriptor importante, pero tiene varios problemas para ser usado de manera estándar. Uno de ellos es que depende del esfuerzo de muestreo de especies. Es posible que lugares con muchas especies den valores bajos en este parámetro si no han sido suficientemente muestreados. Para minimizar este problema se usan otros indicadores de diversidad. En nuestro caso trabajamos con el[ índice de Shannon](https://es.wikipedia.org/wiki/%C3%8Dndice_de_Shannon), que tiene en cuenta tanto el número de especies como su abundancia relativa. 

La diversidad biológica se distribuye por la Tierra según una serie de patrones espaciales que vimos en la sesión teórica sobre diversidad ([aquí](https://rawcdn.githack.com/aprendiendo-cosas/Te_comunidades_diversidad_ecologia_ccaa/2026_2027/guion_comunidades_diversidad.html) el guión). Dichos patrones ponen de manifiesto cómo se comporta la diversidad frente a ciertos factores ambientales. Por ejemplo:

+ Hay un patrón de distribución de la diversidad en función de la latitud. En el Ecuador hay más diversidad que en los polos. 
+ Heterogeneidad ambiental. Se ha comprobado que los lugares más heterogéneos desde un punto de vista ambiental (más cambios en las condiciones climáticas, por ejemplo), albergan más diversidad.
+ Dureza ambiental. En multitud de ocasiones se ha comprobado que los lugares sometidos a más perturbaciones o más fuentes de estrés, tienen menos diversidad biológica.

[Este](https://github.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_ecologia_ccaa/raw/2025_2026/biblio/biodiversity_patterns.pdf) artículo describe con detalle estos patrones y algunos más. El foco de esta actividad es que, si bien los factores anteriores explican la distribución de la diversidad, lo hacen de forma distinta dependiendo de la escala espacial a la que "observamos". Recomiendo que leas el artículo anterior para entender bien lo que se plantea a continuación.



## 3. Planteamiento del problema

En el curso 2019-2020, al terminar la práctica sobre el mapa de biodiversidad, una estudiante (Belén) me hizo la siguiente pregunta: "*Con esto que hemos visto podemos obtener un mapa del índice de Shannon de cada comunidad de Sierra Nevada. Pero, ¿cómo se calcularía el índice de Shannon de todo el espacio protegido?, ¿se calcularía haciendo el promedio de todos los puntos o habría que calcular desde el principio el índice de Shannon considerando que todos los puntos pertenecieran a la misma comunidad?*" No supe contestar en ese momento, pero me comprometí a darle una respuesta más tarde.

Me puse a trabajar y calculé el índice de Shannon para toda Sierra Nevada (a este índice le llamaremos "Shannon a escala de paisaje"), así como el valor promedio del índice de Shannon de todas las comunidades del espacio protegido ("Shannon a escala de comunidad"). Como sospechaba, los valores eran diferentes. Aunque imaginé que había algo "escondido" potencialmente interesante, no supe qué era hasta que repetí el proceso con todos los espacios protegidos de Andalucía:

Primero descargué de GBIF todos los datos de presencia de especies de Andalucía.  Esto supone trabajar con una base de datos de 11.448.644 registros. Abajo puedes ver la densidad de puntos de presencia de especies según GBIF en nuestra región.

<img src="https://github.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_ecologia_ccaa/blob/2025_2026/imagenes/occurrences_gbif.png?raw=true" alt="Puntos GBIF" style="zoom:50%;" />

A partir de estos datos obtuve dos mapas de distribución del índice de Shannon. En cada uno de ellos la referencia espacial era diferente:
***
### 3.1 Mapa de diversidad a escala de comunidad
Consideré que el tamaño medio de una comunidad ecológica en Andalucía eran unos 250 m. Dividí todo el territorio en cuadrículas de ese tamaño y apliqué el script (programa) de R que vimos en la práctica.  Podía haber usado los polígonos de un mapa de vegetación como hemos hecho en prácticas, pero la malla de 250 m era más rápida de procesar para toda Andalucía. La siguiente imagen muestra la malla anterior y los puntos de presencia de especies. 

<img src="https://github.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_ecologia_ccaa/blob/2025_2026/imagenes/grid.png?raw=true" alt="grid" style="zoom:50%;" />

El resultado (tras dos días de procesamiento) se puede ver en la imagen de abajo. Y [aquí](https://github.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_ecologia_ccaa/raw/2025_2026/geoinfo/H_250.tif) puedes descargar la capa en formato raster.

![andalucia](https://github.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_ecologia_ccaa/blob/2025_2026/imagenes/shannon_250.png?raw=true)

### 3.2 Mapa de diversidad a escala de paisaje

También apliqué el script de R anterior a la red de espacios protegidos de Andalucía. Es decir, calculé la diversidad de cada espacio protegido: diversidad a escala de paisaje. En este caso cada espacio protegido recibe un único valor del índice de Shannon. Se calcula computando las abundancias relativas de todas las especies presentes en ese espacio protegido. Es como si consideráramos que cada espacio protegido es una única comunidad. Sabemos que no lo es en realidad, pero también sabemos que los organismos que viven en un espacio protegido comparten más relaciones e intercambios genéticos que los que viven en dos territorios alejados. Así que el símil no es tan descabellado.

A continuación puedes ver el resultado. También puedes descargarlo [aquí](https://github.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_ecologia_ccaa/raw/2025_2026/geoinfo/H_natura.tif) en formato raster:

<img src="https://raw.githubusercontent.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_ecologia_ccaa/2025_2026/imagenes/shannon_natura_label.png" alt="natura Shannon" style="zoom:100%;" />

***

Los mapas anteriores muestran diferentes patrones en la distribución espacial de la diversidad. Ahí van algunos ejemplos:

+ Fíjate, por ejemplo, en los espacios de Sierra Morena (parte norte de Andalucía. Zona etiquetada como A en el mapa anterior). En esos espacios hay alta diversidad (tonos azules) a escala de comunidad, pero baja a escala de paisaje (tonos anaranjados y rojos). 
+ Otro buen ejemplo de esta discrepancia entre el significado de la diversidad a las dos escalas consideradas es el Parque Natural de Cabo de Gata (extremo suroriental de Andalucía, en la costa). Observa cómo las comunidades de esa zona tienen una diversidad baja (es una zona semidesértica donde la vida es dura...). Sin embargo, la diversidad del espacio en su conjunto es muy alta (aparece coloreado de azul en el mapa).
+ Las impresiones anteriores se pueden cuantificar fácilmente. Podemos comparar la diversidad promedio de las comunidades de cada espacio protegido con el índice de Shannon que recibe dicho espacio si lo calculamos a escala de paisaje. Los resultados se pueden ver en la siguiente tabla:

![compara](https://raw.githubusercontent.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_ecologia_ccaa/2025_2026/imagenes/tabla_diversidades.jpg)

En definitiva, la escala espacial a la que se realice el cálculo del índice de Shannon condiciona los resultados obtenidos. Es decir, no es lo mismo calcular el índice de Shannon a escala de comunidad que hacerlo a escala de paisaje. La sospecha de Belén (el valor medio de diversidad por espacio no es el mismo que la diversidad calculada a escala de dicho espacio) De hecho, en los ejemplos que hemos visto los resultados son opuestos. Los lugares que tienen comunidades muy diversas suelen tener baja diversidad a escala de paisaje... ¿por qué ocurrirá esto?



## 4. Tareas a realizar

La idea es que discutamos en clase por qué ocurre lo que he descrito más arriba. Más concretamente, trataremos de contestar a estas preguntas:

1. **¿Por qué cuando cambiamos la escala a la que medimos la diversidad obtenemos resultados diferentes? ¿Hay acaso dos tipos de diversidad distintos?**
2. **¿Por qué en los espacios protegidos seleccionados ocurre que cuando la diversidad de las comunidades es alta, es baja a escala de paisaje?**
3. **¿Por qué los espacios protegidos de Sierra Morena parecen tener menos diversidad que los de las montañas Béticas?.** Fíjate en el mapa de más arriba en el que los espacios de Sierra Morena están etiquetados con la A y los de las montañas Béticas con la B. A modo de pista, te sugiero que pienses en las diferencias de relieve que hay entre ambas zonas. 

Para responder a la segunda pregunta deberemos entender bien la respuesta a la primera. Y para responder bien a la tercera, deberemos de entender bien la segunda...

Reflexiona sobre las preguntas que planteo. Si quieres, charla con una IA sobre las mismas. Pero recuerda que el objetivo no es que la IA te dé la respuesta. El objetivo es que uses esa herramienta para aprender lo que necesitas saber para contestar tú las preguntas. 

## 5. Resultados de la sesión

Aquí resumiré lo que hayamos discutido y concluido en clase





****

[Aquí](https://github.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_ecologia_ccaa/refs/tags/2025_2026.zip) puedes descargar un archivo .zip que contiene este guión en formato html y todo el material que incluye.

****
Haz click [aquí](https://github.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_ecologia_ccaa/releases) para ver cómo ha cambiado este guión en los distintos cursos académicos.

****

[Aquí](https://github.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_ecologia_ccaa/blob/2026_2027/notas_imparticion_A_escalas_shannon_Andalucia_ecologia_ccaa.md) puedes ver las notas que tomó el profesor una vez que se impartió la clase.

---

 <p xmlns:cc="http://creativecommons.org/ns#" >El contenido de este repositorio se puede utilizar bajo la siguiente licencia:  <a  href="https://creativecommons.org/licenses/by-nc-sa/4.0/?ref=chooser-v1"  target="_blank" rel="license noopener noreferrer"  style="display:inline-block;">CC BY-NC-SA 4.0<img  style="height:22px!important;margin-left:3px;vertical-align:text-bottom;"   src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1"  alt=""><img  style="height:22px!important;margin-left:3px;vertical-align:text-bottom;"   src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1"  alt=""><img  style="height:22px!important;margin-left:3px;vertical-align:text-bottom;"   src="https://mirrors.creativecommons.org/presskit/icons/nc.svg?ref=chooser-v1"  alt=""><img  style="height:22px!important;margin-left:3px;vertical-align:text-bottom;"   src="https://mirrors.creativecommons.org/presskit/icons/sa.svg?ref=chooser-v1"  alt=""></a></p> 

<p>Esta licencia no aplica a enlaces a artículos, libros o imágenes no originales. Estos productos tienen su licencia correspondiente.</p>
