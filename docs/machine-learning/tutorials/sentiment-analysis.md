---
title: Uso de ML.NET en un escenario de clasificación binaria de análisis de sentimiento
description: Descubra cómo usar ML.NET en un escenario de clasificación binaria para aprender a usar la predicción de sentimientos a fin de tomar las medidas oportunas.
ms.date: 03/07/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 202edc5127388df2397053d5703d33a39046374f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59303120"
---
# <a name="tutorial-use-mlnet-in-a-sentiment-analysis-binary-classification-scenario"></a><span data-ttu-id="d628f-103">Tutorial: Uso de ML.NET en un escenario de clasificación binaria de análisis de sentimiento</span><span class="sxs-lookup"><span data-stu-id="d628f-103">Tutorial: Use ML.NET in a sentiment analysis binary classification scenario</span></span>

<span data-ttu-id="d628f-104">En este tutorial de ejemplo se muestra cómo utilizar ML.NET para crear un clasificador de sentimientos para predecir una opinión positiva o negativa a través de una aplicación de consola de .NET Core con C# en Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="d628f-104">This sample tutorial illustrates using ML.NET to create a sentiment classifier to predict either positive or negative sentiment via a .NET Core console application using C# in Visual Studio 2017.</span></span> <span data-ttu-id="d628f-105">En el mundo del aprendizaje automático, este tipo de predicción se denomina clasificación binaria.</span><span class="sxs-lookup"><span data-stu-id="d628f-105">In the world of machine learning, this type of prediction is known as binary classification.</span></span>

> [!NOTE]
> <span data-ttu-id="d628f-106">Este tema hace referencia a ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios.</span><span class="sxs-lookup"><span data-stu-id="d628f-106">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="d628f-107">Para obtener más información, visite [la introducción de ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="d628f-107">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="d628f-108">Este tutorial y el ejemplo relacionado usan actualmente **ML.NET en su versión 0.11**.</span><span class="sxs-lookup"><span data-stu-id="d628f-108">This tutorial and related sample are currently using **ML.NET version 0.11**.</span></span> <span data-ttu-id="d628f-109">Para obtener más información, consulte las notas de la versión en el [repositorio de GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="d628f-109">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)</span></span>

<span data-ttu-id="d628f-110">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="d628f-110">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="d628f-111">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="d628f-111">Understand the problem</span></span>
> * <span data-ttu-id="d628f-112">Seleccionar el algoritmo de aprendizaje automático adecuado</span><span class="sxs-lookup"><span data-stu-id="d628f-112">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="d628f-113">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="d628f-113">Prepare your data</span></span>
> * <span data-ttu-id="d628f-114">Transformar los datos</span><span class="sxs-lookup"><span data-stu-id="d628f-114">Transform the data</span></span>
> * <span data-ttu-id="d628f-115">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="d628f-115">Train the model</span></span>
> * <span data-ttu-id="d628f-116">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="d628f-116">Evaluate the model</span></span>
> * <span data-ttu-id="d628f-117">Predecir con el modelo entrenado</span><span class="sxs-lookup"><span data-stu-id="d628f-117">Predict with the trained model</span></span>
> * <span data-ttu-id="d628f-118">Implementar y predecir con un modelo cargado</span><span class="sxs-lookup"><span data-stu-id="d628f-118">Deploy and Predict with a loaded model</span></span>

## <a name="sentiment-analysis-sample-overview"></a><span data-ttu-id="d628f-119">Información general del ejemplo de análisis de sentimiento</span><span class="sxs-lookup"><span data-stu-id="d628f-119">Sentiment analysis sample overview</span></span>

<span data-ttu-id="d628f-120">El ejemplo es una aplicación de consola que utiliza ML.NET para entrenar un modelo que clasifica y predice un sentimiento como positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="d628f-120">The sample is a console app that uses ML.NET to train a model that classifies and predicts sentiment as either positive or negative.</span></span> <span data-ttu-id="d628f-121">El conjunto de datos de opinión de Yelp proviene de la Universidad de California, Irvine (UCI), y se divide en un conjunto de datos de entrenamiento y un conjunto de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="d628f-121">The Yelp sentiment dataset is from University of California, Irvine (UCI), which is split into a train dataset and a test dataset.</span></span> <span data-ttu-id="d628f-122">El ejemplo evalúa el modelo con un el conjunto de datos de prueba para analizar la calidad.</span><span class="sxs-lookup"><span data-stu-id="d628f-122">The sample evaluates the model with the test dataset for quality analysis.</span></span> 

<span data-ttu-id="d628f-123">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).</span><span class="sxs-lookup"><span data-stu-id="d628f-123">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d628f-124">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d628f-124">Prerequisites</span></span>

* <span data-ttu-id="d628f-125">[Visual Studio 2017 15.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.</span><span class="sxs-lookup"><span data-stu-id="d628f-125">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* [<span data-ttu-id="d628f-126">El archivo ZIP del conjunto de datos UCI Sentiment Labeled Sentences</span><span class="sxs-lookup"><span data-stu-id="d628f-126">The UCI Sentiment Labeled Sentences dataset zip file</span></span>](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip)

## <a name="machine-learning-workflow"></a><span data-ttu-id="d628f-127">Flujo de trabajo del aprendizaje automático</span><span class="sxs-lookup"><span data-stu-id="d628f-127">Machine learning workflow</span></span>

<span data-ttu-id="d628f-128">En este tutorial se sigue un flujo de trabajo de aprendizaje automático que permite que el proceso avance de manera ordenada.</span><span class="sxs-lookup"><span data-stu-id="d628f-128">This tutorial follows a machine learning workflow that enables the process to move in an orderly fashion.</span></span>

<span data-ttu-id="d628f-129">Las fases del flujo de trabajo son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="d628f-129">The workflow phases are as follows:</span></span>

1. **<span data-ttu-id="d628f-130">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="d628f-130">Understand the problem</span></span>**
2. **<span data-ttu-id="d628f-131">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="d628f-131">Prepare your data</span></span>**
   * **<span data-ttu-id="d628f-132">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="d628f-132">Load the data</span></span>**
   * **<span data-ttu-id="d628f-133">Extraer características (transformar los datos)</span><span class="sxs-lookup"><span data-stu-id="d628f-133">Extract features (Transform your data)</span></span>**
3. **<span data-ttu-id="d628f-134">Compilar y entrenar</span><span class="sxs-lookup"><span data-stu-id="d628f-134">Build and train</span></span>** 
   * **<span data-ttu-id="d628f-135">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="d628f-135">Train the model</span></span>**
   * **<span data-ttu-id="d628f-136">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="d628f-136">Evaluate the model</span></span>**
4. **<span data-ttu-id="d628f-137">Implementar el modelo</span><span class="sxs-lookup"><span data-stu-id="d628f-137">Deploy Model</span></span>**
   * **<span data-ttu-id="d628f-138">Usar el modelo para la predicción</span><span class="sxs-lookup"><span data-stu-id="d628f-138">Use the Model to predict</span></span>**

### <a name="understand-the-problem"></a><span data-ttu-id="d628f-139">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="d628f-139">Understand the problem</span></span>

<span data-ttu-id="d628f-140">Primero debe entender el problema, de manera que pueda dividirlo en partes que admitan la compilación y el entrenamiento del problema.</span><span class="sxs-lookup"><span data-stu-id="d628f-140">You first need to understand the problem, so you can break it down to parts that can support building and training the model.</span></span> <span data-ttu-id="d628f-141">La división del problema en partes le permite predecir y evaluar los resultados.</span><span class="sxs-lookup"><span data-stu-id="d628f-141">Breaking the problem down allows you to predict and evaluate the results.</span></span>

<span data-ttu-id="d628f-142">El problema en este tutorial es comprender los sentimientos de los comentarios del sitio web entrantes para tomar las medidas oportunas.</span><span class="sxs-lookup"><span data-stu-id="d628f-142">The problem for this tutorial is to understand incoming website comment sentiment to take the appropriate action.</span></span>

<span data-ttu-id="d628f-143">Puede dividir el problema en texto de sentimientos y valor de sentimientos para los datos con los que desea entrenar el modelo, y un valor de sentimiento de predicción que puede evaluar y luego usar de manera operativa.</span><span class="sxs-lookup"><span data-stu-id="d628f-143">You can break down the problem to the sentiment text and sentiment value for the data you want to train the model with, and a predicted sentiment value that you can evaluate and then use operationally.</span></span>

<span data-ttu-id="d628f-144">A continuación, necesita **determinar** el sentimiento, lo que le ayuda con la selección de tareas de aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="d628f-144">You then need to **determine** the sentiment, which helps you with the machine learning task selection.</span></span>

## <a name="select-the-appropriate-machine-learning-algorithm"></a><span data-ttu-id="d628f-145">Seleccionar el algoritmo de aprendizaje automático adecuado</span><span class="sxs-lookup"><span data-stu-id="d628f-145">Select the appropriate machine learning algorithm</span></span>

<span data-ttu-id="d628f-146">Con este problema, tiene constancia de los siguientes hechos:</span><span class="sxs-lookup"><span data-stu-id="d628f-146">With this problem, you know the following facts:</span></span>

<span data-ttu-id="d628f-147">Datos de entrenamiento: los comentarios del sitio web pueden ser positivos (1) o negativos (0) (**opinión**).</span><span class="sxs-lookup"><span data-stu-id="d628f-147">Training data: website comments can be positive (1) or negative (0) (**sentiment**).</span></span>

<span data-ttu-id="d628f-148">Prediga el **sentimiento** de un comentario de sitio web nuevo, positivo o negativo, como en los ejemplos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d628f-148">Predict the **sentiment** of a new website comment, either positive or negative, such as in the following examples:</span></span>

* <span data-ttu-id="d628f-149">Me encantan los camareros.</span><span class="sxs-lookup"><span data-stu-id="d628f-149">I love the wait staff here.</span></span> <span data-ttu-id="d628f-150">Molan mucho.</span><span class="sxs-lookup"><span data-stu-id="d628f-150">They rock.</span></span>
* <span data-ttu-id="d628f-151">La sopa de este sitio es la peor.</span><span class="sxs-lookup"><span data-stu-id="d628f-151">This place has the worst soup.</span></span>

<span data-ttu-id="d628f-152">El algoritmo de aprendizaje automático de clasificación es ideal para este escenario.</span><span class="sxs-lookup"><span data-stu-id="d628f-152">The classification machine learning algorithm is best suited for this scenario.</span></span>

### <a name="about-the-classification-algorithm"></a><span data-ttu-id="d628f-153">Acerca del algoritmo de clasificación</span><span class="sxs-lookup"><span data-stu-id="d628f-153">About the classification algorithm</span></span>

<span data-ttu-id="d628f-154">La clasificación es un algoritmo de aprendizaje automático que usa datos para **determinar** la categoría, el tipo o la clase de un elemento o fila de datos.</span><span class="sxs-lookup"><span data-stu-id="d628f-154">Classification is a machine learning algorithm that uses data to **determine** the category, type, or class of an item or row of data.</span></span> <span data-ttu-id="d628f-155">Por ejemplo, puede utilizar la clasificación para:</span><span class="sxs-lookup"><span data-stu-id="d628f-155">For example, you can use classification to:</span></span>

* <span data-ttu-id="d628f-156">Identificar un sentimiento como positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="d628f-156">Identify sentiment as positive or negative.</span></span>
* <span data-ttu-id="d628f-157">Clasificar correo electrónico como correo no deseado o correo válido.</span><span class="sxs-lookup"><span data-stu-id="d628f-157">Classify email as spam, junk, or good.</span></span>
* <span data-ttu-id="d628f-158">Determinar si la muestra de laboratorio de un paciente es cancerosa.</span><span class="sxs-lookup"><span data-stu-id="d628f-158">Determine whether a patient's lab sample is cancerous.</span></span>
* <span data-ttu-id="d628f-159">Categorizar a los clientes por su propensión a responder a una campaña de ventas.</span><span class="sxs-lookup"><span data-stu-id="d628f-159">Categorize customers by their propensity to respond to a sales campaign.</span></span>

<span data-ttu-id="d628f-160">Los algoritmos de clasificación suelen ser de uno de los tipos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d628f-160">Classification algorithms are frequently one of the following types:</span></span>

* <span data-ttu-id="d628f-161">Binario: A o B.</span><span class="sxs-lookup"><span data-stu-id="d628f-161">Binary: either A or B.</span></span>
* <span data-ttu-id="d628f-162">Multiclase: varias categorías que se pueden predecir mediante el uso de un único modelo.</span><span class="sxs-lookup"><span data-stu-id="d628f-162">Multiclass: multiple categories that can be predicted by using a single model.</span></span>

<span data-ttu-id="d628f-163">Dado que los comentarios del sitio web deben clasificarse como positivos o negativos, use el algoritmo de clasificación binaria.</span><span class="sxs-lookup"><span data-stu-id="d628f-163">Because the website comments need to be classified as either positive or negative, you use the Binary Classification algorithm.</span></span> 

## <a name="create-a-console-application"></a><span data-ttu-id="d628f-164">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="d628f-164">Create a console application</span></span>

1. <span data-ttu-id="d628f-165">Abra Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="d628f-165">Open Visual Studio 2017.</span></span> <span data-ttu-id="d628f-166">Seleccione **Archivo** > **Nuevo** > **Proyecto** de la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="d628f-166">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="d628f-167">En el cuadro de diálogo **Nuevo proyecto**, seleccione el nodo **Visual C#** seguido del nodo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="d628f-167">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="d628f-168">Después, seleccione la plantilla del proyecto **Aplicación de consola (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="d628f-168">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="d628f-169">En el cuadro de texto **Nombre**, escriba "SentimentAnalysis" y después haga clic en el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d628f-169">In the **Name** text box, type "SentimentAnalysis" and then select the **OK** button.</span></span>

2. <span data-ttu-id="d628f-170">Cree un directorio denominado *Datos* en el proyecto para guardar los archivos del conjunto de datos:</span><span class="sxs-lookup"><span data-stu-id="d628f-170">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="d628f-171">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **Nueva carpeta**.</span><span class="sxs-lookup"><span data-stu-id="d628f-171">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="d628f-172">Escriba "Datos" y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="d628f-172">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="d628f-173">Instale el **paquete NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="d628f-173">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="d628f-174">En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="d628f-174">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="d628f-175">Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.ML**, seleccione ese paquete en la lista y seleccione el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="d628f-175">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="d628f-176">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="d628f-176">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="d628f-177">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="d628f-177">Prepare your data</span></span>

1. <span data-ttu-id="d628f-178">Descargue el [archivo zip del conjunto de datos UCI Sentiment Labeled Sentences (vea la referencia en la nota siguiente)](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) y descomprímalo.</span><span class="sxs-lookup"><span data-stu-id="d628f-178">Download [The UCI Sentiment Labeled Sentences dataset zip file (see citations in the following note)](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip), and unzip.</span></span>

2. <span data-ttu-id="d628f-179">Copie el archivo `yelp_labelled.txt` en el directorio *Datos* que ha creado.</span><span class="sxs-lookup"><span data-stu-id="d628f-179">Copy the `yelp_labelled.txt` file into the *Data* directory you created.</span></span>

> [!NOTE]
> <span data-ttu-id="d628f-180">Los conjuntos de datos que se utilizan en este tutorial provienen de "From Group to Individual Labels using Deep Features", Kotzias et.</span><span class="sxs-lookup"><span data-stu-id="d628f-180">The datasets this tutorial uses are from the 'From Group to Individual Labels using Deep Features', Kotzias et.</span></span> <span data-ttu-id="d628f-181">al,.</span><span class="sxs-lookup"><span data-stu-id="d628f-181">al,.</span></span> <span data-ttu-id="d628f-182">KDD 2015, and hosted at the UCI Machine Learning Repository - Dua, D. and Karra Taniskidou, E. (2017).</span><span class="sxs-lookup"><span data-stu-id="d628f-182">KDD 2015, and hosted at the UCI Machine Learning Repository - Dua, D. and Karra Taniskidou, E. (2017).</span></span> <span data-ttu-id="d628f-183">UCI Machine Learning Repository [http://archive.ics.uci.edu/ml].</span><span class="sxs-lookup"><span data-stu-id="d628f-183">UCI Machine Learning Repository [http://archive.ics.uci.edu/ml].</span></span> <span data-ttu-id="d628f-184">Irvine, CA: University of California, School of Information and Computer Science.</span><span class="sxs-lookup"><span data-stu-id="d628f-184">Irvine, CA: University of California, School of Information and Computer Science.</span></span>

3. <span data-ttu-id="d628f-185">En el Explorador de soluciones, haga clic con el botón derecho en el archivo `yelp_labeled.txt` y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d628f-185">In Solution Explorer, right-click the `yelp_labeled.txt` file and select **Properties**.</span></span> <span data-ttu-id="d628f-186">En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.</span><span class="sxs-lookup"><span data-stu-id="d628f-186">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="d628f-187">Crear clases y definir rutas de acceso</span><span class="sxs-lookup"><span data-stu-id="d628f-187">Create classes and define paths</span></span>

<span data-ttu-id="d628f-188">Agregue las siguientes instrucciones `using` adicionales a la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="d628f-188">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddUsings "Add necessary usings")]

<span data-ttu-id="d628f-189">Debe crear dos campos globales para contener la ruta del archivo de conjunto de datos descargado recientemente y la ruta del archivo del modelo guardado:</span><span class="sxs-lookup"><span data-stu-id="d628f-189">You need to create two global fields to hold the recently downloaded dataset file path and the saved model file path:</span></span>

* `_dataPath` <span data-ttu-id="d628f-190">tiene la ruta de acceso al conjunto de datos utilizado para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="d628f-190">has the path to the dataset used to train the model.</span></span>
* `_modelPath` <span data-ttu-id="d628f-191">tiene la ruta de acceso donde se guarda el modelo entrenado.</span><span class="sxs-lookup"><span data-stu-id="d628f-191">has the path where the trained model is saved.</span></span>

<span data-ttu-id="d628f-192">Agregue el código siguiente a la línea justo encima del método `Main` para especificar las rutas de acceso:</span><span class="sxs-lookup"><span data-stu-id="d628f-192">Add the following code to the line right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Declare global variables](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DeclareGlobalVariables "Declare global variables")]

<span data-ttu-id="d628f-193">Debe crear algunas clases para los datos de entrada y las predicciones.</span><span class="sxs-lookup"><span data-stu-id="d628f-193">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="d628f-194">Agregue una nueva clase a su proyecto:</span><span class="sxs-lookup"><span data-stu-id="d628f-194">Add a new class to your project:</span></span>

1. <span data-ttu-id="d628f-195">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="d628f-195">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="d628f-196">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="d628f-196">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="d628f-197">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="d628f-197">Then, select the **Add** button.</span></span>

    <span data-ttu-id="d628f-198">Se abre el archivo *SentimentData.cs* en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="d628f-198">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="d628f-199">Agregue la siguiente instrucción `using` a la parte superior de *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="d628f-199">Add the following `using` statement to the top of *SentimentData.cs*:</span></span>

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#AddUsings "Add necessary usings")]

<span data-ttu-id="d628f-200">Quite la definición de clase existente y agregue el código siguiente, que tiene dos clases `SentimentData` y `SentimentPrediction`, al archivo *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="d628f-200">Remove the existing class definition and add the following code, which has two classes `SentimentData` and `SentimentPrediction`, to the *SentimentData.cs* file:</span></span>

[!code-csharp[DeclareTypes](~/samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#DeclareTypes "Declare data record types")]

<span data-ttu-id="d628f-201">La clase de conjunto de datos de entrada, `SentimentData`, tiene un `string` para el comentario (`SentimentText`) y un `bool` (`Sentiment`) que tiene un valor para el sentimiento positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="d628f-201">The input dataset class, `SentimentData`, has a `string` for the comment (`SentimentText`) and a `bool` (`Sentiment`) that has a value for sentiment of either positive or negative.</span></span> <span data-ttu-id="d628f-202">Ambos campos tienen <xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29> atributos adjuntos a ellos.</span><span class="sxs-lookup"><span data-stu-id="d628f-202">Both fields have <xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29> attributes attached to them.</span></span> <span data-ttu-id="d628f-203">Este atributo describe el orden de cada campo en el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="d628f-203">This attribute describes the order of each field in the data file.</span></span>  <span data-ttu-id="d628f-204">Además, la propiedad `Sentiment` tiene un <xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A> para designarlo como el campo `Label`.</span><span class="sxs-lookup"><span data-stu-id="d628f-204">In addition, the `Sentiment` property has a <xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A> to designate it as the `Label` field.</span></span> `SentimentPrediction` <span data-ttu-id="d628f-205">es la clase usada para la predicción una vez entrenado el modelo.</span><span class="sxs-lookup"><span data-stu-id="d628f-205">is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="d628f-206">Tiene un valor booleano único (`Sentiment`) y un atributo `PredictedLabel` `ColumnName`.</span><span class="sxs-lookup"><span data-stu-id="d628f-206">It has a single boolean (`Sentiment`) and a `PredictedLabel` `ColumnName` attribute.</span></span> <span data-ttu-id="d628f-207">`Label` se usa para crear y entrenar el modelo, y se usa también con el conjunto de datos de prueba dividido para evaluar el modelo.</span><span class="sxs-lookup"><span data-stu-id="d628f-207">The `Label` is used to create and train the model, and it's also used with the split out test dataset to evaluate the model.</span></span> <span data-ttu-id="d628f-208">`PredictedLabel` se usa durante la predicción y la evaluación.</span><span class="sxs-lookup"><span data-stu-id="d628f-208">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="d628f-209">Para la evaluación, se utiliza una entrada con los datos de entrenamiento, los valores de predicción y el modelo.</span><span class="sxs-lookup"><span data-stu-id="d628f-209">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="d628f-210">Cuando se crea un modelo con ML.NET empieza creando un <xref:Microsoft.ML.MLContext>.</span><span class="sxs-lookup"><span data-stu-id="d628f-210">When building a model with ML.NET you start by creating an <xref:Microsoft.ML.MLContext>.</span></span> `MLContext` <span data-ttu-id="d628f-211">es comparable conceptualmente a usar `DbContext` en Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="d628f-211">is comparable conceptually to using `DbContext` in Entity Framework.</span></span> <span data-ttu-id="d628f-212">El entorno proporciona un contexto para el trabajo de ML que puede usarse para el seguimiento y registro de excepciones.</span><span class="sxs-lookup"><span data-stu-id="d628f-212">The environment provides a context for your ML job that can be used for exception tracking and logging.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="d628f-213">Inicializar variables en Main</span><span class="sxs-lookup"><span data-stu-id="d628f-213">Initialize variables in Main</span></span>

<span data-ttu-id="d628f-214">Cree una variable denominada `mlContext` e inicialícela con una nueva instancia de `MLContext`.</span><span class="sxs-lookup"><span data-stu-id="d628f-214">Create a variable called `mlContext` and initialize it with a new instance of `MLContext`.</span></span>  <span data-ttu-id="d628f-215">Reemplace la línea `Console.WriteLine("Hello World!")` por el código siguiente en el método `Main`:</span><span class="sxs-lookup"><span data-stu-id="d628f-215">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateMLContext "Create the ML Context")]

<span data-ttu-id="d628f-216">Agregue lo siguiente como la siguiente línea de código en el método `Main`:</span><span class="sxs-lookup"><span data-stu-id="d628f-216">Add the following as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallLoadData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallLoadData)]

<span data-ttu-id="d628f-217">El método `LoadData` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="d628f-217">The `LoadData` method executes the following tasks:</span></span>

* <span data-ttu-id="d628f-218">Carga los datos.</span><span class="sxs-lookup"><span data-stu-id="d628f-218">Loads the data.</span></span>
* <span data-ttu-id="d628f-219">Divide el conjunto de datos cargado en conjuntos de datos de entrenamiento y prueba.</span><span class="sxs-lookup"><span data-stu-id="d628f-219">Splits the loaded dataset into train and test datasets.</span></span>
* <span data-ttu-id="d628f-220">Devuelve los conjuntos de datos divididos en entrenamiento y prueba.</span><span class="sxs-lookup"><span data-stu-id="d628f-220">Returns the split train and test datasets.</span></span>

<span data-ttu-id="d628f-221">Cree el método `LoadData`, justo después del método `Main`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="d628f-221">Create the `LoadData` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static TrainCatalogBase.TrainTestData LoadData(MLContext mlContext)
{

}
```
## <a name="load-the-data"></a><span data-ttu-id="d628f-222">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="d628f-222">Load the data</span></span>

<span data-ttu-id="d628f-223">Puesto que el tipo de modelo de datos `SentimentData` que ha creado anteriormente coincide con el esquema del conjunto de datos, puede combinar la inicialización, la asignación y la carga del conjunto de datos en una línea de código con el encapsulador `MLContext.Data.LoadFromTextFile` para el [método LoadFromTextFile](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29).</span><span class="sxs-lookup"><span data-stu-id="d628f-223">Since your previously created `SentimentData` data model type matches the dataset schema, you can combine the initialization, mapping, and dataset loading into one line of code using the `MLContext.Data.LoadFromTextFile` wrapper for the [LoadFromTextFile method](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29).</span></span> <span data-ttu-id="d628f-224">Devuelve <xref:Microsoft.Data.DataView.IDataView>.</span><span class="sxs-lookup"><span data-stu-id="d628f-224">It returns a <xref:Microsoft.Data.DataView.IDataView>.</span></span> 

 <span data-ttu-id="d628f-225">Como la entrada y salida de `Transforms`, `DataView` es el tipo de canalización de datos fundamentales, comparable con `IEnumerable` para `LINQ`.</span><span class="sxs-lookup"><span data-stu-id="d628f-225">As the input and output of `Transforms`, a `DataView` is the fundamental data pipeline type, comparable to `IEnumerable` for `LINQ`.</span></span>

<span data-ttu-id="d628f-226">En ML.NET, los datos son similares a una vista SQL.</span><span class="sxs-lookup"><span data-stu-id="d628f-226">In ML.NET, data is similar to a SQL view.</span></span> <span data-ttu-id="d628f-227">Se evalúan lentamente, se esquematizan y son heterogéneos.</span><span class="sxs-lookup"><span data-stu-id="d628f-227">It is lazily evaluated, schematized, and heterogenous.</span></span> <span data-ttu-id="d628f-228">El objeto es la primera parte de la canalización y carga los datos.</span><span class="sxs-lookup"><span data-stu-id="d628f-228">The object is the first part of the pipeline, and loads the data.</span></span> <span data-ttu-id="d628f-229">Para este tutorial, carga un conjunto de datos con comentarios y opiniones tóxicas o no tóxicas correspondiente.</span><span class="sxs-lookup"><span data-stu-id="d628f-229">For this tutorial, it loads a dataset with comments and corresponding toxic or non toxic sentiment.</span></span> <span data-ttu-id="d628f-230">Esto se usa para crear el modelo y entrenarlo.</span><span class="sxs-lookup"><span data-stu-id="d628f-230">This is used to create the model, and train it.</span></span>

 <span data-ttu-id="d628f-231">Agregue el código siguiente a la primera línea del método `LoadData`:</span><span class="sxs-lookup"><span data-stu-id="d628f-231">Add the following code as the first line of the `LoadData` method:</span></span>

[!code-csharp[LoadData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#LoadData "loading dataset")]

### <a name="split-the-dataset-for-model-training-and-testing"></a><span data-ttu-id="d628f-232">División del conjunto de datos para el entrenamiento y la prueba del modelo</span><span class="sxs-lookup"><span data-stu-id="d628f-232">Split the dataset for model training and testing</span></span>

<span data-ttu-id="d628f-233">A continuación, se necesita un conjunto de datos de entrenamiento para entrenar el modelo y un conjunto de datos de prueba para evaluar el modelo.</span><span class="sxs-lookup"><span data-stu-id="d628f-233">Next, you need both a training dataset to train the model and a test dataset to evaluate the model.</span></span> <span data-ttu-id="d628f-234">Use `MLContext.BinaryClassification.TrainTestSplit` que encapsula <xref:Microsoft.ML.StaticPipe.TrainingStaticExtensions.TrainTestSplit%2A> para dividir el conjunto de datos cargado en conjuntos de datos de entrenamiento y prueba y los devuelve dentro de <xref:Microsoft.ML.TrainCatalogBase.TrainTestData>.</span><span class="sxs-lookup"><span data-stu-id="d628f-234">Use the `MLContext.BinaryClassification.TrainTestSplit` which wraps <xref:Microsoft.ML.StaticPipe.TrainingStaticExtensions.TrainTestSplit%2A> to split the loaded dataset into train and test datasets and return them inside of a <xref:Microsoft.ML.TrainCatalogBase.TrainTestData>.</span></span> <span data-ttu-id="d628f-235">Puede especificar la fracción de los datos para la prueba establecida con el parámetro `testFraction`.</span><span class="sxs-lookup"><span data-stu-id="d628f-235">You can specify the fraction of data for the test set with the `testFraction`parameter.</span></span> <span data-ttu-id="d628f-236">El valor predeterminado es 10 %, pero use 20 % en este caso para usar más datos para la evaluación.</span><span class="sxs-lookup"><span data-stu-id="d628f-236">The default is 10% but you use 20% in this case to use more data for the evaluation.</span></span>  

<span data-ttu-id="d628f-237">Para dividir los datos cargados en los conjuntos de datos necesarios, agregue el código siguiente como la siguiente línea en el método `LoadData`:</span><span class="sxs-lookup"><span data-stu-id="d628f-237">To split the loaded data into the needed datasets, add the following code as the next line in the `LoadData` method:</span></span>

[!code-csharp[SplitData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#SplitData "Split the Data")]

<span data-ttu-id="d628f-238">Devuelva el `splitDataView` al final del método `LoadData`:</span><span class="sxs-lookup"><span data-stu-id="d628f-238">Return the `splitDataView` at the end of the `LoadData` method:</span></span>

[!code-csharp[ReturnSplitData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#ReturnSplitData)]

## <a name="build-and-train-the-model"></a><span data-ttu-id="d628f-239">Creación y entrenamiento del modelo</span><span class="sxs-lookup"><span data-stu-id="d628f-239">Build and train the model</span></span>

<span data-ttu-id="d628f-240">Agregue la siguiente llamada al método `BuildAndTrainModel` como siguiente línea de código del método `Main`:</span><span class="sxs-lookup"><span data-stu-id="d628f-240">Add the following call to the `BuildAndTrainModel`method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallBuildAndTrainModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallBuildAndTrainModel)]

<span data-ttu-id="d628f-241">El método `BuildAndTrainModel` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="d628f-241">The `BuildAndTrainModel` method executes the following tasks:</span></span>

* <span data-ttu-id="d628f-242">Extrae y transforma los datos.</span><span class="sxs-lookup"><span data-stu-id="d628f-242">Extracts and transforms the data.</span></span>
* <span data-ttu-id="d628f-243">Entrena el modelo.</span><span class="sxs-lookup"><span data-stu-id="d628f-243">Trains the model.</span></span>
* <span data-ttu-id="d628f-244">Predice sentimientos en función de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="d628f-244">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="d628f-245">Devuelve el modelo.</span><span class="sxs-lookup"><span data-stu-id="d628f-245">Returns the model.</span></span>

<span data-ttu-id="d628f-246">Cree el método `BuildAndTrainModel`, justo después del método `Main`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="d628f-246">Create the `BuildAndTrainModel` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView splitTrainSet)
{

}
```

<span data-ttu-id="d628f-247">Tenga en cuenta que se pasan dos parámetros al método Train: `MLContext` para el contexto (`mlContext`) y `IDataView` para el conjunto de datos de entrenamiento (`splitTrainSet`).</span><span class="sxs-lookup"><span data-stu-id="d628f-247">Notice that two parameters are passed into the Train method; a `MLContext` for the context (`mlContext`), and an `IDataView`for the training dataset (`splitTrainSet`).</span></span> 

## <a name="extract-and-transform-the-data"></a><span data-ttu-id="d628f-248">Extraer y transformar los datos</span><span class="sxs-lookup"><span data-stu-id="d628f-248">Extract and transform the data</span></span>

<span data-ttu-id="d628f-249">El procesamiento previo y la limpieza de datos son tareas importantes que se producen antes de que un conjunto de datos se utilice de forma eficaz para el aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="d628f-249">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span> <span data-ttu-id="d628f-250">Los datos sin procesar contienen a menudo ruido y son poco de fiar; además, es posible que les falten valores.</span><span class="sxs-lookup"><span data-stu-id="d628f-250">Raw data is often noisy and unreliable, and may be missing values.</span></span> <span data-ttu-id="d628f-251">El uso de datos sin estas tareas de modelado puede producir resultados engañosos.</span><span class="sxs-lookup"><span data-stu-id="d628f-251">Using data without these modeling tasks can produce misleading results.</span></span>

<span data-ttu-id="d628f-252">Las canalizaciones de transformación de ML.NET crean un conjunto personalizado de transformaciones que se aplican a los datos antes del entrenamiento o la prueba.</span><span class="sxs-lookup"><span data-stu-id="d628f-252">ML.NET's transform pipelines compose a custom set of transforms that are applied to your data before training or testing.</span></span> <span data-ttu-id="d628f-253">El propósito principal de las transformaciones es la [caracterización](../resources/glossary.md#feature-engineering) de datos.</span><span class="sxs-lookup"><span data-stu-id="d628f-253">The transforms' primary purpose is data [featurization](../resources/glossary.md#feature-engineering).</span></span> <span data-ttu-id="d628f-254">Los algoritmos de aprendizaje automático comprenden los datos [caracterizados](../resources/glossary.md#feature), por lo que el paso siguiente es transformar nuestro datos textuales en un formato que reconozcan nuestros algoritmos de ML.</span><span class="sxs-lookup"><span data-stu-id="d628f-254">Machine learning algorithms understand [featurized](../resources/glossary.md#feature) data, so the next step is to transform our textual data into a format that our ML algorithms recognize.</span></span> <span data-ttu-id="d628f-255">Ese formato es un [vector numérico](../resources/glossary.md#numerical-feature-vector).</span><span class="sxs-lookup"><span data-stu-id="d628f-255">That format is a [numeric vector](../resources/glossary.md#numerical-feature-vector).</span></span>

<span data-ttu-id="d628f-256">Después, llame a `mlContext.Transforms.Text.FeaturizeText` que caracteriza la columna de texto (`SentimentText`) en un vector numérico llamado `Features` utilizado por el algoritmo de aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="d628f-256">Next, call `mlContext.Transforms.Text.FeaturizeText` which featurizes the text column (`SentimentText`) column into a numeric vector called `Features` used by the machine learning algorithm.</span></span> <span data-ttu-id="d628f-257">Se trata de una llamada de contenedor que devuelve <xref:Microsoft.ML.Data.EstimatorChain%601> que eficazmente será una canalización.</span><span class="sxs-lookup"><span data-stu-id="d628f-257">This is a wrapper call that returns an <xref:Microsoft.ML.Data.EstimatorChain%601> that will effectively be a pipeline.</span></span> <span data-ttu-id="d628f-258">Asigne un nombre a `pipeline`, ya que luego anexará el entrenador a `EstimatorChain`.</span><span class="sxs-lookup"><span data-stu-id="d628f-258">Name this `pipeline` as you will then append the trainer to the `EstimatorChain`.</span></span> <span data-ttu-id="d628f-259">Agregue esto como la siguiente línea de código:</span><span class="sxs-lookup"><span data-stu-id="d628f-259">Add this as the next line of code:</span></span>

[!code-csharp[FeaturizeText](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#FeaturizeText "Featurize the text")]

>[!WARNING]
> <span data-ttu-id="d628f-260">En la versión 0.10 de ML.NET se ha cambiado el orden de los parámetros de transformación.</span><span class="sxs-lookup"><span data-stu-id="d628f-260">ML.NET Version 0.10 changed the order of the Transform parameters.</span></span> <span data-ttu-id="d628f-261">Esto no generará un error hasta que se ejecute la aplicación y se compile el modelo.</span><span class="sxs-lookup"><span data-stu-id="d628f-261">This will not error out until you run the application and build the model.</span></span> <span data-ttu-id="d628f-262">Use los nombres de parámetro para las transformaciones, como se muestra en el fragmento de código anterior.</span><span class="sxs-lookup"><span data-stu-id="d628f-262">Use the parameter names for Transforms as illustrated in the previous code snippet.</span></span>

<span data-ttu-id="d628f-263">Este es el paso de preprocesamiento o caracterización.</span><span class="sxs-lookup"><span data-stu-id="d628f-263">This is the preprocessing/featurization step.</span></span> <span data-ttu-id="d628f-264">El uso de componentes adicionales disponibles en ML.NET permite conseguir mejores resultados con el modelo.</span><span class="sxs-lookup"><span data-stu-id="d628f-264">Using additional components available in ML.NET can enable better results with your model.</span></span>

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="d628f-265">Elegir un algoritmo de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="d628f-265">Choose a learning algorithm</span></span>

<span data-ttu-id="d628f-266">Para agregar el entrenador, llame al método contenedor `mlContext.BinaryClassification.Trainers.FastTree` que devuelve un objeto <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer>.</span><span class="sxs-lookup"><span data-stu-id="d628f-266">To add the trainer, call the `mlContext.BinaryClassification.Trainers.FastTree` wrapper method which returns a <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer> object.</span></span> <span data-ttu-id="d628f-267">Esto es un aprendiz de árbol de decisión que usará en esta canalización.</span><span class="sxs-lookup"><span data-stu-id="d628f-267">This is a decision tree learner you'll use in this pipeline.</span></span> <span data-ttu-id="d628f-268">`FastTreeBinaryClassificationTrainer` se anexa a `pipeline` y acepta `SentimentText` (`Features`) caracterizado y los parámetros de entrada `Label` para aprender de los datos históricos.</span><span class="sxs-lookup"><span data-stu-id="d628f-268">The `FastTreeBinaryClassificationTrainer` is appended to the `pipeline` and accepts the featurized `SentimentText` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span>

<span data-ttu-id="d628f-269">Agregue el código siguiente al método `BuildAndTrainModel`:</span><span class="sxs-lookup"><span data-stu-id="d628f-269">Add the following code to the `BuildAndTrainModel` method:</span></span>

[!code-csharp[FastTreeBinaryClassificationTrainer](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddTrainer "Add a FastTreeBinaryClassificationTrainer")]

## <a name="train-the-model"></a><span data-ttu-id="d628f-270">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="d628f-270">Train the model</span></span>

<span data-ttu-id="d628f-271">Se entrena el modelo, <xref:Microsoft.ML.Data.TransformerChain%601>, en función del conjunto de datos que se haya cargado y transformado.</span><span class="sxs-lookup"><span data-stu-id="d628f-271">You train the model, <xref:Microsoft.ML.Data.TransformerChain%601>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="d628f-272">Una vez que se ha definido el estimador, entrenará el modelo mediante el método <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> proporcionando al mismo tiempo los datos de entrenamiento ya cargados.</span><span class="sxs-lookup"><span data-stu-id="d628f-272">Once the estimator has been defined, you train your model using the <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> method while providing the already loaded training data.</span></span> <span data-ttu-id="d628f-273">Esto devuelve un modelo que se usa para las predicciones.</span><span class="sxs-lookup"><span data-stu-id="d628f-273">This returns a model to use for predictions.</span></span> `pipeline.Fit()` <span data-ttu-id="d628f-274">entrena la canalización y devuelve `Transformer` según el elemento `DataView` que se pasa.</span><span class="sxs-lookup"><span data-stu-id="d628f-274">trains the pipeline and returns a `Transformer` based on the `DataView` passed in.</span></span> <span data-ttu-id="d628f-275">El experimento no se ejecuta hasta que se ejecute el método `.Fit()`.</span><span class="sxs-lookup"><span data-stu-id="d628f-275">The experiment is not executed until the `.Fit()` method runs.</span></span>

<span data-ttu-id="d628f-276">Agregue el código siguiente al método `BuildAndTrainModel`:</span><span class="sxs-lookup"><span data-stu-id="d628f-276">Add the following code to the `BuildAndTrainModel` method:</span></span>

[!code-csharp[TrainModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#TrainModel "Train the model")]

### <a name="save-and-return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="d628f-277">Guardar y devolver el modelo entrenado para su uso para la evaluación</span><span class="sxs-lookup"><span data-stu-id="d628f-277">Save and Return the model trained to use for evaluation</span></span>

<span data-ttu-id="d628f-278">En este punto, tiene un modelo de tipo <xref:Microsoft.ML.Data.TransformerChain%601> que se puede integrar en cualquiera de las aplicaciones de .NET nuevas o existentes.</span><span class="sxs-lookup"><span data-stu-id="d628f-278">At this point, you have a model of type <xref:Microsoft.ML.Data.TransformerChain%601> that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="d628f-279">Devuelva el modelo al final del método `BuildAndTrainModel`.</span><span class="sxs-lookup"><span data-stu-id="d628f-279">Return the model at the end of the `BuildAndTrainModel` method.</span></span>

[!code-csharp[ReturnModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#ReturnModel "Return the model")]

## <a name="evaluate-the-model"></a><span data-ttu-id="d628f-280">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="d628f-280">Evaluate the model</span></span>

<span data-ttu-id="d628f-281">Ahora que ha creado y entrenado el modelo, debe evaluarlo con otro conjunto de datos para el control de calidad y la validación.</span><span class="sxs-lookup"><span data-stu-id="d628f-281">Now that you've created and trained the model, you need to evaluate it with a different dataset for quality assurance and validation.</span></span> <span data-ttu-id="d628f-282">En el método `Evaluate`, el modelo creado en `BuildAndTrainModel` se pasa para ser evaluado.</span><span class="sxs-lookup"><span data-stu-id="d628f-282">In the `Evaluate` method, the model created in `BuildAndTrainModel` is passed in to be evaluated.</span></span> <span data-ttu-id="d628f-283">Cree el método `Evaluate`, justo después de `BuildAndTrainModel`, como en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="d628f-283">Create the `Evaluate` method, just after `BuildAndTrainModel`, as in the following code:</span></span>

```csharp
public static void Evaluate(MLContext mlContext, ITransformer model, IDataView splitTestSet)
{

}
```

<span data-ttu-id="d628f-284">El método `Evaluate` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="d628f-284">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="d628f-285">Carga el conjunto de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="d628f-285">Loads the test dataset.</span></span>
* <span data-ttu-id="d628f-286">Crea el evaluador de clasificación binaria.</span><span class="sxs-lookup"><span data-stu-id="d628f-286">Creates the binaryclassification evaluator.</span></span>
* <span data-ttu-id="d628f-287">Evalúa el modelo y crea las métricas.</span><span class="sxs-lookup"><span data-stu-id="d628f-287">Evaluates the model and creates metrics.</span></span>
* <span data-ttu-id="d628f-288">Muestra las métricas.</span><span class="sxs-lookup"><span data-stu-id="d628f-288">Displays the metrics.</span></span>

<span data-ttu-id="d628f-289">Agregue una llamada al método nuevo desde el método `Main`, justo debajo de la llamada al método `Train`, utilizando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="d628f-289">Add a call to the new method from the `Main` method, right under the `Train` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallEvaluate "Call the Evaluate method")]

<span data-ttu-id="d628f-290">A continuación, deberá usará el parámetro `model` de aprendizaje automático (un transformador) y el parámetro `splitTestSet` para introducir las características y devolver las predicciones.</span><span class="sxs-lookup"><span data-stu-id="d628f-290">Next, you'll use the machine learning `model` parameter (a transformer) and the `splitTestSet` parameter to input the features and return predictions.</span></span> <span data-ttu-id="d628f-291">Agregue el código siguiente al método `Evaluate` como la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="d628f-291">Add the following code to the `Evaluate` method as the next line:</span></span>

[!code-csharp[PredictWithTransformer](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#TransformData "Predict using the Transformer")]

<span data-ttu-id="d628f-292">El método `mlContext.BinaryClassification.Evaluate` calcula las métricas de calidad para `PredictionModel` mediante el conjunto de datos especificado.</span><span class="sxs-lookup"><span data-stu-id="d628f-292">The `mlContext.BinaryClassification.Evaluate` method computes the quality metrics for the `PredictionModel` using the specified dataset.</span></span> <span data-ttu-id="d628f-293">Devuelve un objeto <xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics> que contiene las métricas totales calculadas por evaluadores de clasificación binaria.</span><span class="sxs-lookup"><span data-stu-id="d628f-293">It returns a <xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics> object that contains the overall metrics computed by binary classification evaluators.</span></span> <span data-ttu-id="d628f-294">Para mostrar estos elementos a fin de determinar la calidad del modelo, debe obtener primero las métricas.</span><span class="sxs-lookup"><span data-stu-id="d628f-294">To display these to determine the quality of the model, you need to get the metrics first.</span></span> <span data-ttu-id="d628f-295">Agregue el siguiente código como la siguiente línea en el método `Evaluate`:</span><span class="sxs-lookup"><span data-stu-id="d628f-295">Add the following code as the next line in the `Evaluate` method:</span></span>

[!code-csharp[ComputeMetrics](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Evaluate "Compute Metrics")]

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="d628f-296">Mostrar las métricas para la validación del modelo</span><span class="sxs-lookup"><span data-stu-id="d628f-296">Displaying the metrics for model validation</span></span>

<span data-ttu-id="d628f-297">Utilice el código siguiente para mostrar las métricas, compartir los resultados y, a continuación, trabajar con ellos:</span><span class="sxs-lookup"><span data-stu-id="d628f-297">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DisplayMetrics "Display selected metrics")]

<span data-ttu-id="d628f-298">Para guardar el modelo en un archivo .zip antes de devolverlo, agregue el siguiente código para llamar al método `SaveModelAsFile` como la línea siguiente en `Evaluate`:</span><span class="sxs-lookup"><span data-stu-id="d628f-298">To save your model to a .zip file before returning, add the following code to call the `SaveModelAsFile` method as the next line in `Evaluate`:</span></span>

[!code-csharp[SaveModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallSaveModel "Save the model")]

## <a name="save-the-model-as-azip-file"></a><span data-ttu-id="d628f-299">Almacenamiento del modelo como un archivo .zip</span><span class="sxs-lookup"><span data-stu-id="d628f-299">Save the model as a.zip file</span></span>

<span data-ttu-id="d628f-300">Cree el método `SaveModelAsFile`, justo después del método `Evaluate`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="d628f-300">Create the `SaveModelAsFile` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="d628f-301">El método `SaveModelAsFile` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="d628f-301">The `SaveModelAsFile` method executes the following tasks:</span></span>

* <span data-ttu-id="d628f-302">Guarda el modelo como un archivo .zip.</span><span class="sxs-lookup"><span data-stu-id="d628f-302">Saves the model as a .zip file.</span></span>

<span data-ttu-id="d628f-303">A continuación, cree un método para guardar el modelo para que se pueda volver a usar y consumir en otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d628f-303">Next, create a method to save the model so that it can be reused and consumed in other applications.</span></span> <span data-ttu-id="d628f-304">`ITransformer` tiene un método <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> que toma el campo global `_modelPath` y <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="d628f-304">The `ITransformer` has a <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> method that takes in the `_modelPath` global field, and a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="d628f-305">Para guardar esto como un archivo ZIP, creará `FileStream` inmediatamente antes de llamar al método `SaveTo`.</span><span class="sxs-lookup"><span data-stu-id="d628f-305">To save this as a zip file, you'll create the `FileStream` immediately before calling the `SaveTo` method.</span></span> <span data-ttu-id="d628f-306">Agregue el siguiente código al método `SaveModelAsFile` como la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="d628f-306">Add the following code to the `SaveModelAsFile` method as the next line:</span></span>

[!code-csharp[SaveToMethod](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#SaveModel "Add the SaveTo Method")]

<span data-ttu-id="d628f-307">También podría mostrar dónde se escribió el archivo mediante la escritura de un mensaje de consola con `_modelPath`, utilizando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="d628f-307">You could also display where the file was written by writing a console message with the `_modelPath`, using the following code:</span></span>

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="predict-the-test-data-outcome-with-the-saved-model"></a><span data-ttu-id="d628f-308">Predicción de los resultados de datos de prueba con el modelo guardado</span><span class="sxs-lookup"><span data-stu-id="d628f-308">Predict the test data outcome with the saved model</span></span>

<span data-ttu-id="d628f-309">Cree el método `UseModelWithSingleItem`, justo después del método `Evaluate`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="d628f-309">Create the `UseModelWithSingleItem` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void UseModelWithSingleItem(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="d628f-310">El método `UseModelWithSingleItem` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="d628f-310">The `UseModelWithSingleItem` method executes the following tasks:</span></span>

* <span data-ttu-id="d628f-311">Crea un único comentario de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="d628f-311">Creates a single comment of test data.</span></span>
* <span data-ttu-id="d628f-312">Predice sentimientos en función de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="d628f-312">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="d628f-313">Combina datos de prueba y predicciones para la generación de informes.</span><span class="sxs-lookup"><span data-stu-id="d628f-313">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="d628f-314">Muestra los resultados de la predicción.</span><span class="sxs-lookup"><span data-stu-id="d628f-314">Displays the predicted results.</span></span>

<span data-ttu-id="d628f-315">Agregue una llamada al método nuevo desde el método `Main`, justo debajo de la llamada al método `Evaluate`, utilizando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="d628f-315">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallUseModelWithSingleItem](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallUseModelWithSingleItem "Call the UseModelWithSingleItem method")]

<span data-ttu-id="d628f-316">Mientras `model` es `transformer` que opera en muchas filas de datos, un escenario muy común de producción es necesario para las predicciones con los ejemplos individuales.</span><span class="sxs-lookup"><span data-stu-id="d628f-316">While the `model` is a `transformer` that operates on many rows of data, a very common production scenario is a need for predictions on individual examples.</span></span> <span data-ttu-id="d628f-317"><xref:Microsoft.ML.PredictionEngine%602> es un contenedor que se devuelve del método `CreatePredictionEngine`.</span><span class="sxs-lookup"><span data-stu-id="d628f-317">The <xref:Microsoft.ML.PredictionEngine%602> is a wrapper that is returned from the `CreatePredictionEngine` method.</span></span> <span data-ttu-id="d628f-318">Vamos a agregar el código siguiente para crear `PredictionEngine` como la primera línea en el método `Predict`:</span><span class="sxs-lookup"><span data-stu-id="d628f-318">Let's add the following code to create the `PredictionEngine` as the first line in the `Predict` Method:</span></span>

[!code-csharp[CreatePredictionEngine](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreatePredictionEngine1 "Create the PredictionEngine")]
  
<span data-ttu-id="d628f-319">Agregue un comentario para probar la predicción del modelo entrenado en el método `Predict` mediante la creación de una instancia de `SentimentData`:</span><span class="sxs-lookup"><span data-stu-id="d628f-319">Add a comment to test the trained model's prediction in the `Predict` method by creating an instance of `SentimentData`:</span></span>

[!code-csharp[PredictionData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateTestIssue1 "Create test data for single prediction")]

 <span data-ttu-id="d628f-320">Puede usar eso para predecir la opinión positiva o negativa de una única instancia de los datos de comentario.</span><span class="sxs-lookup"><span data-stu-id="d628f-320">You can use that to predict the positive or negative sentiment of a single instance of the comment data.</span></span> <span data-ttu-id="d628f-321">Para obtener una predicción, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> en los datos.</span><span class="sxs-lookup"><span data-stu-id="d628f-321">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="d628f-322">Tenga en cuenta que los datos de entrada son una cadena y el modelo incluye la caracterización.</span><span class="sxs-lookup"><span data-stu-id="d628f-322">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="d628f-323">La canalización está sincronizada durante el entrenamiento y la predicción.</span><span class="sxs-lookup"><span data-stu-id="d628f-323">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="d628f-324">No fue necesario escribir el código de preprocesamiento o caracterización específicamente para las predicciones, y la misma API se encarga de las predicciones por lotes y puntuales.</span><span class="sxs-lookup"><span data-stu-id="d628f-324">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Predict "Create a prediction of sentiment")]

### <a name="use-the-model-prediction"></a><span data-ttu-id="d628f-325">Uso del modelo: predicción</span><span class="sxs-lookup"><span data-stu-id="d628f-325">Use the model: prediction</span></span>

<span data-ttu-id="d628f-326">Muestre `SentimentText` y la predicción del sentimiento correspondiente para compartir los resultados y actuar en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="d628f-326">Display `SentimentText` and corresponding sentiment prediction in order to share the results and act on them accordingly.</span></span> <span data-ttu-id="d628f-327">Esto se denomina puesta en marcha, y se utilizan los datos devueltos como parte de las directivas operativas.</span><span class="sxs-lookup"><span data-stu-id="d628f-327">This is called operationalization, using the returned data as part of the operational policies.</span></span> <span data-ttu-id="d628f-328">Cree una visualización para los resultados mediante el código <xref:System.Console.WriteLine?displayProperty=nameWithType> siguiente:</span><span class="sxs-lookup"><span data-stu-id="d628f-328">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputPrediction](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#OutputPrediction "Display prediction output")]

## <a name="deploy-and-predict-with-a-loaded-model"></a><span data-ttu-id="d628f-329">Implementar y predecir con un modelo cargado</span><span class="sxs-lookup"><span data-stu-id="d628f-329">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="d628f-330">Cree el método `UseLoadedModelWithBatchItems`, justo antes del método `SaveModelAsFile`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="d628f-330">Create the `UseLoadedModelWithBatchItems` method, just before the `SaveModelAsFile` method, using the following code:</span></span>

```csharp
public static void UseLoadedModelWithBatchItems(MLContext mlContext)
{

}
```

<span data-ttu-id="d628f-331">El método `UseLoadedModelWithBatchItems` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="d628f-331">The `UseLoadedModelWithBatchItems` method executes the following tasks:</span></span>

* <span data-ttu-id="d628f-332">Crea datos de prueba por lotes.</span><span class="sxs-lookup"><span data-stu-id="d628f-332">Creates batch test data.</span></span>
* <span data-ttu-id="d628f-333">Predice sentimientos en función de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="d628f-333">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="d628f-334">Combina datos de prueba y predicciones para la generación de informes.</span><span class="sxs-lookup"><span data-stu-id="d628f-334">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="d628f-335">Muestra los resultados de la predicción.</span><span class="sxs-lookup"><span data-stu-id="d628f-335">Displays the predicted results.</span></span>

<span data-ttu-id="d628f-336">Agregue una llamada al método nuevo desde el método `Main`, justo debajo de la llamada al método `UseModelWithSingleItem`, utilizando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="d628f-336">Add a call to the new method from the `Main` method, right under the `UseModelWithSingleItem` method call, using the following code:</span></span>

[!code-csharp[CallPredictModelLoaded](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallUseLoadedModelWithBatchItems "Call the CallUseLoadedModelWithBatchItems method")]

<span data-ttu-id="d628f-337">Agregue algunos comentarios para probar las predicciones del modelo entrenado en el método `UseLoadedModelWithBatchItems`:</span><span class="sxs-lookup"><span data-stu-id="d628f-337">Add some comments to test the trained model's predictions in the `UseLoadedModelWithBatchItems` method:</span></span>

[!code-csharp[PredictionData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateTestIssues "Create test data for predictions")]

<span data-ttu-id="d628f-338">Cargue el modelo</span><span class="sxs-lookup"><span data-stu-id="d628f-338">Load the model</span></span>

[!code-csharp[LoadTheModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#LoadModel "Load the model")]

<span data-ttu-id="d628f-339">Ahora que tiene un modelo, puede utilizarlo para predecir la opinión tóxica o no tóxica de los datos de comentarios con el método <xref:Microsoft.ML.ITransformer.Transform%2A>.</span><span class="sxs-lookup"><span data-stu-id="d628f-339">Now that you have a model, you can use that to predict the Toxic or Non Toxic sentiment of the comment data using the <xref:Microsoft.ML.ITransformer.Transform%2A> method.</span></span> <span data-ttu-id="d628f-340">Para obtener una predicción, use `Predict` en los nuevos datos.</span><span class="sxs-lookup"><span data-stu-id="d628f-340">To get a prediction, use `Predict` on new data.</span></span> <span data-ttu-id="d628f-341">Tenga en cuenta que los datos de entrada son una cadena y el modelo incluye la caracterización.</span><span class="sxs-lookup"><span data-stu-id="d628f-341">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="d628f-342">La canalización está sincronizada durante el entrenamiento y la predicción.</span><span class="sxs-lookup"><span data-stu-id="d628f-342">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="d628f-343">No fue necesario escribir el código de preprocesamiento o caracterización específicamente para las predicciones, y la misma API se encarga de las predicciones por lotes y puntuales.</span><span class="sxs-lookup"><span data-stu-id="d628f-343">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span> <span data-ttu-id="d628f-344">Agregue el código siguiente al método `UseLoadedModelWithBatchItems` para las predicciones:</span><span class="sxs-lookup"><span data-stu-id="d628f-344">Add the following code to the `UseLoadedModelWithBatchItems` method for the predictions:</span></span>

[!code-csharp[Predict](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Prediction "Create predictions of sentiments")]

### <a name="use-the-loaded-model-for-prediction"></a><span data-ttu-id="d628f-345">Uso del modelo cargado para la predicción</span><span class="sxs-lookup"><span data-stu-id="d628f-345">Use the loaded model for prediction</span></span>

<span data-ttu-id="d628f-346">Muestre `SentimentText` y la predicción del sentimiento correspondiente para compartir los resultados y actuar en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="d628f-346">Display `SentimentText` and corresponding sentiment prediction in order to share the results and act on them accordingly.</span></span> <span data-ttu-id="d628f-347">Esto se denomina puesta en marcha, y se utilizan los datos devueltos como parte de las directivas operativas.</span><span class="sxs-lookup"><span data-stu-id="d628f-347">This is called operationalization, using the returned data as part of the operational policies.</span></span> <span data-ttu-id="d628f-348">Cree un encabezado para los resultados con el código <xref:System.Console.WriteLine?displayProperty=nameWithType> siguiente:</span><span class="sxs-lookup"><span data-stu-id="d628f-348">Create a header for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputHeaders](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddInfoMessage "Display prediction outputs")]

<span data-ttu-id="d628f-349">Antes de mostrar los resultados de la predicción, combine el sentimiento con la predicción para ver el comentario original con su sentimiento de predicción.</span><span class="sxs-lookup"><span data-stu-id="d628f-349">Before displaying the predicted results, combine the sentiment and prediction together to see the original comment with its predicted sentiment.</span></span> <span data-ttu-id="d628f-350">El siguiente código utiliza el método <xref:System.Linq.Enumerable.Zip%2A> para que esto ocurra, así que agregue el código siguiente a continuación:</span><span class="sxs-lookup"><span data-stu-id="d628f-350">The following code uses the <xref:System.Linq.Enumerable.Zip%2A> method to make that happen, so add that code next:</span></span>

[!code-csharp[BuildTuples](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#BuildSentimentPredictionPairs "Build the pairs of sentiment data and predictions")]

<span data-ttu-id="d628f-351">Ahora que ha combinado `SentimentText` y `Sentiment` en una clase, puede mostrar los resultados utilizando el método <xref:System.Console.WriteLine?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="d628f-351">Now that you've combined the `SentimentText` and `Sentiment` into a class, you can display the results using the <xref:System.Console.WriteLine?displayProperty=nameWithType> method:</span></span>

[!code-csharp[DisplayPredictions](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DisplayResults "Display the predictions")]

<span data-ttu-id="d628f-352">Debido a que los nombres de elementos de tupla inferidos son una característica nueva en C# 7.1 y la versión de lenguaje predeterminada del proyecto es C# 7.0, debe cambiar la versión del lenguaje a C# 7.1 o superior.</span><span class="sxs-lookup"><span data-stu-id="d628f-352">Because inferred tuple element names are a new feature in C# 7.1 and the default language version of the project is C# 7.0, you need to change the language version to C# 7.1 or higher.</span></span>
<span data-ttu-id="d628f-353">Para ello, haga clic con el botón derecho en el nodo del proyecto en el **Explorador de soluciones** y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d628f-353">To do that, right-click on the project node in **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="d628f-354">Seleccione la pestaña **Compilar** y, después, el botón **Opciones avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="d628f-354">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="d628f-355">En la lista desplegable, seleccione **C# 7.1** (o una versión superior).</span><span class="sxs-lookup"><span data-stu-id="d628f-355">In the dropdown, select  **C# 7.1** (or a higher version).</span></span> <span data-ttu-id="d628f-356">Seleccione el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d628f-356">Select the **OK** button.</span></span>

## <a name="results"></a><span data-ttu-id="d628f-357">Resultados</span><span class="sxs-lookup"><span data-stu-id="d628f-357">Results</span></span>

<span data-ttu-id="d628f-358">Los resultados deberían ser similares a los indicados a continuación.</span><span class="sxs-lookup"><span data-stu-id="d628f-358">Your results should be similar to the following.</span></span> <span data-ttu-id="d628f-359">A medida que la canalización procesa, muestra mensajes.</span><span class="sxs-lookup"><span data-stu-id="d628f-359">As the pipeline processes, it displays messages.</span></span> <span data-ttu-id="d628f-360">Puede ver las advertencias o mensajes de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="d628f-360">You may see warnings, or processing messages.</span></span> <span data-ttu-id="d628f-361">Se han quitado de los siguientes resultados para mayor claridad.</span><span class="sxs-lookup"><span data-stu-id="d628f-361">These have been removed from the following results for clarity.</span></span>

```console
Model quality metrics evaluation
--------------------------------
Accuracy: 79.14%
Auc: 86.27%
F1Score: 80.60%

=============== End of model evaluation ===============
The model is saved to C:\Tutorials\SentimentAnalysis\bin\Debug\netcoreapp2.1\Data\Model.zip

=============== Prediction Test of model with a single sample and test dataset ===============

Sentiment: This was a very bad steak | Prediction: Negative | Probability: 0.4641322
=============== End of Predictions ===============


=============== Prediction Test of loaded model with a multiple samples ===============

Sentiment: This was a horrible meal | Prediction: Negative | Probability: 0.1391833
Sentiment: I love this spaghetti. | Prediction: Positive | Probability: 0.9819039
=============== End of predictions ===============

=============== End of process ===============
Press any key to continue . . .

```

<span data-ttu-id="d628f-362">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="d628f-362">Congratulations!</span></span> <span data-ttu-id="d628f-363">Ya ha creado correctamente un modelo de aprendizaje automático para clasificar y predecir los sentimientos de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="d628f-363">You've now successfully built a machine learning model for classifying and predicting messages sentiment.</span></span> 

<span data-ttu-id="d628f-364">La creación de modelos correctos es un proceso iterativo.</span><span class="sxs-lookup"><span data-stu-id="d628f-364">Building successful models is an iterative process.</span></span> <span data-ttu-id="d628f-365">Este modelo tiene una calidad inicial más baja, ya que el tutorial utiliza pequeños conjuntos de datos para proporcionar un entrenamiento rápido del modelo.</span><span class="sxs-lookup"><span data-stu-id="d628f-365">This model has initial lower quality as the tutorial uses small datasets to provide quick model training.</span></span> <span data-ttu-id="d628f-366">Si no está satisfecho con la calidad del modelo, puede intentar mejorarlo proporcionando conjuntos de datos de entrenamiento más grandes o eligiendo algoritmos de entrenamiento distintos con diferentes hiperparámetros para cada algoritmo.</span><span class="sxs-lookup"><span data-stu-id="d628f-366">If you aren't satisfied with the model quality, you can try to improve it by providing larger training datasets or by choosing different training algorithms with different hyper-parameters for each algorithm.</span></span>

<span data-ttu-id="d628f-367">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).</span><span class="sxs-lookup"><span data-stu-id="d628f-367">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d628f-368">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="d628f-368">Next steps</span></span>

<span data-ttu-id="d628f-369">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="d628f-369">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="d628f-370">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="d628f-370">Understand the problem</span></span>
> * <span data-ttu-id="d628f-371">Seleccionar el algoritmo de aprendizaje automático adecuado</span><span class="sxs-lookup"><span data-stu-id="d628f-371">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="d628f-372">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="d628f-372">Prepare your data</span></span>
> * <span data-ttu-id="d628f-373">Transformar los datos</span><span class="sxs-lookup"><span data-stu-id="d628f-373">Transform the data</span></span>
> * <span data-ttu-id="d628f-374">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="d628f-374">Train the model</span></span>
> * <span data-ttu-id="d628f-375">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="d628f-375">Evaluate the model</span></span>
> * <span data-ttu-id="d628f-376">Predecir con el modelo entrenado</span><span class="sxs-lookup"><span data-stu-id="d628f-376">Predict with the trained model</span></span>
> * <span data-ttu-id="d628f-377">Implementar y predecir con un modelo cargado</span><span class="sxs-lookup"><span data-stu-id="d628f-377">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="d628f-378">Siga con el siguiente tutorial para obtener más información</span><span class="sxs-lookup"><span data-stu-id="d628f-378">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="d628f-379">Clasificación de problemas</span><span class="sxs-lookup"><span data-stu-id="d628f-379">Issue Classification</span></span>](github-issue-classification.md)
