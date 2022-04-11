# ¿Estas preparado para un Ironman 70.3?

<br><br>

## Introducción
<br>
El objetivo de este estudio es proporcionar datos sobre los resultados de atletas amateur a quienes estén pensando en prepararse para correr un Ironman 70.3

<br><br>
## Contexto
<br>
El Ironman 70.3 (medio Ironman), es una carrera de triatlón de larga distancia organizada por la World Triathlon Corporation (WTC). Los participantes de la carrera deben recorrer: 1,9 km nadando, 90 km en bicicleta y 21,1 km de carrera a pie. La suma de estas distancias son 113 km, (70,3 millas).<br>
Las distancias mencionadas hacen que esta sea una carrera accesible para deportistas amateurs que se inician en el triatlón de larga distancia.<br>
El propósito de este estudio es proporcionar a deportistas amateurs de América del Sur, una idea de los tiempos de los participantes en las carreras que se celebran en esta región.
<br><br>
## Datos
<br>
Se evaluaron los datos de las carreras realizadas en 2019 en: Punta del Este, Florianópolis, Río de Janeiro, Maceió, Bariloche, Buenos Aires y Cartagena. Se excluyó la carrera de Pucón por tener una dificultad muy superior a las mencionadas anteriormente.
Los datos se obtuvieron de https://www.obstri.com/

<br><br>

|             | name                         | country               | swim               | bike               | run                      | total        | division  | race_city             |
|-------------|------------------------------|-----------------------|--------------------|--------------------|--------------------------|--------------|-----------|-----------------------|
| description | Nombre de los  participantes | País del participante | tiempo de natación | tiempo de ciclismo | tiempo de carrera  a pie | tiempo total | categoría | ciudad de  la carrera |
| type        | str                          | str                   | timedelta64        | timedelta64        | timedelta64              | timedelta64  | str       | str                   |
| count       | 7549                         | 7549                  | 7323               | 7507               | 7509                     | 7549         | 7549      | 7549                  |
| unique      | 6766                         | 66                    | 1794               | 3668               | 3895                     | 5289         | 34        | 7                     |

 <br><br>
## Metodología
<br>

* Se realiza una limpieza inicial de datos:\n",
   * Se importan los valores de tiempos perdidos como Nan\n",
   * Se concatenan los resultados de todas las carreras y se genera columna con ciudad de la carrera
   * Se excluyen los datos de los corredores profesionales
* Se formatean los tiempos como timedelta
* Se crea una nueva columna para separar el nombre de la categoría
* Se genera un set de datos con los resultados de los participantes masculinos y otro con el de los femeninos
* Se realizan histogramas de los datos de cada disciplina por sexo
* Se detectan valores outliers, se excluyen los tiempos menores a los records conocidos de cada disciplina y los mayores que no tienen sentido
* Se extraen los promedios, los valores máximos y minimos y entre que rangos están la mayoría de los resultados
<br><br>

## Resultados
<br>

### Análisis de resultados de mujeres

<br>
Resultados de segmento natación:

<img src="https://raw.githubusercontent.com/Maitech0/IM70.3SA/main/grafs/fswim_frequency.png" alt="female swimming times" width= "500">


   | count    | 1358     |
   |----------|----------|
   | promedio | 00:43:55 |
   | min      | 00:26:03 |
   | max      | 00:59:58 |
   | std      | 00:06:59 |
   | 25%      | 00:38:29 |
   | 50%      | 00:43:31 |
   | 75%      | 00:48:57 |
  
La mayoría de las participantes termina este segmanto en menos de 49 min.
    <br> El promedio de los rsultados es 44 min.
    <br><br>
    
Resultados de segmento ciclismo:
   
 <img src= "https://raw.githubusercontent.com/Maitech0/IM70.3SA/main/grafs/fbike_frequency.png" alt= "female bike times" width= "500">


   | count    | 1415     |
   |----------|----------|
   | promedio | 03:08:07 |
   | min      | 02:22:45 |
   | max      | 04:30:38 |
   | std      | 00:19:38 |
   | 25%      | 02:54:14 |
   | 50%      | 03:05:28 |
   | 75%      | 03:19:43 |


La mayoría de las participantes termina este segmanto en menos de 3hs 20 min.
<br> El promedio de los rsultados es 3hs 8min.
<br><br>
   
Resultados de segmento carrera a pie:\n",

<img src= "https://raw.githubusercontent.com/Maitech0/IM70.3SA/main/grafs/frun_frequency.png" alt="female run times" width="500"/>

   | count    | 1415     |
   |----------|----------|
   | promedio | 02:10:31 |
   | min      | 01:26:24 |
   | max      | 03:39:51 |
   | std      | 00:21:19 |
   | 25%      | 01:54:48 |
   | 50%      | 02:07:44 |
   | 75%      | 02:23:44 |


La mayoría de las participantes termina este segmanto en menos de 2hs 24 min.
<br> El promedio de los rsultados es 2hs 10min.\n",
<br>
<br>
    
### Análisis de resultados de hombres

<br>
Resultados de segmento natación:

<img src="https://raw.githubusercontent.com/Maitech0/IM70.3SA/main/grafs/mswim_frequency.png" alt="male swim times" width="500">


   | count    | 5946     |
   |----------|----------|
   | promedio | 00:40:12 |
   | min      | 00:21:51 |
   | max      | 00:59:56 |
   | std      | 00:06:57 |
   | 25%      | 00:35:00 |
   | 50%      | 00:39:32 |
   | 75%      | 00:44:41 |

La mayoría de los participantes termina este segmanto en menos de 45 min.
<br> El promedio de los rsultados es 40 min
<br><br>
    
Resultados de segmento ciclismo:
    
<img src="https://raw.githubusercontent.com/Maitech0/IM70.3SA/main/grafs/mbike_frequency.png" alt="male bike times" width="500">


   | count    | 6074     |
   |----------|----------|
   | promedio | 02:51:18 |
   | min      | 02:10:27 |
   | max      | 04:25:26 |
   | std      | 00:19:27 |
   | 25%      | 02:37:28 |
   | 50%      | 02:48:30 |
   | 75%      | 03:02:05 |


La mayoría de las participantes termina este segmanto en menos de 3hs 2min.
<br> El promedio de los rsultados es 2hs 51min.
<br><br>
    
Resultados de segmento carrera a pie:
<img src="https://raw.githubusercontent.com/Maitech0/IM70.3SA/main/grafs/mrun_frequency.png" alt="male bike times" width="500">


 | count    | 6076     |
 |----------|----------|
 | promedio | 02:02:07 |
 | min      | 01:06:24 |
 | max      | 03:50:10 |
 | std      | 00:23:16 |
 | 25%      | 01:45:06 |
 | 50%      | 01:58:31 |
 | 75%      | 02:15:12 |


La mayoría de las participantes termina este segmanto en menos de 2hs 15min.
<br> El promedio de los rsultados es 2hs 2min.
<br><br>

## Conclusión
<br>
En el caso de las participantes mujeres:
Si puedes: nadar 1900m a un ritmo medio mayor a 02:34 min por 100m, recorrer 90km en bicicleta a una velocidad media mayor a 27 km/h y correr 21.1km a un ritmo mayor a 6:50min el km estás pronta para participar en un IRONMAN 70.3
<br>
En el caso de los participantes hombres:<br>
Si puedes: nadar 1900m a un ritmo medio mayor a 02:21min por 100m, recorrer 90km en bicicleta a una velocidad media mayor a 30 km/h y correr 21.1km a un ritmo mayor a 6:26min el km estas pronto para participar en un IRONMAN 70.3

<br><br>\n",
## Anécdotas / Anecdotes\n",
<br>
En cualquier caso terminar un triatlón de esa distancia es algo increíble y si te tardas un poco más sigue siendo una hazaña impresionante. Se propone realizar un nuevo análisis teniendo en cuenta las categorías por edad