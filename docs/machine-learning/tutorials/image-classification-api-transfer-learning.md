---
title: 'Tutorial: Inspección visual automatizada mediante el aprendizaje de transferencia'
description: En este tutorial se muestra cómo usar el aprendizaje de transferencia para entrenar un modelo de aprendizaje profundo de TensorFlow en ML.NET con la API de detección de imágenes con el fin de clasificar las imágenes de superficies de hormigón como con grietas o sin grietas.
author: luisquintanilla
ms.author: luquinta
ms.date: 02/09/2021
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 8397a12d179569c2836c43ab3946a2edba3bdba8
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100469778"
---
# <a name="tutorial-automated-visual-inspection-using-transfer-learning-with-the-mlnet-image-classification-api"></a>Tutorial: Inspección visual automatizada mediante el aprendizaje de transferencia con la API Image Classification de ML.NET

Obtenga información sobre cómo entrenar un modelo de aprendizaje profundo personalizado mediante el aprendizaje de transferencia, un modelo TensorFlow previamente entrenado y la API Image Classification de ML.NET para clasificar las imágenes de superficies de hormigón como con grietas o sin grietas.

En este tutorial aprenderá a:
> [!div class="checklist"]
>
> - Entender el problema
> - Obtener información sobre la API Image Classification de ML.NET
> - Comprender el modelo entrenado previamente
> - Usar el aprendizaje de transferencia para entrenar un modelo de clasificación de imágenes de TensorFlow personalizado
> - Clasificar imágenes con el modelo personalizado

## <a name="prerequisites"></a>Requisitos previos

- [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o posterior, o bien Visual Studio 2017 versión 15.6 o posterior con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.

## <a name="image-classification-transfer-learning-sample-overview"></a>Información general del ejemplo de transferencia de aprendizaje de clasificación de imágenes

Este ejemplo es una aplicación de consola de .NET Core de C# que clasifica imágenes mediante un modelo TensorFlow de aprendizaje profundo entrenado previamente. El código de este ejemplo se puede encontrar en el [explorador ed ejemplos](/samples/dotnet/machinelearning-samples/mlnet-image-classification-transfer-learning/).

## <a name="understand-the-problem"></a>Entender el problema

La clasificación de imágenes es un problema de visión informática. La clasificación de imágenes toma una imagen como entrada y la categoriza en una clase prescrita. A continuación se muestran algunos escenarios en los que la clasificación de imágenes es útil:

- Reconocimiento facial
- Detección de emociones
- Diagnóstico médico
- Detección de puntos de referencia

En este tutorial se entrena un modelo de clasificación de imágenes personalizado para realizar una inspección visual automatizada de los tableros de puente con el fin de identificar las estructuras dañadas por las grietas.

## <a name="mlnet-image-classification-api"></a>API Image Classification de ML.NET

ML.NET proporciona varias formas de realizar la clasificación de imágenes. En este tutorial se aplica el aprendizaje de transferencia mediante la API Image Classification. La API Image Classification utiliza [TensorFlow.NET](https://github.com/SciSharp/TensorFlow.NET), una biblioteca de bajo nivel que proporciona enlaces de C# para la API C++ de TensorFlow.

## <a name="what-is-transfer-learning"></a>¿Qué es el aprendizaje de transferencia?

El aprendizaje de transferencia aplica los conocimientos obtenidos de la resolución de un problema a otro problema relacionado.

Entrenar un modelo de aprendizaje profundo desde cero requiere establecer varios parámetros, una enorme cantidad de datos de entrenamiento etiquetados y una gran cantidad de recursos informáticos (cientos de horas de GPU). El uso de un modelo entrenado previamente, junto con el aprendizaje de transferencia, permite acceso directo al proceso de entrenamiento.

## <a name="training-process"></a>Proceso de entrenamiento

La API Image Classification inicia el proceso de entrenamiento mediante la carga de un modelo TensorFlow previamente entrenado. El proceso de entrenamiento consta de dos pasos:

1. Fase de cuello de botella
2. Fase de entrenamiento

![Pasos de entrenamiento](./media/image-classification-api-transfer-learning/training.png)

### <a name="bottleneck-phase"></a>Fase de cuello de botella

Durante la fase de cuello de botella, se carga el conjunto de imágenes de aprendizaje y los valores de píxeles se usan como entrada, o características, para las capas inmovilizadas del modelo previamente entrenado. Las capas inmovilizadas incluyen todas las capas de la red neuronal hasta la penúltima capa, que se conoce como capa de cuello de botella. Estas capas se denominan inmovilizadas porque en ellas no se producirá ningún aprendizaje y las operaciones son de paso a través. En estas capas inmovilizadas es donde se calculan los patrones de nivel inferior que ayudan a un modelo a diferenciar entre las distintas clases. Cuanto mayor sea el número de capas, más intensiva a nivel de computación será este paso. Afortunadamente, puesto que se trata de un cálculo que se realiza una sola vez, los resultados se pueden almacenar en caché y usar en ejecuciones posteriores cuando se experimente con parámetros distintos.

### <a name="training-phase"></a>Fase de entrenamiento

Una vez calculados los valores de salida de la fase de cuello de botella, se usan como entrada para volver a entrenar la capa final del modelo. Este proceso es iterativo y se ejecuta durante el número de veces que especifican los parámetros del modelo. Durante cada ejecución, se evalúan la pérdida y la precisión. Después, se realizan los ajustes adecuados para mejorar el modelo con el objetivo de minimizar la pérdida y maximizar la precisión. Una vez finalizado el entrenamiento, se generan dos formatos del modelo. Uno de ellos es la versión `.pb` del modelo y el otro es la versión serializada de ML.NET `.zip`. Cuando se trabaja en entornos compatibles con ML.NET, se recomienda usar la versión `.zip` del modelo. Sin embargo, en entornos en los que no se admite ML.NET, se tiene la opción de usar la versión `.pb`.

## <a name="understand-the-pretrained-model"></a>Descripción del modelo entrenado previamente

El modelo previamente entrenado que se usa en este tutorial es la variante de capa 101 del modelo de Residual Network v2 (ResNet). El modelo original se ha entrenado para clasificar las imágenes en mil categorías. El modelo toma como entrada una imagen de tamaño 224 x 224 y genera las probabilidades de clase para cada una de las clases en las que se ha entrenado. Parte de este modelo se usa para entrenar un nuevo modelo mediante imágenes personalizadas con el fin de realizar predicciones entre dos clases.

## <a name="create-console-application"></a>Creación de una aplicación de consola

Ahora que tiene conocimientos generales del aprendizaje de transferencia y de la API Image Classification, es momento de compilar la aplicación.

1. Cree una **Aplicación de consola de .NET Core de C#** llamada "DeepLearning_ImageClassification_Binary".
1. Instale el paquete NuGet **Microsoft.ML**:

    [!INCLUDE [mlnet-current-nuget-version](../../../includes/mlnet-current-nuget-version.md)]

    1. En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.
    1. Elija "nuget.org" como origen del paquete.
    1. Seleccione la pestaña **Examinar**.
    1. Active la casilla **Incluir versión preliminar**.
    1. Busque **Microsoft.ML**.
    1. Seleccione el botón **Instalar**.
    1. Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.
    1. Repita estos pasos para los paquetes NuGet **Microsoft.ML.Vision**, **SciSharp.TensorFlow.Redist** y **Microsoft.ML.ImageAnalytics**.

### <a name="prepare-and-understand-the-data"></a>Preparar y entender los datos

> [!NOTE]
> Los conjuntos de valores de este tutorial están tomados del documento "SDNET2018: A concrete crack image dataset for machine learning applications" (2018) (SDNET2018: Un conjunto de datos de imágenes de hormigón descifradas para aplicaciones de aprendizaje automático) de Marc Maguire, Sattar Dorafshan y Robert J. Thomas. Examinar todos los conjuntos de datos. Documento 48. <https://digitalcommons.usu.edu/all_datasets/48>

SDNET2018 es un conjunto de datos de imágenes que contiene anotaciones para estructuras de hormigón con grietas y sin grietas (tableros de puente, muros y pavimento).

![Ejemplos de tablero de puente del conjunto de datos de SDNET2018](./media/image-classification-api-transfer-learning/sdnet2018decksamples.png)

Los datos se organizan en tres subdirectorios:

- D contiene imágenes de tableros de puente
- P contiene imágenes de pavimentos
- W contiene imágenes de muros

Cada uno de estos subdirectorios contiene a su vez dos subdirectorios adicionales con prefijos:

- C es el prefijo usado para las superficies con grietas.
- U es el prefijo usado para las superficies sin grietas.

En este tutorial, solo se usan imágenes de tableros de puente.

1. Descargue el [conjunto de datos](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/assets.zip) y descomprímalo.
1. Cree un directorio llamado "recursos" en el proyecto para guardar los archivos del conjunto de datos.
1. Copie los subdirectorios *CD* y *UD* del directorio descomprimido recientemente en el directorio *recursos*.

### <a name="create-input-and-output-classes"></a>Creación de las clases de entrada y salida

1. Abra el archivo *Program.cs* y reemplace las instrucciones `using` existentes en la parte superior del archivo por las siguientes:

    [!code-csharp [ProgramUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L1-L7)]

1. Debajo de la clase `Program` en *Program.cs*, cree una clase llamada `ImageData`. Esta clase se utiliza para representar los datos cargados inicialmente.

    [!code-csharp [ImageDataClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L137-L142)]

    `ImageData` contiene las propiedades siguientes:

    - `ImagePath` es la ruta de acceso completa donde se almacena la imagen.
    - `Label` es la categoría a la que pertenece la imagen. Este es el valor que se va a predecir.

1. Cree clases para los datos de entrada y salida.

    1. Debajo de la clase `ImageData`, defina el esquema de los datos de entrada en una nueva clase llamada `ModelInput`.

        [!code-csharp [ModelInputClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L144-L153)]

        `ModelInput` contiene las propiedades siguientes:

        - `Image` es la representación `byte[]` de la imagen. El modelo espera que los datos de la imagen sean de este tipo para el entrenamiento.
        - `LabelAsKey` es la representación numérica de `Label`.
        - `ImagePath` es la ruta de acceso completa donde se almacena la imagen.
        - `Label` es la categoría a la que pertenece la imagen. Este es el valor que se va a predecir.

        Solo se usan `Image` y `LabelAsKey` para entrenar el modelo y hacer predicciones. Las propiedades `ImagePath` y `Label` se conservan por comodidad para tener acceso al nombre y categoría del archivo de imagen original.

    1. Después, debajo de la clase `ModelInput`, defina el esquema de los datos de salida en una nueva clase llamada `ModelOutput`.

        [!code-csharp [ModelOutputClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L155-L162)]

        `ModelOutput` contiene las propiedades siguientes:

        - `ImagePath` es la ruta de acceso completa donde se almacena la imagen.
        - `Label` es la categoría original a la que pertenece la imagen. Este es el valor que se va a predecir.
        - `PredictedLabel` es el valor que predice el modelo.

        De forma similar a `ModelInput`, solo se requiere `PredictedLabel` para realizar predicciones, ya que contiene la predicción que realiza el modelo. Las propiedades `ImagePath` y `Label` se conservan por comodidad para tener acceso al nombre y categoría del archivo de imagen original.

### <a name="create-workspace-directory"></a>Creación del directorio del área de trabajo

Cuando los datos de entrenamiento y validación no cambian a menudo, se recomienda almacenar en caché los valores de cuello de botella calculados para las ejecuciones posteriores.

1. En el proyecto, cree un directorio llamado *workspace* para almacenar los valores de cuello de botella calculados y la versión `.pb` del modelo.

### <a name="define-paths-and-initialize-variables"></a>Definición de rutas de acceso e inicialización de variables

1. Dentro del método `Main`, defina la ubicación de los recursos, los valores de cuello de botella calculados y la versión `.pb` del modelo.

    [!code-csharp [DefinePaths](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L15-L17)]

1. Inicialice la variable `mlContext` con una instancia nueva de [MLContext](xref:Microsoft.ML.MLContext).

    [!code-csharp [MLContext](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L19)]

    La clase [MLContext](xref:Microsoft.ML.MLContext) es un punto de partida para todas las operaciones de ML.NET. Al inicializar mlContext se crea un entorno de ML.NET que se puede compartir entre los objetos del flujo de trabajo de creación de modelos. Como concepto, se parece a `DbContext` en Entity Framework.

## <a name="load-the-data"></a>Carga de los datos

### <a name="create-data-loading-utility-method"></a>Creación de un método de utilidad de carga de datos

Las imágenes se almacenan en dos subdirectorios. Antes de cargar los datos, se debe dar formato a una lista de objetos de `ImageData`. Para ello, agregue el método `LoadImagesFromDirectory` debajo del método `Main`.

```csharp
public static IEnumerable<ImageData> LoadImagesFromDirectory(string folder, bool useFolderNameAsLabel = true)
{

}
```

1. En `LoadImagesFromDirectory`, agregue el código siguiente para obtener todas las rutas de acceso de archivo de los subdirectorios:

    [!code-csharp [GetFiles](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L104-L105)]

1. Luego, recorra en iteración cada uno de los archivos mediante una instrucción `foreach`.

    ```csharp
    foreach (var file in files)
    {

    }
    ```

1. En la instrucción `foreach`, compruebe que se admiten las extensiones de archivo. La API Image Classification admite formatos JPEG y PNG.

    [!code-csharp [CheckExtension](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L109-L111)]

1. Después, obtenga la etiqueta del archivo. Si el parámetro `useFolderNameAsLabel` está establecido en `true`, el directorio principal donde se guarda el archivo se usa como etiqueta. De lo contrario, espera que la etiqueta sea un prefijo del nombre de archivo o el propio nombre de archivo.

    [!code-csharp [GetLabel](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L112-L126)]

1. Por último, cree una nueva instancia de `ModelInput`.

    [!code-csharp [CreateImageData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L128-L132)]

### <a name="prepare-the-data"></a>Preparar los datos

1. De vuelta en el método `Main`, use el método de utilidad `LoadImagesFromDirectory` para obtener la lista de imágenes que se usan para el entrenamiento.

    [!code-csharp [LoadImages](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L22)]

1. Luego, cargue las imágenes en un elemento [`IDataView`](xref:Microsoft.ML.IDataView) con el método [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable%2A).

    [!code-csharp [CreateIDataView](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L24)]

1. Los datos se cargan en el orden en que se han leído desde los directorios. Para equilibrar los datos, ordénelos aleatoriamente mediante el método [`ShuffleRows`](xref:Microsoft.ML.DataOperationsCatalog.ShuffleRows%2A).

    [!code-csharp [ShuffleRows](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L26)]

1. Los modelos de Machine Learning esperan que la entrada esté en formato numérico. Por lo tanto, es necesario realizar algún procesamiento previo en los datos antes del entrenamiento. Cree un elemento [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) formado por las transformaciones [`MapValueToKey`](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) y `LoadRawImageBytes`. La transformación `MapValueToKey` toma el valor de categoría en la columna `Label`, lo convierte en un valor `KeyType` numérico y lo almacena en una nueva columna llamada `LabelAsKey`. `LoadImages` toma los valores de la columna `ImagePath`, junto con el parámetro `imageFolder`, con el fin de cargar las imágenes para el entrenamiento.

    [!code-csharp [PreprocessingPipeline](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L28-L34)]

1. Use el método [`Fit`](xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A) para aplicar los datos a `preprocessingPipeline`[`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) seguido del método [`Transform`](xref:Microsoft.ML.Data.TransformerChain%601.Transform%2A), que devuelve un elemento [`IDataView`](xref:Microsoft.ML.IDataView) que contiene los datos procesados previamente.

    [!code-csharp [PreprocessData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L36-L38)]

1. Para entrenar un modelo, es importante tener un conjunto de datos de entrenamiento, así como un conjunto de datos de validación. El modelo se entrena en el conjunto de entrenamiento. La calidad de las predicciones en los datos no vistos la mide el rendimiento en el conjunto de validación. En función de los resultados de ese rendimiento, el modelo realiza ajustes sobre lo que ha aprendido en un esfuerzo por mejorar. El conjunto de validación puede proceder de dividir el conjunto de datos original o de otro origen que ya se haya reservado para esta finalidad. En este caso, el conjunto de datos procesado previamente se divide en conjuntos de entrenamiento, validación y pruebas.

    [!code-csharp [CreateDataSplits](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L40-L41)]

    En el ejemplo de código anterior se realizan dos divisiones. En primer lugar, los datos procesados previamente se dividen y el 70 % de estos se usa para el entrenamiento, mientras que el 30 % restante se utiliza para la validación. Después, 30 % perteneciente al conjunto de validación se divide en conjuntos de validación y pruebas, donde el 90 % se usa para la validación y el 10 % se usa para las pruebas.

    Una manera de pensar en la finalidad de estas particiones de datos es hacer un examen. Al estudiar para un examen, se revisan las notas, libros u otros recursos para obtener una idea sobre los conceptos que hay que preparar para el examen. Esto es para lo que sirve el conjunto de entrenamiento. Después, se puede realizar un examen ficticio para poner a prueba los conocimientos. Aquí es donde el conjunto de validación es práctico. Se quiere comprobar si se tiene una idea correcta de los conceptos antes de realizar el examen real. En función de estos resultados, tome nota de lo que no haya acertado o de lo que no haya entendido bien e incorpore los cambios a medida que repasa para el examen real. Por último, realice el examen. Esto es para lo que se usa el conjunto de prueba. Nunca ha visto las preguntas que aparecen en el examen y ahora puede usar lo que ha aprendido a partir del entrenamiento y la validación para aplicar sus conocimientos a la tarea que nos ocupa.

1. Asigne a las particiones sus respectivos valores para los datos de entrenamiento, validación y prueba.

    [!code-csharp [CreateDatasets](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L43-L45)]

## <a name="define-the-training-pipeline"></a>Definición de la canalización de entrenamiento

El entrenamiento del modelo consta de un par de pasos. En primer lugar, se usa la API Image Classification para entrenar el modelo. Luego, las etiquetas codificadas de la columna `PredictedLabel` se convierten de nuevo a su valor de categoría original mediante la transformación `MapKeyToValue`.

1. Cree una variable para almacenar un conjunto de parámetros obligatorios y opcionales para un `ImageClassificationTrainer`.

    [!code-csharp [ClassifierOptions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L47-L57)]

    `ImageClassificationTrainer` admite varios parámetros opcionales:

    - `FeatureColumnName` es la columna que se utiliza como entrada del modelo.
    - `LabelColumnName` es la columna del valor que se va a predecir.
    - `ValidationSet` es [`IDataView`](xref:Microsoft.ML.IDataView) que contiene los datos de validación.
    - `Arch` define la arquitectura de modelo previamente entrenada que se va a usar. En este tutorial se usa la variante de capa 101 del modelo ResNetv2.
    - `MetricsCallback` enlaza una función para realizar un seguimiento del progreso durante el entrenamiento.
    - `TestOnTrainSet` indica al modelo que mida el rendimiento en el conjunto de entrenamiento cuando no haya ningún conjunto de validación.
    - `ReuseTrainSetBottleneckCachedValues` indica al modelo si se deben usar los valores almacenados en caché de la fase de cuello de botella en las ejecuciones posteriores. La fase de cuello de botella es un cálculo de paso a través único que es intensiva a nivel de computación la primera vez que se realiza. Si los datos de entrenamiento no cambian y quiere experimentar con un número distinto de épocas o tamaño de lote, el uso de los valores almacenados en caché reduce considerablemente la cantidad de tiempo necesario para entrenar un modelo.
    - `ReuseValidationSetBottleneckCachedValues` es parecido a `ReuseTrainSetBottleneckCachedValues` solo que, en este caso, se usa para el conjunto de validación.
    - `WorkspacePath` define el directorio donde se almacenan los valores de cuello de botella calculados y la versión `.pb` del modelo.

1. Defina la canalización de entrenamiento [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) que consta de `mapLabelEstimator` y `ImageClassificationTrainer`.

    [!code-csharp [TrainingPipeline](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L59-L60)]

1. Use el método [`Fit`](xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A) para entrenar el modelo.

    [!code-csharp [TrainModel](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L62)]

## <a name="use-the-model"></a>Uso del modelo

Ahora que se ha entrenado el modelo, es el momento de usarlo para clasificar las imágenes.

Debajo del método `Main`, cree un método de utilidad nuevo llamado `OutputPrediction` para mostrar información de predicción en la consola.

[!code-csharp [OuputPredictionMethod](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L96-L100)]

### <a name="classify-a-single-image"></a>Clasificación de una sola imagen

1. Agregue un método nuevo llamado `ClassifySingleImage` debajo del método `Main` para crear y generar una única predicción de imagen.

    ```csharp
    public static void ClassifySingleImage(MLContext mlContext, IDataView data, ITransformer trainedModel)
    {

    }
    ```

1. Cree un elemento [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) en el método `ClassifySingleImage`. [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) es una API de conveniencia, que permite pasar datos y luego realizar una predicción en una única instancia de datos.

    [!code-csharp [CreatePredictionEngine](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L73)]

1. Para acceder a una única instancia de `ModelInput`, convierta [`IDataView`](xref:Microsoft.ML.IDataView) de `data` en un elemento [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) mediante el método [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) y, después, obtenga la primera observación.

    [!code-csharp [GetTestInputData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L75)]

1. Use el método [`Predict`](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) para clasificar la imagen.

    [!code-csharp [MakeSinglePrediction](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L77)]

1. Genere la predicción en la consola con el método `OutputPrediction`.

    [!code-csharp [OuputSinglePrediction](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L79-L80)]

1. En el método `Main`, llame a `ClassifySingleImage` mediante el conjunto de prueba de imágenes.

    [!code-csharp [ClassifySingleImage](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L64)]

### <a name="classify-multiple-images"></a>Clasificación de varias imágenes

1. Agregue un método nuevo llamado `ClassifyImages` debajo del método `ClassifySingleImage` para realizar y generar varias predicciones de imágenes.

    ```csharp
    public static void ClassifyImages(MLContext mlContext, IDataView data, ITransformer trainedModel)
    {

    }
    ```

1. Cree un elemento [`IDataView`](xref:Microsoft.ML.IDataView) que contenga las predicciones mediante el método [`Transform`](xref:Microsoft.ML.ITransformer.Transform%2A). Agregue el código siguiente dentro del método `ClassifyImages`.

    [!code-csharp [MakeMultiplePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L85)]

1. Para recorrer en iteración las predicciones, convierta [`IDataView`](xref:Microsoft.ML.IDataView) de `predictionData` en un elemento [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) con el método [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) y, después, obtenga las 10 primeras observaciones.

    [!code-csharp [IEnumerablePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L87)]

1. Recorra en iteración y genere las etiquetas originales y previstas de las predicciones.

    [!code-csharp [OutputMultiplePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L89-L93)]

1. Por último, en el método `Main`, llame a `ClassifyImages` mediante el conjunto de prueba de imágenes.

    [!code-csharp [ClassifyImages](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification/Program.cs#L66)]

## <a name="run-the-application"></a>Ejecutar la aplicación

Ejecute la aplicación de consola. La salida debe ser similar a la siguiente. Es posible que vea advertencias o mensajes de procesamiento, si bien se han quitado de los resultados siguientes para mayor claridad. Por motivos de brevedad, la salida se ha resumido.

**Fase de cuello de botella**

No se imprime ningún valor para el nombre de la imagen porque las imágenes se cargan como un elemento `byte[]` y, por lo tanto, no hay ningún nombre de imagen para mostrar.

```test
Phase: Bottleneck Computation, Dataset used:      Train, Image Index: 279
Phase: Bottleneck Computation, Dataset used:      Train, Image Index: 280
Phase: Bottleneck Computation, Dataset used: Validation, Image Index:   1
Phase: Bottleneck Computation, Dataset used: Validation, Image Index:   2
```

**Fase de entrenamiento**

```text
Phase: Training, Dataset used: Validation, Batch Processed Count:   6, Epoch:  21, Accuracy:  0.6797619
Phase: Training, Dataset used: Validation, Batch Processed Count:   6, Epoch:  22, Accuracy:  0.7642857
Phase: Training, Dataset used: Validation, Batch Processed Count:   6, Epoch:  23, Accuracy:  0.7916667
```

**Salida de clasificación de imágenes**

```text
Classifying single image
Image: 7001-220.jpg | Actual Value: UD | Predicted Value: UD

Classifying multiple images
Image: 7001-220.jpg | Actual Value: UD | Predicted Value: UD
Image: 7001-163.jpg | Actual Value: UD | Predicted Value: UD
Image: 7001-210.jpg | Actual Value: UD | Predicted Value: UD
```

Al inspeccionar la imagen *7001-220.jpg*, puede ver que, de hecho, no tiene grietas.

![Imagen del conjunto de SDNET2018 que se usa para la predicción](./media/image-classification-api-transfer-learning/predictedimage.jpg)

¡Enhorabuena! Ha compilado correctamente un modelo de aprendizaje profundo para la clasificación de imágenes.

### <a name="improve-the-model"></a>Mejora del modelo

Si no está satisfecho con los resultados del modelo, puede intentar mejorar su rendimiento probando algunos de los enfoques siguientes:

- **Más datos**: cuanto mayor sea el número de ejemplos de los que pueda aprender un modelo, mejor funcionará. Descargue el [conjunto de datos SDNET2018](https://digitalcommons.usu.edu/cgi/viewcontent.cgi?filename=2&article=1047&context=all_datasets&type=additional) completo y úselo para entrenar.
- **Aumentar los datos**: Una técnica común para agregar diversidad a los datos es aumentarlos tomando una imagen y aplicando distintas transformaciones (girar, voltear, desplazar o recortar). Esto agrega ejemplos más variados para que el modelo aprenda de ellos.
- **Entrenar durante más tiempo**: cuanto más tiempo se entrene, más ajustado estará el modelo. Aumentar el número de épocas puede mejorar el rendimiento del modelo.
- **Experimentar con otros hiperparámetros**: además de los parámetros que se usan en este tutorial, se pueden ajustar otros parámetros para mejorar potencialmente el rendimiento. Cambiar la velocidad de aprendizaje, que determina el tamaño de las actualizaciones realizadas en el modelo después de cada época, puede mejorar el rendimiento.
- **Usar una arquitectura de modelo diferente**: en función de lo que parezcan los datos, puede variar el modelo que sea capaz de aprender mejor sus características. Si no está satisfecho con el rendimiento del modelo, intente cambiar la arquitectura.

### <a name="additional-resources"></a>Recursos adicionales

- [Aprendizaje profundo frente a aprendizaje automático](/azure/machine-learning/service/concept-deep-learning-vs-machine-learning).

## <a name="next-steps"></a>Pasos siguientes

En este tutorial, se ha obtenido información sobre cómo compilar un modelo de aprendizaje profundo personalizado mediante el aprendizaje de transferencia, un modelo TensorFlow de clasificación de imágenes previamente entrenado y la API Image Classification de ML.NET para clasificar las imágenes de superficies de hormigón como con grietas o sin grietas.

Siga con el siguiente tutorial para obtener más información.

> [!div class="nextstepaction"]
> [Detección de objetos](object-detection-onnx.md)
