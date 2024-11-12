# Modelo de Machine Learning para la Estimación de Costos de Transporte en Colombia 

# DatosalaU_R3_G17
Repositorio del repositorio para el concurso Datos a la U https://www.datos.gov.co/stories/s/Actualidades-del-concurso-Datos-a-la-U/wn73-87k7/

Notebook Solución: https://github.com/davidUrr/DatosalaU_R3_G17/blob/master/analisis.ipynb

### Eje Temático: Transporte
  
* Descripción: En Este conjunto de datos se encuentra la información relacionada con el REGISTRO NACIONAL DE DESPACHOS DE CARGA POR CARRETERA - RNDC, en donde se encontrará la información relacionada de las operaciones de los despachos de carga que se manejan a nivel nacional, habilitados en el marco Normativo.

## Introducción
El Registro Nacional de Despachos de Carga (RNDC) fue implementado inicialmente mediante la Resolución 377 del 15 de febrero de 2013, emitida por el Ministerio de Transporte de Colombia. Esta resolución estableció el RNDC como un sistema de información para registrar las operaciones del servicio público de transporte terrestre automotor de carga. Su propósito es recibir, validar y transmitir la información generada en las operaciones del servicio público de transporte de carga por carretera en el país. Esta herramienta garantiza la transparencia y legalidad en dichas operaciones, facilitando el control y la planificación por parte de las autoridades competentes.

## Problema a solucionar
Las empresas de transporte enfrenta el desafío de estimar con precisión los costos de carga para diferentes rutas y tipos de mercancías, dado que los precios del combustible, las condiciones de las carreteras y las tarifas de peaje varían constantemente. Esta variabilidad hace que los cálculos tradicionales de costos sean inexactos y difíciles de ajustar a tiempo real. A la fecha no se conoce un estudio que permita el aprovechamiento de esta base de datos a través de su análisis con algoritmos de Machine Learning que facilita la estimación de los costos de carga en Colombia

## Conjunto de datos
* https://www.datos.gov.co/Transporte/Registro-Nacional-de-Despachos-de-Carga-por-Carret/vn9u-yhwq/about_data
En Este conjunto de datos se encuentra la información relacionada con el REGISTRO NACIONAL DE DESPACHOS DE CARGA POR CARRETERA - RNDC, en donde se encontrará la información relacionada de las operaciones de los despachos de carga que se manejan a nivel nacional, habilitados en el marco Normativo. Se reconoce en la base de datos un total de 22 variables, donde se reconoce
* Información del vehículo
* Tipo de operación de transporte
* Origen y destino de la carga
* Tipo y naturaleza de la carga
* Variables numéricas como el peso en kilogramos, kilómetros recorridos y el valor pagado (VALORESPAGADOS)
* VALORESPAGADOS se considera la variable objetivo.

## Solución propuesta
Un modelo de Machine Learning que permita la estimación de costos de transporte de manera confiable y repetible, para asegurar la reproducibilidad de esta solución, se desarrollará un archivo Jupyter Notebook (.pynb), que incluye todos los pasos necesarios para realizar el análisis, seleccionar el mejor modelo y ejecutar las estimaciones de costos de carga. Los algoritmos de aprendizaje automático mejoran significativamente la precisión de la estimación de costos en los modelos de transporte al aprovechar los conocimientos basados en datos y las capacidades predictivas. Estos algoritmos pueden analizar variables complejas que afectan a los costos, lo que permite obtener pronósticos más confiables.

### Tipo de modelo: Gradient Boosting Regressor
### Métricas
| Variable        | Valor        |
|------------------|------------------|
| Mean Absolute Error (MAE)    | 0.000151  |
| Mean Squared Error (MSE)    | 0.000002    |
| Root Mean Squared Error (RMSE)    | 0.001309   |
| R-squared (R²)    | 0.920474 |

### Gráficas
| Matriz de Correlación        | Importancia de variables |
|------------------|------------------|
| <img src="https://github.com/user-attachments/assets/ae3676c7-43a9-467e-9114-89a8d761d8be" style="width:50%;display: block; margin: auto;"/> | <img src="https://github.com/user-attachments/assets/e3b5413c-a0a3-40a9-93e9-fb7c30126415" style="display: block; margin: auto;"/>|
| <img src="https://github.com/user-attachments/assets/d48059e0-227f-4c68-84da-348198e25486" style="display: block; margin: auto;"/>|  <img src="https://github.com/user-attachments/assets/4b8fc4b0-9b7f-45e9-b159-57b0f2d20247" style="display: block; margin: auto;"/>|


## Información adicional
La plataforma de RNDC es accesible y se puede descargar el conjunto completo de datos (https://rndc.mintransporte.gov.co/MenuPrincipal/tabid/204/language/es-MX/Default.aspx?returnurl=%2f), en esta se puede recopilar datos desde 2015 hasta 2024 mes actual.
![image](https://github.com/user-attachments/assets/59f30a3a-a7be-4520-a826-73124f31dc96)

En el Notebook se hace una exploración de los datos: https://github.com/davidUrr/DatosalaU_R3_G17/blob/master/exploratorio.ipynb

Para hacer un reconocimiento mas profundo la plataforma RNDC y los datos, se baja la información desde 2015 hasta 2023, es de aclarar que la plataforma solo permite acceder a los datos de forma mensualizada, sin embargo como parte de este trabajo se comparte la consolidación del los datos en el siguiente link (https://drive.google.com/file/d/1XapZCtN82DYOJ6jDU1-bLsJGIY7BgGDn/view?usp=sharing)

Para hacer un mejor aprovechamiento de otras fuentes se incluye:
* La base de datos de codificación DANE donde se puede extrer los datos de longitud, latitud por cada código DANE por ciudad y municipio (https://geoportal.dane.gov.co/geovisores/territorio/consulta-divipola-division-politico-administrativa-de-colombia/), este conjunto se almacena en el archivo (
* La Resolución 4100 de 2004, del Ministerio de Transporte (https://www.alcaldiabogota.gov.co/sisjur/normas/Norma1.jsp?i=15600) permite reconocer los pesos máximos por tipo de vehículo, esto facilita establecer las capacidades ociosas de los vehículos en su uso, este conjunto se adjuta en el archivo.

Algunos datos de interes

| Datos        | Descripción        |
|------------------|------------------|
| 75642468    | Total de viajes registrados entre 2015 y 2023    |
| 13413036    | Número de registros dentro de la base de datos    |
| 13406933    | VALLE DE CAUCA en Origenes de Viaje    |
| 10845932    | VALLE DE CAUCA en Destino de Viaje    |

![image](https://github.com/user-attachments/assets/48fddcc9-cda1-4702-be3c-0b8e025f72b2)

Cuando se analiza la totalidad de viajes por años, se muestra una tendencia creciente, excepto por la época de la pandemia, donde se reduce levemeente sin embargo la tedencia es creciente.

![image](https://github.com/user-attachments/assets/ff1f5ff2-0ef9-4069-85e8-2f8200b0509c)

Cuando se analiza los viajes acumulados del mes, se ve una cierta homogeneidad de los datos, con un tendencia aumentar en el segundo semestre el promedio de viajes, se podría considerar una estacionalidad sobre los viajes que a principio de año son bajos y estos van aumentando gradualmente




En la siguiente tabla se observa el Top 10 de Departamentos de Origen y Destino


| Departamento Origen        | Viajes Totales        |Departamento Destino        | Viajes Totales        |
|------------------|------------------|------------------|------------------|
|  VALLE DEL CAUCA   | 13406933    |VALLE DEL CAUCA| 10845932    |
|CUNDINAMARCA       | 11777908    |ANTIOQUIA | 10161808    |         
| ANTIOQUIA      | 9330727    |BOGOTÁ, D. C.| 8784968    |
| BOGOTÁ, D. C.    | 7360401    |CUNDINAMARCA | 8320896    |       
| ATLÁNTICO    | 6284093   |ATLÁNTICO | 4646906    |          
| SANTANDER    | 4285983   |SANTANDER| 4554658    |           
| BOLÍVAR    | 4147649    |BOLÍVAR | 3631088    |            
| BOYACÁ        | 2155075    |BOYACÁ | 2221628  |             
| RISARALDA     | 2031693   |CASANARE | 2008264    |           
| TOLIMA        | 1719922   |META| 1842502    |


