---
title: ¿Qué es el Generador de modelos y cómo funciona?
description: Cómo usar el Generador de modelos de ML.NET para entrenar un modelo de Machine Learning de forma automática
ms.date: 06/01/2020
ms.custom: overview, mlnet-tooling
ms.openlocfilehash: d7566a03f83eb76999d995a39aaae408405db2e1
ms.sourcegitcommit: b27645cb378d4e8137a267e5467ff31409acf6c0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2021
ms.locfileid: "103231425"
---
# <a name="what-is-model-builder-and-how-does-it-work"></a>¿Qué es el Generador de modelos y cómo funciona?

El Generador de modelos de ML.NET es una extensión gráfica intuitiva de Visual Studio para compilar, entrenar e implementar modelos de Machine Learning personalizados.

El Generador de modelos usa aprendizaje automático automatizado (AutoML) para explorar distintos algoritmos y configuraciones de aprendizaje automático a fin de ayudar a encontrar el más adecuado a cada escenario.

Para usar el Generador de modelos no se necesita experiencia previa con el aprendizaje automático. Lo único que se necesita son algunos datos y un problema para resolver. El Generador de modelos genera el código para agregar el modelo a la aplicación de .NET.

![Animación de la interfaz de usuario de la extensión Generador de modelos de Visual Studio](media/ml-dotnet-model-builder.gif)

> [!NOTE]
> De momento, el Generador de modelos se encuentra en versión preliminar.

## <a name="scenario"></a>Escenario

Se pueden incorporar muchos escenarios diferentes al Generador de modelos a fin de generar un modelo de Machine Learning para la aplicación.

Un escenario es una descripción del tipo de predicción que se quiere realizar usando los datos. Por ejemplo:

- predecir el volumen futuro de ventas de productos en función de los datos de ventas históricos
- clasificar opiniones como positivas o negativas en función de las revisiones de los clientes
- detectar si una transacción bancaria es fraudulenta
- dirigir problemas de comentarios de clientes al equipo correcto de la empresa

Cada escenario se asigna a una tarea de Machine Learning diferente, entre las que se incluyen las siguientes:

- Clasificación binaria
- Clasificación multiclase
- Regresión
- Agrupación en clústeres
- Detección de anomalías
- Clasificación
- Recomendación
- Previsión

Por ejemplo, el escenario de clasificación de opiniones como positivas o negativas se correspondería a la tarea de clasificación binaria.

Para obtener más información sobre las distintas tareas de ML admitidas por ML.NET, vea [Tareas de aprendizaje automático en ML.NET](resources/tasks.md).

### <a name="which-machine-learning-scenario-is-right-for-me"></a>¿Qué escenario de aprendizaje automático es el más adecuado en cada caso?

En el Generador de modelos, debe seleccionar un escenario. El tipo de escenario depende del tipo de predicción que esté intentando realizar.

#### <a name="text-classification"></a>Clasificación de textos

La clasificación se utiliza para clasificar los datos en categorías.

![Diagrama en el que se muestran ejemplos de clasificación binaria, como detección de fraudes, mitigación de riesgos y filtrado de aplicaciones](media/binary-classification-examples.png)

![Ejemplos de clasificación multiclase que incluyen la clasificación de documentos y productos, el enrutamiento de incidencias de soporte técnico y la priorización de problemas de clientes](media/multiclass-classification-examples.png)

#### <a name="value-prediction"></a>Predicción de valores

La predicción de valores, que se corresponde a la tarea de regresión, se usa para predecir números.

![Diagrama en el que se muestran ejemplos de regresión, como la predicción de precios, la previsión de ventas y el mantenimiento predictivo](media/regression-examples.png)

#### <a name="image-classification"></a>Clasificación de la imagen

La clasificación de imágenes se usa para identificar imágenes de distintas categorías. Por ejemplo, diferentes tipos de terreno, animales o defectos de fabricación.

Puede usar el escenario de clasificación de la imagen si tiene un conjunto de imágenes y desea clasificar las imágenes en distintas categorías.

#### <a name="object-detection"></a>Detección de objetos

La detección de objetos se usa para ubicar y categorizar entidades dentro de las imágenes.  Por ejemplo, para buscar e identificar automóviles y personas en una imagen.

Puede usar la detección de objetos cuando las imágenes contengan varios objetos de tipos diferentes.

#### <a name="recommendation"></a>Recomendación

El escenario de recomendaciones predice una lista de elementos sugeridos para un usuario determinado, en función de la similitud y la diferencia entre los usuarios de otros usuarios.

Puede usar el escenario de recomendación cuando tenga un conjunto de usuarios y un conjunto de "productos", como artículos para comprar, películas, libros o programas de TV, junto con un conjunto de "clasificaciones" de los usuarios de esos productos.

## <a name="environment"></a>Entorno

Puede entrenar el modelo de Machine Learning localmente en el equipo o en la nube en Azure, en función del escenario.

Al entrenar localmente, se trabaja dentro de las restricciones de los recursos del equipo (CPU, memoria y disco). Al entrenar en la nube, puede escalar verticalmente los recursos para satisfacer las demandas de su escenario, especialmente para grandes conjuntos de valores.

El entrenamiento de CPU local se admite en todos los escenarios excepto en la detección de objetos.

El entrenamiento de GPU local se admite para la clasificación de imágenes.

El entrenamiento de Azure se admite para la clasificación de imágenes y la detección de objetos.

## <a name="data"></a>Datos

Una vez que ha elegido el escenario, el generador de modelos pide que se proporcione un conjunto de datos. Los datos se usan para entrenar, evaluar y elegir el mejor modelo para el escenario.

![Diagrama en el que se muestran los pasos del generador de modelos](media/model-builder-steps.png)

El generador de modelos admite conjuntos de datos en formatos. tsv,. csv,. txt, así como en el formato de base datos SQL. Si tiene un archivo. txt, las columnas se deben separar con `,`, `;` o `/t`, y el archivo debe tener una fila de encabezado.

Si el conjunto de archivos se compone de imágenes, los tipos de archivo admitidos son `.jpg` y `.png`.

Para obtener más información, vea [Carga de datos de entrenamiento en el Generador de modelos](how-to-guides/load-data-model-builder.md).

### <a name="choose-the-output-to-predict-label"></a>Selección del resultado que se va a predecir (etiqueta)

Un conjunto de datos es una tabla de filas de ejemplos de entrenamiento y columnas de atributos. Cada fila tiene:

- una **etiqueta** (el atributo que se quiere predecir)
- **características** (atributos que se usan como entradas para predecir la etiqueta).

En el escenario de predicción del precio de las viviendas, las características podrían ser:

- los metros cuadrados de la vivienda
- el número de dormitorios y baños
- el código postal

La etiqueta es el precio histórico de la vivienda para esa fila de valores de metros cuadrados, baños y dormitorios y el código postal.

![Tabla donde se muestran las filas y columnas de datos de precios de viviendas con características que constan de etiquetas de tamaño, habitaciones, código postal y precio](media/model-builder-data.png)

### <a name="example-datasets"></a>Conjuntos de datos de ejemplo

Si aún no tiene datos propios, pruebe uno de estos conjuntos de datos:

|Escenario|Ejemplo|Datos|Etiqueta|Características|
|-|-|-|-|-|
|Clasificación|Predicción de anomalías de ventas|[datos de ventas de productos](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)|Ventas de productos|Mes|
||Predicción de sentimiento de comentarios de sitios web|[datos de comentarios de sitio web](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv)|Etiqueta (0 si la opinión es negativa, 1 si es positiva)|Comentario, año|
||Predicción de transacciones de tarjetas de crédito fraudulentas|[datos de tarjetas de crédito](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_CreditCardFraudDetection/CCFraudDetection.Trainer/assets/input/creditcardfraud-dataset.zip)|Clase (1 si es fraudulenta, en caso contrario, 0)|Cantidad, V1-V28 (características anónimas)|
||Predecir el tipo de problema en un repositorio de GitHub|[datos de problemas de GitHub](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/end-to-end-apps/MulticlassClassification-GitHubLabeler/GitHubLabeler/Data/corefx-issues-train.tsv)|Área|Título, descripción|
|Predicción de valores|Predicción del precio de los taxis|[datos de carreras de taxi](https://github.com/dotnet/machinelearning-samples/blob/master/datasets/taxi-fare-train.csv)|Carrera|Tiempo de viaje, distancia|
|Clasificación de la imagen|Predicción de la categoría de una flor |[imágenes de flores](http://download.tensorflow.org/example_images/flower_photos.tgz)|El tipo de flor: margarita, diente de león, rosas, girasoles o tulipanes|Los propios datos de la imagen|
|Recomendación|Predicción de películas que le gusten a alguien|[clasificaciones de películas](http://files.grouplens.org/datasets/movielens/ml-latest-small.zip)|Usuarios, películas|Clasificaciones|

## <a name="train"></a>Entrenamiento

Una vez que se seleccionan el escenario, el entorno, los datos y la etiqueta, el Generador de modelos entrena el modelo.

### <a name="what-is-training"></a>¿Qué es el entrenamiento?

El entrenamiento es un proceso automático mediante el cual el Generador de modelos enseña al modelo a responder a preguntas del escenario. Una vez entrenado, el modelo puede realizar predicciones con datos de entrada que no ha visto antes. Por ejemplo, si está prediciendo los precios de la vivienda y se pone en el mercado un nuevo inmueble, puede predecir su precio de venta.

Dado que el Generador de modelos usa aprendizaje automático automatizado (AutoML), no requiere ninguna entrada ni ajuste por parte del usuario durante el entrenamiento.

### <a name="how-long-should-i-train-for"></a>¿Durante cuánto tiempo debe entrenarse?

El generador de modelos usa AutoML para explorar varios modelos y encontrar el mejor modelo de rendimiento.

Los períodos de entrenamiento más largos permiten a AutoML explorar más modelos con una mayor variedad de opciones de configuración.

En la tabla siguiente se resume el tiempo promedio necesario para obtener un buen rendimiento en un conjunto de conjuntos de valores de ejemplo, en un equipo local.

|Tamaño del conjunto de datos|Promedio de tiempo para entrenar|
|------------|---------------------|
|0-10 MB|10 s|
|10-100 MB|10 min|
|100-500 MB|30 min|
|500-1 GB|60 min|
|1 GB o más|3 horas o más|

Estos números son solo una guía. La duración exacta del entrenamiento depende de varios factores:

- El número de características (columnas) que se usan como entrada para el modelo
- El tipo de columnas
- La tarea de ML
- El rendimiento de la CPU, el disco y la memoria de la máquina usada para el entrenamiento

Por lo general, se aconseja que use más de 100 filas, ya que es posible que los conjuntos de datos con una cantidad menor no generen ningún resultado y tarden mucho más tiempo en entrenarse.

## <a name="evaluate"></a>Evaluate

La evaluación es el proceso por el que se mide el grado de calidad del modelo. El Generador de modelo usa el modelo entrenado para realizar predicciones con nuevos datos de prueba y luego mide la calidad de las predicciones.

El Generador de modelos divide los datos de entrenamiento en un conjunto de entrenamiento y un conjunto de prueba. Los datos de entrenamiento (80 %) se usan para entrenar el modelo y los datos de prueba (20 %) se incluyen para evaluar el modelo.

### <a name="how-do-i-understand-my-model-performance"></a>¿Cómo puedo interpretar el rendimiento de mi modelo?

Un escenario se asigna a una tarea de aprendizaje automático. Cada tarea de ML tiene su propio conjunto de métricas de evaluación.

#### <a name="value-prediction"></a>Predicción de valores

La métrica predeterminada para los problemas de predicción de valores es RSquared, y el valor de RSquared oscila entre 0 y 1. 1 es el mejor valor posible o, en otras palabras, cuanto más se acerque el valor de RSquared a 1, mejor será el rendimiento del modelo.

Otras métricas notificadas, como pérdida absoluta, pérdida al cuadrado y pérdida RMS son métricas adicionales, que pueden usarse para comprender el rendimiento del modelo y compararlo con otros modelos de predicción de valores.

#### <a name="classification-2-categories"></a>Clasificación (2 categorías)

La métrica predeterminada para los problemas de clasificación es la precisión. La precisión define la proporción de predicciones correctas que realiza el modelo en el conjunto de datos de prueba. Cuanto más cerca esté del 100 % o 1.0, mejor será el modelo.

Otras métricas notificadas, como AUC (área bajo la curva), que mide la tasa de positivos verdaderos frente a la tasa de falsos positivos, deben ser superiores a 0,50 para que los modelos sean aceptables.

Se pueden usar métricas adicionales como la puntuación F1 para controlar el equilibrio entre la precisión y la coincidencia.

#### <a name="classification-3-categories"></a>Clasificación (3 categorías)

La métrica predeterminada para la clasificación multiclase es la microprecisión. Cuanto más se acerque la microprecisión al 100 % o 1,0, mejor será el modelo.

Otra métrica importante para la clasificación multiclase es la macroprecisión, que, de forma similar a la de la microprecisión, cuanto más se acerque a 1,0 mejor será el modelo. Una buena manera de imaginarse estos dos tipos de precisión es el siguiente:

- Microprecisión: ¿con qué frecuencia se clasifica una incidencia entrante en el equipo adecuado?
- Macroprecisión: para un equipo promedio, ¿con qué frecuencia es correcta una incidencia entrante para su equipo?

### <a name="more-information-on-evaluation-metrics"></a>Más información sobre las métricas de evaluación

Para obtener más información, vea [Métricas de evaluación de modelos](resources/metrics.md).

## <a name="improve"></a>Mejora

Si la puntuación de rendimiento del modelo no es tan buena como se quiere que sea, se puede:

- Entrenar durante más tiempo. Con más tiempo, el motor de aprendizaje automático automatizado experimenta con más algoritmos y configuraciones.

- Agregar más datos. A veces la cantidad de datos no es suficiente para entrenar un modelo de Machine Learning de alta calidad. Esto es especialmente cierto en el caso de conjuntos de datos que tienen un número de ejemplos menor.

- Equilibrar los datos. En las tareas de clasificación, asegúrese de que el conjunto de entrenamiento esté equilibrado entre las categorías. Por ejemplo, si tiene cuatro clases de 100 ejemplos de entrenamiento y las dos primeras (etiqueta1 y etiqueta2) se usan para 90 registros, pero las otras dos (etiqueta3 y etiqueta4) solo se usan en los 10 registros restantes, la falta de datos equilibrados puede hacer que el modelo se esfuerce por predecir correctamente etiqueta3 o etiqueta4.

## <a name="code"></a>Código

Después de la fase de evaluación, el Generador de modelos genera un archivo de modelo y el código que se puede usar para agregar el modelo a la aplicación. Los modelos de ML.NET se guardan como un archivo zip. El código para cargar y usar el modelo se agrega como un nuevo proyecto a la solución. El Generador de modelos también agrega una aplicación de consola de ejemplo que se puede ejecutar para ver el modelo en acción.

Además, el Generador de modelos produce el código que ha generado el modelo, para que pueda entender los pasos llevados a cabo para generar el modelo. También puede usar el código de entrenamiento del modelo para volver a entrenar el modelo con nuevos datos.

## <a name="whats-next"></a>Pasos adicionales

[Instalar](how-to-guides/install-model-builder.md) la extensión de Visual Studio del generador de modelos

Pruebe la [predicción de precios o cualquier escenario de regresión](tutorials/predict-prices-with-model-builder.md)
