# ProyectoHenry-II - DATA 04
## Axel Moriena - PII-02- Datathon
![image](https://user-images.githubusercontent.com/103937102/199312063-47a110ed-832d-4745-aced-7df92051e94d.png)


#



## Proyecto individual 2
Este será mi segundo proyecto de la carrera de Data Science en Henry.

![image](https://user-images.githubusercontent.com/103937102/199316069-edcc4cf2-46fc-45d0-9e57-c1a3a0ef3910.png)

## Descripción del problema
Usted ha sido contactado de una importante empresa inversora dentro del rubro de la inmobiliaria en Colombia, con el fin de que implemente un modelo de clasificación que permita clasificar el precio de las propiedades en venta, utilizando los datos que se han puesto a su disposición correspondientes al año 2020.Para esto, específicamente, debe predecir la categorización de las propiedades entre baratas o caras, considerando como criterio el valor promedio de los precios (la media).

## Requerimientos para entrega
* Realizar un código script con un Analisis Exploratorio de los Datos. Explicar claramente los pasos realizados mediante comentarios en el script o notebook.
* El proyecto consiste en un datathon, en el que se van creando modelos de Machine Learning para que sean evaluados por los mentores de Henry a través de las métricas de Recall y Accuracy.
* Se proveen dos archivos; uno para poder entrenar, que contiene el precio de las propiedades y en el que hay que realizar una nueva columna como “target”, para poderla utilizar con el fin de entrenar el modelo. Este "target" estará dividido entre "ceros" y "unos". Los "1" para indicar que la propiedad es "cara" y "0" denotando propiedad "barata". 
* La condición de clasificación será el precio promedio de las propiedades. Si son iguales o mayores al promedio serán consideradas "caras", de lo contrario "baratas".
* El otro archivo, que no contiene el precio, se utilizará para predecir los resultados. 
* La evaluación del modelo se realizará con los precios que se encuentran en poder de los mentores de Henry (que suprimieron del dataset). Es decir, la predicción resultante por este modelo, se comparará con los valores de precios reales de las propiedades del archivo de testeo.

### Proceso
De esta manera, utilizando el Notebook “Proyecto II.ipynb” que se encuentra en este repositorio, (https://github.com/AxelM1989/ProyectoHenry-II/blob/main/Proyecto%20II.ipynb), se realizó el EDA (análisis exploratorio de los datos) a través de Pandas en su mayoría. Todo el trabajo fue realizado exclusivamente en Python. Para ello también se utilizaron otras librerías como Scikit-learn, Matplotlib, Seaborn, Numpy, missingno.

Luego de haber analizado el dataset, se limpiaron datos, se dropeando columnas consideradas de no aporte significativo al modelo y se fueron recategorizando features en datos numéricos. Este ultimo paso, necesario ya que los modelos de ML solo reciben datos de tipo numéricos.

Todo el proceso de EDA es el más importante en ML, ya que es indispensable para realizar posteriormente los modelos, por esta razón es la parte que mas conlleva efectuar. Una vez ejecutado el mismo, se divide el dataset en datos de entrenamiento y de prueba (en este caso a través de train_test_split) para poder entrenar.

Claro está que la variable a predecir era una variable “categórica” (propiedad cara o propiedad barata), por lo que nos enfrentamos a un problema de clasificación. Al tener una variable dependiente para que el modelo aprenda en el conjunto de entrenamiento (“target”) se sobreentiende que será un algoritmo supervisado. Por ello a la hora de elegir cual aplicar, el camino se encuentra mas allanado.

El modelo elegido, en este caso, fue el de arboles de decisión y el criterio de la “entropía”. Si bien la capacidad predictiva es superada por otros algoritmos, la razón fundamental de su aplicación radicó en su sencilla implementación y fácil interpretación.

No será motivo de este archivo realizar una explicación de los algoritmos supervisados y no supervisados, ni de los distintos tipos de ellos y sus características.

El archivo “pred.csv” es el que se utiliza para el score del modelo, tiene solamente una columna con los valores predichos y es lo que se solicita por parte de los mentores, para la comprobación del modelo.

## Limitaciones y aclaraciones pertinentes
Se debe aclarar que se realizó este trabajo con una limitación de tiempo por motivos personales ya que hoy 1/11 (un día después de obtener los datasets) debo viajar y volver a final de la semana y por este motivo me enfoqué en poder entregar un modelo mínimo.

Esto significa que soy consciente que el modelo no es adecuado y lejos está de ser óptimo. 

En un futuro lo mejoraré y ya considero algunas opciones para ello:

* Explorar más exhaustivamente el dataset, analizando mejor la distribución de los datos.
* Analizar las coordenadas de "latitud" y "longitud" para ubicar las coordenadas geoespaciales y ver si se identifican con un lugar correcto en el mapa. Intenté utilizar las librerías "folium" y "geopandas" y no pude llegar a un uso adecuado. También considerar emplear esas variables ("latitud" y "longitud").
* Observar comentarios, por ejemplo en las variables "title" y "description", para poder aplicar procesamiento del lenguaje natural (NLP) para mejorar el modelo.
* Probar random forest y otros modelos más complejos que no pude aprender correctamente en el M6 y tampoco en estos dias por el exceso de información, falta de claridad y transparencia en los conceptos y el factor tiempo.
