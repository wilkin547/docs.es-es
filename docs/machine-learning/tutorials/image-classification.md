---
title: 'Tutorial: Modelo de clasificación de imágenes de ML.NET de TensorFlow'
description: Obtenga información sobre cómo transferir el conocimiento de un modelo de TensorFlow existente a un modelo de clasificación de imágenes de ML.NET nuevo. El modelo TensorFlow se entrenó para clasificar las imágenes en mil categorías. El modelo de ML.NET usa el aprendizaje de transferencia para clasificar las imágenes en menos categorías más amplias.
ms.date: 06/30/2020
ms.topic: tutorial
ms.custom: mvc, title-hack-0612
ms.openlocfilehash: b3e5617979d1635248f87db6008d3e234bb3ffc5
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104877038"
---
# <a name="tutorial-generate-an-mlnet-image-classification-model-from-a-pre-trained-tensorflow-model"></a>Tutorial: Generación de un modelo de clasificación de imágenes de ML.NET desde un modelo entrenado previamente de TensorFlow

Obtenga información sobre cómo transferir el conocimiento de un modelo de TensorFlow existente a un modelo de clasificación de imágenes de ML.NET nuevo.

El modelo de TensorFlow se entrenó para clasificar las imágenes en mil categorías. El modelo de ML.NET usa parte del modelo de TensorFlow en su canalización para entrenar un modelo con el fin de clasificar las imágenes en 3 categorías.

Entrenar un modelo de [clasificación de imágenes](https://en.wikipedia.org/wiki/Outline_of_object_recognition) desde cero requiere establecer millones de parámetros, una enorme cantidad de datos de aprendizaje etiquetados y una gran cantidad de recursos informáticos (cientos de horas de GPU). Si bien no es tan eficaz como entrenar un modelo personalizado desde cero, el aprendizaje por transferencia permite acortar este proceso al trabajar con miles de imágenes frente a millones de imágenes etiquetadas y crear un modelo personalizado con bastante rapidez (menos de una hora en una máquina sin GPU). En este tutorial se amplía aún más ese proceso, con solo una docena de imágenes de aprendizaje.

En este tutorial aprenderá a:
> [!div class="checklist"]
>
> * Entender el problema
> * Incorporación del modelo de TensorFlow entrenado previamente en la canalización de ML.NET
> * Entrenamiento y evaluación del modelo de ML.NET
> * Clasificación de una imagen de prueba

Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/main/machine-learning/tutorials/TransferLearningTF). Tenga en cuenta que, de forma predeterminada, la configuración del proyecto de .NET de este tutorial tiene como destino .NET Core 2.2.

## <a name="what-is-transfer-learning"></a>¿Qué es el aprendizaje de transferencia?

El aprendizaje de transferencia es el proceso de usar los conocimientos adquiridos al resolver un problema y aplicarlos a un problema distinto, pero relacionado.

En este tutorial, usará parte de un modelo de TensorFlow (entrenado para clasificar las imágenes en mil categorías) en un modelo de ML.NET que clasifica las imágenes en 3 categorías.

## <a name="prerequisites"></a>Requisitos previos

* [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o posterior, o bien Visual Studio 2017 versión 15.6 o posterior con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.
* [El archivo ZIP del directorio de recursos del tutorial](https://github.com/dotnet/samples/blob/main/machine-learning/tutorials/TransferLearningTF/image-classifier-assets.zip)
* [El modelo de Machine Learning de InceptionV1](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)

## <a name="select-the-right-machine-learning-task"></a>Selección de la tarea de aprendizaje automático adecuada

### <a name="deep-learning"></a>Aprendizaje profundo

El [aprendizaje profundo](https://en.wikipedia.org/wiki/Deep_learning) es un subconjunto de Machine Learning, que está revolucionando áreas como Computer Vision y reconocimiento de voz.

Los modelos de aprendizaje profundo se entrenan mediante el uso de grandes conjuntos de [datos etiquetados](https://en.wikipedia.org/wiki/Labeled_data) y [redes neuronales](https://en.wikipedia.org/wiki/Artificial_neural_network) que contienen varias capas de conocimiento. Aprendizaje profundo:

* Funciona mejor en algunas tareas como Computer Vision.
* Requiere enormes cantidades de datos de entrenamiento.

La clasificación de imágenes es una tarea de Machine Learning común que nos permite clasificar imágenes automáticamente en categorías como:

* Detectar o no una cara humana en una imagen.
* Detectar gatos o perros.

 O bien, como en las imágenes siguientes, determinar si una imagen es un alimento, un juguete o un dispositivo:

![imagen de una pizza](./media/image-classification/220px-Pepperoni_pizza.jpg)
![imagen de un oso de peluche](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![imagen de una tostadora](./media/image-classification/193px-Broodrooster.jpg)

>[!Note]
> Las imágenes anteriores pertenecen a Wikimedia Commons y tienen los siguientes atributos:
>
> * "220px-Pepperoni_pizza.jpg" de dominio público, <https://commons.wikimedia.org/w/index.php?curid=79505>,
> * "119px-Nalle_-_a_small_brown_teddy_bear.jpg" de [Jonik](https://commons.wikimedia.org/wiki/User:Jonik), autofotografía, CC BY-SA 2.0, <https://commons.wikimedia.org/w/index.php?curid=48166>.
> * "193px-Broodrooster.jpg" de [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972), trabajo propio, CC BY-SA 3.0, <https://commons.wikimedia.org/w/index.php?curid=27403>

`Inception model` está entrenado para clasificar imágenes en miles de categorías, pero, en este tutorial, el usuario deberá clasificar las imágenes en un conjunto de categorías más pequeño y solo en esas categorías. Escriba la parte `transfer` de `transfer learning`. Puede transferir la capacidad que `Inception model` tiene para reconocer y clasificar imágenes a las nuevas categorías limitadas del clasificador personalizado de imágenes.

* Alimentos
* Juguetes
* Dispositivos

En este tutorial se usa el modelo de aprendizaje profundo del [modelo de inicio](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) de TensorFlow, un modelo de reconocimiento de imágenes popular entrenado en el conjunto de datos `ImageNet`. El modelo de TensorFlow clasifica imágenes completas en miles de clases como "Paraguas", "Jersey" y "Lavavajillas".

Como `Inception model` se entrenó previamente en miles de imágenes distintas, contiene internamente las [características de imagen](https://en.wikipedia.org/wiki/Feature_(computer_vision)) necesarias para la identificación de imágenes. Podemos usar estas características de imagen internas en el modelo para entrenar un modelo nuevo con muchas menos clases.

Como se muestra en el diagrama siguiente, puede agregar una referencia a los paquetes NuGet de ML.NET en las aplicaciones de .NET Core o .NET Framework. En segundo plano, ML.NET incluye y hace referencia a la biblioteca nativa de `TensorFlow` que permite escribir código que carga un archivo de modelo de `TensorFlow` entrenado existente.

![Diagrama de la arquitectura de ML.NET de transformación de TensorFlow](./media/image-classification/tensorflow-mlnet.png)

### <a name="multiclass-classification"></a>Clasificación multiclase

Después de usar el modelo de inicio de TensorFlow para extraer características adecuadas como entrada para un algoritmo de aprendizaje automático clásico, se agrega un [clasificador multiclase](../resources/tasks.md#multiclass-classification) de ML.NET.

El entrenador específico que se usa en este caso es el [algoritmo de regresión logística multinomial](https://en.wikipedia.org/wiki/Multinomial_logistic_regression).

El algoritmo que implementa este entrenador funciona con un gran número de características, que es el caso de un modelo de aprendizaje profundo que funciona con datos de imagen.

### <a name="data"></a>Datos

Hay dos orígenes de datos: el archivo `.tsv` y los archivos de imagen.  El archivo `tags.tsv` contiene dos columnas: la primera está definida como `ImagePath` y la segunda es la `Label` que corresponde a la imagen. El archivo de ejemplo siguiente no tiene una fila de encabezado y se ve así:

<!-- markdownlint-disable MD010 -->
```tsv
broccoli.jpg    food
pizza.jpg   food
pizza2.jpg  food
teddy2.jpg  toy
teddy3.jpg  toy
teddy4.jpg  toy
toaster.jpg appliance
toaster2.png    appliance
```
<!-- markdownlint-enable MD010 -->

Las imágenes de entrenamiento y prueba se encuentran en las carpetas de recursos que descargará en un archivo ZIP. Estas imágenes pertenecen a Wikimedia Commons.
> *[Wikimedia Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), el repositorio multimedia gratuito*. Recuperado a las 10:48 del 17 de octubre de 2018 desde: <https://commons.wikimedia.org/wiki/Pizza>
> <https://commons.wikimedia.org/wiki/Toaster>
> <https://commons.wikimedia.org/wiki/Teddy_bear>

## <a name="setup"></a>Programa de instalación

### <a name="create-a-project"></a>Crear un proyecto

1. Cree una **aplicación de consola de .NET Core** denominada "TransferLearningTF".

1. Instale el **paquete NuGet Microsoft.ML**:

    [!INCLUDE [mlnet-current-nuget-version](../../../includes/mlnet-current-nuget-version.md)]

    * En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.
    * Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar y busque **Microsoft.ML**.
    * Seleccione el botón **Instalar**.
    * Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de los cambios**.
    * Haga clic en el botón **Acepto** en el cuadro de diálogo **Aceptación de la licencia** si está de acuerdo con los términos de licencia de los paquetes que aparecen.
    * Repita estos pasos para **Microsoft.ML.ImageAnalytics**, **SciSharp.TensorFlow.Redist** y **Microsoft.ML.TensorFlow**.

### <a name="download-assets"></a>Descarga de activos

1. Descargue el [archivo ZIP del directorio de recursos del proyecto](https://github.com/dotnet/samples/blob/main/machine-learning/tutorials/TransferLearningTF/image-classifier-assets.zip) y descomprímalo.

1. Copie el directorio `assets` en el directorio de proyecto *TransferLearningTF*. Este directorio y sus subdirectorios contienen los datos y los archivos auxiliares (excepto los del modelo de inicio, que descargará y agregará en el paso siguiente) que se necesitan en este tutorial.

1. Descargue el [modelo de inicio](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) y descomprímalo.

1. Copie el contenido del directorio `inception5h` que acaba de descomprimir en el directorio `assets/inception` del proyecto *TransferLearningTF*. En este directorio está el modelo y los archivos auxiliares adicionales que se necesitan en este tutorial, tal como se muestra en la imagen siguiente:

   ![Contenido del directorio de inicio](./media/image-classification/inception-files.png)

1. En el Explorador de soluciones, haga clic con el botón derecho en cada uno de los archivos del directorio de recursos y los subdirectorios y seleccione **Propiedades**. En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.

### <a name="create-classes-and-define-paths"></a>Crear clases y definir rutas de acceso

1. Agregue las siguientes instrucciones `using` adicionales a la parte superior del archivo *Program.cs*:

    [!code-csharp[AddUsings](./snippets/image-classification/csharp/Program.cs#AddUsings)]

1. Agregue el código siguiente a la línea inmediatamente por encima del método `Main` para especificar las rutas de acceso a los recursos:

    [!code-csharp[DeclareGlobalVariables](./snippets/image-classification/csharp/Program.cs#DeclareGlobalVariables)]

1. Cree clases para los datos de entrada y las predicciones.

    [!code-csharp[DeclareImageData](./snippets/image-classification/csharp/Program.cs#DeclareImageData)]

    `ImageData` es la clase de datos de imagen de entrada y tiene los campos <xref:System.String> siguientes:

    * `ImagePath` contiene el nombre del archivo de imagen.
    * `Label` contiene un valor para la etiqueta de imagen.

1. Agregue una clase nueva al proyecto para `ImagePrediction`:

    [!code-csharp[DeclareImagePrediction](./snippets/image-classification/csharp/Program.cs#DeclareImagePrediction)]

    `ImagePrediction` es la clase de predicción de imagen y tiene los campos siguientes:

    * `Score` contiene el porcentaje de confianza de una clasificación de imágenes determinada.
    * `PredictedLabelValue` contiene un valor para la etiqueta de clasificación de imágenes prevista.

    `ImagePrediction` es la clase usada para la predicción una vez entrenado el modelo. Tiene una `string` (`ImagePath`) para la ruta de acceso a la imagen. `Label` se usa para reutilizar y entrenar el modelo. `PredictedLabelValue` se usa durante la predicción y la evaluación. Para la evaluación, se utiliza una entrada con los datos de entrenamiento, los valores de predicción y el modelo.

### <a name="initialize-variables-in-main"></a>Inicializar variables en Main

1. Inicialice la variable `mlContext` con una instancia nueva de `MLContext`.  Reemplace la línea `Console.WriteLine("Hello World!")` por el código siguiente en el método `Main`:

    [!code-csharp[CreateMLContext](./snippets/image-classification/csharp/Program.cs#CreateMLContext)]

    La [clase MLContext](xref:Microsoft.ML.MLContext) es un punto de partida para todas las operaciones de ML.NET. Al inicializar `mlContext`, se crea un entorno de ML.NET que se puede compartir entre los objetos del flujo de trabajo de creación de modelos. Como concepto, se parece a `DBContext` en Entity Framework.

### <a name="create-a-struct-for-inception-model-parameters"></a>Creación de una estructura para los parámetros del modelo de inicio

1. El modelo de inicio tiene varios parámetros que se deben transmitir. Cree una estructura para asignar los valores de parámetros a nombres descriptivos con el código siguiente, justo después del método `Main()`:

    [!code-csharp[InceptionSettings](./snippets/image-classification/csharp/Program.cs#InceptionSettings)]

### <a name="create-a-display-utility-method"></a>Crear un método de utilidad para mostrar

Dado que se mostrarán los datos de imagen y las predicciones relacionadas más de una vez, cree un método de utilidad para mostrar a fin de controlar la visualización de los resultados de la imagen y la predicción.

1. Cree el método `DisplayResults()` justo después de la estructura `InceptionSettings` con el código siguiente:

    ```csharp
    private static void DisplayResults(IEnumerable<ImagePrediction> imagePredictionData)
    {

    }
    ```

1. Rellene el cuerpo del método `DisplayResults`:

    [!code-csharp[DisplayPredictions](./snippets/image-classification/csharp/Program.cs#DisplayPredictions)]

### <a name="create-a-tsv-file-utility-method"></a>Crear un método de utilidad de archivo .tsv

1. Cree el método `ReadFromTsv()`, justo después del método `DisplayResults()`, mediante el código siguiente:

    ```csharp
    public static IEnumerable<ImageData> ReadFromTsv(string file, string folder)
    {

    }
    ```

1. Rellene el cuerpo del método `ReadFromTsv`:

    [!code-csharp[ReadFromTsv](./snippets/image-classification/csharp/Program.cs#ReadFromTsv)]

    El código analiza el archivo `tags.tsv` para agregar la ruta de acceso al archivo al nombre del archivo de imagen de la propiedad `ImagePath` y lo carga junto con `Label` en un objeto `ImageData`.

### <a name="create-a-method-to-make-a-prediction"></a>Creación de un método para hacer una predicción

1. Cree el método `ClassifySingleImage()`, justo antes del método `DisplayResults()`, mediante el código siguiente:

    ```csharp
    public static void ClassifySingleImage(MLContext mlContext, ITransformer model)
    {

    }
    ```

1. Cree un objeto `ImageData` que contenga la ruta de acceso completa y el nombre del archivo de imagen para la `ImagePath` única. Agregue el código siguiente como las siguientes líneas en el método `ClassifySingleImage()`:

    [!code-csharp[LoadImageData](./snippets/image-classification/csharp/Program.cs#LoadImageData)]

1. Para hacer una predicción única, agregue el código siguiente como la línea siguiente en el método `ClassifySingleImage`:

    [!code-csharp[PredictSingle](./snippets/image-classification/csharp/Program.cs#PredictSingle)]

    Para obtener la predicción, use el método [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A). [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) es una API de conveniencia, que le permite realizar una predicción en una única instancia de datos. [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) no es seguro para subprocesos. Es aceptable usarlo en entornos de un solo subproceso o prototipo. Para mejorar el rendimiento y la seguridad para subprocesos en entornos de producción, use el servicio `PredictionEnginePool`, que crea un [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) de objetos de [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) para su uso en toda la aplicación. Consulte esta guía sobre cómo [usar `PredictionEnginePool` en una API web de ASP.NET Core](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).

    > [!NOTE]
    > La extensión del servicio `PredictionEnginePool` está actualmente en versión preliminar.

1. Muestre el resultado de la predicción como la línea de código siguiente en el método `ClassifySingleImage()`:

   [!code-csharp[DisplayPrediction](./snippets/image-classification/csharp/Program.cs#DisplayPrediction)]

## <a name="construct-the-mlnet-model-pipeline"></a>Construcción de la canalización del modelo de ML.NET

Una canalización del modelo de ML.NET es una cadena de estimadores. Tenga en cuenta que no se produce ninguna ejecución durante la construcción de la canalización. Se crean los objetos del estimador, pero no se ejecutan.

1. Agregue un método para generar el modelo

    Este método es la parte central del tutorial. Crea una canalización para el modelo y entrena la canalización para generar el modelo de ML.NET. También evalúa el modelo con respecto a algunos datos de prueba previamente desconocidos.

    Cree el método `GenerateModel()` justo después de la estructura `InceptionSettings` y antes del método `DisplayResults()` con el código siguiente:

    ```csharp
    public static ITransformer GenerateModel(MLContext mlContext)
    {

    }
    ```

1. Agregue los estimadores para cargar, cambiar el tamaño y extraer los píxeles de los datos de la imagen:

    [!code-csharp[ImageTransforms](./snippets/image-classification/csharp/Program.cs#ImageTransforms)]

    Los datos de la imagen se deben procesar en el formato que el modelo de TensorFlow espera. En este caso, las imágenes se cargan en la memoria, se cambia el tamaño a un tamaño coherente y los píxeles se extraen en un vector numérico.

1. Agregue el estimador para cargar el modelo de TensorFlow y puntúelo:

    [!code-csharp[ScoreTensorFlowModel](./snippets/image-classification/csharp/Program.cs#ScoreTensorFlowModel)]

    Esta fase de la canalización carga el modelo de TensorFlow en la memoria y, a continuación, procesa el vector de valores de píxeles a través de la red del modelo de TensorFlow. La aplicación de entradas a un modelo de aprendizaje profundo y la generación de una salida mediante el modelo se conoce como **Puntuación**. Al utilizar el modelo en su totalidad, la puntuación hace una inferencia o predicción.

    En este caso, se usa todo el modelo de TensorFlow, excepto la última capa, que es la que realiza la inferencia. El resultado de la penúltima capa tiene la etiqueta `softmax_2_preactivation`. La salida de esta capa es, de hecho, un vector de las características que caracterizan las imágenes de entrada originales.

    Este vector de características generado por el modelo de TensorFlow se usará como entrada para un algoritmo de aprendizaje de ML.NET.

1. Agregue el estimador para asignar las etiquetas de cadena en los datos de entrenamiento a los valores de clave entera:

    [!code-csharp[MapValueToKey](./snippets/image-classification/csharp/Program.cs#MapValueToKey)]

    El entrenador de ML.NET que se anexa a continuación requiere que sus etiquetas estén en formato `key` en lugar de cadenas arbitrarias. Una clave es un número que tiene una asignación de uno a uno a un valor de cadena.

1. Agregue el algoritmo de aprendizaje de ML.NET:

    [!code-csharp[AddTrainer](./snippets/image-classification/csharp/Program.cs#AddTrainer)]

1. Agregue el estimador para asignar el valor de clave de predicción a una cadena:

    [!code-csharp[MapKeyToValue](./snippets/image-classification/csharp/Program.cs#MapKeyToValue)]

## <a name="train-the-model"></a>Entrenar el modelo

1. Cargue los datos de entrenamiento con el contenedor [LoadFromTextFile](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile(Microsoft.ML.DataOperationsCatalog,System.String,Microsoft.ML.Data.TextLoader.Options)). Agregue el siguiente código como la siguiente línea en el método `GenerateModel()`:

    [!code-csharp[LoadData](./snippets/image-classification/csharp/Program.cs#LoadData "Load the data")]

    Los datos de ML.NET se representan como una [clase IDataView](xref:Microsoft.ML.IDataView). `IDataView` es una manera flexible y eficiente de describir datos tabulares (numéricos y de texto). Los datos se pueden cargar desde un archivo de texto o en tiempo real (por ejemplo, archivos de registro o base de datos SQL) en un objeto `IDataView`.

1. Entrene el modelo con los datos cargados anteriormente:

    [!code-csharp[TrainModel](./snippets/image-classification/csharp/Program.cs#TrainModel)]

    El método `Fit()` entrena el modelo mediante la aplicación del conjunto de datos de entrenamiento a la canalización.

## <a name="evaluate-the-accuracy-of-the-model"></a>Evaluación de la precisión del modelo

1. Cargue y transforme los datos de prueba agregando el código siguiente a la siguiente línea del método `GenerateModel`:

    [!code-csharp[LoadAndTransformTestData](./snippets/image-classification/csharp/Program.cs#LoadAndTransformTestData "Load and transform test data")]

    Hay algunas imágenes de ejemplo que puede usar para evaluar el modelo. Al igual que los datos de entrenamiento, deben cargarse en `IDataView`, de modo que el modelo pueda transformarlos.

1. Agregue el código siguiente al método `GenerateModel()` para evaluar el modelo:

    [!code-csharp[Evaluate](./snippets/image-classification/csharp/Program.cs#Evaluate)]

    Una vez que establece la predicción, el método [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A):

    * Evalúa el modelo (compara los valores previstos con el conjunto de datos `labels` de prueba).
    * Devuelve las métricas de rendimiento del modelo.

1. Visualización de las métricas de precisión del modelo

    Utilice el código siguiente para mostrar las métricas, compartir los resultados y, a continuación, trabajar con ellos:

    [!code-csharp[DisplayMetrics](./snippets/image-classification/csharp/Program.cs#DisplayMetrics)]

    Las siguiente métricas se evalúan para la clasificación de imágenes:

    * `Log-loss`: consulte [Pérdida de registro](../resources/glossary.md#log-loss). Le recomendamos que la pérdida logarítmica esté lo más cerca posible de 0.
    * `Per class Log-loss`. Le recomendamos que la pérdida logarítmica por clase esté lo más cerca posible de 0.

1. Agregue el siguiente código para devolver el modelo entrenado, como la siguiente línea:

    [!code-csharp[SaveModel](./snippets/image-classification/csharp/Program.cs#ReturnModel)]

## <a name="run-the-application"></a>Ejecución de la aplicación

1. Agregue la llamada a `GenerateModel` en el método `Main` después de la creación de la clase MLContext:

    [!code-csharp[CallGenerateModel](./snippets/image-classification/csharp/Program.cs#CallGenerateModel)]

1. Agregue la llamada al método `ClassifySingleImage()` como la siguiente línea de código en el método `Main`:

    [!code-csharp[CallClassifySingleImage](./snippets/image-classification/csharp/Program.cs#CallClassifySingleImage)]

1. Ejecute la aplicación de consola (Ctrl + F5). Los resultados deberían ser similares a la salida siguiente.  Es posible que vea advertencias o mensajes de procesamiento, si bien se han quitado de los resultados siguientes para mayor claridad.

    ```console
    =============== Training classification model ===============
    Image: broccoli2.jpg predicted as: food with score: 0.8955513
    Image: pizza3.jpg predicted as: food with score: 0.9667718
    Image: teddy6.jpg predicted as: toy with score: 0.9797683
    =============== Classification metrics ===============
    LogLoss is: 0.0653774699265059
    PerClassLogLoss is: 0.110315812569315 , 0.0204391272836966 , 0
    =============== Making single image classification ===============
    Image: toaster3.jpg predicted as: appliance with score: 0.9646884
    ```

¡Enhorabuena! Ha creado correctamente un modelo de Machine Learning para la clasificación de imágenes al aplicar el aprendizaje de transferencia a un modelo de `TensorFlow` en ML.NET.

Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/main/machine-learning/tutorials/TransferLearningTF).

En este tutorial ha aprendido a:
> [!div class="checklist"]
>
> * Entender el problema
> * Incorporación del modelo de TensorFlow entrenado previamente en la canalización de ML.NET
> * Entrenamiento y evaluación del modelo de ML.NET
> * Clasificación de una imagen de prueba

Consulte el repositorio de GitHub con ejemplos de Machine Learning para explorar un ejemplo expandido de clasificación de imágenes.
> [!div class="nextstepaction"]
> [Repositorio dotnet/machinelearning-samples de GitHub](https://github.com/dotnet/machinelearning-samples/)
