---
title: 'Tutorial: Detección de objetos mediante aprendizaje profundo con ONNX y ML.NET'
description: En este tutorial se muestra cómo usar en ML.NET un modelo de aprendizaje profundo de ONNX entrenado previamente para detectar objetos en imágenes.
author: luisquintanilla
ms.author: luquinta
ms.date: 08/01/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: e44ea5795beb90bafe3faf0bafb463d49ba1fc41
ms.sourcegitcommit: 9ee6cd851b6e176a5811ea28ed0d5935c71950f9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/09/2019
ms.locfileid: "68868722"
---
# <a name="tutorial-detect-objects-using-onnx-in-mlnet"></a><span data-ttu-id="2402f-103">Tutorial: Detección de objetos con ONNX en ML.NET</span><span class="sxs-lookup"><span data-stu-id="2402f-103">Tutorial: Detect objects using ONNX in ML.NET</span></span>

<span data-ttu-id="2402f-104">Aprenda a usar en ML.NET un modelo ONNX previamente entrenado para detectar objetos en imágenes.</span><span class="sxs-lookup"><span data-stu-id="2402f-104">Learn how to use a pre-trained ONNX model in ML.NET to detect objects in images.</span></span>

<span data-ttu-id="2402f-105">Entrenar un modelo de detección de objetos desde cero requiere establecer millones de parámetros, una enorme cantidad de datos de aprendizaje etiquetados y una gran cantidad de recursos informáticos (cientos de horas de GPU).</span><span class="sxs-lookup"><span data-stu-id="2402f-105">Training an object detection model from scratch requires setting millions of parameters, a large amount of labeled training data and a vast amount of compute resources (hundreds of GPU hours).</span></span> <span data-ttu-id="2402f-106">El uso de un modelo entrenado previamente le permite abreviar el proceso de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="2402f-106">Using a pre-trained model allows you to shortcut the training process.</span></span>

<span data-ttu-id="2402f-107">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="2402f-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="2402f-108">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="2402f-108">Understand the problem</span></span>
> * <span data-ttu-id="2402f-109">Conocer qué es ONNX y cómo funciona con ML.NET</span><span class="sxs-lookup"><span data-stu-id="2402f-109">Learn what ONNX is and how it works with ML.NET</span></span>
> * <span data-ttu-id="2402f-110">Entender el modelo</span><span class="sxs-lookup"><span data-stu-id="2402f-110">Understand the model</span></span>
> * <span data-ttu-id="2402f-111">Volver a usar el modelo entrenado previamente</span><span class="sxs-lookup"><span data-stu-id="2402f-111">Reuse the pre-trained model</span></span>
> * <span data-ttu-id="2402f-112">Detectar objetos con un modelo cargado</span><span class="sxs-lookup"><span data-stu-id="2402f-112">Detect objects with a loaded model</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="2402f-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2402f-113">Pre-requisites</span></span>

- <span data-ttu-id="2402f-114">[Visual Studio 2017 15.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.</span><span class="sxs-lookup"><span data-stu-id="2402f-114">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>
- [<span data-ttu-id="2402f-115">Paquete NuGet de Microsoft.ML</span><span class="sxs-lookup"><span data-stu-id="2402f-115">Microsoft.ML NuGet Package</span></span>](https://www.nuget.org/packages/Microsoft.ML/)
- [<span data-ttu-id="2402f-116">Paquete NuGet de Microsoft.ML.ImageAnalytics</span><span class="sxs-lookup"><span data-stu-id="2402f-116">Microsoft.ML.ImageAnalytics NuGet Package</span></span>](https://www.nuget.org/packages/Microsoft.ML.ImageAnalytics/)
- [<span data-ttu-id="2402f-117">Paquete NuGet de Microsoft.ML.OnnxTransformer</span><span class="sxs-lookup"><span data-stu-id="2402f-117">Microsoft.ML.OnnxTransformer NuGet Package</span></span>](https://www.nuget.org/packages/Microsoft.ML.OnnxTransformer/)
- [<span data-ttu-id="2402f-118">Modelo previamente entrenado de Tiny YOLOv2</span><span class="sxs-lookup"><span data-stu-id="2402f-118">Tiny YOLOv2 pre-trained model</span></span>](https://github.com/onnx/models/tree/master/tiny_yolov2)
- <span data-ttu-id="2402f-119">[Netron](https://github.com/lutzroeder/netron) (opcional)</span><span class="sxs-lookup"><span data-stu-id="2402f-119">[Netron](https://github.com/lutzroeder/netron) (optional)</span></span>

## <a name="onnx-object-detection-sample-overview"></a><span data-ttu-id="2402f-120">Información general del ejemplo de detección de objetos de ONNX</span><span class="sxs-lookup"><span data-stu-id="2402f-120">ONNX object detection sample overview</span></span>

<span data-ttu-id="2402f-121">En este ejemplo se crea una aplicación de consola de .NET Core que detecta objetos dentro de una imagen mediante un modelo de aprendizaje profundo de ONNX previamente entrenado.</span><span class="sxs-lookup"><span data-stu-id="2402f-121">This sample creates a .NET core console application that detects objects within an image using a pre-trained deep learning ONNX model.</span></span> <span data-ttu-id="2402f-122">El código de este ejemplo se puede encontrar en el [repositorio dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="2402f-122">The code for this sample can be found on the [dotnet/machinelearning-samples repository](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx) on GitHub.</span></span>

## <a name="what-is-object-detection"></a><span data-ttu-id="2402f-123">¿Qué es la detección de objetos?</span><span class="sxs-lookup"><span data-stu-id="2402f-123">What is object detection?</span></span>

<span data-ttu-id="2402f-124">La detección de objetos es un problema de visión informática.</span><span class="sxs-lookup"><span data-stu-id="2402f-124">Object detection is a computer vision problem.</span></span> <span data-ttu-id="2402f-125">Si bien está estrechamente relacionada con la clasificación de imágenes, la detección de objetos realiza la clasificación de imágenes a una escala más granular.</span><span class="sxs-lookup"><span data-stu-id="2402f-125">While closely related to image classification, object detection performs image classification at a more granular scale.</span></span> <span data-ttu-id="2402f-126">La detección de objetos ubica _y_ categoriza entidades dentro de las imágenes.</span><span class="sxs-lookup"><span data-stu-id="2402f-126">Object detection both locates _and_ categorizes entities within images.</span></span> <span data-ttu-id="2402f-127">Use la detección de objetos cuando las imágenes contengan varios objetos de tipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="2402f-127">Use object detection when images contain multiple objects of different types.</span></span>

![](./media/object-detection-onnx/img-classification-obj-detection.PNG)

<span data-ttu-id="2402f-128">Entre algunos casos de uso para la detección de objetos se incluyen:</span><span class="sxs-lookup"><span data-stu-id="2402f-128">Some use cases for object detection include:</span></span>

- <span data-ttu-id="2402f-129">Automóviles sin conductor</span><span class="sxs-lookup"><span data-stu-id="2402f-129">Self-Driving Cars</span></span>
- <span data-ttu-id="2402f-130">Robótica</span><span class="sxs-lookup"><span data-stu-id="2402f-130">Robotics</span></span>
- <span data-ttu-id="2402f-131">Detección de caras</span><span class="sxs-lookup"><span data-stu-id="2402f-131">Face Detection</span></span>
- <span data-ttu-id="2402f-132">Seguridad en el lugar de trabajo</span><span class="sxs-lookup"><span data-stu-id="2402f-132">Workplace Safety</span></span>
- <span data-ttu-id="2402f-133">Recuento de objetos</span><span class="sxs-lookup"><span data-stu-id="2402f-133">Object Counting</span></span>
- <span data-ttu-id="2402f-134">Reconocimiento de actividades</span><span class="sxs-lookup"><span data-stu-id="2402f-134">Activity Recognition</span></span>

## <a name="select-a-deep-learning-model"></a><span data-ttu-id="2402f-135">Selección de un modelo de aprendizaje profundo</span><span class="sxs-lookup"><span data-stu-id="2402f-135">Select a deep learning model</span></span>

<span data-ttu-id="2402f-136">El aprendizaje profundo es un subconjunto del aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="2402f-136">Deep learning is a subset of machine learning.</span></span> <span data-ttu-id="2402f-137">Para entrenar modelos de aprendizaje profundo, se necesitan grandes cantidades de datos.</span><span class="sxs-lookup"><span data-stu-id="2402f-137">To train deep learning models, large quantities of data are required.</span></span> <span data-ttu-id="2402f-138">Los patrones de los datos se representan mediante una serie de capas.</span><span class="sxs-lookup"><span data-stu-id="2402f-138">Patterns in the data are represented by a series of layers.</span></span> <span data-ttu-id="2402f-139">Las relaciones de los datos se codifican como conexiones entre las capas, que contienen ponderaciones.</span><span class="sxs-lookup"><span data-stu-id="2402f-139">The relationships in the data are encoded as connections between the layers containing weights.</span></span> <span data-ttu-id="2402f-140">Cuanto mayor sea la ponderación, más fuerte será la relación.</span><span class="sxs-lookup"><span data-stu-id="2402f-140">The higher the weight, the stronger the relationship.</span></span> <span data-ttu-id="2402f-141">En conjunto, esta serie de capas y conexiones se conocen como redes neuronales artificiales.</span><span class="sxs-lookup"><span data-stu-id="2402f-141">Collectively, this series of layers and connections are known as artificial neural networks.</span></span> <span data-ttu-id="2402f-142">Cuantas más capas haya en una red, "más profunda" será, lo que la convierte en una red neuronal profunda.</span><span class="sxs-lookup"><span data-stu-id="2402f-142">The more layers in a network, the "deeper" it is, making it a deep neural network.</span></span> 

<span data-ttu-id="2402f-143">Hay diferentes tipos de redes neuronales, las más comunes son perceptrón multicapa (MLP), red neuronal circunvolucional (CNN) y red neuronal recurrente (RNN).</span><span class="sxs-lookup"><span data-stu-id="2402f-143">There are different types of neural networks, the most common being Multi-Layered Perceptron (MLP), Convolutional Neural Network (CNN) and Recurrent Neural Network (RNN).</span></span> <span data-ttu-id="2402f-144">La más básica es MLP, que asigna un conjunto de entradas a un conjunto de salidas.</span><span class="sxs-lookup"><span data-stu-id="2402f-144">The most basic is the MLP, which maps a set of inputs to a set of outputs.</span></span> <span data-ttu-id="2402f-145">Esta red neuronal es la adecuada cuando los datos no tienen un componente espacial ni temporal.</span><span class="sxs-lookup"><span data-stu-id="2402f-145">This neural network is good when the data does not have a spatial or time component.</span></span> <span data-ttu-id="2402f-146">CNN aprovecha las capas circunvolucionales para procesar la información espacial contenida en los datos.</span><span class="sxs-lookup"><span data-stu-id="2402f-146">The CNN makes use of convolutional layers to process spatial information contained in the data.</span></span> <span data-ttu-id="2402f-147">Un buen caso de uso de las CNN es el procesamiento de imágenes para detectar la presencia de una característica en una región de una imagen (por ejemplo, ¿hay una nariz en el centro de una imagen?).</span><span class="sxs-lookup"><span data-stu-id="2402f-147">A good use case for CNNs is image processing to detect the presence of a feature in a region of an image (for example, is there a nose in the center of an image?).</span></span> <span data-ttu-id="2402f-148">Por último, las RNN permiten la persistencia del estado o la memoria que se va a usar como entrada.</span><span class="sxs-lookup"><span data-stu-id="2402f-148">Finally, RNNs allow for the persistence of state or memory to be used as input.</span></span> <span data-ttu-id="2402f-149">Las RNN se usan para el análisis de series temporales, donde la ordenación secuencial y el contexto de eventos son importantes.</span><span class="sxs-lookup"><span data-stu-id="2402f-149">RNNs are used for time-series analysis, where the sequential ordering and context of events is important.</span></span> 

### <a name="understand-the-model"></a><span data-ttu-id="2402f-150">Entender el modelo</span><span class="sxs-lookup"><span data-stu-id="2402f-150">Understand the model</span></span>

<span data-ttu-id="2402f-151">La detección de objetos es una tarea de procesamiento de imágenes.</span><span class="sxs-lookup"><span data-stu-id="2402f-151">Object detection is an image processing task.</span></span> <span data-ttu-id="2402f-152">Por lo tanto, la mayoría de los modelos de aprendizaje profundo entrenados para solucionar este problema son CNN.</span><span class="sxs-lookup"><span data-stu-id="2402f-152">Therefore, most deep learning models trained to solve this problem are CNNs.</span></span> <span data-ttu-id="2402f-153">El modelo que se usa en este tutorial es el Tiny YOLOv2, una versión más compacta del modelo YOLOv2 que se describe en el documento: ["YOLO9000: Better, Faster, Stronger" de Redmon y Fadhari](https://arxiv.org/pdf/1612.08242.pdf).</span><span class="sxs-lookup"><span data-stu-id="2402f-153">The model used in this tutorial is the Tiny YOLOv2 model, a more compact version of the YOLOv2 model described in the paper: ["YOLO9000: Better, Faster, Stronger" by Redmon and Fadhari](https://arxiv.org/pdf/1612.08242.pdf).</span></span> <span data-ttu-id="2402f-154">Tiny YOLOv2 se entrena en el conjunto de datos Pascal VOC y se compone de 15 capas que pueden predecir 20 clases diferentes de objetos.</span><span class="sxs-lookup"><span data-stu-id="2402f-154">Tiny YOLOv2 is trained on the Pascal VOC dataset and is made up of 15 layers that can predict 20 different classes of objects.</span></span> <span data-ttu-id="2402f-155">Dado que Tiny YOLOv2 es una versión comprimida del modelo YOLOv2 original, se logra velocidad a cambio de precisión.</span><span class="sxs-lookup"><span data-stu-id="2402f-155">Because Tiny YOLOv2 is a condensed version of the original YOLOv2 model, a tradeoff is made between speed and accuracy.</span></span> <span data-ttu-id="2402f-156">Los diferentes niveles que componen el modelo se pueden visualizar mediante herramientas como Netron.</span><span class="sxs-lookup"><span data-stu-id="2402f-156">The different layers that make up the model can be visualized using tools like Netron.</span></span> <span data-ttu-id="2402f-157">Al inspeccionar el modelo, se produciría una asignación de las conexiones entre todas las capas que componen la red neuronal, donde cada capa contendría el nombre de la capa, junto con las dimensiones de la entrada y la salida correspondientes.</span><span class="sxs-lookup"><span data-stu-id="2402f-157">Inspecting the model would yield a mapping of the connections between all the layers that make up the neural network, where each layer would contain the name of the layer along with the dimensions of the respective input / output.</span></span> <span data-ttu-id="2402f-158">Las estructuras de datos que se usan para describir las entradas y salidas del modelo se conocen como tensores.</span><span class="sxs-lookup"><span data-stu-id="2402f-158">The data structures used to describe the inputs and outputs of the model are known as tensors.</span></span> <span data-ttu-id="2402f-159">Los tensores se pueden considerar como contenedores que almacenan datos en N dimensiones.</span><span class="sxs-lookup"><span data-stu-id="2402f-159">Tensors can be thought of as containers that store data in N-dimensions.</span></span> <span data-ttu-id="2402f-160">En el caso de Tiny YOLOv2, el nombre de la capa de entrada es `image` y espera un tensor de dimensiones `3 x 416 x 416`.</span><span class="sxs-lookup"><span data-stu-id="2402f-160">In the case of Tiny YOLOv2, the name of the input layer is `image` and it expects a tensor of dimensions `3 x 416 x 416`.</span></span> <span data-ttu-id="2402f-161">El nombre de la capa de salida es `grid` y genera un tensor de salida de dimensiones `125 x 13 x 13`.</span><span class="sxs-lookup"><span data-stu-id="2402f-161">The name of the output layer is `grid` and generates an output tensor of dimensions `125 x 13 x 13`.</span></span>  

![](./media/object-detection-onnx/netron-model-map.png)

<span data-ttu-id="2402f-162">El modelo YOLO toma una imagen `3(RGB) x 416px x 416px`.</span><span class="sxs-lookup"><span data-stu-id="2402f-162">The YOLO model takes an image `3(RGB) x 416px x 416px`.</span></span> <span data-ttu-id="2402f-163">El modelo toma esta entrada y la pasa a través de las diferentes capas para generar una salida.</span><span class="sxs-lookup"><span data-stu-id="2402f-163">The model takes this input and passes it through the different layers to produce an output.</span></span> <span data-ttu-id="2402f-164">El resultado divide la imagen de entrada en una cuadrícula de `13 x 13`, y cada celda de la cuadrícula consta de `125` valores.</span><span class="sxs-lookup"><span data-stu-id="2402f-164">The output divides the input image into a `13 x 13` grid, with each cell in the grid consisting of `125` values.</span></span> 

### <a name="what-is-an-onnx-model"></a><span data-ttu-id="2402f-165">¿Qué es un modelo de ONNX?</span><span class="sxs-lookup"><span data-stu-id="2402f-165">What is an ONNX model?</span></span>

<span data-ttu-id="2402f-166">Open Neural Network Exchange (ONNX) es un formato de código abierto para los modelos de IA.</span><span class="sxs-lookup"><span data-stu-id="2402f-166">The Open Neural Network Exchange (ONNX) is an open source format for AI models.</span></span> <span data-ttu-id="2402f-167">ONNX admite la interoperabilidad entre marcos.</span><span class="sxs-lookup"><span data-stu-id="2402f-167">ONNX supports interoperability between frameworks.</span></span> <span data-ttu-id="2402f-168">Esto significa que puede entrenar un modelo en uno de los muchos marcos de aprendizaje automático populares, como PyTorch, convertirlo en formato ONNX y consumir el modelo ONNX en otro marco, como ML.NET.</span><span class="sxs-lookup"><span data-stu-id="2402f-168">This means you can train a model in one of the many popular machine learning frameworks like PyTorch, convert it into ONNX format and consume the ONNX model in a different framework like ML.NET.</span></span> <span data-ttu-id="2402f-169">Para más información, visite el [sitio web de ONNX](https://onnx.ai/).</span><span class="sxs-lookup"><span data-stu-id="2402f-169">To learn more, visit the [ONNX website](https://onnx.ai/).</span></span> 

![](./media/object-detection-onnx/onnx-frameworks.png)

<span data-ttu-id="2402f-170">El modelo Tiny YOLOv2 entrenado previamente se almacena en formato ONNX, una representación serializada de las capas y los patrones aprendidos de esas capas.</span><span class="sxs-lookup"><span data-stu-id="2402f-170">The pre-trained Tiny YOLOv2 model is stored in ONNX format, a serialized representation of the layers and learned patterns of those layers.</span></span> <span data-ttu-id="2402f-171">En ML.NET, la interoperabilidad con ONNX se logra con los paquetes NuGet [`ImageAnalytics`](xref:Microsoft.ML.Transforms.Image) y [`OnnxTransformer`](xref:Microsoft.ML.Transforms.Onnx.OnnxTransformer).</span><span class="sxs-lookup"><span data-stu-id="2402f-171">In ML.NET, interoperability with ONNX is achieved with the [`ImageAnalytics`](xref:Microsoft.ML.Transforms.Image) and [`OnnxTransformer`](xref:Microsoft.ML.Transforms.Onnx.OnnxTransformer) NuGet packages.</span></span> <span data-ttu-id="2402f-172">El paquete [`ImageAnalytics`](xref:Microsoft.ML.Transforms.Image) contiene una serie de transformaciones que toman una imagen y la codifican en valores numéricos que se pueden usar como entrada en una canalización de entrenamiento o de predicción.</span><span class="sxs-lookup"><span data-stu-id="2402f-172">The [`ImageAnalytics`](xref:Microsoft.ML.Transforms.Image) package contains a series of transforms that take an image and encode it into numerical values that can be used as input into a prediction or training pipeline.</span></span> <span data-ttu-id="2402f-173">El paquete [`OnnxTransformer`](xref:Microsoft.ML.Transforms.Onnx.OnnxTransformer) aprovecha el tiempo de ejecución de ONNX para cargar un modelo de ONNX y usarlo para hacer predicciones basadas en la entrada proporcionada.</span><span class="sxs-lookup"><span data-stu-id="2402f-173">The [`OnnxTransformer`](xref:Microsoft.ML.Transforms.Onnx.OnnxTransformer) package leverages the ONNX Runtime to load an ONNX model and use it to make predictions based on input provided.</span></span> 

![](./media/object-detection-onnx/onnx-ml-net-integration.png)

## <a name="set-up-the-net-core-project"></a><span data-ttu-id="2402f-174">Configurar el proyecto de .NET Core</span><span class="sxs-lookup"><span data-stu-id="2402f-174">Set up the .NET Core project</span></span>

<span data-ttu-id="2402f-175">Ahora que tiene un conocimiento general de lo que es ONNX y de cómo funciona Tiny YOLOv2, es el momento de compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2402f-175">Now that you have a general understanding of what ONNX is and how Tiny YOLOv2 works, it's time to build the application.</span></span>

### <a name="create-a-console-application"></a><span data-ttu-id="2402f-176">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="2402f-176">Create a console application</span></span>

1. <span data-ttu-id="2402f-177">Cree una **aplicación de consola de .NET Core** denominada "ObjectDetection".</span><span class="sxs-lookup"><span data-stu-id="2402f-177">Create a **.NET Core Console Application** called "ObjectDetection".</span></span>

1. <span data-ttu-id="2402f-178">Instale el **paquete NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="2402f-178">Install the **Microsoft.ML NuGet Package**:</span></span>

    - <span data-ttu-id="2402f-179">En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="2402f-179">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> 
    - <span data-ttu-id="2402f-180">Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar y busque **Microsoft.ML**.</span><span class="sxs-lookup"><span data-stu-id="2402f-180">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**.</span></span> 
    - <span data-ttu-id="2402f-181">Seleccione el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="2402f-181">Select the **Install** button.</span></span> 
    - <span data-ttu-id="2402f-182">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="2402f-182">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span> 
    - <span data-ttu-id="2402f-183">Repita estos pasos para **Microsoft.ML.ImageAnalytics** y **Microsoft.ML.OnnxTransformer**.</span><span class="sxs-lookup"><span data-stu-id="2402f-183">Repeat these steps for **Microsoft.ML.ImageAnalytics** and **Microsoft.ML.OnnxTransformer**.</span></span>

### <a name="prepare-your-data-and-pre-trained-model"></a><span data-ttu-id="2402f-184">Preparar los datos y el modelo entrenado previamente</span><span class="sxs-lookup"><span data-stu-id="2402f-184">Prepare your data and pre-trained model</span></span>

1. <span data-ttu-id="2402f-185">Descargue el [archivo ZIP del directorio de recursos del proyecto](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/assets.zip) y descomprímalo.</span><span class="sxs-lookup"><span data-stu-id="2402f-185">Download [The project assets directory zip file](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/assets.zip) and unzip.</span></span>

1. <span data-ttu-id="2402f-186">Copie el directorio `assets` en el directorio de proyecto *ObjectDetection*.</span><span class="sxs-lookup"><span data-stu-id="2402f-186">Copy the `assets` directory into your *ObjectDetection* project directory.</span></span> <span data-ttu-id="2402f-187">Este directorio y sus subdirectorios contienen los archivos de imagen (excepto los del modelo de Tiny YOLOv2, que descargará y agregará en el paso siguiente) que se necesitan en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="2402f-187">This directory and its subdirectories contain the image files (except for the Tiny YOLOv2 model, which you'll download and add in the next step) needed for this tutorial.</span></span>

1. <span data-ttu-id="2402f-188">Descargue el [modelo de Tiny YOLOv2](https://onnxzoo.blob.core.windows.net/models/opset_8/tiny_yolov2/tiny_yolov2.tar.gz) de [ONNX Model Zoo](https://github.com/onnx/models/tree/master/vision/object_detection_segmentation/tiny_yolov2) y descomprímalo.</span><span class="sxs-lookup"><span data-stu-id="2402f-188">Download the [Tiny YOLOv2 model](https://onnxzoo.blob.core.windows.net/models/opset_8/tiny_yolov2/tiny_yolov2.tar.gz) from the [ONNX Model Zoo](https://github.com/onnx/models/tree/master/vision/object_detection_segmentation/tiny_yolov2), and unzip.</span></span>

    <span data-ttu-id="2402f-189">Abra el símbolo del sistema y escriba el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="2402f-189">Open the command prompt and enter the following command:</span></span>

    ```shell
    tar -xvzf tiny_yolov2.tar.gz 
    ```

1. <span data-ttu-id="2402f-190">Copie el archivo `model.onnx` extraído del directorio que acaba de descomprimir en el directorio `assets\Model` del proyecto *ObjectDetection* y cambie su nombre a `TinyYolo2_model.onnx`.</span><span class="sxs-lookup"><span data-stu-id="2402f-190">Copy the extracted `model.onnx` file from the directory just unzipped into your *ObjectDetection* project `assets\Model` directory and rename it to `TinyYolo2_model.onnx`.</span></span> <span data-ttu-id="2402f-191">Este directorio contiene el modelo necesario para este tutorial.</span><span class="sxs-lookup"><span data-stu-id="2402f-191">This directory contains the model needed for this tutorial.</span></span>

1. <span data-ttu-id="2402f-192">En el Explorador de soluciones, haga clic con el botón derecho en cada uno de los archivos del directorio de recursos y los subdirectorios y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2402f-192">In Solution Explorer, right-click each of the files in the asset directory and subdirectories and select **Properties**.</span></span> <span data-ttu-id="2402f-193">En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.</span><span class="sxs-lookup"><span data-stu-id="2402f-193">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="2402f-194">Crear clases y definir rutas de acceso</span><span class="sxs-lookup"><span data-stu-id="2402f-194">Create classes and define paths</span></span>

<span data-ttu-id="2402f-195">Abra el archivo*Program.cs* y agregue las instrucciones `using` adicionales siguientes a la parte superior del archivo:</span><span class="sxs-lookup"><span data-stu-id="2402f-195">Open the *Program.cs* file and add the following additional `using` statements to the top of the file:</span></span>

[!code-csharp [ProgramUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L1-L9)]

<span data-ttu-id="2402f-196">A continuación, defina las rutas de acceso de los distintos recursos.</span><span class="sxs-lookup"><span data-stu-id="2402f-196">Next, define the paths of the various assets.</span></span> 

1. <span data-ttu-id="2402f-197">En primer lugar, agregue el método `GetAbsolutePath` debajo del método `Main` en la clase `Program`.</span><span class="sxs-lookup"><span data-stu-id="2402f-197">First, add the `GetAbsolutePath` method below the `Main` method in the `Program` class.</span></span> 

    [!code-csharp [GetAbsolutePath](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L66-L74)]

1. <span data-ttu-id="2402f-198">Después, dentro del método `Main`, cree campos para almacenar la ubicación de los recursos:</span><span class="sxs-lookup"><span data-stu-id="2402f-198">Then, inside the `Main` method, create fields to store the location of your assets:</span></span>

    [!code-csharp [AssetDefinition](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L17-L21)]

<span data-ttu-id="2402f-199">Agregue un nuevo directorio al proyecto para almacenar los datos de entrada y las clases de predicción.</span><span class="sxs-lookup"><span data-stu-id="2402f-199">Add a new directory to your project to store your input data and prediction classes.</span></span>

<span data-ttu-id="2402f-200">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, luego, seleccione **Agregar** > **Nueva carpeta**.</span><span class="sxs-lookup"><span data-stu-id="2402f-200">In **Solution Explorer**, right-click the project, and then select **Add** > **New Folder**.</span></span> <span data-ttu-id="2402f-201">Cuando la nueva carpeta aparezca en el Explorador de soluciones, asígnele el nombre "DataStructures".</span><span class="sxs-lookup"><span data-stu-id="2402f-201">When the new folder appears in the Solution Explorer, name it "DataStructures".</span></span>

<span data-ttu-id="2402f-202">Cree la clase de datos de entrada en el directorio *DataStructures* recién creado.</span><span class="sxs-lookup"><span data-stu-id="2402f-202">Create your input data class in the newly created *DataStructures* directory.</span></span>

1. <span data-ttu-id="2402f-203">En el **Explorador de soluciones**, haga clic con el botón derecho en el directorio *DataStructures* y luego seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="2402f-203">In **Solution Explorer**, right-click the *DataStructures* directory, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="2402f-204">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *ImageNetData.cs*.</span><span class="sxs-lookup"><span data-stu-id="2402f-204">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *ImageNetData.cs*.</span></span> <span data-ttu-id="2402f-205">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2402f-205">Then, select the **Add** button.</span></span>
     
    <span data-ttu-id="2402f-206">El archivo *ImageNetData.cs* se abre en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="2402f-206">The *ImageNetData.cs* file opens in the code editor.</span></span> <span data-ttu-id="2402f-207">Agregue la instrucción `using` siguiente al principio del archivo *ImageNetData.cs*:</span><span class="sxs-lookup"><span data-stu-id="2402f-207">Add the following `using` statement to the top of *ImageNetData.cs*:</span></span>

    [!code-csharp [ImageNetDataUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/DataStructures/ImageNetData.cs#L1-L4)]

    <span data-ttu-id="2402f-208">Quite la definición de clase existente y agregue el código siguiente para la clase `ImageNetData` al archivo *ImageNetData.cs*:</span><span class="sxs-lookup"><span data-stu-id="2402f-208">Remove the existing class definition and add the following code for the `ImageNetData` class to the *ImageNetData.cs* file:</span></span>
    
    [!code-csharp [ImageNetDataClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/DataStructures/ImageNetData.cs#L8-L23)]

    <span data-ttu-id="2402f-209">`ImageNetData` es la clase de datos de imagen de entrada y tiene los campos <xref:System.String> siguientes:</span><span class="sxs-lookup"><span data-stu-id="2402f-209">`ImageNetData` is the input image data class and has the following <xref:System.String> fields:</span></span>

    - <span data-ttu-id="2402f-210">`ImagePath` contiene la ruta de acceso donde se almacena la imagen.</span><span class="sxs-lookup"><span data-stu-id="2402f-210">`ImagePath` contains the path where the image is stored.</span></span>
    - <span data-ttu-id="2402f-211">`Label` contiene el nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="2402f-211">`Label` contains the name of the file.</span></span>

    <span data-ttu-id="2402f-212">Además, `ImageNetData` contiene un método `ReadFromFile` que carga varios archivos de imagen almacenados en la ruta `imageFolder`especificada y los devuelve como colección de objetos `ImageNetData`.</span><span class="sxs-lookup"><span data-stu-id="2402f-212">Additionally, `ImageNetData` contains a method `ReadFromFile` which loads multiple image files stored in the `imageFolder` path specified and returns them as a collection of `ImageNetData` objects.</span></span>

<span data-ttu-id="2402f-213">Cree la clase de predicción en el directorio *DataStructures*.</span><span class="sxs-lookup"><span data-stu-id="2402f-213">Create your prediction class in the *DataStructures* directory.</span></span>

1. <span data-ttu-id="2402f-214">En el **Explorador de soluciones**, haga clic con el botón derecho en el directorio *DataStructures* y luego seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="2402f-214">In **Solution Explorer**, right-click the *DataStructures* directory, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="2402f-215">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *ImageNetPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="2402f-215">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *ImageNetPrediction.cs*.</span></span> <span data-ttu-id="2402f-216">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2402f-216">Then, select the **Add** button.</span></span>

    <span data-ttu-id="2402f-217">El archivo *ImageNetPrediction.cs* se abre en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="2402f-217">The *ImageNetPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="2402f-218">Agregue la instrucción `using` siguiente al principio del archivo *ImageNetPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="2402f-218">Add the following `using` statement to the top of *ImageNetPrediction.cs*:</span></span>

    [!code-csharp [ImageNetPredictionUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/DataStructures/ImageNetPrediction.cs#L1)]

    <span data-ttu-id="2402f-219">Quite la definición de clase existente y agregue el código siguiente para la clase `ImageNetPrediction` al archivo *ImageNetPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="2402f-219">Remove the existing class definition and add the following code for the `ImageNetPrediction` class to the *ImageNetPrediction.cs* file:</span></span>

    [!code-csharp [ImageNetPredictionClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/DataStructures/ImageNetPrediction.cs#L5-L9)]

    <span data-ttu-id="2402f-220">`ImageNetPrediction` es la clase de datos de predicción y tiene el campo `float[]` siguiente:</span><span class="sxs-lookup"><span data-stu-id="2402f-220">`ImageNetPrediction` is the prediction data class and has the following `float[]` field:</span></span>

    - <span data-ttu-id="2402f-221">`PredictedLabel` contiene las dimensiones, la puntuación de calidad de objeto y las probabilidades de clase para cada uno de los cuadros de límite detectados en una imagen.</span><span class="sxs-lookup"><span data-stu-id="2402f-221">`PredictedLabel` contains the dimensions, objectness score and class probabilities for each of the bounding boxes detected in an image.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="2402f-222">Inicializar variables en Main</span><span class="sxs-lookup"><span data-stu-id="2402f-222">Initialize variables in Main</span></span>

<span data-ttu-id="2402f-223">La [clase MLContext](xref:Microsoft.ML.MLContext) es un punto de partida para todas las operaciones de ML.NET. Al inicializar `mlContext`, se crea un entorno de ML.NET que se puede compartir entre los objetos del flujo de trabajo de creación de modelos.</span><span class="sxs-lookup"><span data-stu-id="2402f-223">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="2402f-224">Como concepto, se parece a `DBContext` en Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="2402f-224">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

<span data-ttu-id="2402f-225">Inicialice la variable `mlContext` con una nueva instancia de `MLContext` al agregar la siguiente línea al método `Main` de *Program.cs* debajo del campo `outputFolder`.</span><span class="sxs-lookup"><span data-stu-id="2402f-225">Initialize the `mlContext` variable with a new instance of `MLContext` by adding the following line to the `Main` method of *Program.cs* below the `outputFolder` field.</span></span>

[!code-csharp [InitMLContext](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L24)]

### <a name="add-helper-methods"></a><span data-ttu-id="2402f-226">Adición de métodos auxiliares</span><span class="sxs-lookup"><span data-stu-id="2402f-226">Add Helper Methods</span></span>

<span data-ttu-id="2402f-227">Una vez que el modelo ha hecho una predicción, lo que se conoce comúnmente como puntuación, y se han procesado las salidas, los rectángulos delimitadores deben dibujarse en la imagen.</span><span class="sxs-lookup"><span data-stu-id="2402f-227">After the model has made a prediction, commonly referred to as scoring, and the outputs have been processed, the bounding boxes have to be drawn on the image.</span></span> <span data-ttu-id="2402f-228">Para ello, agregue un método denominado `DrawBoundingBox` debajo del método `GetAbsolutePath` dentro de *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="2402f-228">To do so, add a method called `DrawBoundingBox` below the `GetAbsolutePath` method insode of *Program.cs*.</span></span>

```csharp
private static void DrawBoundingBox(string inputImageLocation, string outputImageLocation, string imageName, IList<YoloBoundingBox> filteredBoundingBoxes)
{

}
```

<span data-ttu-id="2402f-229">En primer lugar, cargue la imagen y obtenga las dimensiones de altura y ancho en el método `DrawBoundingBox`.</span><span class="sxs-lookup"><span data-stu-id="2402f-229">First, load the image and get the height and width dimensions in the `DrawBoundingBox` method.</span></span>

[!code-csharp [LoadImage](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L78-L81)]

<span data-ttu-id="2402f-230">A continuación, cree un bucle for-each para iterar por cada uno de los rectángulos delimitadores detectados por el modelo.</span><span class="sxs-lookup"><span data-stu-id="2402f-230">Then, create a for-each loop to iterate over each of the bounding boxes detected by the model.</span></span>

```csharp
foreach (var box in filteredBoundingBoxes)
{

}
```

<span data-ttu-id="2402f-231">Dentro del bucle for-each, obtenga las dimensiones del rectángulo delimitador.</span><span class="sxs-lookup"><span data-stu-id="2402f-231">Inside of the for-each loop, get the dimensions of the bounding box.</span></span>

[!code-csharp [GetBBoxDimensions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L86-L89)]

<span data-ttu-id="2402f-232">Dado que las dimensiones del rectángulo delimitador corresponden a la entrada del modelo de `416 x 416`, escale las dimensiones del rectángulo delimitador para que coincidan con el tamaño real de la imagen.</span><span class="sxs-lookup"><span data-stu-id="2402f-232">Because the dimensions of the bounding box correspond to the model input of `416 x 416`, scale the bounding box dimensions to match the actual size of the image.</span></span>

[!code-csharp [ScaleImage](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L92-L95)]

<span data-ttu-id="2402f-233">Luego, defina una plantilla para el texto que aparecerá sobre cada rectángulo delimitador.</span><span class="sxs-lookup"><span data-stu-id="2402f-233">Then, define a template for text that will apear above each bounding box.</span></span> <span data-ttu-id="2402f-234">El texto contendrá la clase del objeto dentro del rectángulo delimitador correspondiente, así como la confianza.</span><span class="sxs-lookup"><span data-stu-id="2402f-234">The text will contain the class of the object inside of the respective bounding box as well as the confidence.</span></span>

[!code-csharp [DefineBBoxText](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L98)]

<span data-ttu-id="2402f-235">Para dibujar en la imagen, conviértala en un objeto [`Graphics`](xref:System.Drawing.Graphics).</span><span class="sxs-lookup"><span data-stu-id="2402f-235">In order to draw on the image, convert it to a [`Graphics`](xref:System.Drawing.Graphics) object.</span></span>

```csharp
using (Graphics thumbnailGraphic = Graphics.FromImage(image))
{
    
}
```

<span data-ttu-id="2402f-236">Dentro del bloque de código `using`, ajuste la configuración del objeto [`Graphics`](xref:System.Drawing.Graphics) del gráfico.</span><span class="sxs-lookup"><span data-stu-id="2402f-236">Inside the `using` code block, tune the graphic's [`Graphics`](xref:System.Drawing.Graphics) object settings.</span></span>

[!code-csharp [TuneGraphicSettings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L102-L104)]

<span data-ttu-id="2402f-237">Luego de eso, establezca las opciones de fuente y color para el texto y el rectángulo delimitador.</span><span class="sxs-lookup"><span data-stu-id="2402f-237">Below that, set the font and color options for the text and bounding box.</span></span>

[!code-csharp [SetColorOptions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L106-L114)]

<span data-ttu-id="2402f-238">Cree y rellene un rectángulo sobre el rectángulo delimitador para que contenga el texto mediante el método [`FillRectangle`](xref:System.Drawing.Graphics.FillRectangle*).</span><span class="sxs-lookup"><span data-stu-id="2402f-238">Create and fill a rectangle above the bounding box to contain the text using the [`FillRectangle`](xref:System.Drawing.Graphics.FillRectangle*) method.</span></span> <span data-ttu-id="2402f-239">Esto le ayudará a contrastar el texto y mejorar la legibilidad.</span><span class="sxs-lookup"><span data-stu-id="2402f-239">This will help contrast the text and improve readability.</span></span>

[!code-csharp [DrawTextBackground](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L117)]

<span data-ttu-id="2402f-240">A continuación, dibuje el texto y el rectángulo delimitador en la imagen con los métodos [`DrawString`](xref:System.Drawing.Graphics.DrawString*) y [`DrawRectangle`](xref:System.Drawing.Graphics.DrawRectangle*).</span><span class="sxs-lookup"><span data-stu-id="2402f-240">Then, Draw the text and bounding box on the image using the [`DrawString`](xref:System.Drawing.Graphics.DrawString*) and [`DrawRectangle`](xref:System.Drawing.Graphics.DrawRectangle*) methods.</span></span>

[!code-csharp [DrawClassAndBBox](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L118-L121)]

<span data-ttu-id="2402f-241">Fuera del bucle for-each, agregue código para guardar las imágenes en `outputDirectory`.</span><span class="sxs-lookup"><span data-stu-id="2402f-241">Outside of the for-each loop, add code to save the images in the `outputDirectory`.</span></span>

[!code-csharp [SaveImage](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L125-L130)]

<span data-ttu-id="2402f-242">Para obtener información adicional de que la aplicación está haciendo predicciones según lo esperado en tiempo de ejecución, agregue un método denominado `LogDetectedObjects` debajo del método `DrawBoundingBox` en el archivo *Program.cs* para generar los objetos detectados en la consola.</span><span class="sxs-lookup"><span data-stu-id="2402f-242">To get additional feedback that the application is making predictions as expected at runtime, add a method called `LogDetectedObjects` below the `DrawBoundingBox` method in the *Program.cs* file to output the detected objects to the console.</span></span>

[!code-csharp [LogOuptuts](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L133-L143)]

<span data-ttu-id="2402f-243">Ambos métodos serán útiles cuando el modelo haya generado salidas y estas se hayan procesado.</span><span class="sxs-lookup"><span data-stu-id="2402f-243">Both of these methods will be useful when the model has produced outputs and those have been processed.</span></span> <span data-ttu-id="2402f-244">En primer lugar, cree la funcionalidad para procesar las salidas del modelo.</span><span class="sxs-lookup"><span data-stu-id="2402f-244">First though, create the functionality to process the model outputs.</span></span>

## <a name="create-a-parser-to-post-process-model-outputs"></a><span data-ttu-id="2402f-245">Crear un analizador para el procesamiento posterior de las salidas del modelo</span><span class="sxs-lookup"><span data-stu-id="2402f-245">Create a parser to post-process model outputs</span></span>

<span data-ttu-id="2402f-246">El modelo segmenta una imagen en una cuadrícula `13 x 13`, donde cada celda de la cuadrícula mide `32px x 32px`.</span><span class="sxs-lookup"><span data-stu-id="2402f-246">The model segments an image into a `13 x 13` grid, where each grid cell is `32px x 32px`.</span></span> <span data-ttu-id="2402f-247">Cada celda de la cuadrícula contiene 5 rectángulos delimitadores de objeto posibles.</span><span class="sxs-lookup"><span data-stu-id="2402f-247">Each grid cell contains 5 potential object bounding boxes.</span></span> <span data-ttu-id="2402f-248">Un rectángulo delimitador tiene 25 elementos:</span><span class="sxs-lookup"><span data-stu-id="2402f-248">A bounding box has  25 elements:</span></span>

![](./media/object-detection-onnx/model-output-description.png)

- <span data-ttu-id="2402f-249">`x`, posición x del centro del rectángulo delimitador relativo a la celda de la cuadrícula a la que está asociada.</span><span class="sxs-lookup"><span data-stu-id="2402f-249">`x` the x position of the bounding box center relative to the grid cell it's associated with.</span></span>
- <span data-ttu-id="2402f-250">`y`, posición y del centro del rectángulo delimitador relativo a la celda de la cuadrícula a la que está asociada.</span><span class="sxs-lookup"><span data-stu-id="2402f-250">`y` the y position of the bounding box center relative to the grid cell it's associated with.</span></span>
- <span data-ttu-id="2402f-251">`w`, ancho del rectángulo delimitador.</span><span class="sxs-lookup"><span data-stu-id="2402f-251">`w` the width of the bounding box.</span></span>
- <span data-ttu-id="2402f-252">`h`, altura del rectángulo delimitador.</span><span class="sxs-lookup"><span data-stu-id="2402f-252">`h` the height of the bounding box.</span></span> 
- <span data-ttu-id="2402f-253">`o`, valor de confianza de que existe un objeto dentro del rectángulo delimitador, también conocido como puntuación de calidad de objeto.</span><span class="sxs-lookup"><span data-stu-id="2402f-253">`o` the confidence value that an object exists within the bounding box, also known as objectness score.</span></span>
- <span data-ttu-id="2402f-254">`p1-p20`, probabilidades de clase para cada una de las 20 clases previstas por el modelo.</span><span class="sxs-lookup"><span data-stu-id="2402f-254">`p1-p20` class probabilities for each of the 20 classes predicted by the model.</span></span>

<span data-ttu-id="2402f-255">En total, los 25 elementos que describen cada uno de los 5 rectángulos delimitadores constituyen los 125 elementos contenidos en cada celda de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="2402f-255">In total, the 25 elements describing each of the 5 bounding boxes make up the 125 elements contained in each grid cell.</span></span>

<span data-ttu-id="2402f-256">La salida generada por el modelo ONNX entrenado previamente es una matriz float de longitud `21125`, que representa los elementos de un tensor con dimensiones `125 x 13 x 13`.</span><span class="sxs-lookup"><span data-stu-id="2402f-256">The output generated by the pre-trained ONNX model is a float array of length `21125`, representing the elements of a tensor with dimensions `125 x 13 x 13`.</span></span> <span data-ttu-id="2402f-257">Para transformar las predicciones generadas por el modelo en un tensor, se requiere algún trabajo posterior al procesamiento.</span><span class="sxs-lookup"><span data-stu-id="2402f-257">In order to transform the predictions generated by the model into a tensor, some post-processing work is required.</span></span> <span data-ttu-id="2402f-258">Para ello, cree un conjunto de clases que ayuden a analizar la salida.</span><span class="sxs-lookup"><span data-stu-id="2402f-258">To do so, create a set of classes to help parse the output.</span></span>

<span data-ttu-id="2402f-259">Agregue un nuevo directorio al proyecto para organizar el conjunto de clases de analizador.</span><span class="sxs-lookup"><span data-stu-id="2402f-259">Add a new directory to your project to organize the set of parser classes.</span></span>

1. <span data-ttu-id="2402f-260">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, luego, seleccione **Agregar** > **Nueva carpeta**.</span><span class="sxs-lookup"><span data-stu-id="2402f-260">In **Solution Explorer**, right-click the project, and then select **Add** > **New Folder**.</span></span> <span data-ttu-id="2402f-261">Cuando la nueva carpeta aparezca en el Explorador de soluciones, asígnele el nombre "YoloParser".</span><span class="sxs-lookup"><span data-stu-id="2402f-261">When the new folder appears in the Solution Explorer, name it "YoloParser".</span></span>

### <a name="create-bounding-boxes-and-dimensions"></a><span data-ttu-id="2402f-262">Crear rectángulos delimitadores y dimensiones</span><span class="sxs-lookup"><span data-stu-id="2402f-262">Create bounding boxes and dimensions</span></span>

<span data-ttu-id="2402f-263">La salida de datos del modelo contiene las coordenadas y las dimensiones de los rectángulos delimitadores de los objetos dentro de la imagen.</span><span class="sxs-lookup"><span data-stu-id="2402f-263">The data output by the model contains coordinates and dimensions of the bounding boxes of objects within the image.</span></span> <span data-ttu-id="2402f-264">Cree una clase base para las dimensiones.</span><span class="sxs-lookup"><span data-stu-id="2402f-264">Create a base class for dimensions.</span></span>

1. <span data-ttu-id="2402f-265">En el **Explorador de soluciones**, haga clic con el botón derecho en el directorio *YoloParser* y luego seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="2402f-265">In **Solution Explorer**, right-click the *YoloParser* directory, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="2402f-266">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *DimensionsBase.cs*.</span><span class="sxs-lookup"><span data-stu-id="2402f-266">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *DimensionsBase.cs*.</span></span> <span data-ttu-id="2402f-267">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2402f-267">Then, select the **Add** button.</span></span>

    <span data-ttu-id="2402f-268">Se abre el archivo *DimensionsBase.cs* en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="2402f-268">The *DimensionsBase.cs* file opens in the code editor.</span></span> <span data-ttu-id="2402f-269">Quite todas las instrucciones `using` y la definición de clase existente.</span><span class="sxs-lookup"><span data-stu-id="2402f-269">Remove all `using` statements and existing class definition.</span></span> 

    <span data-ttu-id="2402f-270">Agregue el código siguiente para la clase `DimensionsBase` al archivo *DimensionsBase.cs*:</span><span class="sxs-lookup"><span data-stu-id="2402f-270">Add the following code for the `DimensionsBase` class to the *DimensionsBase.cs* file:</span></span>

    [!code-csharp [DimensionsBaseClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/DimensionsBase.cs#L3-L9)]

    <span data-ttu-id="2402f-271">`DimensionsBase` tiene los siguientes campos `float`:</span><span class="sxs-lookup"><span data-stu-id="2402f-271">`DimensionsBase` has the following `float` fields:</span></span>

    - <span data-ttu-id="2402f-272">`X` contiene la posición del objeto en el eje x.</span><span class="sxs-lookup"><span data-stu-id="2402f-272">`X` contains the position of the object along the x-axis.</span></span>
    - <span data-ttu-id="2402f-273">`Y` contiene la posición del objeto en el eje y.</span><span class="sxs-lookup"><span data-stu-id="2402f-273">`Y` contains the position of the object along the y-axis.</span></span>
    - <span data-ttu-id="2402f-274">`Height` contiene la altura del objeto.</span><span class="sxs-lookup"><span data-stu-id="2402f-274">`Height` contains the height of the object.</span></span>
    - <span data-ttu-id="2402f-275">`Width` contiene el ancho del objeto.</span><span class="sxs-lookup"><span data-stu-id="2402f-275">`Width` contains the width of the object.</span></span>

<span data-ttu-id="2402f-276">A continuación, cree una clase para los rectángulos delimitadores.</span><span class="sxs-lookup"><span data-stu-id="2402f-276">Next, create a class for your bounding boxes.</span></span>

1. <span data-ttu-id="2402f-277">En el **Explorador de soluciones**, haga clic con el botón derecho en el directorio *YoloParser* y luego seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="2402f-277">In **Solution Explorer**, right-click the *YoloParser* directory, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="2402f-278">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *YoloBoundingBox.cs*.</span><span class="sxs-lookup"><span data-stu-id="2402f-278">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *YoloBoundingBox.cs*.</span></span> <span data-ttu-id="2402f-279">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2402f-279">Then, select the **Add** button.</span></span>

    <span data-ttu-id="2402f-280">Se abre el archivo *YoloBoundingBox.cs* en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="2402f-280">The *YoloBoundingBox.cs* file opens in the code editor.</span></span> <span data-ttu-id="2402f-281">Agregue la instrucción `using` siguiente al principio del archivo *YoloBoundingBox.cs*:</span><span class="sxs-lookup"><span data-stu-id="2402f-281">Add the following `using` statement to the top of *YoloBoundingBox.cs*:</span></span>

    [!code-csharp [YoloBoundingBoxUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloBoundingBox.cs#L1)]

    <span data-ttu-id="2402f-282">Justo encima de la definición de clase existente, agregue una nueva definición de clase denominada `BoundingBoxDimensions` que herede de la clase `DimensionsBase` para que contenga las dimensiones del rectángulo delimitador correspondiente.</span><span class="sxs-lookup"><span data-stu-id="2402f-282">Just above the existing class definition, add a new class definition called `BoundingBoxDimensions` which inherits from the `DimensionsBase` class to contain the dimensions of the respective bounding box.</span></span>

    [!code-csharp [BoundingBoxDimClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloBoundingBox.cs#L5)]

    <span data-ttu-id="2402f-283">Quite la definición de clase `YoloBoundingBox` existente y agregue el código siguiente para la clase `YoloBoundingBox` al archivo *YoloBoundingBox.cs*:</span><span class="sxs-lookup"><span data-stu-id="2402f-283">Remove the existing `YoloBoundingBox` class definition and add the following code for the `YoloBoundingBox` class to the *YoloBoundingBox.cs* file:</span></span>

    [!code-csharp [YoloBoundingBoxClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloBoundingBox.cs#L7-L21)]
    
    <span data-ttu-id="2402f-284">`YoloBoundingBox` tiene los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="2402f-284">`YoloBoundingBox` has the following fields:</span></span>

    - <span data-ttu-id="2402f-285">`Dimensions` contiene las dimensiones del rectángulo delimitador.</span><span class="sxs-lookup"><span data-stu-id="2402f-285">`Dimensions` contains dimensions of the bounding box.</span></span>
    - <span data-ttu-id="2402f-286">`Label` contiene la clase de objeto detectado en el rectángulo delimitador.</span><span class="sxs-lookup"><span data-stu-id="2402f-286">`Label` contains the class of object detected within the bounding box.</span></span>
    - <span data-ttu-id="2402f-287">`Confidence` contiene la confianza de la clase.</span><span class="sxs-lookup"><span data-stu-id="2402f-287">`Confidence` contains the confidence of the class.</span></span>
    - <span data-ttu-id="2402f-288">`Rect` contiene la representación del rectángulo de las dimensiones del rectángulo delimitador.</span><span class="sxs-lookup"><span data-stu-id="2402f-288">`Rect` contains the rectangle representation of the bounding box's dimensions.</span></span>
    - <span data-ttu-id="2402f-289">`BoxColor` contiene el color asociado a la clase correspondiente usada para dibujar en la imagen.</span><span class="sxs-lookup"><span data-stu-id="2402f-289">`BoxColor` contains the color associated with the respective class used to draw on the image.</span></span>

### <a name="create-the-parser"></a><span data-ttu-id="2402f-290">Crear el analizador</span><span class="sxs-lookup"><span data-stu-id="2402f-290">Create the parser</span></span>

<span data-ttu-id="2402f-291">Ahora que se han creado las clases para las dimensiones y los rectángulos delimitadores, es el momento de crear el analizador.</span><span class="sxs-lookup"><span data-stu-id="2402f-291">Now that the classes for dimensions and bounding boxes are created, it's time to create the parser.</span></span>

1. <span data-ttu-id="2402f-292">En el **Explorador de soluciones**, haga clic con el botón derecho en el directorio *YoloParser* y luego seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="2402f-292">In **Solution Explorer**, right-click the *YoloParser* directory, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="2402f-293">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *YoloOutputParser.cs*.</span><span class="sxs-lookup"><span data-stu-id="2402f-293">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *YoloOutputParser.cs*.</span></span> <span data-ttu-id="2402f-294">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2402f-294">Then, select the **Add** button.</span></span>

    <span data-ttu-id="2402f-295">Se abre el archivo *YoloOutputParser.cs* en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="2402f-295">The *YoloOutputParser.cs* file opens in the code editor.</span></span> <span data-ttu-id="2402f-296">Agregue la instrucción `using` siguiente al principio del archivo *YoloOutputParser.cs*:</span><span class="sxs-lookup"><span data-stu-id="2402f-296">Add the following `using` statement to the top of *YoloOutputParser.cs*:</span></span>

    [!code-csharp [YoloParserUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L1-L4)]

    <span data-ttu-id="2402f-297">Dentro de la definición de clase `YoloOutputParser` existente, agregue una clase anidada que contenga las dimensiones de cada una de las celdas de la imagen.</span><span class="sxs-lookup"><span data-stu-id="2402f-297">Inside the existing `YoloOutputParser` class definition, add a nested class that contains the dimensions of each of the cells in the image.</span></span> <span data-ttu-id="2402f-298">Agregue el código siguiente para la clase `CellDimensions` que hereda de la clase `DimensionsBase` en la parte superior de la definición de la clase `YoloOutputParser`.</span><span class="sxs-lookup"><span data-stu-id="2402f-298">Add the following code for the `CellDimensions` class which inherits from the `DimensionsBase` class at the top of the `YoloOutputParser` class definition.</span></span>

    [!code-csharp [YoloParserUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L10)]

1. <span data-ttu-id="2402f-299">Dentro de la definición de la clase `YoloOutputParser`, agregue la constante y los campos siguientes.</span><span class="sxs-lookup"><span data-stu-id="2402f-299">Inside the `YoloOutputParser` class definition, add the following constant and fields.</span></span>

    [!code-csharp [ParserVarDefinitions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L12-L21)]    

    - <span data-ttu-id="2402f-300">`ROW_COUNT` es el número de filas de la cuadrícula en la que se divide la imagen.</span><span class="sxs-lookup"><span data-stu-id="2402f-300">`ROW_COUNT` is the number of rows in the grid the image is divided into.</span></span>
    - <span data-ttu-id="2402f-301">`COL_COUNT` es el número de columnas de la cuadrícula en la que se divide la imagen.</span><span class="sxs-lookup"><span data-stu-id="2402f-301">`COL_COUNT` is the number of columns in the grid the image is divided into.</span></span>
    - <span data-ttu-id="2402f-302">`CHANNEL_COUNT` es el número total de valores contenidos en una celda de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="2402f-302">`CHANNEL_COUNT` is the total number of values contained in one cell of the grid.</span></span>
    - <span data-ttu-id="2402f-303">`BOXES_PER_CELL` es el número de rectángulos delimitadores de una celda.</span><span class="sxs-lookup"><span data-stu-id="2402f-303">`BOXES_PER_CELL` is the number of bounding boxes in a cell,</span></span>
    - <span data-ttu-id="2402f-304">`BOX_INFO_FEATURE_COUNT` es el número de características contenidas en un rectángulo (x,y,altura,ancho,confianza).</span><span class="sxs-lookup"><span data-stu-id="2402f-304">`BOX_INFO_FEATURE_COUNT` is the number of features contained within a box (x,y,height,width,confidence).</span></span>
    - <span data-ttu-id="2402f-305">`CLASS_COUNT` es el número de predicciones de clase que contiene cada rectángulo delimitador.</span><span class="sxs-lookup"><span data-stu-id="2402f-305">`CLASS_COUNT` is the number of class predictions contained in each bounding box.</span></span>
    - <span data-ttu-id="2402f-306">`CELL_WIDTH` es el ancho de una celda de la cuadrícula de imagen.</span><span class="sxs-lookup"><span data-stu-id="2402f-306">`CELL_WIDTH` is the width of one cell in the image grid.</span></span>
    - <span data-ttu-id="2402f-307">`CELL_HEIGHT` es la altura de una celda de la cuadrícula de imagen.</span><span class="sxs-lookup"><span data-stu-id="2402f-307">`CELL_HEIGHT` is the height of one cell in the image grid.</span></span>
    - <span data-ttu-id="2402f-308">`channelStride` es la posición inicial de la celda actual en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="2402f-308">`channelStride` is the starting position of the current cell in the grid.</span></span>

    <span data-ttu-id="2402f-309">Cuando el modelo puntúa una imagen, divide la entrada de `416px x 416px` en una cuadrícula de celdas cuyo tamaño es `13 x 13`.</span><span class="sxs-lookup"><span data-stu-id="2402f-309">When the model scores an image, it divides the `416px x 416px`input into a grid of cells the size of `13 x 13`.</span></span> <span data-ttu-id="2402f-310">El contenido de cada celda mide `32px x 32px`.</span><span class="sxs-lookup"><span data-stu-id="2402f-310">Each cell contains is `32px x 32px`.</span></span> <span data-ttu-id="2402f-311">Dentro de cada celda, hay 5 rectángulos delimitadores, donde cada uno contiene 5 características (x,y,ancho,altura,confianza).</span><span class="sxs-lookup"><span data-stu-id="2402f-311">Within each cell, there are 5 bounding boxes each containing 5 features (x, y, width, height, confidence).</span></span> <span data-ttu-id="2402f-312">Además, cada rectángulo delimitador contiene la probabilidad de cada una de las clases, que, en este caso, es 20.</span><span class="sxs-lookup"><span data-stu-id="2402f-312">In addition, each bounding box contains the probability of each of the classes which in this case is 20.</span></span> <span data-ttu-id="2402f-313">Por lo tanto, cada celda contiene 125 piezas de información (5 características + 20 probabilidades de clase).</span><span class="sxs-lookup"><span data-stu-id="2402f-313">Therefore, each cell contains 125 pieces of information (5 features + 20 class probabilities).</span></span> 

<span data-ttu-id="2402f-314">Cree una lista de delimitadores a continuación de `channelStride` para los 5 rectángulos delimitadores:</span><span class="sxs-lookup"><span data-stu-id="2402f-314">Create a list of anchors below `channelStride` for all 5 bounding boxes:</span></span>

[!code-csharp [ParserAnchors](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L23-L26)]   

<span data-ttu-id="2402f-315">Los delimitadores son proporciones predefinidas de altura y ancho de los rectángulos delimitadores.</span><span class="sxs-lookup"><span data-stu-id="2402f-315">Anchors are pre-defined height and width ratios of bounding boxes.</span></span> <span data-ttu-id="2402f-316">La mayoría de los objetos o clases detectados por un modelo tienen relaciones similares.</span><span class="sxs-lookup"><span data-stu-id="2402f-316">Most object or classes detected by a model have similar ratios.</span></span> <span data-ttu-id="2402f-317">Esto resulta útil cuando se trata de crear rectángulos delimitadores.</span><span class="sxs-lookup"><span data-stu-id="2402f-317">This is valuable when it comes to creating bounding boxes.</span></span> <span data-ttu-id="2402f-318">En lugar de predecir los rectángulos delimitadores, se calcula el desplazamiento de las dimensiones predefinidas; por lo que se reducen los cálculos necesarios para predecir el rectángulo delimitador.</span><span class="sxs-lookup"><span data-stu-id="2402f-318">Instead of predicting the bounding boxes, the offset from the pre-defined dimensions is calculated therefore reducing the computation required to predict the bounding box.</span></span> <span data-ttu-id="2402f-319">Normalmente, estas proporciones de delimitador se calculan en función del conjunto de datos usado.</span><span class="sxs-lookup"><span data-stu-id="2402f-319">Typically these anchor ratios are calculated based on the dataset used.</span></span> <span data-ttu-id="2402f-320">En este caso, dado que el conjunto de datos es conocido y los valores se han calculado previamente, los delimitadores se pueden codificar de forma rígida.</span><span class="sxs-lookup"><span data-stu-id="2402f-320">In this case because the dataset is known and the values have been pre-computed, the anchors can be hard-coded.</span></span>

<span data-ttu-id="2402f-321">A continuación, defina las etiquetas o clases que el modelo predecirá.</span><span class="sxs-lookup"><span data-stu-id="2402f-321">Next, define the labels or classes that the model will predict.</span></span> <span data-ttu-id="2402f-322">Este modelo predice 20 clases, que es un subconjunto del número total de clases que predice el modelo de YOLOv2 original.</span><span class="sxs-lookup"><span data-stu-id="2402f-322">This model predicts 20 classes which is a subset of the total number of classes predicted by the original YOLOv2 model.</span></span>

<span data-ttu-id="2402f-323">Agregue la lista de etiquetas debajo de `anchors`.</span><span class="sxs-lookup"><span data-stu-id="2402f-323">Add your list of labels below the `anchors`.</span></span> 

[!code-csharp [ParserLabels](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L28-L34)]

<span data-ttu-id="2402f-324">Hay colores asociados a cada una de las clases.</span><span class="sxs-lookup"><span data-stu-id="2402f-324">There are colors associated with each of the classes.</span></span> <span data-ttu-id="2402f-325">Asigne los colores de clase debajo de `labels`:</span><span class="sxs-lookup"><span data-stu-id="2402f-325">Assign your class colors below your `labels`:</span></span>

[!code-csharp [ParserColors](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L36-L59)]

### <a name="create-helper-functions"></a><span data-ttu-id="2402f-326">Crear funciones auxiliares</span><span class="sxs-lookup"><span data-stu-id="2402f-326">Create helper functions</span></span>

<span data-ttu-id="2402f-327">La fase posterior al procesamiento implica una serie de pasos.</span><span class="sxs-lookup"><span data-stu-id="2402f-327">There are a series of steps involved in the post-processing phase.</span></span> <span data-ttu-id="2402f-328">Para ayudar con esto, se pueden emplear varios métodos auxiliares.</span><span class="sxs-lookup"><span data-stu-id="2402f-328">To help with that, several helper methods can be employed.</span></span> 

<span data-ttu-id="2402f-329">Los métodos auxiliares que usa el analizador son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="2402f-329">The helper methods used in by the parser are:</span></span>

- <span data-ttu-id="2402f-330">`Sigmoid` aplica la función sigmoidea que da como resultado un número entre 0 y 1.</span><span class="sxs-lookup"><span data-stu-id="2402f-330">`Sigmoid` applies the sigmoid function that outputs a number between 0 and 1.</span></span>
- <span data-ttu-id="2402f-331">`Softmax` normaliza un vector de entrada en una distribución de probabilidad.</span><span class="sxs-lookup"><span data-stu-id="2402f-331">`Softmax` normalizes an input vector into a probability distribution.</span></span>
- <span data-ttu-id="2402f-332">`GetOffset` asigna los elementos de la salida del modelo unidimensional a la posición correspondiente en un tensor de `125 x 13 x 13`.</span><span class="sxs-lookup"><span data-stu-id="2402f-332">`GetOffset` maps elements in the one-dimensional model output to the corresponding position in a `125 x 13 x 13` tensor.</span></span>
- <span data-ttu-id="2402f-333">`ExtractBoundingBoxes` extrae las dimensiones del rectángulo delimitador mediante el método `GetOffset` de la salida del modelo.</span><span class="sxs-lookup"><span data-stu-id="2402f-333">`ExtractBoundingBoxes` extracts the bounding box dimensions using the `GetOffset` method from the model output.</span></span>
- <span data-ttu-id="2402f-334">`GetConfidence` extrae el valor de confianza que indica qué tan seguro está el modelo de que ha detectado un objeto y usa la función `Sigmoid` para convertirlo en porcentaje.</span><span class="sxs-lookup"><span data-stu-id="2402f-334">`GetConfidence` extracts the confidence value which states how sure the model is that it has detected an object and uses the `Sigmoid` function to turn it into a percentage.</span></span>
- <span data-ttu-id="2402f-335">`MapBoundingBoxToCell` usa las dimensiones del rectángulo delimitador y las asigna a su celda correspondiente dentro de la imagen.</span><span class="sxs-lookup"><span data-stu-id="2402f-335">`MapBoundingBoxToCell` uses the bounding box dimensions and maps them onto its respective cell within the image.</span></span>
- <span data-ttu-id="2402f-336">`ExtractClasses` extrae las predicciones de clase para el rectángulo delimitador de la salida del modelo usando el método `GetOffset` y las convierte en una distribución de probabilidad mediante el método `Softmax`.</span><span class="sxs-lookup"><span data-stu-id="2402f-336">`ExtractClasses` extracts the class predictions for the bounding box from the model output using the `GetOffset` method and turns them into a probability distribution using the `Softmax` method.</span></span>
- <span data-ttu-id="2402f-337">`GetTopResult` selecciona la clase de la lista de clases predichas con la probabilidad más alta.</span><span class="sxs-lookup"><span data-stu-id="2402f-337">`GetTopResult` selects the class from the list of predicted classes with the highest probability.</span></span>
- <span data-ttu-id="2402f-338">`IntersectionOverUnion` filtra los rectángulos delimitadores superpuestos con probabilidades más bajas.</span><span class="sxs-lookup"><span data-stu-id="2402f-338">`IntersectionOverUnion` filters overlapping bounding boxes with lower probabilities.</span></span>

<span data-ttu-id="2402f-339">Agregue el código para todos los métodos auxiliares debajo de la lista de `classColors`.</span><span class="sxs-lookup"><span data-stu-id="2402f-339">Add the code for all the helper methods below your list of `classColors`.</span></span>

[!code-csharp [ParserHelperMethods](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L61-L151)]

<span data-ttu-id="2402f-340">Una vez que haya definido todos los métodos auxiliares, es el momento de usarlos para procesar la salida del modelo.</span><span class="sxs-lookup"><span data-stu-id="2402f-340">Once you have defined all of the helper methods, it's time to use them to process the model output.</span></span>

<span data-ttu-id="2402f-341">Debajo del método `IntersectionOverUnion`, cree el método `ParseOutputs` para procesar la salida generada por el modelo.</span><span class="sxs-lookup"><span data-stu-id="2402f-341">Below the `IntersectionOverUnion` method, create the `ParseOutputs` method to process the output generated by the model.</span></span>

```csharp
public IList<YoloBoundingBox> ParseOutputs(float[] yoloModelOutputs, float threshold = .3F)
{

}
```
    
<span data-ttu-id="2402f-342">Cree una lista para almacenar los rectángulos delimitadores y defina las variables dentro del método `ParseOutputs`.</span><span class="sxs-lookup"><span data-stu-id="2402f-342">Create a list to store your bounding boxes and define variables inside the `ParseOutputs` method.</span></span>

[!code-csharp [BBoxList](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L155)]

<span data-ttu-id="2402f-343">Cada imagen se divide en una cuadrícula de `13 x 13` celdas.</span><span class="sxs-lookup"><span data-stu-id="2402f-343">Each image is divided into a grid of `13 x 13` cells.</span></span> <span data-ttu-id="2402f-344">Cada celda contiene cinco rectángulos delimitadores.</span><span class="sxs-lookup"><span data-stu-id="2402f-344">Each cell contains five bounding boxes.</span></span> <span data-ttu-id="2402f-345">Debajo de la variable `boxes`, agregue código para procesar todos los rectángulos de cada una de las celdas.</span><span class="sxs-lookup"><span data-stu-id="2402f-345">Below the `boxes` variable, add code to process all of the boxes in each of the cells.</span></span>

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

<span data-ttu-id="2402f-346">Dentro del bucle más interno, calcule la posición inicial del rectángulo actual dentro de la salida del modelo unidimensional.</span><span class="sxs-lookup"><span data-stu-id="2402f-346">Inside the inner-most loop, calculate the starting position of the current box within the one-dimensional model output.</span></span>

[!code-csharp [ChannelDef](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L163)]

<span data-ttu-id="2402f-347">Justo debajo de eso, use el método `ExtractBoundingBoxDimensions` para obtener las dimensiones del rectángulo delimitador actual.</span><span class="sxs-lookup"><span data-stu-id="2402f-347">Directly below that, use the `ExtractBoundingBoxDimensions` method to get the dimensions of the current bounding box.</span></span>

[!code-csharp [GetBBoxDims](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L165)]

<span data-ttu-id="2402f-348">Luego, use el método `GetConfidence` para obtener la confianza del rectángulo delimitador actual.</span><span class="sxs-lookup"><span data-stu-id="2402f-348">Then, use the `GetConfidence` method to get the confidence for the current bounding box.</span></span>

[!code-csharp [GetConfidence](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L167)]

<span data-ttu-id="2402f-349">Después de eso, use el método `MapBoundingBoxToCell` para asignar el rectángulo delimitador actual a la celda actual que se está procesando.</span><span class="sxs-lookup"><span data-stu-id="2402f-349">After that, use the `MapBoundingBoxToCell` method to map the current bounding box to the current cell being processed.</span></span>

[!code-csharp [MapBoundingBoxes](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L169)]

<span data-ttu-id="2402f-350">Antes de realizar cualquier procesamiento adicional, compruebe si el valor de confianza es mayor que el umbral proporcionado.</span><span class="sxs-lookup"><span data-stu-id="2402f-350">Before doing any further processing, check whether your confidence value is greater than the threshold provided.</span></span> <span data-ttu-id="2402f-351">Si no es así, procese el siguiente rectángulo delimitador.</span><span class="sxs-lookup"><span data-stu-id="2402f-351">If not, process the next bounding box.</span></span>

[!code-csharp [CheckThreshold1](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L171-L172)]

<span data-ttu-id="2402f-352">De lo contrario, continúe procesando la salida.</span><span class="sxs-lookup"><span data-stu-id="2402f-352">Otherwise, continue processing the output.</span></span> <span data-ttu-id="2402f-353">El paso siguiente consiste en obtener la distribución de probabilidad de las clases previstas para el rectángulo delimitador actual mediante el método `ExtractClasses`.</span><span class="sxs-lookup"><span data-stu-id="2402f-353">The next step is to get the probability distribution of the predicted classes for the current bounding box using the `ExtractClasses` method.</span></span>

[!code-csharp [ExtractClasses](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L174)]

<span data-ttu-id="2402f-354">A continuación, use el método `GetTopResult` para obtener el valor y el índice de la clase con la probabilidad más alta para el rectángulo actual y calcular su puntuación.</span><span class="sxs-lookup"><span data-stu-id="2402f-354">Then, use the `GetTopResult` method to get the value and index of the class with the highest probability for the current box and compute its score.</span></span>

[!code-csharp [GetTopResult](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L176-L177)]

<span data-ttu-id="2402f-355">Use `topScore` para conservar una vez más solo aquellos rectángulos delimitadores que estén por encima del umbral especificado.</span><span class="sxs-lookup"><span data-stu-id="2402f-355">Use the `topScore` to once again keep only those bounding boxes that are above the specified threshold.</span></span>

[!code-csharp [CheckThreshold2](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L179-L180)]

<span data-ttu-id="2402f-356">Por último, si el rectángulo delimitador actual supera el umbral, cree un nuevo objeto `BoundingBox` y agréguelo a la lista `boxes`.</span><span class="sxs-lookup"><span data-stu-id="2402f-356">Finally, if the current bounding box exceeds the threshold, create a new `BoundingBox` object and add it to the `boxes` list.</span></span>

[!code-csharp [AddBBoxToList](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L182-L194)]

<span data-ttu-id="2402f-357">Una vez que se hayan procesado todas las celdas de la imagen, devuelva la lista `boxes`.</span><span class="sxs-lookup"><span data-stu-id="2402f-357">Once all cells in the image have been processed, return the `boxes` list.</span></span> <span data-ttu-id="2402f-358">Agregue la siguiente instrucción return debajo del bucle for más exterior en el método `ParseOutputs`.</span><span class="sxs-lookup"><span data-stu-id="2402f-358">Add the following return statement below the outer-most for-loop in the `ParseOutputs` method.</span></span>

[!code-csharp [ReturnBoxes](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L198)]

### <a name="filter-overlapping-boxes"></a><span data-ttu-id="2402f-359">Filtrar los rectángulos superpuestos</span><span class="sxs-lookup"><span data-stu-id="2402f-359">Filter overlapping boxes</span></span>

<span data-ttu-id="2402f-360">Ahora que todos los rectángulos delimitadores de gran confianza se han extraído de la salida del modelo, es necesario realizar un filtrado adicional para quitar las imágenes superpuestas.</span><span class="sxs-lookup"><span data-stu-id="2402f-360">Now that all of the highly confident bounding boxes have been extracted from the model output, additional filtering needs to be done to remove overlapping images.</span></span> <span data-ttu-id="2402f-361">Agregue un método denominado `FilterBoundingBoxes` debajo del método `ParseOutputs`:</span><span class="sxs-lookup"><span data-stu-id="2402f-361">Add a method called `FilterBoundingBoxes` below the `ParseOutputs` method:</span></span>

```csharp
public IList<YoloBoundingBox> FilterBoundingBoxes(IList<YoloBoundingBox> boxes, int limit, float threshold)
{

}
```

<span data-ttu-id="2402f-362">Dentro del método `FilterBoundingBoxes`, empiece por crear una matriz igual al tamaño de los rectángulos detectados, y marque todas las ranuras como activas o listas para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="2402f-362">Inside the `FilterBoundingBoxes` method, start off by creating an array equal to the size of detected boxes and marking all slots as active or ready for processing.</span></span>

[!code-csharp [InitActiveSlots](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L203-L207)]

<span data-ttu-id="2402f-363">Después, ordene la lista que contiene los rectángulos delimitadores en orden descendente en función de la confianza.</span><span class="sxs-lookup"><span data-stu-id="2402f-363">Then, sort the list containing your bounding boxes in descending order based on confidence.</span></span>

[!code-csharp [SortBoxes](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L209-L211)]

<span data-ttu-id="2402f-364">Luego de eso, cree una lista que contenga los resultados filtrados.</span><span class="sxs-lookup"><span data-stu-id="2402f-364">After that, create a list to hold the filtered results.</span></span>

[!code-csharp [InitFilterResult](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L213)]

<span data-ttu-id="2402f-365">Comience a procesar cada rectángulo delimitador iterando cada uno de los rectángulos delimitadores.</span><span class="sxs-lookup"><span data-stu-id="2402f-365">Begin processing each bounding box by iterating over each of the bounding boxes.</span></span>

```csharp
for (int i = 0; i < boxes.Count; i++)
{

}
```

<span data-ttu-id="2402f-366">Dentro de este bucle for, compruebe si se puede procesar el rectángulo delimitador actual.</span><span class="sxs-lookup"><span data-stu-id="2402f-366">Inside of this for-loop, check whether the current bounding box can be processed.</span></span>

```csharp
if (isActiveBoxes[i])
{
    
}
```

<span data-ttu-id="2402f-367">Si es así, agregue el rectángulo delimitador a la lista de resultados.</span><span class="sxs-lookup"><span data-stu-id="2402f-367">If so, add the bounding box to the list of results.</span></span> <span data-ttu-id="2402f-368">Si los resultados superan el límite de rectángulos especificado que se van a extraer, interrumpa el bucle.</span><span class="sxs-lookup"><span data-stu-id="2402f-368">If the results exceeds the specified limit of boxes to be extracted, break out of the loop.</span></span> <span data-ttu-id="2402f-369">Agregue el código siguiente dentro de la instrucción if.</span><span class="sxs-lookup"><span data-stu-id="2402f-369">Add the following code inside the if-statement.</span></span>

[!code-csharp [AddFirstBBoxToResults](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L219-L223)]

<span data-ttu-id="2402f-370">De lo contrario, fíjese en los rectángulos delimitadores adyacentes.</span><span class="sxs-lookup"><span data-stu-id="2402f-370">Otherwise, look at the adjacent bounding boxes.</span></span> <span data-ttu-id="2402f-371">Agregue el código siguiente debajo de la comprobación del límite del rectángulo.</span><span class="sxs-lookup"><span data-stu-id="2402f-371">Add the following code below the box limit check.</span></span>

```csharp
for (var j = i + 1; j < boxes.Count; j++)
{

}
```

<span data-ttu-id="2402f-372">Al igual que el primer rectángulo, si el rectángulo adyacente está activo o listo para procesarse, use el método `IntersectionOverUnion` para comprobar si el primer rectángulo y el segundo rectángulo superan el umbral especificado.</span><span class="sxs-lookup"><span data-stu-id="2402f-372">Like the first box, if the adjacent box is active or ready to be processed, use the `IntersectionOverUnion` method to check whether the first box and the second box exceed the specified threshold.</span></span> <span data-ttu-id="2402f-373">Agregue el código siguiente a su bucle for más interno.</span><span class="sxs-lookup"><span data-stu-id="2402f-373">Add the following code to your inner-most for-loop.</span></span>

[!code-csharp [IOUBBox](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L227-L239)]

<span data-ttu-id="2402f-374">Fuera del bucle for más interno que comprueba los rectángulos delimitadores adyacentes, compruebe si hay rectángulos delimitadores restantes para procesar.</span><span class="sxs-lookup"><span data-stu-id="2402f-374">Outside of the inner-most for-loop that checks adjacent bounding boxes, see whether there are any remaining bounding boxes to be processed.</span></span> <span data-ttu-id="2402f-375">En caso contrario, interrumpa el bucle for externo.</span><span class="sxs-lookup"><span data-stu-id="2402f-375">If not, break out of the outer for-loop.</span></span>

[!code-csharp [CheckActiveSlots](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L242-L243)]

<span data-ttu-id="2402f-376">Por último, fuera del bucle for inicial del método `FilterBoundingBoxes`, devuelva los resultados:</span><span class="sxs-lookup"><span data-stu-id="2402f-376">Finally, outside of the initial for-loop of the `FilterBoundingBoxes` method, return the results:</span></span>

[!code-csharp [ReturnFilteredBBox](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L246)]

<span data-ttu-id="2402f-377">Estupendo.</span><span class="sxs-lookup"><span data-stu-id="2402f-377">Great!</span></span> <span data-ttu-id="2402f-378">Ahora es el momento de usar este código junto con el modelo para la puntuación.</span><span class="sxs-lookup"><span data-stu-id="2402f-378">Now it's time to use this code along with the model for scoring.</span></span>

## <a name="use-the-model-for-scoring"></a><span data-ttu-id="2402f-379">Uso del modelo para puntuación</span><span class="sxs-lookup"><span data-stu-id="2402f-379">Use the model for scoring</span></span>

<span data-ttu-id="2402f-380">Al igual que con el procesamiento posterior, hay algunos pasos en el procedimiento de puntuación.</span><span class="sxs-lookup"><span data-stu-id="2402f-380">Just like with post-processing, there are a few steps in the scoring steps.</span></span> <span data-ttu-id="2402f-381">Para ayudarlo con esto, agregue al proyecto una clase que contendrá la lógica de puntuación.</span><span class="sxs-lookup"><span data-stu-id="2402f-381">To help with this, add a class that will contain the scoring logic to your project.</span></span>

1. <span data-ttu-id="2402f-382">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="2402f-382">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="2402f-383">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *OnnxModelScorer.cs*.</span><span class="sxs-lookup"><span data-stu-id="2402f-383">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *OnnxModelScorer.cs*.</span></span> <span data-ttu-id="2402f-384">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2402f-384">Then, select the **Add** button.</span></span>

    <span data-ttu-id="2402f-385">El archivo *OnnxModelScorer.cs* se abre en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="2402f-385">The *OnnxModelScorer.cs* file opens in the code editor.</span></span> <span data-ttu-id="2402f-386">Agregue la instrucción `using` siguiente al principio del archivo *OnnxModelScorer.cs*:</span><span class="sxs-lookup"><span data-stu-id="2402f-386">Add the following `using` statement to the top of *OnnxModelScorer.cs*:</span></span>

    [!code-csharp [ScorerUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L1-L7)]

    <span data-ttu-id="2402f-387">Dentro de la definición de la clase `OnnxModelScorer`, agregue las variables siguientes.</span><span class="sxs-lookup"><span data-stu-id="2402f-387">Inside the `OnnxModelScorer` class definition, add the following variables.</span></span>

    [!code-csharp [InitScorerVars](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L13-L17)]

    <span data-ttu-id="2402f-388">Justo debajo de eso, cree un constructor para la clase `OnnxModelScorer`que inicializará las variables definidas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="2402f-388">Directly below that, create a constructor for the `OnnxModelScorer` class that will initialize the previously defined variables.</span></span>

    [!code-csharp [ScorerCtor](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L19-L24)]

    <span data-ttu-id="2402f-389">Una vez creado el constructor, defina un par de estructuras que contengan variables relacionadas con la configuración de la imagen y el modelo.</span><span class="sxs-lookup"><span data-stu-id="2402f-389">Once you have created the constructor, define a couple of structs that contain variables related to the image and model settings.</span></span> <span data-ttu-id="2402f-390">Cree una estructura denominada `ImageNetSettings` para que contenga la altura y el ancho esperados como entrada para el modelo.</span><span class="sxs-lookup"><span data-stu-id="2402f-390">Create a struct called `ImageNetSettings` to contain the height and width expected as input for the model.</span></span>

    [!code-csharp [ImageNetSettingStruct](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L26-L30)]

    <span data-ttu-id="2402f-391">Después, cree otra estructura denominada `TinyYoloModelSettings` que contenga los nombres de las capas de entrada y salida del modelo.</span><span class="sxs-lookup"><span data-stu-id="2402f-391">After that, create another struct called `TinyYoloModelSettings` which contains the names of the input and output layers of the model.</span></span> <span data-ttu-id="2402f-392">Para visualizar el nombre de las capas de entrada y salida del modelo, puede usar una herramienta como [Netron.](https://github.com/lutzroeder/netron)</span><span class="sxs-lookup"><span data-stu-id="2402f-392">To visualize the name of the input and output layers of the model, you can use a tool like [Netron](https://github.com/lutzroeder/netron).</span></span>

    [!code-csharp [YoloSettingsStruct](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L32-L43)]

    <span data-ttu-id="2402f-393">A continuación, cree el primer conjunto de métodos que usará para la puntuación.</span><span class="sxs-lookup"><span data-stu-id="2402f-393">Next, create the first set of methods use for scoring.</span></span> <span data-ttu-id="2402f-394">Cree el método `LoadModel` dentro de la clase `OnnxModelScorer`.</span><span class="sxs-lookup"><span data-stu-id="2402f-394">Create the `LoadModel` method inside of your `OnnxModelScorer` class.</span></span>

    ```csharp
    private ITransformer LoadModel(string modelLocation)
    {

    }
    ```

    <span data-ttu-id="2402f-395">Dentro del método `LoadModel`, agregue el código siguiente para el registro.</span><span class="sxs-lookup"><span data-stu-id="2402f-395">Inside the `LoadModel` method, add the following code for logging.</span></span>

    [!code-csharp [LoadModelLog](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L47-L49)]

    <span data-ttu-id="2402f-396">Las canalizaciones ML.NET suelen esperar que los datos funcionen cuando se llama al método [`Fit`](xref:Microsoft.ML.IEstimator%601.Fit*).</span><span class="sxs-lookup"><span data-stu-id="2402f-396">ML.NET pipelines typically expect data to operate on when the [`Fit`](xref:Microsoft.ML.IEstimator%601.Fit*) method is called.</span></span> <span data-ttu-id="2402f-397">En este caso, se usará un proceso similar al de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="2402f-397">In this case, a process similar to training will be used.</span></span> <span data-ttu-id="2402f-398">Sin embargo, dado que no se está produciendo ningún entrenamiento real, es aceptable usar un [`IDataView`](xref:Microsoft.ML.IDataView) vacío.</span><span class="sxs-lookup"><span data-stu-id="2402f-398">However, because no actual training is happening, it is acceptable to use an empty [`IDataView`](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="2402f-399">Cree un nuevo [`IDataView`](xref:Microsoft.ML.IDataView) para la canalización a partir de una lista vacía.</span><span class="sxs-lookup"><span data-stu-id="2402f-399">Create a new [`IDataView`](xref:Microsoft.ML.IDataView) for the pipeline from an empty list.</span></span>

    [!code-csharp [LoadEmptyIDV](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L52)]    

    <span data-ttu-id="2402f-400">Luego de eso, defina la canalización.</span><span class="sxs-lookup"><span data-stu-id="2402f-400">Below that, define the pipeline.</span></span> <span data-ttu-id="2402f-401">La canalización constará de cuatro transformaciones.</span><span class="sxs-lookup"><span data-stu-id="2402f-401">The pipeline will consist of four transforms.</span></span>

    - <span data-ttu-id="2402f-402">[`LoadImages`](xref:Microsoft.ML.ImageEstimatorsCatalog.LoadImages*) carga la imagen como mapa de bits.</span><span class="sxs-lookup"><span data-stu-id="2402f-402">[`LoadImages`](xref:Microsoft.ML.ImageEstimatorsCatalog.LoadImages*) loads the image as a Bitmap.</span></span>
    - <span data-ttu-id="2402f-403">[`ResizeImages`](xref:Microsoft.ML.ImageEstimatorsCatalog.ResizeImages*) cambia la escala de la imagen al tamaño especificado (en este caso, `416 x 416`).</span><span class="sxs-lookup"><span data-stu-id="2402f-403">[`ResizeImages`](xref:Microsoft.ML.ImageEstimatorsCatalog.ResizeImages*) rescales the image to the size specified (in this case, `416 x 416`).</span></span>
    - <span data-ttu-id="2402f-404">[`ExtractPixels`](xref:Microsoft.ML.ImageEstimatorsCatalog.ExtractPixels*) cambia la representación en píxeles de la imagen de un mapa de bits a un vector numérico.</span><span class="sxs-lookup"><span data-stu-id="2402f-404">[`ExtractPixels`](xref:Microsoft.ML.ImageEstimatorsCatalog.ExtractPixels*) changes the pixel representation of the image from a Bitmap to a numerical vector.</span></span>
    - <span data-ttu-id="2402f-405">[`ApplyOnnxModel`](xref:Microsoft.ML.OnnxCatalog.ApplyOnnxModel*) carga el modelo de ONNX y lo usa para puntuar los datos proporcionados.</span><span class="sxs-lookup"><span data-stu-id="2402f-405">[`ApplyOnnxModel`](xref:Microsoft.ML.OnnxCatalog.ApplyOnnxModel*) loads the ONNX model and uses it to score on the data provided.</span></span>

    <span data-ttu-id="2402f-406">Defina la canalización en el método `LoadModel` debajo de la variable `data`.</span><span class="sxs-lookup"><span data-stu-id="2402f-406">Define your pipeline in the `LoadModel` method below the `data` variable.</span></span>

    [!code-csharp [ScoringPipeline](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L55-L58)]

    <span data-ttu-id="2402f-407">Ahora es el momento de crear una instancia del modelo para la puntuación.</span><span class="sxs-lookup"><span data-stu-id="2402f-407">Now it's time to instantiate the model for scoring.</span></span> <span data-ttu-id="2402f-408">Llame al método [`Fit`](xref:Microsoft.ML.IEstimator%601.Fit*) en la canalización y devuélvalo para seguir procesándolo.</span><span class="sxs-lookup"><span data-stu-id="2402f-408">Call the [`Fit`](xref:Microsoft.ML.IEstimator%601.Fit*) method on the pipeline and return it for further processing.</span></span>

    [!code-csharp [FitReturnModel](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L61-L63)]

<span data-ttu-id="2402f-409">Una vez que el modelo esté cargado, podrá usarse para hacer predicciones.</span><span class="sxs-lookup"><span data-stu-id="2402f-409">Once the model is loaded, it can then be used to make predictions.</span></span> <span data-ttu-id="2402f-410">Para facilitar este proceso, cree un método denominado `PredictDataUsingModel` debajo del método `LoadModel`.</span><span class="sxs-lookup"><span data-stu-id="2402f-410">To facilitate that process, create a method called `PredictDataUsingModel` below the `LoadModel` method.</span></span>

```csharp
private IEnumerable<float[]> PredictDataUsingModel(IDataView testData, ITransformer model)
{

}
```

<span data-ttu-id="2402f-411">Dentro de `PredictDataUsingModel`, agregue el código siguiente para el registro.</span><span class="sxs-lookup"><span data-stu-id="2402f-411">Inside the `PredictDataUsingModel`, add the following code for logging.</span></span>

[!code-csharp [PredictDataLog](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L68-L71)]

<span data-ttu-id="2402f-412">A continuación, use el método [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) para puntuar los datos.</span><span class="sxs-lookup"><span data-stu-id="2402f-412">Then, use the [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) method to score the data.</span></span>

[!code-csharp [ScoreImages](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L73)]

<span data-ttu-id="2402f-413">Extraiga las probabilidades previstas y devuélvalas para su procesamiento adicional.</span><span class="sxs-lookup"><span data-stu-id="2402f-413">Extract the predicted probabilities and return them for additional processing.</span></span>

[!code-csharp [ReturnModelOutput](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L75-L77)]

<span data-ttu-id="2402f-414">Ahora que ambos pasos están configurados, combínelos en un único método.</span><span class="sxs-lookup"><span data-stu-id="2402f-414">Now that both steps are set up, combine them into a single method.</span></span> <span data-ttu-id="2402f-415">Debajo del método `PredictDataUsingModel`, agregue un nuevo método denominado `Score`.</span><span class="sxs-lookup"><span data-stu-id="2402f-415">Below the `PredictDataUsingModel` method, add a new method called `Score`.</span></span>

[!code-csharp [ScoreMethod](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L80-L85)]

<span data-ttu-id="2402f-416">Ya casi lo tenemos.</span><span class="sxs-lookup"><span data-stu-id="2402f-416">Almost there!</span></span> <span data-ttu-id="2402f-417">Ahora es el momento de ponerlo todo en práctica.</span><span class="sxs-lookup"><span data-stu-id="2402f-417">Now it's time to put it all to use.</span></span>

## <a name="detect-objects"></a><span data-ttu-id="2402f-418">Detectar objetos</span><span class="sxs-lookup"><span data-stu-id="2402f-418">Detect objects</span></span>

<span data-ttu-id="2402f-419">Ahora que ha completado toda la configuración, es el momento de detectar algunos objetos.</span><span class="sxs-lookup"><span data-stu-id="2402f-419">Now that all of the setup is complete, it's time to detect some objects.</span></span> <span data-ttu-id="2402f-420">Dentro del método `Main` de la clase *Program.cs*, agregue una instrucción try-catch.</span><span class="sxs-lookup"><span data-stu-id="2402f-420">Inside the `Main` method of your *Program.cs* class, add a try-catch statement.</span></span>

```csharp
try
{

}
catch (Exception ex)
{
    Console.WriteLine(ex.ToString());
}
```

<span data-ttu-id="2402f-421">Dentro del bloque `try`, empiece a implementar la lógica de detección de objetos.</span><span class="sxs-lookup"><span data-stu-id="2402f-421">Inside of the `try` block, start implementing the object detection logic.</span></span> <span data-ttu-id="2402f-422">En primer lugar, cargue los datos en un [`IDataView`](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="2402f-422">First, load the data into an [`IDataView`](xref:Microsoft.ML.IDataView).</span></span>

[!code-csharp [LoadData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L29-L30)]

<span data-ttu-id="2402f-423">Luego, cree una instancia de `OnnxModelScorer` y úsela para puntuar los datos cargados.</span><span class="sxs-lookup"><span data-stu-id="2402f-423">Then, create an instance of `OnnxModelScorer` and use it to score the loaded data.</span></span>

[!code-csharp [ScoreData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L33-L36)]

<span data-ttu-id="2402f-424">Ahora es el momento de completar el paso de procesamiento posterior.</span><span class="sxs-lookup"><span data-stu-id="2402f-424">Now it's time for the post-processing step.</span></span> <span data-ttu-id="2402f-425">Cree una instancia de `YoloOutputParser` y úsela para procesar la salida del modelo.</span><span class="sxs-lookup"><span data-stu-id="2402f-425">Create an instance of `YoloOutputParser` and use it to process the model output.</span></span>

[!code-csharp [ParsePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L39-L44)]

<span data-ttu-id="2402f-426">Una vez que se haya procesado la salida del modelo, es el momento de dibujar los rectángulos delimitadores en las imágenes.</span><span class="sxs-lookup"><span data-stu-id="2402f-426">Once the model output has been processed, it's time to draw the bounding boxes on the images.</span></span> <span data-ttu-id="2402f-427">Cree un bucle for para iterar cada una de las imágenes puntuadas.</span><span class="sxs-lookup"><span data-stu-id="2402f-427">Create a for-loop to iterate over each of the scored images.</span></span>

```csharp
for (var i = 0; i < images.Count(); i++)
{

}
```

<span data-ttu-id="2402f-428">Dentro del bucle for, obtenga el nombre del archivo de imagen y los rectángulos delimitadores asociados a él.</span><span class="sxs-lookup"><span data-stu-id="2402f-428">Inside of the for-loop, get the name of the image file and the bounding boxes associated with it.</span></span>

[!code-csharp [GetImageFileName](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L49-L50)]

<span data-ttu-id="2402f-429">A continuación, use el método `DrawBoundingBox` para dibujar los rectángulos delimitadores en la imagen.</span><span class="sxs-lookup"><span data-stu-id="2402f-429">Below that, use the `DrawBoundingBox` method to draw the bounding boxes on the image.</span></span>

[!code-csharp [DrawBBoxes](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L52)]

<span data-ttu-id="2402f-430">Por último, agregue cierta lógica de registro con el método `LogDetectedObjects`.</span><span class="sxs-lookup"><span data-stu-id="2402f-430">Lastly, add some logging logic with the `LogDetectedObjects` method.</span></span>

[!code-csharp [LogPredictionsOutput](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L54)]

<span data-ttu-id="2402f-431">Después de la instrucción try-catch, agregue lógica adicional para indicar que el proceso ha terminado de ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="2402f-431">After the try-catch statement, add additional logic to indicate the process is done running.</span></span>

[!code-csharp [EndProcessLog](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L62-L63)]

<span data-ttu-id="2402f-432">Ya está.</span><span class="sxs-lookup"><span data-stu-id="2402f-432">That's it!</span></span> 

## <a name="results"></a><span data-ttu-id="2402f-433">Resultados</span><span class="sxs-lookup"><span data-stu-id="2402f-433">Results</span></span> 

<span data-ttu-id="2402f-434">Después de seguir los pasos anteriores, ejecute la aplicación de consola (Ctrl + F5).</span><span class="sxs-lookup"><span data-stu-id="2402f-434">After following the previous steps, run your console app (Ctrl + F5).</span></span> <span data-ttu-id="2402f-435">Los resultados deberían ser similares a la salida siguiente.</span><span class="sxs-lookup"><span data-stu-id="2402f-435">Your results should be similar to the following output.</span></span> <span data-ttu-id="2402f-436">Es posible que vea advertencias o mensajes de procesamiento, si bien se han quitado de los resultados siguientes para mayor claridad.</span><span class="sxs-lookup"><span data-stu-id="2402f-436">You may see warnings or processing messages, but these messages have been removed from the following results for clarity.</span></span>

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

<span data-ttu-id="2402f-437">Para ver las imágenes con rectángulos delimitadores, desplácese hasta el directorio `assets/images/output/`.</span><span class="sxs-lookup"><span data-stu-id="2402f-437">To see the images with bounding boxes, navigate to the `assets/images/output/` directory.</span></span> <span data-ttu-id="2402f-438">A continuación se muestra un ejemplo de una de las imágenes procesadas.</span><span class="sxs-lookup"><span data-stu-id="2402f-438">Below is a sample from one of the processed images.</span></span> 

![](./media/object-detection-onnx/image3.jpg)

<span data-ttu-id="2402f-439">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="2402f-439">Congratulations!</span></span> <span data-ttu-id="2402f-440">Ha creado correctamente un modelo de Machine Learning para la detección de objetos al reutilizar un modelo de `ONNX` entrenado previamente en ML.NET.</span><span class="sxs-lookup"><span data-stu-id="2402f-440">You've now successfully built a machine learning model for object detection by reusing a pre-trained `ONNX` model in ML.NET.</span></span>

<span data-ttu-id="2402f-441">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx).</span><span class="sxs-lookup"><span data-stu-id="2402f-441">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx) repository.</span></span>

<span data-ttu-id="2402f-442">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="2402f-442">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="2402f-443">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="2402f-443">Understand the problem</span></span>
> * <span data-ttu-id="2402f-444">Conocer qué es ONNX y cómo funciona con ML.NET</span><span class="sxs-lookup"><span data-stu-id="2402f-444">Learn what ONNX is and how it works with ML.NET</span></span>
> * <span data-ttu-id="2402f-445">Entender el modelo</span><span class="sxs-lookup"><span data-stu-id="2402f-445">Understand the model</span></span>
> * <span data-ttu-id="2402f-446">Volver a usar el modelo entrenado previamente</span><span class="sxs-lookup"><span data-stu-id="2402f-446">Reuse the pre-trained model</span></span>
> * <span data-ttu-id="2402f-447">Detectar objetos con un modelo cargado</span><span class="sxs-lookup"><span data-stu-id="2402f-447">Detect objects with a loaded model</span></span>

<span data-ttu-id="2402f-448">Consulte el repositorio de GitHub con ejemplos de Machine Learning para explorar un ejemplo expandido de detección de objetos.</span><span class="sxs-lookup"><span data-stu-id="2402f-448">Check out the Machine Learning samples GitHub repository to explore an expanded object detection sample.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="2402f-449">Repositorio dotnet/machinelearning-samples de GitHub</span><span class="sxs-lookup"><span data-stu-id="2402f-449">dotnet/machinelearning-samples GitHub repository</span></span>](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/end-to-end-apps/DeepLearning_ObjectDetection_Onnx)
