---
title: Uso de ML.NET en un escenario de clasificación binaria de análisis de sentimiento
description: Descubra cómo usar ML.NET en un escenario de clasificación binaria para aprender a usar la predicción de sentimientos a fin de tomar las medidas oportunas.
ms.date: 12/20/2018
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: c6ef4da7f429b92591c90daa3fb06f367d8a578a
ms.sourcegitcommit: 3b9b7ae6771712337d40374d2fef6b25b0d53df6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/04/2019
ms.locfileid: "54030170"
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
> * Predecir una única instancia del resultado de datos de prueba con el modelo
> * Predecir los resultados de datos de prueba con un modelo cargado

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
2. **Preparar los datos**
   * **Cargar los datos**
   * **Extraer características (transformar los datos)**
3. **Compilar y entrenar** 
   * **Entrenar el modelo**
   * **Evaluar el modelo**
4. **Run**
   * **Consumo del modelo**

### <a name="understand-the-problem"></a>Entender el problema

Primero debe entender el problema, de manera que pueda dividirlo en partes que admitan la compilación y el entrenamiento del problema. La división del problema en partes le permite predecir y evaluar los resultados.

El problema en este tutorial es comprender los sentimientos de los comentarios del sitio web entrantes para tomar las medidas oportunas.

Puede dividir el problema en texto de sentimientos y valor de sentimientos para los datos con los que desea entrenar el modelo, y un valor de sentimiento de predicción que puede evaluar y luego usar de manera operativa.

A continuación, necesita **determinar** el sentimiento, lo que le ayuda con la selección de tareas de aprendizaje automático.

## <a name="select-the-appropriate-machine-learning-task"></a>Seleccionar la tarea de aprendizaje automático adecuada

Con este problema, tiene constancia de los siguientes hechos:

Datos de entrenamiento: los comentarios del sitio web pueden ser tóxicos (1) o no tóxicos (0) (**opinión**).
Prediga la **opinión** de un comentario de sitio web nuevo, ya sea tóxico o no tóxico, como en los ejemplos siguientes:

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

1. Abra Visual Studio 2017. Seleccione **Archivo** > **Nuevo** > **Proyecto** de la barra de menús. En el cuadro de diálogo **Nuevo proyecto**, seleccione el nodo **Visual C#** seguido del nodo **.NET Core**. Después, seleccione la plantilla del proyecto **Aplicación de consola (.NET Core)**. En el cuadro de texto **Nombre**, escriba "SentimentAnalysis" y después haga clic en el botón **Aceptar**.

2. Cree un directorio denominado *Datos* en el proyecto para guardar los archivos del conjunto de datos:

    En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **Nueva carpeta**. Escriba "Datos" y presione Entrar.

3. Instale el **paquete NuGet Microsoft.ML**:

    En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**. Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.ML**, seleccione ese paquete en la lista y seleccione el botón **Instalar**. Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.

### <a name="prepare-your-data"></a>Preparar los datos

1. Descargue los conjuntos de datos [WikiPedia detox-250-line-data.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv) y [wikipedia-detox-250-line-test.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv) y guárdelos en la carpeta *Datos* creada previamente. El primer conjunto de datos entrena el modelo de aprendizaje automático y el segundo puede usarse para evaluar su grado de precisión.

2. En el Explorador de soluciones, haga clic con el botón secundario en cada uno de los archivos \*.tsv y seleccione **Propiedades**. En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.

### <a name="create-classes-and-define-paths"></a>Crear clases y definir rutas de acceso

Agregue las siguientes instrucciones `using` adicionales a la parte superior del archivo *Program.cs*:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#1 "Add necessary usings")]

Debe crear tres campos globales para contener las rutas de acceso a los archivos descargados recientemente y una variable global para `TextLoader`:

* `_trainDataPath` tiene la ruta de acceso al conjunto de datos utilizado para entrenar el modelo.
* `_testDataPath` tiene la ruta de acceso al conjunto de datos utilizado para evaluar el modelo.
* `_modelPath` tiene la ruta de acceso donde se guarda el modelo entrenado.
* `_textLoader` es el <xref:Microsoft.ML.Runtime.Data.TextLoader> utilizado para cargar y transformar los conjuntos de datos.

Agregue el código siguiente a la línea justo encima del método `Main` para especificar esas rutas de acceso y la variable `_textLoader`:

[!code-csharp[Declare global variables](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#2 "Declare global variables")]

Debe crear algunas clases para los datos de entrada y las predicciones. Agregue una nueva clase a su proyecto:

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.

1. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *SentimentData.cs*. A continuación, seleccione el botón **Agregar**.

    Se abre el archivo *SentimentData.cs* en el editor de código. Agregue la siguiente instrucción `using` a la parte superior de *SentimentData.cs*:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#1 "Add necessary usings")]

Quite la definición de clase existente y agregue el código siguiente, que tiene dos clases `SentimentData` y `SentimentPrediction`, al archivo *SentimentData.cs*:

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#2 "Declare data record types")]

`SentimentData` es la clase de conjunto de datos de entrada y tiene un `float` (`Sentiment`) que tiene un valor para el sentimiento positivo o negativo, y una cadena para el comentario (`SentimentText`). Ambos campos tienen `Column` atributos adjuntos a ellos. Este atributo describe el orden de cada campo en el archivo de datos, y que es el campo `Label`. `SentimentPrediction` es la clase usada para la predicción una vez entrenado el modelo. Tiene un valor booleano único (`Sentiment`) y un atributo `PredictedLabel` `ColumnName`. `Label` se usa para crear y entrenar el modelo, y se usa también con un segundo conjunto de datos para evaluar el modelo. `PredictedLabel` se usa durante la predicción y la evaluación. Para la evaluación, se utiliza una entrada con los datos de entrenamiento, los valores de predicción y el modelo.

Cuando se crea un modelo con ML.NET empieza creando un `MLContext`. Esto es comparable conceptualmente a usar `DbContext` en Entity Framework. El entorno proporciona un contexto para el trabajo de ML que puede usarse para el seguimiento y registro de excepciones.

### <a name="initialize-variables-in-main"></a>Inicializar variables en Main

Cree una variable denominada `mlContext` e inicialícela con una nueva instancia de `MLContext`.  Reemplace la línea `Console.WriteLine("Hello World!")` por el código siguiente en el método `Main`:

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#3 "Create the ML Context")]

A continuación, para realizar la configuración para la carga de datos, inicialice la variable global `_textLoader` con el fin de volver a usarla.  Tenga en cuenta que usa una variable `TextReader`. Cuando crea `TextLoader` mediante `TextReader`, se pasa en el contexto necesario y la clase <xref:Microsoft.ML.Runtime.Data.TextLoader.Arguments> que habilita la personalización.

 Especifique el esquema de datos, pasando una matriz de objetos <xref:Microsoft.ML.Runtime.Data.TextLoader.Column> al cargador que contiene todos los nombres de columna y sus tipos. Definió el esquema de datos anteriormente al crear nuestra clase `SentimentData`. Para nuestro esquema, la primera columna (Label) es <xref:System.Boolean> (la opinión) y la segunda columna (SentimentText) es la característica de tipo texto o cadena utilizada para predecir la opinión.
La clase `TextReader` devuelve la variable <xref:Microsoft.ML.Runtime.Data.TextLoader> totalmente inicializada.  

Para inicializar la variable global `_textLoader` con el fin de volver a usarla para los conjuntos de datos necesarios, agregue el código siguiente después de la inicialización de `mlContext`:

[!code-csharp[initTextReader](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#4 "Initialize the TextReader")]

Agregue lo siguiente como la siguiente línea de código en el método `Main`:

[!code-csharp[Train](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#5 "Train your model")]

El método `Train` ejecuta las tareas siguientes:

* Carga los datos.
* Extrae y transforma los datos.
* Entrena el modelo.
* Predice sentimientos en función de datos de prueba.
* Devuelve el modelo.

Cree el método `Train`, justo después del método `Main`, mediante el código siguiente:

```csharp
 public static ITransformer Train(MLContext mlContext, string dataPath)
{

}
```

Tenga en cuenta que se pasan dos parámetros al método Train: `MLContext` para el contexto (`mlContext`) y <xref:System.String> para la ruta de acceso del conjunto de datos (`dataPath`). Va a usar este método varias veces para entrenar y probar.

## <a name="load-the-data"></a>Carga de los datos

Cargará los datos mediante la variable global `_textLoader` con el parámetro `dataPath`. Devuelve <xref:Microsoft.ML.Runtime.Data.IDataView>. Como la entrada y salida de `Transforms`, `DataView` es el tipo de canalización de datos fundamentales, comparable con `IEnumerable` para `LINQ`.

En ML.NET, los datos son similares a una vista SQL. Se evalúan lentamente, se esquematizan y son heterogéneos. El objeto es la primera parte de la canalización y carga los datos. Para este tutorial, carga un conjunto de datos con comentarios y opiniones tóxicas o no tóxicas correspondiente. Esto se usa para crear el modelo y entrenarlo.

 Agregue el código siguiente a la primera línea del método `Train`:

[!code-csharp[LoadTrainData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#6 "loading training dataset")]

## <a name="extract-and-transform-the-data"></a>Extraer y transformar los datos

El procesamiento previo y la limpieza de datos son tareas importantes que se producen antes de que un conjunto de datos se utilice de forma eficaz para el aprendizaje automático. Los datos sin procesar contienen a menudo ruido y son poco de fiar; además, es posible que les falten valores. El uso de datos sin estas tareas de modelado puede producir resultados engañosos.

Las canalizaciones de transformación de ML.NET crean un conjunto personalizado de transformaciones que se aplican a los datos antes del entrenamiento o la prueba. El propósito principal de las transformaciones es la [caracterización](../resources/glossary.md#feature-engineering) de datos. Los algoritmos de aprendizaje automático comprenden los datos [caracterizados](../resources/glossary.md#feature), por lo que el paso siguiente es transformar nuestro datos textuales en un formato que reconozcan nuestros algoritmos de ML. Ese formato es un [vector numérico](../resources/glossary.md#numerical-feature-vector).

Después, llame a `mlContext.Transforms.Text.FeaturizeText` que caracteriza la columna de texto (`SentimentText`) en un vector numérico llamado `Features` utilizado por el algoritmo de aprendizaje automático. Se trata de una llamada de contenedor que devuelve <xref:Microsoft.ML.Runtime.Data.EstimatorChain%601> que eficazmente será una canalización. Asigne un nombre a `pipeline`, ya que luego anexará el entrenador a `EstimatorChain`. Agregue esto como la siguiente línea de código:

[!code-csharp[TextFeaturizingEstimator](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#7 "Add a TextFeaturizingEstimator")]

Este es el paso de preprocesamiento o caracterización. El uso de componentes adicionales disponibles en ML.NET permite conseguir mejores resultados con el modelo.

## <a name="choose-a-learning-algorithm"></a>Elegir un algoritmo de aprendizaje

Para agregar el entrenador, llame al método contenedor `mlContext.Transforms.Text.FeaturizeText` que devuelve un objeto <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer>. Esto es un aprendiz de árbol de decisión que usará en esta canalización. `FastTreeBinaryClassificationTrainer` se anexa a `pipeline` y acepta `SentimentText` (`Features`) caracterizado y los parámetros de entrada `Label` para aprender de los datos históricos.

Agregue el código siguiente al método `Train`:

[!code-csharp[FastTreeBinaryClassificationTrainer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#8 "Add a FastTreeBinaryClassificationTrainer")]

## <a name="train-the-model"></a>Entrenar el modelo

Se entrena el modelo, <xref:Microsoft.ML.Data.TransformerChain%601>, en función del conjunto de datos que se haya cargado y transformado. Una vez que se ha definido el estimador, entrenará el modelo mediante <xref:Microsoft.ML.Runtime.Data.EstimatorChain%601.Fit%2A> proporcionando al mismo tiempo los datos de entrenamiento ya cargados. Esto devuelve un modelo que se usa para las predicciones. `pipeline.Fit()` entrena la canalización y devuelve `Transformer` según la `DataView` que se pasa. El experimento no se ejecuta hasta que esto suceda.

Agregue el código siguiente al método `Train`:

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#9 "Train the model")]

### <a name="save-and-return-the-model-trained-to-use-for-evaluation"></a>Guardar y devolver el modelo entrenado para su uso para la evaluación

En este punto, tiene un modelo de tipo <xref:Microsoft.ML.Data.TransformerChain%601> que se puede integrar en cualquiera de las aplicaciones de .NET nuevas o existentes. Devuelva el modelo al final del método `Train`.

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#10 "Return the model")]

## <a name="evaluate-the-model"></a>Evaluar el modelo

Ahora que ha creado y entrenado el modelo, debe evaluarlo con otro conjunto de datos para el control de calidad y la validación. En el método `Evaluate`, el modelo creado en `Train` se pasa para ser evaluado. Cree el método `Evaluate`, justo después de `Train`, como en el código siguiente:

```csharp
public static void Evaluate(MLContext mlContext, ITransformer model)
{

}
```

El método `Evaluate` ejecuta las tareas siguientes:

* Carga el conjunto de datos de prueba.
* Crea el evaluador binario.
* Evalúa el modelo y crea métricas.
* Muestra las métricas.

Agregue una llamada al método nuevo desde el método `Main`, justo debajo de la llamada al método `Train`, utilizando el código siguiente:

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#11 "Call the Evaluate method")]

Cargará el conjunto de datos de prueba mediante la variable global `_textLoader` inicializada anteriormente con el campo global `_testDataPath`. Puede evaluar el modelo utilizando este conjunto de datos como una comprobación de calidad. Agregue el código siguiente al método `Evaluate`:

[!code-csharp[LoadTestDataset](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#12 "Load the test dataset")]

A continuación, deberá usará el parámetro `model` de aprendizaje automático (un transformador) para introducir las características y devolver las predicciones. Agregue el siguiente código al método `Evaluate` como la siguiente línea:

[!code-csharp[PredictWithTransformer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#13 "Predict using the Transformer")]

El método `BinaryClassificationContext.Evaluate` calcula las métricas de calidad para `PredictionModel` mediante el conjunto de datos especificado. Devuelve un objeto `BinaryClassificationEvaluator.CalibratedResult` que contiene las métricas totales calculadas por evaluadores de clasificación binaria. Para mostrar estos elementos a fin de determinar la calidad del modelo, debe obtener primero las métricas. Agregue el siguiente código como la siguiente línea en el método `Evaluate`:

[!code-csharp[ComputeMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#14 "Compute Metrics")]

### <a name="displaying-the-metrics-for-model-validation"></a>Mostrar las métricas para la validación del modelo

Utilice el código siguiente para mostrar las métricas, compartir los resultados y, a continuación, trabajar con ellos:

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#15 "Display selected metrics")]

Para guardar el modelo en un archivo .zip antes de devolverlo, agregue el siguiente código para llamar al método `SaveModelAsFile` como la línea siguiente en `TrainFinalModel`:

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#23 "Save the model")]

## <a name="save-the-model-as-azip-file"></a>Almacenamiento del modelo como un archivo .zip

Cree el método `SaveModelAsFile`, justo después del método `Evaluate`, mediante el código siguiente:

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

El método `SaveModelAsFile` ejecuta las tareas siguientes:

* Guarda el modelo como un archivo .zip.

A continuación, cree un método para guardar el modelo para que se pueda volver a usar y consumir en otras aplicaciones. `ITransformer` tiene un método <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.Runtime.IHostEnvironment,System.IO.Stream)> que toma el campo global `_modelPath` y <xref:System.IO.Stream>. Para guardar esto como un archivo ZIP, creará `FileStream` inmediatamente antes de llamar al método `SaveTo`. Agregue el siguiente código al método `SaveModelAsFile` como la siguiente línea:

[!code-csharp[SaveToMethod](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#24 "Add the SaveTo Method")]

También podría mostrar dónde se escribió el archivo mediante la escritura de un mensaje de consola con `_modelPath`, utilizando el código siguiente:

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="predict-the-test-data-outcome-with-the-model-and-a-single-comment"></a>Predicción del resultado de los datos de prueba con el modelo y un único comentario

Cree el método `Predict`, justo después del método `Evaluate`, mediante el código siguiente:

```csharp
private static void Predict(MLContext mlContext, ITransformer model)
{

}
```

El método `Predict` ejecuta las tareas siguientes:

* Crea un único comentario de datos de prueba.
* Predice sentimientos en función de datos de prueba.
* Combina datos de prueba y predicciones para la generación de informes.
* Muestra los resultados de la predicción.

Agregue una llamada al método nuevo desde el método `Main`, justo debajo de la llamada al método `Evaluate`, utilizando el código siguiente:

[!code-csharp[CallPredict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#16 "Call the Predict method")]

Mientras `model` es `transformer` que opera en muchas filas de datos, un escenario muy común de producción es necesario para las predicciones con los ejemplos individuales. <xref:Microsoft.ML.Runtime.Data.PredictionFunction%602> es un contenedor que se devuelve del método `MakePredictionFunction`. Vamos a agregar el código siguiente para crear PredictionFunction como la primera línea en el método `Predict`:

[!code-csharp[MakePredictionFunction](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#17 "Create the PredictionFunction")]
  
Agregue un comentario para probar la predicción del modelo entrenado en el método `Predict` mediante la creación de una instancia de `SentimentData`:

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#18 "Create test data for single prediction")]


 Puede usar eso para predecir la opinión tóxica o no tóxica de una única instancia de los datos de comentario. Para obtener una predicción, use <xref:Microsoft.ML.Runtime.Data.PredictionFunction%602.Predict(%600)> en los datos. Tenga en cuenta que los datos de entrada son una cadena y el modelo incluye la caracterización. La canalización está sincronizada durante el entrenamiento y la predicción. No fue necesario escribir el código de preprocesamiento o caracterización específicamente para las predicciones, y la misma API se encarga de las predicciones por lotes y puntuales.

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#19 "Create a prediction of sentiment")]

### <a name="model-operationalization-prediction"></a>Puesta en marcha del modelo: predicción

Muestre `SentimentText` y la predicción del sentimiento correspondiente para compartir los resultados y actuar en consecuencia. Esto se denomina puesta en marcha, y se utilizan los datos devueltos como parte de las directivas operativas. Cree una visualización para los resultados mediante el código <xref:System.Console.WriteLine?displayProperty=nameWithType> siguiente:

[!code-csharp[OutputPrediction](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#20 "Display prediction output")]

## <a name="predict-the-test-data-outcomes-with-the-saved-model"></a>Predicción de los resultados de datos de prueba con el modelo guardado

Cree el método `PredictWithModelLoadedFromFile`, justo antes del método `SaveModelAsFile`, mediante el código siguiente:

```csharp
public static void PredictWithModelLoadedFromFile(MLContext mlContext)
{

}
```

El método `PredictWithModelLoadedFromFile` ejecuta las tareas siguientes:

* Crea datos de prueba por lotes.
* Predice sentimientos en función de datos de prueba.
* Combina datos de prueba y predicciones para la generación de informes.
* Muestra los resultados de la predicción.

Agregue una llamada al método nuevo desde el método `Main`, justo debajo de la llamada al método `Predict`, utilizando el código siguiente:

[!code-csharp[CallPredictModelLoaded](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#25 "Call the PredictWithModelLoadedFromFile method")]

Agregue algunos comentarios para probar las predicciones del modelo entrenado en el método `PredictWithModelLoadedFromFile`:

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#26 "Create test data for predictions")]

Cargue el modelo

[!code-csharp[LoadTheModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#27 "Load the model")]

Ahora que tiene un modelo, puede utilizarlo para predecir la opinión tóxica o no tóxica de los datos de comentarios con el método <xref:Microsoft.ML.Core.Data.ITransformer.Transform(Microsoft.ML.Runtime.Data.IDataView)>. Para obtener una predicción, use `Predict` en los nuevos datos. Tenga en cuenta que los datos de entrada son una cadena y el modelo incluye la caracterización. La canalización está sincronizada durante el entrenamiento y la predicción. No fue necesario escribir el código de preprocesamiento o caracterización específicamente para las predicciones, y la misma API se encarga de las predicciones por lotes y puntuales. Agregue el código siguiente al método `PredictWithModelLoadedFromFile` para las predicciones:

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#28 "Create predictions of sentiments")]

### <a name="model-operationalization-prediction"></a>Puesta en marcha del modelo: predicción

Muestre `SentimentText` y la predicción del sentimiento correspondiente para compartir los resultados y actuar en consecuencia. Esto se denomina puesta en marcha, y se utilizan los datos devueltos como parte de las directivas operativas. Cree un encabezado para los resultados con el código <xref:System.Console.WriteLine?displayProperty=nameWithType> siguiente:

[!code-csharp[OutputHeaders](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#29 "Display prediction outputs")]

Antes de mostrar los resultados de la predicción, combine el sentimiento con la predicción para ver el comentario original con su sentimiento de predicción. El siguiente código utiliza el método <xref:System.Linq.Enumerable.Zip%2A> para que esto ocurra, así que agregue el código siguiente a continuación:

[!code-csharp[BuildTuples](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#30 "Build the pairs of sentiment data and predictions")]

Ahora que ha combinado `SentimentText` y `Sentiment` en una clase, puede mostrar los resultados utilizando el método <xref:System.Console.WriteLine?displayProperty=nameWithType>:

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#31 "Display the predictions")]

Debido a que los nombres de elementos de tupla inferidos son una característica nueva en C# 7.1 y la versión de lenguaje predeterminada del proyecto es C# 7.0, debe cambiar la versión del lenguaje a C# 7.1 o superior.
Para ello, haga clic con el botón derecho en el nodo del proyecto en el **Explorador de soluciones** y seleccione **Propiedades**. Seleccione la pestaña **Compilar** y, después, el botón **Opciones avanzadas**. En la lista desplegable, seleccione **C# 7.1** (o una versión superior). Seleccione el botón **Aceptar**.

## <a name="results"></a>Resultados

Los resultados deberían ser similares a los indicados a continuación. A medida que la canalización procesa, muestra mensajes. Puede ver las advertencias o mensajes de procesamiento. Se han quitado de los siguientes resultados para mayor claridad.

```console
Model quality metrics evaluation
--------------------------------
Accuracy: 94.44%
Auc: 98.77%
F1Score: 94.74%
=============== End of model evaluation ===============

=============== Prediction Test of model with a single sample and test dataset ===============

Sentiment: This is a very rude movie | Prediction: Toxic | Probability: 0.5297049
=============== End of Predictions ===============

=============== New iteration of Model ===============
=============== Create and Train the Model ===============
=============== End of training ===============


The model is saved to: C:\Tutorial\SentimentAnalysis\bin\Debug\netcoreapp2.0\Data\Model.zip

=============== Prediction Test of loaded model with a multiple samples ===============

Sentiment: This is a very rude movie | Prediction: Toxic | Probability: 0.4585565
Sentiment: He is the best, and the article should say that. | Prediction: Not Toxic | Probability: 0.9924279

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
