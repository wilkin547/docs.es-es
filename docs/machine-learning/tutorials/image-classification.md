---
title: Creación de un clasificador de imágenes personalizado de ML.NET con TensorFlow
description: Descubra cómo crear un clasificador de imágenes personalizado de ML.NET en un escenario de aprendizaje por transferencia de TensorFlow para clasificar imágenes mediante la reutilización de un modelo entrenado previamente de TensorFlow.
ms.date: 04/05/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 9b9ac1f1f15b4003a19a3d30d6cadf3e86946376
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59517972"
---
# <a name="tutorial-build-an-mlnet-custom-image-classifier-with-tensorflow"></a>Tutorial: Creación de un clasificador de imágenes personalizado de ML.NET con TensorFlow

En este tutorial de ejemplo se ilustra cómo se puede usar un modelo `TensorFlow` de clasificador de imágenes ya entrenado para crear un nuevo modelo personalizado para clasificar imágenes en algunas categorías.

¿Qué pasaría si pudiera volver a usar un modelo que ya se entrenó previamente para resolver un problema similar y volver a entrenar la totalidad o algunas de las capas de ese modelo para que resuelva su problema? Esta técnica de volver a usar parte de un modelo ya entrenado para crear un modelo nuevo se conoce como [aprendizaje por transferencia](https://en.wikipedia.org/wiki/Transfer_learning).

Entrenar un modelo de [clasificación de imágenes](https://en.wikipedia.org/wiki/Outline_of_object_recognition) desde cero requiere establecer millones de parámetros, una enorme cantidad de datos de aprendizaje etiquetados y una gran cantidad de recursos informáticos (cientos de horas de GPU). Si bien no es tan eficaz como entrenar un modelo personalizado desde cero, el aprendizaje por transferencia permite acortar este proceso al trabajar con miles de imágenes frente a millones de imágenes etiquetadas y crear un modelo personalizado con bastante rapidez (menos de una hora en una máquina sin GPU).

En este tutorial aprenderá a:
> [!div class="checklist"]
> * Entender el problema
> * Volver a usar y ajustar el modelo entrenado previamente
> * Clasificar imágenes

> [!NOTE]
> Este tema hace referencia a ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios. Para obtener más información, visite [la introducción de ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Este tutorial y el ejemplo relacionado usan actualmente **ML.NET en su versión 0.10**. Para más información, consulte las notas de la versión en el repositorio [dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes) de GitHub.

## <a name="image-classification-sample-overview"></a>Información general del ejemplo de clasificación de imágenes

El ejemplo es una aplicación de consola que usa ML.NET para crear un clasificador de imágenes mediante la reutilización de un modelo entrenado previamente para clasificar imágenes con una pequeña cantidad de datos de aprendizaje.

Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF).

## <a name="prerequisites"></a>Requisitos previos

* [Visual Studio 2017 15.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.

* Paquete NuGet de Microsoft.ML 0.10.0
* Paquete NuGet de Microsoft.ML.ImageAnalytics 0.10.0
* Paquete NuGet de Microsoft.ML.TensorFlow 0.10.0

* [El archivo ZIP del directorio de recursos del tutorial](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip)

* [El modelo de Machine Learning de InceptionV3](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)

## <a name="select-the-appropriate-machine-learning-task"></a>Seleccionar la tarea de aprendizaje automático adecuada

El [aprendizaje profundo](https://en.wikipedia.org/wiki/Deep_learning) es un subconjunto de Machine Learning, que está revolucionando áreas como Computer Vision y reconocimiento de voz.

Los modelos de aprendizaje profundo se entrenan mediante el uso de grandes conjuntos de [datos etiquetados](https://en.wikipedia.org/wiki/Labeled_data) y [redes neuronales](https://en.wikipedia.org/wiki/Artificial_neural_network) que contienen varias capas de conocimiento. Aprendizaje profundo:

* Funciona mejor en algunas tareas como Computer Vision.

* Funciona bien con enormes cantidades de datos.

La clasificación de imágenes es una tarea de Machine Learning común que nos permite clasificar imágenes automáticamente en varias categorías, como:

* Detectar o no una cara humana en una imagen.
* Detectar gatos o perros.

 O bien, como en las imágenes siguientes, determinar si una imagen es un alimento, un juguete o un dispositivo:

![imagen de una pizza](./media/image-classification/220px-Pepperoni_pizza.jpg)
![imagen de un oso de peluche](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![imagen de una tostadora](./media/image-classification/193px-Broodrooster.jpg)

>[!Note]
> Las imágenes anteriores pertenecen a Wikimedia Commons y tienen los siguientes atributos:
>
> * "220px-Pepperoni_pizza.jpg" de dominio público, https://commons.wikimedia.org/w/index.php?curid=79505,
> * "119px-Nalle_-_a_small_brown_teddy_bear.jpg" de [Jonik](https://commons.wikimedia.org/wiki/User:Jonik), autofotografía, CC BY-SA 2.0, https://commons.wikimedia.org/w/index.php?curid=48166.
> * "193px-Broodrooster.jpg" de [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972), trabajo propio, CC BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=27403

El aprendizaje por transferencia incluye algunas estrategias como *volver a entrenar todas las capas* y *penúltima capa*. En este tutorial se explicará y se mostrará cómo usar la *estrategia de penúltima capa*. La *estrategia de penúltima capa* vuelve a usar un modelo entrenado previamente para resolver un problema específico. De ese modo, la estrategia vuelve a entrenar la capa final de ese modelo para que resuelva un problema nuevo. Volver a usar el modelo entrenado previamente como parte del modelo nuevo permitirá ahorrar mucho tiempo y recursos.

El modelo de clasificación de imágenes vuelve a usar el [modelo de inicio](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip), un popular modelo de reconocimiento de imágenes entrenado en el conjunto de datos `ImageNet`, donde el modelo de TensorFlow intenta clasificar imágenes enteras en miles de clases, como "Umbrella" (Paraguas), "Jersey" (Suéter) y "Dishwasher" (Lavavajillas).

`Inception v3 model` se puede clasificar como una [red neuronal convolucional profunda](https://en.wikipedia.org/wiki/Convolutional_neural_network) y puede lograr un rendimiento razonable en tareas difíciles de reconocimiento visual, ya sea igualando o superando el rendimiento humano en algunos dominios. El modelo/algoritmo lo desarrollaron varios investigadores basándose en la publicación original: ["Rethinking the Inception Architecture for Computer Vision” (Replanteamiento de la arquitectura de inicio para Computer Vision) de Szegedy, et. al.](https://arxiv.org/abs/1512.00567)

Como `Inception model` se entrenó previamente en miles de imágenes distintas, contiene las [características de imagen](https://en.wikipedia.org/wiki/Feature_(computer_vision)) necesarias para la identificación de imágenes. Las capas inferiores de las características de imagen reconocen características simples (como los bordes) y las capas superiores reconocen características más complejas (como las formas). La capa final se entrena con un conjunto de datos mucho más pequeño, porque se empieza con un modelo entrenado previamente que ya entiende cómo clasificar imágenes. Como el modelo permite clasificar más de dos categorías, se trata de un ejemplo de un [clasificador multiclase](../resources/tasks.md#multiclass-classification). 

`TensorFlow` es un popular kit de herramientas de aprendizaje profundo y aprendizaje automático que permite entrenar redes neuronales profundas (y cálculos numéricos generales) y se implementa como `transformer` en ML.NET. En este tutorial, se usa para reutilizar `Inception model`.

Como se muestra en el diagrama siguiente, puede agregar una referencia a los paquetes NuGet de ML.NET en las aplicaciones de .NET Core o .NET Framework. En segundo plano, ML.NET incluye y hace referencia a la biblioteca nativa de `TensorFlow` que permite escribir código que carga un archivo de modelo de `TensorFlow` entrenado existente para puntuación.  

![Diagrama de la arquitectura de ML.NET de transformación de TensorFlow](./media/image-classification/tensorflow-mlnet.png)

`Inception model` está entrenado para clasificar imágenes en miles de categorías, pero el usuario deberá clasificar las imágenes en un conjunto de categorías más pequeño y solo en esas categorías. Escriba la parte `transfer` de `transfer learning`. Puede transferir la capacidad que `Inception model` tiene para reconocer y clasificar imágenes a las nuevas categorías limitadas del clasificador personalizado de imágenes.  

 Va a volver a entrenar la capa final de ese modelo con un conjunto de tres categorías:

* Alimentos
* Juguetes
* Dispositivos

La capa usa un [algoritmo de regresión logística multinomial](https://en.wikipedia.org/wiki/Multinomial_logistic_regression) para encontrar la categoría correcta lo más rápido que sea posible. Este algoritmo clasifica el uso de probabilidades para determinar la respuesta, dándole un valor a la categoría correcta y un valor de cero a las demás.  

### <a name="dataset"></a>DataSet

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
> *[Wikimedia Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), el repositorio multimedia gratuito*. Recuperado a las 10:48 del 17 de octubre de 2018 desde:  
> https://commons.wikimedia.org/wiki/Pizza  
> https://commons.wikimedia.org/wiki/Toaster  
> https://commons.wikimedia.org/wiki/Teddy_bear  

## <a name="create-a-console-application"></a>Creación de una aplicación de consola

### <a name="create-a-project"></a>Crear un proyecto

1. Abra Visual Studio 2017. Seleccione **Archivo** > **Nuevo** > **Proyecto** de la barra de menús. En el cuadro de diálogo **Nuevo proyecto**, seleccione el nodo **Visual C#** seguido del nodo **.NET Core**. Después, seleccione la plantilla del proyecto **Aplicación de consola (.NET Core)**. En el cuadro de texto **Nombre**, escriba "TransferLearningTF" y seleccione el botón **Aceptar**.

2. Instale el **paquete NuGet Microsoft.ML**:

    En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**. Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar y busque **Microsoft.ML**. Haga clic en el menú desplegable **Versión**, seleccione el paquete **0.10.0** en la lista y, luego, el botón **Instalar**. Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados. Repita estos pasos para **Microsoft.ML.ImageAnalytics v0.10.0** y **Microsoft.ML.TensorFlow v0.10.0**.

  > [!NOTE]
  > En este tutorial se usa **Microsoft.ML v0.10.0**, **Microsoft.ML.ImageAnalytics v0.10.0** y **Microsoft.ML.TensorFlow v0.10.0**.

### <a name="prepare-your-data"></a>Preparar los datos

1. Descargue el [archivo ZIP del directorio de recursos del proyecto](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip) y descomprímalo.

2. Copie el directorio `assets` en el directorio de proyecto *TransferLearningTF*. Este directorio y sus subdirectorios contienen los datos y los archivos auxiliares (excepto los del modelo de inicio, que descargará y agregará en el paso siguiente) que se necesitan en este tutorial.

3. Descargue el [modelo de inicio](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) y descomprímalo.

4. Copie el contenido del directorio `inception5h` que acaba de descomprimir en el directorio `assets\inputs-train\inception` del proyecto *TransferLearningTF*. En este directorio está el modelo y los archivos auxiliares adicionales que se necesitan en este tutorial, tal como se muestra en la imagen siguiente:

   ![Contenido del directorio de inicio](./media/image-classification/inception-files.png)

5. En el Explorador de soluciones, haga clic con el botón derecho en cada uno de los archivos del directorio de recursos y los subdirectorios y seleccione **Propiedades**. En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.

### <a name="create-classes-and-define-paths"></a>Crear clases y definir rutas de acceso

Agregue las siguientes instrucciones `using` adicionales a la parte superior del archivo *Program.cs*:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddUsings)]

Cree campos globales para contener las rutas de acceso a los distintos recursos y variables globales para `LabelTokey`,`ImageReal` y `PredictedLabelValue`:

* `_assetsPath` tiene la ruta de acceso a los recursos.
* `_trainTagsTsv` tiene la ruta de acceso al archivo tsv de etiquetas de datos de imagen de entrenamiento.
* `_predictTagsTsv` tiene la ruta de acceso al archivo tsv de etiquetas de datos de imagen de predicción.
* `_trainImagesFolder` tiene la ruta de acceso a las imágenes que se usan para entrenar el modelo.
* `_predictImagesFolder` tiene la ruta de acceso a las imágenes que el modelo entrenado va a clasificar.
* `_inceptionPb` tiene la ruta de acceso al modelo de inicio entrenado previamente que se reutilizará para volver a entrenar el modelo.
* `_inputImageClassifierZip` tiene la ruta de acceso desde donde se carga el modelo de entrenamiento.
* `_outputImageClassifierZip` tiene la ruta de acceso donde se guarda el modelo entrenado.
* `LabelTokey` es el valor `Label` asignado a una clave.
* `ImageReal` es la columna que contiene el valor de imagen previsto.
* `PredictedLabelValue` es la columna que contiene el valor de etiqueta previsto.

Agregue el código siguiente a la línea justo encima del método `Main` para especificar esas rutas de acceso y otras variables:

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DeclareGlobalVariables)]

Cree algunas clases para los datos de entrada y predicciones. Agregue una nueva clase a su proyecto:

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.

1. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *ImageData.cs*. A continuación, seleccione el botón **Agregar**.

    El archivo *ImageData.cs* se abre en el editor de código. Agregue la instrucción `using` siguiente al principio del archivo *ImageData.cs*:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TransferLearningTF/ImageData.cs#AddUsings)]

Quite la definición de clase existente y agregue el código siguiente para la clase `ImageData` al archivo *ImageData.cs*:

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/TransferLearningTF/ImageData.cs#DeclareTypes)]

`ImageData` es la clase de datos de imagen de entrada y tiene los campos <xref:System.String> siguientes:

* `ImagePath` contiene el nombre del archivo de imagen.
* `Label` contiene un valor para la etiqueta de imagen.

Agregue una clase nueva al proyecto para `ImagePrediction`:

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.

1. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *ImagePrediction.cs*. A continuación, seleccione el botón **Agregar**.

    El archivo *ImagePrediction.cs* se abre en el editor de código. Quite las instrucciones `using` de `System.Collections.Generic` y de `System.Text` del inicio del archivo *ImagePrediction.cs*:

Quite la definición de clase existente y agregue el código siguiente, que tiene la clase `ImagePrediction`, al archivo *ImagePrediction.cs*:

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TransferLearningTF/ImagePrediction.cs#DeclareTypes)]

`ImagePrediction` es la clase de predicción de imagen y tiene los campos siguientes:

* `Score` contiene el porcentaje de confianza de una clasificación de imágenes determinada.
* `PredictedLabelValue` contiene un valor para la etiqueta de clasificación de imágenes prevista.

`ImagePrediction` es la clase usada para la predicción una vez entrenado el modelo. Tiene una `string` (`ImagePath`) para la ruta de acceso a la imagen. `Label` se usa para reutilizar y volver a entrenar el modelo. `PredictedLabelValue` se usa durante la predicción y la evaluación. Para la evaluación, se utiliza una entrada con los datos de entrenamiento, los valores de predicción y el modelo.

La [clase MLContext](xref:Microsoft.ML.MLContext) es un punto de partida para todas las operaciones de ML.NET. Al inicializar `mlContext`, se crea un entorno de ML.NET que se puede compartir entre los objetos del flujo de trabajo de creación de modelos. Como concepto, se parece a `DBContext` en Entity Framework.

### <a name="initialize-variables-in-main"></a>Inicializar variables en Main

Inicialice la variable `mlContext` con una instancia nueva de `MLContext`.  Reemplace la línea `Console.WriteLine("Hello World!")` por el código siguiente en el método `Main`:

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CreateMLContext)]

### <a name="create-a-struct-for-default-parameters"></a>Crear una estructura para parámetros predeterminados

El modelo de inicio tiene varios parámetros predeterminados que se deben transmitir. Cree una estructura para asignar los valores de parámetros predeterminados a nombres descriptivos con el código siguiente, justo después del método `Main()`:

[!code-csharp[InceptionSettings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#InceptionSettings)]

### <a name="create-a-display-utility-method"></a>Crear un método de utilidad para mostrar

Empareje y visualice los datos de imagen y las predicciones relacionadas más de una vez y no querrá duplicar el código. Cree un método de utilidad para mostrar que controle el emparejamiento y la visualización de la imagen y los resultados de la predicción.

El método `PairAndDisplayResults()` ejecuta las tareas siguientes:

* Combina datos y predicciones para crear informes.
* Muestra los resultados de la predicción.

Cree el método `PairAndDisplayResults()` justo después de la estructura `InceptionSettings` con el código siguiente:

```csharp
private static void PairAndDisplayResults(IEnumerable<ImageNetData> imageData, IEnumerable<ImageNetPrediction> imagePredictionData)
{

}
```

Antes de mostrar los resultados previstos, combine `imageData` y `imagePrediction` para ver la `Image Path` original con su categoría prevista. Para ello, el código siguiente usa el método <xref:System.Linq.Enumerable.Zip%2A?displayProperty=nameWithType>, por lo que debe agregarlo como la primera línea del método `PairAndDisplayResults()`:

[!code-csharp[BuildImagePredictionPairs](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#BuildImagePredictionPairs)]

Ahora que ha combinado `imageData` y `imageData` en una clase, puede mostrar los resultados utilizando el método <xref:System.Console.WriteLine?displayProperty=nameWithType>:

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPredictions)]

Llamará al método `PairAndDisplayResults()` en los dos siguientes métodos.

### <a name="create-a-tsv-file-utility-method"></a>Crear un método de utilidad de archivo .tsv

El método `ReadFromTsv()` ejecuta las tareas siguientes:

* Lee el archivo `tags.tsv` de datos de imagen.
* Agrega la ruta de acceso al archivo al nombre del archivo de imagen.
* Carga los datos de archivo en un objeto IEnumerable`ImageData`.

Cree el método `ReadFromTsv()`, justo después del método `PairAndDisplayResults()`, mediante el código siguiente:

```csharp
public static IEnumerable<ImageData> ReadFromTsv(string file, string folder)
{

}
```

El código siguiente analiza el archivo `tags.tsv` para agregar la ruta de acceso al archivo al nombre del archivo de imagen de la propiedad `ImagePath` y lo carga junto con `Label` en un objeto `ImageData`. Agréguelo como la primera línea del método `ReadFromTsv()`.  Necesita la ruta de acceso al archivo completo para mostrar los resultados de la predicción.

[!code-csharp[ReadFromTsv](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReadFromTsv)]
En ML.NET hay tres conceptos principales: [Data](../basic-concepts-model-training-in-mldotnet.md#data) (datos), [Transformers](../basic-concepts-model-training-in-mldotnet.md#transformer) (transformadores) y [Estimators](../basic-concepts-model-training-in-mldotnet.md#estimator) (estimadores).

## <a name="reuse-and-tune-pre-trained-model"></a>Volver a usar y ajustar el modelo entrenado previamente

Agregue la siguiente llamada al método `ReuseAndTuneInceptionModel()` como siguiente línea de código del método `Main()`:

[!code-csharp[CallReuseAndTuneInceptionModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallReuseAndTuneInceptionModel)]

El método `ReuseAndTuneInceptionModel()` ejecuta las tareas siguientes:

* Carga los datos.
* Extrae y transforma los datos.
* Asigna una puntuación al modelo de TensorFlow.
* Ajusta (vuelve a entrenar) el modelo.
* Muestra los resultados del modelo.
* Evalúa el modelo.
* Guarda el modelo.

Cree el método `ReuseAndTuneInceptionModel()` justo después de la estructura `InceptionSettings` y antes del método `PairAndDisplayResults()` con el código siguiente:

```csharp
public static void ReuseAndTuneInceptionModel(MLContext mlContext, string dataLocation, string imagesFolder, string inputModelLocation, string outputModelLocation)
{

}
```

### <a name="load-the-data"></a>Carga de los datos

Los datos de ML.NET se representan como una [clase IDataView](xref:Microsoft.Data.DataView.IDataView). `IDataView` es una manera flexible y eficiente de describir datos tabulares (numéricos y de texto). Los datos se pueden cargar desde un archivo de texto o en tiempo real (por ejemplo, archivos de registro o base de datos SQL) en un objeto `IDataView`.

Cargue los datos con el contenedor `MLContext.Data.ReadFromTextFile`. Agregue el siguiente código como la siguiente línea en el método `ReuseAndTuneInceptionModel()`:

[!code-csharp[LoadData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadData "Load the data")]

### <a name="extract-features-and-transform-the-data"></a>Extraer características y transformar los datos

El procesamiento previo y la limpieza de datos son tareas importantes que se producen antes de que un conjunto de datos se utilice de forma eficaz para el aprendizaje automático.  El uso de datos sin estas tareas de modelado puede producir resultados engañosos.

Los algoritmos de aprendizaje automático entienden los datos [caracterizados](../resources/glossary.md#feature) y, cuando trabaje con redes neuronales profundas, deberá adaptar las imágenes al formato que espera la red. Ese formato es un [vector numérico](../resources/glossary.md#numerical-feature-vector).

Después del entrenamiento y la evaluación, prediga con los valores de la columna **Etiqueta**. A medida que usa un modelo entrenado previamente, asigne los campos al nuevo modelo con el método [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A). Este método transforma `Label` en una columna de tipo de clave numérica (`LabelTokey`) y la agrega como una columna de conjunto de datos nueva:  Asígnele el nombre `estimator`, porque también le agregará el instructor. Agregue esta línea de código:

[!code-csharp[MapValueToKey1](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapValueToKey1)]

El estimador de procesamiento de imágenes usa los caracterizadores de [red neuronal profunda (DNN)](https://en.wikipedia.org/wiki/Deep_learning#Deep_neural_networks) entrenados previamente para extraer las características. Cuando trabaje con redes neuronales profundas, puede adaptar las imágenes al formato de red esperado. Este es el motivo por el que usa varias transformaciones de imágenes a fin de colocar los datos de imagen en el formato esperado del modelo:

1. Las imágenes de la transformación `LoadImages` se cargan en memoria como un tipo de mapa de bits.
2. La transformación `Resize` cambia el tamaño de las imágenes porque el modelo entrenado previamente tiene definido el alto y el ancho de las imágenes de entrada.
3. La transformación `ImagePixelExtractingEstimator` extrae los píxeles de las imágenes de entrada y las convierte en un vector numérico.

Agregue estas transformaciones de imágenes como las líneas de código siguientes:

[!code-csharp[ImageTransforms](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ImageTransforms)]

`TensorFlowTransform` extrae salidas especificadas (la `softmax2_pre_activation` de las características de imagen de `Inception model`) y asigna una puntuación al conjunto de datos con el modelo `TensorFlow` entrenado previamente.

`softmax2_pre_activation` ayuda al modelo al determinar a qué clase pertenecen las imágenes. `softmax2_pre_activation` devuelve una probabilidad para cada una de las categorías de una imagen y la suma de todas esas probabilidades debe ser 1. Se supone que una imagen pertenecerá solo a una categoría, tal como se muestra en el ejemplo siguiente:

| Clase         | Probabilidad   |
| ------------- | ------------- |
| `Food`        |  0,001        |
| `Toy`         |  0,95         |
| `Appliance`   |  0,06         |

Anexe `TensorFlowTransform` al `estimator` con la línea de código siguiente:

[!code-csharp[ScoreTensorFlowModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ScoreTensorFlowModel)]

### <a name="choose-a-training-algorithm"></a>Elija un algoritmo de entrenamiento

Para agregar el algoritmo de entrenamiento, llame al método contenedor `mlContext.MulticlassClassification.Trainers.LogisticRegression()`.  `LogisticRegression` se anexa a `estimator` y acepta las características de imagen de inicio (`softmax2_pre_activation`) y los parámetros de entrada `Label` para aprender de los datos históricos.  Agregue el instructor con el código siguiente:

[!code-csharp[AddTrainer](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddTrainer)]

También deberá asignar `predictedlabel` al `predictedlabelvalue`:

[!code-csharp[MapValueToKey2](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapValueToKey2)]

El método `Fit()` entrena el modelo con el conjunto de datos de entrenamiento proporcionado. Ejecuta las definiciones de `Estimator`, para lo que transforma los datos y aplica el entrenamiento, y devuelve el modelo entrenado, que es un `Transformer`. Ajuste el modelo a los datos `Train` y devuelva el modelo entrenado. Para ello, agregue lo que se indica a continuación como la siguiente línea de código en el método `ReuseAndTuneInceptionModel()`:

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#TrainModel)]

El método [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) realiza predicciones para varias filas de entrada proporcionadas de un conjunto de datos de prueba.  Transforme los datos `Training` mediante la adición del código siguiente a `ReuseAndTuneInceptionModel()`:

[!code-csharp[TransformData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#TransformData)]

Convierta las `DataViews` de predicción y los datos de imagen en `IEnumerables` fuertemente tipados para emparejar y facilitar la visualización. Para ello, use el método `MLContext.CreateEnumerable()` y el código siguiente:

[!code-csharp[EnumerateDataViews](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#EnumerateDataViews)]

Llame al método `PairAndDisplayResults()` para emparejar y mostrar los datos y las predicciones como la línea siguiente del método `ReuseAndTuneInceptionModel()`:

[!code-csharp[CallPairAndDisplayResults1](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallPairAndDisplayResults1)]

Una vez que establece la predicción, el método [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A):

* Evalúa el modelo (compara los valores previstos con el conjunto de datos `Labels` real).

* Devuelve las métricas de rendimiento del modelo. 

Agregue el código siguiente al método `ReuseAndTuneInceptionModel()` como la siguiente línea:

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#Evaluate)]

Las siguiente métricas se evalúan para la clasificación de imágenes:

* `Log-loss`: consulte [Pérdida de registro](../resources/glossary.md#log-loss). Le recomendamos que la pérdida logarítmica esté lo más cerca posible de 0.

* `Per class Log-loss`. Le recomendamos que la pérdida logarítmica por clase esté lo más cerca posible de 0.

Utilice el código siguiente para mostrar las métricas, compartir los resultados y, a continuación, trabajar con ellos:

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayMetrics)]

`mlContext.Model.Save` guarda el modelo entrenado en un archivo ZIP (en la carpeta "assets/outputs") que después puede usarse en otras aplicaciones de .NET para realizar predicciones. Agregue el código siguiente al método `ReuseAndTuneInceptionModel()` como la siguiente línea:

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#SaveModel)]

## <a name="classify-images-with-a-loaded-model"></a>Clasifique imágenes con un modelo cargado

Agregue la siguiente llamada al método `ClassifyImages()` como la siguiente línea de código del método `Main`:

[!code-csharp[CallClassifyImages](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallClassifyImages)]

El método `ClassifyImages()` ejecuta las tareas siguientes:

* Carga el modelo.
* Lee el archivo .TSV en `IEnumerable`.
* Predice las clasificaciones de imágenes en función de los datos de prueba.

Cree el método `ClassifyImages()`, justo después del método `ReuseAndTuneInceptionModel()` y antes del método `PairAndDisplayResults()` con el código siguiente:

```csharp
public static void ClassifyImages(MLContext mlContext, string dataLocation, string imagesFolder, string outputModelLocation)
{

}
```

En primer lugar, cargue el modelo que ha guardado anteriormente con el siguiente código:

[!code-csharp[LoadModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadModel)]

Llame al método `ReadFromTsv()` para crear una clase `IEnumerable<ImageData>` que contenga la ruta de acceso completa de cada `ImagePath`. Esta ruta de acceso a archivo es necesaria para emparejar los datos y los resultados de la predicción. También deberá convertir la clase `IEnumerable<ImageData>` en una `IDataView` que usará para realizar predicciones. Agregue el código siguiente como las próximas dos líneas del método `ClassifyImages()`:

[!code-csharp[ReadFromTSV](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReadFromTSV)]

Tal como hizo anteriormente con los datos de imagen de entrenamiento, prediga la categoría de los datos de imagen de prueba con el método [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A). Agregue el código siguiente al método `ClassifyImages()` para las predicciones y para convertir la `IDataView` de `predictions` en `IEnumerable` para el emparejamiento y la visualización:

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#Predict)]

Para emparejar y mostrar los datos de imagen de prueba y las predicciones, agregue el código siguiente para llamar al método `PairAndDisplayResults()` creado anteriormente como la línea siguiente del método `ClassifyImages()`:

[!code-csharp[CallPairAndDisplayResults2](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallPairAndDisplayResults2)]

## <a name="classify-a-single-image-with-a-loaded-model"></a>Clasifique una imagen única con un modelo cargado

Agregue la siguiente llamada al método `ClassifySingleImage()` como la siguiente línea de código del método `Main`:

[!code-csharp[CallClassifySingleImage](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallClassifySingleImage)]

El método `ClassifyImages()` ejecuta las tareas siguientes:

* Carga el modelo.
* Carga una instancia de `ImageData`.
* Predice la clasificación de imágenes en función de los datos de prueba.

Cree el método `ClassifySingleImage()` justo después del método `ClassifyImages()` y antes del método `PairAndDisplayResults()` con el código siguiente:

```csharp
public static void ClassifySingleImage(MLContext mlContext, string imagePath, string outputModelLocation)
{

}
```

En primer lugar, cargue el modelo que ha guardado anteriormente con el siguiente código:

[!code-csharp[LoadModel2](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadModel2)]

Cree una clase `ImageData` que contenga la ruta de acceso completa y el nombre del archivo de imagen para la `ImagePath` única. Agregue el código siguiente como las siguientes líneas en el método `ClassifySingleImage()`:

[!code-csharp[LoadImageData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadImageData)]

La [clase PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) es una API de conveniencia que realiza una predicción en una instancia única de datos. La función [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) realiza una predicción en una sola columna de datos. Pase `imageData` a `PredictionEngine` para predecir la categoría de imagen al agregar el código siguiente a `ClassifySingleImage()`:

[!code-csharp[PredictSingle](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#PredictSingle)]

Muestre el resultado de la predicción como la línea de código siguiente en el método `ClassifySingleImage()`:

[!code-csharp[DisplayPrediction](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPrediction)]

## <a name="results"></a>Resultados

Después de seguir los pasos anteriores, ejecute la aplicación de consola (Ctrl + F5). Los resultados deberían ser similares a la salida siguiente.  Es posible que vea advertencias o mensajes de procesamiento, si bien se han quitado de los resultados siguientes para mayor claridad.

```console
=============== Training classification model ===============
Image: broccoli.jpg predicted as: food with score: 0.976743
Image: pizza.jpg predicted as: food with score: 0.9751652
Image: pizza2.jpg predicted as: food with score: 0.9660203
Image: teddy2.jpg predicted as: toy with score: 0.9748783
Image: teddy3.jpg predicted as: toy with score: 0.9829691
Image: teddy4.jpg predicted as: toy with score: 0.9868168
Image: toaster.jpg predicted as: appliance with score: 0.9769174
Image: toaster2.png predicted as: appliance with score: 0.9800823
=============== Classification metrics ===============
LogLoss is: 0.0228266745633507
PerClassLogLoss is: 0.0277501705149937 , 0.0186303530571291 , 0.0217359128952187
=============== Save model to local file ===============
Model saved: C:\Tutorials\TransferLearningTF\bin\Debug\netcoreapp2.2\assets\outputs\imageClassifier.zip
=============== Loading model ===============
Model loaded: C:\Tutorials\TransferLearningTF\bin\Debug\netcoreapp2.2\assets\outputs\imageClassifier.zip
=============== Making classifications ===============
Image: broccoli.png predicted as: food with score: 0.905548
Image: pizza3.jpg predicted as: food with score: 0.9709008
Image: teddy6.jpg predicted as: toy with score: 0.9750155
=============== Loading model ===============
Model loaded: C:\Tutorials\TransferLearningTF\bin\Debug\netcoreapp2.2\assets\outputs\imageClassifier.zip
=============== Making single image classification ===============
Image: toaster3.jpg predicted as: appliance with score: 0.9625379
Press any key to continue . . .
```

¡Enhorabuena! Ha creado correctamente un modelo de Machine Learning para la clasificación de imágenes al reutilizar un modelo de `TensorFlow` entrenado previamente en ML.NET.

Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF).

En este tutorial ha aprendido a:
> [!div class="checklist"]
> * Entender el problema
> * Volver a usar y ajustar el modelo entrenado previamente
> * Clasifique imágenes con un modelo cargado

Consulte el repositorio de GitHub con ejemplos de Machine Learning para explorar un ejemplo expandido de clasificación de imágenes.
> [!div class="nextstepaction"]
> [Repositorio dotnet/machinelearning-samples de GitHub](https://github.com/dotnet/machinelearning-samples/)
