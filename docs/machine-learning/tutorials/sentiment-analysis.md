---
title: Uso de ML.NET en un escenario de clasificación binaria de análisis de sentimiento
description: Descubra cómo usar ML.NET en un escenario de clasificación binaria para aprender a usar la predicción de sentimientos a fin de tomar las medidas oportunas.
ms.date: 03/07/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: b0d02babd126a62ef9a87b251f525a08376069aa
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2019
ms.locfileid: "57845796"
---
# <a name="tutorial-use-mlnet-in-a-sentiment-analysis-binary-classification-scenario"></a>Tutorial: Uso de ML.NET en un escenario de clasificación binaria de análisis de sentimiento

En este tutorial de ejemplo se muestra cómo utilizar ML.NET para crear un clasificador de sentimientos para predecir una opinión positiva o negativa a través de una aplicación de consola de .NET Core con C# en Visual Studio 2017. En el mundo del aprendizaje automático, este tipo de predicción se denomina clasificación binaria.

> [!NOTE]
> Este tema hace referencia a ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios. Para obtener más información, visite [la introducción de ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Este tutorial y el ejemplo relacionado usan actualmente **ML.NET en su versión 0.11**. Para obtener más información, consulte las notas de la versión en el [repositorio de GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

En este tutorial aprenderá a:
> [!div class="checklist"]
> * Entender el problema
> * Seleccionar el algoritmo de aprendizaje automático adecuado
> * Preparar los datos
> * Transformar los datos
> * Entrenar el modelo
> * Evaluar el modelo
> * Predecir con el modelo entrenado
> * Implementar y predecir con un modelo cargado

## <a name="sentiment-analysis-sample-overview"></a>Información general del ejemplo de análisis de sentimiento

El ejemplo es una aplicación de consola que utiliza ML.NET para entrenar un modelo que clasifica y predice un sentimiento como positivo o negativo. El conjunto de datos de opinión de Yelp proviene de la Universidad de California, Irvine (UCI), y se divide en un conjunto de datos de entrenamiento y un conjunto de datos de prueba. El ejemplo evalúa el modelo con un el conjunto de datos de prueba para analizar la calidad. 

Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).

## <a name="prerequisites"></a>Requisitos previos

* [Visual Studio 2017 15.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.

* [El archivo zip del conjunto de datos UCI Sentiment Labeled Sentences](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip)

## <a name="machine-learning-workflow"></a>Flujo de trabajo del aprendizaje automático

En este tutorial se sigue un flujo de trabajo de aprendizaje automático que permite que el proceso avance de manera ordenada.

Las fases del flujo de trabajo son las siguientes:

1. **Entender el problema**
2. **Preparar los datos**
   * **Cargar los datos**
   * **Extraer características (transformar los datos)**
3. **Compilar y entrenar** 
   * **Entrenar el modelo**
   * **Evaluar el modelo**
4. **Implementar el modelo**
   * **Usar el modelo para la predicción**

### <a name="understand-the-problem"></a>Entender el problema

Primero debe entender el problema, de manera que pueda dividirlo en partes que admitan la compilación y el entrenamiento del problema. La división del problema en partes le permite predecir y evaluar los resultados.

El problema en este tutorial es comprender los sentimientos de los comentarios del sitio web entrantes para tomar las medidas oportunas.

Puede dividir el problema en texto de sentimientos y valor de sentimientos para los datos con los que desea entrenar el modelo, y un valor de sentimiento de predicción que puede evaluar y luego usar de manera operativa.

A continuación, necesita **determinar** el sentimiento, lo que le ayuda con la selección de tareas de aprendizaje automático.

## <a name="select-the-appropriate-machine-learning-algorithm"></a>Seleccionar el algoritmo de aprendizaje automático adecuado

Con este problema, tiene constancia de los siguientes hechos:

Datos de entrenamiento: los comentarios del sitio web pueden ser positivos (1) o negativos (0) (**opinión**).

Prediga el **sentimiento** de un comentario de sitio web nuevo, positivo o negativo, como en los ejemplos siguientes:

* Me encantan los camareros. Molan mucho.
* La sopa de este sitio es la peor.

El algoritmo de aprendizaje automático de clasificación es ideal para este escenario.

### <a name="about-the-classification-algorithm"></a>Acerca del algoritmo de clasificación

La clasificación es un algoritmo de aprendizaje automático que usa datos para **determinar** la categoría, el tipo o la clase de un elemento o fila de datos. Por ejemplo, puede utilizar la clasificación para:

* Identificar un sentimiento como positivo o negativo.
* Clasificar correo electrónico como correo no deseado o correo válido.
* Determinar si la muestra de laboratorio de un paciente es cancerosa.
* Categorizar a los clientes por su propensión a responder a una campaña de ventas.

Los algoritmos de clasificación suelen ser de uno de los tipos siguientes:

* Binario: A o B.
* Multiclase: varias categorías que se pueden predecir mediante el uso de un único modelo.

Dado que los comentarios del sitio web deben clasificarse como positivos o negativos, use el algoritmo de clasificación binaria. 

## <a name="create-a-console-application"></a>Creación de una aplicación de consola

1. Abra Visual Studio 2017. Seleccione **Archivo** > **Nuevo** > **Proyecto** de la barra de menús. En el cuadro de diálogo **Nuevo proyecto**, seleccione el nodo **Visual C#** seguido del nodo **.NET Core**. Después, seleccione la plantilla del proyecto **Aplicación de consola (.NET Core)**. En el cuadro de texto **Nombre**, escriba "SentimentAnalysis" y después haga clic en el botón **Aceptar**.

2. Cree un directorio denominado *Datos* en el proyecto para guardar los archivos del conjunto de datos:

    En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **Nueva carpeta**. Escriba "Datos" y presione Entrar.

3. Instale el **paquete NuGet Microsoft.ML**:

    En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**. Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.ML**, seleccione ese paquete en la lista y seleccione el botón **Instalar**. Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.

### <a name="prepare-your-data"></a>Preparar los datos

1. Descargue el [archivo zip del conjunto de datos UCI Sentiment Labeled Sentences (vea la referencia en la nota siguiente)](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) y descomprímalo.

2. Copie el archivo `yelp_labelled.txt` en el directorio *Datos* que ha creado.

> [!NOTE]
> Los conjuntos de datos que se utilizan en este tutorial provienen de "From Group to Individual Labels using Deep Features", Kotzias et. al,. KDD 2015, and hosted at the UCI Machine Learning Repository - Dua, D. and Karra Taniskidou, E. (2017). UCI Machine Learning Repository [http://archive.ics.uci.edu/ml]. Irvine, CA: University of California, School of Information and Computer Science.

3. En el Explorador de soluciones, haga clic con el botón derecho en el archivo `yelp_labeled.txt` y seleccione **Propiedades**. En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.

### <a name="create-classes-and-define-paths"></a>Crear clases y definir rutas de acceso

Agregue las siguientes instrucciones `using` adicionales a la parte superior del archivo *Program.cs*:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddUsings "Add necessary usings")]

Debe crear dos campos globales para contener la ruta del archivo de conjunto de datos descargado recientemente y la ruta del archivo del modelo guardado:

* `_dataPath` tiene la ruta de acceso al conjunto de datos utilizado para entrenar el modelo.
* `_modelPath` tiene la ruta de acceso donde se guarda el modelo entrenado.

Agregue el código siguiente a la línea justo encima del método `Main` para especificar las rutas de acceso:

[!code-csharp[Declare global variables](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DeclareGlobalVariables "Declare global variables")]

Debe crear algunas clases para los datos de entrada y las predicciones. Agregue una nueva clase a su proyecto:

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.

1. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *SentimentData.cs*. A continuación, seleccione el botón **Agregar**.

    Se abre el archivo *SentimentData.cs* en el editor de código. Agregue la siguiente instrucción `using` a la parte superior de *SentimentData.cs*:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#AddUsings "Add necessary usings")]

Quite la definición de clase existente y agregue el código siguiente, que tiene dos clases `SentimentData` y `SentimentPrediction`, al archivo *SentimentData.cs*:

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#DeclareTypes "Declare data record types")]

La clase de conjunto de datos de entrada, `SentimentData`, tiene un `string` para el comentario (`SentimentText`) y un `bool` (`Sentiment`) que tiene un valor para el sentimiento positivo o negativo. Ambos campos tienen <xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29> atributos adjuntos a ellos. Este atributo describe el orden de cada campo en el archivo de datos.  Además, la propiedad `Sentiment` tiene un <xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A> para designarlo como el campo `Label`. `SentimentPrediction` es la clase usada para la predicción una vez entrenado el modelo. Tiene un valor booleano único (`Sentiment`) y un atributo `PredictedLabel` `ColumnName`. `Label` se usa para crear y entrenar el modelo, y se usa también con el conjunto de datos de prueba dividido para evaluar el modelo. `PredictedLabel` se usa durante la predicción y la evaluación. Para la evaluación, se utiliza una entrada con los datos de entrenamiento, los valores de predicción y el modelo.

Cuando se crea un modelo con ML.NET empieza creando un <xref:Microsoft.ML.MLContext>. `MLContext` es comparable conceptualmente a usar `DbContext` en Entity Framework. El entorno proporciona un contexto para el trabajo de ML que puede usarse para el seguimiento y registro de excepciones.

### <a name="initialize-variables-in-main"></a>Inicializar variables en Main

Cree una variable denominada `mlContext` e inicialícela con una nueva instancia de `MLContext`.  Reemplace la línea `Console.WriteLine("Hello World!")` por el código siguiente en el método `Main`:

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateMLContext "Create the ML Context")]

Agregue lo siguiente como la siguiente línea de código en el método `Main`:

[!code-csharp[CallLoadData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallLoadData)]

El método `LoadData` ejecuta las tareas siguientes:

* Carga los datos.
* Divide el conjunto de datos cargado en conjuntos de datos de entrenamiento y prueba.
* Devuelve los conjuntos de datos divididos en entrenamiento y prueba.

Cree el método `LoadData`, justo después del método `Main`, mediante el código siguiente:

```csharp
public static (IDataView trainSet, IDataView testSet) LoadData(MLContext mlContext)
{

}
```
## <a name="load-the-data"></a>Carga de los datos

Puesto que el tipo de modelo de datos `SentimentData` que ha creado anteriormente coincide con el esquema del conjunto de datos, puede combinar la inicialización, la asignación y la carga del conjunto de datos en una línea de código con el encapsulador `MLContext.Data.LoadFromTextFile` para el [método LoadFromTextFile](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29). Devuelve <xref:Microsoft.Data.DataView.IDataView>. 

 Como la entrada y salida de `Transforms`, `DataView` es el tipo de canalización de datos fundamentales, comparable con `IEnumerable` para `LINQ`.

En ML.NET, los datos son similares a una vista SQL. Se evalúan lentamente, se esquematizan y son heterogéneos. El objeto es la primera parte de la canalización y carga los datos. Para este tutorial, carga un conjunto de datos con comentarios y opiniones tóxicas o no tóxicas correspondiente. Esto se usa para crear el modelo y entrenarlo.

 Agregue el código siguiente a la primera línea del método `LoadData`:

[!code-csharp[LoadData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#LoadData "loading dataset")]

### <a name="split-the-dataset-for-model-training-and-testing"></a>División del conjunto de datos para el entrenamiento y la prueba del modelo

A continuación, se necesita un conjunto de datos de entrenamiento para entrenar el modelo y un conjunto de datos de prueba para evaluar el modelo. Use `MLContext.BinaryClassification.TrainTestSplit` que encapsula <xref:Microsoft.ML.StaticPipe.TrainingStaticExtensions.TrainTestSplit%2A> para dividir el conjunto de datos cargado en conjuntos de datos de entrenamiento y prueba y los devuelve dentro de <xref:Microsoft.ML.TrainCatalogBase.TrainTestData>. Puede especificar la fracción de los datos para la prueba establecida con el parámetro `testFraction`. El valor predeterminado es 10 %, pero use 20 % en este caso para usar más datos para la evaluación.  

Para dividir los datos cargados en los conjuntos de datos necesarios, agregue el código siguiente como la siguiente línea en el método `LoadData`:

[!code-csharp[SplitData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#SplitData "Split the Data")]

Devuelva el `splitDataView` al final del método `LoadData`:

[!code-csharp[ReturnSplitData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#ReturnSplitData)]

## <a name="build-and-train-the-model"></a>Creación y entrenamiento del modelo

Agregue la siguiente llamada al método `BuildAndTrainModel` como siguiente línea de código del método `Main`:

[!code-csharp[CallBuildAndTrainModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallBuildAndTrainModel)]

El método `BuildAndTrainModel` ejecuta las tareas siguientes:

* Extrae y transforma los datos.
* Entrena el modelo.
* Predice sentimientos en función de datos de prueba.
* Devuelve el modelo.

Cree el método `BuildAndTrainModel`, justo después del método `Main`, mediante el código siguiente:

```csharp
public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView splitTrainSet)
{

}
```

Tenga en cuenta que se pasan dos parámetros al método Train: `MLContext` para el contexto (`mlContext`) y `IDataView` para el conjunto de datos de entrenamiento (`splitTrainSet`). 

## <a name="extract-and-transform-the-data"></a>Extraer y transformar los datos

El procesamiento previo y la limpieza de datos son tareas importantes que se producen antes de que un conjunto de datos se utilice de forma eficaz para el aprendizaje automático. Los datos sin procesar contienen a menudo ruido y son poco de fiar; además, es posible que les falten valores. El uso de datos sin estas tareas de modelado puede producir resultados engañosos.

Las canalizaciones de transformación de ML.NET crean un conjunto personalizado de transformaciones que se aplican a los datos antes del entrenamiento o la prueba. El propósito principal de las transformaciones es la [caracterización](../resources/glossary.md#feature-engineering) de datos. Los algoritmos de aprendizaje automático comprenden los datos [caracterizados](../resources/glossary.md#feature), por lo que el paso siguiente es transformar nuestro datos textuales en un formato que reconozcan nuestros algoritmos de ML. Ese formato es un [vector numérico](../resources/glossary.md#numerical-feature-vector).

Después, llame a `mlContext.Transforms.Text.FeaturizeText` que caracteriza la columna de texto (`SentimentText`) en un vector numérico llamado `Features` utilizado por el algoritmo de aprendizaje automático. Se trata de una llamada de contenedor que devuelve <xref:Microsoft.ML.Data.EstimatorChain%601> que eficazmente será una canalización. Asigne un nombre a `pipeline`, ya que luego anexará el entrenador a `EstimatorChain`. Agregue esto como la siguiente línea de código:

[!code-csharp[FeaturizeText](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#FeaturizeText "Featurize the text")]

>[!WARNING]
> En la versión 0.10 de ML.NET se ha cambiado el orden de los parámetros de transformación. Esto no generará un error hasta que se ejecute la aplicación y se compile el modelo. Use los nombres de parámetro para las transformaciones, como se muestra en el fragmento de código anterior.

Este es el paso de preprocesamiento o caracterización. El uso de componentes adicionales disponibles en ML.NET permite conseguir mejores resultados con el modelo.

## <a name="choose-a-learning-algorithm"></a>Elegir un algoritmo de aprendizaje

Para agregar el entrenador, llame al método contenedor `mlContext.BinaryClassification.Trainers.FastTree` que devuelve un objeto <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer>. Esto es un aprendiz de árbol de decisión que usará en esta canalización. `FastTreeBinaryClassificationTrainer` se anexa a `pipeline` y acepta `SentimentText` (`Features`) caracterizado y los parámetros de entrada `Label` para aprender de los datos históricos.

Agregue el código siguiente al método `BuildAndTrainModel`:

[!code-csharp[FastTreeBinaryClassificationTrainer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddTrainer "Add a FastTreeBinaryClassificationTrainer")]

## <a name="train-the-model"></a>Entrenar el modelo

Se entrena el modelo, <xref:Microsoft.ML.Data.TransformerChain%601>, en función del conjunto de datos que se haya cargado y transformado. Una vez que se ha definido el estimador, entrenará el modelo mediante el método <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> proporcionando al mismo tiempo los datos de entrenamiento ya cargados. Esto devuelve un modelo que se usa para las predicciones. `pipeline.Fit()` entrena la canalización y devuelve `Transformer` según la `DataView` que se pasa. El experimento no se ejecuta hasta que se ejecute el método `.Fit()`.

Agregue el código siguiente al método `BuildAndTrainModel`:

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#TrainModel "Train the model")]

### <a name="save-and-return-the-model-trained-to-use-for-evaluation"></a>Guardar y devolver el modelo entrenado para su uso para la evaluación

En este punto, tiene un modelo de tipo <xref:Microsoft.ML.Data.TransformerChain%601> que se puede integrar en cualquiera de las aplicaciones de .NET nuevas o existentes. Devuelva el modelo al final del método `BuildAndTrainModel`.

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#ReturnModel "Return the model")]

## <a name="evaluate-the-model"></a>Evaluar el modelo

Ahora que ha creado y entrenado el modelo, debe evaluarlo con otro conjunto de datos para el control de calidad y la validación. En el método `Evaluate`, el modelo creado en `BuildAndTrainModel` se pasa para ser evaluado. Cree el método `Evaluate`, justo después de `BuildAndTrainModel`, como en el código siguiente:

```csharp
public static void Evaluate(MLContext mlContext, ITransformer model, IDataView splitTestSet)
{

}
```

El método `Evaluate` ejecuta las tareas siguientes:

* Carga el conjunto de datos de prueba.
* Crea el evaluador de clasificación binaria.
* Evalúa el modelo y crea las métricas.
* Muestra las métricas.

Agregue una llamada al método nuevo desde el método `Main`, justo debajo de la llamada al método `Train`, utilizando el código siguiente:

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallEvaluate "Call the Evaluate method")]

A continuación, deberá usará el parámetro `model` de aprendizaje automático (un transformador) y el parámetro `splitTestSet` para introducir las características y devolver las predicciones. Agregue el código siguiente al método `Evaluate` como la siguiente línea:

[!code-csharp[PredictWithTransformer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#TransformData "Predict using the Transformer")]

El método `mlContext.BinaryClassification.Evaluate` calcula las métricas de calidad para `PredictionModel` mediante el conjunto de datos especificado. Devuelve un objeto <xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics> que contiene las métricas totales calculadas por evaluadores de clasificación binaria. Para mostrar estos elementos a fin de determinar la calidad del modelo, debe obtener primero las métricas. Agregue el siguiente código como la siguiente línea en el método `Evaluate`:

[!code-csharp[ComputeMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Evaluate "Compute Metrics")]

### <a name="displaying-the-metrics-for-model-validation"></a>Mostrar las métricas para la validación del modelo

Utilice el código siguiente para mostrar las métricas, compartir los resultados y, a continuación, trabajar con ellos:

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DisplayMetrics "Display selected metrics")]

Para guardar el modelo en un archivo .zip antes de devolverlo, agregue el siguiente código para llamar al método `SaveModelAsFile` como la línea siguiente en `Evaluate`:

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallSaveModel "Save the model")]

## <a name="save-the-model-as-azip-file"></a>Almacenamiento del modelo como un archivo .zip

Cree el método `SaveModelAsFile`, justo después del método `Evaluate`, mediante el código siguiente:

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

El método `SaveModelAsFile` ejecuta las tareas siguientes:

* Guarda el modelo como un archivo .zip.

A continuación, cree un método para guardar el modelo para que se pueda volver a usar y consumir en otras aplicaciones. `ITransformer` tiene un método <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> que toma el campo global `_modelPath` y <xref:System.IO.Stream>. Para guardar esto como un archivo ZIP, creará `FileStream` inmediatamente antes de llamar al método `SaveTo`. Agregue el código siguiente al método `SaveModelAsFile` como la siguiente línea:

[!code-csharp[SaveToMethod](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#SaveModel "Add the SaveTo Method")]

## <a name="deploy-and-predict-with-a-loaded-model"></a>Implementar y predecir con un modelo cargado

También podría mostrar dónde se escribió el archivo mediante la escritura de un mensaje de consola con `_modelPath`, utilizando el código siguiente:

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="predict-the-test-data-outcome-with-the-saved-model"></a>Predicción de los resultados de datos de prueba con el modelo guardado

Cree el método `UseModelWithSingleItem`, justo después del método `Evaluate`, mediante el código siguiente:

```csharp
private static void UseModelWithSingleItem(MLContext mlContext, ITransformer model)
{

}
```

El método `UseModelWithSingleItem` ejecuta las tareas siguientes:

* Crea un único comentario de datos de prueba.
* Predice sentimientos en función de datos de prueba.
* Combina datos de prueba y predicciones para la generación de informes.
* Muestra los resultados de la predicción.

Agregue una llamada al método nuevo desde el método `Main`, justo debajo de la llamada al método `Evaluate`, utilizando el código siguiente:

[!code-csharp[CallUseModelWithSingleItem](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallUseModelWithSingleItem "Call the UseModelWithSingleItem method")]

Mientras `model` es `transformer` que opera en muchas filas de datos, un escenario muy común de producción es necesario para las predicciones con los ejemplos individuales. <xref:Microsoft.ML.PredictionEngine%602> es un contenedor que se devuelve del método `CreatePredictionEngine`. Vamos a agregar el código siguiente para crear `PredictionEngine` como la primera línea en el método `Predict`:

[!code-csharp[CreatePredictionEngine](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreatePredictionEngine1 "Create the PredictionEngine")]
  
Agregue un comentario para probar la predicción del modelo entrenado en el método `Predict` mediante la creación de una instancia de `SentimentData`:

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateTestIssue1 "Create test data for single prediction")]

 Puede usar eso para predecir la opinión positiva o negativa de una única instancia de los datos de comentario. Para obtener una predicción, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> en los datos. Tenga en cuenta que los datos de entrada son una cadena y el modelo incluye la caracterización. La canalización está sincronizada durante el entrenamiento y la predicción. No fue necesario escribir el código de preprocesamiento o caracterización específicamente para las predicciones, y la misma API se encarga de las predicciones por lotes y puntuales.

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Predict "Create a prediction of sentiment")]

### <a name="use-the-model-prediction"></a>Uso del modelo: predicción

Muestre `SentimentText` y la predicción del sentimiento correspondiente para compartir los resultados y actuar en consecuencia. Esto se denomina puesta en marcha, y se utilizan los datos devueltos como parte de las directivas operativas. Cree una visualización para los resultados mediante el código <xref:System.Console.WriteLine?displayProperty=nameWithType> siguiente:

[!code-csharp[OutputPrediction](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#OutputPrediction "Display prediction output")]

## <a name="deploy-and-predict-with-a-loaded-model"></a>Implementar y predecir con un modelo cargado

Cree el método `UseLoadedModelWithBatchItems`, justo antes del método `SaveModelAsFile`, mediante el código siguiente:

```csharp
public static void UseLoadedModelWithBatchItems(MLContext mlContext)
{

}
```

El método `UseLoadedModelWithBatchItems` ejecuta las tareas siguientes:

* Crea datos de prueba por lotes.
* Predice sentimientos en función de datos de prueba.
* Combina datos de prueba y predicciones para la generación de informes.
* Muestra los resultados de la predicción.

Agregue una llamada al método nuevo desde el método `Main`, justo debajo de la llamada al método `UseModelWithSingleItem`, utilizando el código siguiente:

[!code-csharp[CallPredictModelLoaded](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallUseLoadedModelWithBatchItems "Call the CallUseLoadedModelWithBatchItems method")]

Agregue algunos comentarios para probar las predicciones del modelo entrenado en el método `UseLoadedModelWithBatchItems`:

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateTestIssues "Create test data for predictions")]

Cargue el modelo

[!code-csharp[LoadTheModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#LoadModel "Load the model")]

Ahora que tiene un modelo, puede utilizarlo para predecir la opinión tóxica o no tóxica de los datos de comentarios con el método <xref:Microsoft.ML.ITransformer.Transform%2A>. Para obtener una predicción, use `Predict` en los nuevos datos. Tenga en cuenta que los datos de entrada son una cadena y el modelo incluye la caracterización. La canalización está sincronizada durante el entrenamiento y la predicción. No fue necesario escribir el código de preprocesamiento o caracterización específicamente para las predicciones, y la misma API se encarga de las predicciones por lotes y puntuales. Agregue el código siguiente al método `UseLoadedModelWithBatchItems` para las predicciones:

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Prediction "Create predictions of sentiments")]

### <a name="use-the-loaded-model-for-prediction"></a>Uso del modelo cargado para la predicción

Muestre `SentimentText` y la predicción del sentimiento correspondiente para compartir los resultados y actuar en consecuencia. Esto se denomina puesta en marcha, y se utilizan los datos devueltos como parte de las directivas operativas. Cree un encabezado para los resultados con el código <xref:System.Console.WriteLine?displayProperty=nameWithType> siguiente:

[!code-csharp[OutputHeaders](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddInfoMessage "Display prediction outputs")]

Antes de mostrar los resultados de la predicción, combine el sentimiento con la predicción para ver el comentario original con su sentimiento de predicción. El siguiente código utiliza el método <xref:System.Linq.Enumerable.Zip%2A> para que esto ocurra, así que agregue el código siguiente a continuación:

[!code-csharp[BuildTuples](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#BuildSentimentPredictionPairs "Build the pairs of sentiment data and predictions")]

Ahora que ha combinado `SentimentText` y `Sentiment` en una clase, puede mostrar los resultados utilizando el método <xref:System.Console.WriteLine?displayProperty=nameWithType>:

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DisplayResults "Display the predictions")]

Debido a que los nombres de elementos de tupla inferidos son una característica nueva en C# 7.1 y la versión de lenguaje predeterminada del proyecto es C# 7.0, debe cambiar la versión del lenguaje a C# 7.1 o superior.
Para ello, haga clic con el botón derecho en el nodo del proyecto en el **Explorador de soluciones** y seleccione **Propiedades**. Seleccione la pestaña **Compilar** y, después, el botón **Opciones avanzadas**. En la lista desplegable, seleccione **C# 7.1** (o una versión superior). Seleccione el botón **Aceptar**.

## <a name="results"></a>Resultados

Los resultados deberían ser similares a los indicados a continuación. A medida que la canalización procesa, muestra mensajes. Puede ver las advertencias o mensajes de procesamiento. Se han quitado de los siguientes resultados para mayor claridad.

```console
Model quality metrics evaluation
--------------------------------
Accuracy: 79.14%
Auc: 86.27%
F1Score: 80.60%

=============== End of model evaluation ===============
The model is saved to C:\Tutorials\SentimentAnalysis\bin\Debug\netcoreapp2.1\Data\Model.zip

=============== Prediction Test of model with a single sample and test dataset ===============

Sentiment: This was a very bad steak | Prediction: Negative | Probability: 0.4641322
=============== End of Predictions ===============


=============== Prediction Test of loaded model with a multiple samples ===============

Sentiment: This was a horrible meal | Prediction: Negative | Probability: 0.1391833
Sentiment: I love this spaghetti. | Prediction: Positive | Probability: 0.9819039
=============== End of predictions ===============

=============== End of process ===============
Press any key to continue . . .

```

¡Enhorabuena! Ya ha creado correctamente un modelo de aprendizaje automático para clasificar y predecir los sentimientos de los mensajes. 

La creación de modelos correctos es un proceso iterativo. Este modelo tiene una calidad inicial más baja, ya que el tutorial utiliza pequeños conjuntos de datos para proporcionar un entrenamiento rápido del modelo. Si no está satisfecho con la calidad del modelo, puede intentar mejorarlo proporcionando conjuntos de datos de entrenamiento más grandes o eligiendo algoritmos de entrenamiento distintos con diferentes hiperparámetros para cada algoritmo.

Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).

## <a name="next-steps"></a>Pasos siguientes

En este tutorial ha aprendido a:
> [!div class="checklist"]
> * Entender el problema
> * Seleccionar el algoritmo de aprendizaje automático adecuado
> * Preparar los datos
> * Transformar los datos
> * Entrenar el modelo
> * Evaluar el modelo
> * Predecir con el modelo entrenado
> * Implementar y predecir con un modelo cargado

Siga con el siguiente tutorial para obtener más información
> [!div class="nextstepaction"]
> [Clasificación de problemas](github-issue-classification.md)
