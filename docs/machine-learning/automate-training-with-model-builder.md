---
title: ¿Qué es el Generador de modelos y cómo funciona?
description: Cómo usar el Generador de modelos de ML.NET para entrenar un modelo de Machine Learning de forma automática
ms.date: 01/07/2020
ms.custom: overview
ms.openlocfilehash: ac704b7961a8442a9174cdef5a4cd2a619236a4e
ms.sourcegitcommit: cbdc0f4fd39172b5191a35200c33d5030774463c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "75777402"
---
# <a name="what-is-model-builder-and-how-does-it-work"></a>¿Qué es el Generador de modelos y cómo funciona?

El Generador de modelos de ML.NET es una extensión gráfica intuitiva de Visual Studio para compilar, entrenar e implementar modelos de Machine Learning personalizados.

El Generador de modelos usa aprendizaje automático automatizado (AutoML) para explorar distintos algoritmos y configuraciones de aprendizaje automático a fin de ayudar a encontrar el más adecuado a cada escenario.

Para usar el Generador de modelos no se necesita experiencia previa con el aprendizaje automático. Lo único que se necesita son algunos datos y un problema para resolver. El Generador de modelos genera el código para agregar el modelo a la aplicación de .NET.

![Animación de la interfaz de usuario de la extensión Generador de modelos de Visual Studio](media/ml-dotnet-model-builder.gif)

> [!NOTE]
> De momento, el Generador de modelos se encuentra en versión preliminar.

## <a name="scenarios"></a>Escenarios

Se pueden incorporar muchos escenarios diferentes al Generador de modelos a fin de generar un modelo de Machine Learning para la aplicación.

Un escenario es una descripción del tipo de predicción que se quiere realizar usando los datos. Por ejemplo:

- predecir el volumen futuro de ventas de productos en función de los datos de ventas históricos
- clasificar opiniones como positivas o negativas en función de las revisiones de los clientes
- detectar si una transacción bancaria es fraudulenta
- dirigir problemas de comentarios de clientes al equipo correcto de la empresa

### <a name="which-machine-learning-scenario-is-right-for-me"></a>¿Qué escenario de aprendizaje automático es el más adecuado en cada caso?

En el Generador de modelos, debe seleccionar un escenario. El tipo de escenario depende del tipo de predicción que esté intentando realizar.

#### <a name="predict-a-category-when-there-are-only-two-categories"></a>Predecir una categoría (que cuente solo con dos categorías)

La clasificación binaria se usa para clasificar los datos en dos categorías (sí o no; correcto o incorrecto; verdadero o falso; positivo o negativo).

![Diagrama en el que se muestran ejemplos de clasificación binaria, como detección de fraudes, mitigación de riesgos y filtrado de aplicaciones](media/binary-classification-examples.png)

El análisis de opiniones se puede usar para predecir una opinión positiva o negativa de los comentarios del cliente. Es un ejemplo de la tarea de aprendizaje automático de clasificación binaria.

Si el escenario requiere clasificación en dos categorías, puede usar esta plantilla con un conjunto de datos propio.

#### <a name="predict-a-category-when-there-are-three-or-more-categories"></a>Predecir una categoría (que cuente con tres categorías o más)

La clasificación multiclase puede usarse para clasificar los datos en tres o más clases.

![Ejemplos de clasificación multiclase que incluyen la clasificación de documentos y productos, el enrutamiento de incidencias de soporte técnico y la priorización de problemas de clientes](media/multiclass-classification-examples.png)

La clasificación de problemas se puede usar para clasificar problemas de comentarios de clientes (por ejemplo, en GitHub) mediante el título y la descripción del problema. Es un ejemplo del tipo de tarea de aprendizaje automático de clasificación multiclase.

Puede usar la plantilla de clasificación de problemas para el escenario si quiere clasificar los datos en tres o más categorías.

#### <a name="predict-a-number"></a>Predecir un número

La regresión se usa para predecir números.

![Diagrama en el que se muestran ejemplos de regresión, como la predicción de precios, la previsión de ventas y el mantenimiento predictivo](media/regression-examples.png)

La predicción de precios puede usarse para predecir los precios de viviendas según la ubicación, el tamaño y otras características del inmueble. Es un ejemplo de la tarea de aprendizaje automático de regresión.

Puede usar la plantilla de predicción de precios para el escenario si quiere predecir un valor numérico con un conjunto de datos propio.

#### <a name="classify-images-into-categories"></a>Clasificación de imágenes en categorías

Este escenario es un caso especial de clasificación multiclase, en la que los datos de entrada que se van a clasificar son un conjunto de imágenes.

La clasificación de la imagen se puede utilizar para identificar imágenes de distintas categorías. Por ejemplo, diferentes tipos de terreno, animales o defectos de fabricación.

Puede usar la plantilla de clasificación de la imagen para su escenario si tiene un conjunto de imágenes y desea clasificar las imágenes en distintas categorías.

#### <a name="custom-scenario"></a>Escenario personalizado

El escenario personalizado permite elegir manualmente el escenario.

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

|Escenario|Tarea de Machine Learning|Datos|Etiqueta|Características|
|-|-|-|-|-|
|Predicción de precios|Regresión|[datos de carreras de taxi](https://github.com/dotnet/machinelearning-samples/blob/master/datasets/taxi-fare-train.csv)|Carrera|Tiempo de viaje, distancia|
|Detección de anomalías|Clasificación binaria|[datos de ventas de productos](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)|Ventas de productos|Mes|
|Análisis de sentimiento|Clasificación binaria|[datos de comentarios de sitio web](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv)|Etiqueta (0 si la opinión es negativa, 1 si es positiva)|Comentario, año|
|Detección de fraudes|Clasificación binaria|[datos de tarjetas de crédito](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_CreditCardFraudDetection/CreditCardFraudDetection.Trainer/assets/input/creditcardfraud-dataset.zip)|Clase (1 si es fraudulenta, en caso contrario, 0)|Cantidad, V1-V28 (características anónimas)|
|Clasificación de textos|Clasificación multiclase|[datos de problemas de GitHub](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/end-to-end-apps/MulticlassClassification-GitHubLabeler/GitHubLabeler/Data/corefx-issues-train.tsv)|Área|Título, descripción|
|Clasificación de la imagen|Clasificación multiclase|[Imágenes de flores](http://download.tensorflow.org/example_images/flower_photos.tgz)|El tipo de flor: margarita, diente de león, rosas, girasoles o tulipanes|Los propios datos de la imagen|

## <a name="train"></a>Entrenamiento

Una vez que se seleccionan el escenario, los datos y la etiqueta, el Generador de modelos entrena el modelo.

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

## <a name="evaluate"></a>Evaluate

La evaluación es el proceso por el que se mide el grado de calidad del modelo. El Generador de modelo usa el modelo entrenado para realizar predicciones con nuevos datos de prueba y luego mide la calidad de las predicciones.

El Generador de modelos divide los datos de entrenamiento en un conjunto de entrenamiento y un conjunto de prueba. Los datos de entrenamiento (80 %) se usan para entrenar el modelo y los datos de prueba (20 %) se incluyen para evaluar el modelo. 

### <a name="how-do-i-understand-my-model-performance"></a>¿Cómo puedo interpretar el rendimiento de mi modelo?

Un escenario se asigna a una tarea de aprendizaje automático. Cada tarea de ML tiene su propio conjunto de métricas de evaluación.

#### <a name="regression-for-example-price-prediction"></a>Regresión (por ejemplo, predicción de precios)

La métrica predeterminada para los problemas de regresión es RSquared, y el valor de RSquared oscila entre 0 y 1. 1 es el mejor valor posible o, en otras palabras, cuanto más se acerque el valor de RSquared a 1, mejor será el rendimiento del modelo.

Otras métricas notificadas, como pérdida absoluta, pérdida al cuadrado y pérdida RMS son métricas adicionales, que pueden usarse para comprender el rendimiento del modelo y compararlo con otros modelos de regresión.

#### <a name="binary-classification-for-example-sentiment-analysis"></a>Clasificación binaria (por ejemplo, Análisis de sentimiento)

La métrica predeterminada para los problemas de clasificación es la precisión. La precisión define la proporción de predicciones correctas que realiza el modelo en el conjunto de datos de prueba. Cuanto más cerca esté del 100 % o 1.0, mejor será el modelo.

Otras métricas notificadas, como AUC (área bajo la curva), que mide la tasa de positivos verdaderos frente a la tasa de falsos positivos, deben ser superiores a 0,50 para que los modelos sean aceptables.

Se pueden usar métricas adicionales como la puntuación F1 para controlar el equilibrio entre la precisión y la coincidencia.

#### <a name="multi-class-classification-for-example-issue-classification-image-classification"></a>Clasificación multiclase (por ejemplo, Clasificación de problemas y Clasificación de la imagen)

La métrica predeterminada para la clasificación multiclase es la microprecisión. Cuanto más se acerque la microprecisión al 100 % o 1,0, mejor será el modelo.

Otra métrica importante para la clasificación multiclase es la macroprecisión, que, de forma similar a la de la microprecisión, cuanto más se acerque a 1,0 mejor será el modelo. Una buena manera de imaginarse estos dos tipos de precisión es el siguiente:

- Microprecisión: ¿con qué frecuencia se clasifica una incidencia entrante en el equipo adecuado?
- Macroprecisión: para un equipo promedio, ¿con qué frecuencia es correcta una incidencia entrante para su equipo?

### <a name="more-information-on-evaluation-metrics"></a>Más información sobre las métricas de evaluación

Para obtener más información, vea [Métricas de evaluación de modelos](resources/metrics.md).

## <a name="improve"></a>Mejora

Si la puntuación de rendimiento del modelo no es tan buena como se quiere que sea, se puede:

- Entrenar durante más tiempo. Con más tiempo, el motor de aprendizaje automático automatizado prueba más algoritmos y configuraciones.

- Agregar más datos. A veces la cantidad de datos no es suficiente para entrenar un modelo de Machine Learning de alta calidad.

- Equilibrar los datos. En las tareas de clasificación, asegúrese de que el conjunto de entrenamiento esté equilibrado entre las categorías. Por ejemplo, si tiene cuatro clases de 100 ejemplos de entrenamiento y las dos primeras (etiqueta1 y etiqueta2) se usan para 90 registros, pero las otras dos (etiqueta3 y etiqueta4) solo se usan en los 10 registros restantes, la falta de datos equilibrados puede hacer que el modelo se esfuerce por predecir correctamente etiqueta3 o etiqueta4.

## <a name="code"></a>Código

Después de la fase de evaluación, el Generador de modelos genera un archivo de modelo y el código que se puede usar para agregar el modelo a la aplicación. Los modelos de ML.NET se guardan como un archivo zip. El código para cargar y usar el modelo se agrega como un nuevo proyecto a la solución. El Generador de modelos también agrega una aplicación de consola de ejemplo que se puede ejecutar para ver el modelo en acción.

Además, el Generador de modelos produce el código que ha generado el modelo, para que pueda entender los pasos llevados a cabo para generar el modelo. También puede usar el código de entrenamiento del modelo para volver a entrenar el modelo con nuevos datos.

## <a name="whats-next"></a>Pasos adicionales

[Instalar](how-to-guides/install-model-builder.md) la extensión de Visual Studio del generador de modelos

Pruebe la [predicción de precios o cualquier escenario de regresión](tutorials/predict-prices-with-model-builder.md)
