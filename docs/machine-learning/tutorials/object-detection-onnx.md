---
title: 'Tutorial: Detección de objetos mediante un modelo de aprendizaje profundo de ONNX'
description: En este tutorial se muestra cómo usar en ML.NET un modelo de aprendizaje profundo de ONNX entrenado previamente para detectar objetos en imágenes.
author: luisquintanilla
ms.author: luquinta
ms.date: 06/30/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 305a440634120395dba6881584b2ff46646da211
ms.sourcegitcommit: 1dbe25ff484a02025d5c34146e517c236f7161fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "104653587"
---
# <a name="tutorial-detect-objects-using-onnx-in-mlnet"></a>Tutorial: Detección de objetos con ONNX en ML.NET

Aprenda a usar en ML.NET un modelo ONNX previamente entrenado para detectar objetos en imágenes.

Entrenar un modelo de detección de objetos desde cero requiere establecer millones de parámetros, una enorme cantidad de datos de aprendizaje etiquetados y una gran cantidad de recursos informáticos (cientos de horas de GPU). El uso de un modelo entrenado previamente le permite abreviar el proceso de entrenamiento.

En este tutorial aprenderá a:
> [!div class="checklist"]
>
> - Entender el problema
> - Conocer qué es ONNX y cómo funciona con ML.NET
> - Entender el modelo
> - Volver a usar el modelo entrenado previamente
> - Detectar objetos con un modelo cargado

## <a name="pre-requisites"></a>Requisitos previos

- [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o posterior, o bien Visual Studio 2017 versión 15.6 o posterior con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.
- [Paquete NuGet de Microsoft.ML](https://www.nuget.org/packages/Microsoft.ML/)
- [Paquete NuGet de Microsoft.ML.ImageAnalytics](https://www.nuget.org/packages/Microsoft.ML.ImageAnalytics/)
- [Paquete NuGet de Microsoft.ML.OnnxTransformer](https://www.nuget.org/packages/Microsoft.ML.OnnxTransformer/)
- [Modelo previamente entrenado de Tiny YOLOv2](https://github.com/onnx/models/tree/master/vision/object_detection_segmentation/tiny-yolov2)
- [Netron](https://github.com/lutzroeder/netron) (opcional)

## <a name="onnx-object-detection-sample-overview"></a>Información general del ejemplo de detección de objetos de ONNX

En este ejemplo se crea una aplicación de consola de .NET Core que detecta objetos dentro de una imagen mediante un modelo de aprendizaje profundo de ONNX previamente entrenado. El código de este ejemplo se puede encontrar en el [repositorio dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/main/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx) en GitHub.

## <a name="what-is-object-detection"></a>¿Qué es la detección de objetos?

La detección de objetos es un problema de visión informática. Si bien está estrechamente relacionada con la clasificación de imágenes, la detección de objetos realiza la clasificación de imágenes a una escala más granular. La detección de objetos ubica _y_ categoriza entidades dentro de las imágenes. Use la detección de objetos cuando las imágenes contengan varios objetos de tipos diferentes.

![Capturas de pantalla en las que se muestran las diferencias entre la clasificación de imágenes y la clasificación de objetos.](./media/object-detection-onnx/img-classification-obj-detection.png)

Entre algunos casos de uso para la detección de objetos se incluyen:

- Automóviles sin conductor
- Robótica
- Detección facial
- Seguridad en el lugar de trabajo
- Recuento de objetos
- Reconocimiento de actividades

## <a name="select-a-deep-learning-model"></a>Selección de un modelo de aprendizaje profundo

El aprendizaje profundo es un subconjunto del aprendizaje automático. Para entrenar modelos de aprendizaje profundo, se necesitan grandes cantidades de datos. Los patrones de los datos se representan mediante una serie de capas. Las relaciones de los datos se codifican como conexiones entre las capas, que contienen ponderaciones. Cuanto mayor sea la ponderación, más fuerte será la relación. En conjunto, esta serie de capas y conexiones se conocen como redes neuronales artificiales. Cuantas más capas haya en una red, "más profunda" será, lo que la convierte en una red neuronal profunda.

Hay diferentes tipos de redes neuronales, las más comunes son perceptrón multicapa (MLP), red neuronal circunvolucional (CNN) y red neuronal recurrente (RNN). La más básica es MLP, que asigna un conjunto de entradas a un conjunto de salidas. Esta red neuronal es la adecuada cuando los datos no tienen un componente espacial ni temporal. CNN aprovecha las capas circunvolucionales para procesar la información espacial contenida en los datos. Un buen caso de uso de las CNN es el procesamiento de imágenes para detectar la presencia de una característica en una región de una imagen (por ejemplo, ¿hay una nariz en el centro de una imagen?). Por último, las RNN permiten la persistencia del estado o la memoria que se va a usar como entrada. Las RNN se usan para el análisis de series temporales, donde la ordenación secuencial y el contexto de eventos son importantes.

### <a name="understand-the-model"></a>Entender el modelo

La detección de objetos es una tarea de procesamiento de imágenes. Por lo tanto, la mayoría de los modelos de aprendizaje profundo entrenados para solucionar este problema son CNN. El modelo que se usa en este tutorial es el Tiny YOLOv2, una versión más compacta del modelo YOLOv2 que se describe en el documento: ["YOLO9000: Better, Faster, Stronger" de Redmon y Farhadi](https://arxiv.org/pdf/1612.08242.pdf). Tiny YOLOv2 se entrena en el conjunto de datos Pascal VOC y se compone de 15 capas que pueden predecir 20 clases diferentes de objetos. Dado que Tiny YOLOv2 es una versión comprimida del modelo YOLOv2 original, se logra velocidad a cambio de precisión. Los diferentes niveles que componen el modelo se pueden visualizar mediante herramientas como Netron. Al inspeccionar el modelo, se produciría una asignación de las conexiones entre todas las capas que componen la red neuronal, donde cada capa contendría el nombre de la capa, junto con las dimensiones de la entrada y la salida correspondientes. Las estructuras de datos que se usan para describir las entradas y salidas del modelo se conocen como tensores. Los tensores se pueden considerar como contenedores que almacenan datos en N dimensiones. En el caso de Tiny YOLOv2, el nombre de la capa de entrada es `image` y espera un tensor de dimensiones `3 x 416 x 416`. El nombre de la capa de salida es `grid` y genera un tensor de salida de dimensiones `125 x 13 x 13`.

![Capa de entrada dividida en capas ocultas y, luego, la capa de salida](./media/object-detection-onnx/netron-model-map-layers.png)

El modelo YOLO toma una imagen `3(RGB) x 416px x 416px`. El modelo toma esta entrada y la pasa a través de las diferentes capas para generar una salida. El resultado divide la imagen de entrada en una cuadrícula de `13 x 13`, y cada celda de la cuadrícula consta de `125` valores.

### <a name="what-is-an-onnx-model"></a>¿Qué es un modelo de ONNX?

Open Neural Network Exchange (ONNX) es un formato de código abierto para los modelos de IA. ONNX admite la interoperabilidad entre marcos. Esto significa que puede entrenar un modelo en uno de los muchos marcos de aprendizaje automático populares, como PyTorch, convertirlo en formato ONNX y consumir el modelo ONNX en otro marco, como ML.NET. Para más información, visite el [sitio web de ONNX](https://onnx.ai/).

![Diagrama de los formatos de ONNX admitidos en uso.](./media/object-detection-onnx/onnx-supported-formats.png)

El modelo Tiny YOLOv2 entrenado previamente se almacena en formato ONNX, una representación serializada de las capas y los patrones aprendidos de esas capas. En ML.NET, la interoperabilidad con ONNX se logra con los paquetes NuGet [`ImageAnalytics`](xref:Microsoft.ML.Transforms.Image) y [`OnnxTransformer`](xref:Microsoft.ML.Transforms.Onnx.OnnxTransformer). El paquete [`ImageAnalytics`](xref:Microsoft.ML.Transforms.Image) contiene una serie de transformaciones que toman una imagen y la codifican en valores numéricos que se pueden usar como entrada en una canalización de entrenamiento o de predicción. El paquete [`OnnxTransformer`](xref:Microsoft.ML.Transforms.Onnx.OnnxTransformer) aprovecha el tiempo de ejecución de ONNX para cargar un modelo de ONNX y usarlo para hacer predicciones basadas en la entrada proporcionada.

![Flujo de datos del archivo ONNX en el tiempo de ejecución de ONNX.](./media/object-detection-onnx/onnx-ml-net-integration.png)

## <a name="set-up-the-net-core-project"></a>Configurar el proyecto de .NET Core

Ahora que tiene un conocimiento general de lo que es ONNX y de cómo funciona Tiny YOLOv2, es el momento de compilar la aplicación.

### <a name="create-a-console-application"></a>Creación de una aplicación de consola

1. Cree una **aplicación de consola de .NET Core** denominada "ObjectDetection".

1. Instale el **paquete NuGet Microsoft.ML**:

    [!INCLUDE [mlnet-current-nuget-version](../../../includes/mlnet-current-nuget-version.md)]

    - En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.
    - Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar y busque **Microsoft.ML**.
    - Seleccione el botón **Instalar**.
    - Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.
    - Repita estos pasos para **Microsoft.ML.ImageAnalytics**, **Microsoft.ML.OnnxTransformer** y **Microsoft.ML.OnnxRuntime**.

### <a name="prepare-your-data-and-pre-trained-model"></a>Preparar los datos y el modelo entrenado previamente

1. Descargue el [archivo ZIP del directorio de recursos del proyecto](https://github.com/dotnet/machinelearning-samples/raw/main/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/assets.zip) y descomprímalo.

1. Copie el directorio `assets` en el directorio de proyecto *ObjectDetection*. Este directorio y sus subdirectorios contienen los archivos de imagen (excepto los del modelo de Tiny YOLOv2, que descargará y agregará en el paso siguiente) que se necesitan en este tutorial.

1. Descargue el [modelo de Tiny YOLOv2](https://onnxzoo.blob.core.windows.net/models/opset_8/tiny_yolov2/tiny_yolov2.tar.gz) de [ONNX Model Zoo](https://github.com/onnx/models/tree/master/vision/object_detection_segmentation/tiny-yolov2) y descomprímalo.

    Abra el símbolo del sistema y escriba el comando siguiente:

    ```shell
    tar -xvzf tiny_yolov2.tar.gz
    ```

1. Copie el archivo `model.onnx` extraído del directorio que acaba de descomprimir en el directorio `assets\Model` del proyecto *ObjectDetection* y cambie su nombre a `TinyYolo2_model.onnx`. Este directorio contiene el modelo necesario para este tutorial.

1. En el Explorador de soluciones, haga clic con el botón derecho en cada uno de los archivos del directorio de recursos y los subdirectorios y seleccione **Propiedades**. En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.

### <a name="create-classes-and-define-paths"></a>Crear clases y definir rutas de acceso

Abra el archivo *Program.cs* y agregue las instrucciones `using` adicionales siguientes a la parte superior del archivo:

[!code-csharp [ProgramUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L1-L7)]

A continuación, defina las rutas de acceso de los distintos recursos.

1. En primer lugar, agregue el método `GetAbsolutePath` debajo del método `Main` en la clase `Program`.

    [!code-csharp [GetAbsolutePath](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L66-L74)]

1. Después, dentro del método `Main`, cree campos para almacenar la ubicación de los recursos.

    [!code-csharp [AssetDefinition](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L17-L21)]

Agregue un nuevo directorio al proyecto para almacenar los datos de entrada y las clases de predicción.

En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, luego, seleccione **Agregar** > **Nueva carpeta**. Cuando la nueva carpeta aparezca en el Explorador de soluciones, asígnele el nombre "DataStructures".

Cree la clase de datos de entrada en el directorio *DataStructures* recién creado.

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el directorio *DataStructures* y luego seleccione **Agregar** > **Nuevo elemento**.
1. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *ImageNetData.cs*. A continuación, seleccione el botón **Agregar**.

    El archivo *ImageNetData.cs* se abre en el editor de código. Agregue la instrucción `using` siguiente al principio del archivo *ImageNetData.cs*:

    [!code-csharp [ImageNetDataUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/DataStructures/ImageNetData.cs#L1-L4)]

    Quite la definición de clase existente y agregue el código siguiente para la clase `ImageNetData` al archivo *ImageNetData.cs*:

    [!code-csharp [ImageNetDataClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/DataStructures/ImageNetData.cs#L8-L23)]

    `ImageNetData` es la clase de datos de imagen de entrada y tiene los campos <xref:System.String> siguientes:

    - `ImagePath` contiene la ruta de acceso donde se almacena la imagen.
    - `Label` contiene el nombre del archivo.

    Además, `ImageNetData` contiene un método `ReadFromFile` que carga varios archivos de imagen almacenados en la ruta `imageFolder` especificada y los devuelve como una colección de objetos `ImageNetData`.

Cree la clase de predicción en el directorio *DataStructures*.

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el directorio *DataStructures* y luego seleccione **Agregar** > **Nuevo elemento**.
1. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *ImageNetPrediction.cs*. A continuación, seleccione el botón **Agregar**.

    El archivo *ImageNetPrediction.cs* se abre en el editor de código. Agregue la instrucción `using` siguiente al principio del archivo *ImageNetPrediction.cs*:

    [!code-csharp [ImageNetPredictionUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/DataStructures/ImageNetPrediction.cs#L1)]

    Quite la definición de clase existente y agregue el código siguiente para la clase `ImageNetPrediction` al archivo *ImageNetPrediction.cs*:

    [!code-csharp [ImageNetPredictionClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/DataStructures/ImageNetPrediction.cs#L5-L9)]

    `ImageNetPrediction` es la clase de datos de predicción y tiene el campo `float[]` siguiente:

    - `PredictedLabel` contiene las dimensiones, la puntuación de calidad de objeto y las probabilidades de clase para cada uno de los cuadros de límite detectados en una imagen.

### <a name="initialize-variables-in-main"></a>Inicializar variables en Main

La [clase MLContext](xref:Microsoft.ML.MLContext) es un punto de partida para todas las operaciones de ML.NET. Al inicializar `mlContext`, se crea un entorno de ML.NET que se puede compartir entre los objetos del flujo de trabajo de creación de modelos. Como concepto, se parece a `DBContext` en Entity Framework.

Inicialice la variable `mlContext` con una nueva instancia de `MLContext` al agregar la siguiente línea al método `Main` de *Program.cs* debajo del campo `outputFolder`.

[!code-csharp [InitMLContext](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L24)]

## <a name="create-a-parser-to-post-process-model-outputs"></a>Crear un analizador para el procesamiento posterior de las salidas del modelo

El modelo segmenta una imagen en una cuadrícula `13 x 13`, donde cada celda de la cuadrícula mide `32px x 32px`. Cada celda de la cuadrícula contiene 5 rectángulos delimitadores de objeto posibles. Un rectángulo delimitador tiene 25 elementos:

![Ejemplo de cuadrícula a la izquierda y ejemplo de rectángulo delimitador a la derecha](./media/object-detection-onnx/model-output-description.png)

- `x`, posición x del centro del rectángulo delimitador relativo a la celda de la cuadrícula a la que está asociada.
- `y`, posición y del centro del rectángulo delimitador relativo a la celda de la cuadrícula a la que está asociada.
- `w`, ancho del rectángulo delimitador.
- `h`, altura del rectángulo delimitador.
- `o`, valor de confianza de que existe un objeto dentro del rectángulo delimitador, también conocido como puntuación de calidad de objeto.
- `p1-p20`, probabilidades de clase para cada una de las 20 clases previstas por el modelo.

En total, los 25 elementos que describen cada uno de los 5 rectángulos delimitadores constituyen los 125 elementos contenidos en cada celda de la cuadrícula.

La salida generada por el modelo ONNX entrenado previamente es una matriz float de longitud `21125`, que representa los elementos de un tensor con dimensiones `125 x 13 x 13`. Para transformar las predicciones generadas por el modelo en un tensor, se requiere algún trabajo posterior al procesamiento. Para ello, cree un conjunto de clases que ayuden a analizar la salida.

Agregue un nuevo directorio al proyecto para organizar el conjunto de clases de analizador.

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, luego, seleccione **Agregar** > **Nueva carpeta**. Cuando la nueva carpeta aparezca en el Explorador de soluciones, asígnele el nombre "YoloParser".

### <a name="create-bounding-boxes-and-dimensions"></a>Crear rectángulos delimitadores y dimensiones

La salida de datos del modelo contiene las coordenadas y las dimensiones de los rectángulos delimitadores de los objetos dentro de la imagen. Cree una clase base para las dimensiones.

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el directorio *YoloParser* y luego seleccione **Agregar** > **Nuevo elemento**.
1. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *DimensionsBase.cs*. A continuación, seleccione el botón **Agregar**.

    Se abre el archivo *DimensionsBase.cs* en el editor de código. Quite todas las instrucciones `using` y la definición de clase existente.

    Agregue el código siguiente para la clase `DimensionsBase` al archivo *DimensionsBase.cs*:

    [!code-csharp [DimensionsBaseClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/DimensionsBase.cs#L3-L9)]

    `DimensionsBase` tiene las siguientes propiedades `float`:

    - `X` contiene la posición del objeto en el eje x.
    - `Y` contiene la posición del objeto en el eje y.
    - `Height` contiene la altura del objeto.
    - `Width` contiene el ancho del objeto.

A continuación, cree una clase para los rectángulos delimitadores.

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el directorio *YoloParser* y luego seleccione **Agregar** > **Nuevo elemento**.
1. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *YoloBoundingBox.cs*. A continuación, seleccione el botón **Agregar**.

    Se abre el archivo *YoloBoundingBox.cs* en el editor de código. Agregue la instrucción `using` siguiente al principio del archivo *YoloBoundingBox.cs*:

    [!code-csharp [YoloBoundingBoxUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloBoundingBox.cs#L1)]

    Justo encima de la definición de clase existente, agregue una nueva definición de clase denominada `BoundingBoxDimensions` que herede de la clase `DimensionsBase` para que contenga las dimensiones del rectángulo delimitador correspondiente.

    [!code-csharp [BoundingBoxDimClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloBoundingBox.cs#L5)]

    Quite la definición de clase `YoloBoundingBox` existente y agregue el código siguiente para la clase `YoloBoundingBox` al archivo *YoloBoundingBox.cs*:

    [!code-csharp [YoloBoundingBoxClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloBoundingBox.cs#L7-L21)]

    `YoloBoundingBox` tiene las siguientes propiedades:

    - `Dimensions` contiene las dimensiones del rectángulo delimitador.
    - `Label` contiene la clase de objeto detectado en el rectángulo delimitador.
    - `Confidence` contiene la confianza de la clase.
    - `Rect` contiene la representación del rectángulo de las dimensiones del rectángulo delimitador.
    - `BoxColor` contiene el color asociado a la clase correspondiente usada para dibujar en la imagen.

### <a name="create-the-parser"></a>Crear el analizador

Ahora que se han creado las clases para las dimensiones y los rectángulos delimitadores, es el momento de crear el analizador.

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el directorio *YoloParser* y luego seleccione **Agregar** > **Nuevo elemento**.
1. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *YoloOutputParser.cs*. A continuación, seleccione el botón **Agregar**.

    Se abre el archivo *YoloOutputParser.cs* en el editor de código. Agregue la instrucción `using` siguiente al principio del archivo *YoloOutputParser.cs*:

    [!code-csharp [YoloParserUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L1-L4)]

    Dentro de la definición de clase `YoloOutputParser` existente, agregue una clase anidada que contenga las dimensiones de cada una de las celdas de la imagen. Agregue el código siguiente para la clase `CellDimensions` que hereda de la clase `DimensionsBase` en la parte superior de la definición de la clase `YoloOutputParser`.

    [!code-csharp [YoloParserUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L10)]

1. Dentro de la definición de la clase `YoloOutputParser`, agregue la constante y los campos siguientes.

    [!code-csharp [ParserVarDefinitions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L12-L21)]

    - `ROW_COUNT` es el número de filas de la cuadrícula en la que se divide la imagen.
    - `COL_COUNT` es el número de columnas de la cuadrícula en la que se divide la imagen.
    - `CHANNEL_COUNT` es el número total de valores contenidos en una celda de la cuadrícula.
    - `BOXES_PER_CELL` es el número de rectángulos delimitadores de una celda.
    - `BOX_INFO_FEATURE_COUNT` es el número de características contenidas en un rectángulo (x,y,altura,ancho,confianza).
    - `CLASS_COUNT` es el número de predicciones de clase que contiene cada rectángulo delimitador.
    - `CELL_WIDTH` es el ancho de una celda de la cuadrícula de imagen.
    - `CELL_HEIGHT` es la altura de una celda de la cuadrícula de imagen.
    - `channelStride` es la posición inicial de la celda actual en la cuadrícula.

    Cuando el modelo realiza una predicción, también conocida como puntuación, divide la imagen de entrada `416px x 416px` en una cuadrícula de celdas del tamaño de `13 x 13`. El contenido de cada celda mide `32px x 32px`. Dentro de cada celda, hay 5 rectángulos delimitadores, donde cada uno contiene 5 características (x,y,ancho,altura,confianza). Además, cada rectángulo delimitador contiene la probabilidad de cada una de las clases, que, en este caso, es 20. Por lo tanto, cada celda contiene 125 piezas de información (5 características + 20 probabilidades de clase).

Cree una lista de delimitadores a continuación de `channelStride` para los 5 rectángulos delimitadores:

[!code-csharp [ParserAnchors](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L23-L26)]

Los delimitadores son proporciones predefinidas de altura y ancho de los rectángulos delimitadores. La mayoría de los objetos o clases detectados por un modelo tienen relaciones similares. Esto resulta útil cuando se trata de crear rectángulos delimitadores. En lugar de predecir los rectángulos delimitadores, se calcula el desplazamiento de las dimensiones predefinidas; por lo que se reducen los cálculos necesarios para predecir el rectángulo delimitador. Normalmente, estas proporciones de delimitador se calculan en función del conjunto de datos usado. En este caso, dado que el conjunto de datos es conocido y los valores se han calculado previamente, los delimitadores se pueden codificar de forma rígida.

A continuación, defina las etiquetas o clases que el modelo predecirá. Este modelo predice 20 clases, que es un subconjunto del número total de clases que predice el modelo de YOLOv2 original.

Agregue la lista de etiquetas debajo de `anchors`.

[!code-csharp [ParserLabels](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L28-L34)]

Hay colores asociados a cada una de las clases. Asigne los colores de clase debajo de `labels`:

[!code-csharp [ParserColors](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L36-L59)]

### <a name="create-helper-functions"></a>Crear funciones auxiliares

La fase posterior al procesamiento implica una serie de pasos. Para ayudar con esto, se pueden emplear varios métodos auxiliares.

Los métodos auxiliares que usa el analizador son los siguientes:

- `Sigmoid` aplica la función sigmoidea que da como resultado un número entre 0 y 1.
- `Softmax` normaliza un vector de entrada en una distribución de probabilidad.
- `GetOffset` asigna los elementos de la salida del modelo unidimensional a la posición correspondiente en un tensor de `125 x 13 x 13`.
- `ExtractBoundingBoxes` extrae las dimensiones del rectángulo delimitador mediante el método `GetOffset` de la salida del modelo.
- `GetConfidence` extrae el valor de confianza que indica cómo de seguro está el modelo de que ha detectado un objeto y usa la función `Sigmoid` para convertirlo en porcentaje.
- `MapBoundingBoxToCell` usa las dimensiones del rectángulo delimitador y las asigna a su celda correspondiente dentro de la imagen.
- `ExtractClasses` extrae las predicciones de clase para el rectángulo delimitador de la salida del modelo usando el método `GetOffset` y las convierte en una distribución de probabilidad mediante el método `Softmax`.
- `GetTopResult` selecciona la clase de la lista de clases predichas con la probabilidad más alta.
- `IntersectionOverUnion` filtra los rectángulos delimitadores superpuestos con probabilidades más bajas.

Agregue el código para todos los métodos auxiliares debajo de la lista de `classColors`.

[!code-csharp [ParserHelperMethods](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L61-L151)]

Una vez que haya definido todos los métodos auxiliares, es el momento de usarlos para procesar la salida del modelo.

Debajo del método `IntersectionOverUnion`, cree el método `ParseOutputs` para procesar la salida generada por el modelo.

```csharp
public IList<YoloBoundingBox> ParseOutputs(float[] yoloModelOutputs, float threshold = .3F)
{

}
```

Cree una lista para almacenar los rectángulos delimitadores y defina las variables dentro del método `ParseOutputs`.

[!code-csharp [BBoxList](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L155)]

Cada imagen se divide en una cuadrícula de `13 x 13` celdas. Cada celda contiene cinco rectángulos delimitadores. Debajo de la variable `boxes`, agregue código para procesar todos los rectángulos de cada una de las celdas.

```csharp
for (int row = 0; row < ROW_COUNT; row++)
{
    for (int column = 0; column < COL_COUNT; column++)
    {
        for (int box = 0; box < BOXES_PER_CELL; box++)
        {

        }
    }
}
```

Dentro del bucle más interno, calcule la posición inicial del rectángulo actual dentro de la salida del modelo unidimensional.

[!code-csharp [ChannelDef](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L163)]

Justo debajo de eso, use el método `ExtractBoundingBoxDimensions` para obtener las dimensiones del rectángulo delimitador actual.

[!code-csharp [GetBBoxDims](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L165)]

Luego, use el método `GetConfidence` para obtener la confianza del rectángulo delimitador actual.

[!code-csharp [GetConfidence](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L167)]

Después de eso, use el método `MapBoundingBoxToCell` para asignar el rectángulo delimitador actual a la celda actual que se está procesando.

[!code-csharp [MapBoundingBoxes](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L169)]

Antes de realizar cualquier procesamiento adicional, compruebe si el valor de confianza es mayor que el umbral proporcionado. Si no es así, procese el siguiente rectángulo delimitador.

[!code-csharp [CheckThreshold1](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L171-L172)]

De lo contrario, continúe procesando la salida. El paso siguiente consiste en obtener la distribución de probabilidad de las clases previstas para el rectángulo delimitador actual mediante el método `ExtractClasses`.

[!code-csharp [ExtractClasses](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L174)]

A continuación, use el método `GetTopResult` para obtener el valor y el índice de la clase con la probabilidad más alta para el rectángulo actual y calcular su puntuación.

[!code-csharp [GetTopResult](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L176-L177)]

Use `topScore` para conservar una vez más solo aquellos rectángulos delimitadores que estén por encima del umbral especificado.

[!code-csharp [CheckThreshold2](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L179-L180)]

Por último, si el rectángulo delimitador actual supera el umbral, cree un nuevo objeto `BoundingBox` y agréguelo a la lista `boxes`.

[!code-csharp [AddBBoxToList](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L182-L194)]

Una vez que se hayan procesado todas las celdas de la imagen, devuelva la lista `boxes`. Agregue la siguiente instrucción return debajo del bucle for más exterior en el método `ParseOutputs`.

[!code-csharp [ReturnBoxes](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L198)]

### <a name="filter-overlapping-boxes"></a>Filtrar los rectángulos superpuestos

Ahora que todos los rectángulos delimitadores de gran confianza se han extraído de la salida del modelo, es necesario realizar un filtrado adicional para quitar las imágenes superpuestas. Agregue un método denominado `FilterBoundingBoxes` debajo del método `ParseOutputs`:

```csharp
public IList<YoloBoundingBox> FilterBoundingBoxes(IList<YoloBoundingBox> boxes, int limit, float threshold)
{

}
```

Dentro del método `FilterBoundingBoxes`, empiece por crear una matriz igual al tamaño de los rectángulos detectados, y marque todas las ranuras como activas o listas para su procesamiento.

[!code-csharp [InitActiveSlots](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L203-L207)]

Después, ordene la lista que contiene los rectángulos delimitadores en orden descendente en función de la confianza.

[!code-csharp [SortBoxes](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L209-L211)]

Luego de eso, cree una lista que contenga los resultados filtrados.

[!code-csharp [InitFilterResult](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L213)]

Comience a procesar cada rectángulo delimitador iterando cada uno de los rectángulos delimitadores.

```csharp
for (int i = 0; i < boxes.Count; i++)
{

}
```

Dentro de este bucle for, compruebe si se puede procesar el rectángulo delimitador actual.

```csharp
if (isActiveBoxes[i])
{

}
```

Si es así, agregue el rectángulo delimitador a la lista de resultados. Si los resultados superan el límite de rectángulos especificado que se van a extraer, interrumpa el bucle. Agregue el código siguiente dentro de la instrucción if.

[!code-csharp [AddFirstBBoxToResults](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L219-L223)]

De lo contrario, fíjese en los rectángulos delimitadores adyacentes. Agregue el código siguiente debajo de la comprobación del límite del rectángulo.

```csharp
for (var j = i + 1; j < boxes.Count; j++)
{

}
```

Al igual que el primer rectángulo, si el rectángulo adyacente está activo o listo para procesarse, use el método `IntersectionOverUnion` para comprobar si el primer rectángulo y el segundo rectángulo superan el umbral especificado. Agregue el código siguiente a su bucle for más interno.

[!code-csharp [IOUBBox](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L227-L239)]

Fuera del bucle for más interno que comprueba los rectángulos delimitadores adyacentes, compruebe si hay rectángulos delimitadores restantes para procesar. En caso contrario, interrumpa el bucle for externo.

[!code-csharp [CheckActiveSlots](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L242-L243)]

Por último, fuera del bucle for inicial del método `FilterBoundingBoxes`, devuelva los resultados:

[!code-csharp [ReturnFilteredBBox](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L246)]

Perfecto. Ahora es el momento de usar este código junto con el modelo para la puntuación.

## <a name="use-the-model-for-scoring"></a>Uso del modelo para puntuación

Al igual que con el procesamiento posterior, hay algunos pasos en el procedimiento de puntuación. Para ayudarlo con esto, agregue al proyecto una clase que contendrá la lógica de puntuación.

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.
1. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *OnnxModelScorer.cs*. A continuación, seleccione el botón **Agregar**.

    El archivo *OnnxModelScorer.cs* se abre en el editor de código. Agregue la instrucción `using` siguiente al principio del archivo *OnnxModelScorer.cs*:

    [!code-csharp [ScorerUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L1-L7)]

    Dentro de la definición de la clase `OnnxModelScorer`, agregue las variables siguientes.

    [!code-csharp [InitScorerVars](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L13-L17)]

    Justo debajo de eso, cree un constructor para la clase `OnnxModelScorer`que inicializará las variables definidas anteriormente.

    [!code-csharp [ScorerCtor](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L19-L24)]

    Una vez creado el constructor, defina un par de estructuras que contengan variables relacionadas con la configuración de la imagen y el modelo. Cree una estructura denominada `ImageNetSettings` para que contenga la altura y el ancho esperados como entrada para el modelo.

    [!code-csharp [ImageNetSettingStruct](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L26-L30)]

    Después, cree otra estructura denominada `TinyYoloModelSettings` que contenga los nombres de las capas de entrada y salida del modelo. Para visualizar el nombre de las capas de entrada y salida del modelo, puede usar una herramienta como [Netron.](https://github.com/lutzroeder/netron)

    [!code-csharp [YoloSettingsStruct](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L32-L43)]

    A continuación, cree el primer conjunto de métodos que usará para la puntuación. Cree el método `LoadModel` dentro de la clase `OnnxModelScorer`.

    ```csharp
    private ITransformer LoadModel(string modelLocation)
    {

    }
    ```

    Dentro del método `LoadModel`, agregue el código siguiente para el registro.

    [!code-csharp [LoadModelLog](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L47-L49)]

    Es necesario que las canalizaciones ML.NET conozcan el esquema de datos en el que van a funcionar cuando se llame al método [`Fit`](xref:Microsoft.ML.IEstimator%601.Fit%2A). En este caso, se usará un proceso similar al de entrenamiento. Sin embargo, dado que no se está produciendo ningún entrenamiento real, es aceptable usar un [`IDataView`](xref:Microsoft.ML.IDataView) vacío. Cree un nuevo [`IDataView`](xref:Microsoft.ML.IDataView) para la canalización a partir de una lista vacía.

    [!code-csharp [LoadEmptyIDV](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L52)]

    Luego de eso, defina la canalización. La canalización constará de cuatro transformaciones.

    - [`LoadImages`](xref:Microsoft.ML.ImageEstimatorsCatalog.LoadImages%2A) carga la imagen como mapa de bits.
    - [`ResizeImages`](xref:Microsoft.ML.ImageEstimatorsCatalog.ResizeImages%2A) cambia la escala de la imagen al tamaño especificado (en este caso, `416 x 416`).
    - [`ExtractPixels`](xref:Microsoft.ML.ImageEstimatorsCatalog.ExtractPixels%2A) cambia la representación en píxeles de la imagen de un mapa de bits a un vector numérico.
    - [`ApplyOnnxModel`](xref:Microsoft.ML.OnnxCatalog.ApplyOnnxModel%2A) carga el modelo de ONNX y lo usa para puntuar los datos proporcionados.

    Defina la canalización en el método `LoadModel` debajo de la variable `data`.

    [!code-csharp [ScoringPipeline](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L55-L58)]

    Ahora es el momento de crear una instancia del modelo para la puntuación. Llame al método [`Fit`](xref:Microsoft.ML.IEstimator%601.Fit%2A) en la canalización y devuélvalo para seguir procesándolo.

    [!code-csharp [FitReturnModel](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L61-L63)]

Una vez que el modelo esté cargado, podrá usarse para hacer predicciones. Para facilitar este proceso, cree un método denominado `PredictDataUsingModel` debajo del método `LoadModel`.

```csharp
private IEnumerable<float[]> PredictDataUsingModel(IDataView testData, ITransformer model)
{

}
```

Dentro de `PredictDataUsingModel`, agregue el código siguiente para el registro.

[!code-csharp [PredictDataLog](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L68-L71)]

A continuación, use el método [`Transform`](xref:Microsoft.ML.ITransformer.Transform%2A) para puntuar los datos.

[!code-csharp [ScoreImages](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L73)]

Extraiga las probabilidades previstas y devuélvalas para su procesamiento adicional.

[!code-csharp [ReturnModelOutput](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L75-L77)]

Ahora que ambos pasos están configurados, combínelos en un único método. Debajo del método `PredictDataUsingModel`, agregue un nuevo método denominado `Score`.

[!code-csharp [ScoreMethod](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L80-L85)]

Ya casi lo tenemos. Ahora es el momento de ponerlo todo en práctica.

## <a name="detect-objects"></a>Detectar objetos

Ahora que ha completado toda la configuración, es el momento de detectar algunos objetos. Para empezar, agregue referencias al puntuador y al analizador en la clase *Program.cs*.

[!code-csharp [ReferenceScorerParser](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L8-L9)]

### <a name="score-and-parse-model-outputs"></a>Resultados del modelo de puntuación y análisis

Dentro del método `Main` de la clase *Program.cs*, agregue una instrucción try-catch.

```csharp
try
{

}
catch (Exception ex)
{
    Console.WriteLine(ex.ToString());
}
```

Dentro del bloque `try`, empiece a implementar la lógica de detección de objetos. En primer lugar, cargue los datos en un [`IDataView`](xref:Microsoft.ML.IDataView).

[!code-csharp [LoadData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L29-L30)]

Luego, cree una instancia de `OnnxModelScorer` y úsela para puntuar los datos cargados.

[!code-csharp [ScoreData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L33-L36)]

Ahora es el momento de completar el paso de procesamiento posterior. Cree una instancia de `YoloOutputParser` y úsela para procesar la salida del modelo.

[!code-csharp [ParsePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L39-L44)]

Una vez que se haya procesado la salida del modelo, es el momento de dibujar los rectángulos delimitadores en las imágenes.

### <a name="visualize-predictions"></a>Visualización de predicciones

Una vez que el modelo ha puntuado las imágenes y se han procesado los resultados, hay que dibujar los rectángulos delimitadores en la imagen. Para ello, agregue un método denominado `DrawBoundingBox` debajo del método `GetAbsolutePath` dentro de *Program.cs*.

```csharp
private static void DrawBoundingBox(string inputImageLocation, string outputImageLocation, string imageName, IList<YoloBoundingBox> filteredBoundingBoxes)
{

}
```

En primer lugar, cargue la imagen y obtenga las dimensiones de altura y ancho en el método `DrawBoundingBox`.

[!code-csharp [LoadImage](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L78-L81)]

A continuación, cree un bucle for-each para iterar por cada uno de los rectángulos delimitadores detectados por el modelo.

```csharp
foreach (var box in filteredBoundingBoxes)
{

}
```

Dentro del bucle for-each, obtenga las dimensiones del rectángulo delimitador.

[!code-csharp [GetBBoxDimensions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L86-L89)]

Dado que las dimensiones del rectángulo delimitador corresponden a la entrada del modelo de `416 x 416`, escale las dimensiones del rectángulo delimitador para que coincidan con el tamaño real de la imagen.

[!code-csharp [ScaleImage](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L92-L95)]

Luego, defina una plantilla para el texto que aparecerá sobre cada rectángulo delimitador. El texto contendrá la clase del objeto dentro del rectángulo delimitador correspondiente, así como la confianza.

[!code-csharp [DefineBBoxText](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L98)]

Para dibujar en la imagen, conviértala en un objeto [`Graphics`](xref:System.Drawing.Graphics).

```csharp
using (Graphics thumbnailGraphic = Graphics.FromImage(image))
{

}
```

Dentro del bloque de código `using`, ajuste la configuración del objeto [`Graphics`](xref:System.Drawing.Graphics) del gráfico.

[!code-csharp [TuneGraphicSettings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L102-L104)]

Luego de eso, establezca las opciones de fuente y color para el texto y el rectángulo delimitador.

[!code-csharp [SetColorOptions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L106-L114)]

Cree y rellene un rectángulo sobre el rectángulo delimitador para que contenga el texto mediante el método [`FillRectangle`](xref:System.Drawing.Graphics.FillRectangle%2A). Esto le ayudará a contrastar el texto y mejorar la legibilidad.

[!code-csharp [DrawTextBackground](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L117)]

A continuación, dibuje el texto y el rectángulo delimitador en la imagen con los métodos [`DrawString`](xref:System.Drawing.Graphics.DrawString%2A) y [`DrawRectangle`](xref:System.Drawing.Graphics.DrawRectangle%2A).

[!code-csharp [DrawClassAndBBox](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L118-L121)]

Fuera del bucle for-each, agregue código para guardar las imágenes en `outputDirectory`.

[!code-csharp [SaveImage](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L125-L130)]

Para recibir información adicional de que la aplicación está haciendo predicciones según lo esperado en tiempo de ejecución, agregue un método denominado `LogDetectedObjects` debajo del método `DrawBoundingBox` en el archivo *Program.cs* para generar los objetos detectados en la consola.

[!code-csharp [LogOutputs](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L133-L143)]

Ahora que tiene métodos auxiliares para crear comentarios visuales a partir de las predicciones, agregue un bucle for para iterar en cada una de las imágenes puntuadas.

```csharp
for (var i = 0; i < images.Count(); i++)
{

}
```

Dentro del bucle for, obtenga el nombre del archivo de imagen y los rectángulos delimitadores asociados a él.

[!code-csharp [GetImageFileName](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L49-L50)]

A continuación, use el método `DrawBoundingBox` para dibujar los rectángulos delimitadores en la imagen.

[!code-csharp [DrawBBoxes](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L52)]

Por último, use el método `LogDetectedObjects` para generar predicciones en la consola.

[!code-csharp [LogPredictionsOutput](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L54)]

Después de la instrucción try-catch, agregue lógica adicional para indicar que el proceso ha terminado de ejecutarse.

[!code-csharp [EndProcessLog](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L62-L63)]

Ya está.

## <a name="results"></a>Resultados

Después de seguir los pasos anteriores, ejecute la aplicación de consola (Ctrl + F5). Los resultados deberían ser similares a la salida siguiente. Es posible que vea advertencias o mensajes de procesamiento, si bien se han quitado de los resultados siguientes para mayor claridad.

```console
=====Identify the objects in the images=====

.....The objects in the image image1.jpg are detected as below....
car and its Confidence score: 0.9697262
car and its Confidence score: 0.6674225
person and its Confidence score: 0.5226039
car and its Confidence score: 0.5224892
car and its Confidence score: 0.4675332

.....The objects in the image image2.jpg are detected as below....
cat and its Confidence score: 0.6461141
cat and its Confidence score: 0.6400049

.....The objects in the image image3.jpg are detected as below....
chair and its Confidence score: 0.840578
chair and its Confidence score: 0.796363
diningtable and its Confidence score: 0.6056048
diningtable and its Confidence score: 0.3737402

.....The objects in the image image4.jpg are detected as below....
dog and its Confidence score: 0.7608147
person and its Confidence score: 0.6321323
dog and its Confidence score: 0.5967442
person and its Confidence score: 0.5730394
person and its Confidence score: 0.5551759

========= End of Process..Hit any Key ========
```

Para ver las imágenes con rectángulos delimitadores, desplácese hasta el directorio `assets/images/output/`. A continuación se muestra un ejemplo de una de las imágenes procesadas.

![Imagen procesada de ejemplo de un comedor](./media/object-detection-onnx/dinning-room-table-chairs.png)

¡Enhorabuena! Ha creado correctamente un modelo de Machine Learning para la detección de objetos al reutilizar un modelo de `ONNX` entrenado previamente en ML.NET.

Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/main/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx).

En este tutorial ha aprendido a:
> [!div class="checklist"]
>
> - Entender el problema
> - Conocer qué es ONNX y cómo funciona con ML.NET
> - Entender el modelo
> - Volver a usar el modelo entrenado previamente
> - Detectar objetos con un modelo cargado

Consulte el repositorio de GitHub con ejemplos de Machine Learning para explorar un ejemplo expandido de detección de objetos.
> [!div class="nextstepaction"]
> [Repositorio dotnet/machinelearning-samples de GitHub](https://github.com/dotnet/machinelearning-samples/tree/main/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx)
