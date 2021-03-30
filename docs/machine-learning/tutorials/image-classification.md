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
# <a name="tutorial-generate-an-mlnet-image-classification-model-from-a-pre-trained-tensorflow-model"></a><span data-ttu-id="00966-105">Tutorial: Generación de un modelo de clasificación de imágenes de ML.NET desde un modelo entrenado previamente de TensorFlow</span><span class="sxs-lookup"><span data-stu-id="00966-105">Tutorial: Generate an ML.NET image classification model from a pre-trained TensorFlow model</span></span>

<span data-ttu-id="00966-106">Obtenga información sobre cómo transferir el conocimiento de un modelo de TensorFlow existente a un modelo de clasificación de imágenes de ML.NET nuevo.</span><span class="sxs-lookup"><span data-stu-id="00966-106">Learn how to transfer the knowledge from an existing TensorFlow model into a new ML.NET image classification model.</span></span>

<span data-ttu-id="00966-107">El modelo de TensorFlow se entrenó para clasificar las imágenes en mil categorías.</span><span class="sxs-lookup"><span data-stu-id="00966-107">The TensorFlow model was trained to classify images into a thousand categories.</span></span> <span data-ttu-id="00966-108">El modelo de ML.NET usa parte del modelo de TensorFlow en su canalización para entrenar un modelo con el fin de clasificar las imágenes en 3 categorías.</span><span class="sxs-lookup"><span data-stu-id="00966-108">The ML.NET model makes use of part of the TensorFlow model in its pipeline to train a model to classify images into 3 categories.</span></span>

<span data-ttu-id="00966-109">Entrenar un modelo de [clasificación de imágenes](https://en.wikipedia.org/wiki/Outline_of_object_recognition) desde cero requiere establecer millones de parámetros, una enorme cantidad de datos de aprendizaje etiquetados y una gran cantidad de recursos informáticos (cientos de horas de GPU).</span><span class="sxs-lookup"><span data-stu-id="00966-109">Training an [Image Classification](https://en.wikipedia.org/wiki/Outline_of_object_recognition) model from scratch requires setting millions of parameters, a ton of labeled training data and a vast amount of compute resources (hundreds of GPU hours).</span></span> <span data-ttu-id="00966-110">Si bien no es tan eficaz como entrenar un modelo personalizado desde cero, el aprendizaje por transferencia permite acortar este proceso al trabajar con miles de imágenes frente a millones de imágenes etiquetadas y crear un modelo personalizado con bastante rapidez (menos de una hora en una máquina sin GPU).</span><span class="sxs-lookup"><span data-stu-id="00966-110">While not as effective as training a custom model from scratch, transfer learning allows you to shortcut this process by working with thousands of images vs. millions of labeled images and build a customized model fairly quickly (within an hour on a machine without a GPU).</span></span> <span data-ttu-id="00966-111">En este tutorial se amplía aún más ese proceso, con solo una docena de imágenes de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="00966-111">This tutorial scales that process down even further, using only a dozen training images.</span></span>

<span data-ttu-id="00966-112">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="00966-112">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="00966-113">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="00966-113">Understand the problem</span></span>
> * <span data-ttu-id="00966-114">Incorporación del modelo de TensorFlow entrenado previamente en la canalización de ML.NET</span><span class="sxs-lookup"><span data-stu-id="00966-114">Incorporate the pre-trained TensorFlow model into the ML.NET pipeline</span></span>
> * <span data-ttu-id="00966-115">Entrenamiento y evaluación del modelo de ML.NET</span><span class="sxs-lookup"><span data-stu-id="00966-115">Train and evaluate the ML.NET model</span></span>
> * <span data-ttu-id="00966-116">Clasificación de una imagen de prueba</span><span class="sxs-lookup"><span data-stu-id="00966-116">Classify a test image</span></span>

<span data-ttu-id="00966-117">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/main/machine-learning/tutorials/TransferLearningTF).</span><span class="sxs-lookup"><span data-stu-id="00966-117">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/main/machine-learning/tutorials/TransferLearningTF) repository.</span></span> <span data-ttu-id="00966-118">Tenga en cuenta que, de forma predeterminada, la configuración del proyecto de .NET de este tutorial tiene como destino .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="00966-118">Note that by default, the .NET project configuration for this tutorial targets .NET core 2.2.</span></span>

## <a name="what-is-transfer-learning"></a><span data-ttu-id="00966-119">¿Qué es el aprendizaje de transferencia?</span><span class="sxs-lookup"><span data-stu-id="00966-119">What is transfer learning?</span></span>

<span data-ttu-id="00966-120">El aprendizaje de transferencia es el proceso de usar los conocimientos adquiridos al resolver un problema y aplicarlos a un problema distinto, pero relacionado.</span><span class="sxs-lookup"><span data-stu-id="00966-120">Transfer learning is the process of using knowledge gained while solving one problem and applying it to a different but related problem.</span></span>

<span data-ttu-id="00966-121">En este tutorial, usará parte de un modelo de TensorFlow (entrenado para clasificar las imágenes en mil categorías) en un modelo de ML.NET que clasifica las imágenes en 3 categorías.</span><span class="sxs-lookup"><span data-stu-id="00966-121">For this tutorial, you use part of a TensorFlow model - trained to classify images into a thousand categories - in an ML.NET model that classifies images into 3 categories.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="00966-122">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="00966-122">Prerequisites</span></span>

* <span data-ttu-id="00966-123">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o posterior, o bien Visual Studio 2017 versión 15.6 o posterior con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.</span><span class="sxs-lookup"><span data-stu-id="00966-123">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or later or Visual Studio 2017 version 15.6 or later with the ".NET Core cross-platform development" workload installed.</span></span>
* [<span data-ttu-id="00966-124">El archivo ZIP del directorio de recursos del tutorial</span><span class="sxs-lookup"><span data-stu-id="00966-124">The tutorial assets directory .ZIP file</span></span>](https://github.com/dotnet/samples/blob/main/machine-learning/tutorials/TransferLearningTF/image-classifier-assets.zip)
* [<span data-ttu-id="00966-125">El modelo de Machine Learning de InceptionV1</span><span class="sxs-lookup"><span data-stu-id="00966-125">The InceptionV1 machine learning model</span></span>](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)

## <a name="select-the-right-machine-learning-task"></a><span data-ttu-id="00966-126">Selección de la tarea de aprendizaje automático adecuada</span><span class="sxs-lookup"><span data-stu-id="00966-126">Select the right machine learning task</span></span>

### <a name="deep-learning"></a><span data-ttu-id="00966-127">Aprendizaje profundo</span><span class="sxs-lookup"><span data-stu-id="00966-127">Deep learning</span></span>

<span data-ttu-id="00966-128">El [aprendizaje profundo](https://en.wikipedia.org/wiki/Deep_learning) es un subconjunto de Machine Learning, que está revolucionando áreas como Computer Vision y reconocimiento de voz.</span><span class="sxs-lookup"><span data-stu-id="00966-128">[Deep learning](https://en.wikipedia.org/wiki/Deep_learning) is a subset of Machine Learning, which is revolutionizing areas like Computer Vision and Speech Recognition.</span></span>

<span data-ttu-id="00966-129">Los modelos de aprendizaje profundo se entrenan mediante el uso de grandes conjuntos de [datos etiquetados](https://en.wikipedia.org/wiki/Labeled_data) y [redes neuronales](https://en.wikipedia.org/wiki/Artificial_neural_network) que contienen varias capas de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="00966-129">Deep learning models are trained by using large sets of [labeled data](https://en.wikipedia.org/wiki/Labeled_data) and [neural networks](https://en.wikipedia.org/wiki/Artificial_neural_network) that contain multiple learning layers.</span></span> <span data-ttu-id="00966-130">Aprendizaje profundo:</span><span class="sxs-lookup"><span data-stu-id="00966-130">Deep learning:</span></span>

* <span data-ttu-id="00966-131">Funciona mejor en algunas tareas como Computer Vision.</span><span class="sxs-lookup"><span data-stu-id="00966-131">Performs better on some tasks like Computer Vision.</span></span>
* <span data-ttu-id="00966-132">Requiere enormes cantidades de datos de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="00966-132">Requires huge amounts of training data.</span></span>

<span data-ttu-id="00966-133">La clasificación de imágenes es una tarea de Machine Learning común que nos permite clasificar imágenes automáticamente en categorías como:</span><span class="sxs-lookup"><span data-stu-id="00966-133">Image Classification is a common Machine Learning task that allows us to automatically classify images into categories such as:</span></span>

* <span data-ttu-id="00966-134">Detectar o no una cara humana en una imagen.</span><span class="sxs-lookup"><span data-stu-id="00966-134">Detecting a human face in an image or not.</span></span>
* <span data-ttu-id="00966-135">Detectar gatos o perros.</span><span class="sxs-lookup"><span data-stu-id="00966-135">Detecting cats vs. dogs.</span></span>

 <span data-ttu-id="00966-136">O bien, como en las imágenes siguientes, determinar si una imagen es un alimento, un juguete o un dispositivo:</span><span class="sxs-lookup"><span data-stu-id="00966-136">Or as in the following images, determining if an image is a(n)  food, toy, or appliance:</span></span>

<span data-ttu-id="00966-137">![imagen de una pizza](./media/image-classification/220px-Pepperoni_pizza.jpg)
![imagen de un oso de peluche](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![imagen de una tostadora](./media/image-classification/193px-Broodrooster.jpg)</span><span class="sxs-lookup"><span data-stu-id="00966-137">![pizza image](./media/image-classification/220px-Pepperoni_pizza.jpg)
![teddy bear image](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![toaster image](./media/image-classification/193px-Broodrooster.jpg)</span></span>

>[!Note]
> <span data-ttu-id="00966-138">Las imágenes anteriores pertenecen a Wikimedia Commons y tienen los siguientes atributos:</span><span class="sxs-lookup"><span data-stu-id="00966-138">The preceding images belong to Wikimedia Commons and are attributed as follows:</span></span>
>
> * <span data-ttu-id="00966-139">"220px-Pepperoni_pizza.jpg" de dominio público, <https://commons.wikimedia.org/w/index.php?curid=79505>,</span><span class="sxs-lookup"><span data-stu-id="00966-139">"220px-Pepperoni_pizza.jpg" Public Domain, <https://commons.wikimedia.org/w/index.php?curid=79505>,</span></span>
> * <span data-ttu-id="00966-140">"119px-Nalle_-_a_small_brown_teddy_bear.jpg" de [Jonik](https://commons.wikimedia.org/wiki/User:Jonik), autofotografía, CC BY-SA 2.0, <https://commons.wikimedia.org/w/index.php?curid=48166>.</span><span class="sxs-lookup"><span data-stu-id="00966-140">"119px-Nalle_-_a_small_brown_teddy_bear.jpg" By [Jonik](https://commons.wikimedia.org/wiki/User:Jonik) - Self-photographed, CC BY-SA 2.0, <https://commons.wikimedia.org/w/index.php?curid=48166>.</span></span>
> * <span data-ttu-id="00966-141">"193px-Broodrooster.jpg" de [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972), trabajo propio, CC BY-SA 3.0, <https://commons.wikimedia.org/w/index.php?curid=27403></span><span class="sxs-lookup"><span data-stu-id="00966-141">"193px-Broodrooster.jpg" By [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972) - Own work, CC BY-SA 3.0, <https://commons.wikimedia.org/w/index.php?curid=27403></span></span>

<span data-ttu-id="00966-142">`Inception model` está entrenado para clasificar imágenes en miles de categorías, pero, en este tutorial, el usuario deberá clasificar las imágenes en un conjunto de categorías más pequeño y solo en esas categorías.</span><span class="sxs-lookup"><span data-stu-id="00966-142">The `Inception model` is trained to classify images into a thousand categories, but for this tutorial, you need to classify images in a smaller category set, and only those categories.</span></span> <span data-ttu-id="00966-143">Escriba la parte `transfer` de `transfer learning`.</span><span class="sxs-lookup"><span data-stu-id="00966-143">Enter the `transfer` part of `transfer learning`.</span></span> <span data-ttu-id="00966-144">Puede transferir la capacidad que `Inception model` tiene para reconocer y clasificar imágenes a las nuevas categorías limitadas del clasificador personalizado de imágenes.</span><span class="sxs-lookup"><span data-stu-id="00966-144">You can transfer the `Inception model`'s ability to recognize and classify images to the new limited categories of your custom image classifier.</span></span>

* <span data-ttu-id="00966-145">Alimentos</span><span class="sxs-lookup"><span data-stu-id="00966-145">Food</span></span>
* <span data-ttu-id="00966-146">Juguetes</span><span class="sxs-lookup"><span data-stu-id="00966-146">Toy</span></span>
* <span data-ttu-id="00966-147">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="00966-147">Appliance</span></span>

<span data-ttu-id="00966-148">En este tutorial se usa el modelo de aprendizaje profundo del [modelo de inicio](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) de TensorFlow, un modelo de reconocimiento de imágenes popular entrenado en el conjunto de datos `ImageNet`.</span><span class="sxs-lookup"><span data-stu-id="00966-148">This tutorial uses the TensorFlow [Inception model](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) deep learning model, a popular image recognition model trained on the `ImageNet` dataset.</span></span> <span data-ttu-id="00966-149">El modelo de TensorFlow clasifica imágenes completas en miles de clases como "Paraguas", "Jersey" y "Lavavajillas".</span><span class="sxs-lookup"><span data-stu-id="00966-149">The TensorFlow model classifies entire images into a thousand classes, such as “Umbrella”, “Jersey”, and “Dishwasher”.</span></span>

<span data-ttu-id="00966-150">Como `Inception model` se entrenó previamente en miles de imágenes distintas, contiene internamente las [características de imagen](https://en.wikipedia.org/wiki/Feature_(computer_vision)) necesarias para la identificación de imágenes.</span><span class="sxs-lookup"><span data-stu-id="00966-150">Because the `Inception model` has already been pre trained on thousands of different images, internally it contains the [image features](https://en.wikipedia.org/wiki/Feature_(computer_vision)) needed for image identification.</span></span> <span data-ttu-id="00966-151">Podemos usar estas características de imagen internas en el modelo para entrenar un modelo nuevo con muchas menos clases.</span><span class="sxs-lookup"><span data-stu-id="00966-151">We can make use of these internal image features in the model to train a new model with far fewer classes.</span></span>

<span data-ttu-id="00966-152">Como se muestra en el diagrama siguiente, puede agregar una referencia a los paquetes NuGet de ML.NET en las aplicaciones de .NET Core o .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="00966-152">As shown in the following diagram, you add a reference to the ML.NET NuGet packages in your .NET Core or .NET Framework applications.</span></span> <span data-ttu-id="00966-153">En segundo plano, ML.NET incluye y hace referencia a la biblioteca nativa de `TensorFlow` que permite escribir código que carga un archivo de modelo de `TensorFlow` entrenado existente.</span><span class="sxs-lookup"><span data-stu-id="00966-153">Under the covers, ML.NET includes and references the native `TensorFlow` library that allows you to write code that loads an existing trained `TensorFlow` model file.</span></span>

![Diagrama de la arquitectura de ML.NET de transformación de TensorFlow](./media/image-classification/tensorflow-mlnet.png)

### <a name="multiclass-classification"></a><span data-ttu-id="00966-155">Clasificación multiclase</span><span class="sxs-lookup"><span data-stu-id="00966-155">Multiclass classification</span></span>

<span data-ttu-id="00966-156">Después de usar el modelo de inicio de TensorFlow para extraer características adecuadas como entrada para un algoritmo de aprendizaje automático clásico, se agrega un [clasificador multiclase](../resources/tasks.md#multiclass-classification) de ML.NET.</span><span class="sxs-lookup"><span data-stu-id="00966-156">After using the TensorFlow inception model to extract features suitable as input for a classical machine learning algorithm, we add an ML.NET [multi-class classifier](../resources/tasks.md#multiclass-classification).</span></span>

<span data-ttu-id="00966-157">El entrenador específico que se usa en este caso es el [algoritmo de regresión logística multinomial](https://en.wikipedia.org/wiki/Multinomial_logistic_regression).</span><span class="sxs-lookup"><span data-stu-id="00966-157">The specific trainer used in this case is the [multinomial logistic regression algorithm](https://en.wikipedia.org/wiki/Multinomial_logistic_regression).</span></span>

<span data-ttu-id="00966-158">El algoritmo que implementa este entrenador funciona con un gran número de características, que es el caso de un modelo de aprendizaje profundo que funciona con datos de imagen.</span><span class="sxs-lookup"><span data-stu-id="00966-158">The algorithm implemented by this trainer performs well on problems with a large number of features, which is the case for a deep learning model operating on image data.</span></span>

### <a name="data"></a><span data-ttu-id="00966-159">Datos</span><span class="sxs-lookup"><span data-stu-id="00966-159">Data</span></span>

<span data-ttu-id="00966-160">Hay dos orígenes de datos: el archivo `.tsv` y los archivos de imagen.</span><span class="sxs-lookup"><span data-stu-id="00966-160">There are two data sources: the `.tsv` file, and the image files.</span></span>  <span data-ttu-id="00966-161">El archivo `tags.tsv` contiene dos columnas: la primera está definida como `ImagePath` y la segunda es la `Label` que corresponde a la imagen.</span><span class="sxs-lookup"><span data-stu-id="00966-161">The `tags.tsv` file contains two columns: the first one is defined as `ImagePath` and the second one is the `Label` corresponding to the image.</span></span> <span data-ttu-id="00966-162">El archivo de ejemplo siguiente no tiene una fila de encabezado y se ve así:</span><span class="sxs-lookup"><span data-stu-id="00966-162">The following example file doesn't have a header row, and looks like this:</span></span>

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

<span data-ttu-id="00966-163">Las imágenes de entrenamiento y prueba se encuentran en las carpetas de recursos que descargará en un archivo ZIP.</span><span class="sxs-lookup"><span data-stu-id="00966-163">The training and testing images are located in the assets folders that you'll download in a zip file.</span></span> <span data-ttu-id="00966-164">Estas imágenes pertenecen a Wikimedia Commons.</span><span class="sxs-lookup"><span data-stu-id="00966-164">These images belong to Wikimedia Commons.</span></span>
> <span data-ttu-id="00966-165">*[Wikimedia Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), el repositorio multimedia gratuito*.</span><span class="sxs-lookup"><span data-stu-id="00966-165">*[Wikimedia Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), the free media repository.*</span></span> <span data-ttu-id="00966-166">Recuperado a las 10:48 del 17 de octubre de 2018 desde: <https://commons.wikimedia.org/wiki/Pizza>
> <https://commons.wikimedia.org/wiki/Toaster>
> <https://commons.wikimedia.org/wiki/Teddy_bear></span><span class="sxs-lookup"><span data-stu-id="00966-166">Retrieved 10:48, October 17, 2018 from: <https://commons.wikimedia.org/wiki/Pizza>
> <https://commons.wikimedia.org/wiki/Toaster>
<https://commons.wikimedia.org/wiki/Teddy_bear></span></span>

## <a name="setup"></a><span data-ttu-id="00966-167">Programa de instalación</span><span class="sxs-lookup"><span data-stu-id="00966-167">Setup</span></span>

### <a name="create-a-project"></a><span data-ttu-id="00966-168">Crear un proyecto</span><span class="sxs-lookup"><span data-stu-id="00966-168">Create a project</span></span>

1. <span data-ttu-id="00966-169">Cree una **aplicación de consola de .NET Core** denominada "TransferLearningTF".</span><span class="sxs-lookup"><span data-stu-id="00966-169">Create a **.NET Core Console Application** called "TransferLearningTF".</span></span>

1. <span data-ttu-id="00966-170">Instale el **paquete NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="00966-170">Install the **Microsoft.ML NuGet Package**:</span></span>

    [!INCLUDE [mlnet-current-nuget-version](../../../includes/mlnet-current-nuget-version.md)]

    * <span data-ttu-id="00966-171">En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="00966-171">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span>
    * <span data-ttu-id="00966-172">Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar y busque **Microsoft.ML**.</span><span class="sxs-lookup"><span data-stu-id="00966-172">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**.</span></span>
    * <span data-ttu-id="00966-173">Seleccione el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="00966-173">Select the **Install** button.</span></span>
    * <span data-ttu-id="00966-174">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de los cambios**.</span><span class="sxs-lookup"><span data-stu-id="00966-174">Select the **OK** button on the **Preview Changes** dialog.</span></span>
    * <span data-ttu-id="00966-175">Haga clic en el botón **Acepto** en el cuadro de diálogo **Aceptación de la licencia** si está de acuerdo con los términos de licencia de los paquetes que aparecen.</span><span class="sxs-lookup"><span data-stu-id="00966-175">Select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>
    * <span data-ttu-id="00966-176">Repita estos pasos para **Microsoft.ML.ImageAnalytics**, **SciSharp.TensorFlow.Redist** y **Microsoft.ML.TensorFlow**.</span><span class="sxs-lookup"><span data-stu-id="00966-176">Repeat these steps for **Microsoft.ML.ImageAnalytics**, **SciSharp.TensorFlow.Redist** and **Microsoft.ML.TensorFlow**.</span></span>

### <a name="download-assets"></a><span data-ttu-id="00966-177">Descarga de activos</span><span class="sxs-lookup"><span data-stu-id="00966-177">Download assets</span></span>

1. <span data-ttu-id="00966-178">Descargue el [archivo ZIP del directorio de recursos del proyecto](https://github.com/dotnet/samples/blob/main/machine-learning/tutorials/TransferLearningTF/image-classifier-assets.zip) y descomprímalo.</span><span class="sxs-lookup"><span data-stu-id="00966-178">Download [The project assets directory zip file](https://github.com/dotnet/samples/blob/main/machine-learning/tutorials/TransferLearningTF/image-classifier-assets.zip), and unzip.</span></span>

1. <span data-ttu-id="00966-179">Copie el directorio `assets` en el directorio de proyecto *TransferLearningTF*.</span><span class="sxs-lookup"><span data-stu-id="00966-179">Copy the `assets` directory into your *TransferLearningTF* project directory.</span></span> <span data-ttu-id="00966-180">Este directorio y sus subdirectorios contienen los datos y los archivos auxiliares (excepto los del modelo de inicio, que descargará y agregará en el paso siguiente) que se necesitan en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="00966-180">This directory and its subdirectories contain the data and support files (except for the Inception model, which you'll download and add in the next step) needed for this tutorial.</span></span>

1. <span data-ttu-id="00966-181">Descargue el [modelo de inicio](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) y descomprímalo.</span><span class="sxs-lookup"><span data-stu-id="00966-181">Download the [Inception model](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip), and unzip.</span></span>

1. <span data-ttu-id="00966-182">Copie el contenido del directorio `inception5h` que acaba de descomprimir en el directorio `assets/inception` del proyecto *TransferLearningTF*.</span><span class="sxs-lookup"><span data-stu-id="00966-182">Copy the contents of the `inception5h` directory just unzipped into your *TransferLearningTF* project `assets/inception` directory.</span></span> <span data-ttu-id="00966-183">En este directorio está el modelo y los archivos auxiliares adicionales que se necesitan en este tutorial, tal como se muestra en la imagen siguiente:</span><span class="sxs-lookup"><span data-stu-id="00966-183">This directory contains the model and additional support files needed for this tutorial, as shown in the following image:</span></span>

   ![Contenido del directorio de inicio](./media/image-classification/inception-files.png)

1. <span data-ttu-id="00966-185">En el Explorador de soluciones, haga clic con el botón derecho en cada uno de los archivos del directorio de recursos y los subdirectorios y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="00966-185">In Solution Explorer, right-click each of the files in the asset directory and subdirectories and select **Properties**.</span></span> <span data-ttu-id="00966-186">En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.</span><span class="sxs-lookup"><span data-stu-id="00966-186">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="00966-187">Crear clases y definir rutas de acceso</span><span class="sxs-lookup"><span data-stu-id="00966-187">Create classes and define paths</span></span>

1. <span data-ttu-id="00966-188">Agregue las siguientes instrucciones `using` adicionales a la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="00966-188">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

    [!code-csharp[AddUsings](./snippets/image-classification/csharp/Program.cs#AddUsings)]

1. <span data-ttu-id="00966-189">Agregue el código siguiente a la línea inmediatamente por encima del método `Main` para especificar las rutas de acceso a los recursos:</span><span class="sxs-lookup"><span data-stu-id="00966-189">Add the following code to the line right above the `Main` method to specify the asset paths:</span></span>

    [!code-csharp[DeclareGlobalVariables](./snippets/image-classification/csharp/Program.cs#DeclareGlobalVariables)]

1. <span data-ttu-id="00966-190">Cree clases para los datos de entrada y las predicciones.</span><span class="sxs-lookup"><span data-stu-id="00966-190">Create classes for your input data, and predictions.</span></span>

    [!code-csharp[DeclareImageData](./snippets/image-classification/csharp/Program.cs#DeclareImageData)]

    <span data-ttu-id="00966-191">`ImageData` es la clase de datos de imagen de entrada y tiene los campos <xref:System.String> siguientes:</span><span class="sxs-lookup"><span data-stu-id="00966-191">`ImageData` is the input image data class and has the following <xref:System.String> fields:</span></span>

    * <span data-ttu-id="00966-192">`ImagePath` contiene el nombre del archivo de imagen.</span><span class="sxs-lookup"><span data-stu-id="00966-192">`ImagePath` contains the image file name.</span></span>
    * <span data-ttu-id="00966-193">`Label` contiene un valor para la etiqueta de imagen.</span><span class="sxs-lookup"><span data-stu-id="00966-193">`Label` contains a value for the image label.</span></span>

1. <span data-ttu-id="00966-194">Agregue una clase nueva al proyecto para `ImagePrediction`:</span><span class="sxs-lookup"><span data-stu-id="00966-194">Add a new class to your project for `ImagePrediction`:</span></span>

    [!code-csharp[DeclareImagePrediction](./snippets/image-classification/csharp/Program.cs#DeclareImagePrediction)]

    <span data-ttu-id="00966-195">`ImagePrediction` es la clase de predicción de imagen y tiene los campos siguientes:</span><span class="sxs-lookup"><span data-stu-id="00966-195">`ImagePrediction` is the image prediction class and has the following fields:</span></span>

    * <span data-ttu-id="00966-196">`Score` contiene el porcentaje de confianza de una clasificación de imágenes determinada.</span><span class="sxs-lookup"><span data-stu-id="00966-196">`Score` contains the confidence percentage for a given image classification.</span></span>
    * <span data-ttu-id="00966-197">`PredictedLabelValue` contiene un valor para la etiqueta de clasificación de imágenes prevista.</span><span class="sxs-lookup"><span data-stu-id="00966-197">`PredictedLabelValue` contains a value for the predicted image classification label.</span></span>

    <span data-ttu-id="00966-198">`ImagePrediction` es la clase usada para la predicción una vez entrenado el modelo.</span><span class="sxs-lookup"><span data-stu-id="00966-198">`ImagePrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="00966-199">Tiene una `string` (`ImagePath`) para la ruta de acceso a la imagen.</span><span class="sxs-lookup"><span data-stu-id="00966-199">It has a `string` (`ImagePath`) for the image path.</span></span> <span data-ttu-id="00966-200">`Label` se usa para reutilizar y entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="00966-200">The `Label` is used to reuse and train the model.</span></span> <span data-ttu-id="00966-201">`PredictedLabelValue` se usa durante la predicción y la evaluación.</span><span class="sxs-lookup"><span data-stu-id="00966-201">The `PredictedLabelValue` is used during prediction and evaluation.</span></span> <span data-ttu-id="00966-202">Para la evaluación, se utiliza una entrada con los datos de entrenamiento, los valores de predicción y el modelo.</span><span class="sxs-lookup"><span data-stu-id="00966-202">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="00966-203">Inicializar variables en Main</span><span class="sxs-lookup"><span data-stu-id="00966-203">Initialize variables in Main</span></span>

1. <span data-ttu-id="00966-204">Inicialice la variable `mlContext` con una instancia nueva de `MLContext`.</span><span class="sxs-lookup"><span data-stu-id="00966-204">Initialize the `mlContext` variable with a new instance of `MLContext`.</span></span>  <span data-ttu-id="00966-205">Reemplace la línea `Console.WriteLine("Hello World!")` por el código siguiente en el método `Main`:</span><span class="sxs-lookup"><span data-stu-id="00966-205">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

    [!code-csharp[CreateMLContext](./snippets/image-classification/csharp/Program.cs#CreateMLContext)]

    <span data-ttu-id="00966-206">La [clase MLContext](xref:Microsoft.ML.MLContext) es un punto de partida para todas las operaciones de ML.NET. Al inicializar `mlContext`, se crea un entorno de ML.NET que se puede compartir entre los objetos del flujo de trabajo de creación de modelos.</span><span class="sxs-lookup"><span data-stu-id="00966-206">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="00966-207">Como concepto, se parece a `DBContext` en Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="00966-207">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

### <a name="create-a-struct-for-inception-model-parameters"></a><span data-ttu-id="00966-208">Creación de una estructura para los parámetros del modelo de inicio</span><span class="sxs-lookup"><span data-stu-id="00966-208">Create a struct for Inception model parameters</span></span>

1. <span data-ttu-id="00966-209">El modelo de inicio tiene varios parámetros que se deben transmitir.</span><span class="sxs-lookup"><span data-stu-id="00966-209">The Inception model has several parameters you need to pass in.</span></span> <span data-ttu-id="00966-210">Cree una estructura para asignar los valores de parámetros a nombres descriptivos con el código siguiente, justo después del método `Main()`:</span><span class="sxs-lookup"><span data-stu-id="00966-210">Create a struct to map the parameter values to friendly names with the following code, just after the `Main()` method:</span></span>

    [!code-csharp[InceptionSettings](./snippets/image-classification/csharp/Program.cs#InceptionSettings)]

### <a name="create-a-display-utility-method"></a><span data-ttu-id="00966-211">Crear un método de utilidad para mostrar</span><span class="sxs-lookup"><span data-stu-id="00966-211">Create a display utility method</span></span>

<span data-ttu-id="00966-212">Dado que se mostrarán los datos de imagen y las predicciones relacionadas más de una vez, cree un método de utilidad para mostrar a fin de controlar la visualización de los resultados de la imagen y la predicción.</span><span class="sxs-lookup"><span data-stu-id="00966-212">Since you'll display the image data and the related predictions more than once, create a display utility method to handle displaying the image and prediction results.</span></span>

1. <span data-ttu-id="00966-213">Cree el método `DisplayResults()` justo después de la estructura `InceptionSettings` con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="00966-213">Create the `DisplayResults()` method, just after the `InceptionSettings` struct, using the following code:</span></span>

    ```csharp
    private static void DisplayResults(IEnumerable<ImagePrediction> imagePredictionData)
    {

    }
    ```

1. <span data-ttu-id="00966-214">Rellene el cuerpo del método `DisplayResults`:</span><span class="sxs-lookup"><span data-stu-id="00966-214">Fill in the body of the `DisplayResults` method:</span></span>

    [!code-csharp[DisplayPredictions](./snippets/image-classification/csharp/Program.cs#DisplayPredictions)]

### <a name="create-a-tsv-file-utility-method"></a><span data-ttu-id="00966-215">Crear un método de utilidad de archivo .tsv</span><span class="sxs-lookup"><span data-stu-id="00966-215">Create a .tsv file utility method</span></span>

1. <span data-ttu-id="00966-216">Cree el método `ReadFromTsv()`, justo después del método `DisplayResults()`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="00966-216">Create the `ReadFromTsv()` method, just after the `DisplayResults()` method, using the following code:</span></span>

    ```csharp
    public static IEnumerable<ImageData> ReadFromTsv(string file, string folder)
    {

    }
    ```

1. <span data-ttu-id="00966-217">Rellene el cuerpo del método `ReadFromTsv`:</span><span class="sxs-lookup"><span data-stu-id="00966-217">Fill in the body of the `ReadFromTsv` method:</span></span>

    [!code-csharp[ReadFromTsv](./snippets/image-classification/csharp/Program.cs#ReadFromTsv)]

    <span data-ttu-id="00966-218">El código analiza el archivo `tags.tsv` para agregar la ruta de acceso al archivo al nombre del archivo de imagen de la propiedad `ImagePath` y lo carga junto con `Label` en un objeto `ImageData`.</span><span class="sxs-lookup"><span data-stu-id="00966-218">The code parses through the `tags.tsv` file to add the file path to the image file name for the `ImagePath` property and load it and the `Label` into an `ImageData` object.</span></span>

### <a name="create-a-method-to-make-a-prediction"></a><span data-ttu-id="00966-219">Creación de un método para hacer una predicción</span><span class="sxs-lookup"><span data-stu-id="00966-219">Create a method to make a prediction</span></span>

1. <span data-ttu-id="00966-220">Cree el método `ClassifySingleImage()`, justo antes del método `DisplayResults()`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="00966-220">Create the `ClassifySingleImage()` method, just before the `DisplayResults()` method, using the following code:</span></span>

    ```csharp
    public static void ClassifySingleImage(MLContext mlContext, ITransformer model)
    {

    }
    ```

1. <span data-ttu-id="00966-221">Cree un objeto `ImageData` que contenga la ruta de acceso completa y el nombre del archivo de imagen para la `ImagePath` única.</span><span class="sxs-lookup"><span data-stu-id="00966-221">Create an `ImageData` object that contains the fully qualified path and image file name for the single `ImagePath`.</span></span> <span data-ttu-id="00966-222">Agregue el código siguiente como las siguientes líneas en el método `ClassifySingleImage()`:</span><span class="sxs-lookup"><span data-stu-id="00966-222">Add the following code as the next  lines in the `ClassifySingleImage()` method:</span></span>

    [!code-csharp[LoadImageData](./snippets/image-classification/csharp/Program.cs#LoadImageData)]

1. <span data-ttu-id="00966-223">Para hacer una predicción única, agregue el código siguiente como la línea siguiente en el método `ClassifySingleImage`:</span><span class="sxs-lookup"><span data-stu-id="00966-223">Make a single prediction, by adding the following code as the next line in the `ClassifySingleImage` method:</span></span>

    [!code-csharp[PredictSingle](./snippets/image-classification/csharp/Program.cs#PredictSingle)]

    <span data-ttu-id="00966-224">Para obtener la predicción, use el método [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A).</span><span class="sxs-lookup"><span data-stu-id="00966-224">To get the prediction, use the [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) method.</span></span> <span data-ttu-id="00966-225">[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) es una API de conveniencia, que le permite realizar una predicción en una única instancia de datos.</span><span class="sxs-lookup"><span data-stu-id="00966-225">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to perform a prediction on a single instance of data.</span></span> <span data-ttu-id="00966-226">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) no es seguro para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="00966-226">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="00966-227">Es aceptable usarlo en entornos de un solo subproceso o prototipo.</span><span class="sxs-lookup"><span data-stu-id="00966-227">It's acceptable to use in single-threaded or prototype environments.</span></span> <span data-ttu-id="00966-228">Para mejorar el rendimiento y la seguridad para subprocesos en entornos de producción, use el servicio `PredictionEnginePool`, que crea un [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) de objetos de [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) para su uso en toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="00966-228">For improved performance and thread safety in production environments, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span> <span data-ttu-id="00966-229">Consulte esta guía sobre cómo [usar `PredictionEnginePool` en una API web de ASP.NET Core](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span><span class="sxs-lookup"><span data-stu-id="00966-229">See this guide on how to [use `PredictionEnginePool` in an ASP.NET Core Web API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span></span>

    > [!NOTE]
    > <span data-ttu-id="00966-230">La extensión del servicio `PredictionEnginePool` está actualmente en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="00966-230">`PredictionEnginePool` service extension is currently in preview.</span></span>

1. <span data-ttu-id="00966-231">Muestre el resultado de la predicción como la línea de código siguiente en el método `ClassifySingleImage()`:</span><span class="sxs-lookup"><span data-stu-id="00966-231">Display the prediction result as the next line of code in the `ClassifySingleImage()` method:</span></span>

   [!code-csharp[DisplayPrediction](./snippets/image-classification/csharp/Program.cs#DisplayPrediction)]

## <a name="construct-the-mlnet-model-pipeline"></a><span data-ttu-id="00966-232">Construcción de la canalización del modelo de ML.NET</span><span class="sxs-lookup"><span data-stu-id="00966-232">Construct the ML.NET model pipeline</span></span>

<span data-ttu-id="00966-233">Una canalización del modelo de ML.NET es una cadena de estimadores.</span><span class="sxs-lookup"><span data-stu-id="00966-233">An ML.NET model pipeline is a chain of estimators.</span></span> <span data-ttu-id="00966-234">Tenga en cuenta que no se produce ninguna ejecución durante la construcción de la canalización.</span><span class="sxs-lookup"><span data-stu-id="00966-234">Note that no execution happens during pipeline construction.</span></span> <span data-ttu-id="00966-235">Se crean los objetos del estimador, pero no se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="00966-235">The estimator objects are created but not executed.</span></span>

1. <span data-ttu-id="00966-236">Agregue un método para generar el modelo</span><span class="sxs-lookup"><span data-stu-id="00966-236">Add a method to generate the model</span></span>

    <span data-ttu-id="00966-237">Este método es la parte central del tutorial.</span><span class="sxs-lookup"><span data-stu-id="00966-237">This method is the heart of the tutorial.</span></span> <span data-ttu-id="00966-238">Crea una canalización para el modelo y entrena la canalización para generar el modelo de ML.NET.</span><span class="sxs-lookup"><span data-stu-id="00966-238">It creates a pipeline for the model, and trains the pipeline to produce the ML.NET model.</span></span> <span data-ttu-id="00966-239">También evalúa el modelo con respecto a algunos datos de prueba previamente desconocidos.</span><span class="sxs-lookup"><span data-stu-id="00966-239">It also evaluates the model against some previously unseen test data.</span></span>

    <span data-ttu-id="00966-240">Cree el método `GenerateModel()` justo después de la estructura `InceptionSettings` y antes del método `DisplayResults()` con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="00966-240">Create the `GenerateModel()` method, just after the `InceptionSettings` struct and just before the `DisplayResults()` method, using the following code:</span></span>

    ```csharp
    public static ITransformer GenerateModel(MLContext mlContext)
    {

    }
    ```

1. <span data-ttu-id="00966-241">Agregue los estimadores para cargar, cambiar el tamaño y extraer los píxeles de los datos de la imagen:</span><span class="sxs-lookup"><span data-stu-id="00966-241">Add the estimators to load, resize and extract the pixels from the image data:</span></span>

    [!code-csharp[ImageTransforms](./snippets/image-classification/csharp/Program.cs#ImageTransforms)]

    <span data-ttu-id="00966-242">Los datos de la imagen se deben procesar en el formato que el modelo de TensorFlow espera.</span><span class="sxs-lookup"><span data-stu-id="00966-242">The image data needs to be processed into the format that the TensorFlow model expects.</span></span> <span data-ttu-id="00966-243">En este caso, las imágenes se cargan en la memoria, se cambia el tamaño a un tamaño coherente y los píxeles se extraen en un vector numérico.</span><span class="sxs-lookup"><span data-stu-id="00966-243">In this case, the images are loaded into memory, resized to a consistent size, and the pixels are extracted into a numeric vector.</span></span>

1. <span data-ttu-id="00966-244">Agregue el estimador para cargar el modelo de TensorFlow y puntúelo:</span><span class="sxs-lookup"><span data-stu-id="00966-244">Add the estimator to load the TensorFlow model, and score it:</span></span>

    [!code-csharp[ScoreTensorFlowModel](./snippets/image-classification/csharp/Program.cs#ScoreTensorFlowModel)]

    <span data-ttu-id="00966-245">Esta fase de la canalización carga el modelo de TensorFlow en la memoria y, a continuación, procesa el vector de valores de píxeles a través de la red del modelo de TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="00966-245">This stage in the pipeline loads the TensorFlow model into memory, then processes the vector of pixel values through the TensorFlow model network.</span></span> <span data-ttu-id="00966-246">La aplicación de entradas a un modelo de aprendizaje profundo y la generación de una salida mediante el modelo se conoce como **Puntuación**.</span><span class="sxs-lookup"><span data-stu-id="00966-246">Applying inputs to a deep learning model, and generating an output using the model, is referred to as **Scoring**.</span></span> <span data-ttu-id="00966-247">Al utilizar el modelo en su totalidad, la puntuación hace una inferencia o predicción.</span><span class="sxs-lookup"><span data-stu-id="00966-247">When using the model in its entirety, scoring makes an inference, or prediction.</span></span>

    <span data-ttu-id="00966-248">En este caso, se usa todo el modelo de TensorFlow, excepto la última capa, que es la que realiza la inferencia.</span><span class="sxs-lookup"><span data-stu-id="00966-248">In this case, you use all of the TensorFlow model except the last layer, which is the layer that makes the inference.</span></span> <span data-ttu-id="00966-249">El resultado de la penúltima capa tiene la etiqueta `softmax_2_preactivation`.</span><span class="sxs-lookup"><span data-stu-id="00966-249">The output of the penultimate layer is labeled `softmax_2_preactivation`.</span></span> <span data-ttu-id="00966-250">La salida de esta capa es, de hecho, un vector de las características que caracterizan las imágenes de entrada originales.</span><span class="sxs-lookup"><span data-stu-id="00966-250">The output of this layer is effectively a vector of features that characterize the original input images.</span></span>

    <span data-ttu-id="00966-251">Este vector de características generado por el modelo de TensorFlow se usará como entrada para un algoritmo de aprendizaje de ML.NET.</span><span class="sxs-lookup"><span data-stu-id="00966-251">This feature vector generated by the TensorFlow model will be used as input to an ML.NET training algorithm.</span></span>

1. <span data-ttu-id="00966-252">Agregue el estimador para asignar las etiquetas de cadena en los datos de entrenamiento a los valores de clave entera:</span><span class="sxs-lookup"><span data-stu-id="00966-252">Add the estimator to map the string labels in the training data to integer key values:</span></span>

    [!code-csharp[MapValueToKey](./snippets/image-classification/csharp/Program.cs#MapValueToKey)]

    <span data-ttu-id="00966-253">El entrenador de ML.NET que se anexa a continuación requiere que sus etiquetas estén en formato `key` en lugar de cadenas arbitrarias.</span><span class="sxs-lookup"><span data-stu-id="00966-253">The ML.NET trainer that is appended next requires its labels to be in `key` format rather than arbitrary strings.</span></span> <span data-ttu-id="00966-254">Una clave es un número que tiene una asignación de uno a uno a un valor de cadena.</span><span class="sxs-lookup"><span data-stu-id="00966-254">A key is a number that has a one to one mapping to a string value.</span></span>

1. <span data-ttu-id="00966-255">Agregue el algoritmo de aprendizaje de ML.NET:</span><span class="sxs-lookup"><span data-stu-id="00966-255">Add the ML.NET training algorithm:</span></span>

    [!code-csharp[AddTrainer](./snippets/image-classification/csharp/Program.cs#AddTrainer)]

1. <span data-ttu-id="00966-256">Agregue el estimador para asignar el valor de clave de predicción a una cadena:</span><span class="sxs-lookup"><span data-stu-id="00966-256">Add the estimator to map the predicted key value back into a string:</span></span>

    [!code-csharp[MapKeyToValue](./snippets/image-classification/csharp/Program.cs#MapKeyToValue)]

## <a name="train-the-model"></a><span data-ttu-id="00966-257">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="00966-257">Train the model</span></span>

1. <span data-ttu-id="00966-258">Cargue los datos de entrenamiento con el contenedor [LoadFromTextFile](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile(Microsoft.ML.DataOperationsCatalog,System.String,Microsoft.ML.Data.TextLoader.Options)).</span><span class="sxs-lookup"><span data-stu-id="00966-258">Load the training data using the [LoadFromTextFile](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile(Microsoft.ML.DataOperationsCatalog,System.String,Microsoft.ML.Data.TextLoader.Options)) wrapper.</span></span> <span data-ttu-id="00966-259">Agregue el siguiente código como la siguiente línea en el método `GenerateModel()`:</span><span class="sxs-lookup"><span data-stu-id="00966-259">Add the following code as the next line in the `GenerateModel()` method:</span></span>

    [!code-csharp[LoadData](./snippets/image-classification/csharp/Program.cs#LoadData "Load the data")]

    <span data-ttu-id="00966-260">Los datos de ML.NET se representan como una [clase IDataView](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="00966-260">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="00966-261">`IDataView` es una manera flexible y eficiente de describir datos tabulares (numéricos y de texto).</span><span class="sxs-lookup"><span data-stu-id="00966-261">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="00966-262">Los datos se pueden cargar desde un archivo de texto o en tiempo real (por ejemplo, archivos de registro o base de datos SQL) en un objeto `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="00966-262">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

1. <span data-ttu-id="00966-263">Entrene el modelo con los datos cargados anteriormente:</span><span class="sxs-lookup"><span data-stu-id="00966-263">Train the model with the data loaded above:</span></span>

    [!code-csharp[TrainModel](./snippets/image-classification/csharp/Program.cs#TrainModel)]

    <span data-ttu-id="00966-264">El método `Fit()` entrena el modelo mediante la aplicación del conjunto de datos de entrenamiento a la canalización.</span><span class="sxs-lookup"><span data-stu-id="00966-264">The `Fit()` method trains your model by applying the training dataset to the pipeline.</span></span>

## <a name="evaluate-the-accuracy-of-the-model"></a><span data-ttu-id="00966-265">Evaluación de la precisión del modelo</span><span class="sxs-lookup"><span data-stu-id="00966-265">Evaluate the accuracy of the model</span></span>

1. <span data-ttu-id="00966-266">Cargue y transforme los datos de prueba agregando el código siguiente a la siguiente línea del método `GenerateModel`:</span><span class="sxs-lookup"><span data-stu-id="00966-266">Load and transform the test data, by adding the following code to the next line of the `GenerateModel` method:</span></span>

    [!code-csharp[LoadAndTransformTestData](./snippets/image-classification/csharp/Program.cs#LoadAndTransformTestData "Load and transform test data")]

    <span data-ttu-id="00966-267">Hay algunas imágenes de ejemplo que puede usar para evaluar el modelo.</span><span class="sxs-lookup"><span data-stu-id="00966-267">There are a few sample images that you can use to evaluate the model.</span></span> <span data-ttu-id="00966-268">Al igual que los datos de entrenamiento, deben cargarse en `IDataView`, de modo que el modelo pueda transformarlos.</span><span class="sxs-lookup"><span data-stu-id="00966-268">Like the training data, these need to be loaded into an `IDataView`, so that they can be transformed by the model.</span></span>

1. <span data-ttu-id="00966-269">Agregue el código siguiente al método `GenerateModel()` para evaluar el modelo:</span><span class="sxs-lookup"><span data-stu-id="00966-269">Add the following code to the `GenerateModel()` method to evaluate the model:</span></span>

    [!code-csharp[Evaluate](./snippets/image-classification/csharp/Program.cs#Evaluate)]

    <span data-ttu-id="00966-270">Una vez que establece la predicción, el método [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A):</span><span class="sxs-lookup"><span data-stu-id="00966-270">Once you have the prediction set, the [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) method:</span></span>

    * <span data-ttu-id="00966-271">Evalúa el modelo (compara los valores previstos con el conjunto de datos `labels` de prueba).</span><span class="sxs-lookup"><span data-stu-id="00966-271">Assesses the model (compares the predicted values with the test dataset `labels`).</span></span>
    * <span data-ttu-id="00966-272">Devuelve las métricas de rendimiento del modelo.</span><span class="sxs-lookup"><span data-stu-id="00966-272">Returns the model performance metrics.</span></span>

1. <span data-ttu-id="00966-273">Visualización de las métricas de precisión del modelo</span><span class="sxs-lookup"><span data-stu-id="00966-273">Display the model accuracy metrics</span></span>

    <span data-ttu-id="00966-274">Utilice el código siguiente para mostrar las métricas, compartir los resultados y, a continuación, trabajar con ellos:</span><span class="sxs-lookup"><span data-stu-id="00966-274">Use the following code to display the metrics, share the results, and then act on them:</span></span>

    [!code-csharp[DisplayMetrics](./snippets/image-classification/csharp/Program.cs#DisplayMetrics)]

    <span data-ttu-id="00966-275">Las siguiente métricas se evalúan para la clasificación de imágenes:</span><span class="sxs-lookup"><span data-stu-id="00966-275">The following metrics are evaluated for image classification:</span></span>

    * <span data-ttu-id="00966-276">`Log-loss`: consulte [Pérdida de registro](../resources/glossary.md#log-loss).</span><span class="sxs-lookup"><span data-stu-id="00966-276">`Log-loss` - see [Log Loss](../resources/glossary.md#log-loss).</span></span> <span data-ttu-id="00966-277">Le recomendamos que la pérdida logarítmica esté lo más cerca posible de 0.</span><span class="sxs-lookup"><span data-stu-id="00966-277">You want Log-loss to be as close to zero as possible.</span></span>
    * <span data-ttu-id="00966-278">`Per class Log-loss`.</span><span class="sxs-lookup"><span data-stu-id="00966-278">`Per class Log-loss`.</span></span> <span data-ttu-id="00966-279">Le recomendamos que la pérdida logarítmica por clase esté lo más cerca posible de 0.</span><span class="sxs-lookup"><span data-stu-id="00966-279">You want per class Log-loss to be as close to zero as possible.</span></span>

1. <span data-ttu-id="00966-280">Agregue el siguiente código para devolver el modelo entrenado, como la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="00966-280">Add the following code to return the trained model as the next line:</span></span>

    [!code-csharp[SaveModel](./snippets/image-classification/csharp/Program.cs#ReturnModel)]

## <a name="run-the-application"></a><span data-ttu-id="00966-281">Ejecución de la aplicación</span><span class="sxs-lookup"><span data-stu-id="00966-281">Run the application!</span></span>

1. <span data-ttu-id="00966-282">Agregue la llamada a `GenerateModel` en el método `Main` después de la creación de la clase MLContext:</span><span class="sxs-lookup"><span data-stu-id="00966-282">Add the call to `GenerateModel` in the `Main` method after the creation of the MLContext class:</span></span>

    [!code-csharp[CallGenerateModel](./snippets/image-classification/csharp/Program.cs#CallGenerateModel)]

1. <span data-ttu-id="00966-283">Agregue la llamada al método `ClassifySingleImage()` como la siguiente línea de código en el método `Main`:</span><span class="sxs-lookup"><span data-stu-id="00966-283">Add the call to the `ClassifySingleImage()` method as the next line of code in the `Main` method:</span></span>

    [!code-csharp[CallClassifySingleImage](./snippets/image-classification/csharp/Program.cs#CallClassifySingleImage)]

1. <span data-ttu-id="00966-284">Ejecute la aplicación de consola (Ctrl + F5).</span><span class="sxs-lookup"><span data-stu-id="00966-284">Run your console app (Ctrl + F5).</span></span> <span data-ttu-id="00966-285">Los resultados deberían ser similares a la salida siguiente.</span><span class="sxs-lookup"><span data-stu-id="00966-285">Your results should be similar to the following output.</span></span>  <span data-ttu-id="00966-286">Es posible que vea advertencias o mensajes de procesamiento, si bien se han quitado de los resultados siguientes para mayor claridad.</span><span class="sxs-lookup"><span data-stu-id="00966-286">You may see warnings or processing messages, but these messages have been removed from the following results for clarity.</span></span>

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

<span data-ttu-id="00966-287">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="00966-287">Congratulations!</span></span> <span data-ttu-id="00966-288">Ha creado correctamente un modelo de Machine Learning para la clasificación de imágenes al aplicar el aprendizaje de transferencia a un modelo de `TensorFlow` en ML.NET.</span><span class="sxs-lookup"><span data-stu-id="00966-288">You've now successfully built a machine learning model for image classification by applying transfer learning to a `TensorFlow` model in ML.NET.</span></span>

<span data-ttu-id="00966-289">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/main/machine-learning/tutorials/TransferLearningTF).</span><span class="sxs-lookup"><span data-stu-id="00966-289">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/main/machine-learning/tutorials/TransferLearningTF) repository.</span></span>

<span data-ttu-id="00966-290">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="00966-290">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="00966-291">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="00966-291">Understand the problem</span></span>
> * <span data-ttu-id="00966-292">Incorporación del modelo de TensorFlow entrenado previamente en la canalización de ML.NET</span><span class="sxs-lookup"><span data-stu-id="00966-292">Incorporate the pre-trained TensorFlow model into the ML.NET pipeline</span></span>
> * <span data-ttu-id="00966-293">Entrenamiento y evaluación del modelo de ML.NET</span><span class="sxs-lookup"><span data-stu-id="00966-293">Train and evaluate the ML.NET model</span></span>
> * <span data-ttu-id="00966-294">Clasificación de una imagen de prueba</span><span class="sxs-lookup"><span data-stu-id="00966-294">Classify a test image</span></span>

<span data-ttu-id="00966-295">Consulte el repositorio de GitHub con ejemplos de Machine Learning para explorar un ejemplo expandido de clasificación de imágenes.</span><span class="sxs-lookup"><span data-stu-id="00966-295">Check out the Machine Learning samples GitHub repository to explore an expanded image classification sample.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="00966-296">Repositorio dotnet/machinelearning-samples de GitHub</span><span class="sxs-lookup"><span data-stu-id="00966-296">dotnet/machinelearning-samples GitHub repository</span></span>](https://github.com/dotnet/machinelearning-samples/)
