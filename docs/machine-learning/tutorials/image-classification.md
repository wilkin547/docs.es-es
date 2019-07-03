---
title: 'Tutorial: Volver a entrenar un clasificador de imágenes de TensorFlow (aprendizaje de transferencia)'
description: Obtenga información sobre cómo volver a entrenar un modelo de TensorFlow de clasificación de imágenes con el aprendizaje de transferencia y ML.NET. El modelo original se entrenó para clasificar imágenes individuales. Después de volver a realizar el entrenamiento, el nuevo modelo organiza las imágenes en categorías generales.
ms.date: 06/12/2019
ms.topic: tutorial
ms.custom: mvc, title-hack-0612
ms.openlocfilehash: 62a926795ce34a8c1639f1d42ebbb34b53dc67ad
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2019
ms.locfileid: "67401734"
---
# <a name="tutorial-retrain-a-tensorflow-image-classifier-with-transfer-learning-and-mlnet"></a><span data-ttu-id="3ef42-105">Tutorial: Volver a entrenar un clasificador de imagen de TensorFlow con el aprendizaje de transferencia y ML.NET</span><span class="sxs-lookup"><span data-stu-id="3ef42-105">Tutorial: Retrain a TensorFlow image classifier with transfer learning and ML.NET</span></span>

<span data-ttu-id="3ef42-106">Obtenga información sobre cómo volver a entrenar un modelo de TensorFlow de clasificación de imágenes con el aprendizaje de transferencia y ML.NET.</span><span class="sxs-lookup"><span data-stu-id="3ef42-106">Learn how to retrain an image classification TensorFlow model with transfer learning and ML.NET.</span></span> <span data-ttu-id="3ef42-107">El modelo original se entrenó para clasificar imágenes individuales.</span><span class="sxs-lookup"><span data-stu-id="3ef42-107">The original model was trained to classify individual images.</span></span> <span data-ttu-id="3ef42-108">Después de volver a realizar el entrenamiento, el nuevo modelo organiza las imágenes en categorías generales.</span><span class="sxs-lookup"><span data-stu-id="3ef42-108">After retraining, the new model organizes the images into broad categories.</span></span> 

<span data-ttu-id="3ef42-109">Entrenar un modelo de [clasificación de imágenes](https://en.wikipedia.org/wiki/Outline_of_object_recognition) desde cero requiere establecer millones de parámetros, una enorme cantidad de datos de aprendizaje etiquetados y una gran cantidad de recursos informáticos (cientos de horas de GPU).</span><span class="sxs-lookup"><span data-stu-id="3ef42-109">Training an [Image Classification](https://en.wikipedia.org/wiki/Outline_of_object_recognition) model from scratch requires setting millions of parameters, a ton of labeled training data and a vast amount of compute resources (hundreds of GPU hours).</span></span> <span data-ttu-id="3ef42-110">Si bien no es tan eficaz como entrenar un modelo personalizado desde cero, el aprendizaje por transferencia permite acortar este proceso al trabajar con miles de imágenes frente a millones de imágenes etiquetadas y crear un modelo personalizado con bastante rapidez (menos de una hora en una máquina sin GPU).</span><span class="sxs-lookup"><span data-stu-id="3ef42-110">While not as effective as training a custom model from scratch, transfer learning allows you to shortcut this process by working with thousands of images vs. millions of labeled images and build a customized model fairly quickly (within an hour on a machine without a GPU).</span></span>

<span data-ttu-id="3ef42-111">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="3ef42-111">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="3ef42-112">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="3ef42-112">Understand the problem</span></span>
> * <span data-ttu-id="3ef42-113">Volver a usar y ajustar el modelo entrenado previamente</span><span class="sxs-lookup"><span data-stu-id="3ef42-113">Reuse and tune the pre-trained model</span></span>
> * <span data-ttu-id="3ef42-114">Clasificar imágenes</span><span class="sxs-lookup"><span data-stu-id="3ef42-114">Classify Images</span></span>

## <a name="what-is-transfer-learning"></a><span data-ttu-id="3ef42-115">¿Qué es el aprendizaje de transferencia?</span><span class="sxs-lookup"><span data-stu-id="3ef42-115">What is transfer learning?</span></span>

<span data-ttu-id="3ef42-116">¿Qué pasaría si pudiera volver a usar un modelo que ya se entrenó previamente para resolver un problema similar y volver a entrenar la totalidad o algunas de las capas de ese modelo para que resuelva su problema?</span><span class="sxs-lookup"><span data-stu-id="3ef42-116">What if you could reuse a model that's already been pre trained to solve a similar problem and retrain either all or some of the layers of that model to make it solve your problem?</span></span> <span data-ttu-id="3ef42-117">Esta técnica de volver a usar parte de un modelo ya entrenado para crear un modelo nuevo se conoce como [aprendizaje por transferencia](https://en.wikipedia.org/wiki/Transfer_learning).</span><span class="sxs-lookup"><span data-stu-id="3ef42-117">This technique of reusing part of an already trained model to build a new model is known as [transfer learning](https://en.wikipedia.org/wiki/Transfer_learning).</span></span>

## <a name="image-classification-sample-overview"></a><span data-ttu-id="3ef42-118">Información general del ejemplo de clasificación de imágenes</span><span class="sxs-lookup"><span data-stu-id="3ef42-118">Image classification sample overview</span></span>

<span data-ttu-id="3ef42-119">El ejemplo es una aplicación de consola que usa ML.NET para crear un clasificador de imágenes mediante la reutilización de un modelo entrenado previamente para clasificar imágenes con una pequeña cantidad de datos de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="3ef42-119">The sample is a console application that uses ML.NET to build an image classifier by reusing a pre-trained model to classify images with a small amount of training data.</span></span>

<span data-ttu-id="3ef42-120">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF).</span><span class="sxs-lookup"><span data-stu-id="3ef42-120">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3ef42-121">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3ef42-121">Prerequisites</span></span>

* <span data-ttu-id="3ef42-122">[Visual Studio 2017 15.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.</span><span class="sxs-lookup"><span data-stu-id="3ef42-122">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* <span data-ttu-id="3ef42-123">Paquete NuGet de Microsoft.ML 1.0.0</span><span class="sxs-lookup"><span data-stu-id="3ef42-123">Microsoft.ML 1.0.0 Nuget package</span></span>
* <span data-ttu-id="3ef42-124">Paquete NuGet de Microsoft.ML.ImageAnalytics 1.0.0</span><span class="sxs-lookup"><span data-stu-id="3ef42-124">Microsoft.ML.ImageAnalytics 1.0.0 Nuget package</span></span>
* <span data-ttu-id="3ef42-125">Paquete NuGet de Microsoft.ML.TensorFlow 0.12.0</span><span class="sxs-lookup"><span data-stu-id="3ef42-125">Microsoft.ML.TensorFlow 0.12.0 Nuget package</span></span>

* [<span data-ttu-id="3ef42-126">El archivo ZIP del directorio de recursos del tutorial</span><span class="sxs-lookup"><span data-stu-id="3ef42-126">The tutorial assets directory .ZIP file</span></span>](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip)

* [<span data-ttu-id="3ef42-127">El modelo de Machine Learning de InceptionV3</span><span class="sxs-lookup"><span data-stu-id="3ef42-127">The InceptionV3 machine learning model</span></span>](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="3ef42-128">Seleccionar la tarea de aprendizaje automático adecuada</span><span class="sxs-lookup"><span data-stu-id="3ef42-128">Select the appropriate machine learning task</span></span>

<span data-ttu-id="3ef42-129">El [aprendizaje profundo](https://en.wikipedia.org/wiki/Deep_learning) es un subconjunto de Machine Learning, que está revolucionando áreas como Computer Vision y reconocimiento de voz.</span><span class="sxs-lookup"><span data-stu-id="3ef42-129">[Deep learning](https://en.wikipedia.org/wiki/Deep_learning) is a subset of Machine Learning, which is revolutionizing areas like Computer Vision and Speech Recognition.</span></span>

<span data-ttu-id="3ef42-130">Los modelos de aprendizaje profundo se entrenan mediante el uso de grandes conjuntos de [datos etiquetados](https://en.wikipedia.org/wiki/Labeled_data) y [redes neuronales](https://en.wikipedia.org/wiki/Artificial_neural_network) que contienen varias capas de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="3ef42-130">Deep learning models are trained by using large sets of [labeled data](https://en.wikipedia.org/wiki/Labeled_data) and [neural networks](https://en.wikipedia.org/wiki/Artificial_neural_network) that contain multiple learning layers.</span></span> <span data-ttu-id="3ef42-131">Aprendizaje profundo:</span><span class="sxs-lookup"><span data-stu-id="3ef42-131">Deep learning:</span></span>

* <span data-ttu-id="3ef42-132">Funciona mejor en algunas tareas como Computer Vision.</span><span class="sxs-lookup"><span data-stu-id="3ef42-132">Performs better on some tasks like Computer Vision.</span></span>

* <span data-ttu-id="3ef42-133">Funciona bien con enormes cantidades de datos.</span><span class="sxs-lookup"><span data-stu-id="3ef42-133">Performs well on huge data amounts.</span></span>

<span data-ttu-id="3ef42-134">La clasificación de imágenes es una tarea de Machine Learning común que nos permite clasificar imágenes automáticamente en varias categorías, como:</span><span class="sxs-lookup"><span data-stu-id="3ef42-134">Image Classification is a common Machine Learning task that allows us to automatically classify images into multiple categories such as:</span></span>

* <span data-ttu-id="3ef42-135">Detectar o no una cara humana en una imagen.</span><span class="sxs-lookup"><span data-stu-id="3ef42-135">Detecting a human face in an image or not.</span></span>
* <span data-ttu-id="3ef42-136">Detectar gatos o perros.</span><span class="sxs-lookup"><span data-stu-id="3ef42-136">Detecting Cats vs. dogs.</span></span>

 <span data-ttu-id="3ef42-137">O bien, como en las imágenes siguientes, determinar si una imagen es un alimento, un juguete o un dispositivo:</span><span class="sxs-lookup"><span data-stu-id="3ef42-137">Or as in the following images determining if an image is a(n)  food, toy, or appliance:</span></span>

<span data-ttu-id="3ef42-138">![imagen de una pizza](./media/image-classification/220px-Pepperoni_pizza.jpg)
![imagen de un oso de peluche](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![imagen de una tostadora](./media/image-classification/193px-Broodrooster.jpg)</span><span class="sxs-lookup"><span data-stu-id="3ef42-138">![pizza image](./media/image-classification/220px-Pepperoni_pizza.jpg)
![teddy bear image](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![toaster image](./media/image-classification/193px-Broodrooster.jpg)</span></span>

>[!Note]
> <span data-ttu-id="3ef42-139">Las imágenes anteriores pertenecen a Wikimedia Commons y tienen los siguientes atributos:</span><span class="sxs-lookup"><span data-stu-id="3ef42-139">The preceding images belong to Wikimedia Commons and are attributed as follows:</span></span>
>
> * <span data-ttu-id="3ef42-140">"220px-Pepperoni_pizza.jpg" de dominio público, https://commons.wikimedia.org/w/index.php?curid=79505,</span><span class="sxs-lookup"><span data-stu-id="3ef42-140">"220px-Pepperoni_pizza.jpg" Public Domain, https://commons.wikimedia.org/w/index.php?curid=79505,</span></span>
> * <span data-ttu-id="3ef42-141">"119px-Nalle_-_a_small_brown_teddy_bear.jpg" de [Jonik](https://commons.wikimedia.org/wiki/User:Jonik), autofotografía, CC BY-SA 2.0, https://commons.wikimedia.org/w/index.php?curid=48166.</span><span class="sxs-lookup"><span data-stu-id="3ef42-141">"119px-Nalle_-_a_small_brown_teddy_bear.jpg" By [Jonik](https://commons.wikimedia.org/wiki/User:Jonik) - Self-photographed, CC BY-SA 2.0, https://commons.wikimedia.org/w/index.php?curid=48166.</span></span>
> * <span data-ttu-id="3ef42-142">"193px-Broodrooster.jpg" de [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972), trabajo propio, CC BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=27403</span><span class="sxs-lookup"><span data-stu-id="3ef42-142">"193px-Broodrooster.jpg" By [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972) - Own work, CC BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=27403</span></span>

<span data-ttu-id="3ef42-143">El aprendizaje por transferencia incluye algunas estrategias como *volver a entrenar todas las capas* y *penúltima capa*.</span><span class="sxs-lookup"><span data-stu-id="3ef42-143">Transfer learning includes a few strategies, such as *retrain all layers* and *penultimate layer*.</span></span> <span data-ttu-id="3ef42-144">En este tutorial se explicará y se mostrará cómo usar la *estrategia de penúltima capa*.</span><span class="sxs-lookup"><span data-stu-id="3ef42-144">This tutorial will explain and show how to use the *penultimate layer strategy*.</span></span> <span data-ttu-id="3ef42-145">La *estrategia de penúltima capa* vuelve a usar un modelo entrenado previamente para resolver un problema específico.</span><span class="sxs-lookup"><span data-stu-id="3ef42-145">The *penultimate layer strategy* reuses a model that's already been pre-trained to solve a specific problem.</span></span> <span data-ttu-id="3ef42-146">De ese modo, la estrategia vuelve a entrenar la capa final de ese modelo para que resuelva un problema nuevo.</span><span class="sxs-lookup"><span data-stu-id="3ef42-146">The strategy then retrains the final layer of that model to make it solve a new problem.</span></span> <span data-ttu-id="3ef42-147">Volver a usar el modelo entrenado previamente como parte del modelo nuevo permitirá ahorrar mucho tiempo y recursos.</span><span class="sxs-lookup"><span data-stu-id="3ef42-147">Reusing the pre-trained model as part of your new model will save significant time and resources.</span></span>

<span data-ttu-id="3ef42-148">El modelo de clasificación de imágenes vuelve a usar el [modelo de inicio](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip), un popular modelo de reconocimiento de imágenes entrenado en el conjunto de datos `ImageNet`, donde el modelo de TensorFlow intenta clasificar imágenes enteras en miles de clases, como "Umbrella" (Paraguas), "Jersey" (Suéter) y "Dishwasher" (Lavavajillas).</span><span class="sxs-lookup"><span data-stu-id="3ef42-148">Your image classification model reuses the [Inception model](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip), a popular image recognition model trained on the `ImageNet` dataset where the TensorFlow model tries to classify entire images into a thousand classes, like “Umbrella”, “Jersey”, and “Dishwasher”.</span></span>

<span data-ttu-id="3ef42-149">`Inception v3 model` se puede clasificar como una [red neuronal convolucional profunda](https://en.wikipedia.org/wiki/Convolutional_neural_network) y puede lograr un rendimiento razonable en tareas difíciles de reconocimiento visual, ya sea igualando o superando el rendimiento humano en algunos dominios.</span><span class="sxs-lookup"><span data-stu-id="3ef42-149">The `Inception v3 model` can be classified as a [deep convolutional neural network](https://en.wikipedia.org/wiki/Convolutional_neural_network) and can achieve reasonable performance on hard visual recognition tasks, matching or exceeding human performance in some domains.</span></span> <span data-ttu-id="3ef42-150">El modelo/algoritmo lo desarrollaron varios investigadores basándose en la publicación original: ["Rethinking the Inception Architecture for Computer Vision” (Replanteamiento de la arquitectura de inicio para Computer Vision) de Szegedy, et. al.](https://arxiv.org/abs/1512.00567)</span><span class="sxs-lookup"><span data-stu-id="3ef42-150">The model/algorithm was developed by multiple researchers and based on the original paper: ["Rethinking the Inception Architecture for Computer Vision” by Szegedy, et. al.](https://arxiv.org/abs/1512.00567)</span></span>

<span data-ttu-id="3ef42-151">Como `Inception model` se entrenó previamente en miles de imágenes distintas, contiene las [características de imagen](https://en.wikipedia.org/wiki/Feature_(computer_vision)) necesarias para la identificación de imágenes.</span><span class="sxs-lookup"><span data-stu-id="3ef42-151">Because the `Inception model` has already been pre trained on thousands of different images, it contains the [image features](https://en.wikipedia.org/wiki/Feature_(computer_vision)) needed for image identification.</span></span> <span data-ttu-id="3ef42-152">Las capas inferiores de las características de imagen reconocen características simples (como los bordes) y las capas superiores reconocen características más complejas (como las formas).</span><span class="sxs-lookup"><span data-stu-id="3ef42-152">The lower image feature layers recognize simple features (such as edges) and the higher layers recognize more complex features (such as shapes).</span></span> <span data-ttu-id="3ef42-153">La capa final se entrena con un conjunto de datos mucho más pequeño, porque se empieza con un modelo entrenado previamente que ya entiende cómo clasificar imágenes.</span><span class="sxs-lookup"><span data-stu-id="3ef42-153">The final layer is trained against a much smaller set of data because you're starting with a pre trained model that already understands how to classify images.</span></span> <span data-ttu-id="3ef42-154">Como el modelo permite clasificar más de dos categorías, se trata de un ejemplo de un [clasificador multiclase](../resources/tasks.md#multiclass-classification).</span><span class="sxs-lookup"><span data-stu-id="3ef42-154">As your model allows you to classify more than two categories, this is an example of a [multi-class classifier](../resources/tasks.md#multiclass-classification).</span></span> 

<span data-ttu-id="3ef42-155">`TensorFlow` es un popular kit de herramientas de aprendizaje profundo y aprendizaje automático que permite entrenar redes neuronales profundas (y cálculos numéricos generales) y se implementa como `transformer` en ML.NET.</span><span class="sxs-lookup"><span data-stu-id="3ef42-155">`TensorFlow` is a popular deep learning and machine learning toolkit that enables training deep neural networks (and general numeric computations), and is implemented as a `transformer` in ML.NET.</span></span> <span data-ttu-id="3ef42-156">En este tutorial, se usa para reutilizar `Inception model`.</span><span class="sxs-lookup"><span data-stu-id="3ef42-156">For this tutorial, it's used to reuse the `Inception model`.</span></span>

<span data-ttu-id="3ef42-157">Como se muestra en el diagrama siguiente, puede agregar una referencia a los paquetes NuGet de ML.NET en las aplicaciones de .NET Core o .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3ef42-157">As shown in the following diagram, you add a reference to the ML.NET NuGet packages in your .NET Core or .NET Framework applications.</span></span> <span data-ttu-id="3ef42-158">En segundo plano, ML.NET incluye y hace referencia a la biblioteca nativa de `TensorFlow` que permite escribir código que carga un archivo de modelo de `TensorFlow` entrenado existente para puntuación.</span><span class="sxs-lookup"><span data-stu-id="3ef42-158">Under the covers, ML.NET includes and references the native `TensorFlow` library that allows you to write code that loads an existing trained `TensorFlow` model file for scoring.</span></span>  

![Diagrama de la arquitectura de ML.NET de transformación de TensorFlow](./media/image-classification/tensorflow-mlnet.png)

<span data-ttu-id="3ef42-160">`Inception model` está entrenado para clasificar imágenes en miles de categorías, pero el usuario deberá clasificar las imágenes en un conjunto de categorías más pequeño y solo en esas categorías.</span><span class="sxs-lookup"><span data-stu-id="3ef42-160">The `Inception model` is trained to classify images into a thousand categories, but you need to classify images in a smaller category set, and only those categories.</span></span> <span data-ttu-id="3ef42-161">Escriba la parte `transfer` de `transfer learning`.</span><span class="sxs-lookup"><span data-stu-id="3ef42-161">Enter the `transfer` part of `transfer learning`.</span></span> <span data-ttu-id="3ef42-162">Puede transferir la capacidad que `Inception model` tiene para reconocer y clasificar imágenes a las nuevas categorías limitadas del clasificador personalizado de imágenes.</span><span class="sxs-lookup"><span data-stu-id="3ef42-162">You can transfer the `Inception model`'s ability to recognize and classify images to the new limited categories of your custom image classifier.</span></span>  

 <span data-ttu-id="3ef42-163">Va a volver a entrenar la capa final de ese modelo con un conjunto de tres categorías:</span><span class="sxs-lookup"><span data-stu-id="3ef42-163">You're going to retrain the final layer of that model using a set of three categories:</span></span>

* <span data-ttu-id="3ef42-164">Alimentos</span><span class="sxs-lookup"><span data-stu-id="3ef42-164">Food</span></span>
* <span data-ttu-id="3ef42-165">Juguetes</span><span class="sxs-lookup"><span data-stu-id="3ef42-165">Toy</span></span>
* <span data-ttu-id="3ef42-166">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="3ef42-166">Appliance</span></span>

<span data-ttu-id="3ef42-167">La capa usa un [algoritmo de regresión logística multinomial](https://en.wikipedia.org/wiki/Multinomial_logistic_regression) para encontrar la categoría correcta lo más rápido que sea posible.</span><span class="sxs-lookup"><span data-stu-id="3ef42-167">Your layer uses a [multinomial logistic regression algorithm](https://en.wikipedia.org/wiki/Multinomial_logistic_regression) to find the correct category as quickly as possible.</span></span> <span data-ttu-id="3ef42-168">Este algoritmo clasifica el uso de probabilidades para determinar la respuesta, dándole un valor a la categoría correcta y un valor de cero a las demás.</span><span class="sxs-lookup"><span data-stu-id="3ef42-168">This algorithm classifies using probabilities to determine the answer, giving a one value to the correct category and a zero value to the others.</span></span>  

### <a name="dataset"></a><span data-ttu-id="3ef42-169">DataSet</span><span class="sxs-lookup"><span data-stu-id="3ef42-169">DataSet</span></span>

<span data-ttu-id="3ef42-170">Hay dos orígenes de datos: el archivo `.tsv` y los archivos de imagen.</span><span class="sxs-lookup"><span data-stu-id="3ef42-170">There are two data sources: the `.tsv` file, and the image files.</span></span>  <span data-ttu-id="3ef42-171">El archivo `tags.tsv` contiene dos columnas: la primera está definida como `ImagePath` y la segunda es la `Label` que corresponde a la imagen.</span><span class="sxs-lookup"><span data-stu-id="3ef42-171">The `tags.tsv` file contains two columns: the first one is defined as `ImagePath` and the second one is the `Label` corresponding to the image.</span></span> <span data-ttu-id="3ef42-172">El archivo de ejemplo siguiente no tiene una fila de encabezado y se ve así:</span><span class="sxs-lookup"><span data-stu-id="3ef42-172">The following example file doesn't have a header row, and looks like this:</span></span>

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

<span data-ttu-id="3ef42-173">Las imágenes de entrenamiento y prueba se encuentran en las carpetas de recursos que descargará en un archivo ZIP.</span><span class="sxs-lookup"><span data-stu-id="3ef42-173">The training and testing images are located in the assets folders that you'll download in a zip file.</span></span> <span data-ttu-id="3ef42-174">Estas imágenes pertenecen a Wikimedia Commons.</span><span class="sxs-lookup"><span data-stu-id="3ef42-174">These images belong to Wikimedia Commons.</span></span>
> <span data-ttu-id="3ef42-175">*[Wikimedia Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), el repositorio multimedia gratuito*.</span><span class="sxs-lookup"><span data-stu-id="3ef42-175">*[Wikimedia Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), the free media repository.*</span></span> <span data-ttu-id="3ef42-176">Recuperado a las 10:48 del 17 de octubre de 2018 desde:</span><span class="sxs-lookup"><span data-stu-id="3ef42-176">Retrieved 10:48, October 17, 2018 from:</span></span>  
> https://commons.wikimedia.org/wiki/Pizza  
> https://commons.wikimedia.org/wiki/Toaster  
> https://commons.wikimedia.org/wiki/Teddy_bear  

## <a name="create-a-console-application"></a><span data-ttu-id="3ef42-177">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="3ef42-177">Create a console application</span></span>

### <a name="create-a-project"></a><span data-ttu-id="3ef42-178">Crear un proyecto</span><span class="sxs-lookup"><span data-stu-id="3ef42-178">Create a project</span></span>

1. <span data-ttu-id="3ef42-179">Cree una **aplicación de consola de .NET Core** denominada "TransferLearningTF".</span><span class="sxs-lookup"><span data-stu-id="3ef42-179">Create a **.NET Core Console Application** called "TransferLearningTF".</span></span>

2. <span data-ttu-id="3ef42-180">Instale el **paquete NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="3ef42-180">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="3ef42-181">En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="3ef42-181">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="3ef42-182">Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar y busque **Microsoft.ML**.</span><span class="sxs-lookup"><span data-stu-id="3ef42-182">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**.</span></span> <span data-ttu-id="3ef42-183">Haga clic en el menú desplegable **Versión**, seleccione el paquete **1.0.0** en la lista y, luego, el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="3ef42-183">Click on the **Version** drop-down, select the **1.0.0** package in the list, and select the **Install** button.</span></span> <span data-ttu-id="3ef42-184">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="3ef42-184">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span> <span data-ttu-id="3ef42-185">Repita estos pasos para **Microsoft.ML.ImageAnalytics v1.0.0** y **Microsoft.ML.TensorFlow v0.12.0**.</span><span class="sxs-lookup"><span data-stu-id="3ef42-185">Repeat these steps for **Microsoft.ML.ImageAnalytics v1.0.0** and **Microsoft.ML.TensorFlow v0.12.0**.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="3ef42-186">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="3ef42-186">Prepare your data</span></span>

1. <span data-ttu-id="3ef42-187">Descargue el [archivo ZIP del directorio de recursos del proyecto](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip) y descomprímalo.</span><span class="sxs-lookup"><span data-stu-id="3ef42-187">Download [The project assets directory zip file](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip), and unzip.</span></span>

2. <span data-ttu-id="3ef42-188">Copie el directorio `assets` en el directorio de proyecto *TransferLearningTF*.</span><span class="sxs-lookup"><span data-stu-id="3ef42-188">Copy the `assets` directory into your *TransferLearningTF* project directory.</span></span> <span data-ttu-id="3ef42-189">Este directorio y sus subdirectorios contienen los datos y los archivos auxiliares (excepto los del modelo de inicio, que descargará y agregará en el paso siguiente) que se necesitan en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="3ef42-189">This directory and its subdirectories contain the data and support files (except for the Inception model, which you'll download and add in the next step) needed for this tutorial.</span></span>

3. <span data-ttu-id="3ef42-190">Descargue el [modelo de inicio](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) y descomprímalo.</span><span class="sxs-lookup"><span data-stu-id="3ef42-190">Download the [Inception model](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip), and unzip.</span></span>

4. <span data-ttu-id="3ef42-191">Copie el contenido del directorio `inception5h` que acaba de descomprimir en el directorio `assets\inputs-train\inception` del proyecto *TransferLearningTF*.</span><span class="sxs-lookup"><span data-stu-id="3ef42-191">Copy the contents of the `inception5h` directory just unzipped into your *TransferLearningTF* project `assets\inputs-train\inception` directory.</span></span> <span data-ttu-id="3ef42-192">En este directorio está el modelo y los archivos auxiliares adicionales que se necesitan en este tutorial, tal como se muestra en la imagen siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ef42-192">This directory contains the model and additional support files needed for this tutorial, as shown in the following image:</span></span>

   ![Contenido del directorio de inicio](./media/image-classification/inception-files.png)

5. <span data-ttu-id="3ef42-194">En el Explorador de soluciones, haga clic con el botón derecho en cada uno de los archivos del directorio de recursos y los subdirectorios y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3ef42-194">In Solution Explorer, right-click each of the files in the asset directory and subdirectories and select **Properties**.</span></span> <span data-ttu-id="3ef42-195">En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.</span><span class="sxs-lookup"><span data-stu-id="3ef42-195">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="3ef42-196">Crear clases y definir rutas de acceso</span><span class="sxs-lookup"><span data-stu-id="3ef42-196">Create classes and define paths</span></span>

<span data-ttu-id="3ef42-197">Agregue las siguientes instrucciones `using` adicionales a la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="3ef42-197">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddUsings)]

<span data-ttu-id="3ef42-198">Cree campos globales para contener las rutas de acceso a los distintos recursos y variables globales para `LabelTokey`,`ImageReal` y `PredictedLabelValue`:</span><span class="sxs-lookup"><span data-stu-id="3ef42-198">Create global fields to hold the paths to the various assets, and global variables for the `LabelTokey`,`ImageReal`, and  `PredictedLabelValue`:</span></span>

* <span data-ttu-id="3ef42-199">`_assetsPath` tiene la ruta de acceso a los recursos.</span><span class="sxs-lookup"><span data-stu-id="3ef42-199">`_assetsPath` has the path to the assets.</span></span>
* <span data-ttu-id="3ef42-200">`_trainTagsTsv` tiene la ruta de acceso al archivo tsv de etiquetas de datos de imagen de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="3ef42-200">`_trainTagsTsv` has the path to the training image data tags tsv file.</span></span>
* <span data-ttu-id="3ef42-201">`_predictTagsTsv` tiene la ruta de acceso al archivo tsv de etiquetas de datos de imagen de predicción.</span><span class="sxs-lookup"><span data-stu-id="3ef42-201">`_predictTagsTsv` has the path to the prediction image data tags tsv file.</span></span>
* <span data-ttu-id="3ef42-202">`_trainImagesFolder` tiene la ruta de acceso a las imágenes que se usan para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="3ef42-202">`_trainImagesFolder` has the path to the images used to train the model.</span></span>
* <span data-ttu-id="3ef42-203">`_predictImagesFolder` tiene la ruta de acceso a las imágenes que el modelo entrenado va a clasificar.</span><span class="sxs-lookup"><span data-stu-id="3ef42-203">`_predictImagesFolder` has the path to the images to be classified by the trained model.</span></span>
* <span data-ttu-id="3ef42-204">`_inceptionPb` tiene la ruta de acceso al modelo de inicio entrenado previamente que se reutilizará para volver a entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="3ef42-204">`_inceptionPb` has the path to the pre-trained Inception model to be reused to retrain your model.</span></span>
* <span data-ttu-id="3ef42-205">`_inputImageClassifierZip` tiene la ruta de acceso desde donde se carga el modelo de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="3ef42-205">`_inputImageClassifierZip` has the path where the trained model is loaded from.</span></span>
* <span data-ttu-id="3ef42-206">`_outputImageClassifierZip` tiene la ruta de acceso donde se guarda el modelo entrenado.</span><span class="sxs-lookup"><span data-stu-id="3ef42-206">`_outputImageClassifierZip` has the path where the trained model is saved.</span></span>
* <span data-ttu-id="3ef42-207">`LabelTokey` es el valor `Label` asignado a una clave.</span><span class="sxs-lookup"><span data-stu-id="3ef42-207">`LabelTokey` is the `Label` value mapped to a key.</span></span>
* <span data-ttu-id="3ef42-208">`ImageReal` es la columna que contiene el valor de imagen previsto.</span><span class="sxs-lookup"><span data-stu-id="3ef42-208">`ImageReal`  is the column containing the predicted image value.</span></span>
* <span data-ttu-id="3ef42-209">`PredictedLabelValue` es la columna que contiene el valor de etiqueta previsto.</span><span class="sxs-lookup"><span data-stu-id="3ef42-209">`PredictedLabelValue` is the column containing the predicted label value.</span></span>

<span data-ttu-id="3ef42-210">Agregue el código siguiente a la línea justo encima del método `Main` para especificar esas rutas de acceso y otras variables:</span><span class="sxs-lookup"><span data-stu-id="3ef42-210">Add the following code to the line right above the `Main` method to specify those paths and the other variables:</span></span>

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DeclareGlobalVariables)]

<span data-ttu-id="3ef42-211">Cree algunas clases para los datos de entrada y predicciones.</span><span class="sxs-lookup"><span data-stu-id="3ef42-211">Create some classes for your input data, and predictions.</span></span> <span data-ttu-id="3ef42-212">Agregue una nueva clase a su proyecto:</span><span class="sxs-lookup"><span data-stu-id="3ef42-212">Add a new class to your project:</span></span>

1. <span data-ttu-id="3ef42-213">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="3ef42-213">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="3ef42-214">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *ImageData.cs*.</span><span class="sxs-lookup"><span data-stu-id="3ef42-214">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *ImageData.cs*.</span></span> <span data-ttu-id="3ef42-215">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="3ef42-215">Then, select the **Add** button.</span></span>

    <span data-ttu-id="3ef42-216">El archivo *ImageData.cs* se abre en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="3ef42-216">The *ImageData.cs* file opens in the code editor.</span></span> <span data-ttu-id="3ef42-217">Agregue la instrucción `using` siguiente al principio del archivo *ImageData.cs*:</span><span class="sxs-lookup"><span data-stu-id="3ef42-217">Add the following `using` statement to the top of *ImageData.cs*:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TransferLearningTF/ImageData.cs#AddUsings)]

<span data-ttu-id="3ef42-218">Quite la definición de clase existente y agregue el código siguiente para la clase `ImageData` al archivo *ImageData.cs*:</span><span class="sxs-lookup"><span data-stu-id="3ef42-218">Remove the existing class definition and add the following code for the `ImageData` class to the *ImageData.cs* file:</span></span>

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/TransferLearningTF/ImageData.cs#DeclareTypes)]

<span data-ttu-id="3ef42-219">`ImageData` es la clase de datos de imagen de entrada y tiene los campos <xref:System.String> siguientes:</span><span class="sxs-lookup"><span data-stu-id="3ef42-219">`ImageData` is the input image data class and has the following <xref:System.String> fields:</span></span>

* <span data-ttu-id="3ef42-220">`ImagePath` contiene el nombre del archivo de imagen.</span><span class="sxs-lookup"><span data-stu-id="3ef42-220">`ImagePath` contains the image file name.</span></span>
* <span data-ttu-id="3ef42-221">`Label` contiene un valor para la etiqueta de imagen.</span><span class="sxs-lookup"><span data-stu-id="3ef42-221">`Label` contains a value for the image label.</span></span>

<span data-ttu-id="3ef42-222">Agregue una clase nueva al proyecto para `ImagePrediction`:</span><span class="sxs-lookup"><span data-stu-id="3ef42-222">Add a new class to your project for `ImagePrediction`:</span></span>

1. <span data-ttu-id="3ef42-223">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="3ef42-223">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="3ef42-224">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *ImagePrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="3ef42-224">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *ImagePrediction.cs*.</span></span> <span data-ttu-id="3ef42-225">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="3ef42-225">Then, select the **Add** button.</span></span>

    <span data-ttu-id="3ef42-226">El archivo *ImagePrediction.cs* se abre en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="3ef42-226">The *ImagePrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="3ef42-227">Quite las instrucciones `using` de `System.Collections.Generic` y de `System.Text` del inicio del archivo *ImagePrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="3ef42-227">Remove both the `System.Collections.Generic` and the `System.Text` `using` statements at the top of *ImagePrediction.cs*:</span></span>

<span data-ttu-id="3ef42-228">Quite la definición de clase existente y agregue el código siguiente, que tiene la clase `ImagePrediction`, al archivo *ImagePrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="3ef42-228">Remove the existing class definition and add the following code, which has the `ImagePrediction` class, to the *ImagePrediction.cs* file:</span></span>

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TransferLearningTF/ImagePrediction.cs#DeclareTypes)]

<span data-ttu-id="3ef42-229">`ImagePrediction` es la clase de predicción de imagen y tiene los campos siguientes:</span><span class="sxs-lookup"><span data-stu-id="3ef42-229">`ImagePrediction` is the image prediction class and has the following fields:</span></span>

* <span data-ttu-id="3ef42-230">`Score` contiene el porcentaje de confianza de una clasificación de imágenes determinada.</span><span class="sxs-lookup"><span data-stu-id="3ef42-230">`Score` contains the confidence percentage for a given image classification.</span></span>
* <span data-ttu-id="3ef42-231">`PredictedLabelValue` contiene un valor para la etiqueta de clasificación de imágenes prevista.</span><span class="sxs-lookup"><span data-stu-id="3ef42-231">`PredictedLabelValue` contains a value for the predicted image classification label.</span></span>

<span data-ttu-id="3ef42-232">`ImagePrediction` es la clase usada para la predicción una vez entrenado el modelo.</span><span class="sxs-lookup"><span data-stu-id="3ef42-232">`ImagePrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="3ef42-233">Tiene una `string` (`ImagePath`) para la ruta de acceso a la imagen.</span><span class="sxs-lookup"><span data-stu-id="3ef42-233">It has a `string` (`ImagePath`) for the image path.</span></span> <span data-ttu-id="3ef42-234">`Label` se usa para reutilizar y volver a entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="3ef42-234">The `Label` is used to reuse and retrain the model.</span></span> <span data-ttu-id="3ef42-235">`PredictedLabelValue` se usa durante la predicción y la evaluación.</span><span class="sxs-lookup"><span data-stu-id="3ef42-235">The `PredictedLabelValue` is used during prediction and evaluation.</span></span> <span data-ttu-id="3ef42-236">Para la evaluación, se utiliza una entrada con los datos de entrenamiento, los valores de predicción y el modelo.</span><span class="sxs-lookup"><span data-stu-id="3ef42-236">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="3ef42-237">La [clase MLContext](xref:Microsoft.ML.MLContext) es un punto de partida para todas las operaciones de ML.NET. Al inicializar `mlContext`, se crea un entorno de ML.NET que se puede compartir entre los objetos del flujo de trabajo de creación de modelos.</span><span class="sxs-lookup"><span data-stu-id="3ef42-237">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="3ef42-238">Como concepto, se parece a `DBContext` en Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="3ef42-238">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="3ef42-239">Inicializar variables en Main</span><span class="sxs-lookup"><span data-stu-id="3ef42-239">Initialize variables in Main</span></span>

<span data-ttu-id="3ef42-240">Inicialice la variable `mlContext` con una instancia nueva de `MLContext`.</span><span class="sxs-lookup"><span data-stu-id="3ef42-240">Initialize the `mlContext` variable with a new instance of `MLContext`.</span></span>  <span data-ttu-id="3ef42-241">Reemplace la línea `Console.WriteLine("Hello World!")` por el código siguiente en el método `Main`:</span><span class="sxs-lookup"><span data-stu-id="3ef42-241">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CreateMLContext)]

### <a name="create-a-struct-for-default-parameters"></a><span data-ttu-id="3ef42-242">Crear una estructura para parámetros predeterminados</span><span class="sxs-lookup"><span data-stu-id="3ef42-242">Create a struct for default parameters</span></span>

<span data-ttu-id="3ef42-243">El modelo de inicio tiene varios parámetros predeterminados que se deben transmitir.</span><span class="sxs-lookup"><span data-stu-id="3ef42-243">The Inception model has several default parameters you need to pass in.</span></span> <span data-ttu-id="3ef42-244">Cree una estructura para asignar los valores de parámetros predeterminados a nombres descriptivos con el código siguiente, justo después del método `Main()`:</span><span class="sxs-lookup"><span data-stu-id="3ef42-244">Create a struct to map the default parameter values to friendly names with the following code, just after the `Main()` method:</span></span>

[!code-csharp[InceptionSettings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#InceptionSettings)]

### <a name="create-a-display-utility-method"></a><span data-ttu-id="3ef42-245">Crear un método de utilidad para mostrar</span><span class="sxs-lookup"><span data-stu-id="3ef42-245">Create a display utility method</span></span>

<span data-ttu-id="3ef42-246">Dado que se mostrarán los datos de imagen y las predicciones relacionadas más de una vez, cree un método de utilidad para mostrar a fin de controlar la visualización de los resultados de la imagen y la predicción.</span><span class="sxs-lookup"><span data-stu-id="3ef42-246">Since you'll display the image data and the related predictions more than once, create a display utility method to handle displaying the image and prediction results.</span></span>

<span data-ttu-id="3ef42-247">El método `DisplayResults()` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="3ef42-247">The `DisplayResults()` method executes the following tasks:</span></span>

* <span data-ttu-id="3ef42-248">Muestra los resultados de la predicción.</span><span class="sxs-lookup"><span data-stu-id="3ef42-248">Displays the predicted results.</span></span>

<span data-ttu-id="3ef42-249">Cree el método `DisplayResults()` justo después de la estructura `InceptionSettings` con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ef42-249">Create the `DisplayResults()` method, just after the `InceptionSettings` struct, using the following code:</span></span>

```csharp
private static void DisplayResults(IEnumerable<ImagePrediction> imagePredictionData)
{

}
```

<span data-ttu-id="3ef42-250">El método `Transform()` rellenó `ImagePath` en `ImagePrediction`, junto con los campos de predicción.</span><span class="sxs-lookup"><span data-stu-id="3ef42-250">The `Transform()` method populated `ImagePath` in `ImagePrediction` along with the predicted fields.</span></span> <span data-ttu-id="3ef42-251">A medida que el proceso ML.NET se ejecuta, cada componente agrega columnas, y esto facilita la presentación de los resultados:</span><span class="sxs-lookup"><span data-stu-id="3ef42-251">As the ML.NET process progresses, each component adds columns, and this makes it easy to display the results:</span></span>

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPredictions)]

<span data-ttu-id="3ef42-252">Llamará al método `DisplayResults()` en los dos métodos de clasificación de imágenes.</span><span class="sxs-lookup"><span data-stu-id="3ef42-252">You'll call the `DisplayResults()` method in the two image classification methods.</span></span>

### <a name="create-a-tsv-file-utility-method"></a><span data-ttu-id="3ef42-253">Crear un método de utilidad de archivo .tsv</span><span class="sxs-lookup"><span data-stu-id="3ef42-253">Create a .tsv file utility method</span></span>

<span data-ttu-id="3ef42-254">El método `ReadFromTsv()` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="3ef42-254">The `ReadFromTsv()` method executes the following tasks:</span></span>

* <span data-ttu-id="3ef42-255">Lee el archivo `tags.tsv` de datos de imagen.</span><span class="sxs-lookup"><span data-stu-id="3ef42-255">Reads the image data `tags.tsv` file.</span></span>
* <span data-ttu-id="3ef42-256">Agrega la ruta de acceso al archivo al nombre del archivo de imagen.</span><span class="sxs-lookup"><span data-stu-id="3ef42-256">Adds the file path to the image file name.</span></span>
* <span data-ttu-id="3ef42-257">Carga los datos de archivo en un objeto IEnumerable`ImageData`.</span><span class="sxs-lookup"><span data-stu-id="3ef42-257">Loads the file data into an IEnumerable`ImageData` object.</span></span>

<span data-ttu-id="3ef42-258">Cree el método `ReadFromTsv()`, justo después del método `PairAndDisplayResults()`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ef42-258">Create the `ReadFromTsv()` method, just after the `PairAndDisplayResults()` method, using the following code:</span></span>

```csharp
public static IEnumerable<ImageData> ReadFromTsv(string file, string folder)
{

}
```

<span data-ttu-id="3ef42-259">El código siguiente analiza el archivo `tags.tsv` para agregar la ruta de acceso al archivo al nombre del archivo de imagen de la propiedad `ImagePath` y lo carga junto con `Label` en un objeto `ImageData`.</span><span class="sxs-lookup"><span data-stu-id="3ef42-259">The following code parses through the `tags.tsv` file to add the file path to the image file name for the `ImagePath` property and load it and the `Label` into an `ImageData` object.</span></span> <span data-ttu-id="3ef42-260">Agréguelo como la primera línea del método `ReadFromTsv()`.</span><span class="sxs-lookup"><span data-stu-id="3ef42-260">Add it as the first line of the `ReadFromTsv()` method.</span></span>  <span data-ttu-id="3ef42-261">Necesita la ruta de acceso al archivo completo para mostrar los resultados de la predicción.</span><span class="sxs-lookup"><span data-stu-id="3ef42-261">You need the fully qualified file path to display the prediction results.</span></span>

[!code-csharp[ReadFromTsv](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReadFromTsv)]
<span data-ttu-id="3ef42-262">En ML.NET hay tres conceptos principales: [Data](../resources/glossary.md#data) (datos), [Transformers](../resources/glossary.md#transformer) (transformadores) y [Estimators](../resources/glossary.md#estimator) (estimadores).</span><span class="sxs-lookup"><span data-stu-id="3ef42-262">There are three major concepts in ML.NET: [Data](../resources/glossary.md#data), [Transformers](../resources/glossary.md#transformer), and [Estimators](../resources/glossary.md#estimator).</span></span>

## <a name="reuse-and-tune-pre-trained-model"></a><span data-ttu-id="3ef42-263">Volver a usar y ajustar el modelo entrenado previamente</span><span class="sxs-lookup"><span data-stu-id="3ef42-263">Reuse and tune pre-trained model</span></span>

<span data-ttu-id="3ef42-264">Agregue la siguiente llamada al método `ReuseAndTuneInceptionModel()` como siguiente línea de código del método `Main()`:</span><span class="sxs-lookup"><span data-stu-id="3ef42-264">Add the following call to the `ReuseAndTuneInceptionModel()`method as the next line of code in the `Main()` method:</span></span>

[!code-csharp[CallReuseAndTuneInceptionModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallReuseAndTuneInceptionModel)]

<span data-ttu-id="3ef42-265">El método `ReuseAndTuneInceptionModel()` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="3ef42-265">The `ReuseAndTuneInceptionModel()` method executes the following tasks:</span></span>

* <span data-ttu-id="3ef42-266">Carga los datos.</span><span class="sxs-lookup"><span data-stu-id="3ef42-266">Loads the data</span></span>
* <span data-ttu-id="3ef42-267">Extrae y transforma los datos.</span><span class="sxs-lookup"><span data-stu-id="3ef42-267">Extracts and transforms the data.</span></span>
* <span data-ttu-id="3ef42-268">Asigna una puntuación al modelo de TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="3ef42-268">Scores the TensorFlow model.</span></span>
* <span data-ttu-id="3ef42-269">Ajusta (vuelve a entrenar) el modelo.</span><span class="sxs-lookup"><span data-stu-id="3ef42-269">Tunes (retrains) the model.</span></span>
* <span data-ttu-id="3ef42-270">Muestra los resultados del modelo.</span><span class="sxs-lookup"><span data-stu-id="3ef42-270">Displays model results.</span></span>
* <span data-ttu-id="3ef42-271">Evalúa el modelo.</span><span class="sxs-lookup"><span data-stu-id="3ef42-271">Evaluates the model.</span></span>
* <span data-ttu-id="3ef42-272">Devuelve el modelo.</span><span class="sxs-lookup"><span data-stu-id="3ef42-272">Returns the model.</span></span>

<span data-ttu-id="3ef42-273">Cree el método `ReuseAndTuneInceptionModel()` justo después de la estructura `InceptionSettings` y antes del método `DisplayResults()` con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ef42-273">Create the `ReuseAndTuneInceptionModel()` method, just after the `InceptionSettings` struct and just before the `DisplayResults()` method, using the following code:</span></span>

```csharp
public static ITransformer ReuseAndTuneInceptionModel(MLContext mlContext, string dataLocation, string imagesFolder, string inputModelLocation, string outputModelLocation)
{

}
```

### <a name="load-the-data"></a><span data-ttu-id="3ef42-274">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="3ef42-274">Load the data</span></span>

<span data-ttu-id="3ef42-275">Los datos de ML.NET se representan como una [clase IDataView](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="3ef42-275">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="3ef42-276">`IDataView` es una manera flexible y eficiente de describir datos tabulares (numéricos y de texto).</span><span class="sxs-lookup"><span data-stu-id="3ef42-276">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="3ef42-277">Los datos se pueden cargar desde un archivo de texto o en tiempo real (por ejemplo, archivos de registro o base de datos SQL) en un objeto `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="3ef42-277">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

<span data-ttu-id="3ef42-278">Cargue los datos con el contenedor `MLContext.Data.LoadFromTextFile`.</span><span class="sxs-lookup"><span data-stu-id="3ef42-278">Load the data using the `MLContext.Data.LoadFromTextFile` wrapper.</span></span> <span data-ttu-id="3ef42-279">Agregue el siguiente código como la siguiente línea en el método `ReuseAndTuneInceptionModel()`:</span><span class="sxs-lookup"><span data-stu-id="3ef42-279">Add the following code as the next line in the `ReuseAndTuneInceptionModel()` method:</span></span>

[!code-csharp[LoadData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadData "Load the data")]

### <a name="extract-features-and-transform-the-data"></a><span data-ttu-id="3ef42-280">Extraer características y transformar los datos</span><span class="sxs-lookup"><span data-stu-id="3ef42-280">Extract Features and transform the data</span></span>

<span data-ttu-id="3ef42-281">El procesamiento previo y la limpieza de datos son tareas importantes que se producen antes de que un conjunto de datos se utilice de forma eficaz para el aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="3ef42-281">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span>  <span data-ttu-id="3ef42-282">El uso de datos sin estas tareas de modelado puede producir resultados engañosos.</span><span class="sxs-lookup"><span data-stu-id="3ef42-282">Using data without these modeling tasks can produce misleading results.</span></span>

<span data-ttu-id="3ef42-283">Los algoritmos de aprendizaje automático entienden los datos [caracterizados](../resources/glossary.md#feature) y, cuando trabaje con redes neuronales profundas, deberá adaptar las imágenes al formato que espera la red.</span><span class="sxs-lookup"><span data-stu-id="3ef42-283">Machine learning algorithms understand [featurized](../resources/glossary.md#feature) data, and when dealing with deep neural networks you must adapt the images to the format expected by the network.</span></span> <span data-ttu-id="3ef42-284">Ese formato es un [vector numérico](../resources/glossary.md#numerical-feature-vector).</span><span class="sxs-lookup"><span data-stu-id="3ef42-284">That format is a [numeric vector](../resources/glossary.md#numerical-feature-vector).</span></span>

<span data-ttu-id="3ef42-285">Después del entrenamiento y la evaluación, prediga con los valores de la columna **Etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="3ef42-285">After training and evaluation, predict with the **Label** column values.</span></span> <span data-ttu-id="3ef42-286">A medida que usa un modelo entrenado previamente, asigne los campos al nuevo modelo con el método [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A).</span><span class="sxs-lookup"><span data-stu-id="3ef42-286">As you're using a pre-trained model, map fields to the new model with the [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) method.</span></span> <span data-ttu-id="3ef42-287">Este método transforma `Label` en una columna de tipo de clave numérica (`LabelTokey`) y la agrega como una columna de conjunto de datos nueva:  Asígnele el nombre `estimator`, porque también le agregará el instructor.</span><span class="sxs-lookup"><span data-stu-id="3ef42-287">This method transforms the `Label` into a numeric key type (`LabelTokey`) column and add it as new dataset column:  Name this `estimator` as you'll also add the trainer to it.</span></span> <span data-ttu-id="3ef42-288">Agregue esta línea de código:</span><span class="sxs-lookup"><span data-stu-id="3ef42-288">Add the next line of code:</span></span>

[!code-csharp[MapValueToKey1](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapValueToKey1)]

<span data-ttu-id="3ef42-289">El estimador de procesamiento de imágenes usa los caracterizadores de [red neuronal profunda (DNN)](https://en.wikipedia.org/wiki/Deep_learning#Deep_neural_networks) entrenados previamente para extraer las características.</span><span class="sxs-lookup"><span data-stu-id="3ef42-289">Your image processing estimator uses pre-trained [Deep Neural Network(DNN)](https://en.wikipedia.org/wiki/Deep_learning#Deep_neural_networks) featurizers for feature extraction.</span></span> <span data-ttu-id="3ef42-290">Cuando trabaje con redes neuronales profundas, puede adaptar las imágenes al formato de red esperado.</span><span class="sxs-lookup"><span data-stu-id="3ef42-290">When dealing with deep neural networks, you  adapt the images to the expected network format.</span></span> <span data-ttu-id="3ef42-291">Este es el motivo por el que usa varias transformaciones de imágenes a fin de colocar los datos de imagen en el formato esperado del modelo:</span><span class="sxs-lookup"><span data-stu-id="3ef42-291">This is the reason you use several image transforms to get the image data into the model's expected form:</span></span>

1. <span data-ttu-id="3ef42-292">Las imágenes de la transformación `LoadImages` se cargan en memoria como un tipo de mapa de bits.</span><span class="sxs-lookup"><span data-stu-id="3ef42-292">The `LoadImages`transform images are loaded in memory as a Bitmap type.</span></span>
2. <span data-ttu-id="3ef42-293">La transformación `ResizeImages` cambia el tamaño de las imágenes porque el modelo entrenado previamente tiene definido el alto y el ancho de las imágenes de entrada.</span><span class="sxs-lookup"><span data-stu-id="3ef42-293">The `ResizeImages` transform resizes the images as the pre-trained model has a defined input image width and height.</span></span>
3. <span data-ttu-id="3ef42-294">La transformación `ExtractPixels` extrae los píxeles de las imágenes de entrada y las convierte en un vector numérico.</span><span class="sxs-lookup"><span data-stu-id="3ef42-294">The `ExtractPixels` transform extracts the pixels from the input images and converts them into a numeric vector.</span></span>

<span data-ttu-id="3ef42-295">Agregue estas transformaciones de imágenes como las líneas de código siguientes:</span><span class="sxs-lookup"><span data-stu-id="3ef42-295">Add these image transforms as the next lines of code:</span></span>

[!code-csharp[ImageTransforms](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ImageTransforms)]

<span data-ttu-id="3ef42-296">`LoadTensorFlowModel` es un método de conveniencia que permite que el modelo `TensorFlow` se cargue una vez y, a continuación, crea el método `TensorFlowEstimator` mediante `ScoreTensorFlowModel`.</span><span class="sxs-lookup"><span data-stu-id="3ef42-296">The `LoadTensorFlowModel` is a convenience method that allows the `TensorFlow` model to be loaded once and then creates the `TensorFlowEstimator` using `ScoreTensorFlowModel`.</span></span> <span data-ttu-id="3ef42-297">`ScoreTensorFlowModel` extrae salidas especificadas (la `softmax2_pre_activation` de las características de imagen de `Inception model`) y asigna una puntuación al conjunto de datos con el modelo `TensorFlow` entrenado previamente.</span><span class="sxs-lookup"><span data-stu-id="3ef42-297">The `ScoreTensorFlowModel` extracts specified outputs (the `Inception model`'s image features `softmax2_pre_activation`), and scores a dataset using the pre-trained `TensorFlow` model.</span></span>

<span data-ttu-id="3ef42-298">`softmax2_pre_activation` ayuda al modelo al determinar a qué clase pertenecen las imágenes.</span><span class="sxs-lookup"><span data-stu-id="3ef42-298">`softmax2_pre_activation` assists the model with determining which class the images belongs to.</span></span> <span data-ttu-id="3ef42-299">`softmax2_pre_activation` devuelve una probabilidad para cada una de las categorías de una imagen y la suma de todas esas probabilidades debe ser 1.</span><span class="sxs-lookup"><span data-stu-id="3ef42-299">`softmax2_pre_activation` returns a probability for each of the categories for an image, and all of those probabilities must add up to 1.</span></span> <span data-ttu-id="3ef42-300">Se supone que una imagen pertenecerá solo a una categoría, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ef42-300">It assumes that an image will belong to only one category, as shown in the following example:</span></span>

| <span data-ttu-id="3ef42-301">Clase</span><span class="sxs-lookup"><span data-stu-id="3ef42-301">Class</span></span>         | <span data-ttu-id="3ef42-302">Probabilidad</span><span class="sxs-lookup"><span data-stu-id="3ef42-302">Probability</span></span>   |
| ------------- | ------------- |
| `Food`        |  <span data-ttu-id="3ef42-303">0,001</span><span class="sxs-lookup"><span data-stu-id="3ef42-303">0.001</span></span>        |
| `Toy`         |  <span data-ttu-id="3ef42-304">0,95</span><span class="sxs-lookup"><span data-stu-id="3ef42-304">0.95</span></span>         |
| `Appliance`   |  <span data-ttu-id="3ef42-305">0,06</span><span class="sxs-lookup"><span data-stu-id="3ef42-305">0.06</span></span>         |

<span data-ttu-id="3ef42-306">Anexe `TensorFlowTransform` al `estimator` con la línea de código siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ef42-306">Append the `TensorFlowTransform` to the `estimator` with the following line of code:</span></span>

[!code-csharp[ScoreTensorFlowModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ScoreTensorFlowModel)]

### <a name="choose-a-training-algorithm"></a><span data-ttu-id="3ef42-307">Elija un algoritmo de entrenamiento</span><span class="sxs-lookup"><span data-stu-id="3ef42-307">Choose a training algorithm</span></span>

<span data-ttu-id="3ef42-308">Para agregar el algoritmo de entrenamiento, llame al método contenedor `mlContext.MulticlassClassification.Trainers.LbfgsMaximumEntropy()`.</span><span class="sxs-lookup"><span data-stu-id="3ef42-308">To add the training algorithm, call the `mlContext.MulticlassClassification.Trainers.LbfgsMaximumEntropy()` wrapper method.</span></span>  <span data-ttu-id="3ef42-309">[LbfgsMaximumEntropy](xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer) se anexa a `estimator` y acepta las características de imagen de inicio (`softmax2_pre_activation`) y los parámetros de entrada `Label` para aprender de los datos históricos.</span><span class="sxs-lookup"><span data-stu-id="3ef42-309">The [LbfgsMaximumEntropy](xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer) is appended to the `estimator` and accepts the Inception image features (`softmax2_pre_activation`) and the `Label` input parameters to learn from the historic data.</span></span>  <span data-ttu-id="3ef42-310">Agregue el instructor con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ef42-310">Add the trainer with the following code:</span></span>

[!code-csharp[AddTrainer](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddTrainer)]

<span data-ttu-id="3ef42-311">También deberá asignar `predictedlabel` al `predictedlabelvalue`:</span><span class="sxs-lookup"><span data-stu-id="3ef42-311">You also need to map the `predictedlabel` to the `predictedlabelvalue`:</span></span>

[!code-csharp[MapValueToKey2](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapValueToKey2)]

<span data-ttu-id="3ef42-312">El método `Fit()` entrena el modelo transformando el conjunto de datos y aplicando el entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="3ef42-312">The `Fit()` method trains your model by transforming the dataset and applying the training.</span></span> <span data-ttu-id="3ef42-313">Ajuste el modelo al conjunto de datos de entrenamiento y devuelva el modelo entrenado. Para ello, agregue lo que se indica a continuación como la siguiente línea de código en el método `ReuseAndTuneInceptionModel()`:</span><span class="sxs-lookup"><span data-stu-id="3ef42-313">Fit the model to the training dataset and return the trained model by adding the following as the next line of code in the `ReuseAndTuneInceptionModel()` method:</span></span>

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#TrainModel)]

<span data-ttu-id="3ef42-314">El método [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) realiza predicciones para varias filas de entrada proporcionadas de un conjunto de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="3ef42-314">The [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method makes predictions for multiple provided input rows of a test dataset.</span></span>  <span data-ttu-id="3ef42-315">Transforme los datos `Training` mediante la adición del código siguiente a `ReuseAndTuneInceptionModel()`:</span><span class="sxs-lookup"><span data-stu-id="3ef42-315">Transform the `Training` data by adding the following code to `ReuseAndTuneInceptionModel()`:</span></span>

[!code-csharp[TransformData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#TransformData)]

<span data-ttu-id="3ef42-316">Convierta las `DataViews` de predicción y los datos de imagen en `IEnumerables` fuertemente tipados para emparejar y facilitar la visualización.</span><span class="sxs-lookup"><span data-stu-id="3ef42-316">Convert your image data and prediction `DataViews` into strongly-typed `IEnumerables` to pair for easier display.</span></span> <span data-ttu-id="3ef42-317">Para ello, use el método `MLContext.CreateEnumerable()` y el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ef42-317">Use the `MLContext.CreateEnumerable()` method to do that, using the following code:</span></span>

[!code-csharp[EnumerateDataViews](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#EnumerateDataViews)]

<span data-ttu-id="3ef42-318">Llame al método `DisplayResults()` para mostrar los datos y las predicciones como la línea siguiente del método `ReuseAndTuneInceptionModel()`:</span><span class="sxs-lookup"><span data-stu-id="3ef42-318">Call the `DisplayResults()` method to display your data and predictions as the next line in the `ReuseAndTuneInceptionModel()` method:</span></span>

[!code-csharp[CallDisplayResults1](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallDisplayResults1)]

<span data-ttu-id="3ef42-319">Una vez que establece la predicción, el método [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A):</span><span class="sxs-lookup"><span data-stu-id="3ef42-319">Once you have the prediction set, the [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) method:</span></span>

* <span data-ttu-id="3ef42-320">Evalúa el modelo (compara los valores previstos con el conjunto de datos `Labels` real).</span><span class="sxs-lookup"><span data-stu-id="3ef42-320">Assesses the model (compares the predicted values with the actual dataset `Labels`).</span></span>

* <span data-ttu-id="3ef42-321">Devuelve las métricas de rendimiento del modelo.</span><span class="sxs-lookup"><span data-stu-id="3ef42-321">Returns the model performance metrics.</span></span>

<span data-ttu-id="3ef42-322">Agregue el código siguiente al método `ReuseAndTuneInceptionModel()` como la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="3ef42-322">Add the following code to the `ReuseAndTuneInceptionModel()` method as the next line:</span></span>

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#Evaluate)]

<span data-ttu-id="3ef42-323">Las siguiente métricas se evalúan para la clasificación de imágenes:</span><span class="sxs-lookup"><span data-stu-id="3ef42-323">The following metrics are evaluated for image classification:</span></span>

* <span data-ttu-id="3ef42-324">`Log-loss`: consulte [Pérdida de registro](../resources/glossary.md#log-loss).</span><span class="sxs-lookup"><span data-stu-id="3ef42-324">`Log-loss` - see [Log Loss](../resources/glossary.md#log-loss).</span></span> <span data-ttu-id="3ef42-325">Le recomendamos que la pérdida logarítmica esté lo más cerca posible de 0.</span><span class="sxs-lookup"><span data-stu-id="3ef42-325">You want Log-loss to be as close to zero as possible.</span></span>

* <span data-ttu-id="3ef42-326">`Per class Log-loss`.</span><span class="sxs-lookup"><span data-stu-id="3ef42-326">`Per class Log-loss`.</span></span> <span data-ttu-id="3ef42-327">Le recomendamos que la pérdida logarítmica por clase esté lo más cerca posible de 0.</span><span class="sxs-lookup"><span data-stu-id="3ef42-327">You want per class Log-loss to be as close to zero as possible.</span></span>

<span data-ttu-id="3ef42-328">Utilice el código siguiente para mostrar las métricas, compartir los resultados y, a continuación, trabajar con ellos:</span><span class="sxs-lookup"><span data-stu-id="3ef42-328">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayMetrics)]

 <span data-ttu-id="3ef42-329">Agregue el siguiente código para devolver el modelo entrenado, como la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="3ef42-329">Add the following code to return the trained model as the next line:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReturnModel)]

## <a name="classify-images-with-a-loaded-model"></a><span data-ttu-id="3ef42-330">Clasifique imágenes con un modelo cargado</span><span class="sxs-lookup"><span data-stu-id="3ef42-330">Classify images with a loaded model</span></span>

<span data-ttu-id="3ef42-331">Agregue la siguiente llamada al método `ClassifyImages()` como la siguiente línea de código del método `Main`:</span><span class="sxs-lookup"><span data-stu-id="3ef42-331">Add the following call to the `ClassifyImages()` method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallClassifyImages](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallClassifyImages)]

<span data-ttu-id="3ef42-332">El método `ClassifyImages()` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="3ef42-332">The `ClassifyImages()` method executes the following tasks:</span></span>

* <span data-ttu-id="3ef42-333">Lee el archivo .TSV en `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="3ef42-333">Reads .TSV file into `IEnumerable`.</span></span>
* <span data-ttu-id="3ef42-334">Predice las clasificaciones de imágenes en función de los datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="3ef42-334">Predicts image classifications based on test data.</span></span>

<span data-ttu-id="3ef42-335">Cree el método `ClassifyImages()` justo después del método `ReuseAndTuneInceptionModel()` y antes del método `PairAndDisplayResults()` con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ef42-335">Create the `ClassifyImages()` method, just after the `ReuseAndTuneInceptionModel()` method and just before the `PairAndDisplayResults()` method, using the following code:</span></span>

```csharp
public static void ClassifyImages(MLContext mlContext, string dataLocation, string imagesFolder, string outputModelLocation, ITransformer model)
{

}
```

<span data-ttu-id="3ef42-336">En primer lugar, llame al método `ReadFromTsv()` para crear una clase `IEnumerable<ImageData>` que contenga la ruta de acceso completa de cada `ImagePath`.</span><span class="sxs-lookup"><span data-stu-id="3ef42-336">First, call the `ReadFromTsv()` method to create an `IEnumerable<ImageData>` class that contains the fully qualified path for each `ImagePath`.</span></span> <span data-ttu-id="3ef42-337">Esta ruta de acceso a archivo es necesaria para emparejar los datos y los resultados de la predicción.</span><span class="sxs-lookup"><span data-stu-id="3ef42-337">You need that file path to pair your data and prediction results.</span></span> <span data-ttu-id="3ef42-338">También deberá convertir la clase `IEnumerable<ImageData>` en una `IDataView` que usará para realizar predicciones.</span><span class="sxs-lookup"><span data-stu-id="3ef42-338">You also need to convert the `IEnumerable<ImageData>` class to an `IDataView` that you will use to predict.</span></span> <span data-ttu-id="3ef42-339">Agregue el código siguiente como las próximas dos líneas del método `ClassifyImages()`:</span><span class="sxs-lookup"><span data-stu-id="3ef42-339">Add the following code as the next two lines in the `ClassifyImages()` method:</span></span>

[!code-csharp[CallReadFromTSV](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallReadFromTSV)]

<span data-ttu-id="3ef42-340">Tal como hizo anteriormente con los datos de imagen de entrenamiento, prediga la categoría de los datos de imagen de prueba con el método [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) del modelo que se pasó.</span><span class="sxs-lookup"><span data-stu-id="3ef42-340">As you did previously with the training image data, predict the category of the test image data using the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method of the model passed in.</span></span> <span data-ttu-id="3ef42-341">Agregue el código siguiente al método `ClassifyImages()` para las predicciones y para convertir la `IDataView` de `predictions` en `IEnumerable` para el emparejamiento y la visualización:</span><span class="sxs-lookup"><span data-stu-id="3ef42-341">Add the following code to the `ClassifyImages()` method for the predictions and to convert the `predictions` `IDataView` into an `IEnumerable` for pairing and display:</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#Predict)]

<span data-ttu-id="3ef42-342">Para emparejar y mostrar los datos de imagen de prueba y las predicciones, agregue el código siguiente para llamar al método `DisplayResults()` creado anteriormente como la línea siguiente del método `ClassifyImages()`:</span><span class="sxs-lookup"><span data-stu-id="3ef42-342">To pair and display your test image data and predictions, add the following code to call the `DisplayResults()` method previously created as the next line in the `ClassifyImages()` method:</span></span>

[!code-csharp[CallDisplayResults2](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallDisplayResults2)]

## <a name="classify-a-single-image-with-a-loaded-model"></a><span data-ttu-id="3ef42-343">Clasifique una imagen única con un modelo cargado</span><span class="sxs-lookup"><span data-stu-id="3ef42-343">Classify a single image with a loaded model</span></span>

<span data-ttu-id="3ef42-344">Agregue la siguiente llamada al método `ClassifySingleImage()` como la siguiente línea de código del método `Main`:</span><span class="sxs-lookup"><span data-stu-id="3ef42-344">Add the following call to the `ClassifySingleImage()` method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallClassifySingleImage](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallClassifySingleImage)]

<span data-ttu-id="3ef42-345">El método `ClassifySingleImage()` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="3ef42-345">The `ClassifySingleImage()` method executes the following tasks:</span></span>

* <span data-ttu-id="3ef42-346">Carga una instancia de `ImageData`.</span><span class="sxs-lookup"><span data-stu-id="3ef42-346">Loads an `ImageData` instance.</span></span>
* <span data-ttu-id="3ef42-347">Predice la clasificación de imágenes en función de los datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="3ef42-347">Predicts image classification based on test data.</span></span>

<span data-ttu-id="3ef42-348">Cree el método `ClassifySingleImage()` justo después del método `ClassifyImages()` y antes del método `PairAndDisplayResults()` con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ef42-348">Create the `ClassifySingleImage()` method, just after the `ClassifyImages()` method and just before the `PairAndDisplayResults()` method, using the following code:</span></span>

```csharp
public static void ClassifySingleImage(MLContext mlContext, string imagePath, string outputModelLocation, ITransformer model)
{

}
```

<span data-ttu-id="3ef42-349">En primer lugar, cree una clase `ImageData` que contenga la ruta de acceso completa y el nombre del archivo de imagen para la `ImagePath` única.</span><span class="sxs-lookup"><span data-stu-id="3ef42-349">First, create an `ImageData` class that contains the fully qualified path and image file name for the single `ImagePath`.</span></span> <span data-ttu-id="3ef42-350">Agregue el código siguiente como las siguientes líneas en el método `ClassifySingleImage()`:</span><span class="sxs-lookup"><span data-stu-id="3ef42-350">Add the following code as the next  lines in the `ClassifySingleImage()` method:</span></span>

[!code-csharp[LoadImageData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadImageData)]

<span data-ttu-id="3ef42-351">La [clase PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) es una API de conveniencia que realiza una predicción en una instancia única de datos.</span><span class="sxs-lookup"><span data-stu-id="3ef42-351">The [PredictionEngine class](xref:Microsoft.ML.PredictionEngine%602) is a convenience API that performs a prediction on a single instance of data.</span></span> <span data-ttu-id="3ef42-352">La función [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) realiza una predicción en una sola columna de datos.</span><span class="sxs-lookup"><span data-stu-id="3ef42-352">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single column of data.</span></span> <span data-ttu-id="3ef42-353">Pase `imageData` a `PredictionEngine` para predecir la categoría de imagen al agregar el código siguiente a `ClassifySingleImage()`:</span><span class="sxs-lookup"><span data-stu-id="3ef42-353">Pass `imageData` to the `PredictionEngine` to predict the image category by adding the following code to `ClassifySingleImage()`:</span></span>

[!code-csharp[PredictSingle](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#PredictSingle)]

<span data-ttu-id="3ef42-354">Muestre el resultado de la predicción como la línea de código siguiente en el método `ClassifySingleImage()`:</span><span class="sxs-lookup"><span data-stu-id="3ef42-354">Display the prediction result as the next line of code in the `ClassifySingleImage()` method:</span></span>

[!code-csharp[DisplayPrediction](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPrediction)]

## <a name="results"></a><span data-ttu-id="3ef42-355">Resultados</span><span class="sxs-lookup"><span data-stu-id="3ef42-355">Results</span></span>

<span data-ttu-id="3ef42-356">Después de seguir los pasos anteriores, ejecute la aplicación de consola (Ctrl + F5).</span><span class="sxs-lookup"><span data-stu-id="3ef42-356">After following the previous steps, run your console app (Ctrl + F5).</span></span> <span data-ttu-id="3ef42-357">Los resultados deberían ser similares a la salida siguiente.</span><span class="sxs-lookup"><span data-stu-id="3ef42-357">Your results should be similar to the following output.</span></span>  <span data-ttu-id="3ef42-358">Es posible que vea advertencias o mensajes de procesamiento, si bien se han quitado de los resultados siguientes para mayor claridad.</span><span class="sxs-lookup"><span data-stu-id="3ef42-358">You may see warnings or processing messages, but these messages have been removed from the following results for clarity.</span></span>

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
=============== Making classifications ===============
Image: broccoli.png predicted as: food with score: 0.905548
Image: pizza3.jpg predicted as: food with score: 0.9709008
Image: teddy6.jpg predicted as: toy with score: 0.9750155
=============== Making single image classification ===============
Image: toaster3.jpg predicted as: appliance with score: 0.9625379

C:\Program Files\dotnet\dotnet.exe (process 4304) exited with code 0.
Press any key to close this window . . .
```

<span data-ttu-id="3ef42-359">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="3ef42-359">Congratulations!</span></span> <span data-ttu-id="3ef42-360">Ha creado correctamente un modelo de Machine Learning para la clasificación de imágenes al reutilizar un modelo de `TensorFlow` entrenado previamente en ML.NET.</span><span class="sxs-lookup"><span data-stu-id="3ef42-360">You've now successfully built a machine learning model for image classification by reusing a pre-trained `TensorFlow` model in ML.NET.</span></span>

<span data-ttu-id="3ef42-361">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF).</span><span class="sxs-lookup"><span data-stu-id="3ef42-361">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) repository.</span></span>

<span data-ttu-id="3ef42-362">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="3ef42-362">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="3ef42-363">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="3ef42-363">Understand the problem</span></span>
> * <span data-ttu-id="3ef42-364">Volver a usar y ajustar el modelo entrenado previamente</span><span class="sxs-lookup"><span data-stu-id="3ef42-364">Reuse and tune the pre-trained model</span></span>
> * <span data-ttu-id="3ef42-365">Clasifique imágenes con un modelo cargado</span><span class="sxs-lookup"><span data-stu-id="3ef42-365">Classify images with a loaded model</span></span>

<span data-ttu-id="3ef42-366">Consulte el repositorio de GitHub con ejemplos de Machine Learning para explorar un ejemplo expandido de clasificación de imágenes.</span><span class="sxs-lookup"><span data-stu-id="3ef42-366">Check out the Machine Learning samples GitHub repository to explore an expanded image classification sample.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="3ef42-367">Repositorio dotnet/machinelearning-samples de GitHub</span><span class="sxs-lookup"><span data-stu-id="3ef42-367">dotnet/machinelearning-samples GitHub repository</span></span>](https://github.com/dotnet/machinelearning-samples/)
