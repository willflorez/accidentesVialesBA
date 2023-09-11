# SegundoProyectoIndividualHenry
<p align="center">
<img src="https://user-images.githubusercontent.com/67664604/217914153-1eb00e25-ac08-4dfa-aaf8-53c09038f082.png"  height=300>
</p>

## Índice 
<!-- TABLA DE CONTENIDO -->
<details>
  <summary>Tabla de contenido</summary>
  <ol>  
    <li><a href="#Introducción">Introducción</a></li>
    <li><a href="#Objetivo">Objetivo</a></li>
    <li><a href="#pila-de-tecnologías">Pila de Tecnologías</a></li>
    <li><a href="#EDA">EDA</a></li>
    <li><a href="# ESTUDIANDO EL PRIMER KPI">KPI 1</a></li>
    <li><a href="#ABORDANDO EL SEGUNDO KPI">KPI 2</a></li>
    <li><a href="#ESTUDIANDO EL TERCER KPI">KPI 3</a></li>
  </ol>
</details>

## Introducción
En este proyecto individual como parte de la formación de la carrera de Data Science de Henry, desempeño el papel de un Data Analyst, recibo un conjunto de datos de accidentes viales de la ciudad autónoma de Buenos Aires. En los datos hay información acerca de los actores viales involucrados en accidentes de tránsito en el lapso comprendido entre los años 2016 y 2021. 
## Objetivo

1. Analizar detalladamente el conjunto de datos para entender la situación problema de la manera correcta, sin conjeturas propias y ceñirme a la realidad que la información entrega.
2. Crear un dashboard para la presentación del análisis hecho por mi de los datos entregados.

**Primer acercamiento al conjunto de datos:** El conjunto de datos se encontraba casi listo para trabajar, pocos datos nulos o faltantes, ningún registro duplicado. Existían valores marcados como 'SD', la mayoría los conservé, porque entendí que es un inidicador de la imposibilidad de determinación, por ejemplo, en un accidente de tránsito la edad del fallecido se encuentra sin dato.

**Analisis Exploratorio de Datos** El objetivo es entender que conclusiones pueden obtenerse a partir de los datos entregados. Existen columnas que esclarecen la ubicación del accidente, otras que especifican la victima y otras de valor tipo tiempo, abordando todos los detalles del siniestro.


## Conjunto de Tecnologías

![Visual Studio Code](https://img.shields.io/badge/Visual%20Studio%20Code-0078d7.svg?style=for-the-badge&logo=visual-studio-code&logoColor=white)
![Jupyter Notebook](https://img.shields.io/badge/jupyter-%23FA0F00.svg?style=for-the-badge&logo=jupyter&logoColor=white)
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black)
![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi)
![Git](https://img.shields.io/badge/git-%23F05033.svg?style=for-the-badge&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white)
![Markdown](https://img.shields.io/badge/markdown-%23000000.svg?style=for-the-badge&logo=markdown&logoColor=white)


## EDA

En la exploración de datos evidencio que puede obtenerse toda la información necesaria para individualizar cada hecho. Conozco la fecha de ocurrencia del evento, la ubicación, el número de víctimas, los actores viales involucrados, el tipo de corredor vial que sirve como escenario del siniestro, el sexo de los partipantes y el papel que jugaron, el tipo de vehículo partipante.

*Estos procesos se desarrollaron localmente en **Visual Studio Code (VSCODE)** utilizando **Jupyter Notebook** como entorno de trabajo. La combinación de herramientas tecnológicas empleada esta basada en **Python** como lenguaje de programación, junto con librerias  como **numpy y pandas** para la manipulación de datos. Además, se utilizo **matplotlib y seaborn** para la creación de visualizaciones gráficas.*

**1. Columna Altura: Se elimina por cuanto su número de valores nulos es demasiado alto (567). Mostraba la nomenclatura del hecho, un dato que puede reemplazarse con el contenido en otras columnas.

**2. Columna Cruce: Con 171 datos nulos se conserva, se transforma en una columna que tiene como datos los valores 'SI' o 'NO', mi intención es cuantificar el impacto de los cruces en la cantidad de accidentes, mas allá de conocer el nombre de la calle, los valores nulos son ahora 'SD', sin dato de cruce o cruce inexistente.

TODAS LAS TRANSFORMACIONES SE REALIZAN EN PRO DEL ANALISIS CORRECTO DE LOS DATOS Y SU GRAFICACION Y POSTERIOR REALIZACION DE DASHBOARD EN POWER BI.

**3. Columna HORA: Transformada en tipo datetime, era de tipo objeto.

**4. Columnas pos x y pos y: Transformadas a tipo float, erand etipo objeto.

**5. Adelanto la exportación de los datos a un archivo de tipo csv y aplico funcion describe(), queriendo conocer mejor el conjunto de datos.

	N_VICTIMAS	AAAA	MM	DD	COMUNA	pos x	pos y
count	696.000000	696.000000	696.000000	696.000000	696.000000	684.000000	684.000000
mean	1.030172	2018.188218	6.692529	15.936782	7.425287	-58.441545	-34.619632
std	0.179393	1.683754	3.571309	8.639646	4.387050	0.046144	0.035289
min	1.000000	2016.000000	1.000000	1.000000	0.000000	-58.529942	-34.705250
25%	1.000000	2017.000000	4.000000	9.000000	4.000000	-58.476218	-34.643689
50%	1.000000	2018.000000	7.000000	16.000000	8.000000	-58.444513	-34.622928
75%	1.000000	2020.000000	10.000000	23.000000	11.000000	-58.401841	-34.596799
max	3.000000	2021.000000	12.000000	31.000000	15.000000	-58.356082	-34.534654

## ESTUDIANDO EL PRIMER KPI

RESPECTO A CANTIDAD DE VICTIMAS:

**6. El paso obligado por la curiosidad es conocer numero de víctimas por año, de esta manera:

AAAA	N_VICTIMAS
0	2016	146
1	2017	140
2	2018	149
3	2019	104
4	2020	81
5	2021	97

Creo la columna semestre para considerar el primer KPI (reducir en un 10% la tasa de homicidios en siniestros viales de los últimos seis meses, en CABA, en comparación con la tasa de homicidios en siniestros viales del semestre anterior), el número de fallecidos por semestre acá:

AAAA	Semestre	N_VICTIMAS
0	2016	1	65
1	2016	2	81
2	2017	1	69
3	2017	2	71
4	2018	1	70
5	2018	2	79
6	2019	1	57
7	2019	2	47
8	2020	1	31
9	2020	2	50
10	2021	1	55
11	2021	2	42

CONCLUSION DE LA TABLA ANTERIOR RESPECTO A LA CANTIDAD DE VICTIMAS POR SEMESTRE: 
EN EL SEGUNDO SEMESTRE DEL AÑO 2021 RESPECTO AL PRIMERO DE ESE MISMO AÑO EXISTE UNA REDUCCION DEL 24%. EN EL PRIMER SEMESTRE DEL AÑO 2020 EXISTE UNA REDUCCION DEL 34%. EN EL SEGUNDO SEMESTRE DEL AÑO 2019 EXISTE UNA REDUCCION DEL 18%. EN EL PRIMER SEMESTRE DEL AÑO 2019 RESPECTO AL SEGUNDO SEMESTRE DEL AÑO ANTERIOR EXISTE UNA REDUCCION DEL 28%. EN EL PRIMER SEMESTRE DEL AÑO 2017 RESPECTO AL SEGUNDO SEMESTRE DEL AÑO ANTERIOR EXISTE UNA REDUCCION DEL 15%.

El peor de los meses: 
Año 2016: El mes con más siniestros (19 víctimas) fue el mes 12
Año 2017: El mes con más siniestros (18 víctimas) fue el mes 5
Año 2018: El mes con más siniestros (16 víctimas) fue el mes 8
Año 2019: El mes con más siniestros (14 víctimas) fue el mes 8
Año 2020: El mes con más siniestros (22 víctimas) fue el mes 12
Año 2021: El mes con más siniestros (13 víctimas) fue el mes 1

ME PERMITO CONCLUIR CON BASE EN LAS TABLAS ANTERIORES QUE LOS SINIESTROS SON UN CONJUNTO DE DATOS MUY DISTRIBUIDOS A LO LARGO DEL TIEMPO Y NO EXISTE UN MES O AÑO QUE LLAME LA ATENCION POR UNA FUERTE SUBIDA EN LA CANTIDAD DE VICTIMAS FATALES


RESPECTO A LA UBICACION:

**7. Distribución de víctimas por comunas.

COMUNA	N_VICTIMAS
	1	93
	2	25
	3	46
	4	79
	5	22
	6	22
	7	62
	8	67
	9	75
	10	30
	11	33
	12	39
	13	40
	14	37
	15	45

Comuna 1 la de mayor accidentalidad. El top 5 lo completan las comunas 4, 8, 9 y 7.

En el archivo EDA.ipynb se explora la hora de mayor accidentalidad y los actores viales involucrados.

**8. El tipo de calle donde más se presentan accidentes es la 'Avenida' como lo muestra la siguiente tabla, la primera de ellas presenta 57 accidentes, su nombre y su tipo a continuación.

Calle
PAZ, GRAL. AV.                                57
RIVADAVIA AV.                                 19
DEL LIBERTADOR AV.                            18
AUTOPISTA 1 SUR PRESIDENTE ARTURO FRONDIZI    14
ALBERDI, JUAN BAUTISTA AV.                    13
                                              ..
PILCOMAYO                                      1
CERVANTES                                      1
CONGRESO AV.                                   1
AUSTRALIA AV.                                  1
PADRE CARLOS MUJICA                            1

PARA MAYOR COMPRENSION DE ESTOS ANUNCIADOS POR FAVOR REVISAR EL ARCHIVO EDA.ipynb EN EL MOMENTO DESEADO.

Existe una gráfica donde se compara la comuna y sus tipos de calle, la comuna 1 cuenta con varias avenidas, es in indicador de su cantidad de accidentes. (Se estableció que las avenidas presentan mas accidentalidad, la comuna 1 es la que mas avenidas tiene).

**9. El gráfico de los sitios de los accidentes evidencia que los hechos ocurren a lo largo y ancho de CABA, sin concentración de siniestros en un lugar en particular. Ver gráfica con GeoPandas.

DE LOS DIAS AL FALLECIMIENTO:

**10. Creé una columna que se llama 'Dias al Fallecimiento' tuve curiosidad de saber si todas las víctimas morían el mismo día, lo hacen la mayoría de involucrados (mas de 500 casos) y otros hasta 25 días después.

RESPECTO DE QUIENES MUEREN

**11. El actor vial 'MOTO' es junto con el 'PEATON' el protagonista principal de la mayoria de accidentes, el género masculino es el preponderante en las víctimas. De nuevo ver EDA.ipynb.

CONCLUSION DE ESTE APARTADO.

De la categoría víctimas, las motos y los peatones son los mas afectados. Cuando se analiza la cantidad de víctimas en moto el conductor es el mas impactado (categoria ROL), los hombres mueren mas en este estudio que las mujeres, el rango etario que concentra la mayor cantidad de hechos es de 20 a 39. La comuna 1 es un escenario peligroso.

DEL PRIMER KPI:

EL SEGUNDO SEMESTRE DEL AÑO 2021 CUMPLE CON LA REDUCCION DEL 10%. SE ESPERABA UNA TASA DE HOMICIDIOS DE ACCIDENTES VIALES IGUAL A 1.49% (EL PRIMER SEMESTRE DE ESE AÑO FUE DE 1.65) Y SE OBTUVO UNA TASA DE 1.26. 

SE DEFINIO ASI: 'Definimos a la tasa de homicidios en siniestros viales como el número de víctimas fatales en accidentes de tránsito por cada 100,000 habitantes en un área geográfica durante un período de tiempo específico. Su fórmula es: (Número de homicidios en siniestros viales / Población total) * 100,000'

POBLACION DE CABA PARA LA FECHA 3.317.463 HABITANTES, SEGUN LA ALCALDIA DE BS AS.


## ABORDANDO EL SEGUNDO KPI: 

Reducir en un 7% la cantidad de accidentes mortales de motociclistas en el último año, en CABA, respecto al año anterior.

**12. Grafico teniendo en cuenta la cantidad de accidentes donde se involucran motos en el periodo de tiempo estudiado, hallo el porcentaje de hombres y mujeres fallecidos, porcentaje de conductores y acompañantes, con el ánimo de comprender mejor la situación,. Abajo una tabla de numero de fallecidos cuando el ROL es conductor y VICTIMA es moto:

AAAA	N_VICTIMAS	Cambio_Porcentual
2016	56	        NaN
2017	48	        -14.285714
2018	53	        10.416667
2019	45	        -15.094340
2020	27	        -40.000000
2021	39	        44.444444

DEL SEGUNDO KPI :  NO SE CUMPLE, LA TASA OBJETIVO ERA DE 33.48 Y SE OBTUVO -47.75% HUBO UN INCREMENTO EN EL NUMERO DE ACCIDENTES.

SE DEFINIO ASI:'Definimos a la cantidad de accidentes mortales de motociclistas en siniestros viales como el número absoluto de accidentes fatales en los que estuvieron involucradas víctimas que viajaban en moto en un determinado periodo temporal. Su fórmula para medir la evolución de los accidentes mortales con víctimas en moto es: (Número de accidentes mortales con víctimas en moto en el año anterior - Número de accidentes mortales con víctimas en moto en el año actual) / (Número de accidentes mortales con víctimas en moto en el año anterior) * 100'


## ESTUDIANDO EL TERCER KPI: 
Reducir en un 5% la cantidad de accidentes mortales de peatones en el último año, en CABA, respecto al año anterior.






DEL TERCER KPI: 


SE DEFINIO ASI: 'DISMINUCION DEL 5% DE MUERTES DE PEATON RESPECTO DEL AÑO ANTERIOR. DEFINIENDOLO COMO (ACCIDENTES MORTALES DE PEATONES EN EL AÑO ANTERIOR - ACCIDENTES MORTALES AÑO ACTUAL) / (ACCIDENTES MORTALES DE PEATONES EN EL AÑO ANTERIOR) * 100'





