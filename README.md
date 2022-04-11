{
 "cells": [
  {
   "cell_type": "markdown",
   "id": "064e25bd",
   "metadata": {},
   "source": [
    "# ¿Estas preparado para un Ironman 70.3?\n",
    "\n",
    "<br><br>\n",
    "\n",
    "## Introducción \n",
    "<br>\n",
    "El objetivo de este estudio es proporcionar datos sobre los resultados de atletas amateur a quienes estén pensando en prepararse para correr un Ironman 70.3.\n",
    "\n",
    "<br><br>\n",
    "\n",
    "\n",
    "## Contexto\n",
    "<br>\n",
    "El Ironman 70.3 (medio Ironman), es una carrera de triatlón de larga distancia organizada por la World Triathlon Corporation (WTC). Los participantes de la carrera deben recorrer: 1,9 km nadando, 90 km en bicicleta y 21,1 km de carrera a pie. La suma de estas distancias son 113 km, (70,3 millas).<br>\n",
    "Las distancias mencionadas hacen que esta sea una carrera accesible para deportistas amateurs que se inician en el triatlón de larga distancia.<br>\n",
    "El propósito de este estudio es proporcionar a deportistas amateurs de América del Sur, una idea de los tiempos de los participantes en las carreras que se celebran en esta región.\n",
    "\n",
    "<br><br>\n",
    "\n",
    "\n",
    "\n",
    "## Datos\n",
    "<br>\n",
    "Se evaluaron los datos de las carreras realizadas en 2019 en: Punta del Este, Florianópolis, Río de Janeiro, Maceió, Bariloche, Buenos Aires y Cartagena. Se excluyó la carrera de Pucón por tener una dificultad muy superior a las mencionadas anteriormente.\n",
    "Los datos se obtuvieron de https://www.obstri.com/  \n",
    "\n",
    "<br><br>\n",
    "\n",
    "|             | name                         | country               | swim               | bike               | run                      | total        | division  | race_city             |\n",
    "|-------------|------------------------------|-----------------------|--------------------|--------------------|--------------------------|--------------|-----------|-----------------------|\n",
    "| description | Nombre de los  participantes | País del participante | tiempo de natación | tiempo de ciclismo | tiempo de carrera  a pie | tiempo total | categoría | ciudad de  la carrera |\n",
    "| type        | str                          | str                   | timedelta64        | timedelta64        | timedelta64              | timedelta64  | str       | str                   |\n",
    "| count       | 7549                         | 7549                  | 7323               | 7507               | 7509                     | 7549         | 7549      | 7549                  |\n",
    "| unique      | 6766                         | 66                    | 1794               | 3668               | 3895                     | 5289         | 34        | 7                     |\n",
    "\n",
    "\n",
    "<br><br>\n",
    "## Metodología\n",
    "<br>\n",
    "\n",
    "* Se realiza una limpieza inicial de datos:\n",
    "    * Se importan los valores de tiempos perdidos como Nan\n",
    "    * Se concatenan los resultados de todas las carreras y se genera columna con ciudad de la carrera\n",
    "    * Se excluyen los datos de los corredores profesionales\n",
    "* Se formatean los tiempos como timedelta\n",
    "* Se crea una nueva columna para separar el nombre de la categoría\n",
    "* Se genera un set de datos con los resultados de los participantes masculinos y otro con el de los femeninos\n",
    "* Se realizan histogramas de los datos de cada disciplina por sexo\n",
    "*Se detectan valores outliers, se excluyen los tiempos menores a los records conocidos de cada disciplina y los mayores que no tienen sentido \n",
    "* Se extraen los promedios, los valores máximos y minimos y entre que rangos están la mayoría de los resultados \n",
    "\n",
    "<br><br>\n",
    "\n",
    "## Resultados\n",
    "<br>\n",
    "\n",
    "### Análisis de resultados de mujeres\n",
    "\n",
    "<br>\n",
    "Resultados de segmento natación:\n",
    "\n",
    "<img src=\"https://raw.githubusercontent.com/Maitech0/IM70.3SA/main/grafs/fswim_frequency.png\" alt=\"female swimming times\" width=\"500\"/>\n",
    "\n",
    "\n",
    "| count    | 1358     |\n",
    "|----------|----------|\n",
    "| promedio | 00:43:55 |\n",
    "| min      | 00:26:03 |\n",
    "| max      | 00:59:58 |\n",
    "| std      | 00:06:59 |\n",
    "| 25%      | 00:38:29 |\n",
    "| 50%      | 00:43:31 |\n",
    "| 75%      | 00:48:57 |\n",
    "\n",
    "La mayoría de las participantes termina este segmanto en menos de 49 min. \n",
    "<br> El promedio de los rsultados es 44 min.\n",
    "<br><br>\n",
    "\n",
    "Resultados de segmento ciclismo:\n",
    "\n",
    "<img src=\"https://raw.githubusercontent.com/Maitech0/IM70.3SA/main/grafs/fbike_frequency.png\" alt=\"female bike times\" width=\"500\"/>\n",
    "\n",
    "\n",
    "| count    | 1415     |\n",
    "|----------|----------|\n",
    "| promedio | 03:08:07 |\n",
    "| min      | 02:22:45 |\n",
    "| max      | 04:30:38 |\n",
    "| std      | 00:19:38 |\n",
    "| 25%      | 02:54:14 |\n",
    "| 50%      | 03:05:28 |\n",
    "| 75%      | 03:19:43 |\n",
    "\n",
    "\n",
    "\n",
    "La mayoría de las participantes termina este segmanto en menos de 3hs 20 min. \n",
    "<br> El promedio de los rsultados es 3hs 8min.\n",
    "<br><br>\n",
    "\n",
    "Resultados de segmento carrera a pie:\n",
    "\n",
    "<img src=\"https://raw.githubusercontent.com/Maitech0/IM70.3SA/main/grafs/frun_frequency.png\" alt=\"female run times\" width=\"500\"/>\n",
    "\n",
    "| count    | 1415     |\n",
    "|----------|----------|\n",
    "| promedio | 02:10:31 |\n",
    "| min      | 01:26:24 |\n",
    "| max      | 03:39:51 |\n",
    "| std      | 00:21:19 |\n",
    "| 25%      | 01:54:48 |\n",
    "| 50%      | 02:07:44 |\n",
    "| 75%      | 02:23:44 |\n",
    "\n",
    "\n",
    "La mayoría de las participantes termina este segmanto en menos de 2hs 24 min. \n",
    "<br> El promedio de los rsultados es 2hs 10min.\n",
    "<br>\n",
    "<br>\n",
    "\n",
    "### Análisis de resultados de hombres\n",
    "\n",
    "<br>\n",
    "Resultados de segmento natación:\n",
    "\n",
    "<img src=\"https://raw.githubusercontent.com/Maitech0/IM70.3SA/main/grafs/mswim_frequency.png\" alt=\"male swim times\" width=\"500\"/>\n",
    "\n",
    "\n",
    "| count    | 5946     |\n",
    "|----------|----------|\n",
    "| promedio | 00:40:12 |\n",
    "| min      | 00:21:51 |\n",
    "| max      | 00:59:56 |\n",
    "| std      | 00:06:57 |\n",
    "| 25%      | 00:35:00 |\n",
    "| 50%      | 00:39:32 |\n",
    "| 75%      | 00:44:41 |\n",
    "\n",
    "La mayoría de los participantes termina este segmanto en menos de 45 min. \n",
    "<br> El promedio de los rsultados es 40 min.\n",
    "<br><br>\n",
    "\n",
    "Resultados de segmento ciclismo:\n",
    "\n",
    "<img src=\"https://raw.githubusercontent.com/Maitech0/IM70.3SA/main/grafs/mbike_frequency.png\" alt=\"male bike times\" width=\"500\"/>\n",
    "\n",
    "\n",
    "| count    | 6074     |\n",
    "|----------|----------|\n",
    "| promedio | 02:51:18 |\n",
    "| min      | 02:10:27 |\n",
    "| max      | 04:25:26 |\n",
    "| std      | 00:19:27 |\n",
    "| 25%      | 02:37:28 |\n",
    "| 50%      | 02:48:30 |\n",
    "| 75%      | 03:02:05 |\n",
    "\n",
    "\n",
    "La mayoría de las participantes termina este segmanto en menos de 3hs 2min. \n",
    "<br> El promedio de los rsultados es 2hs 51min.\n",
    "<br><br>\n",
    "\n",
    "Resultados de segmento carrera a pie:\n",
    "<img src=\"https://raw.githubusercontent.com/Maitech0/IM70.3SA/main/grafs/mrun_frequency.png\" alt=\"male bike times\" width=\"500\"/>\n",
    "\n",
    "\n",
    "| count    | 6076     |\n",
    "|----------|----------|\n",
    "| promedio | 02:02:07 |\n",
    "| min      | 01:06:24 |\n",
    "| max      | 03:50:10 |\n",
    "| std      | 00:23:16 |\n",
    "| 25%      | 01:45:06 |\n",
    "| 50%      | 01:58:31 |\n",
    "| 75%      | 02:15:12 |\n",
    "\n",
    "\n",
    "La mayoría de las participantes termina este segmanto en menos de 2hs 15min. \n",
    "<br> El promedio de los rsultados es 2hs 2min.\n",
    "<br><br>\n",
    "\n",
    "## Conclusión\n",
    "<br>\n",
    "En el caso de las participantes mujeres:<br>\n",
    "Si puedes: nadar 1900m a un ritmo medio mayor a 02:34 min por 100m, recorrer 90km en bicicleta a una velocidad media mayor a 27 km/h y correr 21.1km a un ritmo mayor a 6:50min el km estás pronta para participar en un IRONMAN 70.3\n",
    "<br>\n",
    "En el caso de los participantes hombres:<br>\n",
    "Si puedes: nadar 1900m a un ritmo medio mayor a 02:21min por 100m, recorrer 90km en bicicleta a una velocidad media mayor a 30 km/h y correr 21.1km a un ritmo mayor a 6:26min el km estas pronto para participar en un IRONMAN 70.3\n",
    "\n",
    "<br><br>\n",
    "## Anécdotas / Anecdotes\n",
    "<br>\n",
    "En cualquier caso terminar un triatlón de esa distancia es algo increíble y si te tardas un poco más sigue siendo una hazaña impresionante. Se propone realizar un nuevo análisis teniendo en cuenta las categorías por edad\n",
    "\n"
   ]
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3 (ipykernel)",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.9.7"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 5
}
