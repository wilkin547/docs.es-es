---
title: 'Tutorial: Análisis de comentarios del sitio web: clasificación binaria'
description: En este tutorial se muestra cómo crear una aplicación de consola de .NET Core que clasifica las opiniones de los comentarios del sitio web y toma las medidas oportunas. El clasificador binario de opiniones usa C# en Visual Studio.
ms.date: 06/30/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 3dbcb3cbd4eea2d01638bedc7123f570ff9d64d1
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104874595"
---
# <a name="tutorial-analyze-sentiment-of-website-comments-with-binary-classification-in-mlnet"></a>Tutorial: Análisis de opinión de los comentarios del sitio web con clasificación binaria de ML.NET

En este tutorial se muestra cómo crear una aplicación de consola de .NET Core que clasifica las opiniones de los comentarios del sitio web y toma las medidas oportunas. El clasificador binario de opiniones utiliza C# en Visual Studio 2017.

En este tutorial aprenderá a:
> [!div class="checklist"]
>
> - Creación de una aplicación de consola
> - Preparar los datos
> - Carga de los datos
> - Creación y entrenamiento del modelo
> - Evaluar el modelo
> - Uso del modelo para realizar una predicción
> - Ver los resultados

Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/main/machine-learning/tutorials/SentimentAnalysis).

## <a name="prerequisites"></a>Requisitos previos

- [Visual Studio 2017, versión 15.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada

- [Conjunto de datos de frases con etiqueta de opinión de UCI](http://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) (archivo ZIP)

## <a name="create-a-console-application"></a>Creación de una aplicación de consola

1. Cree una **aplicación de consola de .NET Core** denominada "SentimentAnalysis".

2. Cree un directorio denominado *Datos* en el proyecto para guardar los archivos de conjunto de datos.

3. Instale el **paquete NuGet Microsoft.ML**:

    [!INCLUDE [mlnet-current-nuget-version](../../../includes/mlnet-current-nuget-version.md)]

    En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**. Elija "nuget.org" como origen del paquete y luego seleccione la pestaña **Examinar**. Busque **Microsoft.ML**, seleccione el paquete que desee y luego, el botón **Instalar**. Acepte los términos de licencia del paquete que elija para continuar con la instalación.

## <a name="prepare-your-data"></a>Preparar los datos

> [!NOTE]
> Los conjuntos de datos de este tutorial proceden de "From Group to Individual Labels using Deep Features", Kotzias et. al,. KDD 2015, and hosted at the UCI Machine Learning Repository - Dua, D. and Karra Taniskidou, E. (2017). UCI Machine Learning Repository [http://archive.ics.uci.edu/ml ]. Irvine, CA: University of California, School of Information and Computer Science.

1. Descargue el [archivo ZIP de conjunto de datos de frases con etiqueta de opinión de UCI](http://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) y descomprímalo.

2. Copie el archivo `yelp_labelled.txt` en el directorio *Datos* que ha creado.

3. En el Explorador de soluciones, haga clic con el botón derecho en el archivo `yelp_labeled.txt` y seleccione **Propiedades**. En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.

### <a name="create-classes-and-define-paths"></a>Crear clases y definir rutas de acceso

1. Agregue las siguientes instrucciones `using` adicionales a la parte superior del archivo *Program.cs*:

    [!code-csharp[AddUsings](./snippets/sentiment-analysis/csharp/Program.cs#AddUsings "Add necessary usings")]

1. Agregue el código siguiente a la línea por encima del método `Main` para crear un campo que incluya la ruta de acceso del archivo del conjunto de datos descargado recientemente:

    [!code-csharp[Declare global variables](./snippets/sentiment-analysis/csharp/Program.cs#DeclareGlobalVariables "Declare global variables")]

1. Luego, cree clases para los datos de entrada y las predicciones. Agregue una nueva clase a su proyecto:

    - En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.

    - En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *SentimentData.cs*. A continuación, seleccione el botón **Agregar**.

1. Se abre el archivo *SentimentData.cs* en el editor de código. Agregue la siguiente instrucción `using` a la parte superior de *SentimentData.cs*:

    [!code-csharp[AddUsings](./snippets/sentiment-analysis/csharp/SentimentData.cs#AddUsings "Add necessary usings")]

1. Quite la definición de clase existente y agregue el código siguiente, que tiene dos clases `SentimentData` y `SentimentPrediction`, al archivo *SentimentData.cs*:

    [!code-csharp[DeclareTypes](./snippets/sentiment-analysis/csharp/SentimentData.cs#DeclareTypes "Declare data record types")]

### <a name="how-the-data-was-prepared"></a>¿Cómo se han preparado los datos?

La clase de conjunto de datos de entrada, `SentimentData`, tiene un `string` para comentarios del usuario (`SentimentText`) y un valor `bool` (`Sentiment`) de 1 (positivo) o de 0 (negativo) para las opiniones. Ambos campos tienen atributos [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) adjuntos a ellos, que describe el orden de archivo de datos de cada campo.  Además, la propiedad `Sentiment` tiene un atributo [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A) que lo designa como campo `Label`. El archivo de ejemplo siguiente no tiene una fila de encabezado y se ve así:

|SentimentText                         |Opinión (etiqueta) |
|--------------------------------------|----------|
|La camarera era algo lenta en el servicio.|    0     |
|La corteza no es buena.                    |    0     |
|¡Ah! Me encantó el lugar.              |    1     |
|El servicio fue muy rápido.              |    1     |

`SentimentPrediction` es la clase de predicción que se utiliza tras el entrenamiento del modelo. Hereda de `SentimentData` para que la entrada `SentimentText` pueda mostrarse junto con la predicción de salida. El booleano `Prediction` es el valor que predice el modelo cuando se proporciona con la nueva entrada `SentimentText`.

La clase de salida `SentimentPrediction` contiene otras dos propiedades calculadas por el modelo: `Score`, el resultado sin formato calculado por el modelo y `Probability`, la puntuación calibrada de la probabilidad de que el texto tenga un sentimiento positivo.

Para este tutorial, la propiedad más importante es `Prediction`.

## <a name="load-the-data"></a>Carga de los datos

Los datos de ML.NET se representan como una [clase IDataView](xref:Microsoft.ML.IDataView). `IDataView` es una manera flexible y eficiente de describir datos tabulares (numéricos y de texto). Los datos se pueden cargar desde un archivo de texto o en tiempo real (por ejemplo, archivos de registro o base de datos SQL) en un objeto `IDataView`.

La [clase MLContext](xref:Microsoft.ML.MLContext) es un punto de partida para todas las operaciones de ML.NET. La inicialización de `mlContext` crea un entorno de ML.NET que se puede compartir entre los objetos del flujo de trabajo de creación de modelos. Como concepto, se parece a `DBContext` en Entity Framework.

Prepare la aplicación y luego cargue datos:

1. Reemplace la línea `Console.WriteLine("Hello World!")` del método `Main` por el siguiente código para declarar e inicializar la variable mlContext:

    [!code-csharp[CreateMLContext](./snippets/sentiment-analysis/csharp/Program.cs#CreateMLContext "Create the ML Context")]

2. Agregue lo siguiente como la siguiente línea de código en el método `Main()`:

    [!code-csharp[CallLoadData](./snippets/sentiment-analysis/csharp/Program.cs#CallLoadData)]

3. Cree el método `LoadData()`, justo después del método `Main()`, mediante el código siguiente:

    ```csharp
    public static TrainTestData LoadData(MLContext mlContext)
    {

    }
    ```

    El método `LoadData()` ejecuta las tareas siguientes:

    - Carga los datos.
    - Divide el conjunto de datos cargado en conjuntos de datos de entrenamiento y prueba.
    - Devuelve los conjuntos de datos divididos en entrenamiento y prueba.

4. Agregue el código siguiente a la primera línea del método `LoadData()`:

    [!code-csharp[LoadData](./snippets/sentiment-analysis/csharp/Program.cs#LoadData "loading dataset")]

    El método [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) define el esquema de datos y lee en el archivo. Toma las variables de ruta de acceso de datos y devuelve `IDataView`.

### <a name="split-the-dataset-for-model-training-and-testing"></a>División del conjunto de datos para el entrenamiento y la prueba del modelo

Al preparar un modelo, se utiliza parte del conjunto de datos para entrenarlo y parte del conjunto de datos para probar la precisión del modelo.

1. Para dividir los datos cargados en los conjuntos de datos necesarios, agregue el código siguiente como la siguiente línea en el método `LoadData()`:

    [!code-csharp[SplitData](./snippets/sentiment-analysis/csharp/Program.cs#SplitData "Split the Data")]

    El código anterior usa el método [TrainTestSplit()](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit%2A) para dividir el conjunto de datos cargado en conjuntos de datos de entrenamiento y de prueba, que devuelve en la clase <xref:Microsoft.ML.DataOperationsCatalog.TrainTestData>. Especifique el porcentaje de datos del conjunto de prueba con el parámetro `testFraction`. El valor predeterminado es 10 %; en este caso se usa 20 % para evaluar más datos.

2. Devuelva el `splitDataView` al final del método `LoadData()`:

    [!code-csharp[ReturnSplitData](./snippets/sentiment-analysis/csharp/Program.cs#ReturnSplitData)]

## <a name="build-and-train-the-model"></a>Creación y entrenamiento del modelo

1. Agregue la siguiente llamada al método `BuildAndTrainModel` como siguiente línea de código del método `Main()`:

    [!code-csharp[CallBuildAndTrainModel](./snippets/sentiment-analysis/csharp/Program.cs#CallBuildAndTrainModel)]

    El método `BuildAndTrainModel()` ejecuta las tareas siguientes:

    - Extrae y transforma los datos.
    - Entrena el modelo.
    - Predice sentimientos en función de datos de prueba.
    - Devuelve el modelo.

2. Cree el método `BuildAndTrainModel()`, justo después del método `Main()`, mediante el código siguiente:

    ```csharp
    public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView splitTrainSet)
    {

    }
    ```

### <a name="extract-and-transform-the-data"></a>Extraer y transformar los datos

1. Llame a `FeaturizeText` como siguiente línea de código:

    [!code-csharp[FeaturizeText](./snippets/sentiment-analysis/csharp/Program.cs#FeaturizeText "Featurize the text")]

    El método `FeaturizeText()` del código anterior convierte la columna de texto (`SentimentText`) en una columna de tipo de clave numérico `Features` que el algoritmo de aprendizaje automático utiliza y agrega como nueva columna de conjunto de datos:

    |SentimentText                         |Opinión |Características              |
    |--------------------------------------|----------|----------------------|
    |La camarera era algo lenta en el servicio.|    0     |[0,76, 0,65, 0,44, …] |
    |La corteza no es buena.                    |    0     |[0,98, 0,43, 0,54, …] |
    |¡Ah! Me encantó el lugar.              |    1     |[0,35, 0,73, 0,46, …] |
    |El servicio fue muy rápido.              |    1     |[0,39, 0, 0,75, …]    |

### <a name="add-a-learning-algorithm"></a>Incorporación de un algoritmo de aprendizaje

Esta aplicación usa un algoritmo de clasificación que clasifica elementos o filas de datos. La aplicación clasifica los comentarios del sitio web como positivos o negativos, así que use la tarea de clasificación binaria.

Anexe la tarea de aprendizaje automático a las definiciones de transformación de datos agregando lo siguiente como siguiente línea de código en `BuildAndTrainModel()`:

[!code-csharp[SdcaLogisticRegressionBinaryTrainer](./snippets/sentiment-analysis/csharp/Program.cs#AddTrainer "Add a SdcaLogisticRegressionBinaryTrainer")]

[SdcaLogisticRegressionBinaryTrainer](xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer) es el algoritmo de entrenamiento de clasificación. Se anexa a `estimator` y acepta `SentimentText` (`Features`) caracterizado y los parámetros de entrada `Label` para aprender de los datos históricos.

### <a name="train-the-model"></a>Entrenar el modelo

Ajuste el modelo a los datos `splitTrainSet` y devuelva el modelo entrenado. Para ello, agregue lo que se indica a continuación como la siguiente línea de código en el método `BuildAndTrainModel()`:

[!code-csharp[TrainModel](./snippets/sentiment-analysis/csharp/Program.cs#TrainModel "Train the model")]

El método [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) entrena el modelo al transformar el conjunto de datos y aplicar el aprendizaje.

### <a name="return-the-model-trained-to-use-for-evaluation"></a>Devolución del modelo entrenado para su uso para la evaluación

 Devuelva el modelo al final del método `BuildAndTrainModel()`:

[!code-csharp[ReturnModel](./snippets/sentiment-analysis/csharp/Program.cs#ReturnModel "Return the model")]

## <a name="evaluate-the-model"></a>Evaluar el modelo

Cuando el modelo haya sido entrenado, use los datos de prueba para validar su rendimiento.

1. Cree el método `Evaluate()`, justo después de `BuildAndTrainModel()`, con el código siguiente:

    ```csharp
    public static void Evaluate(MLContext mlContext, ITransformer model, IDataView splitTestSet)
    {

    }
    ```

    El método `Evaluate()` ejecuta las tareas siguientes:

    - Carga el conjunto de datos de prueba.
    - Crea el evaluador BinaryClassification.
    - Evalúa el modelo y crea las métricas.
    - Muestra las métricas.

2. Agregue una llamada al método nuevo desde el método `Main()`, justo debajo de la llamada al método `BuildAndTrainModel()`, utilizando el código siguiente:

    [!code-csharp[CallEvaluate](./snippets/sentiment-analysis/csharp/Program.cs#CallEvaluate "Call the Evaluate method")]

3. Transforme los datos `splitTestSet` mediante la adición del código siguiente a `Evaluate()`:

    [!code-csharp[PredictWithTransformer](./snippets/sentiment-analysis/csharp/Program.cs#TransformData "Predict using the Transformer")]

    El código anterior usa el método [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) para realizar predicciones para varias filas de entrada de un conjunto de datos de prueba especificado.

4. Para evaluar el modelo, agregue lo que se indica a continuación como la siguiente línea de código en el método `Evaluate()`:

    [!code-csharp[ComputeMetrics](./snippets/sentiment-analysis/csharp/Program.cs#Evaluate "Compute Metrics")]

Cuando haya establecido el conjunto de predicción (`predictions`), el método [Evaluate()](xref:Microsoft.ML.BinaryClassificationCatalog.Evaluate%2A) evalúa el modelo, que compara los valores de predicción con el valor real de `Labels` en el conjunto de datos de prueba y devuelve un objeto [CalibratedBinaryClassificationMetrics](xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics) sobre cómo se ejecuta el modelo.

### <a name="displaying-the-metrics-for-model-validation"></a>Mostrar las métricas para la validación del modelo

Use el siguiente código para mostrar las métricas:

[!code-csharp[DisplayMetrics](./snippets/sentiment-analysis/csharp/Program.cs#DisplayMetrics "Display selected metrics")]

- La métrica `Accuracy` obtiene la precisión de un modelo, que corresponde a la proporción de predicciones correctas en el conjunto de pruebas.

- La métrica `AreaUnderRocCurve` indica el nivel de confianza del modelo en clasificar correctamente las clases positivas y negativas. Se desea que `AreaUnderRocCurve` esté lo más cerca de uno posible.

- La métrica `F1Score` obtiene la puntuación F1 del modelo, que es una medida del equilibrio entre [precisión](../resources/glossary.md#precision) y [recuperación](../resources/glossary.md#recall).  Se desea que `F1Score` esté lo más cerca de uno posible.

### <a name="predict-the-test-data-outcome"></a>Predicción del resultado de datos de prueba

1. Cree el método `UseModelWithSingleItem()`, justo después del método `Evaluate()`, mediante el código siguiente:

    ```csharp
    private static void UseModelWithSingleItem(MLContext mlContext, ITransformer model)
    {

    }
    ```

    El método `UseModelWithSingleItem()` ejecuta las tareas siguientes:

    - Crea un único comentario de datos de prueba.
    - Predice sentimientos en función de datos de prueba.
    - Combina datos de prueba y predicciones para la generación de informes.
    - Muestra los resultados de la predicción.

2. Agregue una llamada al método nuevo desde el método `Main()`, justo debajo de la llamada al método `Evaluate()`, utilizando el código siguiente:

    [!code-csharp[CallUseModelWithSingleItem](./snippets/sentiment-analysis/csharp/Program.cs#CallUseModelWithSingleItem "Call the UseModelWithSingleItem method")]

3. Agregue el código siguiente como primera línea en el método `UseModelWithSingleItem()`:

    [!code-csharp[CreatePredictionEngine](./snippets/sentiment-analysis/csharp/Program.cs#CreatePredictionEngine1 "Create the PredictionEngine")]

    [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) es una API de conveniencia, que le permite realizar una predicción en una única instancia de datos. [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) no es seguro para subprocesos. Es aceptable usarlo en entornos de un solo subproceso o prototipo. Para mejorar el rendimiento y la seguridad para subprocesos en entornos de producción, use el servicio `PredictionEnginePool`, que crea un [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) de objetos de [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) para su uso en toda la aplicación. Consulte esta guía sobre cómo [usar `PredictionEnginePool` en una API web de ASP.NET Core](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).

    > [!NOTE]
    > La extensión del servicio `PredictionEnginePool` está actualmente en versión preliminar.

4. Agregue un comentario para probar la predicción del modelo entrenado en el método `UseModelWithSingleItem()` mediante la creación de una instancia de `SentimentData`:

    [!code-csharp[PredictionData](./snippets/sentiment-analysis/csharp/Program.cs#CreateTestIssue1 "Create test data for single prediction")]

5. Pase los datos del comentario de prueba a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) agregando lo siguiente como siguientes líneas de código al método `UseModelWithSingleItem()`:

    [!code-csharp[Predict](./snippets/sentiment-analysis/csharp/Program.cs#Predict "Create a prediction of sentiment")]

    La función [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) realiza una predicción sobre una sola fila de datos.

6. Muestre `SentimentText` y la predicción de opiniones correspondiente con el código siguiente:

    [!code-csharp[OutputPrediction](./snippets/sentiment-analysis/csharp/Program.cs#OutputPrediction "Display prediction output")]

## <a name="use-the-model-for-prediction"></a>Uso del modelo de predicción

### <a name="deploy-and-predict-batch-items"></a>Implementación y predicción de elementos por lotes

1. Cree el método `UseModelWithBatchItems()`, justo después del método `UseModelWithSingleItem()`, mediante el código siguiente:

    ```csharp
    public static void UseModelWithBatchItems(MLContext mlContext, ITransformer model)
    {

    }
    ```

    El método `UseModelWithBatchItems()` ejecuta las tareas siguientes:

    - Crea datos de prueba por lotes.
    - Predice sentimientos en función de datos de prueba.
    - Combina datos de prueba y predicciones para la generación de informes.
    - Muestra los resultados de la predicción.

2. Agregue una llamada al método nuevo desde el método `Main`, justo debajo de la llamada al método `UseModelWithSingleItem()`, utilizando el código siguiente:

    [!code-csharp[CallPredictModelBatchItems](./snippets/sentiment-analysis/csharp/Program.cs#CallUseModelWithBatchItems "Call the CallUseModelWithBatchItems method")]

3. Agregue algunos comentarios para probar las predicciones del modelo entrenado en el método `UseModelWithBatchItems()`:

    [!code-csharp[PredictionData](./snippets/sentiment-analysis/csharp/Program.cs#CreateTestIssues "Create test data for predictions")]

### <a name="predict-comment-sentiment"></a>Predicción de opiniones de comentarios

Use el modelo para predecir la opinión de datos de comentario con el método [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A):

[!code-csharp[Predict](./snippets/sentiment-analysis/csharp/Program.cs#Prediction "Create predictions of sentiments")]

### <a name="combine-and-display-the-predictions"></a>Combinación y presentación de las predicciones

Cree un encabezado para las predicciones con el código siguiente:

[!code-csharp[OutputHeaders](./snippets/sentiment-analysis/csharp/Program.cs#AddInfoMessage "Display prediction outputs")]

Dado que `SentimentPrediction` se hereda de `SentimentData`, el método `Transform()` rellena `SentimentText` con los campos de predicción. A medida que el proceso ML.NET se ejecuta, cada componente agrega columnas, y esto facilita la presentación de los resultados:

[!code-csharp[DisplayPredictions](./snippets/sentiment-analysis/csharp/Program.cs#DisplayResults "Display the predictions")]

## <a name="results"></a>Resultados

Los resultados deberían ser similares a los indicados a continuación. Durante el procesamiento, se muestran mensajes. Puede ver las advertencias o mensajes de procesamiento. Se han quitado de los siguientes resultados para mayor claridad.

```console
Model quality metrics evaluation
--------------------------------
Accuracy: 83.96%
Auc: 90.51%
F1Score: 84.04%

=============== End of model evaluation ===============

=============== Prediction Test of model with a single sample and test dataset ===============

Sentiment: This was a very bad steak | Prediction: Negative | Probability: 0.1027377
=============== End of Predictions ===============

=============== Prediction Test of loaded model with a multiple samples ===============

Sentiment: This was a horrible meal | Prediction: Negative | Probability: 0.1369192
Sentiment: I love this spaghetti. | Prediction: Positive | Probability: 0.9960636
=============== End of predictions ===============

=============== End of process ===============
Press any key to continue . . .

```

¡Enhorabuena! Ya ha creado correctamente un modelo de aprendizaje automático para clasificar y predecir los sentimientos de los mensajes.

La creación de modelos correctos es un proceso iterativo. Este modelo tiene una calidad inicial más baja, ya que el tutorial utiliza pequeños conjuntos de datos para proporcionar un entrenamiento rápido del modelo. Si no está satisfecho con la calidad del modelo, puede intentar mejorarlo proporcionando conjuntos de datos de entrenamiento más grandes o eligiendo distintos algoritmos de entrenamiento con distintos [hiperparámetros](../resources/glossary.md#hyperparameter) para cada algoritmo.

Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/main/machine-learning/tutorials/SentimentAnalysis).

## <a name="next-steps"></a>Pasos siguientes

En este tutorial ha aprendido a:
> [!div class="checklist"]
>
> - Creación de una aplicación de consola
> - Preparar los datos
> - Carga de los datos
> - Creación y entrenamiento del modelo
> - Evaluar el modelo
> - Uso del modelo para realizar una predicción
> - Ver los resultados

Siga con el siguiente tutorial para obtener más información
> [!div class="nextstepaction"]
> [Clasificación de problemas](github-issue-classification.md)
