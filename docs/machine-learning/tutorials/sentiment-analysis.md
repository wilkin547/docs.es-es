---
title: Uso de ML.NET en un escenario de clasificación binaria de análisis de sentimiento
description: Descubra cómo usar ML.NET en un escenario de clasificación binaria para aprender a usar la predicción de sentimientos a fin de tomar las medidas oportunas.
ms.date: 06/04/2018
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 727718c00b9270e2bbbe0840879b3a7e164a02d8
ms.sourcegitcommit: ed7b4b9b77d35e94a35a2634e8c874f46603fb2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2018
ms.locfileid: "36948623"
---
# <a name="tutorial-use-mlnet-in-a-sentiment-analysis-binary-classification-scenario"></a>Tutorial: Uso de ML.NET en un escenario de clasificación binaria de análisis de sentimiento

> [!NOTE]
> Este tema hace referencia a ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios. Para obtener más información, visite [la introducción de ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

En este tutorial de ejemplo se muestra cómo utilizar ML.NET para crear un clasificador de sentimientos a través de una aplicación de consola de .NET Core con C# en Visual Studio 2017.

En este tutorial aprenderá a:
> [!div class="checklist"]
> * Entender el problema
> * Seleccionar la tarea de aprendizaje automático adecuada
> * Preparar los datos
> * Crear la canalización de aprendizaje
> * Cargar un clasificador
> * Entrenar el modelo
> * Evaluar el modelo con otro conjunto de datos
> * Predecir los resultados de datos de prueba con el modelo

## <a name="sentiment-analysis-sample-overview"></a>Información general del ejemplo de análisis de sentimiento

El ejemplo es una aplicación de consola que utiliza ML.NET para entrenar un modelo que clasifica y predice un sentimiento como positivo o negativo. También se evalúa el modelo con un segundo conjunto de datos para realizar el análisis de calidad. Los conjuntos de datos de sentimientos proceden del proyecto WikiDetox.

## <a name="prerequisites"></a>Requisitos previos

* [Visual Studio 2017 15.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.

* El [archivo separado por tabulaciones de datos de la línea detox de Wikipedia (wikiPedia-detox-250-line-data.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv).
* El [archivo separado por tabulaciones de pruebas de la línea detox de Wikipedia (wikipedia-detox-250-line-test.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv).

## <a name="machine-learning-workflow"></a>Flujo de trabajo del aprendizaje automático

En este tutorial se sigue un flujo de trabajo de aprendizaje automático que permite que el proceso avance de manera ordenada.

Las fases del flujo de trabajo son las siguientes:

1. **Entender el problema**
2. **Ingerir los datos**
3. **Procesar previamente los datos y aplicar ingeniería a las características**
4. **Entrenar y predecir el modelo**
5. **Evaluar el modelo**
6. **Poner en marcha el modelo**

### <a name="understand-the-problem"></a>Entender el problema

Primero debe entender el problema, de manera que pueda dividirlo en partes que admitan la compilación y el entrenamiento del problema. La división del problema en partes le permite predecir y evaluar los resultados.

El problema en este tutorial es comprender los sentimientos de los comentarios del sitio web entrantes para tomar las medidas oportunas.

Puede dividir el problema en texto de sentimientos y valor de sentimientos para los datos con los que desea entrenar el modelo, y un valor de sentimiento de predicción que puede evaluar y luego usar de manera operativa.

A continuación, necesita **determinar** el sentimiento, lo que le ayuda con la selección de tareas de aprendizaje automático.

## <a name="select-the-appropriate-machine-learning-task"></a>Seleccionar la tarea de aprendizaje automático adecuada

Con este problema, tiene constancia de los siguientes hechos:

Datos de entrenamiento: los comentarios del sitio web pueden ser positivos o negativos (**sentimiento**).
Prediga el **sentimiento** de un comentario de sitio web nuevo, positivo o negativo, como en los ejemplos siguientes:

* Evite agregar elementos sin sentido a Wikipedia.
* Él es el mejor, y el artículo debe reflejarlo.

La tarea de aprendizaje automático de clasificación es ideal para este escenario.

### <a name="about-the-classification-task"></a>Acerca de la tarea de clasificación

La clasificación es una tarea de aprendizaje automático que usa datos para **determinar** la categoría, el tipo o la clase de un elemento o fila de datos. Por ejemplo, puede utilizar la clasificación para:

* Identificar un sentimiento como positivo o negativo.
* Clasificar correo electrónico como correo no deseado o correo válido.
* Determinar si la muestra de laboratorio de un paciente es cancerosa.
* Categorizar a los clientes por su propensión a responder a una campaña de ventas.

Las tareas de clasificación son a menudo de uno de los siguientes tipos:

* Binario: A o B.
* Multiclase: varias categorías que se pueden predecir mediante el uso de un único modelo.

## <a name="create-a-console-application"></a>Creación de una aplicación de consola

1. Abra Visual Studio 2017. Seleccione **Archivo** > **Nuevo** > **Proyecto** de la barra de menús. En el cuadro de diálogo *Nuevo proyecto**, seleccione el nodo **Visual C#** seguido del nodo **.NET Core**. Después, seleccione la plantilla del proyecto **Aplicación de consola (.NET Core)**. En el cuadro de texto **Nombre**, escriba "SentimentAnalysis" y después haga clic en el botón **Aceptar**.

2. Cree un directorio denominado *Datos* en el proyecto para guardar los archivos del conjunto de datos:

    En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **Nueva carpeta**. Escriba "Datos" y presione Entrar.

3. Instale el **paquete NuGet Microsoft.ML**:

    En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**. Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.ML**, seleccione ese paquete en la lista y seleccione el botón **Instalar**. Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.

### <a name="prepare-your-data"></a>Preparar los datos

1. Descargue los conjuntos de datos [WikiPedia detox-250-line-data.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv) y [wikipedia-detox-250-line-test.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv) y guárdelos en la carpeta *Datos* creada previamente. El primer conjunto de datos entrena el modelo de aprendizaje automático y el segundo puede usarse para evaluar su grado de precisión.

2. En el Explorador de soluciones, haga clic con el botón secundario en cada uno de los archivos \*.tsv y seleccione **Propiedades**. En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** a **Siempre**.

### <a name="create-classes-and-define-paths"></a>Crear clases y definir rutas de acceso

Agregue las siguientes instrucciones `using` adicionales a la parte superior del archivo *Program.cs*:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#1 "Add necessary usings")]

Debe crear tres campos globales para contener las rutas de acceso a los archivos descargados recientemente:

* `_dataPath` tiene la ruta de acceso al conjunto de datos utilizado para entrenar el modelo.
* `_testDataPath` tiene la ruta de acceso al conjunto de datos utilizado para evaluar el modelo.
* `_modelPath` tiene la ruta de acceso donde se guarda el modelo entrenado.

Agregue el código siguiente a la línea justo encima del método `Main` para especificar las rutas de acceso:

[!code-csharp[Declare file variables](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#2 "Declare variables to store data files")]

Debe crear algunas clases para los datos de entrada y las predicciones. Agregue una nueva clase a su proyecto:

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.

1. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *SentimentData.cs*. A continuación, seleccione el botón **Agregar**.

    Se abre el archivo *SentimentData.cs* en el editor de código. Agregue la siguiente instrucción `using` a la parte superior de *SentimentData.cs*:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#1 "Add necessary usings")]

Quite la definición de clase existente y agregue el código siguiente, que tiene dos clases `SentimentData` y `SentimentPrediction`, al archivo *SentimentData.cs*:

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#2 "Declare data record types")]

`SentimentData` es la clase de conjunto de datos de entrada y tiene un `float` (`Sentiment`) que tiene un valor para el sentimiento positivo o negativo, y una cadena para el comentario (`SentimentText`). Ambos campos tienen `Column` atributos adjuntos a ellos. Este atributo describe el orden de cada campo en el archivo de datos, y que es el campo `Label`. `SentimentPrediction` es la clase usada para la predicción una vez entrenado el modelo. Tiene un valor booleano único (`Sentiment`) y un atributo `PredictedLabel` `ColumnName`. `Label` se usa para crear y entrenar el modelo, y se usa también con un segundo conjunto de datos para evaluar el modelo. `PredictedLabel` se usa durante la predicción y la evaluación. Para la evaluación, se utiliza una entrada con los datos de entrenamiento, los valores de predicción y el modelo.

En el archivo *Program.cs*, cambie la firma del método `Main` reemplazando `void` por `async Task`, como en el ejemplo siguiente:

```csharp
static async Task Main(string[] args) 
{

}
```

Se agrega `async` a `Main` con un tipo de valor devuelto <xref:System.Threading.Tasks.Task> porque más adelante se guarda el modelo en un archivo ZIP, y el programa debe esperar hasta que finalice la tarea externa.

> [!NOTE]
> Un método *async main* permite usar `await` en el método `Main`. Para obtener más información, consulte el tema [async main](../../../docs/csharp/programming-guide/main-and-command-args/index.md) en la guía de programación de C#.

Reemplace la línea `Console.WriteLine("Hello World!")` por el código siguiente en el método `Main`:

[!code-csharp[Train](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#3 "Train your model")]

El método `Train` ejecuta las tareas siguientes:

* Carga o ingiere los datos.
* Preprocesa y caracteriza los datos.
* Entrena el modelo.
* Predice sentimientos en función de datos de prueba.

Cree el método `Train`, justo después del método `Main`, mediante el código siguiente:

```csharp
public static async Task<PredictionModel<SentimentData, SentimentPrediction>> Train()
{

}
```

## <a name="ingest-the-data"></a>Ingerir los datos

Inicialice una nueva instancia de <xref:Microsoft.ML.LearningPipeline> que incluirá la carga de datos, el procesamiento y la caracterización de los datos y el modelo. Agregue el código siguiente a la primera línea del método `Train`:

[!code-csharp[LearningPipeline](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#5 "Create a learning pipeline")]

El objeto <xref:Microsoft.ML.Data.TextLoader> es la primera parte de la canalización y carga los datos del archivo de entrenamiento.

[!code-csharp[TextLoader](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#6 "Add a text loader to the pipeline")]

## <a name="data-preprocess-and-feature-engineering"></a>Procesar previamente los datos y aplicar ingeniería a las características

El procesamiento previo y la limpieza de datos son tareas importantes que se producen antes de que un conjunto de datos se utilice de forma eficaz para el aprendizaje automático. Los datos sin procesar contienen a menudo ruido y son poco de fiar; además, es posible que les falten valores. El uso de datos sin estas tareas de modelado puede producir resultados engañosos. Las canalizaciones de transformación de ML.NET le permiten crear un conjunto personalizado de transformaciones que se aplican a los datos antes del entrenamiento o la prueba. El propósito principal de las transformaciones es la caracterización de datos. La ventaja de una canalización de transformación es que, una vez definida, puede guardarla para aplicarla a los datos de prueba.

Aplique un <xref:Microsoft.ML.Transforms.TextFeaturizer> para convertir la columna `SentimentText` en un [vector numérico](../resources/glossary.md#numerical-feature-vector) llamado `Features` utilizado por el algoritmo de aprendizaje automático. Este es el paso de preprocesamiento o caracterización. El uso de componentes adicionales disponibles en ML.NET permite conseguir mejores resultados con el modelo. Agregue `TextFeaturizer` a la canalización como la siguiente línea de código:

[!code-csharp[TextFeaturizer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#7 "Add a TextFeaturizer to the pipeline")]

## <a name="choose-a-learning-algorithm"></a>Elegir un algoritmo de aprendizaje

El objeto <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier> es un aprendiz de árbol de decisión que usará en esta canalización. De manera similar al paso de la caracterización, probar diferentes aprendices disponibles en ML.NET y cambiar sus parámetros genera resultados diferentes. Para la optimización, puede establecer [hiperparámetros](../resources/glossary.md#hyperparameter) como <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.NumTrees>, <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.NumLeaves> y <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.MinDocumentsInLeafs>. Estos hiperparámetros se establecen antes de que algo afecte al modelo y son específicos del modelo. Se utilizan para ajustar el árbol de decisiones para el rendimiento, por lo que los valores más grandes pueden afectar negativamente al rendimiento.

Agregue el código siguiente al método `Train`:

[!code-csharp[BinaryClassifier](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#8 "Add a fast binary tree classifier")]

## <a name="train-the-model"></a>Entrenar el modelo

Se entrena el modelo, <xref:Microsoft.ML.PredictionModel%602>, en función del conjunto de datos que se haya cargado y transformado. `pipeline.Train<SentimentData, SentimentPrediction>()` entrena la canalización (carga los datos, entrena al caracterizador y el aprendiz). El experimento no se ejecuta hasta que esto suceda.

Agregue el código siguiente al método `Train`:

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#9 "Train the model")]

### <a name="save-and-return-the-model-trained-to-use-for-evaluation"></a>Guardar y devolver el modelo entrenado para su uso para la evaluación

En este punto, tiene un modelo que se puede integrar en cualquiera de las aplicaciones de .NET nuevas o existentes. Para guardar el modelo en un archivo .zip antes de devolverlo, agregue este código a la línea siguiente en `Train`:

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#10 "Save the model")]

Devuelva el modelo al final del método `Train`.

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#11 "Return the model")]

## <a name="evaluate-the-model"></a>Evaluar el modelo

Ahora que ha creado y entrenado el modelo, debe evaluarlo con otro conjunto de datos para el control de calidad y la validación. En el método `Evaluate`, el modelo creado en `Train` se pasa para ser evaluado. Cree el método `Evaluate`, justo después de `Train`, como en el código siguiente:

```csharp
public static void Evaluate(PredictionModel<SentimentData, SentimentPrediction> model)
{

}
```

El método `Evaluate` ejecuta las tareas siguientes:

* Carga el conjunto de datos de prueba.
* Crea el evaluador binario.
* Evalúa el modelo y crea métricas.
* Muestra las métricas.

Agregue una llamada al método nuevo desde el método `Main`, justo debajo de la llamada al método `Train`, utilizando el código siguiente:

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#12 "Call the Evaluate method")]

La clase <xref:Microsoft.ML.Data.TextLoader> carga el nuevo conjunto de datos de prueba con el mismo esquema. Puede evaluar el modelo utilizando este conjunto de datos como una comprobación de calidad. Agregue el código siguiente al método `Evaluate`:

[!code-csharp[LoadText](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#13 "Load the test dataset")]

El objeto <xref:Microsoft.ML.Models.BinaryClassificationEvaluator> calcula las métricas de calidad para `PredictionModel` con el conjunto de datos especificado. Para ver esas métricas, agregue el evaluador como la siguiente línea en el método `Evaluate`, con el código siguiente:

[!code-csharp[BinaryEvaluator](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#14 "Create the binary evaluator")]

<xref:Microsoft.ML.Models.BinaryClassificationMetrics> contiene las métricas totales calculadas por evaluadores de clasificación binaria. Para mostrar estos elementos a fin de determinar la calidad del modelo, debe obtener primero las métricas. Agregue el código siguiente:

[!code-csharp[CreateMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#15 "Evaluate the model and create metrics")]

### <a name="displaying-the-metrics-for-model-validation"></a>Mostrar las métricas para la validación del modelo

Utilice el código siguiente para mostrar las métricas, compartir los resultados y, a continuación, trabajar con ellos:

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#16 "Display selected metrics")]

## <a name="predict-the-test-data-outcomes-with-the-model"></a>Predecir los resultados de datos de prueba con el modelo

Cree el método `Predict`, justo después del método `Evaluate`, mediante el código siguiente:

```csharp
public static void Predict(PredictionModel<SentimentData, SentimentPrediction> model)
{

}
```

El método `Predict` ejecuta las tareas siguientes:

* Crea datos de prueba.
* Predice sentimientos en función de datos de prueba.
* Combina datos de prueba y predicciones para la generación de informes.
* Muestra los resultados de la predicción.

Agregue una llamada al método nuevo desde el método `Main`, justo debajo de la llamada al método `Evaluate`, utilizando el código siguiente:

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#17 "Call the Predict method")]

Agregue algunos comentarios para probar las predicciones del modelo entrenado en el método `Predict`:

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#18 "Create test data for predictions")]

Ahora que tiene un modelo, puede utilizarlo para predecir el sentimiento positivo o negativo de los datos de comentarios con el método <xref:Microsoft.ML.PredictionModel.Predict%2A?displayProperty=nameWithType>. Para obtener una predicción, use `Predict` en los nuevos datos. Tenga en cuenta que los datos de entrada son una cadena y el modelo incluye la caracterización. La canalización está sincronizada durante el entrenamiento y la predicción. No fue necesario escribir el código de preprocesamiento o caracterización específicamente para las predicciones, y la misma API se encarga de las predicciones por lotes y puntuales.

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#19 "Create predictions of sentiments")]

### <a name="model-operationalization-prediction"></a>Puesta en marcha del modelo: predicción

Muestre `SentimentText` y la predicción del sentimiento correspondiente para compartir los resultados y actuar en consecuencia. Esto se denomina puesta en marcha, y se utilizan los datos devueltos como parte de las directivas operativas. Cree un encabezado para los resultados con el código <xref:System.Console.WriteLine?displayProperty=nameWithType> siguiente:

[!code-csharp[OutputHeaders](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#20 "Display prediction outputs")]

Antes de mostrar los resultados de la predicción, combine el sentimiento con la predicción para ver el comentario original con su sentimiento de predicción. El siguiente código utiliza el método <xref:System.Linq.Enumerable.Zip%2A> para que esto ocurra, así que agregue el código siguiente a continuación:

[!code-csharp[BuildTuples](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#21 "Build the pairs of sentiment data and predictions")]

Ahora que ha combinado `SentimentText` y `Sentiment` en una clase, puede mostrar los resultados utilizando el método <xref:System.Console.WriteLine?displayProperty=nameWithType>:

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#22 "Display the predictions")]

Debido a que los nombres de elementos de tupla inferidos son una característica nueva en C# 7.1 y la versión de lenguaje predeterminada del proyecto es C# 7.0, debe cambiar la versión del lenguaje a C# 7.1 o superior.
Para ello, haga clic con el botón derecho en el nodo del proyecto en el **Explorador de soluciones** y seleccione **Propiedades**. Seleccione la pestaña **Compilar** y, después, el botón **Opciones avanzadas**. En la lista desplegable, seleccione **C# 7.1** (o una versión superior). Seleccione el botón **Aceptar**.

## <a name="results"></a>Resultados

Los resultados deberían ser similares a los indicados a continuación. A medida que la canalización procesa, muestra mensajes. Puede ver las advertencias o mensajes de procesamiento. Se han quitado de los siguientes resultados para mayor claridad.

```

PredictionModel quality metrics evaluation
------------------------------------------
Accuracy: 66.67%
Auc: 94.44%
F1Score: 75.00%

Sentiment Predictions
---------------------
Sentiment: Please refrain from adding nonsense to Wikipedia. | Prediction: Negative
Sentiment: He is the best, and the article should say that. | Prediction: Positive

```

¡Enhorabuena! Ya ha creado correctamente un modelo de aprendizaje automático para clasificar y predecir los sentimientos de los mensajes. Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).

## <a name="next-steps"></a>Pasos siguientes

En este tutorial ha aprendido a:
> [!div class="checklist"]
> * Entender el problema
> * Seleccionar la tarea de aprendizaje automático adecuada
> * Preparar los datos
> * Crear la canalización de aprendizaje
> * Cargar un clasificador
> * Entrenar el modelo
> * Evaluar el modelo con otro conjunto de datos
> * Predecir los resultados de datos de prueba con el modelo

Siga con el siguiente tutorial para obtener más información
> [!div class="nextstepaction"]
> [Predictor de tarifa de taxi](taxi-fare.md)
