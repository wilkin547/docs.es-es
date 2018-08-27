---
title: Uso de ML.NET en un escenario de clasificación binaria de análisis de sentimiento
description: Descubra cómo usar ML.NET en un escenario de clasificación binaria para aprender a usar la predicción de sentimientos a fin de tomar las medidas oportunas.
ms.date: 06/04/2018
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 57ade448f5773bee3474cb46bec8ad33e3afbee3
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "43000393"
---
# <a name="tutorial-use-mlnet-in-a-sentiment-analysis-binary-classification-scenario"></a><span data-ttu-id="80587-103">Tutorial: Uso de ML.NET en un escenario de clasificación binaria de análisis de sentimiento</span><span class="sxs-lookup"><span data-stu-id="80587-103">Tutorial: Use ML.NET in a sentiment analysis binary classification scenario</span></span>

> [!NOTE]
> <span data-ttu-id="80587-104">Este tema hace referencia a ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios.</span><span class="sxs-lookup"><span data-stu-id="80587-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="80587-105">Para obtener más información, visite [la introducción de ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="80587-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="80587-106">En este tutorial de ejemplo se muestra cómo utilizar ML.NET para crear un clasificador de sentimientos a través de una aplicación de consola de .NET Core con C# en Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="80587-106">This sample tutorial illustrates using ML.NET to create a sentiment classifier via a .NET Core console application using C# in Visual Studio 2017.</span></span>

<span data-ttu-id="80587-107">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="80587-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="80587-108">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="80587-108">Understand the problem</span></span>
> * <span data-ttu-id="80587-109">Seleccionar la tarea de aprendizaje automático adecuada</span><span class="sxs-lookup"><span data-stu-id="80587-109">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="80587-110">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="80587-110">Prepare your data</span></span>
> * <span data-ttu-id="80587-111">Crear la canalización de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="80587-111">Create the learning pipeline</span></span>
> * <span data-ttu-id="80587-112">Cargar un clasificador</span><span class="sxs-lookup"><span data-stu-id="80587-112">Load a classifier</span></span>
> * <span data-ttu-id="80587-113">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="80587-113">Train the model</span></span>
> * <span data-ttu-id="80587-114">Evaluar el modelo con otro conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="80587-114">Evaluate the model with a different dataset</span></span>
> * <span data-ttu-id="80587-115">Predecir los resultados de datos de prueba con el modelo</span><span class="sxs-lookup"><span data-stu-id="80587-115">Predict the test data outcomes with the model</span></span>

## <a name="sentiment-analysis-sample-overview"></a><span data-ttu-id="80587-116">Información general del ejemplo de análisis de sentimiento</span><span class="sxs-lookup"><span data-stu-id="80587-116">Sentiment analysis sample overview</span></span>

<span data-ttu-id="80587-117">El ejemplo es una aplicación de consola que utiliza ML.NET para entrenar un modelo que clasifica y predice un sentimiento como positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="80587-117">The sample is a console app that uses ML.NET to train a model that classifies and predicts sentiment as either positive or negative.</span></span> <span data-ttu-id="80587-118">También se evalúa el modelo con un segundo conjunto de datos para realizar el análisis de calidad.</span><span class="sxs-lookup"><span data-stu-id="80587-118">It also evaluates the model with a second dataset for quality analysis.</span></span> <span data-ttu-id="80587-119">Los conjuntos de datos de sentimientos proceden del proyecto WikiDetox.</span><span class="sxs-lookup"><span data-stu-id="80587-119">The sentiment datasets are from the WikiDetox project.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="80587-120">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="80587-120">Prerequisites</span></span>

* <span data-ttu-id="80587-121">[Visual Studio 2017 15.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.</span><span class="sxs-lookup"><span data-stu-id="80587-121">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* <span data-ttu-id="80587-122">El [archivo separado por tabulaciones de datos de la línea detox de Wikipedia (wikiPedia-detox-250-line-data.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv).</span><span class="sxs-lookup"><span data-stu-id="80587-122">The [Wikipedia detox line data tab separated file (wikiPedia-detox-250-line-data.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv).</span></span>
* <span data-ttu-id="80587-123">El [archivo separado por tabulaciones de pruebas de la línea detox de Wikipedia (wikipedia-detox-250-line-test.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv).</span><span class="sxs-lookup"><span data-stu-id="80587-123">The [Wikipedia detox line test tab separated file (wikipedia-detox-250-line-test.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv).</span></span>

## <a name="machine-learning-workflow"></a><span data-ttu-id="80587-124">Flujo de trabajo del aprendizaje automático</span><span class="sxs-lookup"><span data-stu-id="80587-124">Machine learning workflow</span></span>

<span data-ttu-id="80587-125">En este tutorial se sigue un flujo de trabajo de aprendizaje automático que permite que el proceso avance de manera ordenada.</span><span class="sxs-lookup"><span data-stu-id="80587-125">This tutorial follows a machine learning workflow that enables the process to move in an orderly fashion.</span></span>

<span data-ttu-id="80587-126">Las fases del flujo de trabajo son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="80587-126">The workflow phases are as follows:</span></span>

1. <span data-ttu-id="80587-127">**Entender el problema**</span><span class="sxs-lookup"><span data-stu-id="80587-127">**Understand the problem**</span></span>
2. <span data-ttu-id="80587-128">**Ingerir los datos**</span><span class="sxs-lookup"><span data-stu-id="80587-128">**Ingest the data**</span></span>
3. <span data-ttu-id="80587-129">**Procesar previamente los datos y aplicar ingeniería a las características**</span><span class="sxs-lookup"><span data-stu-id="80587-129">**Data preprocess and feature engineering**</span></span>
4. <span data-ttu-id="80587-130">**Entrenar y predecir el modelo**</span><span class="sxs-lookup"><span data-stu-id="80587-130">**Train and predict the model**</span></span>
5. <span data-ttu-id="80587-131">**Evaluar el modelo**</span><span class="sxs-lookup"><span data-stu-id="80587-131">**Evaluate the model**</span></span>
6. <span data-ttu-id="80587-132">**Poner en marcha el modelo**</span><span class="sxs-lookup"><span data-stu-id="80587-132">**Model operationalization**</span></span>

### <a name="understand-the-problem"></a><span data-ttu-id="80587-133">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="80587-133">Understand the problem</span></span>

<span data-ttu-id="80587-134">Primero debe entender el problema, de manera que pueda dividirlo en partes que admitan la compilación y el entrenamiento del problema.</span><span class="sxs-lookup"><span data-stu-id="80587-134">You first need to understand the problem, so you can break it down to parts that can support building and training the model.</span></span> <span data-ttu-id="80587-135">La división del problema en partes le permite predecir y evaluar los resultados.</span><span class="sxs-lookup"><span data-stu-id="80587-135">Breaking the problem down you to predict and evaluate the results.</span></span>

<span data-ttu-id="80587-136">El problema en este tutorial es comprender los sentimientos de los comentarios del sitio web entrantes para tomar las medidas oportunas.</span><span class="sxs-lookup"><span data-stu-id="80587-136">The problem for this tutorial is to understand incoming website comment sentiment to take the appropriate action.</span></span>

<span data-ttu-id="80587-137">Puede dividir el problema en texto de sentimientos y valor de sentimientos para los datos con los que desea entrenar el modelo, y un valor de sentimiento de predicción que puede evaluar y luego usar de manera operativa.</span><span class="sxs-lookup"><span data-stu-id="80587-137">You can break down the problem to the sentiment text and sentiment value for the data you want to train the model with, and a predicted sentiment value that you can evaluate and then use operationally.</span></span>

<span data-ttu-id="80587-138">A continuación, necesita **determinar** el sentimiento, lo que le ayuda con la selección de tareas de aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="80587-138">You then need to **determine** the sentiment, which helps you with the machine learning task selection.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="80587-139">Seleccionar la tarea de aprendizaje automático adecuada</span><span class="sxs-lookup"><span data-stu-id="80587-139">Select the appropriate machine learning task</span></span>

<span data-ttu-id="80587-140">Con este problema, tiene constancia de los siguientes hechos:</span><span class="sxs-lookup"><span data-stu-id="80587-140">With this problem, you know the following facts:</span></span>

<span data-ttu-id="80587-141">Datos de entrenamiento: los comentarios del sitio web pueden ser positivos o negativos (**sentimiento**).</span><span class="sxs-lookup"><span data-stu-id="80587-141">Training data: website comments can be positive or negative (**sentiment**).</span></span>
<span data-ttu-id="80587-142">Prediga el **sentimiento** de un comentario de sitio web nuevo, positivo o negativo, como en los ejemplos siguientes:</span><span class="sxs-lookup"><span data-stu-id="80587-142">Predict the **sentiment** of a new website comment, either positive or negative, such as in the following examples:</span></span>

* <span data-ttu-id="80587-143">Evite agregar elementos sin sentido a Wikipedia.</span><span class="sxs-lookup"><span data-stu-id="80587-143">Please refrain from adding nonsense to Wikipedia.</span></span>
* <span data-ttu-id="80587-144">Él es el mejor, y el artículo debe reflejarlo.</span><span class="sxs-lookup"><span data-stu-id="80587-144">He is the best, and the article should say that.</span></span>

<span data-ttu-id="80587-145">La tarea de aprendizaje automático de clasificación es ideal para este escenario.</span><span class="sxs-lookup"><span data-stu-id="80587-145">The classification machine learning task is best suited for this scenario.</span></span>

### <a name="about-the-classification-task"></a><span data-ttu-id="80587-146">Acerca de la tarea de clasificación</span><span class="sxs-lookup"><span data-stu-id="80587-146">About the classification task</span></span>

<span data-ttu-id="80587-147">La clasificación es una tarea de aprendizaje automático que usa datos para **determinar** la categoría, el tipo o la clase de un elemento o fila de datos.</span><span class="sxs-lookup"><span data-stu-id="80587-147">Classification is a machine learning task that uses data to **determine** the category, type, or class of an item or row of data.</span></span> <span data-ttu-id="80587-148">Por ejemplo, puede utilizar la clasificación para:</span><span class="sxs-lookup"><span data-stu-id="80587-148">For example, you can use classification to:</span></span>

* <span data-ttu-id="80587-149">Identificar un sentimiento como positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="80587-149">Identify sentiment as positive or negative.</span></span>
* <span data-ttu-id="80587-150">Clasificar correo electrónico como correo no deseado o correo válido.</span><span class="sxs-lookup"><span data-stu-id="80587-150">Classify email as spam, junk, or good.</span></span>
* <span data-ttu-id="80587-151">Determinar si la muestra de laboratorio de un paciente es cancerosa.</span><span class="sxs-lookup"><span data-stu-id="80587-151">Determine whether a patient's lab sample is cancerous.</span></span>
* <span data-ttu-id="80587-152">Categorizar a los clientes por su propensión a responder a una campaña de ventas.</span><span class="sxs-lookup"><span data-stu-id="80587-152">Categorize customers by their propensity to respond to a sales campaign.</span></span>

<span data-ttu-id="80587-153">Las tareas de clasificación son a menudo de uno de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="80587-153">Classification tasks are frequently one of the following types:</span></span>

* <span data-ttu-id="80587-154">Binario: A o B.</span><span class="sxs-lookup"><span data-stu-id="80587-154">Binary: either A or B.</span></span>
* <span data-ttu-id="80587-155">Multiclase: varias categorías que se pueden predecir mediante el uso de un único modelo.</span><span class="sxs-lookup"><span data-stu-id="80587-155">Multiclass: multiple categories that can be predicted by using a single model.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="80587-156">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="80587-156">Create a console application</span></span>

1. <span data-ttu-id="80587-157">Abra Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="80587-157">Open Visual Studio 2017.</span></span> <span data-ttu-id="80587-158">Seleccione **Archivo** > **Nuevo** > **Proyecto** de la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="80587-158">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="80587-159">En el cuadro de diálogo *Nuevo proyecto*\*, seleccione el nodo **Visual C#** seguido del nodo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="80587-159">In the *New Project*\* dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="80587-160">Después, seleccione la plantilla del proyecto **Aplicación de consola (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="80587-160">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="80587-161">En el cuadro de texto **Nombre**, escriba "SentimentAnalysis" y después haga clic en el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="80587-161">In the **Name** text box, type "SentimentAnalysis" and then select the **OK** button.</span></span>

2. <span data-ttu-id="80587-162">Cree un directorio denominado *Datos* en el proyecto para guardar los archivos del conjunto de datos:</span><span class="sxs-lookup"><span data-stu-id="80587-162">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="80587-163">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **Nueva carpeta**.</span><span class="sxs-lookup"><span data-stu-id="80587-163">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="80587-164">Escriba "Datos" y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="80587-164">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="80587-165">Instale el **paquete NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="80587-165">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="80587-166">En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="80587-166">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="80587-167">Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.ML**, seleccione ese paquete en la lista y seleccione el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="80587-167">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="80587-168">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="80587-168">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="80587-169">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="80587-169">Prepare your data</span></span>

1. <span data-ttu-id="80587-170">Descargue los conjuntos de datos [WikiPedia detox-250-line-data.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv) y [wikipedia-detox-250-line-test.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv) y guárdelos en la carpeta *Datos* creada previamente.</span><span class="sxs-lookup"><span data-stu-id="80587-170">Download the [WikiPedia detox-250-line-data.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv) and the [wikipedia-detox-250-line-test.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv) data sets and save them to the *Data* folder previously created.</span></span> <span data-ttu-id="80587-171">El primer conjunto de datos entrena el modelo de aprendizaje automático y el segundo puede usarse para evaluar su grado de precisión.</span><span class="sxs-lookup"><span data-stu-id="80587-171">The first dataset trains the machine learning model and the second can be used to evaluate how accurate your model is.</span></span>

2. <span data-ttu-id="80587-172">En el Explorador de soluciones, haga clic con el botón secundario en cada uno de los archivos \*.tsv y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="80587-172">In Solution Explorer, right-click each of the \*.tsv files and select **Properties**.</span></span> <span data-ttu-id="80587-173">En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.</span><span class="sxs-lookup"><span data-stu-id="80587-173">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="80587-174">Crear clases y definir rutas de acceso</span><span class="sxs-lookup"><span data-stu-id="80587-174">Create classes and define paths</span></span>

<span data-ttu-id="80587-175">Agregue las siguientes instrucciones `using` adicionales a la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="80587-175">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#1 "Add necessary usings")]

<span data-ttu-id="80587-176">Debe crear tres campos globales para contener las rutas de acceso a los archivos descargados recientemente:</span><span class="sxs-lookup"><span data-stu-id="80587-176">You need to create three global fields to hold the paths to the recently downloaded files:</span></span>

* <span data-ttu-id="80587-177">`_dataPath` tiene la ruta de acceso al conjunto de datos utilizado para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="80587-177">`_dataPath` has the path to the dataset used to train the model.</span></span>
* <span data-ttu-id="80587-178">`_testDataPath` tiene la ruta de acceso al conjunto de datos utilizado para evaluar el modelo.</span><span class="sxs-lookup"><span data-stu-id="80587-178">`_testDataPath` has the path to the dataset used to evaluate the model.</span></span>
* <span data-ttu-id="80587-179">`_modelPath` tiene la ruta de acceso donde se guarda el modelo entrenado.</span><span class="sxs-lookup"><span data-stu-id="80587-179">`_modelPath` has the path where the trained model is saved.</span></span>

<span data-ttu-id="80587-180">Agregue el código siguiente a la línea justo encima del método `Main` para especificar las rutas de acceso:</span><span class="sxs-lookup"><span data-stu-id="80587-180">Add the following code to the line right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Declare file variables](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#2 "Declare variables to store data files")]

<span data-ttu-id="80587-181">Debe crear algunas clases para los datos de entrada y las predicciones.</span><span class="sxs-lookup"><span data-stu-id="80587-181">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="80587-182">Agregue una nueva clase a su proyecto:</span><span class="sxs-lookup"><span data-stu-id="80587-182">Add a new class to your project:</span></span>

1. <span data-ttu-id="80587-183">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="80587-183">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="80587-184">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="80587-184">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="80587-185">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="80587-185">Then, select the **Add** button.</span></span>

    <span data-ttu-id="80587-186">Se abre el archivo *SentimentData.cs* en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="80587-186">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="80587-187">Agregue la siguiente instrucción `using` a la parte superior de *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="80587-187">Add the following `using` statement to the top of *SentimentData.cs*:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#1 "Add necessary usings")]

<span data-ttu-id="80587-188">Quite la definición de clase existente y agregue el código siguiente, que tiene dos clases `SentimentData` y `SentimentPrediction`, al archivo *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="80587-188">Remove the existing class definition and add the following code, which has two classes `SentimentData` and `SentimentPrediction`, to the *SentimentData.cs* file:</span></span>

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#2 "Declare data record types")]

<span data-ttu-id="80587-189">`SentimentData` es la clase de conjunto de datos de entrada y tiene un `float` (`Sentiment`) que tiene un valor para el sentimiento positivo o negativo, y una cadena para el comentario (`SentimentText`).</span><span class="sxs-lookup"><span data-stu-id="80587-189">`SentimentData` is the input dataset class and has a `float` (`Sentiment`) that has a value for sentiment of either positive or negative, and a string for the comment (`SentimentText`).</span></span> <span data-ttu-id="80587-190">Ambos campos tienen `Column` atributos adjuntos a ellos.</span><span class="sxs-lookup"><span data-stu-id="80587-190">Both fields have `Column` attributes attached to them.</span></span> <span data-ttu-id="80587-191">Este atributo describe el orden de cada campo en el archivo de datos, y que es el campo `Label`.</span><span class="sxs-lookup"><span data-stu-id="80587-191">This attribute describes the order of each field in the data file, and which is the `Label` field.</span></span> <span data-ttu-id="80587-192">`SentimentPrediction` es la clase usada para la predicción una vez entrenado el modelo.</span><span class="sxs-lookup"><span data-stu-id="80587-192">`SentimentPrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="80587-193">Tiene un valor booleano único (`Sentiment`) y un atributo `PredictedLabel` `ColumnName`.</span><span class="sxs-lookup"><span data-stu-id="80587-193">It has a single boolean (`Sentiment`) and a `PredictedLabel` `ColumnName` attribute.</span></span> <span data-ttu-id="80587-194">`Label` se usa para crear y entrenar el modelo, y se usa también con un segundo conjunto de datos para evaluar el modelo.</span><span class="sxs-lookup"><span data-stu-id="80587-194">The `Label` is used to create and train the model, and it's also used with a second dataset to evaluate the model.</span></span> <span data-ttu-id="80587-195">`PredictedLabel` se usa durante la predicción y la evaluación.</span><span class="sxs-lookup"><span data-stu-id="80587-195">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="80587-196">Para la evaluación, se utiliza una entrada con los datos de entrenamiento, los valores de predicción y el modelo.</span><span class="sxs-lookup"><span data-stu-id="80587-196">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="80587-197">En el archivo *Program.cs*, cambie la firma del método `Main` reemplazando `void` por `async Task`, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="80587-197">In the *Program.cs* file, change the `Main` method signature by replacing `void` with `async Task`, as in the following example:</span></span>

```csharp
static async Task Main(string[] args) 
{

}
```

<span data-ttu-id="80587-198">Se agrega `async` a `Main` con un tipo de valor devuelto <xref:System.Threading.Tasks.Task> porque más adelante se guarda el modelo en un archivo ZIP, y el programa debe esperar hasta que finalice la tarea externa.</span><span class="sxs-lookup"><span data-stu-id="80587-198">You add `async` to `Main` with a <xref:System.Threading.Tasks.Task> return type because you're saving the model to a zip file later, and the program needs to wait until that external task completes.</span></span>

> [!NOTE]
> <span data-ttu-id="80587-199">Un método *async main* permite usar `await` en el método `Main`.</span><span class="sxs-lookup"><span data-stu-id="80587-199">An *async main* method enables you to use `await` in your `Main` method.</span></span> <span data-ttu-id="80587-200">Para obtener más información, consulte el tema [async main](../../../docs/csharp/programming-guide/main-and-command-args/index.md) en la guía de programación de C#.</span><span class="sxs-lookup"><span data-stu-id="80587-200">For more information, see the [async main](../../../docs/csharp/programming-guide/main-and-command-args/index.md) topic in the C# programming guide.</span></span>

<span data-ttu-id="80587-201">Reemplace la línea `Console.WriteLine("Hello World!")` por el código siguiente en el método `Main`:</span><span class="sxs-lookup"><span data-stu-id="80587-201">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[Train](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#3 "Train your model")]

<span data-ttu-id="80587-202">El método `Train` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="80587-202">The `Train` method executes the following tasks:</span></span>

* <span data-ttu-id="80587-203">Carga o ingiere los datos.</span><span class="sxs-lookup"><span data-stu-id="80587-203">Loads or ingests the data.</span></span>
* <span data-ttu-id="80587-204">Preprocesa y caracteriza los datos.</span><span class="sxs-lookup"><span data-stu-id="80587-204">Preprocesses and featurizes the data.</span></span>
* <span data-ttu-id="80587-205">Entrena el modelo.</span><span class="sxs-lookup"><span data-stu-id="80587-205">Trains the model.</span></span>
* <span data-ttu-id="80587-206">Predice sentimientos en función de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="80587-206">Predicts sentiment based on test data.</span></span>

<span data-ttu-id="80587-207">Cree el método `Train`, justo después del método `Main`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="80587-207">Create the `Train` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static async Task<PredictionModel<SentimentData, SentimentPrediction>> Train()
{

}
```

## <a name="ingest-the-data"></a><span data-ttu-id="80587-208">Ingerir los datos</span><span class="sxs-lookup"><span data-stu-id="80587-208">Ingest the data</span></span>

<span data-ttu-id="80587-209">Inicialice una nueva instancia de <xref:Microsoft.ML.LearningPipeline> que incluirá la carga de datos, el procesamiento y la caracterización de los datos y el modelo.</span><span class="sxs-lookup"><span data-stu-id="80587-209">Initialize a new instance of <xref:Microsoft.ML.LearningPipeline> that will include the data loading, data processing/featurization, and model.</span></span> <span data-ttu-id="80587-210">Agregue el código siguiente a la primera línea del método `Train`:</span><span class="sxs-lookup"><span data-stu-id="80587-210">Add the following code as the first line of the `Train` method:</span></span>

[!code-csharp[LearningPipeline](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#5 "Create a learning pipeline")]

<span data-ttu-id="80587-211">El objeto <xref:Microsoft.ML.Data.TextLoader> es la primera parte de la canalización y carga los datos del archivo de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="80587-211">The <xref:Microsoft.ML.Data.TextLoader> object is the first part of the pipeline, and loads the training file data.</span></span>

[!code-csharp[TextLoader](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#6 "Add a text loader to the pipeline")]

## <a name="data-preprocess-and-feature-engineering"></a><span data-ttu-id="80587-212">Procesar previamente los datos y aplicar ingeniería a las características</span><span class="sxs-lookup"><span data-stu-id="80587-212">Data preprocess and feature engineering</span></span>

<span data-ttu-id="80587-213">El procesamiento previo y la limpieza de datos son tareas importantes que se producen antes de que un conjunto de datos se utilice de forma eficaz para el aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="80587-213">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span> <span data-ttu-id="80587-214">Los datos sin procesar contienen a menudo ruido y son poco de fiar; además, es posible que les falten valores.</span><span class="sxs-lookup"><span data-stu-id="80587-214">Raw data is often noisy and unreliable, and may be missing values.</span></span> <span data-ttu-id="80587-215">El uso de datos sin estas tareas de modelado puede producir resultados engañosos.</span><span class="sxs-lookup"><span data-stu-id="80587-215">Using data without these modeling tasks can produce misleading results.</span></span> <span data-ttu-id="80587-216">Las canalizaciones de transformación de ML.NET le permiten crear un conjunto personalizado de transformaciones que se aplican a los datos antes del entrenamiento o la prueba.</span><span class="sxs-lookup"><span data-stu-id="80587-216">ML.NET's transform pipelines allow you to compose a custom set of transforms that are applied to your data before training or testing.</span></span> <span data-ttu-id="80587-217">El propósito principal de las transformaciones es la caracterización de datos.</span><span class="sxs-lookup"><span data-stu-id="80587-217">The transforms' primary purpose is for data featurization.</span></span> <span data-ttu-id="80587-218">La ventaja de una canalización de transformación es que, una vez definida, puede guardarla para aplicarla a los datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="80587-218">A transform pipeline's advantage is that after transform pipeline definition, save the pipeline to apply it to test data.</span></span>

<span data-ttu-id="80587-219">Aplique un <xref:Microsoft.ML.Transforms.TextFeaturizer> para convertir la columna `SentimentText` en un [vector numérico](../resources/glossary.md#numerical-feature-vector) llamado `Features` utilizado por el algoritmo de aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="80587-219">Apply a <xref:Microsoft.ML.Transforms.TextFeaturizer> to convert the `SentimentText` column into a [numeric vector](../resources/glossary.md#numerical-feature-vector) called `Features` used by the machine learning algorithm.</span></span> <span data-ttu-id="80587-220">Este es el paso de preprocesamiento o caracterización.</span><span class="sxs-lookup"><span data-stu-id="80587-220">This is the preprocessing/featurization step.</span></span> <span data-ttu-id="80587-221">El uso de componentes adicionales disponibles en ML.NET permite conseguir mejores resultados con el modelo.</span><span class="sxs-lookup"><span data-stu-id="80587-221">Using additional components available in ML.NET can enable better results with your model.</span></span> <span data-ttu-id="80587-222">Agregue `TextFeaturizer` a la canalización como la siguiente línea de código:</span><span class="sxs-lookup"><span data-stu-id="80587-222">Add `TextFeaturizer` to the pipeline as the next line of code:</span></span>

[!code-csharp[TextFeaturizer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#7 "Add a TextFeaturizer to the pipeline")]

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="80587-223">Elegir un algoritmo de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="80587-223">Choose a learning algorithm</span></span>

<span data-ttu-id="80587-224">El objeto <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier> es un aprendiz de árbol de decisión que usará en esta canalización.</span><span class="sxs-lookup"><span data-stu-id="80587-224">The <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier> object is a decision tree learner you'll use in this pipeline.</span></span> <span data-ttu-id="80587-225">De manera similar al paso de la caracterización, probar diferentes aprendices disponibles en ML.NET y cambiar sus parámetros genera resultados diferentes.</span><span class="sxs-lookup"><span data-stu-id="80587-225">Similar to the featurization step, trying out different learners available in ML.NET and changing their parameters leads to different results.</span></span> <span data-ttu-id="80587-226">Para la optimización, puede establecer [hiperparámetros](../resources/glossary.md#hyperparameter) como <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.NumTrees>, <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.NumLeaves> y <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.MinDocumentsInLeafs>.</span><span class="sxs-lookup"><span data-stu-id="80587-226">For tuning, you can set [hyperparameters](../resources/glossary.md#hyperparameter) like <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.NumTrees>, <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.NumLeaves>, and <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.MinDocumentsInLeafs>.</span></span> <span data-ttu-id="80587-227">Estos hiperparámetros se establecen antes de que algo afecte al modelo y son específicos del modelo.</span><span class="sxs-lookup"><span data-stu-id="80587-227">These hyperparameters are set before anything affects the model and are model-specific.</span></span> <span data-ttu-id="80587-228">Se utilizan para ajustar el árbol de decisiones para el rendimiento, por lo que los valores más grandes pueden afectar negativamente al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="80587-228">They're used to tune the decision tree for performance, so larger values can negatively impact performance.</span></span>

<span data-ttu-id="80587-229">Agregue el código siguiente al método `Train`:</span><span class="sxs-lookup"><span data-stu-id="80587-229">Add the following code to the `Train` method:</span></span>

[!code-csharp[BinaryClassifier](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#8 "Add a fast binary tree classifier")]

## <a name="train-the-model"></a><span data-ttu-id="80587-230">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="80587-230">Train the model</span></span>

<span data-ttu-id="80587-231">Se entrena el modelo, <xref:Microsoft.ML.PredictionModel%602>, en función del conjunto de datos que se haya cargado y transformado.</span><span class="sxs-lookup"><span data-stu-id="80587-231">You train the model, <xref:Microsoft.ML.PredictionModel%602>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="80587-232">`pipeline.Train<SentimentData, SentimentPrediction>()` entrena la canalización (carga los datos, entrena al caracterizador y el aprendiz).</span><span class="sxs-lookup"><span data-stu-id="80587-232">`pipeline.Train<SentimentData, SentimentPrediction>()` trains the pipeline (loads the data, trains the featurizer and learner).</span></span> <span data-ttu-id="80587-233">El experimento no se ejecuta hasta que esto suceda.</span><span class="sxs-lookup"><span data-stu-id="80587-233">The experiment is not executed until this happens.</span></span>

<span data-ttu-id="80587-234">Agregue el código siguiente al método `Train`:</span><span class="sxs-lookup"><span data-stu-id="80587-234">Add the following code to the `Train` method:</span></span>

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#9 "Train the model")]

### <a name="save-and-return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="80587-235">Guardar y devolver el modelo entrenado para su uso para la evaluación</span><span class="sxs-lookup"><span data-stu-id="80587-235">Save and Return the model trained to use for evaluation</span></span>

<span data-ttu-id="80587-236">En este punto, tiene un modelo que se puede integrar en cualquiera de las aplicaciones de .NET nuevas o existentes.</span><span class="sxs-lookup"><span data-stu-id="80587-236">At this point, you have a model that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="80587-237">Para guardar el modelo en un archivo .zip antes de devolverlo, agregue este código a la línea siguiente en `Train`:</span><span class="sxs-lookup"><span data-stu-id="80587-237">To save your model to a .zip file before returning, add the following code to the next line in `Train`:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#10 "Save the model")]

<span data-ttu-id="80587-238">Devuelva el modelo al final del método `Train`.</span><span class="sxs-lookup"><span data-stu-id="80587-238">Return the model at the end of the `Train` method.</span></span>

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#11 "Return the model")]

## <a name="evaluate-the-model"></a><span data-ttu-id="80587-239">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="80587-239">Evaluate the model</span></span>

<span data-ttu-id="80587-240">Ahora que ha creado y entrenado el modelo, debe evaluarlo con otro conjunto de datos para el control de calidad y la validación.</span><span class="sxs-lookup"><span data-stu-id="80587-240">Now that you've created and trained the model, you need to evaluate it with a different dataset for quality assurance and validation.</span></span> <span data-ttu-id="80587-241">En el método `Evaluate`, el modelo creado en `Train` se pasa para ser evaluado.</span><span class="sxs-lookup"><span data-stu-id="80587-241">In the `Evaluate` method, the model created in `Train` is passed in to be evaluated.</span></span> <span data-ttu-id="80587-242">Cree el método `Evaluate`, justo después de `Train`, como en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="80587-242">Create the `Evaluate` method, just after `Train`, as in the following code:</span></span>

```csharp
public static void Evaluate(PredictionModel<SentimentData, SentimentPrediction> model)
{

}
```

<span data-ttu-id="80587-243">El método `Evaluate` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="80587-243">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="80587-244">Carga el conjunto de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="80587-244">Loads the test dataset.</span></span>
* <span data-ttu-id="80587-245">Crea el evaluador binario.</span><span class="sxs-lookup"><span data-stu-id="80587-245">Creates the binary evaluator.</span></span>
* <span data-ttu-id="80587-246">Evalúa el modelo y crea métricas.</span><span class="sxs-lookup"><span data-stu-id="80587-246">Evaluates the model and create metrics.</span></span>
* <span data-ttu-id="80587-247">Muestra las métricas.</span><span class="sxs-lookup"><span data-stu-id="80587-247">Displays the metrics.</span></span>

<span data-ttu-id="80587-248">Agregue una llamada al método nuevo desde el método `Main`, justo debajo de la llamada al método `Train`, utilizando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="80587-248">Add a call to the new method from the `Main` method, right under the `Train` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#12 "Call the Evaluate method")]

<span data-ttu-id="80587-249">La clase <xref:Microsoft.ML.Data.TextLoader> carga el nuevo conjunto de datos de prueba con el mismo esquema.</span><span class="sxs-lookup"><span data-stu-id="80587-249">The <xref:Microsoft.ML.Data.TextLoader> class loads the new test dataset with the same schema.</span></span> <span data-ttu-id="80587-250">Puede evaluar el modelo utilizando este conjunto de datos como una comprobación de calidad.</span><span class="sxs-lookup"><span data-stu-id="80587-250">You can evaluate the model using this dataset as a quality check.</span></span> <span data-ttu-id="80587-251">Agregue el código siguiente al método `Evaluate`:</span><span class="sxs-lookup"><span data-stu-id="80587-251">Add the following code to the `Evaluate` method:</span></span>

[!code-csharp[LoadText](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#13 "Load the test dataset")]

<span data-ttu-id="80587-252">El objeto <xref:Microsoft.ML.Models.BinaryClassificationEvaluator> calcula las métricas de calidad para `PredictionModel` con el conjunto de datos especificado.</span><span class="sxs-lookup"><span data-stu-id="80587-252">The <xref:Microsoft.ML.Models.BinaryClassificationEvaluator> object computes the quality metrics for the `PredictionModel` using the specified dataset.</span></span> <span data-ttu-id="80587-253">Para ver esas métricas, agregue el evaluador como la siguiente línea en el método `Evaluate`, con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="80587-253">To see those metrics, add the evaluator as the next line in the `Evaluate` method, with the following code:</span></span>

[!code-csharp[BinaryEvaluator](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#14 "Create the binary evaluator")]

<span data-ttu-id="80587-254"><xref:Microsoft.ML.Models.BinaryClassificationMetrics> contiene las métricas totales calculadas por evaluadores de clasificación binaria.</span><span class="sxs-lookup"><span data-stu-id="80587-254">The <xref:Microsoft.ML.Models.BinaryClassificationMetrics> contains the overall metrics computed by binary classification evaluators.</span></span> <span data-ttu-id="80587-255">Para mostrar estos elementos a fin de determinar la calidad del modelo, debe obtener primero las métricas.</span><span class="sxs-lookup"><span data-stu-id="80587-255">To display these to determine the quality of the model, you need to get the metrics first.</span></span> <span data-ttu-id="80587-256">Agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="80587-256">Add the following code:</span></span>

[!code-csharp[CreateMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#15 "Evaluate the model and create metrics")]

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="80587-257">Mostrar las métricas para la validación del modelo</span><span class="sxs-lookup"><span data-stu-id="80587-257">Displaying the metrics for model validation</span></span>

<span data-ttu-id="80587-258">Utilice el código siguiente para mostrar las métricas, compartir los resultados y, a continuación, trabajar con ellos:</span><span class="sxs-lookup"><span data-stu-id="80587-258">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#16 "Display selected metrics")]

## <a name="predict-the-test-data-outcomes-with-the-model"></a><span data-ttu-id="80587-259">Predecir los resultados de datos de prueba con el modelo</span><span class="sxs-lookup"><span data-stu-id="80587-259">Predict the test data outcomes with the model</span></span>

<span data-ttu-id="80587-260">Cree el método `Predict`, justo después del método `Evaluate`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="80587-260">Create the `Predict` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
public static void Predict(PredictionModel<SentimentData, SentimentPrediction> model)
{

}
```

<span data-ttu-id="80587-261">El método `Predict` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="80587-261">The `Predict` method executes the following tasks:</span></span>

* <span data-ttu-id="80587-262">Crea datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="80587-262">Creates test data.</span></span>
* <span data-ttu-id="80587-263">Predice sentimientos en función de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="80587-263">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="80587-264">Combina datos de prueba y predicciones para la generación de informes.</span><span class="sxs-lookup"><span data-stu-id="80587-264">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="80587-265">Muestra los resultados de la predicción.</span><span class="sxs-lookup"><span data-stu-id="80587-265">Displays the predicted results.</span></span>

<span data-ttu-id="80587-266">Agregue una llamada al método nuevo desde el método `Main`, justo debajo de la llamada al método `Evaluate`, utilizando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="80587-266">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#17 "Call the Predict method")]

<span data-ttu-id="80587-267">Agregue algunos comentarios para probar las predicciones del modelo entrenado en el método `Predict`:</span><span class="sxs-lookup"><span data-stu-id="80587-267">Add some comments to test the trained model's predictions in the `Predict` method:</span></span>

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#18 "Create test data for predictions")]

<span data-ttu-id="80587-268">Ahora que tiene un modelo, puede utilizarlo para predecir el sentimiento positivo o negativo de los datos de comentarios con el método <xref:Microsoft.ML.PredictionModel.Predict%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="80587-268">Now that you have a model, you can use that to predict the positive or negative sentiment of the comment data using the <xref:Microsoft.ML.PredictionModel.Predict%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="80587-269">Para obtener una predicción, use `Predict` en los nuevos datos.</span><span class="sxs-lookup"><span data-stu-id="80587-269">To get a prediction, use `Predict` on new data.</span></span> <span data-ttu-id="80587-270">Tenga en cuenta que los datos de entrada son una cadena y el modelo incluye la caracterización.</span><span class="sxs-lookup"><span data-stu-id="80587-270">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="80587-271">La canalización está sincronizada durante el entrenamiento y la predicción.</span><span class="sxs-lookup"><span data-stu-id="80587-271">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="80587-272">No fue necesario escribir el código de preprocesamiento o caracterización específicamente para las predicciones, y la misma API se encarga de las predicciones por lotes y puntuales.</span><span class="sxs-lookup"><span data-stu-id="80587-272">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#19 "Create predictions of sentiments")]

### <a name="model-operationalization-prediction"></a><span data-ttu-id="80587-273">Puesta en marcha del modelo: predicción</span><span class="sxs-lookup"><span data-stu-id="80587-273">Model operationalization: prediction</span></span>

<span data-ttu-id="80587-274">Muestre `SentimentText` y la predicción del sentimiento correspondiente para compartir los resultados y actuar en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="80587-274">Display `SentimentText` and corresponding sentiment prediction in order to share the results and act on them accordingly.</span></span> <span data-ttu-id="80587-275">Esto se denomina puesta en marcha, y se utilizan los datos devueltos como parte de las directivas operativas.</span><span class="sxs-lookup"><span data-stu-id="80587-275">This is called operationalization, using the returned data as part of the operational policies.</span></span> <span data-ttu-id="80587-276">Cree un encabezado para los resultados con el código <xref:System.Console.WriteLine?displayProperty=nameWithType> siguiente:</span><span class="sxs-lookup"><span data-stu-id="80587-276">Create a header for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputHeaders](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#20 "Display prediction outputs")]

<span data-ttu-id="80587-277">Antes de mostrar los resultados de la predicción, combine el sentimiento con la predicción para ver el comentario original con su sentimiento de predicción.</span><span class="sxs-lookup"><span data-stu-id="80587-277">Before displaying the predicted results, combine the sentiment and prediction together to see the original comment with its predicted sentiment.</span></span> <span data-ttu-id="80587-278">El siguiente código utiliza el método <xref:System.Linq.Enumerable.Zip%2A> para que esto ocurra, así que agregue el código siguiente a continuación:</span><span class="sxs-lookup"><span data-stu-id="80587-278">The following code uses the <xref:System.Linq.Enumerable.Zip%2A> method to make that happen, so add that code next:</span></span>

[!code-csharp[BuildTuples](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#21 "Build the pairs of sentiment data and predictions")]

<span data-ttu-id="80587-279">Ahora que ha combinado `SentimentText` y `Sentiment` en una clase, puede mostrar los resultados utilizando el método <xref:System.Console.WriteLine?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="80587-279">Now that you've combined the `SentimentText` and `Sentiment` into a class, you can display the results using the <xref:System.Console.WriteLine?displayProperty=nameWithType> method:</span></span>

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#22 "Display the predictions")]

<span data-ttu-id="80587-280">Debido a que los nombres de elementos de tupla inferidos son una característica nueva en C# 7.1 y la versión de lenguaje predeterminada del proyecto es C# 7.0, debe cambiar la versión del lenguaje a C# 7.1 o superior.</span><span class="sxs-lookup"><span data-stu-id="80587-280">Because inferred tuple element names are a new feature in C# 7.1 and the default language version of the project is C# 7.0, you need to change the language version to C# 7.1 or higher.</span></span>
<span data-ttu-id="80587-281">Para ello, haga clic con el botón derecho en el nodo del proyecto en el **Explorador de soluciones** y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="80587-281">To do that, right-click on the project node in **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="80587-282">Seleccione la pestaña **Compilar** y, después, el botón **Opciones avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="80587-282">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="80587-283">En la lista desplegable, seleccione **C# 7.1** (o una versión superior).</span><span class="sxs-lookup"><span data-stu-id="80587-283">In the dropdown, select  **C# 7.1** (or a higher version).</span></span> <span data-ttu-id="80587-284">Seleccione el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="80587-284">Select the **OK** button.</span></span>

## <a name="results"></a><span data-ttu-id="80587-285">Resultados</span><span class="sxs-lookup"><span data-stu-id="80587-285">Results</span></span>

<span data-ttu-id="80587-286">Los resultados deberían ser similares a los indicados a continuación.</span><span class="sxs-lookup"><span data-stu-id="80587-286">Your results should be similar to the following.</span></span> <span data-ttu-id="80587-287">A medida que la canalización procesa, muestra mensajes.</span><span class="sxs-lookup"><span data-stu-id="80587-287">As the pipeline processes, it displays messages.</span></span> <span data-ttu-id="80587-288">Puede ver las advertencias o mensajes de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="80587-288">You may see warnings, or processing messages.</span></span> <span data-ttu-id="80587-289">Se han quitado de los siguientes resultados para mayor claridad.</span><span class="sxs-lookup"><span data-stu-id="80587-289">These have been removed from the following results for clarity.</span></span>

```

PredictionModel quality metrics evaluation
------------------------------------------
Accuracy: 66.67%
Auc: 94.44%
F1Score: 75.00%

Sentiment Predictions
---------------------
Sentiment: Please refrain from adding nonsense to Wikipedia. | Prediction: Negative
Sentiment: He is the best, and the article should say that. | Prediction: Positive

```

<span data-ttu-id="80587-290">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="80587-290">Congratulations!</span></span> <span data-ttu-id="80587-291">Ya ha creado correctamente un modelo de aprendizaje automático para clasificar y predecir los sentimientos de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="80587-291">You've now successfully built a machine learning model for classifying and predicting messages sentiment.</span></span> <span data-ttu-id="80587-292">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).</span><span class="sxs-lookup"><span data-stu-id="80587-292">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="80587-293">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="80587-293">Next steps</span></span>

<span data-ttu-id="80587-294">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="80587-294">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="80587-295">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="80587-295">Understand the problem</span></span>
> * <span data-ttu-id="80587-296">Seleccionar la tarea de aprendizaje automático adecuada</span><span class="sxs-lookup"><span data-stu-id="80587-296">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="80587-297">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="80587-297">Prepare your data</span></span>
> * <span data-ttu-id="80587-298">Crear la canalización de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="80587-298">Create the learning pipeline</span></span>
> * <span data-ttu-id="80587-299">Cargar un clasificador</span><span class="sxs-lookup"><span data-stu-id="80587-299">Load a classifier</span></span>
> * <span data-ttu-id="80587-300">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="80587-300">Train the model</span></span>
> * <span data-ttu-id="80587-301">Evaluar el modelo con otro conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="80587-301">Evaluate the model with a different dataset</span></span>
> * <span data-ttu-id="80587-302">Predecir los resultados de datos de prueba con el modelo</span><span class="sxs-lookup"><span data-stu-id="80587-302">Predict the test data outcomes with the model</span></span>

<span data-ttu-id="80587-303">Siga con el siguiente tutorial para obtener más información</span><span class="sxs-lookup"><span data-stu-id="80587-303">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="80587-304">Predictor de tarifa de taxi</span><span class="sxs-lookup"><span data-stu-id="80587-304">Taxi Fare Predictor</span></span>](taxi-fare.md)
