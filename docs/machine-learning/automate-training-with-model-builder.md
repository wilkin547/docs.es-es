---
title: ¿Qué es el Generador de modelos y cómo funciona?
description: Cómo usar el Generador de modelos de ML.NET para entrenar un modelo de Machine Learning de forma automática
author: natke
ms.date: 06/26/2019
ms.custom: overview
ms.openlocfilehash: 6f5bbe3c389e3ca42550a48ef3e6edbc963ac2e9
ms.sourcegitcommit: 52e588dc2ee74d484cd07ac60076be25cbf777ab
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2019
ms.locfileid: "67410593"
---
# <a name="what-is-model-builder-and-how-does-it-work"></a>¿Qué es el Generador de modelos y cómo funciona?

El Generador de modelos de ML.NET es una extensión gráfica fácil de entender de Visual Studio para compilar, entrenar e implementar modelos de Machine Learning personalizados. 

El Generador de modelos usa aprendizaje automático automatizado (AutoML) para explorar distintos algoritmos y configuraciones de aprendizaje automático a fin de ayudar a encontrar el más adecuado a cada escenario.

Para usar el Generador de modelos no se necesita experiencia previa con el aprendizaje automático. Lo único que se necesita son algunos datos y un problema para resolver. El Generador de modelos genera el código para agregar el modelo a la aplicación de .NET.

![Animación de la interfaz de usuario de la extensión Generador de modelos de Visual Studio](media/ml-dotnet-model-builder.gif)

> [!NOTE]
> De momento, el Generador de modelos se encuentra en versión preliminar.

## <a name="scenarios"></a>Escenarios

Se pueden incorporar muchos escenarios diferentes al Generador de modelos a fin de generar un modelo de Machine Learning para la aplicación.

Un escenario es una descripción del tipo de predicción que se quiere realizar en los datos. Por ejemplo:
- predecir el volumen futuro de ventas de productos en función de los datos de ventas históricos
- clasificar opiniones como positivas o negativas en función de las revisiones de los clientes
- detectar si una transacción bancaria es fraudulenta
- dirigir problemas de comentarios de clientes al equipo correcto de la empresa

En el Generador de modelos es necesario asignar el escenario a una [tarea de ML.NET](resources/tasks.md). Puede usar el Generador de modelos para la **regresión** (predicción de números) y la **clasificación** (predicción de categorías).

### <a name="which-machine-learning-scenario-is-right-for-me"></a>¿Qué escenario de aprendizaje automático es el más adecuado en cada caso?

El Generador de modelos incluye plantillas para el análisis de opiniones, la clasificación de problemas, la predicción de precios y escenarios personalizados. Estas plantillas se pueden usar como punto de partida para un escenario de ML.NET concreto.

#### <a name="sentiment-analysis-binary-classification"></a>Análisis de opinión (clasificación binaria)

El análisis de opiniones se puede usar para predecir una opinión positiva o negativa de los comentarios del cliente. Es un ejemplo de la tarea de clasificación binaria.

La clasificación binaria se usa para clasificar los datos en dos clases (sí o no; correcto o incorrecto; verdadero o falso; positivo o negativo). Se puede usar para responder a preguntas como:

- ¿Es este correo electrónico no deseado? (detección de spam)
- ¿Qué candidatos pueden ser aptos para la pertenencia? (filtrado de solicitudes)
- ¿Qué cuentas podrían no pagar sus facturas puntualmente? (mitigación de riesgos)
- ¿Es esta transacción de tarjeta de crédito fraudulenta? (detección de fraudes)

Si el escenario requiere clasificación en dos categorías, puede usar esta plantilla con un conjunto de datos propio.
 
#### <a name="issue-classification-multiclass-classification"></a>Clasificación de problemas (clasificación multiclase)

La clasificación de problemas se puede usar para clasificar problemas de comentarios de clientes (por ejemplo, en GitHub) mediante el título y la descripción del problema. Es un ejemplo de la tarea de clasificación multiclase.

La clasificación multiclase puede usarse para clasificar los datos en tres o más clases. Se puede usar para responder a preguntas como:

- ¿A qué departamento debo dirigir una incidencia de soporte técnico? (enrutamiento de incidencias de soporte técnico)
- ¿Cuál es la prioridad del problema de un cliente? (clasificación por orden de prioridad de problemas de clientes)
- ¿A qué categoría pertenece un producto? (clasificación de productos)
- ¿Qué tipo de documento? (clasificación de documentos o correo electrónico)

Puede usar la plantilla de clasificación de problemas para el escenario si quiere clasificar los datos en tres o más categorías.

#### <a name="price-prediction-regression"></a>Predicción de precios (regresión)

La predicción de precios puede usarse para predecir los precios de viviendas según la ubicación, el tamaño y otras características del inmueble. Es un ejemplo de la tarea de regresión.

La regresión se usa para predecir números. Se puede usar para responder a preguntas como:

- ¿Por qué precio se va a vender una casa? (predicción de precios)
- ¿Después de cuánto tiempo va a necesitar mantenimiento una pieza mecánica? (mantenimiento predictivo)
- ¿Cuál es el contenido de humedad de este secador? (supervisión de máquinas)
- ¿Cuáles van a ser las ventas totales anuales de esta región? (previsión de ventas)

Puede usar la plantilla de predicción de precios para el escenario si quiere predecir un valor numérico con un conjunto de datos propio.

#### <a name="custom-scenario-choose-your-task"></a>Escenario personalizado (elija la tarea)

El escenario personalizado permite elegir una tarea propia. Elija el escenario que más sentido tenga para el problema.

El escenario personalizado permite elegir una tarea de aprendizaje automático propia. En las plantillas anteriores, la tarea de aprendizaje automático se ha ajustado al escenario: clasificación binaria, clasificación multiclase o regresión. En esta plantilla, puede elegir la tarea de Machine Learning que quiere usar en los datos.

## <a name="data"></a>Datos

Una vez que se ha asignado el escenario a una tarea, el Generador de modelos pide que se proporcione un conjunto de datos. Los datos se usan para entrenar, evaluar y elegir el mejor modelo para el escenario. También se debe elegir el resultado que se quiere predecir.

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

### <a name="data-formats"></a>Formatos de datos

El Generador de modelos coloca las siguientes limitaciones en los datos:

- Los datos deben estar almacenados en un archivo (.csv o .tsv con una fila de encabezado) o en una base de datos de SQL Server.
- Un límite de 1 GB en el conjunto de datos de entrenamiento
- SQL Server tiene un límite de 100 000 filas para entrenamiento
- Los datos de SQL Server se copian desde el servidor en el equipo local antes del entrenamiento

### <a name="example-datasets"></a>Conjuntos de datos de ejemplo

Si aún no tiene datos propios, pruebe uno de estos conjuntos de datos:

|Escenario|Tarea de Machine Learning|Datos|Etiqueta|Características|
|-|-|-|-|-|
|Predicción de precios|regresión|[datos de carreras de taxi](https://github.com/dotnet/machinelearning-samples/blob/master/datasets/taxi-fare-train.csv)|Carrera|Tiempo de viaje, distancia|
|Detección de anomalías|clasificación binaria|[datos de ventas de productos](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)|Ventas de productos|Mes|
|análisis de opiniones|clasificación binaria|[datos de comentarios de sitio web](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_SentimentAnalysis/SentimentAnalysis/Data/wikiDetoxAnnotated40kRows.tsv)|Etiqueta (0 si la opinión es negativa, 1 si es positiva)|Comentario, año|
|Detección de fraudes|clasificación binaria|[datos de tarjetas de crédito](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_CreditCardFraudDetection/CreditCardFraudDetection.Trainer/assets/input/creditcardfraud-dataset.zip)|Clase (1 si es fraudulenta, en caso contrario, 0)|Cantidad, V1-V28 (características anónimas)|
|Clasificación de textos|clasificación multiclase|[datos de problemas de GitHub](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/end-to-end-apps/MulticlassClassification-GitHubLabeler/GitHubLabeler/Data/corefx-issues-train.tsv)|Área|Título, descripción|

## <a name="train"></a>Train

Una vez que se seleccionan el escenario, los datos y la etiqueta, el Generador de modelos entrena el modelo.

### <a name="what-is-training"></a>¿Qué es el entrenamiento?

El entrenamiento es un proceso automático mediante el cual el Generador de modelos enseña al modelo a responder a preguntas del escenario. Una vez entrenado, el modelo puede realizar predicciones con datos de entrada que no ha visto antes. Por ejemplo, si está prediciendo los precios de la vivienda y se pone en el mercado un nuevo inmueble, puede predecir su precio de venta.

Dado que el Generador de modelos usa aprendizaje automático automatizado (AutoML), no requiere ninguna entrada ni ajuste por parte del usuario durante el entrenamiento.

### <a name="how-long-should-i-train-for"></a>¿Durante cuánto tiempo debe entrenarse?

Puede proporcionar un tiempo de entrenamiento. En general, el entrenamiento durante más tiempo da lugar a un modelo más preciso. También se necesita más tiempo de entrenamiento a medida que aumenta el tamaño del conjunto de datos de entrenamiento. En la tabla siguiente se proporcionan algunas directrices de tiempo de entrenamiento para conjuntos de datos de tamaño en aumento.

Tamaño del conjunto de datos  | Tipo de conjunto de datos       | Prom. Tiempo de entrenamiento
------------- | ------------------ | --------------
0 - 10 MB     | Numérico y texto   | 10 s
10 - 100 MB   | Numérico y texto   | 10 min 
100 - 500 MB  | Numérico y texto   | 30 min 
500 - 1 GB    | Numérico y texto   | 60 min 
1 GB o más         | Numérico y texto   | Más de 3 horas 

El tiempo exacto de entrenamiento también depende de:

- el tipo de columnas de que se trate, es decir, texto frente a números
- el tipo de tarea de aprendizaje automático (regresión o clasificación)
- el número de filas que se usan para el entrenamiento
- el número de columnas de características que se usan para el entrenamiento

El Generador de modelos se ha probado a escala con un conjunto de datos de 1 TB, pero la creación de un modelo de alta calidad para ese tamaño de conjunto de datos puede durar hasta cuatro días.

## <a name="evaluate"></a>Evaluate

La evaluación es el proceso de usar el modelo entrenado para realizar predicciones con nuevos datos de prueba y luego medir la calidad de las predicciones.

El Generador de modelos divide los datos de entrenamiento en un conjunto de entrenamiento y un conjunto de prueba. Los datos de entrenamiento (80 %) se usan para entrenar el modelo y los datos de prueba (20 %) se incluyen para evaluar el modelo.  Las métricas usadas para la evaluación dependen de la tarea de Machine Learning. Para obtener más información, vea [Métricas de evaluación de modelos](resources/metrics.md).  

### <a name="sentiment-analysis-binary-classification"></a>Análisis de opinión (clasificación binaria)

La métrica predeterminada para los problemas de clasificación binaria es la **precisión**. La precisión define la proporción de predicciones correctas que realiza el modelo en el conjunto de datos de prueba. **Cuanto más cerca de 100 %, mejor es el modelo**.

Otras métricas notificadas, como AUC (área bajo la curva), que mide la tasa de positivos verdaderos frente a la tasa de falsos positivos, deben ser superiores a 0,50 para que los modelos sean aceptables. 

Otras métricas, como la puntuación F1, pueden usarse para controlar el equilibrio entre precisión (relación de predicciones correctas con respecto al total de predicciones de esa clase) y coincidencia (proporción de predicciones correctas con respecto a los miembros reales totales de esa clase).

### <a name="issue-classification-multiclass-classification"></a>Clasificación de problemas (clasificación multiclase)

La métrica predeterminada para los problemas de clasificación multiclase es la **microprecisión**. **Cuanto más cerca de 100 %, mejor es el modelo**.

En el caso de los problemas donde los datos se clasifican en varias clases, hay dos tipos de precisión:

- Microprecisión: fracción de predicciones correctas en todas las instancias. En el escenario de clasificación de problemas, la microprecisión es la proporción de problemas entrantes que se asignan a la categoría correcta. 
- Macroprecisión: precisión media en el nivel de clase. En el escenario de clasificación de problemas, la precisión se mide para cada categoría y luego se calcula el promedio de precisión de las categorías. En el caso de esta métrica, todas las clases tienen el mismo peso. En los conjuntos de datos perfectamente equilibrados (donde hay un número igual de ejemplos de cada categoría), la microprecisión y la macroprecisión son lo mismo.


### <a name="price-prediction-regression"></a>Predicción de precios (regresión)

La métrica predeterminada para los problemas de regresión es **RSquared**. 1 es el mejor valor posible. Cuanto más se acerca RSquared a 1, mejor es el modelo.

Otras métricas notificadas, como pérdida absoluta, pérdida al cuadrado y pérdida RMS, pueden usarse para comprender el modelo y compararlo con otros modelos de regresión. 

## <a name="improve"></a>Mejora

Si la puntuación de rendimiento del modelo no es tan buena como se quiere que sea, se puede:

* Entrenar durante más tiempo. Con más tiempo, el motor de aprendizaje automático automatizado prueba más algoritmos y configuraciones.

* Agregar más datos. A veces la cantidad de datos no es suficiente para entrenar un modelo de Machine Learning de alta calidad. 

* Equilibrar los datos. En las tareas de clasificación, asegúrese de que el conjunto de entrenamiento esté equilibrado entre las categorías. Por ejemplo, si tiene cuatro clases de 100 ejemplos de entrenamiento y las dos primeras (etiqueta1 y etiqueta2) se usan para 90 registros, pero las otras dos (etiqueta3 y etiqueta4) solo se usan en los 10 registros restantes, la falta de datos equilibrados puede hacer que el modelo se esfuerce por predecir correctamente etiqueta3 o etiqueta4.

## <a name="code"></a>Código

Después de la fase de evaluación, el Generador de modelos genera un archivo de modelo y el código que se puede usar para agregar el modelo a la aplicación. Los modelos de ML.NET se guardan como un archivo zip. El código para cargar y usar el modelo se agrega como un nuevo proyecto a la solución. El Generador de modelos también agrega una aplicación de consola de ejemplo que se puede ejecutar para ver el modelo en acción.

Además, el Generador de modelos produce el código que ha generado el modelo, para que pueda entender los pasos llevados a cabo para generar el modelo. También puede usar el código de entrenamiento del modelo para volver a entrenar el modelo con nuevos datos.

## <a name="whats-next"></a>Pasos adicionales

Pruebe la [predicción de precios o cualquier escenario de regresión](tutorials/predict-prices-with-model-builder.md)
