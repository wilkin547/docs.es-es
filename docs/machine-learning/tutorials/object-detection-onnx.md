---
title: 'Tutorial: Detección de objetos mediante un modelo de aprendizaje profundo de ONNX'
description: En este tutorial se muestra cómo usar en ML.NET un modelo de aprendizaje profundo de ONNX entrenado previamente para detectar objetos en imágenes.
author: luisquintanilla
ms.author: luquinta
ms.date: 01/30/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 7ff9986c09e39f5c4d24f52c351db6455ff63e77
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77092725"
---
# <a name="tutorial-detect-objects-using-onnx-in-mlnet"></a><span data-ttu-id="11aa6-103">Tutorial: Detección de objetos con ONNX en ML.NET</span><span class="sxs-lookup"><span data-stu-id="11aa6-103">Tutorial: Detect objects using ONNX in ML.NET</span></span>

<span data-ttu-id="11aa6-104">Aprenda a usar en ML.NET un modelo ONNX previamente entrenado para detectar objetos en imágenes.</span><span class="sxs-lookup"><span data-stu-id="11aa6-104">Learn how to use a pre-trained ONNX model in ML.NET to detect objects in images.</span></span>

<span data-ttu-id="11aa6-105">Entrenar un modelo de detección de objetos desde cero requiere establecer millones de parámetros, una enorme cantidad de datos de aprendizaje etiquetados y una gran cantidad de recursos informáticos (cientos de horas de GPU).</span><span class="sxs-lookup"><span data-stu-id="11aa6-105">Training an object detection model from scratch requires setting millions of parameters, a large amount of labeled training data and a vast amount of compute resources (hundreds of GPU hours).</span></span> <span data-ttu-id="11aa6-106">El uso de un modelo entrenado previamente le permite abreviar el proceso de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="11aa6-106">Using a pre-trained model allows you to shortcut the training process.</span></span>

<span data-ttu-id="11aa6-107">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="11aa6-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="11aa6-108">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="11aa6-108">Understand the problem</span></span>
> - <span data-ttu-id="11aa6-109">Conocer qué es ONNX y cómo funciona con ML.NET</span><span class="sxs-lookup"><span data-stu-id="11aa6-109">Learn what ONNX is and how it works with ML.NET</span></span>
> - <span data-ttu-id="11aa6-110">Entender el modelo</span><span class="sxs-lookup"><span data-stu-id="11aa6-110">Understand the model</span></span>
> - <span data-ttu-id="11aa6-111">Volver a usar el modelo entrenado previamente</span><span class="sxs-lookup"><span data-stu-id="11aa6-111">Reuse the pre-trained model</span></span>
> - <span data-ttu-id="11aa6-112">Detectar objetos con un modelo cargado</span><span class="sxs-lookup"><span data-stu-id="11aa6-112">Detect objects with a loaded model</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="11aa6-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="11aa6-113">Pre-requisites</span></span>

- <span data-ttu-id="11aa6-114">[Visual Studio 2017, versión 15.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.</span><span class="sxs-lookup"><span data-stu-id="11aa6-114">[Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>
- [<span data-ttu-id="11aa6-115">Paquete NuGet de Microsoft.ML</span><span class="sxs-lookup"><span data-stu-id="11aa6-115">Microsoft.ML NuGet Package</span></span>](https://www.nuget.org/packages/Microsoft.ML/)
- [<span data-ttu-id="11aa6-116">Paquete NuGet de Microsoft.ML.ImageAnalytics</span><span class="sxs-lookup"><span data-stu-id="11aa6-116">Microsoft.ML.ImageAnalytics NuGet Package</span></span>](https://www.nuget.org/packages/Microsoft.ML.ImageAnalytics/)
- [<span data-ttu-id="11aa6-117">Paquete NuGet de Microsoft.ML.OnnxTransformer</span><span class="sxs-lookup"><span data-stu-id="11aa6-117">Microsoft.ML.OnnxTransformer NuGet Package</span></span>](https://www.nuget.org/packages/Microsoft.ML.OnnxTransformer/)
- [<span data-ttu-id="11aa6-118">Modelo previamente entrenado de Tiny YOLOv2</span><span class="sxs-lookup"><span data-stu-id="11aa6-118">Tiny YOLOv2 pre-trained model</span></span>](https://github.com/onnx/models/tree/master/vision/object_detection_segmentation/tiny_yolov2)
- <span data-ttu-id="11aa6-119">[Netron](https://github.com/lutzroeder/netron) (opcional)</span><span class="sxs-lookup"><span data-stu-id="11aa6-119">[Netron](https://github.com/lutzroeder/netron) (optional)</span></span>

## <a name="onnx-object-detection-sample-overview"></a><span data-ttu-id="11aa6-120">Información general del ejemplo de detección de objetos de ONNX</span><span class="sxs-lookup"><span data-stu-id="11aa6-120">ONNX object detection sample overview</span></span>

<span data-ttu-id="11aa6-121">En este ejemplo se crea una aplicación de consola de .NET Core que detecta objetos dentro de una imagen mediante un modelo de aprendizaje profundo de ONNX previamente entrenado.</span><span class="sxs-lookup"><span data-stu-id="11aa6-121">This sample creates a .NET core console application that detects objects within an image using a pre-trained deep learning ONNX model.</span></span> <span data-ttu-id="11aa6-122">El código de este ejemplo se puede encontrar en el [repositorio dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="11aa6-122">The code for this sample can be found on the [dotnet/machinelearning-samples repository](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx) on GitHub.</span></span>

## <a name="what-is-object-detection"></a><span data-ttu-id="11aa6-123">¿Qué es la detección de objetos?</span><span class="sxs-lookup"><span data-stu-id="11aa6-123">What is object detection?</span></span>

<span data-ttu-id="11aa6-124">La detección de objetos es un problema de visión informática.</span><span class="sxs-lookup"><span data-stu-id="11aa6-124">Object detection is a computer vision problem.</span></span> <span data-ttu-id="11aa6-125">Si bien está estrechamente relacionada con la clasificación de imágenes, la detección de objetos realiza la clasificación de imágenes a una escala más granular.</span><span class="sxs-lookup"><span data-stu-id="11aa6-125">While closely related to image classification, object detection performs image classification at a more granular scale.</span></span> <span data-ttu-id="11aa6-126">La detección de objetos ubica _y_ categoriza entidades dentro de las imágenes.</span><span class="sxs-lookup"><span data-stu-id="11aa6-126">Object detection both locates _and_ categorizes entities within images.</span></span> <span data-ttu-id="11aa6-127">Use la detección de objetos cuando las imágenes contengan varios objetos de tipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="11aa6-127">Use object detection when images contain multiple objects of different types.</span></span>

![Capturas de pantalla en las que se muestran las diferencias entre la clasificación de imágenes y la clasificación de objetos.](./media/object-detection-onnx/img-classification-obj-detection.png)

<span data-ttu-id="11aa6-129">Entre algunos casos de uso para la detección de objetos se incluyen:</span><span class="sxs-lookup"><span data-stu-id="11aa6-129">Some use cases for object detection include:</span></span>

- <span data-ttu-id="11aa6-130">Automóviles sin conductor</span><span class="sxs-lookup"><span data-stu-id="11aa6-130">Self-Driving Cars</span></span>
- <span data-ttu-id="11aa6-131">Robótica</span><span class="sxs-lookup"><span data-stu-id="11aa6-131">Robotics</span></span>
- <span data-ttu-id="11aa6-132">Detección facial</span><span class="sxs-lookup"><span data-stu-id="11aa6-132">Face Detection</span></span>
- <span data-ttu-id="11aa6-133">Seguridad en el lugar de trabajo</span><span class="sxs-lookup"><span data-stu-id="11aa6-133">Workplace Safety</span></span>
- <span data-ttu-id="11aa6-134">Recuento de objetos</span><span class="sxs-lookup"><span data-stu-id="11aa6-134">Object Counting</span></span>
- <span data-ttu-id="11aa6-135">Reconocimiento de actividades</span><span class="sxs-lookup"><span data-stu-id="11aa6-135">Activity Recognition</span></span>

## <a name="select-a-deep-learning-model"></a><span data-ttu-id="11aa6-136">Selección de un modelo de aprendizaje profundo</span><span class="sxs-lookup"><span data-stu-id="11aa6-136">Select a deep learning model</span></span>

<span data-ttu-id="11aa6-137">El aprendizaje profundo es un subconjunto del aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="11aa6-137">Deep learning is a subset of machine learning.</span></span> <span data-ttu-id="11aa6-138">Para entrenar modelos de aprendizaje profundo, se necesitan grandes cantidades de datos.</span><span class="sxs-lookup"><span data-stu-id="11aa6-138">To train deep learning models, large quantities of data are required.</span></span> <span data-ttu-id="11aa6-139">Los patrones de los datos se representan mediante una serie de capas.</span><span class="sxs-lookup"><span data-stu-id="11aa6-139">Patterns in the data are represented by a series of layers.</span></span> <span data-ttu-id="11aa6-140">Las relaciones de los datos se codifican como conexiones entre las capas, que contienen ponderaciones.</span><span class="sxs-lookup"><span data-stu-id="11aa6-140">The relationships in the data are encoded as connections between the layers containing weights.</span></span> <span data-ttu-id="11aa6-141">Cuanto mayor sea la ponderación, más fuerte será la relación.</span><span class="sxs-lookup"><span data-stu-id="11aa6-141">The higher the weight, the stronger the relationship.</span></span> <span data-ttu-id="11aa6-142">En conjunto, esta serie de capas y conexiones se conocen como redes neuronales artificiales.</span><span class="sxs-lookup"><span data-stu-id="11aa6-142">Collectively, this series of layers and connections are known as artificial neural networks.</span></span> <span data-ttu-id="11aa6-143">Cuantas más capas haya en una red, "más profunda" será, lo que la convierte en una red neuronal profunda.</span><span class="sxs-lookup"><span data-stu-id="11aa6-143">The more layers in a network, the "deeper" it is, making it a deep neural network.</span></span>

<span data-ttu-id="11aa6-144">Hay diferentes tipos de redes neuronales, las más comunes son perceptrón multicapa (MLP), red neuronal circunvolucional (CNN) y red neuronal recurrente (RNN).</span><span class="sxs-lookup"><span data-stu-id="11aa6-144">There are different types of neural networks, the most common being Multi-Layered Perceptron (MLP), Convolutional Neural Network (CNN) and Recurrent Neural Network (RNN).</span></span> <span data-ttu-id="11aa6-145">La más básica es MLP, que asigna un conjunto de entradas a un conjunto de salidas.</span><span class="sxs-lookup"><span data-stu-id="11aa6-145">The most basic is the MLP, which maps a set of inputs to a set of outputs.</span></span> <span data-ttu-id="11aa6-146">Esta red neuronal es la adecuada cuando los datos no tienen un componente espacial ni temporal.</span><span class="sxs-lookup"><span data-stu-id="11aa6-146">This neural network is good when the data does not have a spatial or time component.</span></span> <span data-ttu-id="11aa6-147">CNN aprovecha las capas circunvolucionales para procesar la información espacial contenida en los datos.</span><span class="sxs-lookup"><span data-stu-id="11aa6-147">The CNN makes use of convolutional layers to process spatial information contained in the data.</span></span> <span data-ttu-id="11aa6-148">Un buen caso de uso de las CNN es el procesamiento de imágenes para detectar la presencia de una característica en una región de una imagen (por ejemplo, ¿hay una nariz en el centro de una imagen?).</span><span class="sxs-lookup"><span data-stu-id="11aa6-148">A good use case for CNNs is image processing to detect the presence of a feature in a region of an image (for example, is there a nose in the center of an image?).</span></span> <span data-ttu-id="11aa6-149">Por último, las RNN permiten la persistencia del estado o la memoria que se va a usar como entrada.</span><span class="sxs-lookup"><span data-stu-id="11aa6-149">Finally, RNNs allow for the persistence of state or memory to be used as input.</span></span> <span data-ttu-id="11aa6-150">Las RNN se usan para el análisis de series temporales, donde la ordenación secuencial y el contexto de eventos son importantes.</span><span class="sxs-lookup"><span data-stu-id="11aa6-150">RNNs are used for time-series analysis, where the sequential ordering and context of events is important.</span></span>

### <a name="understand-the-model"></a><span data-ttu-id="11aa6-151">Entender el modelo</span><span class="sxs-lookup"><span data-stu-id="11aa6-151">Understand the model</span></span>

<span data-ttu-id="11aa6-152">La detección de objetos es una tarea de procesamiento de imágenes.</span><span class="sxs-lookup"><span data-stu-id="11aa6-152">Object detection is an image-processing task.</span></span> <span data-ttu-id="11aa6-153">Por lo tanto, la mayoría de los modelos de aprendizaje profundo entrenados para solucionar este problema son CNN.</span><span class="sxs-lookup"><span data-stu-id="11aa6-153">Therefore, most deep learning models trained to solve this problem are CNNs.</span></span> <span data-ttu-id="11aa6-154">El modelo que se usa en este tutorial es el Tiny YOLOv2, una versión más compacta del modelo YOLOv2 que se describe en el documento: ["YOLO9000: Better, Faster, Stronger" de Redmon y Fadhari](https://arxiv.org/pdf/1612.08242.pdf).</span><span class="sxs-lookup"><span data-stu-id="11aa6-154">The model used in this tutorial is the Tiny YOLOv2 model, a more compact version of the YOLOv2 model described in the paper: ["YOLO9000: Better, Faster, Stronger" by Redmon and Fadhari](https://arxiv.org/pdf/1612.08242.pdf).</span></span> <span data-ttu-id="11aa6-155">Tiny YOLOv2 se entrena en el conjunto de datos Pascal VOC y se compone de 15 capas que pueden predecir 20 clases diferentes de objetos.</span><span class="sxs-lookup"><span data-stu-id="11aa6-155">Tiny YOLOv2 is trained on the Pascal VOC dataset and is made up of 15 layers that can predict 20 different classes of objects.</span></span> <span data-ttu-id="11aa6-156">Dado que Tiny YOLOv2 es una versión comprimida del modelo YOLOv2 original, se logra velocidad a cambio de precisión.</span><span class="sxs-lookup"><span data-stu-id="11aa6-156">Because Tiny YOLOv2 is a condensed version of the original YOLOv2 model, a tradeoff is made between speed and accuracy.</span></span> <span data-ttu-id="11aa6-157">Los diferentes niveles que componen el modelo se pueden visualizar mediante herramientas como Netron.</span><span class="sxs-lookup"><span data-stu-id="11aa6-157">The different layers that make up the model can be visualized using tools like Netron.</span></span> <span data-ttu-id="11aa6-158">Al inspeccionar el modelo, se produciría una asignación de las conexiones entre todas las capas que componen la red neuronal, donde cada capa contendría el nombre de la capa, junto con las dimensiones de la entrada y la salida correspondientes.</span><span class="sxs-lookup"><span data-stu-id="11aa6-158">Inspecting the model would yield a mapping of the connections between all the layers that make up the neural network, where each layer would contain the name of the layer along with the dimensions of the respective input / output.</span></span> <span data-ttu-id="11aa6-159">Las estructuras de datos que se usan para describir las entradas y salidas del modelo se conocen como tensores.</span><span class="sxs-lookup"><span data-stu-id="11aa6-159">The data structures used to describe the inputs and outputs of the model are known as tensors.</span></span> <span data-ttu-id="11aa6-160">Los tensores se pueden considerar como contenedores que almacenan datos en N dimensiones.</span><span class="sxs-lookup"><span data-stu-id="11aa6-160">Tensors can be thought of as containers that store data in N-dimensions.</span></span> <span data-ttu-id="11aa6-161">En el caso de Tiny YOLOv2, el nombre de la capa de entrada es `image` y espera un tensor de dimensiones `3 x 416 x 416`.</span><span class="sxs-lookup"><span data-stu-id="11aa6-161">In the case of Tiny YOLOv2, the name of the input layer is `image` and it expects a tensor of dimensions `3 x 416 x 416`.</span></span> <span data-ttu-id="11aa6-162">El nombre de la capa de salida es `grid` y genera un tensor de salida de dimensiones `125 x 13 x 13`.</span><span class="sxs-lookup"><span data-stu-id="11aa6-162">The name of the output layer is `grid` and generates an output tensor of dimensions `125 x 13 x 13`.</span></span>

![Capa de entrada dividida en capas ocultas y, luego, la capa de salida](./media/object-detection-onnx/netron-model-map-layers.png)

<span data-ttu-id="11aa6-164">El modelo YOLO toma una imagen `3(RGB) x 416px x 416px`.</span><span class="sxs-lookup"><span data-stu-id="11aa6-164">The YOLO model takes an image `3(RGB) x 416px x 416px`.</span></span> <span data-ttu-id="11aa6-165">El modelo toma esta entrada y la pasa a través de las diferentes capas para generar una salida.</span><span class="sxs-lookup"><span data-stu-id="11aa6-165">The model takes this input and passes it through the different layers to produce an output.</span></span> <span data-ttu-id="11aa6-166">El resultado divide la imagen de entrada en una cuadrícula de `13 x 13`, y cada celda de la cuadrícula consta de `125` valores.</span><span class="sxs-lookup"><span data-stu-id="11aa6-166">The output divides the input image into a `13 x 13` grid, with each cell in the grid consisting of `125` values.</span></span>

### <a name="what-is-an-onnx-model"></a><span data-ttu-id="11aa6-167">¿Qué es un modelo de ONNX?</span><span class="sxs-lookup"><span data-stu-id="11aa6-167">What is an ONNX model?</span></span>

<span data-ttu-id="11aa6-168">Open Neural Network Exchange (ONNX) es un formato de código abierto para los modelos de IA.</span><span class="sxs-lookup"><span data-stu-id="11aa6-168">The Open Neural Network Exchange (ONNX) is an open source format for AI models.</span></span> <span data-ttu-id="11aa6-169">ONNX admite la interoperabilidad entre marcos.</span><span class="sxs-lookup"><span data-stu-id="11aa6-169">ONNX supports interoperability between frameworks.</span></span> <span data-ttu-id="11aa6-170">Esto significa que puede entrenar un modelo en uno de los muchos marcos de aprendizaje automático populares, como PyTorch, convertirlo en formato ONNX y consumir el modelo ONNX en otro marco, como ML.NET.</span><span class="sxs-lookup"><span data-stu-id="11aa6-170">This means you can train a model in one of the many popular machine learning frameworks like PyTorch, convert it into ONNX format and consume the ONNX model in a different framework like ML.NET.</span></span> <span data-ttu-id="11aa6-171">Para más información, visite el [sitio web de ONNX](https://onnx.ai/).</span><span class="sxs-lookup"><span data-stu-id="11aa6-171">To learn more, visit the [ONNX website](https://onnx.ai/).</span></span>

![Diagrama de los formatos de ONNX admitidos en uso.](./media/object-detection-onnx/onnx-supported-formats.png)

<span data-ttu-id="11aa6-173">El modelo Tiny YOLOv2 entrenado previamente se almacena en formato ONNX, una representación serializada de las capas y los patrones aprendidos de esas capas.</span><span class="sxs-lookup"><span data-stu-id="11aa6-173">The pre-trained Tiny YOLOv2 model is stored in ONNX format, a serialized representation of the layers and learned patterns of those layers.</span></span> <span data-ttu-id="11aa6-174">En ML.NET, la interoperabilidad con ONNX se logra con los paquetes NuGet [`ImageAnalytics`](xref:Microsoft.ML.Transforms.Image) y [`OnnxTransformer`](xref:Microsoft.ML.Transforms.Onnx.OnnxTransformer).</span><span class="sxs-lookup"><span data-stu-id="11aa6-174">In ML.NET, interoperability with ONNX is achieved with the [`ImageAnalytics`](xref:Microsoft.ML.Transforms.Image) and [`OnnxTransformer`](xref:Microsoft.ML.Transforms.Onnx.OnnxTransformer) NuGet packages.</span></span> <span data-ttu-id="11aa6-175">El paquete [`ImageAnalytics`](xref:Microsoft.ML.Transforms.Image) contiene una serie de transformaciones que toman una imagen y la codifican en valores numéricos que se pueden usar como entrada en una canalización de entrenamiento o de predicción.</span><span class="sxs-lookup"><span data-stu-id="11aa6-175">The [`ImageAnalytics`](xref:Microsoft.ML.Transforms.Image) package contains a series of transforms that take an image and encode it into numerical values that can be used as input into a prediction or training pipeline.</span></span> <span data-ttu-id="11aa6-176">El paquete [`OnnxTransformer`](xref:Microsoft.ML.Transforms.Onnx.OnnxTransformer) aprovecha el tiempo de ejecución de ONNX para cargar un modelo de ONNX y usarlo para hacer predicciones basadas en la entrada proporcionada.</span><span class="sxs-lookup"><span data-stu-id="11aa6-176">The [`OnnxTransformer`](xref:Microsoft.ML.Transforms.Onnx.OnnxTransformer) package leverages the ONNX Runtime to load an ONNX model and use it to make predictions based on input provided.</span></span>

![Flujo de datos del archivo ONNX en el tiempo de ejecución de ONNX.](./media/object-detection-onnx/onnx-ml-net-integration.png)

## <a name="set-up-the-net-core-project"></a><span data-ttu-id="11aa6-178">Configurar el proyecto de .NET Core</span><span class="sxs-lookup"><span data-stu-id="11aa6-178">Set up the .NET Core project</span></span>

<span data-ttu-id="11aa6-179">Ahora que tiene un conocimiento general de lo que es ONNX y de cómo funciona Tiny YOLOv2, es el momento de compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="11aa6-179">Now that you have a general understanding of what ONNX is and how Tiny YOLOv2 works, it's time to build the application.</span></span>

### <a name="create-a-console-application"></a><span data-ttu-id="11aa6-180">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="11aa6-180">Create a console application</span></span>

1. <span data-ttu-id="11aa6-181">Cree una **aplicación de consola de .NET Core** denominada "ObjectDetection".</span><span class="sxs-lookup"><span data-stu-id="11aa6-181">Create a **.NET Core Console Application** called "ObjectDetection".</span></span>

1. <span data-ttu-id="11aa6-182">Instale el **paquete NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="11aa6-182">Install the **Microsoft.ML NuGet Package**:</span></span>

    - <span data-ttu-id="11aa6-183">En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="11aa6-183">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span>
    - <span data-ttu-id="11aa6-184">Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar y busque **Microsoft.ML**.</span><span class="sxs-lookup"><span data-stu-id="11aa6-184">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**.</span></span>
    - <span data-ttu-id="11aa6-185">Seleccione el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="11aa6-185">Select the **Install** button.</span></span>
    - <span data-ttu-id="11aa6-186">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="11aa6-186">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>
    - <span data-ttu-id="11aa6-187">Repita estos pasos para **Microsoft.ML.ImageAnalytics** y **Microsoft.ML.OnnxTransformer**.</span><span class="sxs-lookup"><span data-stu-id="11aa6-187">Repeat these steps for **Microsoft.ML.ImageAnalytics** and **Microsoft.ML.OnnxTransformer**.</span></span>

### <a name="prepare-your-data-and-pre-trained-model"></a><span data-ttu-id="11aa6-188">Preparar los datos y el modelo entrenado previamente</span><span class="sxs-lookup"><span data-stu-id="11aa6-188">Prepare your data and pre-trained model</span></span>

1. <span data-ttu-id="11aa6-189">Descargue el [archivo ZIP del directorio de recursos del proyecto](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/assets.zip) y descomprímalo.</span><span class="sxs-lookup"><span data-stu-id="11aa6-189">Download [The project assets directory zip file](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/assets.zip) and unzip.</span></span>

1. <span data-ttu-id="11aa6-190">Copie el directorio `assets` en el directorio de proyecto *ObjectDetection*.</span><span class="sxs-lookup"><span data-stu-id="11aa6-190">Copy the `assets` directory into your *ObjectDetection* project directory.</span></span> <span data-ttu-id="11aa6-191">Este directorio y sus subdirectorios contienen los archivos de imagen (excepto los del modelo de Tiny YOLOv2, que descargará y agregará en el paso siguiente) que se necesitan en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="11aa6-191">This directory and its subdirectories contain the image files (except for the Tiny YOLOv2 model, which you'll download and add in the next step) needed for this tutorial.</span></span>

1. <span data-ttu-id="11aa6-192">Descargue el [modelo de Tiny YOLOv2](https://onnxzoo.blob.core.windows.net/models/opset_8/tiny_yolov2/tiny_yolov2.tar.gz) de [ONNX Model Zoo](https://github.com/onnx/models/tree/master/vision/object_detection_segmentation/tiny_yolov2) y descomprímalo.</span><span class="sxs-lookup"><span data-stu-id="11aa6-192">Download the [Tiny YOLOv2 model](https://onnxzoo.blob.core.windows.net/models/opset_8/tiny_yolov2/tiny_yolov2.tar.gz) from the [ONNX Model Zoo](https://github.com/onnx/models/tree/master/vision/object_detection_segmentation/tiny_yolov2), and unzip.</span></span>

    <span data-ttu-id="11aa6-193">Abra el símbolo del sistema y escriba el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="11aa6-193">Open the command prompt and enter the following command:</span></span>

    ```shell
    tar -xvzf tiny_yolov2.tar.gz
    ```

1. <span data-ttu-id="11aa6-194">Copie el archivo `model.onnx` extraído del directorio que acaba de descomprimir en el directorio `assets\Model` del proyecto *ObjectDetection* y cambie su nombre a `TinyYolo2_model.onnx`.</span><span class="sxs-lookup"><span data-stu-id="11aa6-194">Copy the extracted `model.onnx` file from the directory just unzipped into your *ObjectDetection* project `assets\Model` directory and rename it to `TinyYolo2_model.onnx`.</span></span> <span data-ttu-id="11aa6-195">Este directorio contiene el modelo necesario para este tutorial.</span><span class="sxs-lookup"><span data-stu-id="11aa6-195">This directory contains the model needed for this tutorial.</span></span>

1. <span data-ttu-id="11aa6-196">En el Explorador de soluciones, haga clic con el botón derecho en cada uno de los archivos del directorio de recursos y los subdirectorios y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="11aa6-196">In Solution Explorer, right-click each of the files in the asset directory and subdirectories and select **Properties**.</span></span> <span data-ttu-id="11aa6-197">En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.</span><span class="sxs-lookup"><span data-stu-id="11aa6-197">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="11aa6-198">Crear clases y definir rutas de acceso</span><span class="sxs-lookup"><span data-stu-id="11aa6-198">Create classes and define paths</span></span>

<span data-ttu-id="11aa6-199">Abra el archivo*Program.cs* y agregue las instrucciones `using` adicionales siguientes a la parte superior del archivo:</span><span class="sxs-lookup"><span data-stu-id="11aa6-199">Open the *Program.cs* file and add the following additional `using` statements to the top of the file:</span></span>

[!code-csharp [ProgramUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L1-L7)]

<span data-ttu-id="11aa6-200">A continuación, defina las rutas de acceso de los distintos recursos.</span><span class="sxs-lookup"><span data-stu-id="11aa6-200">Next, define the paths of the various assets.</span></span>

1. <span data-ttu-id="11aa6-201">En primer lugar, agregue el método `GetAbsolutePath` debajo del método `Main` en la clase `Program`.</span><span class="sxs-lookup"><span data-stu-id="11aa6-201">First, add the `GetAbsolutePath` method below the `Main` method in the `Program` class.</span></span>

    [!code-csharp [GetAbsolutePath](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L66-L74)]

1. <span data-ttu-id="11aa6-202">Después, dentro del método `Main`, cree campos para almacenar la ubicación de los recursos.</span><span class="sxs-lookup"><span data-stu-id="11aa6-202">Then, inside the `Main` method, create fields to store the location of your assets.</span></span>

    [!code-csharp [AssetDefinition](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L17-L21)]

<span data-ttu-id="11aa6-203">Agregue un nuevo directorio al proyecto para almacenar los datos de entrada y las clases de predicción.</span><span class="sxs-lookup"><span data-stu-id="11aa6-203">Add a new directory to your project to store your input data and prediction classes.</span></span>

<span data-ttu-id="11aa6-204">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, luego, seleccione **Agregar** > **Nueva carpeta**.</span><span class="sxs-lookup"><span data-stu-id="11aa6-204">In **Solution Explorer**, right-click the project, and then select **Add** > **New Folder**.</span></span> <span data-ttu-id="11aa6-205">Cuando la nueva carpeta aparezca en el Explorador de soluciones, asígnele el nombre "DataStructures".</span><span class="sxs-lookup"><span data-stu-id="11aa6-205">When the new folder appears in the Solution Explorer, name it "DataStructures".</span></span>

<span data-ttu-id="11aa6-206">Cree la clase de datos de entrada en el directorio *DataStructures* recién creado.</span><span class="sxs-lookup"><span data-stu-id="11aa6-206">Create your input data class in the newly created *DataStructures* directory.</span></span>

1. <span data-ttu-id="11aa6-207">En el **Explorador de soluciones**, haga clic con el botón derecho en el directorio *DataStructures* y luego seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="11aa6-207">In **Solution Explorer**, right-click the *DataStructures* directory, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="11aa6-208">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *ImageNetData.cs*.</span><span class="sxs-lookup"><span data-stu-id="11aa6-208">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *ImageNetData.cs*.</span></span> <span data-ttu-id="11aa6-209">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="11aa6-209">Then, select the **Add** button.</span></span>

    <span data-ttu-id="11aa6-210">El archivo *ImageNetData.cs* se abre en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="11aa6-210">The *ImageNetData.cs* file opens in the code editor.</span></span> <span data-ttu-id="11aa6-211">Agregue la instrucción `using` siguiente al principio del archivo *ImageNetData.cs*:</span><span class="sxs-lookup"><span data-stu-id="11aa6-211">Add the following `using` statement to the top of *ImageNetData.cs*:</span></span>

    [!code-csharp [ImageNetDataUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/DataStructures/ImageNetData.cs#L1-L4)]

    <span data-ttu-id="11aa6-212">Quite la definición de clase existente y agregue el código siguiente para la clase `ImageNetData` al archivo *ImageNetData.cs*:</span><span class="sxs-lookup"><span data-stu-id="11aa6-212">Remove the existing class definition and add the following code for the `ImageNetData` class to the *ImageNetData.cs* file:</span></span>

    [!code-csharp [ImageNetDataClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/DataStructures/ImageNetData.cs#L8-L23)]

    <span data-ttu-id="11aa6-213">`ImageNetData` es la clase de datos de imagen de entrada y tiene los campos <xref:System.String> siguientes:</span><span class="sxs-lookup"><span data-stu-id="11aa6-213">`ImageNetData` is the input image data class and has the following <xref:System.String> fields:</span></span>

    - <span data-ttu-id="11aa6-214">`ImagePath` contiene la ruta de acceso donde se almacena la imagen.</span><span class="sxs-lookup"><span data-stu-id="11aa6-214">`ImagePath` contains the path where the image is stored.</span></span>
    - <span data-ttu-id="11aa6-215">`Label` contiene el nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="11aa6-215">`Label` contains the name of the file.</span></span>

    <span data-ttu-id="11aa6-216">Además, `ImageNetData` contiene un método `ReadFromFile` que carga varios archivos de imagen almacenados en la ruta `imageFolder` especificada y los devuelve como una colección de objetos `ImageNetData`.</span><span class="sxs-lookup"><span data-stu-id="11aa6-216">Additionally, `ImageNetData` contains a method `ReadFromFile` that loads multiple image files stored in the `imageFolder` path specified and returns them as a collection of `ImageNetData` objects.</span></span>

<span data-ttu-id="11aa6-217">Cree la clase de predicción en el directorio *DataStructures*.</span><span class="sxs-lookup"><span data-stu-id="11aa6-217">Create your prediction class in the *DataStructures* directory.</span></span>

1. <span data-ttu-id="11aa6-218">En el **Explorador de soluciones**, haga clic con el botón derecho en el directorio *DataStructures* y luego seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="11aa6-218">In **Solution Explorer**, right-click the *DataStructures* directory, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="11aa6-219">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *ImageNetPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="11aa6-219">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *ImageNetPrediction.cs*.</span></span> <span data-ttu-id="11aa6-220">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="11aa6-220">Then, select the **Add** button.</span></span>

    <span data-ttu-id="11aa6-221">El archivo *ImageNetPrediction.cs* se abre en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="11aa6-221">The *ImageNetPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="11aa6-222">Agregue la instrucción `using` siguiente al principio del archivo *ImageNetPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="11aa6-222">Add the following `using` statement to the top of *ImageNetPrediction.cs*:</span></span>

    [!code-csharp [ImageNetPredictionUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/DataStructures/ImageNetPrediction.cs#L1)]

    <span data-ttu-id="11aa6-223">Quite la definición de clase existente y agregue el código siguiente para la clase `ImageNetPrediction` al archivo *ImageNetPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="11aa6-223">Remove the existing class definition and add the following code for the `ImageNetPrediction` class to the *ImageNetPrediction.cs* file:</span></span>

    [!code-csharp [ImageNetPredictionClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/DataStructures/ImageNetPrediction.cs#L5-L9)]

    <span data-ttu-id="11aa6-224">`ImageNetPrediction` es la clase de datos de predicción y tiene el campo `float[]` siguiente:</span><span class="sxs-lookup"><span data-stu-id="11aa6-224">`ImageNetPrediction` is the prediction data class and has the following `float[]` field:</span></span>

    - <span data-ttu-id="11aa6-225">`PredictedLabel` contiene las dimensiones, la puntuación de calidad de objeto y las probabilidades de clase para cada uno de los cuadros de límite detectados en una imagen.</span><span class="sxs-lookup"><span data-stu-id="11aa6-225">`PredictedLabel` contains the dimensions, objectness score, and class probabilities for each of the bounding boxes detected in an image.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="11aa6-226">Inicializar variables en Main</span><span class="sxs-lookup"><span data-stu-id="11aa6-226">Initialize variables in Main</span></span>

<span data-ttu-id="11aa6-227">La [clase MLContext](xref:Microsoft.ML.MLContext) es un punto de partida para todas las operaciones de ML.NET. Al inicializar `mlContext`, se crea un entorno de ML.NET que se puede compartir entre los objetos del flujo de trabajo de creación de modelos.</span><span class="sxs-lookup"><span data-stu-id="11aa6-227">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="11aa6-228">Como concepto, se parece a `DBContext` en Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="11aa6-228">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

<span data-ttu-id="11aa6-229">Inicialice la variable `mlContext` con una nueva instancia de `MLContext` al agregar la siguiente línea al método `Main` de *Program.cs* debajo del campo `outputFolder`.</span><span class="sxs-lookup"><span data-stu-id="11aa6-229">Initialize the `mlContext` variable with a new instance of `MLContext` by adding the following line to the `Main` method of *Program.cs* below the `outputFolder` field.</span></span>

[!code-csharp [InitMLContext](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L24)]

## <a name="create-a-parser-to-post-process-model-outputs"></a><span data-ttu-id="11aa6-230">Crear un analizador para el procesamiento posterior de las salidas del modelo</span><span class="sxs-lookup"><span data-stu-id="11aa6-230">Create a parser to post-process model outputs</span></span>

<span data-ttu-id="11aa6-231">El modelo segmenta una imagen en una cuadrícula `13 x 13`, donde cada celda de la cuadrícula mide `32px x 32px`.</span><span class="sxs-lookup"><span data-stu-id="11aa6-231">The model segments an image into a `13 x 13` grid, where each grid cell is `32px x 32px`.</span></span> <span data-ttu-id="11aa6-232">Cada celda de la cuadrícula contiene 5 rectángulos delimitadores de objeto posibles.</span><span class="sxs-lookup"><span data-stu-id="11aa6-232">Each grid cell contains 5 potential object bounding boxes.</span></span> <span data-ttu-id="11aa6-233">Un rectángulo delimitador tiene 25 elementos:</span><span class="sxs-lookup"><span data-stu-id="11aa6-233">A bounding box has  25 elements:</span></span>

![Ejemplo de cuadrícula a la izquierda y ejemplo de rectángulo delimitador a la derecha](./media/object-detection-onnx/model-output-description.png)

- <span data-ttu-id="11aa6-235">`x`, posición x del centro del rectángulo delimitador relativo a la celda de la cuadrícula a la que está asociada.</span><span class="sxs-lookup"><span data-stu-id="11aa6-235">`x` the x position of the bounding box center relative to the grid cell it's associated with.</span></span>
- <span data-ttu-id="11aa6-236">`y`, posición y del centro del rectángulo delimitador relativo a la celda de la cuadrícula a la que está asociada.</span><span class="sxs-lookup"><span data-stu-id="11aa6-236">`y` the y position of the bounding box center relative to the grid cell it's associated with.</span></span>
- <span data-ttu-id="11aa6-237">`w`, ancho del rectángulo delimitador.</span><span class="sxs-lookup"><span data-stu-id="11aa6-237">`w` the width of the bounding box.</span></span>
- <span data-ttu-id="11aa6-238">`h`, altura del rectángulo delimitador.</span><span class="sxs-lookup"><span data-stu-id="11aa6-238">`h` the height of the bounding box.</span></span>
- <span data-ttu-id="11aa6-239">`o`, valor de confianza de que existe un objeto dentro del rectángulo delimitador, también conocido como puntuación de calidad de objeto.</span><span class="sxs-lookup"><span data-stu-id="11aa6-239">`o` the confidence value that an object exists within the bounding box, also known as objectness score.</span></span>
- <span data-ttu-id="11aa6-240">`p1-p20`, probabilidades de clase para cada una de las 20 clases previstas por el modelo.</span><span class="sxs-lookup"><span data-stu-id="11aa6-240">`p1-p20` class probabilities for each of the 20 classes predicted by the model.</span></span>

<span data-ttu-id="11aa6-241">En total, los 25 elementos que describen cada uno de los 5 rectángulos delimitadores constituyen los 125 elementos contenidos en cada celda de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="11aa6-241">In total, the 25 elements describing each of the 5 bounding boxes make up the 125 elements contained in each grid cell.</span></span>

<span data-ttu-id="11aa6-242">La salida generada por el modelo ONNX entrenado previamente es una matriz float de longitud `21125`, que representa los elementos de un tensor con dimensiones `125 x 13 x 13`.</span><span class="sxs-lookup"><span data-stu-id="11aa6-242">The output generated by the pre-trained ONNX model is a float array of length `21125`, representing the elements of a tensor with dimensions `125 x 13 x 13`.</span></span> <span data-ttu-id="11aa6-243">Para transformar las predicciones generadas por el modelo en un tensor, se requiere algún trabajo posterior al procesamiento.</span><span class="sxs-lookup"><span data-stu-id="11aa6-243">In order to transform the predictions generated by the model into a tensor, some post-processing work is required.</span></span> <span data-ttu-id="11aa6-244">Para ello, cree un conjunto de clases que ayuden a analizar la salida.</span><span class="sxs-lookup"><span data-stu-id="11aa6-244">To do so, create a set of classes to help parse the output.</span></span>

<span data-ttu-id="11aa6-245">Agregue un nuevo directorio al proyecto para organizar el conjunto de clases de analizador.</span><span class="sxs-lookup"><span data-stu-id="11aa6-245">Add a new directory to your project to organize the set of parser classes.</span></span>

1. <span data-ttu-id="11aa6-246">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, luego, seleccione **Agregar** > **Nueva carpeta**.</span><span class="sxs-lookup"><span data-stu-id="11aa6-246">In **Solution Explorer**, right-click the project, and then select **Add** > **New Folder**.</span></span> <span data-ttu-id="11aa6-247">Cuando la nueva carpeta aparezca en el Explorador de soluciones, asígnele el nombre "YoloParser".</span><span class="sxs-lookup"><span data-stu-id="11aa6-247">When the new folder appears in the Solution Explorer, name it "YoloParser".</span></span>

### <a name="create-bounding-boxes-and-dimensions"></a><span data-ttu-id="11aa6-248">Crear rectángulos delimitadores y dimensiones</span><span class="sxs-lookup"><span data-stu-id="11aa6-248">Create bounding boxes and dimensions</span></span>

<span data-ttu-id="11aa6-249">La salida de datos del modelo contiene las coordenadas y las dimensiones de los rectángulos delimitadores de los objetos dentro de la imagen.</span><span class="sxs-lookup"><span data-stu-id="11aa6-249">The data output by the model contains coordinates and dimensions of the bounding boxes of objects within the image.</span></span> <span data-ttu-id="11aa6-250">Cree una clase base para las dimensiones.</span><span class="sxs-lookup"><span data-stu-id="11aa6-250">Create a base class for dimensions.</span></span>

1. <span data-ttu-id="11aa6-251">En el **Explorador de soluciones**, haga clic con el botón derecho en el directorio *YoloParser* y luego seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="11aa6-251">In **Solution Explorer**, right-click the *YoloParser* directory, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="11aa6-252">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *DimensionsBase.cs*.</span><span class="sxs-lookup"><span data-stu-id="11aa6-252">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *DimensionsBase.cs*.</span></span> <span data-ttu-id="11aa6-253">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="11aa6-253">Then, select the **Add** button.</span></span>

    <span data-ttu-id="11aa6-254">Se abre el archivo *DimensionsBase.cs* en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="11aa6-254">The *DimensionsBase.cs* file opens in the code editor.</span></span> <span data-ttu-id="11aa6-255">Quite todas las instrucciones `using` y la definición de clase existente.</span><span class="sxs-lookup"><span data-stu-id="11aa6-255">Remove all `using` statements and existing class definition.</span></span>

    <span data-ttu-id="11aa6-256">Agregue el código siguiente para la clase `DimensionsBase` al archivo *DimensionsBase.cs*:</span><span class="sxs-lookup"><span data-stu-id="11aa6-256">Add the following code for the `DimensionsBase` class to the *DimensionsBase.cs* file:</span></span>

    [!code-csharp [DimensionsBaseClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/DimensionsBase.cs#L3-L9)]

    <span data-ttu-id="11aa6-257">`DimensionsBase` tiene las siguientes propiedades `float`:</span><span class="sxs-lookup"><span data-stu-id="11aa6-257">`DimensionsBase` has the following `float` properties:</span></span>

    - <span data-ttu-id="11aa6-258">`X` contiene la posición del objeto en el eje x.</span><span class="sxs-lookup"><span data-stu-id="11aa6-258">`X` contains the position of the object along the x-axis.</span></span>
    - <span data-ttu-id="11aa6-259">`Y` contiene la posición del objeto en el eje y.</span><span class="sxs-lookup"><span data-stu-id="11aa6-259">`Y` contains the position of the object along the y-axis.</span></span>
    - <span data-ttu-id="11aa6-260">`Height` contiene la altura del objeto.</span><span class="sxs-lookup"><span data-stu-id="11aa6-260">`Height` contains the height of the object.</span></span>
    - <span data-ttu-id="11aa6-261">`Width` contiene el ancho del objeto.</span><span class="sxs-lookup"><span data-stu-id="11aa6-261">`Width` contains the width of the object.</span></span>

<span data-ttu-id="11aa6-262">A continuación, cree una clase para los rectángulos delimitadores.</span><span class="sxs-lookup"><span data-stu-id="11aa6-262">Next, create a class for your bounding boxes.</span></span>

1. <span data-ttu-id="11aa6-263">En el **Explorador de soluciones**, haga clic con el botón derecho en el directorio *YoloParser* y luego seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="11aa6-263">In **Solution Explorer**, right-click the *YoloParser* directory, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="11aa6-264">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *YoloBoundingBox.cs*.</span><span class="sxs-lookup"><span data-stu-id="11aa6-264">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *YoloBoundingBox.cs*.</span></span> <span data-ttu-id="11aa6-265">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="11aa6-265">Then, select the **Add** button.</span></span>

    <span data-ttu-id="11aa6-266">Se abre el archivo *YoloBoundingBox.cs* en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="11aa6-266">The *YoloBoundingBox.cs* file opens in the code editor.</span></span> <span data-ttu-id="11aa6-267">Agregue la instrucción `using` siguiente al principio del archivo *YoloBoundingBox.cs*:</span><span class="sxs-lookup"><span data-stu-id="11aa6-267">Add the following `using` statement to the top of *YoloBoundingBox.cs*:</span></span>

    [!code-csharp [YoloBoundingBoxUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloBoundingBox.cs#L1)]

    <span data-ttu-id="11aa6-268">Justo encima de la definición de clase existente, agregue una nueva definición de clase denominada `BoundingBoxDimensions` que herede de la clase `DimensionsBase` para que contenga las dimensiones del rectángulo delimitador correspondiente.</span><span class="sxs-lookup"><span data-stu-id="11aa6-268">Just above the existing class definition, add a new class definition called `BoundingBoxDimensions` that inherits from the `DimensionsBase` class to contain the dimensions of the respective bounding box.</span></span>

    [!code-csharp [BoundingBoxDimClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloBoundingBox.cs#L5)]

    <span data-ttu-id="11aa6-269">Quite la definición de clase `YoloBoundingBox` existente y agregue el código siguiente para la clase `YoloBoundingBox` al archivo *YoloBoundingBox.cs*:</span><span class="sxs-lookup"><span data-stu-id="11aa6-269">Remove the existing `YoloBoundingBox` class definition and add the following code for the `YoloBoundingBox` class to the *YoloBoundingBox.cs* file:</span></span>

    [!code-csharp [YoloBoundingBoxClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloBoundingBox.cs#L7-L21)]

    <span data-ttu-id="11aa6-270">`YoloBoundingBox` tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="11aa6-270">`YoloBoundingBox` has the following properties:</span></span>

    - <span data-ttu-id="11aa6-271">`Dimensions` contiene las dimensiones del rectángulo delimitador.</span><span class="sxs-lookup"><span data-stu-id="11aa6-271">`Dimensions` contains dimensions of the bounding box.</span></span>
    - <span data-ttu-id="11aa6-272">`Label` contiene la clase de objeto detectado en el rectángulo delimitador.</span><span class="sxs-lookup"><span data-stu-id="11aa6-272">`Label` contains the class of object detected within the bounding box.</span></span>
    - <span data-ttu-id="11aa6-273">`Confidence` contiene la confianza de la clase.</span><span class="sxs-lookup"><span data-stu-id="11aa6-273">`Confidence` contains the confidence of the class.</span></span>
    - <span data-ttu-id="11aa6-274">`Rect` contiene la representación del rectángulo de las dimensiones del rectángulo delimitador.</span><span class="sxs-lookup"><span data-stu-id="11aa6-274">`Rect` contains the rectangle representation of the bounding box's dimensions.</span></span>
    - <span data-ttu-id="11aa6-275">`BoxColor` contiene el color asociado a la clase correspondiente usada para dibujar en la imagen.</span><span class="sxs-lookup"><span data-stu-id="11aa6-275">`BoxColor` contains the color associated with the respective class used to draw on the image.</span></span>

### <a name="create-the-parser"></a><span data-ttu-id="11aa6-276">Crear el analizador</span><span class="sxs-lookup"><span data-stu-id="11aa6-276">Create the parser</span></span>

<span data-ttu-id="11aa6-277">Ahora que se han creado las clases para las dimensiones y los rectángulos delimitadores, es el momento de crear el analizador.</span><span class="sxs-lookup"><span data-stu-id="11aa6-277">Now that the classes for dimensions and bounding boxes are created, it's time to create the parser.</span></span>

1. <span data-ttu-id="11aa6-278">En el **Explorador de soluciones**, haga clic con el botón derecho en el directorio *YoloParser* y luego seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="11aa6-278">In **Solution Explorer**, right-click the *YoloParser* directory, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="11aa6-279">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *YoloOutputParser.cs*.</span><span class="sxs-lookup"><span data-stu-id="11aa6-279">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *YoloOutputParser.cs*.</span></span> <span data-ttu-id="11aa6-280">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="11aa6-280">Then, select the **Add** button.</span></span>

    <span data-ttu-id="11aa6-281">Se abre el archivo *YoloOutputParser.cs* en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="11aa6-281">The *YoloOutputParser.cs* file opens in the code editor.</span></span> <span data-ttu-id="11aa6-282">Agregue la instrucción `using` siguiente al principio del archivo *YoloOutputParser.cs*:</span><span class="sxs-lookup"><span data-stu-id="11aa6-282">Add the following `using` statement to the top of *YoloOutputParser.cs*:</span></span>

    [!code-csharp [YoloParserUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L1-L4)]

    <span data-ttu-id="11aa6-283">Dentro de la definición de clase `YoloOutputParser` existente, agregue una clase anidada que contenga las dimensiones de cada una de las celdas de la imagen.</span><span class="sxs-lookup"><span data-stu-id="11aa6-283">Inside the existing `YoloOutputParser` class definition, add a nested class that contains the dimensions of each of the cells in the image.</span></span> <span data-ttu-id="11aa6-284">Agregue el código siguiente para la clase `CellDimensions` que hereda de la clase `DimensionsBase` en la parte superior de la definición de la clase `YoloOutputParser`.</span><span class="sxs-lookup"><span data-stu-id="11aa6-284">Add the following code for the `CellDimensions` class that inherits from the `DimensionsBase` class at the top of the `YoloOutputParser` class definition.</span></span>

    [!code-csharp [YoloParserUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L10)]

1. <span data-ttu-id="11aa6-285">Dentro de la definición de la clase `YoloOutputParser`, agregue la constante y los campos siguientes.</span><span class="sxs-lookup"><span data-stu-id="11aa6-285">Inside the `YoloOutputParser` class definition, add the following constants and fields.</span></span>

    [!code-csharp [ParserVarDefinitions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L12-L21)]

    - <span data-ttu-id="11aa6-286">`ROW_COUNT` es el número de filas de la cuadrícula en la que se divide la imagen.</span><span class="sxs-lookup"><span data-stu-id="11aa6-286">`ROW_COUNT` is the number of rows in the grid the image is divided into.</span></span>
    - <span data-ttu-id="11aa6-287">`COL_COUNT` es el número de columnas de la cuadrícula en la que se divide la imagen.</span><span class="sxs-lookup"><span data-stu-id="11aa6-287">`COL_COUNT` is the number of columns in the grid the image is divided into.</span></span>
    - <span data-ttu-id="11aa6-288">`CHANNEL_COUNT` es el número total de valores contenidos en una celda de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="11aa6-288">`CHANNEL_COUNT` is the total number of values contained in one cell of the grid.</span></span>
    - <span data-ttu-id="11aa6-289">`BOXES_PER_CELL` es el número de rectángulos delimitadores de una celda.</span><span class="sxs-lookup"><span data-stu-id="11aa6-289">`BOXES_PER_CELL` is the number of bounding boxes in a cell,</span></span>
    - <span data-ttu-id="11aa6-290">`BOX_INFO_FEATURE_COUNT` es el número de características contenidas en un rectángulo (x,y,altura,ancho,confianza).</span><span class="sxs-lookup"><span data-stu-id="11aa6-290">`BOX_INFO_FEATURE_COUNT` is the number of features contained within a box (x,y,height,width,confidence).</span></span>
    - <span data-ttu-id="11aa6-291">`CLASS_COUNT` es el número de predicciones de clase que contiene cada rectángulo delimitador.</span><span class="sxs-lookup"><span data-stu-id="11aa6-291">`CLASS_COUNT` is the number of class predictions contained in each bounding box.</span></span>
    - <span data-ttu-id="11aa6-292">`CELL_WIDTH` es el ancho de una celda de la cuadrícula de imagen.</span><span class="sxs-lookup"><span data-stu-id="11aa6-292">`CELL_WIDTH` is the width of one cell in the image grid.</span></span>
    - <span data-ttu-id="11aa6-293">`CELL_HEIGHT` es la altura de una celda de la cuadrícula de imagen.</span><span class="sxs-lookup"><span data-stu-id="11aa6-293">`CELL_HEIGHT` is the height of one cell in the image grid.</span></span>
    - <span data-ttu-id="11aa6-294">`channelStride` es la posición inicial de la celda actual en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="11aa6-294">`channelStride` is the starting position of the current cell in the grid.</span></span>

    <span data-ttu-id="11aa6-295">Cuando el modelo realiza una predicción, también conocida como puntuación, divide la imagen de entrada `416px x 416px` en una cuadrícula de celdas del tamaño de `13 x 13`.</span><span class="sxs-lookup"><span data-stu-id="11aa6-295">When the model makes a prediction, also known as scoring, it divides the `416px x 416px` input image into a grid of cells the size of `13 x 13`.</span></span> <span data-ttu-id="11aa6-296">El contenido de cada celda mide `32px x 32px`.</span><span class="sxs-lookup"><span data-stu-id="11aa6-296">Each cell contains is `32px x 32px`.</span></span> <span data-ttu-id="11aa6-297">Dentro de cada celda, hay 5 rectángulos delimitadores, donde cada uno contiene 5 características (x,y,ancho,altura,confianza).</span><span class="sxs-lookup"><span data-stu-id="11aa6-297">Within each cell, there are 5 bounding boxes each containing 5 features (x, y, width, height, confidence).</span></span> <span data-ttu-id="11aa6-298">Además, cada rectángulo delimitador contiene la probabilidad de cada una de las clases, que, en este caso, es 20.</span><span class="sxs-lookup"><span data-stu-id="11aa6-298">In addition, each bounding box contains the probability of each of the classes, which in this case is 20.</span></span> <span data-ttu-id="11aa6-299">Por lo tanto, cada celda contiene 125 piezas de información (5 características + 20 probabilidades de clase).</span><span class="sxs-lookup"><span data-stu-id="11aa6-299">Therefore, each cell contains 125 pieces of information (5 features + 20 class probabilities).</span></span>

<span data-ttu-id="11aa6-300">Cree una lista de delimitadores a continuación de `channelStride` para los 5 rectángulos delimitadores:</span><span class="sxs-lookup"><span data-stu-id="11aa6-300">Create a list of anchors below `channelStride` for all 5 bounding boxes:</span></span>

[!code-csharp [ParserAnchors](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L23-L26)]

<span data-ttu-id="11aa6-301">Los delimitadores son proporciones predefinidas de altura y ancho de los rectángulos delimitadores.</span><span class="sxs-lookup"><span data-stu-id="11aa6-301">Anchors are pre-defined height and width ratios of bounding boxes.</span></span> <span data-ttu-id="11aa6-302">La mayoría de los objetos o clases detectados por un modelo tienen relaciones similares.</span><span class="sxs-lookup"><span data-stu-id="11aa6-302">Most object or classes detected by a model have similar ratios.</span></span> <span data-ttu-id="11aa6-303">Esto resulta útil cuando se trata de crear rectángulos delimitadores.</span><span class="sxs-lookup"><span data-stu-id="11aa6-303">This is valuable when it comes to creating bounding boxes.</span></span> <span data-ttu-id="11aa6-304">En lugar de predecir los rectángulos delimitadores, se calcula el desplazamiento de las dimensiones predefinidas; por lo que se reducen los cálculos necesarios para predecir el rectángulo delimitador.</span><span class="sxs-lookup"><span data-stu-id="11aa6-304">Instead of predicting the bounding boxes, the offset from the pre-defined dimensions is calculated therefore reducing the computation required to predict the bounding box.</span></span> <span data-ttu-id="11aa6-305">Normalmente, estas proporciones de delimitador se calculan en función del conjunto de datos usado.</span><span class="sxs-lookup"><span data-stu-id="11aa6-305">Typically these anchor ratios are calculated based on the dataset used.</span></span> <span data-ttu-id="11aa6-306">En este caso, dado que el conjunto de datos es conocido y los valores se han calculado previamente, los delimitadores se pueden codificar de forma rígida.</span><span class="sxs-lookup"><span data-stu-id="11aa6-306">In this case, because the dataset is known and the values have been pre-computed, the anchors can be hard-coded.</span></span>

<span data-ttu-id="11aa6-307">A continuación, defina las etiquetas o clases que el modelo predecirá.</span><span class="sxs-lookup"><span data-stu-id="11aa6-307">Next, define the labels or classes that the model will predict.</span></span> <span data-ttu-id="11aa6-308">Este modelo predice 20 clases, que es un subconjunto del número total de clases que predice el modelo de YOLOv2 original.</span><span class="sxs-lookup"><span data-stu-id="11aa6-308">This model predicts 20 classes, which is a subset of the total number of classes predicted by the original YOLOv2 model.</span></span>

<span data-ttu-id="11aa6-309">Agregue la lista de etiquetas debajo de `anchors`.</span><span class="sxs-lookup"><span data-stu-id="11aa6-309">Add your list of labels below the `anchors`.</span></span>

[!code-csharp [ParserLabels](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L28-L34)]

<span data-ttu-id="11aa6-310">Hay colores asociados a cada una de las clases.</span><span class="sxs-lookup"><span data-stu-id="11aa6-310">There are colors associated with each of the classes.</span></span> <span data-ttu-id="11aa6-311">Asigne los colores de clase debajo de `labels`:</span><span class="sxs-lookup"><span data-stu-id="11aa6-311">Assign your class colors below your `labels`:</span></span>

[!code-csharp [ParserColors](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L36-L59)]

### <a name="create-helper-functions"></a><span data-ttu-id="11aa6-312">Crear funciones auxiliares</span><span class="sxs-lookup"><span data-stu-id="11aa6-312">Create helper functions</span></span>

<span data-ttu-id="11aa6-313">La fase posterior al procesamiento implica una serie de pasos.</span><span class="sxs-lookup"><span data-stu-id="11aa6-313">There are a series of steps involved in the post-processing phase.</span></span> <span data-ttu-id="11aa6-314">Para ayudar con esto, se pueden emplear varios métodos auxiliares.</span><span class="sxs-lookup"><span data-stu-id="11aa6-314">To help with that, several helper methods can be employed.</span></span>

<span data-ttu-id="11aa6-315">Los métodos auxiliares que usa el analizador son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="11aa6-315">The helper methods used in by the parser are:</span></span>

- <span data-ttu-id="11aa6-316">`Sigmoid` aplica la función sigmoidea que da como resultado un número entre 0 y 1.</span><span class="sxs-lookup"><span data-stu-id="11aa6-316">`Sigmoid` applies the sigmoid function that outputs a number between 0 and 1.</span></span>
- <span data-ttu-id="11aa6-317">`Softmax` normaliza un vector de entrada en una distribución de probabilidad.</span><span class="sxs-lookup"><span data-stu-id="11aa6-317">`Softmax` normalizes an input vector into a probability distribution.</span></span>
- <span data-ttu-id="11aa6-318">`GetOffset` asigna los elementos de la salida del modelo unidimensional a la posición correspondiente en un tensor de `125 x 13 x 13`.</span><span class="sxs-lookup"><span data-stu-id="11aa6-318">`GetOffset` maps elements in the one-dimensional model output to the corresponding position in a `125 x 13 x 13` tensor.</span></span>
- <span data-ttu-id="11aa6-319">`ExtractBoundingBoxes` extrae las dimensiones del rectángulo delimitador mediante el método `GetOffset` de la salida del modelo.</span><span class="sxs-lookup"><span data-stu-id="11aa6-319">`ExtractBoundingBoxes` extracts the bounding box dimensions using the `GetOffset` method from the model output.</span></span>
- <span data-ttu-id="11aa6-320">`GetConfidence` extrae el valor de confianza que indica cómo de seguro está el modelo de que ha detectado un objeto y usa la función `Sigmoid` para convertirlo en porcentaje.</span><span class="sxs-lookup"><span data-stu-id="11aa6-320">`GetConfidence` extracts the confidence value that states how sure the model is that it has detected an object and uses the `Sigmoid` function to turn it into a percentage.</span></span>
- <span data-ttu-id="11aa6-321">`MapBoundingBoxToCell` usa las dimensiones del rectángulo delimitador y las asigna a su celda correspondiente dentro de la imagen.</span><span class="sxs-lookup"><span data-stu-id="11aa6-321">`MapBoundingBoxToCell` uses the bounding box dimensions and maps them onto its respective cell within the image.</span></span>
- <span data-ttu-id="11aa6-322">`ExtractClasses` extrae las predicciones de clase para el rectángulo delimitador de la salida del modelo usando el método `GetOffset` y las convierte en una distribución de probabilidad mediante el método `Softmax`.</span><span class="sxs-lookup"><span data-stu-id="11aa6-322">`ExtractClasses` extracts the class predictions for the bounding box from the model output using the `GetOffset` method and turns them into a probability distribution using the `Softmax` method.</span></span>
- <span data-ttu-id="11aa6-323">`GetTopResult` selecciona la clase de la lista de clases predichas con la probabilidad más alta.</span><span class="sxs-lookup"><span data-stu-id="11aa6-323">`GetTopResult` selects the class from the list of predicted classes with the highest probability.</span></span>
- <span data-ttu-id="11aa6-324">`IntersectionOverUnion` filtra los rectángulos delimitadores superpuestos con probabilidades más bajas.</span><span class="sxs-lookup"><span data-stu-id="11aa6-324">`IntersectionOverUnion` filters overlapping bounding boxes with lower probabilities.</span></span>

<span data-ttu-id="11aa6-325">Agregue el código para todos los métodos auxiliares debajo de la lista de `classColors`.</span><span class="sxs-lookup"><span data-stu-id="11aa6-325">Add the code for all the helper methods below your list of `classColors`.</span></span>

[!code-csharp [ParserHelperMethods](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L61-L151)]

<span data-ttu-id="11aa6-326">Una vez que haya definido todos los métodos auxiliares, es el momento de usarlos para procesar la salida del modelo.</span><span class="sxs-lookup"><span data-stu-id="11aa6-326">Once you have defined all of the helper methods, it's time to use them to process the model output.</span></span>

<span data-ttu-id="11aa6-327">Debajo del método `IntersectionOverUnion`, cree el método `ParseOutputs` para procesar la salida generada por el modelo.</span><span class="sxs-lookup"><span data-stu-id="11aa6-327">Below the `IntersectionOverUnion` method, create the `ParseOutputs` method to process the output generated by the model.</span></span>

```csharp
public IList<YoloBoundingBox> ParseOutputs(float[] yoloModelOutputs, float threshold = .3F)
{

}
```

<span data-ttu-id="11aa6-328">Cree una lista para almacenar los rectángulos delimitadores y defina las variables dentro del método `ParseOutputs`.</span><span class="sxs-lookup"><span data-stu-id="11aa6-328">Create a list to store your bounding boxes and define variables inside the `ParseOutputs` method.</span></span>

[!code-csharp [BBoxList](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L155)]

<span data-ttu-id="11aa6-329">Cada imagen se divide en una cuadrícula de `13 x 13` celdas.</span><span class="sxs-lookup"><span data-stu-id="11aa6-329">Each image is divided into a grid of `13 x 13` cells.</span></span> <span data-ttu-id="11aa6-330">Cada celda contiene cinco rectángulos delimitadores.</span><span class="sxs-lookup"><span data-stu-id="11aa6-330">Each cell contains five bounding boxes.</span></span> <span data-ttu-id="11aa6-331">Debajo de la variable `boxes`, agregue código para procesar todos los rectángulos de cada una de las celdas.</span><span class="sxs-lookup"><span data-stu-id="11aa6-331">Below the `boxes` variable, add code to process all of the boxes in each of the cells.</span></span>

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

<span data-ttu-id="11aa6-332">Dentro del bucle más interno, calcule la posición inicial del rectángulo actual dentro de la salida del modelo unidimensional.</span><span class="sxs-lookup"><span data-stu-id="11aa6-332">Inside the inner-most loop, calculate the starting position of the current box within the one-dimensional model output.</span></span>

[!code-csharp [ChannelDef](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L163)]

<span data-ttu-id="11aa6-333">Justo debajo de eso, use el método `ExtractBoundingBoxDimensions` para obtener las dimensiones del rectángulo delimitador actual.</span><span class="sxs-lookup"><span data-stu-id="11aa6-333">Directly below that, use the `ExtractBoundingBoxDimensions` method to get the dimensions of the current bounding box.</span></span>

[!code-csharp [GetBBoxDims](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L165)]

<span data-ttu-id="11aa6-334">Luego, use el método `GetConfidence` para obtener la confianza del rectángulo delimitador actual.</span><span class="sxs-lookup"><span data-stu-id="11aa6-334">Then, use the `GetConfidence` method to get the confidence for the current bounding box.</span></span>

[!code-csharp [GetConfidence](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L167)]

<span data-ttu-id="11aa6-335">Después de eso, use el método `MapBoundingBoxToCell` para asignar el rectángulo delimitador actual a la celda actual que se está procesando.</span><span class="sxs-lookup"><span data-stu-id="11aa6-335">After that, use the `MapBoundingBoxToCell` method to map the current bounding box to the current cell being processed.</span></span>

[!code-csharp [MapBoundingBoxes](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L169)]

<span data-ttu-id="11aa6-336">Antes de realizar cualquier procesamiento adicional, compruebe si el valor de confianza es mayor que el umbral proporcionado.</span><span class="sxs-lookup"><span data-stu-id="11aa6-336">Before doing any further processing, check whether your confidence value is greater than the threshold provided.</span></span> <span data-ttu-id="11aa6-337">Si no es así, procese el siguiente rectángulo delimitador.</span><span class="sxs-lookup"><span data-stu-id="11aa6-337">If not, process the next bounding box.</span></span>

[!code-csharp [CheckThreshold1](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L171-L172)]

<span data-ttu-id="11aa6-338">De lo contrario, continúe procesando la salida.</span><span class="sxs-lookup"><span data-stu-id="11aa6-338">Otherwise, continue processing the output.</span></span> <span data-ttu-id="11aa6-339">El paso siguiente consiste en obtener la distribución de probabilidad de las clases previstas para el rectángulo delimitador actual mediante el método `ExtractClasses`.</span><span class="sxs-lookup"><span data-stu-id="11aa6-339">The next step is to get the probability distribution of the predicted classes for the current bounding box using the `ExtractClasses` method.</span></span>

[!code-csharp [ExtractClasses](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L174)]

<span data-ttu-id="11aa6-340">A continuación, use el método `GetTopResult` para obtener el valor y el índice de la clase con la probabilidad más alta para el rectángulo actual y calcular su puntuación.</span><span class="sxs-lookup"><span data-stu-id="11aa6-340">Then, use the `GetTopResult` method to get the value and index of the class with the highest probability for the current box and compute its score.</span></span>

[!code-csharp [GetTopResult](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L176-L177)]

<span data-ttu-id="11aa6-341">Use `topScore` para conservar una vez más solo aquellos rectángulos delimitadores que estén por encima del umbral especificado.</span><span class="sxs-lookup"><span data-stu-id="11aa6-341">Use the `topScore` to once again keep only those bounding boxes that are above the specified threshold.</span></span>

[!code-csharp [CheckThreshold2](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L179-L180)]

<span data-ttu-id="11aa6-342">Por último, si el rectángulo delimitador actual supera el umbral, cree un nuevo objeto `BoundingBox` y agréguelo a la lista `boxes`.</span><span class="sxs-lookup"><span data-stu-id="11aa6-342">Finally, if the current bounding box exceeds the threshold, create a new `BoundingBox` object and add it to the `boxes` list.</span></span>

[!code-csharp [AddBBoxToList](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L182-L194)]

<span data-ttu-id="11aa6-343">Una vez que se hayan procesado todas las celdas de la imagen, devuelva la lista `boxes`.</span><span class="sxs-lookup"><span data-stu-id="11aa6-343">Once all cells in the image have been processed, return the `boxes` list.</span></span> <span data-ttu-id="11aa6-344">Agregue la siguiente instrucción return debajo del bucle for más exterior en el método `ParseOutputs`.</span><span class="sxs-lookup"><span data-stu-id="11aa6-344">Add the following return statement below the outer-most for-loop in the `ParseOutputs` method.</span></span>

[!code-csharp [ReturnBoxes](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L198)]

### <a name="filter-overlapping-boxes"></a><span data-ttu-id="11aa6-345">Filtrar los rectángulos superpuestos</span><span class="sxs-lookup"><span data-stu-id="11aa6-345">Filter overlapping boxes</span></span>

<span data-ttu-id="11aa6-346">Ahora que todos los rectángulos delimitadores de gran confianza se han extraído de la salida del modelo, es necesario realizar un filtrado adicional para quitar las imágenes superpuestas.</span><span class="sxs-lookup"><span data-stu-id="11aa6-346">Now that all of the highly confident bounding boxes have been extracted from the model output, additional filtering needs to be done to remove overlapping images.</span></span> <span data-ttu-id="11aa6-347">Agregue un método denominado `FilterBoundingBoxes` debajo del método `ParseOutputs`:</span><span class="sxs-lookup"><span data-stu-id="11aa6-347">Add a method called `FilterBoundingBoxes` below the `ParseOutputs` method:</span></span>

```csharp
public IList<YoloBoundingBox> FilterBoundingBoxes(IList<YoloBoundingBox> boxes, int limit, float threshold)
{

}
```

<span data-ttu-id="11aa6-348">Dentro del método `FilterBoundingBoxes`, empiece por crear una matriz igual al tamaño de los rectángulos detectados, y marque todas las ranuras como activas o listas para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="11aa6-348">Inside the `FilterBoundingBoxes` method, start off by creating an array equal to the size of detected boxes and marking all slots as active or ready for processing.</span></span>

[!code-csharp [InitActiveSlots](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L203-L207)]

<span data-ttu-id="11aa6-349">Después, ordene la lista que contiene los rectángulos delimitadores en orden descendente en función de la confianza.</span><span class="sxs-lookup"><span data-stu-id="11aa6-349">Then, sort the list containing your bounding boxes in descending order based on confidence.</span></span>

[!code-csharp [SortBoxes](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L209-L211)]

<span data-ttu-id="11aa6-350">Luego de eso, cree una lista que contenga los resultados filtrados.</span><span class="sxs-lookup"><span data-stu-id="11aa6-350">After that, create a list to hold the filtered results.</span></span>

[!code-csharp [InitFilterResult](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L213)]

<span data-ttu-id="11aa6-351">Comience a procesar cada rectángulo delimitador iterando cada uno de los rectángulos delimitadores.</span><span class="sxs-lookup"><span data-stu-id="11aa6-351">Begin processing each bounding box by iterating over each of the bounding boxes.</span></span>

```csharp
for (int i = 0; i < boxes.Count; i++)
{

}
```

<span data-ttu-id="11aa6-352">Dentro de este bucle for, compruebe si se puede procesar el rectángulo delimitador actual.</span><span class="sxs-lookup"><span data-stu-id="11aa6-352">Inside of this for-loop, check whether the current bounding box can be processed.</span></span>

```csharp
if (isActiveBoxes[i])
{

}
```

<span data-ttu-id="11aa6-353">Si es así, agregue el rectángulo delimitador a la lista de resultados.</span><span class="sxs-lookup"><span data-stu-id="11aa6-353">If so, add the bounding box to the list of results.</span></span> <span data-ttu-id="11aa6-354">Si los resultados superan el límite de rectángulos especificado que se van a extraer, interrumpa el bucle.</span><span class="sxs-lookup"><span data-stu-id="11aa6-354">If the results exceed the specified limit of boxes to be extracted, break out of the loop.</span></span> <span data-ttu-id="11aa6-355">Agregue el código siguiente dentro de la instrucción if.</span><span class="sxs-lookup"><span data-stu-id="11aa6-355">Add the following code inside the if-statement.</span></span>

[!code-csharp [AddFirstBBoxToResults](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L219-L223)]

<span data-ttu-id="11aa6-356">De lo contrario, fíjese en los rectángulos delimitadores adyacentes.</span><span class="sxs-lookup"><span data-stu-id="11aa6-356">Otherwise, look at the adjacent bounding boxes.</span></span> <span data-ttu-id="11aa6-357">Agregue el código siguiente debajo de la comprobación del límite del rectángulo.</span><span class="sxs-lookup"><span data-stu-id="11aa6-357">Add the following code below the box limit check.</span></span>

```csharp
for (var j = i + 1; j < boxes.Count; j++)
{

}
```

<span data-ttu-id="11aa6-358">Al igual que el primer rectángulo, si el rectángulo adyacente está activo o listo para procesarse, use el método `IntersectionOverUnion` para comprobar si el primer rectángulo y el segundo rectángulo superan el umbral especificado.</span><span class="sxs-lookup"><span data-stu-id="11aa6-358">Like the first box, if the adjacent box is active or ready to be processed, use the `IntersectionOverUnion` method to check whether the first box and the second box exceed the specified threshold.</span></span> <span data-ttu-id="11aa6-359">Agregue el código siguiente a su bucle for más interno.</span><span class="sxs-lookup"><span data-stu-id="11aa6-359">Add the following code to your innermost for-loop.</span></span>

[!code-csharp [IOUBBox](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L227-L239)]

<span data-ttu-id="11aa6-360">Fuera del bucle for más interno que comprueba los rectángulos delimitadores adyacentes, compruebe si hay rectángulos delimitadores restantes para procesar.</span><span class="sxs-lookup"><span data-stu-id="11aa6-360">Outside of the inner-most for-loop that checks adjacent bounding boxes, see whether there are any remaining bounding boxes to be processed.</span></span> <span data-ttu-id="11aa6-361">En caso contrario, interrumpa el bucle for externo.</span><span class="sxs-lookup"><span data-stu-id="11aa6-361">If not, break out of the outer for-loop.</span></span>

[!code-csharp [CheckActiveSlots](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L242-L243)]

<span data-ttu-id="11aa6-362">Por último, fuera del bucle for inicial del método `FilterBoundingBoxes`, devuelva los resultados:</span><span class="sxs-lookup"><span data-stu-id="11aa6-362">Finally, outside of the initial for-loop of the `FilterBoundingBoxes` method, return the results:</span></span>

[!code-csharp [ReturnFilteredBBox](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L246)]

<span data-ttu-id="11aa6-363">Perfecto.</span><span class="sxs-lookup"><span data-stu-id="11aa6-363">Great!</span></span> <span data-ttu-id="11aa6-364">Ahora es el momento de usar este código junto con el modelo para la puntuación.</span><span class="sxs-lookup"><span data-stu-id="11aa6-364">Now it's time to use this code along with the model for scoring.</span></span>

## <a name="use-the-model-for-scoring"></a><span data-ttu-id="11aa6-365">Uso del modelo para puntuación</span><span class="sxs-lookup"><span data-stu-id="11aa6-365">Use the model for scoring</span></span>

<span data-ttu-id="11aa6-366">Al igual que con el procesamiento posterior, hay algunos pasos en el procedimiento de puntuación.</span><span class="sxs-lookup"><span data-stu-id="11aa6-366">Just like with post-processing, there are a few steps in the scoring steps.</span></span> <span data-ttu-id="11aa6-367">Para ayudarlo con esto, agregue al proyecto una clase que contendrá la lógica de puntuación.</span><span class="sxs-lookup"><span data-stu-id="11aa6-367">To help with this, add a class that will contain the scoring logic to your project.</span></span>

1. <span data-ttu-id="11aa6-368">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="11aa6-368">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="11aa6-369">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *OnnxModelScorer.cs*.</span><span class="sxs-lookup"><span data-stu-id="11aa6-369">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *OnnxModelScorer.cs*.</span></span> <span data-ttu-id="11aa6-370">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="11aa6-370">Then, select the **Add** button.</span></span>

    <span data-ttu-id="11aa6-371">El archivo *OnnxModelScorer.cs* se abre en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="11aa6-371">The *OnnxModelScorer.cs* file opens in the code editor.</span></span> <span data-ttu-id="11aa6-372">Agregue la instrucción `using` siguiente al principio del archivo *OnnxModelScorer.cs*:</span><span class="sxs-lookup"><span data-stu-id="11aa6-372">Add the following `using` statement to the top of *OnnxModelScorer.cs*:</span></span>

    [!code-csharp [ScorerUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L1-L7)]

    <span data-ttu-id="11aa6-373">Dentro de la definición de la clase `OnnxModelScorer`, agregue las variables siguientes.</span><span class="sxs-lookup"><span data-stu-id="11aa6-373">Inside the `OnnxModelScorer` class definition, add the following variables.</span></span>

    [!code-csharp [InitScorerVars](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L13-L17)]

    <span data-ttu-id="11aa6-374">Justo debajo de eso, cree un constructor para la clase `OnnxModelScorer`que inicializará las variables definidas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="11aa6-374">Directly below that, create a constructor for the `OnnxModelScorer` class that will initialize the previously defined variables.</span></span>

    [!code-csharp [ScorerCtor](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L19-L24)]

    <span data-ttu-id="11aa6-375">Una vez creado el constructor, defina un par de estructuras que contengan variables relacionadas con la configuración de la imagen y el modelo.</span><span class="sxs-lookup"><span data-stu-id="11aa6-375">Once you have created the constructor, define a couple of structs that contain variables related to the image and model settings.</span></span> <span data-ttu-id="11aa6-376">Cree una estructura denominada `ImageNetSettings` para que contenga la altura y el ancho esperados como entrada para el modelo.</span><span class="sxs-lookup"><span data-stu-id="11aa6-376">Create a struct called `ImageNetSettings` to contain the height and width expected as input for the model.</span></span>

    [!code-csharp [ImageNetSettingStruct](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L26-L30)]

    <span data-ttu-id="11aa6-377">Después, cree otra estructura denominada `TinyYoloModelSettings` que contenga los nombres de las capas de entrada y salida del modelo.</span><span class="sxs-lookup"><span data-stu-id="11aa6-377">After that, create another struct called `TinyYoloModelSettings` that contains the names of the input and output layers of the model.</span></span> <span data-ttu-id="11aa6-378">Para visualizar el nombre de las capas de entrada y salida del modelo, puede usar una herramienta como [Netron.](https://github.com/lutzroeder/netron)</span><span class="sxs-lookup"><span data-stu-id="11aa6-378">To visualize the name of the input and output layers of the model, you can use a tool like [Netron](https://github.com/lutzroeder/netron).</span></span>

    [!code-csharp [YoloSettingsStruct](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L32-L43)]

    <span data-ttu-id="11aa6-379">A continuación, cree el primer conjunto de métodos que usará para la puntuación.</span><span class="sxs-lookup"><span data-stu-id="11aa6-379">Next, create the first set of methods use for scoring.</span></span> <span data-ttu-id="11aa6-380">Cree el método `LoadModel` dentro de la clase `OnnxModelScorer`.</span><span class="sxs-lookup"><span data-stu-id="11aa6-380">Create the `LoadModel` method inside of your `OnnxModelScorer` class.</span></span>

    ```csharp
    private ITransformer LoadModel(string modelLocation)
    {

    }
    ```

    <span data-ttu-id="11aa6-381">Dentro del método `LoadModel`, agregue el código siguiente para el registro.</span><span class="sxs-lookup"><span data-stu-id="11aa6-381">Inside the `LoadModel` method, add the following code for logging.</span></span>

    [!code-csharp [LoadModelLog](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L47-L49)]

    <span data-ttu-id="11aa6-382">Es necesario que las canalizaciones ML.NET conozcan el esquema de datos en el que van a funcionar cuando se llame al método [`Fit`](xref:Microsoft.ML.IEstimator%601.Fit*).</span><span class="sxs-lookup"><span data-stu-id="11aa6-382">ML.NET pipelines need to know the data schema to operate on when the [`Fit`](xref:Microsoft.ML.IEstimator%601.Fit*) method is called.</span></span> <span data-ttu-id="11aa6-383">En este caso, se usará un proceso similar al de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="11aa6-383">In this case, a process similar to training will be used.</span></span> <span data-ttu-id="11aa6-384">Sin embargo, dado que no se está produciendo ningún entrenamiento real, es aceptable usar un [`IDataView`](xref:Microsoft.ML.IDataView) vacío.</span><span class="sxs-lookup"><span data-stu-id="11aa6-384">However, because no actual training is happening, it is acceptable to use an empty [`IDataView`](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="11aa6-385">Cree un nuevo [`IDataView`](xref:Microsoft.ML.IDataView) para la canalización a partir de una lista vacía.</span><span class="sxs-lookup"><span data-stu-id="11aa6-385">Create a new [`IDataView`](xref:Microsoft.ML.IDataView) for the pipeline from an empty list.</span></span>

    [!code-csharp [LoadEmptyIDV](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L52)]

    <span data-ttu-id="11aa6-386">Luego de eso, defina la canalización.</span><span class="sxs-lookup"><span data-stu-id="11aa6-386">Below that, define the pipeline.</span></span> <span data-ttu-id="11aa6-387">La canalización constará de cuatro transformaciones.</span><span class="sxs-lookup"><span data-stu-id="11aa6-387">The pipeline will consist of four transforms.</span></span>

    - <span data-ttu-id="11aa6-388">[`LoadImages`](xref:Microsoft.ML.ImageEstimatorsCatalog.LoadImages*) carga la imagen como mapa de bits.</span><span class="sxs-lookup"><span data-stu-id="11aa6-388">[`LoadImages`](xref:Microsoft.ML.ImageEstimatorsCatalog.LoadImages*) loads the image as a Bitmap.</span></span>
    - <span data-ttu-id="11aa6-389">[`ResizeImages`](xref:Microsoft.ML.ImageEstimatorsCatalog.ResizeImages*) cambia la escala de la imagen al tamaño especificado (en este caso, `416 x 416`).</span><span class="sxs-lookup"><span data-stu-id="11aa6-389">[`ResizeImages`](xref:Microsoft.ML.ImageEstimatorsCatalog.ResizeImages*) rescales the image to the size specified (in this case, `416 x 416`).</span></span>
    - <span data-ttu-id="11aa6-390">[`ExtractPixels`](xref:Microsoft.ML.ImageEstimatorsCatalog.ExtractPixels*) cambia la representación en píxeles de la imagen de un mapa de bits a un vector numérico.</span><span class="sxs-lookup"><span data-stu-id="11aa6-390">[`ExtractPixels`](xref:Microsoft.ML.ImageEstimatorsCatalog.ExtractPixels*) changes the pixel representation of the image from a Bitmap to a numerical vector.</span></span>
    - <span data-ttu-id="11aa6-391">[`ApplyOnnxModel`](xref:Microsoft.ML.OnnxCatalog.ApplyOnnxModel*) carga el modelo de ONNX y lo usa para puntuar los datos proporcionados.</span><span class="sxs-lookup"><span data-stu-id="11aa6-391">[`ApplyOnnxModel`](xref:Microsoft.ML.OnnxCatalog.ApplyOnnxModel*) loads the ONNX model and uses it to score on the data provided.</span></span>

    <span data-ttu-id="11aa6-392">Defina la canalización en el método `LoadModel` debajo de la variable `data`.</span><span class="sxs-lookup"><span data-stu-id="11aa6-392">Define your pipeline in the `LoadModel` method below the `data` variable.</span></span>

    [!code-csharp [ScoringPipeline](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L55-L58)]

    <span data-ttu-id="11aa6-393">Ahora es el momento de crear una instancia del modelo para la puntuación.</span><span class="sxs-lookup"><span data-stu-id="11aa6-393">Now it's time to instantiate the model for scoring.</span></span> <span data-ttu-id="11aa6-394">Llame al método [`Fit`](xref:Microsoft.ML.IEstimator%601.Fit*) en la canalización y devuélvalo para seguir procesándolo.</span><span class="sxs-lookup"><span data-stu-id="11aa6-394">Call the [`Fit`](xref:Microsoft.ML.IEstimator%601.Fit*) method on the pipeline and return it for further processing.</span></span>

    [!code-csharp [FitReturnModel](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L61-L63)]

<span data-ttu-id="11aa6-395">Una vez que el modelo esté cargado, podrá usarse para hacer predicciones.</span><span class="sxs-lookup"><span data-stu-id="11aa6-395">Once the model is loaded, it can then be used to make predictions.</span></span> <span data-ttu-id="11aa6-396">Para facilitar este proceso, cree un método denominado `PredictDataUsingModel` debajo del método `LoadModel`.</span><span class="sxs-lookup"><span data-stu-id="11aa6-396">To facilitate that process, create a method called `PredictDataUsingModel` below the `LoadModel` method.</span></span>

```csharp
private IEnumerable<float[]> PredictDataUsingModel(IDataView testData, ITransformer model)
{

}
```

<span data-ttu-id="11aa6-397">Dentro de `PredictDataUsingModel`, agregue el código siguiente para el registro.</span><span class="sxs-lookup"><span data-stu-id="11aa6-397">Inside the `PredictDataUsingModel`, add the following code for logging.</span></span>

[!code-csharp [PredictDataLog](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L68-L71)]

<span data-ttu-id="11aa6-398">A continuación, use el método [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) para puntuar los datos.</span><span class="sxs-lookup"><span data-stu-id="11aa6-398">Then, use the [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) method to score the data.</span></span>

[!code-csharp [ScoreImages](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L73)]

<span data-ttu-id="11aa6-399">Extraiga las probabilidades previstas y devuélvalas para su procesamiento adicional.</span><span class="sxs-lookup"><span data-stu-id="11aa6-399">Extract the predicted probabilities and return them for additional processing.</span></span>

[!code-csharp [ReturnModelOutput](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L75-L77)]

<span data-ttu-id="11aa6-400">Ahora que ambos pasos están configurados, combínelos en un único método.</span><span class="sxs-lookup"><span data-stu-id="11aa6-400">Now that both steps are set up, combine them into a single method.</span></span> <span data-ttu-id="11aa6-401">Debajo del método `PredictDataUsingModel`, agregue un nuevo método denominado `Score`.</span><span class="sxs-lookup"><span data-stu-id="11aa6-401">Below the `PredictDataUsingModel` method, add a new method called `Score`.</span></span>

[!code-csharp [ScoreMethod](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L80-L85)]

<span data-ttu-id="11aa6-402">Ya casi lo tenemos.</span><span class="sxs-lookup"><span data-stu-id="11aa6-402">Almost there!</span></span> <span data-ttu-id="11aa6-403">Ahora es el momento de ponerlo todo en práctica.</span><span class="sxs-lookup"><span data-stu-id="11aa6-403">Now it's time to put it all to use.</span></span>

## <a name="detect-objects"></a><span data-ttu-id="11aa6-404">Detectar objetos</span><span class="sxs-lookup"><span data-stu-id="11aa6-404">Detect objects</span></span>

<span data-ttu-id="11aa6-405">Ahora que ha completado toda la configuración, es el momento de detectar algunos objetos.</span><span class="sxs-lookup"><span data-stu-id="11aa6-405">Now that all of the setup is complete, it's time to detect some objects.</span></span> <span data-ttu-id="11aa6-406">Para empezar, agregue referencias al puntuador y al analizador en la clase *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="11aa6-406">Start off by adding references to the scorer and parser in your *Program.cs* class.</span></span>

[!code-csharp [ReferenceScorerParser](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L8-L9)]

### <a name="score-and-parse-model-outputs"></a><span data-ttu-id="11aa6-407">Resultados del modelo de puntuación y análisis</span><span class="sxs-lookup"><span data-stu-id="11aa6-407">Score and parse model outputs</span></span>

<span data-ttu-id="11aa6-408">Dentro del método `Main` de la clase *Program.cs*, agregue una instrucción try-catch.</span><span class="sxs-lookup"><span data-stu-id="11aa6-408">Inside the `Main` method of your *Program.cs* class, add a try-catch statement.</span></span>

```csharp
try
{

}
catch (Exception ex)
{
    Console.WriteLine(ex.ToString());
}
```

<span data-ttu-id="11aa6-409">Dentro del bloque `try`, empiece a implementar la lógica de detección de objetos.</span><span class="sxs-lookup"><span data-stu-id="11aa6-409">Inside of the `try` block, start implementing the object detection logic.</span></span> <span data-ttu-id="11aa6-410">En primer lugar, cargue los datos en un [`IDataView`](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="11aa6-410">First, load the data into an [`IDataView`](xref:Microsoft.ML.IDataView).</span></span>

[!code-csharp [LoadData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L29-L30)]

<span data-ttu-id="11aa6-411">Luego, cree una instancia de `OnnxModelScorer` y úsela para puntuar los datos cargados.</span><span class="sxs-lookup"><span data-stu-id="11aa6-411">Then, create an instance of `OnnxModelScorer` and use it to score the loaded data.</span></span>

[!code-csharp [ScoreData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L33-L36)]

<span data-ttu-id="11aa6-412">Ahora es el momento de completar el paso de procesamiento posterior.</span><span class="sxs-lookup"><span data-stu-id="11aa6-412">Now it's time for the post-processing step.</span></span> <span data-ttu-id="11aa6-413">Cree una instancia de `YoloOutputParser` y úsela para procesar la salida del modelo.</span><span class="sxs-lookup"><span data-stu-id="11aa6-413">Create an instance of `YoloOutputParser` and use it to process the model output.</span></span>

[!code-csharp [ParsePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L39-L44)]

<span data-ttu-id="11aa6-414">Una vez que se haya procesado la salida del modelo, es el momento de dibujar los rectángulos delimitadores en las imágenes.</span><span class="sxs-lookup"><span data-stu-id="11aa6-414">Once the model output has been processed, it's time to draw the bounding boxes on the images.</span></span>

### <a name="visualize-predictions"></a><span data-ttu-id="11aa6-415">Visualización de predicciones</span><span class="sxs-lookup"><span data-stu-id="11aa6-415">Visualize predictions</span></span>

<span data-ttu-id="11aa6-416">Una vez que el modelo ha puntuado las imágenes y se han procesado los resultados, hay que dibujar los rectángulos delimitadores en la imagen.</span><span class="sxs-lookup"><span data-stu-id="11aa6-416">After the model has scored the images and the outputs have been processed, the bounding boxes have to be drawn on the image.</span></span> <span data-ttu-id="11aa6-417">Para ello, agregue un método denominado `DrawBoundingBox` debajo del método `GetAbsolutePath` dentro de *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="11aa6-417">To do so, add a method called `DrawBoundingBox` below the `GetAbsolutePath` method inside of *Program.cs*.</span></span>

```csharp
private static void DrawBoundingBox(string inputImageLocation, string outputImageLocation, string imageName, IList<YoloBoundingBox> filteredBoundingBoxes)
{

}
```

<span data-ttu-id="11aa6-418">En primer lugar, cargue la imagen y obtenga las dimensiones de altura y ancho en el método `DrawBoundingBox`.</span><span class="sxs-lookup"><span data-stu-id="11aa6-418">First, load the image and get the height and width dimensions in the `DrawBoundingBox` method.</span></span>

[!code-csharp [LoadImage](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L78-L81)]

<span data-ttu-id="11aa6-419">A continuación, cree un bucle for-each para iterar por cada uno de los rectángulos delimitadores detectados por el modelo.</span><span class="sxs-lookup"><span data-stu-id="11aa6-419">Then, create a for-each loop to iterate over each of the bounding boxes detected by the model.</span></span>

```csharp
foreach (var box in filteredBoundingBoxes)
{

}
```

<span data-ttu-id="11aa6-420">Dentro del bucle for-each, obtenga las dimensiones del rectángulo delimitador.</span><span class="sxs-lookup"><span data-stu-id="11aa6-420">Inside of the for-each loop, get the dimensions of the bounding box.</span></span>

[!code-csharp [GetBBoxDimensions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L86-L89)]

<span data-ttu-id="11aa6-421">Dado que las dimensiones del rectángulo delimitador corresponden a la entrada del modelo de `416 x 416`, escale las dimensiones del rectángulo delimitador para que coincidan con el tamaño real de la imagen.</span><span class="sxs-lookup"><span data-stu-id="11aa6-421">Because the dimensions of the bounding box correspond to the model input of `416 x 416`, scale the bounding box dimensions to match the actual size of the image.</span></span>

[!code-csharp [ScaleImage](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L92-L95)]

<span data-ttu-id="11aa6-422">Luego, defina una plantilla para el texto que aparecerá sobre cada rectángulo delimitador.</span><span class="sxs-lookup"><span data-stu-id="11aa6-422">Then, define a template for text that will appear above each bounding box.</span></span> <span data-ttu-id="11aa6-423">El texto contendrá la clase del objeto dentro del rectángulo delimitador correspondiente, así como la confianza.</span><span class="sxs-lookup"><span data-stu-id="11aa6-423">The text will contain the class of the object inside of the respective bounding box as well as the confidence.</span></span>

[!code-csharp [DefineBBoxText](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L98)]

<span data-ttu-id="11aa6-424">Para dibujar en la imagen, conviértala en un objeto [`Graphics`](xref:System.Drawing.Graphics).</span><span class="sxs-lookup"><span data-stu-id="11aa6-424">In order to draw on the image, convert it to a [`Graphics`](xref:System.Drawing.Graphics) object.</span></span>

```csharp
using (Graphics thumbnailGraphic = Graphics.FromImage(image))
{

}
```

<span data-ttu-id="11aa6-425">Dentro del bloque de código `using`, ajuste la configuración del objeto [`Graphics`](xref:System.Drawing.Graphics) del gráfico.</span><span class="sxs-lookup"><span data-stu-id="11aa6-425">Inside the `using` code block, tune the graphic's [`Graphics`](xref:System.Drawing.Graphics) object settings.</span></span>

[!code-csharp [TuneGraphicSettings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L102-L104)]

<span data-ttu-id="11aa6-426">Luego de eso, establezca las opciones de fuente y color para el texto y el rectángulo delimitador.</span><span class="sxs-lookup"><span data-stu-id="11aa6-426">Below that, set the font and color options for the text and bounding box.</span></span>

[!code-csharp [SetColorOptions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L106-L114)]

<span data-ttu-id="11aa6-427">Cree y rellene un rectángulo sobre el rectángulo delimitador para que contenga el texto mediante el método [`FillRectangle`](xref:System.Drawing.Graphics.FillRectangle*).</span><span class="sxs-lookup"><span data-stu-id="11aa6-427">Create and fill a rectangle above the bounding box to contain the text using the [`FillRectangle`](xref:System.Drawing.Graphics.FillRectangle*) method.</span></span> <span data-ttu-id="11aa6-428">Esto le ayudará a contrastar el texto y mejorar la legibilidad.</span><span class="sxs-lookup"><span data-stu-id="11aa6-428">This will help contrast the text and improve readability.</span></span>

[!code-csharp [DrawTextBackground](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L117)]

<span data-ttu-id="11aa6-429">A continuación, dibuje el texto y el rectángulo delimitador en la imagen con los métodos [`DrawString`](xref:System.Drawing.Graphics.DrawString*) y [`DrawRectangle`](xref:System.Drawing.Graphics.DrawRectangle*).</span><span class="sxs-lookup"><span data-stu-id="11aa6-429">Then, Draw the text and bounding box on the image using the [`DrawString`](xref:System.Drawing.Graphics.DrawString*) and [`DrawRectangle`](xref:System.Drawing.Graphics.DrawRectangle*) methods.</span></span>

[!code-csharp [DrawClassAndBBox](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L118-L121)]

<span data-ttu-id="11aa6-430">Fuera del bucle for-each, agregue código para guardar las imágenes en `outputDirectory`.</span><span class="sxs-lookup"><span data-stu-id="11aa6-430">Outside of the for-each loop, add code to save the images in the `outputDirectory`.</span></span>

[!code-csharp [SaveImage](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L125-L130)]

<span data-ttu-id="11aa6-431">Para recibir información adicional de que la aplicación está haciendo predicciones según lo esperado en tiempo de ejecución, agregue un método denominado `LogDetectedObjects` debajo del método `DrawBoundingBox` en el archivo *Program.cs* para generar los objetos detectados en la consola.</span><span class="sxs-lookup"><span data-stu-id="11aa6-431">For additional feedback that the application is making predictions as expected at runtime, add a method called `LogDetectedObjects` below the `DrawBoundingBox` method in the *Program.cs* file to output the detected objects to the console.</span></span>

[!code-csharp [LogOutputs](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L133-L143)]

<span data-ttu-id="11aa6-432">Ahora que tiene métodos auxiliares para crear comentarios visuales a partir de las predicciones, agregue un bucle for para iterar en cada una de las imágenes puntuadas.</span><span class="sxs-lookup"><span data-stu-id="11aa6-432">Now that you have helper methods to create visual feedback from the predictions, add a for-loop to iterate over each of the scored images.</span></span>

```csharp
for (var i = 0; i < images.Count(); i++)
{

}
```

<span data-ttu-id="11aa6-433">Dentro del bucle for, obtenga el nombre del archivo de imagen y los rectángulos delimitadores asociados a él.</span><span class="sxs-lookup"><span data-stu-id="11aa6-433">Inside of the for-loop, get the name of the image file and the bounding boxes associated with it.</span></span>

[!code-csharp [GetImageFileName](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L49-L50)]

<span data-ttu-id="11aa6-434">A continuación, use el método `DrawBoundingBox` para dibujar los rectángulos delimitadores en la imagen.</span><span class="sxs-lookup"><span data-stu-id="11aa6-434">Below that, use the `DrawBoundingBox` method to draw the bounding boxes on the image.</span></span>

[!code-csharp [DrawBBoxes](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L52)]

<span data-ttu-id="11aa6-435">Por último, use el método `LogDetectedObjects` para generar predicciones en la consola.</span><span class="sxs-lookup"><span data-stu-id="11aa6-435">Lastly, use the `LogDetectedObjects` method to output predictions to the console.</span></span>

[!code-csharp [LogPredictionsOutput](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L54)]

<span data-ttu-id="11aa6-436">Después de la instrucción try-catch, agregue lógica adicional para indicar que el proceso ha terminado de ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="11aa6-436">After the try-catch statement, add additional logic to indicate the process is done running.</span></span>

[!code-csharp [EndProcessLog](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L62-L63)]

<span data-ttu-id="11aa6-437">Ya está.</span><span class="sxs-lookup"><span data-stu-id="11aa6-437">That's it!</span></span>

## <a name="results"></a><span data-ttu-id="11aa6-438">Resultados</span><span class="sxs-lookup"><span data-stu-id="11aa6-438">Results</span></span>

<span data-ttu-id="11aa6-439">Después de seguir los pasos anteriores, ejecute la aplicación de consola (Ctrl + F5).</span><span class="sxs-lookup"><span data-stu-id="11aa6-439">After following the previous steps, run your console app (Ctrl + F5).</span></span> <span data-ttu-id="11aa6-440">Los resultados deberían ser similares a la salida siguiente.</span><span class="sxs-lookup"><span data-stu-id="11aa6-440">Your results should be similar to the following output.</span></span> <span data-ttu-id="11aa6-441">Es posible que vea advertencias o mensajes de procesamiento, si bien se han quitado de los resultados siguientes para mayor claridad.</span><span class="sxs-lookup"><span data-stu-id="11aa6-441">You may see warnings or processing messages, but these messages have been removed from the following results for clarity.</span></span>

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

<span data-ttu-id="11aa6-442">Para ver las imágenes con rectángulos delimitadores, desplácese hasta el directorio `assets/images/output/`.</span><span class="sxs-lookup"><span data-stu-id="11aa6-442">To see the images with bounding boxes, navigate to the `assets/images/output/` directory.</span></span> <span data-ttu-id="11aa6-443">A continuación se muestra un ejemplo de una de las imágenes procesadas.</span><span class="sxs-lookup"><span data-stu-id="11aa6-443">Below is a sample from one of the processed images.</span></span>

![Imagen procesada de ejemplo de un comedor](./media/object-detection-onnx/dinning-room-table-chairs.png)

<span data-ttu-id="11aa6-445">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="11aa6-445">Congratulations!</span></span> <span data-ttu-id="11aa6-446">Ha creado correctamente un modelo de Machine Learning para la detección de objetos al reutilizar un modelo de `ONNX` entrenado previamente en ML.NET.</span><span class="sxs-lookup"><span data-stu-id="11aa6-446">You've now successfully built a machine learning model for object detection by reusing a pre-trained `ONNX` model in ML.NET.</span></span>

<span data-ttu-id="11aa6-447">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx).</span><span class="sxs-lookup"><span data-stu-id="11aa6-447">You can find the source code for this tutorial at the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx) repository.</span></span>

<span data-ttu-id="11aa6-448">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="11aa6-448">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="11aa6-449">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="11aa6-449">Understand the problem</span></span>
> - <span data-ttu-id="11aa6-450">Conocer qué es ONNX y cómo funciona con ML.NET</span><span class="sxs-lookup"><span data-stu-id="11aa6-450">Learn what ONNX is and how it works with ML.NET</span></span>
> - <span data-ttu-id="11aa6-451">Entender el modelo</span><span class="sxs-lookup"><span data-stu-id="11aa6-451">Understand the model</span></span>
> - <span data-ttu-id="11aa6-452">Volver a usar el modelo entrenado previamente</span><span class="sxs-lookup"><span data-stu-id="11aa6-452">Reuse the pre-trained model</span></span>
> - <span data-ttu-id="11aa6-453">Detectar objetos con un modelo cargado</span><span class="sxs-lookup"><span data-stu-id="11aa6-453">Detect objects with a loaded model</span></span>

<span data-ttu-id="11aa6-454">Consulte el repositorio de GitHub con ejemplos de Machine Learning para explorar un ejemplo expandido de detección de objetos.</span><span class="sxs-lookup"><span data-stu-id="11aa6-454">Check out the Machine Learning samples GitHub repository to explore an expanded object detection sample.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="11aa6-455">Repositorio dotnet/machinelearning-samples de GitHub</span><span class="sxs-lookup"><span data-stu-id="11aa6-455">dotnet/machinelearning-samples GitHub repository</span></span>](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx)
