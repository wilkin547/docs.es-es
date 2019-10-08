---
title: 'Tutorial: Generación de un modelo de clasificación de imágenes de ML.NET desde un modelo entrenado previamente de TensorFlow'
description: Obtenga información sobre cómo transferir el conocimiento de un modelo de TensorFlow existente a un modelo de clasificación de imágenes de ML.NET nuevo. El modelo TensorFlow se entrenó para clasificar las imágenes en mil categorías. El modelo de ML.NET usa el aprendizaje de transferencia para clasificar las imágenes en menos categorías más amplias.
ms.date: 09/30/2019
ms.topic: tutorial
ms.custom: mvc, title-hack-0612
author: natke
ms.author: nakersha
ms.openlocfilehash: 8ae966330ca85722c72c92e26363d99c7d9de3e7
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698646"
---
# <a name="tutorial-generate-an-mlnet-image-classification-model-from-a-pre-trained-tensorflow-model"></a><span data-ttu-id="6dcb0-105">Tutorial: Generación de un modelo de clasificación de imágenes de ML.NET desde un modelo entrenado previamente de TensorFlow</span><span class="sxs-lookup"><span data-stu-id="6dcb0-105">Tutorial: Generate an ML.NET image classification model from a pre-trained TensorFlow model</span></span>

<span data-ttu-id="6dcb0-106">Obtenga información sobre cómo transferir el conocimiento de un modelo de TensorFlow existente a un modelo de clasificación de imágenes de ML.NET nuevo.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-106">Learn how to transfer the knowledge from an existing TensorFlow model into a new ML.NET image classification model.</span></span>

<span data-ttu-id="6dcb0-107">El modelo de TensorFlow se entrenó para clasificar las imágenes en mil categorías.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-107">The TensorFlow model was trained to classify images into a thousand categories.</span></span> <span data-ttu-id="6dcb0-108">El modelo de ML.NET usa parte del modelo de TensorFlow en su canalización para entrenar un modelo con el fin de clasificar las imágenes en 3 categorías.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-108">The ML.NET model makes use of part of the TensorFlow model in its pipeline to train a model to classify images into 3 categories.</span></span>

<span data-ttu-id="6dcb0-109">Entrenar un modelo de [clasificación de imágenes](https://en.wikipedia.org/wiki/Outline_of_object_recognition) desde cero requiere establecer millones de parámetros, una enorme cantidad de datos de aprendizaje etiquetados y una gran cantidad de recursos informáticos (cientos de horas de GPU).</span><span class="sxs-lookup"><span data-stu-id="6dcb0-109">Training an [Image Classification](https://en.wikipedia.org/wiki/Outline_of_object_recognition) model from scratch requires setting millions of parameters, a ton of labeled training data and a vast amount of compute resources (hundreds of GPU hours).</span></span> <span data-ttu-id="6dcb0-110">Si bien no es tan eficaz como entrenar un modelo personalizado desde cero, el aprendizaje por transferencia permite acortar este proceso al trabajar con miles de imágenes frente a millones de imágenes etiquetadas y crear un modelo personalizado con bastante rapidez (menos de una hora en una máquina sin GPU).</span><span class="sxs-lookup"><span data-stu-id="6dcb0-110">While not as effective as training a custom model from scratch, transfer learning allows you to shortcut this process by working with thousands of images vs. millions of labeled images and build a customized model fairly quickly (within an hour on a machine without a GPU).</span></span> <span data-ttu-id="6dcb0-111">En este tutorial se amplía aún más ese proceso, con solo una docena de imágenes de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-111">This tutorial scales that process down even further, using only a dozen training images.</span></span>

<span data-ttu-id="6dcb0-112">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-112">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="6dcb0-113">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="6dcb0-113">Understand the problem</span></span>
> * <span data-ttu-id="6dcb0-114">Incorporación del modelo de TensorFlow entrenado previamente en la canalización de ML.NET</span><span class="sxs-lookup"><span data-stu-id="6dcb0-114">Incorporate the pre-trained TensorFlow model into the ML.NET pipeline</span></span>
> * <span data-ttu-id="6dcb0-115">Entrenamiento y evaluación del modelo de ML.NET</span><span class="sxs-lookup"><span data-stu-id="6dcb0-115">Train and evaluate the ML.NET model</span></span>
> * <span data-ttu-id="6dcb0-116">Clasificación de una imagen de prueba</span><span class="sxs-lookup"><span data-stu-id="6dcb0-116">Classify a test image</span></span>

<span data-ttu-id="6dcb0-117">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF).</span><span class="sxs-lookup"><span data-stu-id="6dcb0-117">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) repository.</span></span> <span data-ttu-id="6dcb0-118">Tenga en cuenta que, de forma predeterminada, la configuración del proyecto de .NET de este tutorial tiene como destino .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-118">Note that by default, the .NET project configuration for this tutorial targets .NET core 2.2.</span></span>

## <a name="what-is-transfer-learning"></a><span data-ttu-id="6dcb0-119">¿Qué es el aprendizaje de transferencia?</span><span class="sxs-lookup"><span data-stu-id="6dcb0-119">What is transfer learning?</span></span>

<span data-ttu-id="6dcb0-120">El aprendizaje de transferencia es el proceso de usar los conocimientos adquiridos al resolver un problema y aplicarlos a un problema distinto, pero relacionado.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-120">Transfer learning is the process of using knowledge gained while solving one problem and applying it to a different but related problem.</span></span>

<span data-ttu-id="6dcb0-121">En este tutorial, usará parte de un modelo de TensorFlow (entrenado para clasificar las imágenes en mil categorías) en un modelo de ML.NET que clasifica las imágenes en 3 categorías.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-121">For this tutorial, you use part of a TensorFlow model - trained to classify images into a thousand categories - in an ML.NET model that classifies images into 3 categories.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6dcb0-122">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6dcb0-122">Prerequisites</span></span>

* <span data-ttu-id="6dcb0-123">[Visual Studio 2017 15.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-123">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* <span data-ttu-id="6dcb0-124">Paquete NuGet de Microsoft.ML 1.3.1</span><span class="sxs-lookup"><span data-stu-id="6dcb0-124">Microsoft.ML 1.3.1 Nuget package</span></span>
* <span data-ttu-id="6dcb0-125">Paquete NuGet de Microsoft.ML.ImageAnalytics 1.3.1</span><span class="sxs-lookup"><span data-stu-id="6dcb0-125">Microsoft.ML.ImageAnalytics 1.3.1 Nuget package</span></span>
* <span data-ttu-id="6dcb0-126">Paquete NuGet de Microsoft.ML.TensorFlow 1.3.1</span><span class="sxs-lookup"><span data-stu-id="6dcb0-126">Microsoft.ML.TensorFlow 1.3.1 Nuget package</span></span>

* [<span data-ttu-id="6dcb0-127">El archivo ZIP del directorio de recursos del tutorial</span><span class="sxs-lookup"><span data-stu-id="6dcb0-127">The tutorial assets directory .ZIP file</span></span>](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip)

* [<span data-ttu-id="6dcb0-128">El modelo de Machine Learning de InceptionV1</span><span class="sxs-lookup"><span data-stu-id="6dcb0-128">The InceptionV1 machine learning model</span></span>](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)

## <a name="select-the-right-machine-learning-task"></a><span data-ttu-id="6dcb0-129">Selección de la tarea de aprendizaje automático adecuada</span><span class="sxs-lookup"><span data-stu-id="6dcb0-129">Select the right machine learning task</span></span>

### <a name="deep-learning"></a><span data-ttu-id="6dcb0-130">Aprendizaje profundo</span><span class="sxs-lookup"><span data-stu-id="6dcb0-130">Deep learning</span></span>

<span data-ttu-id="6dcb0-131">El [aprendizaje profundo](https://en.wikipedia.org/wiki/Deep_learning) es un subconjunto de Machine Learning, que está revolucionando áreas como Computer Vision y reconocimiento de voz.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-131">[Deep learning](https://en.wikipedia.org/wiki/Deep_learning) is a subset of Machine Learning, which is revolutionizing areas like Computer Vision and Speech Recognition.</span></span>

<span data-ttu-id="6dcb0-132">Los modelos de aprendizaje profundo se entrenan mediante el uso de grandes conjuntos de [datos etiquetados](https://en.wikipedia.org/wiki/Labeled_data) y [redes neuronales](https://en.wikipedia.org/wiki/Artificial_neural_network) que contienen varias capas de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-132">Deep learning models are trained by using large sets of [labeled data](https://en.wikipedia.org/wiki/Labeled_data) and [neural networks](https://en.wikipedia.org/wiki/Artificial_neural_network) that contain multiple learning layers.</span></span> <span data-ttu-id="6dcb0-133">Aprendizaje profundo:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-133">Deep learning:</span></span>

* <span data-ttu-id="6dcb0-134">Funciona mejor en algunas tareas como Computer Vision.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-134">Performs better on some tasks like Computer Vision.</span></span>
* <span data-ttu-id="6dcb0-135">Requiere enormes cantidades de datos de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-135">Requires huge amounts of training data.</span></span>

<span data-ttu-id="6dcb0-136">La clasificación de imágenes es una tarea de Machine Learning común que nos permite clasificar imágenes automáticamente en categorías como:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-136">Image Classification is a common Machine Learning task that allows us to automatically classify images into categories such as:</span></span>

* <span data-ttu-id="6dcb0-137">Detectar o no una cara humana en una imagen.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-137">Detecting a human face in an image or not.</span></span>
* <span data-ttu-id="6dcb0-138">Detectar gatos o perros.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-138">Detecting cats vs. dogs.</span></span>

 <span data-ttu-id="6dcb0-139">O bien, como en las imágenes siguientes, determinar si una imagen es un alimento, un juguete o un dispositivo:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-139">Or as in the following images, determining if an image is a(n)  food, toy, or appliance:</span></span>

<span data-ttu-id="6dcb0-140">![imagen de una pizza](./media/image-classification/220px-Pepperoni_pizza.jpg)
![imagen de un oso de peluche](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![imagen de una tostadora](./media/image-classification/193px-Broodrooster.jpg)</span><span class="sxs-lookup"><span data-stu-id="6dcb0-140">![pizza image](./media/image-classification/220px-Pepperoni_pizza.jpg)
![teddy bear image](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![toaster image](./media/image-classification/193px-Broodrooster.jpg)</span></span>

>[!Note]
> <span data-ttu-id="6dcb0-141">Las imágenes anteriores pertenecen a Wikimedia Commons y tienen los siguientes atributos:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-141">The preceding images belong to Wikimedia Commons and are attributed as follows:</span></span>
>
> * <span data-ttu-id="6dcb0-142">"220px-Pepperoni_pizza.jpg" de dominio público, https://commons.wikimedia.org/w/index.php?curid=79505,</span><span class="sxs-lookup"><span data-stu-id="6dcb0-142">"220px-Pepperoni_pizza.jpg" Public Domain, https://commons.wikimedia.org/w/index.php?curid=79505,</span></span>
> * <span data-ttu-id="6dcb0-143">"119px-Nalle_-_a_small_brown_teddy_bear.jpg" de [Jonik](https://commons.wikimedia.org/wiki/User:Jonik), autofotografía, CC BY-SA 2.0, https://commons.wikimedia.org/w/index.php?curid=48166.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-143">"119px-Nalle_-_a_small_brown_teddy_bear.jpg" By [Jonik](https://commons.wikimedia.org/wiki/User:Jonik) - Self-photographed, CC BY-SA 2.0, https://commons.wikimedia.org/w/index.php?curid=48166.</span></span>
> * <span data-ttu-id="6dcb0-144">"193px-Broodrooster.jpg" de [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972), trabajo propio, CC BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=27403</span><span class="sxs-lookup"><span data-stu-id="6dcb0-144">"193px-Broodrooster.jpg" By [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972) - Own work, CC BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=27403</span></span>

<span data-ttu-id="6dcb0-145">`Inception model` está entrenado para clasificar imágenes en miles de categorías, pero, en este tutorial, el usuario deberá clasificar las imágenes en un conjunto de categorías más pequeño y solo en esas categorías.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-145">The `Inception model` is trained to classify images into a thousand categories, but for this tutorial, you need to classify images in a smaller category set, and only those categories.</span></span> <span data-ttu-id="6dcb0-146">Escriba la parte `transfer` de `transfer learning`.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-146">Enter the `transfer` part of `transfer learning`.</span></span> <span data-ttu-id="6dcb0-147">Puede transferir la capacidad que `Inception model` tiene para reconocer y clasificar imágenes a las nuevas categorías limitadas del clasificador personalizado de imágenes.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-147">You can transfer the `Inception model`'s ability to recognize and classify images to the new limited categories of your custom image classifier.</span></span>

* <span data-ttu-id="6dcb0-148">Alimentos</span><span class="sxs-lookup"><span data-stu-id="6dcb0-148">Food</span></span>
* <span data-ttu-id="6dcb0-149">Juguetes</span><span class="sxs-lookup"><span data-stu-id="6dcb0-149">Toy</span></span>
* <span data-ttu-id="6dcb0-150">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="6dcb0-150">Appliance</span></span>

<span data-ttu-id="6dcb0-151">En este tutorial se usa el modelo de aprendizaje profundo del [modelo de inicio](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) de TensorFlow, un modelo de reconocimiento de imágenes popular entrenado en el conjunto de datos `ImageNet`.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-151">This tutorial uses the TensorFlow [Inception model](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) deep learning model, a popular image recognition model trained on the `ImageNet` dataset.</span></span> <span data-ttu-id="6dcb0-152">El modelo de TensorFlow clasifica imágenes completas en miles de clases como "Paraguas", "Jersey" y "Lavavajillas".</span><span class="sxs-lookup"><span data-stu-id="6dcb0-152">The TensorFlow model classifies entire images into a thousand classes, such as “Umbrella”, “Jersey”, and “Dishwasher”.</span></span>

<span data-ttu-id="6dcb0-153">Como `Inception model` se entrenó previamente en miles de imágenes distintas, contiene internamente las [características de imagen](https://en.wikipedia.org/wiki/Feature_(computer_vision)) necesarias para la identificación de imágenes.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-153">Because the `Inception model` has already been pre trained on thousands of different images, internally it contains the [image features](https://en.wikipedia.org/wiki/Feature_(computer_vision)) needed for image identification.</span></span> <span data-ttu-id="6dcb0-154">Podemos usar estas características de imagen internas en el modelo para entrenar un modelo nuevo con muchas menos clases.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-154">We can make use of these internal image features in the model to train a new model with far fewer classes.</span></span>

<span data-ttu-id="6dcb0-155">Como se muestra en el diagrama siguiente, puede agregar una referencia a los paquetes NuGet de ML.NET en las aplicaciones de .NET Core o .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-155">As shown in the following diagram, you add a reference to the ML.NET NuGet packages in your .NET Core or .NET Framework applications.</span></span> <span data-ttu-id="6dcb0-156">En segundo plano, ML.NET incluye y hace referencia a la biblioteca nativa de `TensorFlow` que permite escribir código que carga un archivo de modelo de `TensorFlow` entrenado existente.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-156">Under the covers, ML.NET includes and references the native `TensorFlow` library that allows you to write code that loads an existing trained `TensorFlow` model file.</span></span>

![Diagrama de la arquitectura de ML.NET de transformación de TensorFlow](./media/image-classification/tensorflow-mlnet.png)

### <a name="multiclass-classification"></a><span data-ttu-id="6dcb0-158">Clasificación multiclase</span><span class="sxs-lookup"><span data-stu-id="6dcb0-158">Multiclass classification</span></span>

<span data-ttu-id="6dcb0-159">Después de usar el modelo de inicio de TensorFlow para extraer características adecuadas como entrada para un algoritmo de aprendizaje automático clásico, se agrega un [clasificador multiclase](../resources/tasks.md#multiclass-classification) de ML.NET.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-159">After using the TensorFlow inception model to extract features suitable as input for a classical machine learning algorithm, we add an ML.NET [multi-class classifier](../resources/tasks.md#multiclass-classification).</span></span>

<span data-ttu-id="6dcb0-160">El entrenador específico que se usa en este caso es el [algoritmo de regresión logística multinomial](https://en.wikipedia.org/wiki/Multinomial_logistic_regression).</span><span class="sxs-lookup"><span data-stu-id="6dcb0-160">The specific trainer used in this case is the [multinomial logistic regression algorithm](https://en.wikipedia.org/wiki/Multinomial_logistic_regression).</span></span>

<span data-ttu-id="6dcb0-161">El algoritmo que implementa este entrenador funciona con un gran número de características, que es el caso de un modelo de aprendizaje profundo que funciona con datos de imagen.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-161">The algorithm implemented by this trainer performs well on problems with a large number of features, which is the case for a deep learning model operating on image data.</span></span>

### <a name="data"></a><span data-ttu-id="6dcb0-162">Datos</span><span class="sxs-lookup"><span data-stu-id="6dcb0-162">Data</span></span>

<span data-ttu-id="6dcb0-163">Hay dos orígenes de datos: el archivo `.tsv` y los archivos de imagen.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-163">There are two data sources: the `.tsv` file, and the image files.</span></span>  <span data-ttu-id="6dcb0-164">El archivo `tags.tsv` contiene dos columnas: la primera está definida como `ImagePath` y la segunda es la `Label` que corresponde a la imagen.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-164">The `tags.tsv` file contains two columns: the first one is defined as `ImagePath` and the second one is the `Label` corresponding to the image.</span></span> <span data-ttu-id="6dcb0-165">El archivo de ejemplo siguiente no tiene una fila de encabezado y se ve así:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-165">The following example file doesn't have a header row, and looks like this:</span></span>

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

<span data-ttu-id="6dcb0-166">Las imágenes de entrenamiento y prueba se encuentran en las carpetas de recursos que descargará en un archivo ZIP.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-166">The training and testing images are located in the assets folders that you'll download in a zip file.</span></span> <span data-ttu-id="6dcb0-167">Estas imágenes pertenecen a Wikimedia Commons.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-167">These images belong to Wikimedia Commons.</span></span>
> <span data-ttu-id="6dcb0-168">*[Wikimedia Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), el repositorio multimedia gratuito*.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-168">*[Wikimedia Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), the free media repository.*</span></span> <span data-ttu-id="6dcb0-169">Recuperado a las 10:48 del 17 de octubre de 2018 desde: https://commons.wikimedia.org/wiki/Pizza https://commons.wikimedia.org/wiki/Toaster https://commons.wikimedia.org/wiki/Teddy_bear</span><span class="sxs-lookup"><span data-stu-id="6dcb0-169">Retrieved 10:48, October 17, 2018 from: https://commons.wikimedia.org/wiki/Pizza https://commons.wikimedia.org/wiki/Toaster https://commons.wikimedia.org/wiki/Teddy_bear</span></span>

## <a name="setup"></a><span data-ttu-id="6dcb0-170">Programa de instalación</span><span class="sxs-lookup"><span data-stu-id="6dcb0-170">Setup</span></span>

### <a name="create-a-project"></a><span data-ttu-id="6dcb0-171">Crear un proyecto</span><span class="sxs-lookup"><span data-stu-id="6dcb0-171">Create a project</span></span>

1. <span data-ttu-id="6dcb0-172">Cree una **aplicación de consola de .NET Core** denominada "TransferLearningTF".</span><span class="sxs-lookup"><span data-stu-id="6dcb0-172">Create a **.NET Core Console Application** called "TransferLearningTF".</span></span>

1. <span data-ttu-id="6dcb0-173">Instale el **paquete NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-173">Install the **Microsoft.ML NuGet Package**:</span></span>

    * <span data-ttu-id="6dcb0-174">En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-174">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span>
    * <span data-ttu-id="6dcb0-175">Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar y busque **Microsoft.ML**.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-175">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**.</span></span>
    * <span data-ttu-id="6dcb0-176">Haga clic en el menú desplegable **Versión**, seleccione el paquete **1.3.1** en la lista y, luego, el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-176">Click on the **Version** drop-down, select the **1.3.1** package in the list, and select the **Install** button.</span></span>
    * <span data-ttu-id="6dcb0-177">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de los cambios**.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-177">Select the **OK** button on the **Preview Changes** dialog.</span></span>
    * <span data-ttu-id="6dcb0-178">Haga clic en el botón **Acepto** en el cuadro de diálogo **Aceptación de la licencia** si está de acuerdo con los términos de licencia de los paquetes que aparecen.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-178">Select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>
    * <span data-ttu-id="6dcb0-179">Repita estos pasos para **Microsoft.ML.ImageAnalytics v1.3.1** y **Microsoft.ML.TensorFlow v1.3.1**.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-179">Repeat these steps for **Microsoft.ML.ImageAnalytics v1.3.1** and **Microsoft.ML.TensorFlow v1.3.1**.</span></span>

### <a name="download-assets"></a><span data-ttu-id="6dcb0-180">Descarga de activos</span><span class="sxs-lookup"><span data-stu-id="6dcb0-180">Download assets</span></span>

1. <span data-ttu-id="6dcb0-181">Descargue el [archivo ZIP del directorio de recursos del proyecto](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip) y descomprímalo.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-181">Download [The project assets directory zip file](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip), and unzip.</span></span>

1. <span data-ttu-id="6dcb0-182">Copie el directorio `assets` en el directorio de proyecto *TransferLearningTF*.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-182">Copy the `assets` directory into your *TransferLearningTF* project directory.</span></span> <span data-ttu-id="6dcb0-183">Este directorio y sus subdirectorios contienen los datos y los archivos auxiliares (excepto los del modelo de inicio, que descargará y agregará en el paso siguiente) que se necesitan en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-183">This directory and its subdirectories contain the data and support files (except for the Inception model, which you'll download and add in the next step) needed for this tutorial.</span></span>

1. <span data-ttu-id="6dcb0-184">Descargue el [modelo de inicio](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) y descomprímalo.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-184">Download the [Inception model](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip), and unzip.</span></span>

1. <span data-ttu-id="6dcb0-185">Copie el contenido del directorio `inception5h` que acaba de descomprimir en el directorio `assets/inputs-train/inception` del proyecto *TransferLearningTF*.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-185">Copy the contents of the `inception5h` directory just unzipped into your *TransferLearningTF* project `assets/inputs-train/inception` directory.</span></span> <span data-ttu-id="6dcb0-186">En este directorio está el modelo y los archivos auxiliares adicionales que se necesitan en este tutorial, tal como se muestra en la imagen siguiente:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-186">This directory contains the model and additional support files needed for this tutorial, as shown in the following image:</span></span>

   ![Contenido del directorio de inicio](./media/image-classification/inception-files.png)

1. <span data-ttu-id="6dcb0-188">En el Explorador de soluciones, haga clic con el botón derecho en cada uno de los archivos del directorio de recursos y los subdirectorios y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-188">In Solution Explorer, right-click each of the files in the asset directory and subdirectories and select **Properties**.</span></span> <span data-ttu-id="6dcb0-189">En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-189">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="6dcb0-190">Crear clases y definir rutas de acceso</span><span class="sxs-lookup"><span data-stu-id="6dcb0-190">Create classes and define paths</span></span>

1. <span data-ttu-id="6dcb0-191">Agregue las siguientes instrucciones `using` adicionales a la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-191">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

    [!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddUsings)]

1. <span data-ttu-id="6dcb0-192">Agregue el código siguiente a la línea inmediatamente por encima del método `Main` para especificar las rutas de acceso a los recursos:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-192">Add the following code to the line right above the `Main` method to specify the asset paths:</span></span>

    [!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DeclareGlobalVariables)]

1. <span data-ttu-id="6dcb0-193">Cree clases para los datos de entrada y las predicciones.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-193">Create classes for your input data, and predictions.</span></span>

    [!code-csharp[DeclareImageData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DeclareImageData)]

    <span data-ttu-id="6dcb0-194">`ImageData` es la clase de datos de imagen de entrada y tiene los campos <xref:System.String> siguientes:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-194">`ImageData` is the input image data class and has the following <xref:System.String> fields:</span></span>

    * <span data-ttu-id="6dcb0-195">`ImagePath` contiene el nombre del archivo de imagen.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-195">`ImagePath` contains the image file name.</span></span>
    * <span data-ttu-id="6dcb0-196">`Label` contiene un valor para la etiqueta de imagen.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-196">`Label` contains a value for the image label.</span></span>

1. <span data-ttu-id="6dcb0-197">Agregue una clase nueva al proyecto para `ImagePrediction`:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-197">Add a new class to your project for `ImagePrediction`:</span></span>

    [!code-csharp[DeclareImagePrediction](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DeclareImagePrediction)]

    <span data-ttu-id="6dcb0-198">`ImagePrediction` es la clase de predicción de imagen y tiene los campos siguientes:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-198">`ImagePrediction` is the image prediction class and has the following fields:</span></span>

    * <span data-ttu-id="6dcb0-199">`Score` contiene el porcentaje de confianza de una clasificación de imágenes determinada.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-199">`Score` contains the confidence percentage for a given image classification.</span></span>
    * <span data-ttu-id="6dcb0-200">`PredictedLabelValue` contiene un valor para la etiqueta de clasificación de imágenes prevista.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-200">`PredictedLabelValue` contains a value for the predicted image classification label.</span></span>

    <span data-ttu-id="6dcb0-201">`ImagePrediction` es la clase usada para la predicción una vez entrenado el modelo.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-201">`ImagePrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="6dcb0-202">Tiene una `string` (`ImagePath`) para la ruta de acceso a la imagen.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-202">It has a `string` (`ImagePath`) for the image path.</span></span> <span data-ttu-id="6dcb0-203">`Label` se usa para reutilizar y entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-203">The `Label` is used to reuse and train the model.</span></span> <span data-ttu-id="6dcb0-204">`PredictedLabelValue` se usa durante la predicción y la evaluación.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-204">The `PredictedLabelValue` is used during prediction and evaluation.</span></span> <span data-ttu-id="6dcb0-205">Para la evaluación, se utiliza una entrada con los datos de entrenamiento, los valores de predicción y el modelo.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-205">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="6dcb0-206">Inicializar variables en Main</span><span class="sxs-lookup"><span data-stu-id="6dcb0-206">Initialize variables in Main</span></span>

1. <span data-ttu-id="6dcb0-207">Inicialice la variable `mlContext` con una instancia nueva de `MLContext`.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-207">Initialize the `mlContext` variable with a new instance of `MLContext`.</span></span>  <span data-ttu-id="6dcb0-208">Reemplace la línea `Console.WriteLine("Hello World!")` por el código siguiente en el método `Main`:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-208">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

    [!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CreateMLContext)]

    <span data-ttu-id="6dcb0-209">La [clase MLContext](xref:Microsoft.ML.MLContext) es un punto de partida para todas las operaciones de ML.NET. Al inicializar `mlContext`, se crea un entorno de ML.NET que se puede compartir entre los objetos del flujo de trabajo de creación de modelos.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-209">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="6dcb0-210">Como concepto, se parece a `DBContext` en Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-210">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

### <a name="create-a-struct-for-inception-model-parameters"></a><span data-ttu-id="6dcb0-211">Creación de una estructura para los parámetros del modelo de inicio</span><span class="sxs-lookup"><span data-stu-id="6dcb0-211">Create a struct for Inception model parameters</span></span>

1. <span data-ttu-id="6dcb0-212">El modelo de inicio tiene varios parámetros que se deben transmitir.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-212">The Inception model has several parameters you need to pass in.</span></span> <span data-ttu-id="6dcb0-213">Cree una estructura para asignar los valores de parámetros a nombres descriptivos con el código siguiente, justo después del método `Main()`:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-213">Create a struct to map the parameter values to friendly names with the following code, just after the `Main()` method:</span></span>

    [!code-csharp[InceptionSettings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#InceptionSettings)]

### <a name="create-a-display-utility-method"></a><span data-ttu-id="6dcb0-214">Crear un método de utilidad para mostrar</span><span class="sxs-lookup"><span data-stu-id="6dcb0-214">Create a display utility method</span></span>

<span data-ttu-id="6dcb0-215">Dado que se mostrarán los datos de imagen y las predicciones relacionadas más de una vez, cree un método de utilidad para mostrar a fin de controlar la visualización de los resultados de la imagen y la predicción.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-215">Since you'll display the image data and the related predictions more than once, create a display utility method to handle displaying the image and prediction results.</span></span>

1. <span data-ttu-id="6dcb0-216">Cree el método `DisplayResults()` justo después de la estructura `InceptionSettings` con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-216">Create the `DisplayResults()` method, just after the `InceptionSettings` struct, using the following code:</span></span>

    ```csharp
    private static void DisplayResults(IEnumerable<ImagePrediction> imagePredictionData)
    {

    }
    ```

1. <span data-ttu-id="6dcb0-217">Rellene el cuerpo del método `DisplayResults`:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-217">Fill in the body of the `DisplayResults` method:</span></span>

    [!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPredictions)]

### <a name="create-a-tsv-file-utility-method"></a><span data-ttu-id="6dcb0-218">Crear un método de utilidad de archivo .tsv</span><span class="sxs-lookup"><span data-stu-id="6dcb0-218">Create a .tsv file utility method</span></span>

1. <span data-ttu-id="6dcb0-219">Cree el método `ReadFromTsv()`, justo después del método `DisplayResults()`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-219">Create the `ReadFromTsv()` method, just after the `DisplayResults()` method, using the following code:</span></span>

    ```csharp
    public static IEnumerable<ImageData> ReadFromTsv(string file, string folder)
    {

    }
    ```

1. <span data-ttu-id="6dcb0-220">Rellene el cuerpo del método `ReadFromTsv`:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-220">Fill in the body of the `ReadFromTsv` method:</span></span>

    [!code-csharp[ReadFromTsv](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReadFromTsv)]

    <span data-ttu-id="6dcb0-221">El código analiza el archivo `tags.tsv` para agregar la ruta de acceso al archivo al nombre del archivo de imagen de la propiedad `ImagePath` y lo carga junto con `Label` en un objeto `ImageData`.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-221">The code parses through the `tags.tsv` file to add the file path to the image file name for the `ImagePath` property and load it and the `Label` into an `ImageData` object.</span></span>

### <a name="create-a-method-to-make-a-prediction"></a><span data-ttu-id="6dcb0-222">Creación de un método para hacer una predicción</span><span class="sxs-lookup"><span data-stu-id="6dcb0-222">Create a method to make a prediction</span></span>

1. <span data-ttu-id="6dcb0-223">Cree el método `ClassifySingleImage()`, justo antes del método `DisplayResults()`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-223">Create the `ClassifySingleImage()` method, just before the `DisplayResults()` method, using the following code:</span></span>

    ```csharp
    public static void ClassifySingleImage(MLContext mlContext, ITransformer model)
    {

    }
    ```

1. <span data-ttu-id="6dcb0-224">Cree un objeto `ImageData` que contenga la ruta de acceso completa y el nombre del archivo de imagen para la `ImagePath` única.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-224">Create an `ImageData` object that contains the fully qualified path and image file name for the single `ImagePath`.</span></span> <span data-ttu-id="6dcb0-225">Agregue el código siguiente como las siguientes líneas en el método `ClassifySingleImage()`:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-225">Add the following code as the next  lines in the `ClassifySingleImage()` method:</span></span>

    [!code-csharp[LoadImageData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadImageData)]

1. <span data-ttu-id="6dcb0-226">Para hacer una predicción única, agregue el código siguiente como la línea siguiente en el método `ClassifySingleImage`:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-226">Make a single prediction, by adding the following code as the next line in the `ClassifySingleImage` method:</span></span>

    [!code-csharp[PredictSingle](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#PredictSingle)]

    <span data-ttu-id="6dcb0-227">Para obtener la predicción, use el método [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A).</span><span class="sxs-lookup"><span data-stu-id="6dcb0-227">To get the prediction, use the [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) method.</span></span> <span data-ttu-id="6dcb0-228">[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) es una API de conveniencia, que le permite realizar una predicción en una única instancia de datos.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-228">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to perform a prediction on a single instance of data.</span></span> <span data-ttu-id="6dcb0-229">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) no es seguro para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-229">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="6dcb0-230">Es aceptable usarlo en entornos de un solo subproceso o prototipo.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-230">It's acceptable to use in single-threaded or prototype environments.</span></span> <span data-ttu-id="6dcb0-231">Para mejorar el rendimiento y la seguridad para subprocesos en entornos de producción, use el servicio `PredictionEnginePool`, que crea un [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) de objetos de [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) para su uso en toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-231">For improved performance and thread safety in production environments, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span> <span data-ttu-id="6dcb0-232">Consulte esta guía sobre cómo [usar `PredictionEnginePool` en una API web de ASP.NET Core](https://docs.microsoft.com/en-us/dotnet/machine-learning/how-to-guides/serve-model-web-api-ml-net#register-predictionenginepool-for-use-in-the-application)</span><span class="sxs-lookup"><span data-stu-id="6dcb0-232">See this guide on how to [use `PredictionEnginePool` in an ASP.NET Core Web API](https://docs.microsoft.com/en-us/dotnet/machine-learning/how-to-guides/serve-model-web-api-ml-net#register-predictionenginepool-for-use-in-the-application)</span></span>

    > [!NOTE]
    > <span data-ttu-id="6dcb0-233">La extensión del servicio `PredictionEnginePool` está actualmente en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-233">`PredictionEnginePool` service extension is currently in preview.</span></span>

1. <span data-ttu-id="6dcb0-234">Muestre el resultado de la predicción como la línea de código siguiente en el método `ClassifySingleImage()`:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-234">Display the prediction result as the next line of code in the `ClassifySingleImage()` method:</span></span>

   [!code-csharp[DisplayPrediction](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPrediction)]

## <a name="construct-the-mlnet-model-pipeline"></a><span data-ttu-id="6dcb0-235">Construcción de la canalización del modelo de ML.NET</span><span class="sxs-lookup"><span data-stu-id="6dcb0-235">Construct the ML.NET model pipeline</span></span>

<span data-ttu-id="6dcb0-236">Una canalización del modelo de ML.NET es una cadena de estimadores.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-236">An ML.NET model pipeline is a chain of estimators.</span></span> <span data-ttu-id="6dcb0-237">Tenga en cuenta que no se produce ninguna ejecución durante la construcción de la canalización.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-237">Note that no execution happens during pipeline construction.</span></span> <span data-ttu-id="6dcb0-238">Se crean los objetos del estimador, pero no se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-238">The estimator objects are created but not executed.</span></span>

1. <span data-ttu-id="6dcb0-239">Agregue un método para generar el modelo</span><span class="sxs-lookup"><span data-stu-id="6dcb0-239">Add a method to generate the model</span></span>

    <span data-ttu-id="6dcb0-240">Este método es la parte central del tutorial.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-240">This method is the heart of the tutorial.</span></span> <span data-ttu-id="6dcb0-241">Crea una canalización para el modelo y entrena la canalización para generar el modelo de ML.NET.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-241">It creates a pipeline for the model, and trains the pipeline to produce the ML.NET model.</span></span> <span data-ttu-id="6dcb0-242">También evalúa el modelo con respecto a algunos datos de prueba previamente desconocidos.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-242">It also evaluates the model against some previously unseen test data.</span></span>

    <span data-ttu-id="6dcb0-243">Cree el método `GenerateModel()` justo después de la estructura `InceptionSettings` y antes del método `DisplayResults()` con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-243">Create the `GenerateModel()` method, just after the `InceptionSettings` struct and just before the `DisplayResults()` method, using the following code:</span></span>

    ```csharp
    public static ITransformer GenerateModel(MLContext mlContext)
    {

    }
    ```

1. <span data-ttu-id="6dcb0-244">Agregue los estimadores para cargar, cambiar el tamaño y extraer los píxeles de los datos de la imagen:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-244">Add the estimators to load, resize and extract the pixels from the image data:</span></span>

    [!code-csharp[ImageTransforms](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ImageTransforms)]

    <span data-ttu-id="6dcb0-245">Los datos de la imagen se deben procesar en el formato que el modelo de TensorFlow espera.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-245">The image data needs to be processed into the format that the TensorFlow model expects.</span></span> <span data-ttu-id="6dcb0-246">En este caso, las imágenes se cargan en la memoria, se cambia el tamaño a un tamaño coherente y los píxeles se extraen en un vector numérico.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-246">In this case, the images are loaded into memory, resized to a consistent size, and the pixels are extracted into a numeric vector.</span></span>

1. <span data-ttu-id="6dcb0-247">Agregue el estimador para cargar el modelo de TensorFlow y puntúelo:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-247">Add the estimator to load the TensorFlow model, and score it:</span></span>

    [!code-csharp[ScoreTensorFlowModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ScoreTensorFlowModel)]

    <span data-ttu-id="6dcb0-248">Esta fase de la canalización carga el modelo de TensorFlow en la memoria y, a continuación, procesa el vector de valores de píxeles a través de la red del modelo de TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-248">This stage in the pipeline loads the TensorFlow model into memory, then processes the vector of pixel values through the TensorFlow model network.</span></span> <span data-ttu-id="6dcb0-249">La aplicación de entradas a un modelo de aprendizaje profundo y la generación de una salida mediante el modelo se conoce como **Puntuación**.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-249">Applying inputs to a deep learning model, and generating an output using the model, is referred to as **Scoring**.</span></span> <span data-ttu-id="6dcb0-250">Al utilizar el modelo en su totalidad, la puntuación hace una inferencia o predicción.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-250">When using the model in its entirety, scoring makes an inference, or prediction.</span></span> 

    <span data-ttu-id="6dcb0-251">En este caso, se usa todo el modelo de TensorFlow, excepto la última capa, que es la que realiza la inferencia.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-251">In this case, you use all of the TensorFlow model except the last layer, which is the layer that makes the inference.</span></span> <span data-ttu-id="6dcb0-252">El resultado de la penúltima capa tiene la etiqueta `softmax_2_preactivation`.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-252">The output of the penultimate layer is labeled `softmax_2_preactivation`.</span></span> <span data-ttu-id="6dcb0-253">La salida de esta capa es, de hecho, un vector de las características que caracterizan las imágenes de entrada originales.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-253">The output of this layer is effectively a vector of features that characterize the original input images.</span></span>

    <span data-ttu-id="6dcb0-254">Este vector de características generado por el modelo de TensorFlow se usará como entrada para un algoritmo de aprendizaje de ML.NET.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-254">This feature vector generated by the TensorFlow model will be used as input to an ML.NET training algorithm.</span></span>

1. <span data-ttu-id="6dcb0-255">Agregue el estimador para asignar las etiquetas de cadena en los datos de entrenamiento a los valores de clave entera:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-255">Add the estimator to map the string labels in the training data to integer key values:</span></span>

    [!code-csharp[MapValueToKey](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapValueToKey)]

    <span data-ttu-id="6dcb0-256">El entrenador de ML.NET que se anexa a continuación requiere que sus etiquetas estén en formato `key` en lugar de cadenas arbitrarias.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-256">The ML.NET trainer that is appended next requires its labels to be in `key` format rather than arbitrary strings.</span></span> <span data-ttu-id="6dcb0-257">Una clave es un número que tiene una asignación de uno a uno a un valor de cadena.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-257">A key is a number that has a one to one mapping to a string value.</span></span>

1. <span data-ttu-id="6dcb0-258">Agregue el algoritmo de aprendizaje de ML.NET:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-258">Add the ML.NET training algorithm:</span></span>

    [!code-csharp[AddTrainer](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddTrainer)]

1. <span data-ttu-id="6dcb0-259">Agregue el estimador para asignar el valor de clave de predicción a una cadena:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-259">Add the estimator to map the predicted key value back into a string:</span></span>

    [!code-csharp[MapKeyToValue](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapKeyToValue)]

## <a name="train-the-model"></a><span data-ttu-id="6dcb0-260">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="6dcb0-260">Train the model</span></span>

1. <span data-ttu-id="6dcb0-261">Cargue los datos de entrenamiento con el contenedor [LoadFromTextFile](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile(Microsoft.ML.DataOperationsCatalog,System.String,Microsoft.ML.Data.TextLoader.Options)).</span><span class="sxs-lookup"><span data-stu-id="6dcb0-261">Load the training data using the [LoadFromTextFile](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile(Microsoft.ML.DataOperationsCatalog,System.String,Microsoft.ML.Data.TextLoader.Options)) wrapper.</span></span> <span data-ttu-id="6dcb0-262">Agregue el siguiente código como la siguiente línea en el método `GenerateModel()`:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-262">Add the following code as the next line in the `GenerateModel()` method:</span></span>

    [!code-csharp[LoadData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadData "Load the data")]

    <span data-ttu-id="6dcb0-263">Los datos de ML.NET se representan como una [clase IDataView](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="6dcb0-263">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="6dcb0-264">`IDataView` es una manera flexible y eficiente de describir datos tabulares (numéricos y de texto).</span><span class="sxs-lookup"><span data-stu-id="6dcb0-264">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="6dcb0-265">Los datos se pueden cargar desde un archivo de texto o en tiempo real (por ejemplo, archivos de registro o base de datos SQL) en un objeto `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-265">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

1. <span data-ttu-id="6dcb0-266">Entrene el modelo con los datos cargados anteriormente:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-266">Train the model with the data loaded above:</span></span>

    [!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#TrainModel)]

    <span data-ttu-id="6dcb0-267">El método `Fit()` entrena el modelo mediante la aplicación del conjunto de datos de entrenamiento a la canalización.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-267">The `Fit()` method trains your model by applying the training dataset to the pipeline.</span></span>

## <a name="evaluate-the-accuracy-of-the-model"></a><span data-ttu-id="6dcb0-268">Evaluación de la precisión del modelo</span><span class="sxs-lookup"><span data-stu-id="6dcb0-268">Evaluate the accuracy of the model</span></span>

1. <span data-ttu-id="6dcb0-269">Cargue y transforme los datos de prueba agregando el código siguiente a la siguiente línea del método `GenerateModel`:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-269">Load and transform the test data, by adding the following code to the next line of the `GenerateModel` method:</span></span>

    [!code-csharp[LoadAndTransformTestData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadAndTransformTestData "Load and transform test data")]

    <span data-ttu-id="6dcb0-270">Hay algunas imágenes de ejemplo que puede usar para evaluar el modelo.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-270">There are a few sample images that you can use to evaluate the model.</span></span> <span data-ttu-id="6dcb0-271">Al igual que los datos de entrenamiento, deben cargarse en `IDataView`, de modo que el modelo pueda transformarlos.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-271">Like the training data, these need to be loaded into an `IDataView`, so that they can be transformed by the model.</span></span>
   
1. <span data-ttu-id="6dcb0-272">Agregue el código siguiente al método `GenerateModel()` para evaluar el modelo:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-272">Add the following code to the `GenerateModel()` method to evaluate the model:</span></span>

    [!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#Evaluate)]

    <span data-ttu-id="6dcb0-273">Una vez que establece la predicción, el método [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A):</span><span class="sxs-lookup"><span data-stu-id="6dcb0-273">Once you have the prediction set, the [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) method:</span></span>

    * <span data-ttu-id="6dcb0-274">Evalúa el modelo (compara los valores previstos con el conjunto de datos `labels` de prueba).</span><span class="sxs-lookup"><span data-stu-id="6dcb0-274">Assesses the model (compares the predicted values with the test dataset `labels`).</span></span>
    * <span data-ttu-id="6dcb0-275">Devuelve las métricas de rendimiento del modelo.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-275">Returns the model performance metrics.</span></span>

1. <span data-ttu-id="6dcb0-276">Visualización de las métricas de precisión del modelo</span><span class="sxs-lookup"><span data-stu-id="6dcb0-276">Display the model accuracy metrics</span></span>

    <span data-ttu-id="6dcb0-277">Utilice el código siguiente para mostrar las métricas, compartir los resultados y, a continuación, trabajar con ellos:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-277">Use the following code to display the metrics, share the results, and then act on them:</span></span>

    [!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayMetrics)]

    <span data-ttu-id="6dcb0-278">Las siguiente métricas se evalúan para la clasificación de imágenes:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-278">The following metrics are evaluated for image classification:</span></span>

    * <span data-ttu-id="6dcb0-279">`Log-loss`: consulte [Pérdida de registro](../resources/glossary.md#log-loss).</span><span class="sxs-lookup"><span data-stu-id="6dcb0-279">`Log-loss` - see [Log Loss](../resources/glossary.md#log-loss).</span></span> <span data-ttu-id="6dcb0-280">Le recomendamos que la pérdida logarítmica esté lo más cerca posible de 0.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-280">You want Log-loss to be as close to zero as possible.</span></span>
    * <span data-ttu-id="6dcb0-281">`Per class Log-loss`.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-281">`Per class Log-loss`.</span></span> <span data-ttu-id="6dcb0-282">Le recomendamos que la pérdida logarítmica por clase esté lo más cerca posible de 0.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-282">You want per class Log-loss to be as close to zero as possible.</span></span>

1. <span data-ttu-id="6dcb0-283">Agregue el siguiente código para devolver el modelo entrenado, como la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-283">Add the following code to return the trained model as the next line:</span></span>

    [!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReturnModel)]

## <a name="run-the-application"></a><span data-ttu-id="6dcb0-284">Ejecución de la aplicación</span><span class="sxs-lookup"><span data-stu-id="6dcb0-284">Run the application!</span></span>

1. <span data-ttu-id="6dcb0-285">Agregue la llamada a `GenerateModel` en el método `Main` después de la creación de la clase MLContext:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-285">Add the call to `GenerateModel` in the `Main` method after the creation of the MLContext class:</span></span>

    [!code-csharp[CallGenerateModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallGenerateModel)]

1. <span data-ttu-id="6dcb0-286">Agregue la llamada al método `ClassifySingleImage()` como la siguiente línea de código en el método `Main`:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-286">Add the call to the `ClassifySingleImage()` method as the next line of code in the `Main` method:</span></span>

    [!code-csharp[CallClassifySingleImage](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallClassifySingleImage)]

1. <span data-ttu-id="6dcb0-287">Ejecute la aplicación de consola (Ctrl + F5).</span><span class="sxs-lookup"><span data-stu-id="6dcb0-287">Run your console app (Ctrl + F5).</span></span> <span data-ttu-id="6dcb0-288">Los resultados deberían ser similares a la salida siguiente.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-288">Your results should be similar to the following output.</span></span>  <span data-ttu-id="6dcb0-289">Es posible que vea advertencias o mensajes de procesamiento, si bien se han quitado de los resultados siguientes para mayor claridad.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-289">You may see warnings or processing messages, but these messages have been removed from the following results for clarity.</span></span>

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
    =============== Making single image classification ===============
    Image: toaster3.jpg predicted as: appliance with score: 0.9625379

    C:\Program Files\dotnet\dotnet.exe (process 4304) exited with code 0.
    Press any key to close this window . . .
    ```

<span data-ttu-id="6dcb0-290">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="6dcb0-290">Congratulations!</span></span> <span data-ttu-id="6dcb0-291">Ha creado correctamente un modelo de Machine Learning para la clasificación de imágenes al aplicar el aprendizaje de transferencia a un modelo de `TensorFlow` en ML.NET.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-291">You've now successfully built a machine learning model for image classification by applying transfer learning to a `TensorFlow` model in ML.NET.</span></span>

<span data-ttu-id="6dcb0-292">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF).</span><span class="sxs-lookup"><span data-stu-id="6dcb0-292">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) repository.</span></span>

<span data-ttu-id="6dcb0-293">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="6dcb0-293">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="6dcb0-294">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="6dcb0-294">Understand the problem</span></span>
> * <span data-ttu-id="6dcb0-295">Incorporación del modelo de TensorFlow entrenado previamente en la canalización de ML.NET</span><span class="sxs-lookup"><span data-stu-id="6dcb0-295">Incorporate the pre-trained TensorFlow model into the ML.NET pipeline</span></span>
> * <span data-ttu-id="6dcb0-296">Entrenamiento y evaluación del modelo de ML.NET</span><span class="sxs-lookup"><span data-stu-id="6dcb0-296">Train and evaluate the ML.NET model</span></span>
> * <span data-ttu-id="6dcb0-297">Clasificación de una imagen de prueba</span><span class="sxs-lookup"><span data-stu-id="6dcb0-297">Classify a test image</span></span>

<span data-ttu-id="6dcb0-298">Consulte el repositorio de GitHub con ejemplos de Machine Learning para explorar un ejemplo expandido de clasificación de imágenes.</span><span class="sxs-lookup"><span data-stu-id="6dcb0-298">Check out the Machine Learning samples GitHub repository to explore an expanded image classification sample.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="6dcb0-299">Repositorio dotnet/machinelearning-samples de GitHub</span><span class="sxs-lookup"><span data-stu-id="6dcb0-299">dotnet/machinelearning-samples GitHub repository</span></span>](https://github.com/dotnet/machinelearning-samples/)
