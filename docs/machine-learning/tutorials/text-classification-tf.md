---
title: 'Tutorial: Análisis de la opinión de reseñas de películas con un modelo de TensorFlow entrenado previamente'
description: En este tutorial se muestra cómo usar un modelo de TensorFlow previamente entrenado para clasificar la opinión en comentarios de sitios Web. El clasificador binario de opiniones es una aplicación de consola de C# desarrollada con Visual Studio.
ms.date: 11/15/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 0e80cdc6bb7dcc62a57466e909451da972c92db8
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75738700"
---
# <a name="tutorial-analyze-sentiment-of-movie-reviews-using-a-pre-trained-tensorflow-model-in-mlnet"></a>Tutorial: Análisis de la opinión de reseñas de películas con un modelo de TensorFlow entrenado previamente en ML.NET

En este tutorial se muestra cómo usar un modelo de TensorFlow previamente entrenado para clasificar la opinión en comentarios de sitios Web. El clasificador binario de opiniones es una aplicación de consola de C# desarrollada con Visual Studio.

El modelo de TensorFlow que se usa en este tutorial se entrenó con reseñas de películas procedentes de la base de datos de IMDB. Cuando haya terminado de desarrollar la aplicación, podrá proporcionar el texto de la reseña de la película y la aplicación le indicará si la reseña tiene una opinión positiva o negativa.

En este tutorial aprenderá a:
> [!div class="checklist"]
>
> * Carga de un modelo de TensorFlow entrenado previamente
> * Transformación del texto de comentario del sitio web en características adecuadas para el modelo
> * Uso del modelo para realizar una predicción

Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TextClassificationTF).

## <a name="prerequisites"></a>Requisitos previos

* [Visual Studio 2017, versión 15.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.

## <a name="setup"></a>Programa de instalación

### <a name="create-the-application"></a>Crear la aplicación

1. Cree una **aplicación de consola de .NET Core** denominada "TextClassificationTF".

2. Cree un directorio denominado *Datos* en el proyecto para guardar los archivos del conjunto de datos.

3. Instale el **paquete NuGet Microsoft.ML**:

    En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**. Elija "nuget.org" como origen del paquete y luego seleccione la pestaña **Examinar**. Busque **Microsoft.ML**, seleccione el paquete que desee y luego, el botón **Instalar**. Acepte los términos de licencia del paquete que elija para continuar con la instalación. Repita estos pasos para **Microsoft.ML.TensorFlow** y **SciSharp.TensorFlow.Redist**.

### <a name="add-the-tensorflow-model-to-the-project"></a>Adición del modelo TensorFlow al proyecto

> [!NOTE]
> El modelo de este tutorial procede del repositorio de GitHub, [dotnet/machinelearning-testdata](https://github.com/dotnet/machinelearning-testdata/tree/master/Microsoft.ML.TensorFlow.TestModels/sentiment_model). El modelo tiene el formato TensorFlow SavedModel.

1. Descargue el [archivo zip sentiment_model](https://github.com/dotnet/samples/blob/master/machine-learning/models/textclassificationtf/sentiment_model.zip?raw=true) y descomprímalo.

    El archivo zip contiene:

    * `saved_model.pb`: el propio modelo de TensorFlow. El modelo toma una matriz de enteros de longitud fija (tamaño 600) de características que representan el texto de una cadena de reseña de IMDB y genera dos probabilidades que suman 1: la probabilidad de que la reseña de entrada tenga una opinión positiva y la probabilidad de que la reseña de entrada tenga una opinión negativa.
    * `imdb_word_index.csv`: una asignación de palabras individuales a un valor entero. La asignación se usa para generar las características de entrada para el modelo de TensorFlow.

2. Copie el contenido del directorio `sentiment_model` más interno en el directorio `sentiment_model` del proyecto *TextClassificationTF*. En este directorio está el modelo y los archivos auxiliares adicionales que se necesitan en este tutorial, tal como se muestra en la imagen siguiente:

   ![contenido del directorio sentiment_model](./media/text-classification-tf/sentiment-model-files.png)

3. En el Explorador de soluciones, haga clic con el botón derecho en cada uno de los archivos del directorio `sentiment_model` y los subdirectorios y seleccione **Propiedades**. En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.

### <a name="add-using-statements-and-global-variables"></a>Adición de instrucciones Using y variables globales

1. Agregue las siguientes instrucciones `using` adicionales a la parte superior del archivo *Program.cs*:

   [!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TextClassificationTF/Program.cs#AddUsings "Add necessary usings")]

1. Cree dos variables globales justo encima del método `Main`para que contengan la ruta de acceso del archivo de modelo guardado y la longitud del vector de características.

   [!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TextClassificationTF/Program.cs#DeclareGlobalVariables "Declare global variables")]

    * `_modelPath` es la ruta de acceso del archivo del modelo entrenado.
    * `FeatureLength` es la longitud de la matriz de características de tipo entero que el modelo espera.

### <a name="model-the-data"></a>Modelado de los datos

Las reseñas de películas son texto de forma libre. La aplicación convierte el texto en el formato de entrada que el modelo espera en varias fases discretas.

La primera consiste en dividir el texto en palabras independientes y usar el archivo de asignación proporcionado para asignar cada palabra a una codificación de enteros. El resultado de esta transformación es una matriz de enteros de longitud variable cuya longitud corresponde al número de palabras de la oración.

|Propiedad.| Valor|Tipo|
|-------------|-----------------------|------|
|ReviewText|Esta película es realmente buena|cadena|
|VariableLengthFeatures|14,22,9,66,78,... |int[]|

El tamaño de la matriz de características de longitud variable se cambia a una longitud fija de 600. Esta es la longitud que espera el modelo de TensorFlow.

|Propiedad.| Valor|Tipo|
|-------------|-----------------------|------|
|ReviewText|Esta película es realmente buena|cadena|
|VariableLengthFeatures|14,22,9,66,78,... |int[]|
|Características|14,22,9,66,78,... |int[600]|

1. Cree una clase para los datos de entrada, después del método `Main`:

    [!code-csharp[MovieReviewClass](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#MovieReviewClass "Declare movie review type")]

    La clase de datos de entrada, `MovieReview`, tiene un objeto `string` para comentarios de usuario (`ReviewText`).

1. Cree una clase para las características de longitud variable, después del método `Main`:

    [!code-csharp[VariableLengthFeatures](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#VariableLengthFeatures "Declare variable length features type")]

    La propiedad `VariableLengthFeatures` tiene un atributo [VectorType](xref:Microsoft.ML.Data.VectorTypeAttribute.%23ctor%2A) para designarla como vector.  Todos los elementos de vector deben ser del mismo tipo. En conjuntos de datos con un gran número de columnas, la carga de varias columnas como un único vector reduce el número de pasadas de datos cuando se aplican transformaciones de datos.

    Esta clase se usa en la acción `ResizeFeatures`. Los nombres de sus propiedades (en este caso, solo una) se usan para indicar las columnas de DataView que se pueden usar como _entrada_ de la acción de asignación personalizada.

1. Cree una clase para las características de longitud fija, después del método `Main`:

    [!code-csharp[FixedLengthFeatures](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#FixedLengthFeatures)]

    Esta clase se usa en la acción `ResizeFeatures`. Los nombres de sus propiedades (en este caso, solo una) se usan para indicar las columnas de DataView que se pueden usar como _salida_ de la acción de asignación personalizada.

    Tenga en cuenta que el nombre de la propiedad `Features` viene determinado por el modelo de TensorFlow. Este nombre de propiedad no se puede cambiar.

1. Cree una clase para la predicción después del método `Main`:

    [!code-csharp[Prediction](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#Prediction "Declare prediction class")]

    `MovieReviewSentimentPrediction` es la clase de predicción que se utiliza tras el entrenamiento del modelo. `MovieReviewSentimentPrediction` tiene una sola matriz `float` (`Prediction`) y un atributo `VectorType`.

### <a name="create-the-mlcontext-lookup-dictionary-and-action-to-resize-features"></a>Creación de la clase MLContext, el diccionario de búsqueda y la acción para cambiar el tamaño de las características

La [clase MLContext](xref:Microsoft.ML.MLContext) es un punto de partida para todas las operaciones de ML.NET. La inicialización de `mlContext` crea un entorno de ML.NET que se puede compartir entre los objetos del flujo de trabajo de creación de modelos. Como concepto, se parece a `DBContext` en Entity Framework.

1. Reemplace la línea `Console.WriteLine("Hello World!")` del método `Main` por el siguiente código para declarar e inicializar la variable mlContext:

   [!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#CreateMLContext "Create the ML Context")]

1. Cree un diccionario para codificar palabras como enteros mediante el método [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%2A) para cargar los datos de asignación de un archivo, como se aprecia en la tabla siguiente:

    |Palabra     |Índice    |
    |---------|---------|
    |niños     |  362    |
    |quiero     |  181    |
    |incorrecto    |  355    |
    |efectos  |  302    |
    |sentimiento  |  547    |

    Agregue el código siguiente para crear la asignación de búsqueda:

    [!code-csharp[CreateLookupMap](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#CreateLookupMap)]

1. Agregue un objeto `Action` para cambiar el tamaño de la matriz de enteros de palabras de longitud variable a una matriz de enteros de tamaño fijo, con las siguientes líneas de código:

   [!code-csharp[ResizeFeatures](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#ResizeFeatures)]

## <a name="load-the-pre-trained-tensorflow-model"></a>Carga del modelo de TensorFlow entrenado previamente

1. Agregue código para cargar el modelo de TensorFlow:

    [!code-csharp[LoadTensorFlowModel](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#LoadTensorFlowModel)]

    Una vez cargado el modelo, puede extraer su esquema de entrada y de salida. Los esquemas se muestran solo a efectos de interés y aprendizaje. No necesita este código para que la aplicación final funcione:

    [!code-csharp[GetModelSchema](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#GetModelSchema)]

    El esquema de entrada es la matriz de longitud fija de palabras codificadas en enteros. El esquema de salida es una matriz float de probabilidades que indica si la opinión de una reseña es negativa o positiva. Estos valores suman 1, ya que la probabilidad de que sea positiva es el complemento de la probabilidad de que la opinión sea negativa.

## <a name="create-the-mlnet-pipeline"></a>Creación de la canalización de ML.NET

1. Cree la canalización y divida el texto de entrada en palabras con la transformación [TokenizeIntoWords](xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A) para dividir el texto en palabras como la siguiente línea de código:

   [!code-csharp[TokenizeIntoWords](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#TokenizeIntoWords)]

   La transformación [TokenizeIntoWords](xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A) usa espacios para analizar el texto o la cadena por palabras. Crea otra columna y divide cada cadena de entrada en un vector de subcadenas según el separador definido por el usuario.

1. Asigne las palabras a su codificación de enteros con la tabla de búsqueda que declaró anteriormente:

    [!code-csharp[MapValue](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#MapValue)]

1. Cambie el tamaño de las codificaciones de enteros de longitud variable al de longitud fija que requiere el modelo:

    [!code-csharp[CustomMapping](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#CustomMapping)]

1. Clasifique la entrada con el modelo de TensorFlow cargado:

    [!code-csharp[ScoreTensorFlowModel](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#ScoreTensorFlowModel)]

    La salida del modelo de TensorFlow se denomina `Prediction/Softmax`. Tenga en cuenta que el nombre `Prediction/Softmax` viene determinado por el modelo de TensorFlow. Este nombre no se puede cambiar.

1. Cree otra columna para la predicción de salida:

    [!code-csharp[SnippetCopyColumns](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#SnippetCopyColumns)]

    Tiene que copiar la columna `Prediction/Softmax` en otra cuyo nombre pueda usarse como propiedad en una clase de C#: `Prediction`. El carácter `/` no está permitido en un nombre de propiedad de C#.

## <a name="create-the-mlnet-model-from-the-pipeline"></a>Creación del modelo de ML.NET a partir de la canalización

1. Agregue el código para crear el modelo a partir de la canalización:

    [!code-csharp[SnippetCreateModel](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#SnippetCreateModel)]

    Un modelo de ML.NET se crea a partir de la cadena de estimadores de la canalización llamando al método `Fit`. En este caso, no se adaptan los datos para crear el modelo, puesto que el modelo de TensorFlow ya se ha entrenado previamente. Proporcionamos un objeto de vista de datos vacío para satisfacer los requisitos del método `Fit`.

## <a name="use-the-model-to-make-a-prediction"></a>Uso del modelo para realizar una predicción

1. Agregue el método `PredictSentiment` después del método `Main`:

    ```csharp
    public static void PredictSentiment(MLContext mlContext, ITransformer model)
    {

    }
    ```

1. Agregue el código siguiente para crear `PredictionEngine` como la primera línea en el método `PredictSentiment()`:

    [!code-csharp[CreatePredictionEngine](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#CreatePredictionEngine)]

    [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) es una API de conveniencia, que le permite realizar una predicción en una única instancia de datos. [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) no es seguro para subprocesos. Es aceptable usarlo en entornos de un solo subproceso o prototipo. Para mejorar el rendimiento y la seguridad para subprocesos en entornos de producción, use el servicio `PredictionEnginePool`, que crea un [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) de objetos de [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) para su uso en toda la aplicación. Consulte esta guía sobre cómo [usar `PredictionEnginePool` en una API web de ASP.NET Core](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).

    > [!NOTE]
    > La extensión del servicio `PredictionEnginePool` está actualmente en versión preliminar.

1. Agregue un comentario para probar la predicción del modelo entrenado en el método `Predict()` mediante la creación de una instancia de `MovieReview`:

    [!code-csharp[CreateTestData](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#CreateTestData)]

1. Pase los datos del comentario de prueba a `Prediction Engine` agregando las líneas de código siguientes al método `PredictSentiment()`:

    [!code-csharp[Predict](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#Predict)]

1. La función [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) realiza una predicción sobre una sola fila de datos:

    |Propiedad.| Valor|Tipo|
    |-------------|-----------------------|------|
    |Predicción|[0.5459937, 0.454006255]|float[]|

1. Muestre la predicción de opiniones con el código siguiente:

    [!code-csharp[DisplayPredictions](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#DisplayPredictions)]

1. Agregue una llamada a `PredictSentiment` al final del método `Main`:

    [!code-csharp[CallPredictSentiment](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#CallPredictSentiment)]

## <a name="results"></a>Resultados

Compile y ejecute su aplicación.

Los resultados deberían ser similares a los indicados a continuación. Durante el procesamiento, se muestran mensajes. Puede ver las advertencias o mensajes de procesamiento. Estos mensajes se han quitado de los resultados siguientes para mayor claridad.

```console
Number of classes: 2
Is sentiment/review positive ? Yes
```

¡Enhorabuena! Ha creado correctamente un modelo de Machine Learning para clasificar y predecir la opinión de los mensajes reutilizando un modelo de `TensorFlow` entrenado previamente en ML.NET.

Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TextClassificationTF).

En este tutorial ha aprendido a:
> [!div class="checklist"]
>
> * Carga de un modelo de TensorFlow entrenado previamente
> * Transformación del texto de comentario del sitio web en características adecuadas para el modelo
> * Uso del modelo para realizar una predicción
