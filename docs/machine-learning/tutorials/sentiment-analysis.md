---
title: Uso de ML.NET en un escenario de clasificación binaria de análisis de sentimiento
description: Descubra cómo usar ML.NET en un escenario de clasificación binaria para aprender a usar la predicción de sentimientos a fin de tomar las medidas oportunas.
ms.date: 02/15/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: d6d5cae107e25000add5c8430a35131a79696bc2
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2019
ms.locfileid: "56092766"
---
# <a name="tutorial-use-mlnet-in-a-sentiment-analysis-binary-classification-scenario"></a><span data-ttu-id="9555d-103">Tutorial: Uso de ML.NET en un escenario de clasificación binaria de análisis de sentimiento</span><span class="sxs-lookup"><span data-stu-id="9555d-103">Tutorial: Use ML.NET in a sentiment analysis binary classification scenario</span></span>

> [!NOTE]
> <span data-ttu-id="9555d-104">Este tema hace referencia a ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios.</span><span class="sxs-lookup"><span data-stu-id="9555d-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="9555d-105">Para obtener más información, visite [la introducción de ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="9555d-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="9555d-106">En este tutorial de ejemplo se muestra cómo utilizar ML.NET para crear un clasificador de sentimientos a través de una aplicación de consola de .NET Core con C# en Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="9555d-106">This sample tutorial illustrates using ML.NET to create a sentiment classifier via a .NET Core console application using C# in Visual Studio 2017.</span></span>

<span data-ttu-id="9555d-107">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="9555d-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="9555d-108">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="9555d-108">Understand the problem</span></span>
> * <span data-ttu-id="9555d-109">Seleccionar el algoritmo de aprendizaje automático adecuado</span><span class="sxs-lookup"><span data-stu-id="9555d-109">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="9555d-110">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="9555d-110">Prepare your data</span></span>
> * <span data-ttu-id="9555d-111">Transformar los datos</span><span class="sxs-lookup"><span data-stu-id="9555d-111">Transform the data</span></span>
> * <span data-ttu-id="9555d-112">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="9555d-112">Train the model</span></span>
> * <span data-ttu-id="9555d-113">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="9555d-113">Evaluate the model</span></span>
> * <span data-ttu-id="9555d-114">Predecir con el modelo entrenado</span><span class="sxs-lookup"><span data-stu-id="9555d-114">Predict with the trained model</span></span>
> * <span data-ttu-id="9555d-115">Implementar y predecir con un modelo cargado</span><span class="sxs-lookup"><span data-stu-id="9555d-115">Deploy and Predict with a loaded model</span></span>

## <a name="sentiment-analysis-sample-overview"></a><span data-ttu-id="9555d-116">Información general del ejemplo de análisis de sentimiento</span><span class="sxs-lookup"><span data-stu-id="9555d-116">Sentiment analysis sample overview</span></span>

<span data-ttu-id="9555d-117">El ejemplo es una aplicación de consola que utiliza ML.NET para entrenar un modelo que clasifica y predice un sentimiento como positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="9555d-117">The sample is a console app that uses ML.NET to train a model that classifies and predicts sentiment as either positive or negative.</span></span> <span data-ttu-id="9555d-118">También se evalúa el modelo con un segundo conjunto de datos para realizar el análisis de calidad.</span><span class="sxs-lookup"><span data-stu-id="9555d-118">It also evaluates the model with a second dataset for quality analysis.</span></span> <span data-ttu-id="9555d-119">Los conjuntos de datos de sentimientos proceden del proyecto WikiDetox.</span><span class="sxs-lookup"><span data-stu-id="9555d-119">The sentiment datasets are from the WikiDetox project.</span></span>

<span data-ttu-id="9555d-120">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).</span><span class="sxs-lookup"><span data-stu-id="9555d-120">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9555d-121">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9555d-121">Prerequisites</span></span>

* <span data-ttu-id="9555d-122">[Visual Studio 2017 15.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.</span><span class="sxs-lookup"><span data-stu-id="9555d-122">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* <span data-ttu-id="9555d-123">El [archivo separado por tabulaciones de datos de la línea detox de Wikipedia (wikiPedia-detox-250-line-data.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv).</span><span class="sxs-lookup"><span data-stu-id="9555d-123">The [Wikipedia detox line data tab separated file (wikiPedia-detox-250-line-data.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv).</span></span>
* <span data-ttu-id="9555d-124">El [archivo separado por tabulaciones de pruebas de la línea detox de Wikipedia (wikipedia-detox-250-line-test.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv).</span><span class="sxs-lookup"><span data-stu-id="9555d-124">The [Wikipedia detox line test tab separated file (wikipedia-detox-250-line-test.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv).</span></span>

## <a name="machine-learning-workflow"></a><span data-ttu-id="9555d-125">Flujo de trabajo del aprendizaje automático</span><span class="sxs-lookup"><span data-stu-id="9555d-125">Machine learning workflow</span></span>

<span data-ttu-id="9555d-126">En este tutorial se sigue un flujo de trabajo de aprendizaje automático que permite que el proceso avance de manera ordenada.</span><span class="sxs-lookup"><span data-stu-id="9555d-126">This tutorial follows a machine learning workflow that enables the process to move in an orderly fashion.</span></span>

<span data-ttu-id="9555d-127">Las fases del flujo de trabajo son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="9555d-127">The workflow phases are as follows:</span></span>

1. <span data-ttu-id="9555d-128">**Entender el problema**</span><span class="sxs-lookup"><span data-stu-id="9555d-128">**Understand the problem**</span></span>
2. <span data-ttu-id="9555d-129">**Preparar los datos**</span><span class="sxs-lookup"><span data-stu-id="9555d-129">**Prepare your data**</span></span>
   * <span data-ttu-id="9555d-130">**Cargar los datos**</span><span class="sxs-lookup"><span data-stu-id="9555d-130">**Load the data**</span></span>
   * <span data-ttu-id="9555d-131">**Extraer características (transformar los datos)**</span><span class="sxs-lookup"><span data-stu-id="9555d-131">**Extract features (Transform your data)**</span></span>
3. <span data-ttu-id="9555d-132">**Compilar y entrenar**</span><span class="sxs-lookup"><span data-stu-id="9555d-132">**Build and train**</span></span> 
   * <span data-ttu-id="9555d-133">**Entrenar el modelo**</span><span class="sxs-lookup"><span data-stu-id="9555d-133">**Train the model**</span></span>
   * <span data-ttu-id="9555d-134">**Evaluar el modelo**</span><span class="sxs-lookup"><span data-stu-id="9555d-134">**Evaluate the model**</span></span>
4. <span data-ttu-id="9555d-135">**Implementar el modelo**</span><span class="sxs-lookup"><span data-stu-id="9555d-135">**Deploy Model**</span></span>
   * <span data-ttu-id="9555d-136">**Usar el modelo para la predicción**</span><span class="sxs-lookup"><span data-stu-id="9555d-136">**Use the Model to predict**</span></span>

### <a name="understand-the-problem"></a><span data-ttu-id="9555d-137">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="9555d-137">Understand the problem</span></span>

<span data-ttu-id="9555d-138">Primero debe entender el problema, de manera que pueda dividirlo en partes que admitan la compilación y el entrenamiento del problema.</span><span class="sxs-lookup"><span data-stu-id="9555d-138">You first need to understand the problem, so you can break it down to parts that can support building and training the model.</span></span> <span data-ttu-id="9555d-139">La división del problema en partes le permite predecir y evaluar los resultados.</span><span class="sxs-lookup"><span data-stu-id="9555d-139">Breaking the problem down allows you to predict and evaluate the results.</span></span>

<span data-ttu-id="9555d-140">El problema en este tutorial es comprender los sentimientos de los comentarios del sitio web entrantes para tomar las medidas oportunas.</span><span class="sxs-lookup"><span data-stu-id="9555d-140">The problem for this tutorial is to understand incoming website comment sentiment to take the appropriate action.</span></span>

<span data-ttu-id="9555d-141">Puede dividir el problema en texto de sentimientos y valor de sentimientos para los datos con los que desea entrenar el modelo, y un valor de sentimiento de predicción que puede evaluar y luego usar de manera operativa.</span><span class="sxs-lookup"><span data-stu-id="9555d-141">You can break down the problem to the sentiment text and sentiment value for the data you want to train the model with, and a predicted sentiment value that you can evaluate and then use operationally.</span></span>

<span data-ttu-id="9555d-142">A continuación, necesita **determinar** el sentimiento, lo que le ayuda con la selección de tareas de aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="9555d-142">You then need to **determine** the sentiment, which helps you with the machine learning task selection.</span></span>

## <a name="select-the-appropriate-machine-learning-algorithm"></a><span data-ttu-id="9555d-143">Seleccionar el algoritmo de aprendizaje automático adecuado</span><span class="sxs-lookup"><span data-stu-id="9555d-143">Select the appropriate machine learning algorithm</span></span>

<span data-ttu-id="9555d-144">Con este problema, tiene constancia de los siguientes hechos:</span><span class="sxs-lookup"><span data-stu-id="9555d-144">With this problem, you know the following facts:</span></span>

<span data-ttu-id="9555d-145">Datos de entrenamiento: los comentarios del sitio web pueden ser tóxicos (1) o no tóxicos (0) (**opinión**).</span><span class="sxs-lookup"><span data-stu-id="9555d-145">Training data: website comments can be toxic (1) or not toxic (0) (**sentiment**).</span></span>
<span data-ttu-id="9555d-146">Prediga la **opinión** de un comentario de sitio web nuevo, ya sea tóxico o no tóxico, como en los ejemplos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9555d-146">Predict the **sentiment** of a new website comment, either toxic or not toxic, such as in the following examples:</span></span>

* <span data-ttu-id="9555d-147">Evite agregar elementos sin sentido a Wikipedia.</span><span class="sxs-lookup"><span data-stu-id="9555d-147">Please refrain from adding nonsense to Wikipedia.</span></span>
* <span data-ttu-id="9555d-148">Él es el mejor, y el artículo debe reflejarlo.</span><span class="sxs-lookup"><span data-stu-id="9555d-148">He is the best, and the article should say that.</span></span>

<span data-ttu-id="9555d-149">El algoritmo de aprendizaje automático de clasificación es ideal para este escenario.</span><span class="sxs-lookup"><span data-stu-id="9555d-149">The classification machine learning algorithm is best suited for this scenario.</span></span>

### <a name="about-the-classification-task"></a><span data-ttu-id="9555d-150">Acerca de la tarea de clasificación</span><span class="sxs-lookup"><span data-stu-id="9555d-150">About the classification task</span></span>

<span data-ttu-id="9555d-151">La clasificación es un algoritmo de aprendizaje automático que usa datos para **determinar** la categoría, el tipo o la clase de un elemento o fila de datos.</span><span class="sxs-lookup"><span data-stu-id="9555d-151">Classification is a machine learning algorithm that uses data to **determine** the category, type, or class of an item or row of data.</span></span> <span data-ttu-id="9555d-152">Por ejemplo, puede utilizar la clasificación para:</span><span class="sxs-lookup"><span data-stu-id="9555d-152">For example, you can use classification to:</span></span>

* <span data-ttu-id="9555d-153">Identificar un sentimiento como positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="9555d-153">Identify sentiment as positive or negative.</span></span>
* <span data-ttu-id="9555d-154">Clasificar correo electrónico como correo no deseado o correo válido.</span><span class="sxs-lookup"><span data-stu-id="9555d-154">Classify email as spam, junk, or good.</span></span>
* <span data-ttu-id="9555d-155">Determinar si la muestra de laboratorio de un paciente es cancerosa.</span><span class="sxs-lookup"><span data-stu-id="9555d-155">Determine whether a patient's lab sample is cancerous.</span></span>
* <span data-ttu-id="9555d-156">Categorizar a los clientes por su propensión a responder a una campaña de ventas.</span><span class="sxs-lookup"><span data-stu-id="9555d-156">Categorize customers by their propensity to respond to a sales campaign.</span></span>

<span data-ttu-id="9555d-157">Los algoritmos de clasificación suelen ser de uno de los tipos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9555d-157">Classification algorithms are frequently one of the following types:</span></span>

* <span data-ttu-id="9555d-158">Binario: A o B.</span><span class="sxs-lookup"><span data-stu-id="9555d-158">Binary: either A or B.</span></span>
* <span data-ttu-id="9555d-159">Multiclase: varias categorías que se pueden predecir mediante el uso de un único modelo.</span><span class="sxs-lookup"><span data-stu-id="9555d-159">Multiclass: multiple categories that can be predicted by using a single model.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="9555d-160">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="9555d-160">Create a console application</span></span>

1. <span data-ttu-id="9555d-161">Abra Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="9555d-161">Open Visual Studio 2017.</span></span> <span data-ttu-id="9555d-162">Seleccione **Archivo** > **Nuevo** > **Proyecto** de la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="9555d-162">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="9555d-163">En el cuadro de diálogo **Nuevo proyecto**, seleccione el nodo **Visual C#** seguido del nodo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="9555d-163">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="9555d-164">Después, seleccione la plantilla del proyecto **Aplicación de consola (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="9555d-164">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="9555d-165">En el cuadro de texto **Nombre**, escriba "SentimentAnalysis" y después haga clic en el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9555d-165">In the **Name** text box, type "SentimentAnalysis" and then select the **OK** button.</span></span>

2. <span data-ttu-id="9555d-166">Cree un directorio denominado *Datos* en el proyecto para guardar los archivos del conjunto de datos:</span><span class="sxs-lookup"><span data-stu-id="9555d-166">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="9555d-167">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **Nueva carpeta**.</span><span class="sxs-lookup"><span data-stu-id="9555d-167">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="9555d-168">Escriba "Datos" y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="9555d-168">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="9555d-169">Instale el **paquete NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="9555d-169">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="9555d-170">En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="9555d-170">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="9555d-171">Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.ML**, seleccione ese paquete en la lista y seleccione el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="9555d-171">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="9555d-172">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="9555d-172">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="9555d-173">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="9555d-173">Prepare your data</span></span>

1. <span data-ttu-id="9555d-174">Descargue los conjuntos de datos [Wikipedia detox-250-line-data.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv) y [wikipedia-detox-250-line-test.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv), y guárdelos en la carpeta *Datos* creada previamente.</span><span class="sxs-lookup"><span data-stu-id="9555d-174">Download the [Wikipedia detox-250-line-data.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv) and the [wikipedia-detox-250-line-test.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv) data sets and save them to the *Data* folder previously created.</span></span> <span data-ttu-id="9555d-175">El primer conjunto de datos entrena el modelo de aprendizaje automático y el segundo puede usarse para evaluar su grado de precisión.</span><span class="sxs-lookup"><span data-stu-id="9555d-175">The first dataset trains the machine learning model and the second can be used to evaluate how accurate your model is.</span></span>

2. <span data-ttu-id="9555d-176">En el Explorador de soluciones, haga clic con el botón secundario en cada uno de los archivos \*.tsv y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="9555d-176">In Solution Explorer, right-click each of the \*.tsv files and select **Properties**.</span></span> <span data-ttu-id="9555d-177">En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.</span><span class="sxs-lookup"><span data-stu-id="9555d-177">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="9555d-178">Crear clases y definir rutas de acceso</span><span class="sxs-lookup"><span data-stu-id="9555d-178">Create classes and define paths</span></span>

<span data-ttu-id="9555d-179">Agregue las siguientes instrucciones `using` adicionales a la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="9555d-179">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#1 "Add necessary usings")]

<span data-ttu-id="9555d-180">Debe crear tres campos globales para contener las rutas de acceso a los archivos descargados recientemente y una variable global para `TextLoader`:</span><span class="sxs-lookup"><span data-stu-id="9555d-180">You need to create three global fields to hold the paths to the recently downloaded files, and a global variable for the `TextLoader`:</span></span>

* <span data-ttu-id="9555d-181">`_trainDataPath` tiene la ruta de acceso al conjunto de datos utilizado para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="9555d-181">`_trainDataPath` has the path to the dataset used to train the model.</span></span>
* <span data-ttu-id="9555d-182">`_testDataPath` tiene la ruta de acceso al conjunto de datos utilizado para evaluar el modelo.</span><span class="sxs-lookup"><span data-stu-id="9555d-182">`_testDataPath` has the path to the dataset used to evaluate the model.</span></span>
* <span data-ttu-id="9555d-183">`_modelPath` tiene la ruta de acceso donde se guarda el modelo entrenado.</span><span class="sxs-lookup"><span data-stu-id="9555d-183">`_modelPath` has the path where the trained model is saved.</span></span>
* <span data-ttu-id="9555d-184">`_textLoader` es el <xref:Microsoft.ML.Data.TextLoader> utilizado para cargar y transformar los conjuntos de datos.</span><span class="sxs-lookup"><span data-stu-id="9555d-184">`_textLoader` is the <xref:Microsoft.ML.Data.TextLoader> used to load and transform the datasets.</span></span>

<span data-ttu-id="9555d-185">Agregue el código siguiente a la línea justo encima del método `Main` para especificar esas rutas de acceso y la variable `_textLoader`:</span><span class="sxs-lookup"><span data-stu-id="9555d-185">Add the following code to the line right above the `Main` method to specify those paths and the `_textLoader` variable:</span></span>

[!code-csharp[Declare global variables](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#2 "Declare global variables")]

<span data-ttu-id="9555d-186">Debe crear algunas clases para los datos de entrada y las predicciones.</span><span class="sxs-lookup"><span data-stu-id="9555d-186">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="9555d-187">Agregue una nueva clase a su proyecto:</span><span class="sxs-lookup"><span data-stu-id="9555d-187">Add a new class to your project:</span></span>

1. <span data-ttu-id="9555d-188">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="9555d-188">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="9555d-189">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="9555d-189">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="9555d-190">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="9555d-190">Then, select the **Add** button.</span></span>

    <span data-ttu-id="9555d-191">Se abre el archivo *SentimentData.cs* en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="9555d-191">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="9555d-192">Agregue la siguiente instrucción `using` a la parte superior de *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="9555d-192">Add the following `using` statement to the top of *SentimentData.cs*:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#1 "Add necessary usings")]

<span data-ttu-id="9555d-193">Quite la definición de clase existente y agregue el código siguiente, que tiene dos clases `SentimentData` y `SentimentPrediction`, al archivo *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="9555d-193">Remove the existing class definition and add the following code, which has two classes `SentimentData` and `SentimentPrediction`, to the *SentimentData.cs* file:</span></span>

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#2 "Declare data record types")]

<span data-ttu-id="9555d-194">`SentimentData` es la clase de conjunto de datos de entrada y tiene un `float` (`Sentiment`) que tiene un valor para el sentimiento positivo o negativo, y una cadena para el comentario (`SentimentText`).</span><span class="sxs-lookup"><span data-stu-id="9555d-194">`SentimentData` is the input dataset class and has a `float` (`Sentiment`) that has a value for sentiment of either positive or negative, and a string for the comment (`SentimentText`).</span></span> <span data-ttu-id="9555d-195">Ambos campos tienen `Column` atributos adjuntos a ellos.</span><span class="sxs-lookup"><span data-stu-id="9555d-195">Both fields have `Column` attributes attached to them.</span></span> <span data-ttu-id="9555d-196">Este atributo describe el orden de cada campo en el archivo de datos, y que es el campo `Label`.</span><span class="sxs-lookup"><span data-stu-id="9555d-196">This attribute describes the order of each field in the data file, and which is the `Label` field.</span></span> <span data-ttu-id="9555d-197">`SentimentPrediction` es la clase usada para la predicción una vez entrenado el modelo.</span><span class="sxs-lookup"><span data-stu-id="9555d-197">`SentimentPrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="9555d-198">Tiene un valor booleano único (`Sentiment`) y un atributo `PredictedLabel` `ColumnName`.</span><span class="sxs-lookup"><span data-stu-id="9555d-198">It has a single boolean (`Sentiment`) and a `PredictedLabel` `ColumnName` attribute.</span></span> <span data-ttu-id="9555d-199">`Label` se usa para crear y entrenar el modelo, y se usa también con un segundo conjunto de datos para evaluar el modelo.</span><span class="sxs-lookup"><span data-stu-id="9555d-199">The `Label` is used to create and train the model, and it's also used with a second dataset to evaluate the model.</span></span> <span data-ttu-id="9555d-200">`PredictedLabel` se usa durante la predicción y la evaluación.</span><span class="sxs-lookup"><span data-stu-id="9555d-200">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="9555d-201">Para la evaluación, se utiliza una entrada con los datos de entrenamiento, los valores de predicción y el modelo.</span><span class="sxs-lookup"><span data-stu-id="9555d-201">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="9555d-202">Cuando se crea un modelo con ML.NET empieza creando un `MLContext`.</span><span class="sxs-lookup"><span data-stu-id="9555d-202">When building a model with ML.NET you start by creating an `MLContext`.</span></span> <span data-ttu-id="9555d-203">Esto es comparable conceptualmente a usar `DbContext` en Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="9555d-203">This is comparable conceptually to using `DbContext` in Entity Framework.</span></span> <span data-ttu-id="9555d-204">El entorno proporciona un contexto para el trabajo de ML que puede usarse para el seguimiento y registro de excepciones.</span><span class="sxs-lookup"><span data-stu-id="9555d-204">The environment provides a context for your ML job that can be used for exception tracking and logging.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="9555d-205">Inicializar variables en Main</span><span class="sxs-lookup"><span data-stu-id="9555d-205">Initialize variables in Main</span></span>

<span data-ttu-id="9555d-206">Cree una variable denominada `mlContext` e inicialícela con una nueva instancia de `MLContext`.</span><span class="sxs-lookup"><span data-stu-id="9555d-206">Create a variable called `mlContext` and initialize it with a new instance of `MLContext`.</span></span>  <span data-ttu-id="9555d-207">Reemplace la línea `Console.WriteLine("Hello World!")` por el código siguiente en el método `Main`:</span><span class="sxs-lookup"><span data-stu-id="9555d-207">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#3 "Create the ML Context")]

<span data-ttu-id="9555d-208">A continuación, para realizar la configuración para la carga de datos, inicialice la variable global `_textLoader` con el fin de volver a usarla.</span><span class="sxs-lookup"><span data-stu-id="9555d-208">Next, to setup for data loading initialize the `_textLoader` global variable in order to reuse it.</span></span>  <span data-ttu-id="9555d-209">Cuando se crea un elemento `TextLoader` mediante `MLContext.Data.CreateTextLoader`, se pasa el contexto necesario y la clase <xref:Microsoft.ML.Data.TextLoader.Arguments> que habilita la personalización.</span><span class="sxs-lookup"><span data-stu-id="9555d-209">When you create a `TextLoader` using  `MLContext.Data.CreateTextLoader`, you pass in the context needed and the <xref:Microsoft.ML.Data.TextLoader.Arguments> class which enables customization.</span></span>

 <span data-ttu-id="9555d-210">Especifique el esquema de datos, pasando una matriz de objetos <xref:Microsoft.ML.Data.TextLoader.Column> al cargador que contiene todos los nombres de columna y sus tipos.</span><span class="sxs-lookup"><span data-stu-id="9555d-210">Specify the data schema by passing an array of <xref:Microsoft.ML.Data.TextLoader.Column> objects to the loader containing all the column names and their types.</span></span> <span data-ttu-id="9555d-211">Definió el esquema de datos anteriormente al crear nuestra clase `SentimentData`.</span><span class="sxs-lookup"><span data-stu-id="9555d-211">You defined the data schema previously when you created our `SentimentData` class.</span></span> <span data-ttu-id="9555d-212">Para nuestro esquema, la primera columna (Label) es <xref:System.Boolean> (la opinión) y la segunda columna (SentimentText) es la característica de tipo texto o cadena utilizada para predecir la opinión.</span><span class="sxs-lookup"><span data-stu-id="9555d-212">For our schema, the first column (Label) is a <xref:System.Boolean> (the prediction) and the second column (SentimentText) is the feature of type text/string used for predicting the sentiment.</span></span>
<span data-ttu-id="9555d-213">La clase `TextLoader` devuelve la variable <xref:Microsoft.ML.Data.TextLoader> totalmente inicializada.</span><span class="sxs-lookup"><span data-stu-id="9555d-213">The `TextLoader` class returns a fully initialized <xref:Microsoft.ML.Data.TextLoader></span></span>  

<span data-ttu-id="9555d-214">Para inicializar la variable global `_textLoader` con el fin de volver a usarla para los conjuntos de datos necesarios, agregue el código siguiente después de la inicialización de `mlContext`:</span><span class="sxs-lookup"><span data-stu-id="9555d-214">To initialize the `_textLoader` global variable in order to reuse it for the needed datasets, add the following code after the  `mlContext` initialization:</span></span>

[!code-csharp[initTextLoader](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#4 "Initialize the TextLoader")]

<span data-ttu-id="9555d-215">Agregue lo siguiente como la siguiente línea de código en el método `Main`:</span><span class="sxs-lookup"><span data-stu-id="9555d-215">Add the following as the next line of code in the `Main` method:</span></span>

[!code-csharp[Train](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#5 "Train your model")]

<span data-ttu-id="9555d-216">El método `Train` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="9555d-216">The `Train` method executes the following tasks:</span></span>

* <span data-ttu-id="9555d-217">Carga los datos.</span><span class="sxs-lookup"><span data-stu-id="9555d-217">Loads the data.</span></span>
* <span data-ttu-id="9555d-218">Extrae y transforma los datos.</span><span class="sxs-lookup"><span data-stu-id="9555d-218">Extracts and transforms the data.</span></span>
* <span data-ttu-id="9555d-219">Entrena el modelo.</span><span class="sxs-lookup"><span data-stu-id="9555d-219">Trains the model.</span></span>
* <span data-ttu-id="9555d-220">Predice sentimientos en función de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="9555d-220">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="9555d-221">Devuelve el modelo.</span><span class="sxs-lookup"><span data-stu-id="9555d-221">Returns the model.</span></span>

<span data-ttu-id="9555d-222">Cree el método `Train`, justo después del método `Main`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="9555d-222">Create the `Train` method, just after the `Main` method, using the following code:</span></span>

```csharp
 public static ITransformer Train(MLContext mlContext, string dataPath)
{

}
```

<span data-ttu-id="9555d-223">Tenga en cuenta que se pasan dos parámetros al método Train: `MLContext` para el contexto (`mlContext`) y <xref:System.String> para la ruta de acceso del conjunto de datos (`dataPath`).</span><span class="sxs-lookup"><span data-stu-id="9555d-223">Notice that two parameters are passed into the Train method; a `MLContext` for the context (`mlContext`), and a <xref:System.String> for the dataset path (`dataPath`).</span></span> <span data-ttu-id="9555d-224">Va a usar este método varias veces para entrenar y probar.</span><span class="sxs-lookup"><span data-stu-id="9555d-224">You're going to use this method more than once for training and testing.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="9555d-225">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="9555d-225">Load the data</span></span>

<span data-ttu-id="9555d-226">Cargará los datos mediante la variable global `_textLoader` con el parámetro `dataPath`.</span><span class="sxs-lookup"><span data-stu-id="9555d-226">You'll load the data using the `_textLoader` global variable with the `dataPath` parameter.</span></span> <span data-ttu-id="9555d-227">Devuelve <xref:Microsoft.Data.DataView.IDataView>.</span><span class="sxs-lookup"><span data-stu-id="9555d-227">It returns a <xref:Microsoft.Data.DataView.IDataView>.</span></span> <span data-ttu-id="9555d-228">Como la entrada y salida de `Transforms`, `DataView` es el tipo de canalización de datos fundamentales, comparable con `IEnumerable` para `LINQ`.</span><span class="sxs-lookup"><span data-stu-id="9555d-228">As the input and output of `Transforms`, a `DataView` is the fundamental data pipeline type, comparable to `IEnumerable` for `LINQ`.</span></span>

<span data-ttu-id="9555d-229">En ML.NET, los datos son similares a una vista SQL.</span><span class="sxs-lookup"><span data-stu-id="9555d-229">In ML.NET, data is similar to a SQL view.</span></span> <span data-ttu-id="9555d-230">Se evalúan lentamente, se esquematizan y son heterogéneos.</span><span class="sxs-lookup"><span data-stu-id="9555d-230">It is lazily evaluated, schematized, and heterogenous.</span></span> <span data-ttu-id="9555d-231">El objeto es la primera parte de la canalización y carga los datos.</span><span class="sxs-lookup"><span data-stu-id="9555d-231">The object is the first part of the pipeline, and loads the data.</span></span> <span data-ttu-id="9555d-232">Para este tutorial, carga un conjunto de datos con comentarios y opiniones tóxicas o no tóxicas correspondiente.</span><span class="sxs-lookup"><span data-stu-id="9555d-232">For this tutorial, it loads a dataset with comments and corresponding toxic or non toxic sentiment.</span></span> <span data-ttu-id="9555d-233">Esto se usa para crear el modelo y entrenarlo.</span><span class="sxs-lookup"><span data-stu-id="9555d-233">This is used to create the model, and train it.</span></span>

 <span data-ttu-id="9555d-234">Agregue el código siguiente a la primera línea del método `Train`:</span><span class="sxs-lookup"><span data-stu-id="9555d-234">Add the following code as the first line of the `Train` method:</span></span>

[!code-csharp[LoadTrainData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#6 "loading training dataset")]

## <a name="extract-and-transform-the-data"></a><span data-ttu-id="9555d-235">Extraer y transformar los datos</span><span class="sxs-lookup"><span data-stu-id="9555d-235">Extract and transform the data</span></span>

<span data-ttu-id="9555d-236">El procesamiento previo y la limpieza de datos son tareas importantes que se producen antes de que un conjunto de datos se utilice de forma eficaz para el aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="9555d-236">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span> <span data-ttu-id="9555d-237">Los datos sin procesar contienen a menudo ruido y son poco de fiar; además, es posible que les falten valores.</span><span class="sxs-lookup"><span data-stu-id="9555d-237">Raw data is often noisy and unreliable, and may be missing values.</span></span> <span data-ttu-id="9555d-238">El uso de datos sin estas tareas de modelado puede producir resultados engañosos.</span><span class="sxs-lookup"><span data-stu-id="9555d-238">Using data without these modeling tasks can produce misleading results.</span></span>

<span data-ttu-id="9555d-239">Las canalizaciones de transformación de ML.NET crean un conjunto personalizado de transformaciones que se aplican a los datos antes del entrenamiento o la prueba.</span><span class="sxs-lookup"><span data-stu-id="9555d-239">ML.NET's transform pipelines compose a custom set of transforms that are applied to your data before training or testing.</span></span> <span data-ttu-id="9555d-240">El propósito principal de las transformaciones es la [caracterización](../resources/glossary.md#feature-engineering) de datos.</span><span class="sxs-lookup"><span data-stu-id="9555d-240">The transforms' primary purpose is data [featurization](../resources/glossary.md#feature-engineering).</span></span> <span data-ttu-id="9555d-241">Los algoritmos de aprendizaje automático comprenden los datos [caracterizados](../resources/glossary.md#feature), por lo que el paso siguiente es transformar nuestro datos textuales en un formato que reconozcan nuestros algoritmos de ML.</span><span class="sxs-lookup"><span data-stu-id="9555d-241">Machine learning algorithms understand [featurized](../resources/glossary.md#feature) data, so the next step is to transform our textual data into a format that our ML algorithms recognize.</span></span> <span data-ttu-id="9555d-242">Ese formato es un [vector numérico](../resources/glossary.md#numerical-feature-vector).</span><span class="sxs-lookup"><span data-stu-id="9555d-242">That format is a [numeric vector](../resources/glossary.md#numerical-feature-vector).</span></span>

<span data-ttu-id="9555d-243">Después, llame a `mlContext.Transforms.Text.FeaturizeText` que caracteriza la columna de texto (`SentimentText`) en un vector numérico llamado `Features` utilizado por el algoritmo de aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="9555d-243">Next, call `mlContext.Transforms.Text.FeaturizeText` which featurizes the text column (`SentimentText`) column into a numeric vector called `Features` used by the machine learning algorithm.</span></span> <span data-ttu-id="9555d-244">Se trata de una llamada de contenedor que devuelve <xref:Microsoft.ML.Data.EstimatorChain%601> que eficazmente será una canalización.</span><span class="sxs-lookup"><span data-stu-id="9555d-244">This is a wrapper call that returns an <xref:Microsoft.ML.Data.EstimatorChain%601> that will effectively be a pipeline.</span></span> <span data-ttu-id="9555d-245">Asigne un nombre a `pipeline`, ya que luego anexará el entrenador a `EstimatorChain`.</span><span class="sxs-lookup"><span data-stu-id="9555d-245">Name this `pipeline` as you will then append the trainer to the `EstimatorChain`.</span></span> <span data-ttu-id="9555d-246">Agregue esto como la siguiente línea de código:</span><span class="sxs-lookup"><span data-stu-id="9555d-246">Add this as the next line of code:</span></span>

[!code-csharp[TextFeaturizingEstimator](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#7 "Add a TextFeaturizingEstimator")]

<span data-ttu-id="9555d-247">Este es el paso de preprocesamiento o caracterización.</span><span class="sxs-lookup"><span data-stu-id="9555d-247">This is the preprocessing/featurization step.</span></span> <span data-ttu-id="9555d-248">El uso de componentes adicionales disponibles en ML.NET permite conseguir mejores resultados con el modelo.</span><span class="sxs-lookup"><span data-stu-id="9555d-248">Using additional components available in ML.NET can enable better results with your model.</span></span>

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="9555d-249">Elegir un algoritmo de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="9555d-249">Choose a learning algorithm</span></span>

<span data-ttu-id="9555d-250">Para agregar el entrenador, llame al método contenedor `mlContext.Transforms.Text.FeaturizeText` que devuelve un objeto <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer>.</span><span class="sxs-lookup"><span data-stu-id="9555d-250">To add the trainer, call the `mlContext.Transforms.Text.FeaturizeText` wrapper method which returns a <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer> object.</span></span> <span data-ttu-id="9555d-251">Esto es un aprendiz de árbol de decisión que usará en esta canalización.</span><span class="sxs-lookup"><span data-stu-id="9555d-251">This is a decision tree learner you'll use in this pipeline.</span></span> <span data-ttu-id="9555d-252">`FastTreeBinaryClassificationTrainer` se anexa a `pipeline` y acepta `SentimentText` (`Features`) caracterizado y los parámetros de entrada `Label` para aprender de los datos históricos.</span><span class="sxs-lookup"><span data-stu-id="9555d-252">The `FastTreeBinaryClassificationTrainer` is appended to the `pipeline` and accepts the featurized `SentimentText` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span>

<span data-ttu-id="9555d-253">Agregue el código siguiente al método `Train`:</span><span class="sxs-lookup"><span data-stu-id="9555d-253">Add the following code to the `Train` method:</span></span>

[!code-csharp[FastTreeBinaryClassificationTrainer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#8 "Add a FastTreeBinaryClassificationTrainer")]

## <a name="train-the-model"></a><span data-ttu-id="9555d-254">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="9555d-254">Train the model</span></span>

<span data-ttu-id="9555d-255">Se entrena el modelo, <xref:Microsoft.ML.Data.TransformerChain%601>, en función del conjunto de datos que se haya cargado y transformado.</span><span class="sxs-lookup"><span data-stu-id="9555d-255">You train the model, <xref:Microsoft.ML.Data.TransformerChain%601>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="9555d-256">Una vez que se ha definido el estimador, entrenará el modelo mediante <xref:Microsoft.ML.Data.EstimatorChain%601.Fit*> proporcionando al mismo tiempo los datos de entrenamiento ya cargados.</span><span class="sxs-lookup"><span data-stu-id="9555d-256">Once the estimator has been defined, you train your model using the <xref:Microsoft.ML.Data.EstimatorChain%601.Fit*> while providing the already loaded training data.</span></span> <span data-ttu-id="9555d-257">Esto devuelve un modelo que se usa para las predicciones.</span><span class="sxs-lookup"><span data-stu-id="9555d-257">This returns a model to use for predictions.</span></span> <span data-ttu-id="9555d-258">`pipeline.Fit()` entrena la canalización y devuelve `Transformer` según la `DataView` que se pasa.</span><span class="sxs-lookup"><span data-stu-id="9555d-258">`pipeline.Fit()` trains the pipeline and returns a `Transformer` based on the `DataView` passed in.</span></span> <span data-ttu-id="9555d-259">El experimento no se ejecuta hasta que esto suceda.</span><span class="sxs-lookup"><span data-stu-id="9555d-259">The experiment is not executed until this happens.</span></span>

<span data-ttu-id="9555d-260">Agregue el código siguiente al método `Train`:</span><span class="sxs-lookup"><span data-stu-id="9555d-260">Add the following code to the `Train` method:</span></span>

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#9 "Train the model")]

### <a name="save-and-return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="9555d-261">Guardar y devolver el modelo entrenado para su uso para la evaluación</span><span class="sxs-lookup"><span data-stu-id="9555d-261">Save and Return the model trained to use for evaluation</span></span>

<span data-ttu-id="9555d-262">En este punto, tiene un modelo de tipo <xref:Microsoft.ML.Data.TransformerChain%601> que se puede integrar en cualquiera de las aplicaciones de .NET nuevas o existentes.</span><span class="sxs-lookup"><span data-stu-id="9555d-262">At this point, you have a model of type <xref:Microsoft.ML.Data.TransformerChain%601> that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="9555d-263">Devuelva el modelo al final del método `Train`.</span><span class="sxs-lookup"><span data-stu-id="9555d-263">Return the model at the end of the `Train` method.</span></span>

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#10 "Return the model")]

## <a name="evaluate-the-model"></a><span data-ttu-id="9555d-264">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="9555d-264">Evaluate the model</span></span>

<span data-ttu-id="9555d-265">Ahora que ha creado y entrenado el modelo, debe evaluarlo con otro conjunto de datos para el control de calidad y la validación.</span><span class="sxs-lookup"><span data-stu-id="9555d-265">Now that you've created and trained the model, you need to evaluate it with a different dataset for quality assurance and validation.</span></span> <span data-ttu-id="9555d-266">En el método `Evaluate`, el modelo creado en `Train` se pasa para ser evaluado.</span><span class="sxs-lookup"><span data-stu-id="9555d-266">In the `Evaluate` method, the model created in `Train` is passed in to be evaluated.</span></span> <span data-ttu-id="9555d-267">Cree el método `Evaluate`, justo después de `Train`, como en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="9555d-267">Create the `Evaluate` method, just after `Train`, as in the following code:</span></span>

```csharp
public static void Evaluate(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="9555d-268">El método `Evaluate` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="9555d-268">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="9555d-269">Carga el conjunto de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="9555d-269">Loads the test dataset.</span></span>
* <span data-ttu-id="9555d-270">Crea el evaluador binario.</span><span class="sxs-lookup"><span data-stu-id="9555d-270">Creates the binary evaluator.</span></span>
* <span data-ttu-id="9555d-271">Evalúa el modelo y crea métricas.</span><span class="sxs-lookup"><span data-stu-id="9555d-271">Evaluates the model and create metrics.</span></span>
* <span data-ttu-id="9555d-272">Muestra las métricas.</span><span class="sxs-lookup"><span data-stu-id="9555d-272">Displays the metrics.</span></span>

<span data-ttu-id="9555d-273">Agregue una llamada al método nuevo desde el método `Main`, justo debajo de la llamada al método `Train`, utilizando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="9555d-273">Add a call to the new method from the `Main` method, right under the `Train` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#11 "Call the Evaluate method")]

<span data-ttu-id="9555d-274">Cargará el conjunto de datos de prueba mediante la variable global `_textLoader` inicializada anteriormente con el campo global `_testDataPath`.</span><span class="sxs-lookup"><span data-stu-id="9555d-274">You'll load the test dataset using the previously initialized  `_textLoader` global variable with the `_testDataPath` global field.</span></span> <span data-ttu-id="9555d-275">Puede evaluar el modelo utilizando este conjunto de datos como una comprobación de calidad.</span><span class="sxs-lookup"><span data-stu-id="9555d-275">You can evaluate the model using this dataset as a quality check.</span></span> <span data-ttu-id="9555d-276">Agregue el código siguiente al método `Evaluate`:</span><span class="sxs-lookup"><span data-stu-id="9555d-276">Add the following code to the `Evaluate` method:</span></span>

[!code-csharp[LoadTestDataset](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#12 "Load the test dataset")]

<span data-ttu-id="9555d-277">A continuación, deberá usará el parámetro `model` de aprendizaje automático (un transformador) para introducir las características y devolver las predicciones.</span><span class="sxs-lookup"><span data-stu-id="9555d-277">Next, you'll use the machine learning `model` parameter (a transformer) to input the features and return predictions.</span></span> <span data-ttu-id="9555d-278">Agregue el siguiente código al método `Evaluate` como la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="9555d-278">Add the following code to the `Evaluate` method as the next line:</span></span>

[!code-csharp[PredictWithTransformer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#13 "Predict using the Transformer")]

<span data-ttu-id="9555d-279">El método `BinaryClassificationContext.Evaluate` calcula las métricas de calidad para `PredictionModel` mediante el conjunto de datos especificado.</span><span class="sxs-lookup"><span data-stu-id="9555d-279">The `BinaryClassificationContext.Evaluate` method computes the quality metrics for the `PredictionModel` using the specified dataset.</span></span> <span data-ttu-id="9555d-280">Devuelve un objeto `BinaryClassificationEvaluator.CalibratedResult` que contiene las métricas totales calculadas por evaluadores de clasificación binaria.</span><span class="sxs-lookup"><span data-stu-id="9555d-280">It returns a `BinaryClassificationEvaluator.CalibratedResult` object contains the overall metrics computed by binary classification evaluators.</span></span> <span data-ttu-id="9555d-281">Para mostrar estos elementos a fin de determinar la calidad del modelo, debe obtener primero las métricas.</span><span class="sxs-lookup"><span data-stu-id="9555d-281">To display these to determine the quality of the model, you need to get the metrics first.</span></span> <span data-ttu-id="9555d-282">Agregue el siguiente código como la siguiente línea en el método `Evaluate`:</span><span class="sxs-lookup"><span data-stu-id="9555d-282">Add the following code as the next line in the `Evaluate` method:</span></span>

[!code-csharp[ComputeMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#14 "Compute Metrics")]

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="9555d-283">Mostrar las métricas para la validación del modelo</span><span class="sxs-lookup"><span data-stu-id="9555d-283">Displaying the metrics for model validation</span></span>

<span data-ttu-id="9555d-284">Utilice el código siguiente para mostrar las métricas, compartir los resultados y, a continuación, trabajar con ellos:</span><span class="sxs-lookup"><span data-stu-id="9555d-284">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#15 "Display selected metrics")]

<span data-ttu-id="9555d-285">Para guardar el modelo en un archivo .zip antes de devolverlo, agregue el siguiente código para llamar al método `SaveModelAsFile` como la línea siguiente en `Evaluate`:</span><span class="sxs-lookup"><span data-stu-id="9555d-285">To save your model to a .zip file before returning, add the following code to call the `SaveModelAsFile` method as the next line in `Evaluate`:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#23 "Save the model")]

## <a name="save-the-model-as-azip-file"></a><span data-ttu-id="9555d-286">Almacenamiento del modelo como un archivo .zip</span><span class="sxs-lookup"><span data-stu-id="9555d-286">Save the model as a.zip file</span></span>

<span data-ttu-id="9555d-287">Cree el método `SaveModelAsFile`, justo después del método `Evaluate`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="9555d-287">Create the `SaveModelAsFile` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="9555d-288">El método `SaveModelAsFile` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="9555d-288">The `SaveModelAsFile` method executes the following tasks:</span></span>

* <span data-ttu-id="9555d-289">Guarda el modelo como un archivo .zip.</span><span class="sxs-lookup"><span data-stu-id="9555d-289">Saves the model as a .zip file.</span></span>

<span data-ttu-id="9555d-290">A continuación, cree un método para guardar el modelo para que se pueda volver a usar y consumir en otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="9555d-290">Next, create a method to save the model so that it can be reused and consumed in other applications.</span></span> <span data-ttu-id="9555d-291">`ITransformer` tiene un método <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> que toma el campo global `_modelPath` y <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="9555d-291">The `ITransformer` has a <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> method that takes in the `_modelPath` global field, and a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="9555d-292">Para guardar esto como un archivo ZIP, creará `FileStream` inmediatamente antes de llamar al método `SaveTo`.</span><span class="sxs-lookup"><span data-stu-id="9555d-292">To save this as a zip file, you'll create the `FileStream` immediately before calling the `SaveTo` method.</span></span> <span data-ttu-id="9555d-293">Agregue el código siguiente al método `SaveModelAsFile` como la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="9555d-293">Add the following code to the `SaveModelAsFile` method as the next line:</span></span>

[!code-csharp[SaveToMethod](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#24 "Add the SaveTo Method")]
<span data-ttu-id="9555d-294">Implementar y predecir con un modelo cargado También podría mostrar dónde se ha escrito el archivo mediante la escritura de un mensaje de consola con `_modelPath`, con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="9555d-294">Deploy and Predict with a loaded model You could also display where the file was written by writing a console message with the `_modelPath`, using the following code:</span></span>

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="predict-the-test-data-outcome-with-the-saved-model"></a><span data-ttu-id="9555d-295">Predicción de los resultados de datos de prueba con el modelo guardado</span><span class="sxs-lookup"><span data-stu-id="9555d-295">Predict the test data outcome with the saved model</span></span>

<span data-ttu-id="9555d-296">Cree el método `Predict`, justo después del método `Evaluate`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="9555d-296">Create the `Predict` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void Predict(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="9555d-297">El método `Predict` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="9555d-297">The `Predict` method executes the following tasks:</span></span>

* <span data-ttu-id="9555d-298">Crea un único comentario de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="9555d-298">Creates a single comment of test data.</span></span>
* <span data-ttu-id="9555d-299">Predice sentimientos en función de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="9555d-299">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="9555d-300">Combina datos de prueba y predicciones para la generación de informes.</span><span class="sxs-lookup"><span data-stu-id="9555d-300">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="9555d-301">Muestra los resultados de la predicción.</span><span class="sxs-lookup"><span data-stu-id="9555d-301">Displays the predicted results.</span></span>

<span data-ttu-id="9555d-302">Agregue una llamada al método nuevo desde el método `Main`, justo debajo de la llamada al método `Evaluate`, utilizando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="9555d-302">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallPredict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#16 "Call the Predict method")]

<span data-ttu-id="9555d-303">Mientras `model` es `transformer` que opera en muchas filas de datos, un escenario muy común de producción es necesario para las predicciones con los ejemplos individuales.</span><span class="sxs-lookup"><span data-stu-id="9555d-303">While the `model` is a `transformer` that operates on many rows of data, a very common production scenario is a need for predictions on individual examples.</span></span> <span data-ttu-id="9555d-304"><xref:Microsoft.ML.PredictionEngine%602> es un contenedor que se devuelve del método `CreatePredictionEngine`.</span><span class="sxs-lookup"><span data-stu-id="9555d-304">The <xref:Microsoft.ML.PredictionEngine%602> is a wrapper that is returned from the `CreatePredictionEngine` method.</span></span> <span data-ttu-id="9555d-305">Vamos a agregar el código siguiente para crear `PredictionEngine` como la primera línea en el método `Predict`:</span><span class="sxs-lookup"><span data-stu-id="9555d-305">Let's add the following code to create the `PredictionEngine` as the first line in the `Predict` Method:</span></span>

[!code-csharp[CreatePredictionEngine](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#17 "Create the PredictionEngine")]
  
<span data-ttu-id="9555d-306">Agregue un comentario para probar la predicción del modelo entrenado en el método `Predict` mediante la creación de una instancia de `SentimentData`:</span><span class="sxs-lookup"><span data-stu-id="9555d-306">Add a comment to test the trained model's prediction in the `Predict` method by creating an instance of `SentimentData`:</span></span>

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#18 "Create test data for single prediction")]

 <span data-ttu-id="9555d-307">Puede usar eso para predecir la opinión tóxica o no tóxica de una única instancia de los datos de comentario.</span><span class="sxs-lookup"><span data-stu-id="9555d-307">You can use that to predict the Toxic or Non Toxic sentiment of a single instance of the comment data.</span></span> <span data-ttu-id="9555d-308">Para obtener una predicción, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> en los datos.</span><span class="sxs-lookup"><span data-stu-id="9555d-308">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="9555d-309">Tenga en cuenta que los datos de entrada son una cadena y el modelo incluye la caracterización.</span><span class="sxs-lookup"><span data-stu-id="9555d-309">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="9555d-310">La canalización está sincronizada durante el entrenamiento y la predicción.</span><span class="sxs-lookup"><span data-stu-id="9555d-310">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="9555d-311">No fue necesario escribir el código de preprocesamiento o caracterización específicamente para las predicciones, y la misma API se encarga de las predicciones por lotes y puntuales.</span><span class="sxs-lookup"><span data-stu-id="9555d-311">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#19 "Create a prediction of sentiment")]

### <a name="using-the-model-prediction"></a><span data-ttu-id="9555d-312">Uso del modelo: predicción</span><span class="sxs-lookup"><span data-stu-id="9555d-312">Using the model: prediction</span></span>

<span data-ttu-id="9555d-313">Muestre `SentimentText` y la predicción del sentimiento correspondiente para compartir los resultados y actuar en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="9555d-313">Display `SentimentText` and corresponding sentiment prediction in order to share the results and act on them accordingly.</span></span> <span data-ttu-id="9555d-314">Esto se denomina puesta en marcha, y se utilizan los datos devueltos como parte de las directivas operativas.</span><span class="sxs-lookup"><span data-stu-id="9555d-314">This is called operationalization, using the returned data as part of the operational policies.</span></span> <span data-ttu-id="9555d-315">Cree una visualización para los resultados mediante el código <xref:System.Console.WriteLine?displayProperty=nameWithType> siguiente:</span><span class="sxs-lookup"><span data-stu-id="9555d-315">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputPrediction](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#20 "Display prediction output")]

## <a name="deploy-and-predict-with-a-loaded-model"></a><span data-ttu-id="9555d-316">Implementar y predecir con un modelo cargado</span><span class="sxs-lookup"><span data-stu-id="9555d-316">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="9555d-317">Cree el método `PredictWithModelLoadedFromFile`, justo antes del método `SaveModelAsFile`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="9555d-317">Create the `PredictWithModelLoadedFromFile` method, just before the `SaveModelAsFile` method, using the following code:</span></span>

```csharp
public static void PredictWithModelLoadedFromFile(MLContext mlContext)
{

}
```

<span data-ttu-id="9555d-318">El método `PredictWithModelLoadedFromFile` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="9555d-318">The `PredictWithModelLoadedFromFile` method executes the following tasks:</span></span>

* <span data-ttu-id="9555d-319">Crea datos de prueba por lotes.</span><span class="sxs-lookup"><span data-stu-id="9555d-319">Creates batch test data.</span></span>
* <span data-ttu-id="9555d-320">Predice sentimientos en función de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="9555d-320">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="9555d-321">Combina datos de prueba y predicciones para la generación de informes.</span><span class="sxs-lookup"><span data-stu-id="9555d-321">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="9555d-322">Muestra los resultados de la predicción.</span><span class="sxs-lookup"><span data-stu-id="9555d-322">Displays the predicted results.</span></span>

<span data-ttu-id="9555d-323">Agregue una llamada al método nuevo desde el método `Main`, justo debajo de la llamada al método `Predict`, utilizando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="9555d-323">Add a call to the new method from the `Main` method, right under the `Predict` method call, using the following code:</span></span>

[!code-csharp[CallPredictModelLoaded](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#25 "Call the PredictWithModelLoadedFromFile method")]

<span data-ttu-id="9555d-324">Agregue algunos comentarios para probar las predicciones del modelo entrenado en el método `PredictWithModelLoadedFromFile`:</span><span class="sxs-lookup"><span data-stu-id="9555d-324">Add some comments to test the trained model's predictions in the `PredictWithModelLoadedFromFile` method:</span></span>

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#26 "Create test data for predictions")]

<span data-ttu-id="9555d-325">Cargue el modelo</span><span class="sxs-lookup"><span data-stu-id="9555d-325">Load the model</span></span>

[!code-csharp[LoadTheModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#27 "Load the model")]

<span data-ttu-id="9555d-326">Ahora que tiene un modelo, puede utilizarlo para predecir la opinión tóxica o no tóxica de los datos de comentarios con el método <xref:Microsoft.ML.Core.Data.ITransformer.Transform%2A>.</span><span class="sxs-lookup"><span data-stu-id="9555d-326">Now that you have a model, you can use that to predict the Toxic or Non Toxic sentiment of the comment data using the <xref:Microsoft.ML.Core.Data.ITransformer.Transform%2A> method.</span></span> <span data-ttu-id="9555d-327">Para obtener una predicción, use `Predict` en los nuevos datos.</span><span class="sxs-lookup"><span data-stu-id="9555d-327">To get a prediction, use `Predict` on new data.</span></span> <span data-ttu-id="9555d-328">Tenga en cuenta que los datos de entrada son una cadena y el modelo incluye la caracterización.</span><span class="sxs-lookup"><span data-stu-id="9555d-328">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="9555d-329">La canalización está sincronizada durante el entrenamiento y la predicción.</span><span class="sxs-lookup"><span data-stu-id="9555d-329">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="9555d-330">No fue necesario escribir el código de preprocesamiento o caracterización específicamente para las predicciones, y la misma API se encarga de las predicciones por lotes y puntuales.</span><span class="sxs-lookup"><span data-stu-id="9555d-330">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span> <span data-ttu-id="9555d-331">Agregue el código siguiente al método `PredictWithModelLoadedFromFile` para las predicciones:</span><span class="sxs-lookup"><span data-stu-id="9555d-331">Add the following code to the `PredictWithModelLoadedFromFile` method for the predictions:</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#28 "Create predictions of sentiments")]

### <a name="using-the-loaded-model-for-prediction"></a><span data-ttu-id="9555d-332">Uso del modelo cargado para la predicción</span><span class="sxs-lookup"><span data-stu-id="9555d-332">Using the loaded model for prediction</span></span>

<span data-ttu-id="9555d-333">Muestre `SentimentText` y la predicción del sentimiento correspondiente para compartir los resultados y actuar en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="9555d-333">Display `SentimentText` and corresponding sentiment prediction in order to share the results and act on them accordingly.</span></span> <span data-ttu-id="9555d-334">Esto se denomina puesta en marcha, y se utilizan los datos devueltos como parte de las directivas operativas.</span><span class="sxs-lookup"><span data-stu-id="9555d-334">This is called operationalization, using the returned data as part of the operational policies.</span></span> <span data-ttu-id="9555d-335">Cree un encabezado para los resultados con el código <xref:System.Console.WriteLine?displayProperty=nameWithType> siguiente:</span><span class="sxs-lookup"><span data-stu-id="9555d-335">Create a header for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputHeaders](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#29 "Display prediction outputs")]

<span data-ttu-id="9555d-336">Antes de mostrar los resultados de la predicción, combine el sentimiento con la predicción para ver el comentario original con su sentimiento de predicción.</span><span class="sxs-lookup"><span data-stu-id="9555d-336">Before displaying the predicted results, combine the sentiment and prediction together to see the original comment with its predicted sentiment.</span></span> <span data-ttu-id="9555d-337">El siguiente código utiliza el método <xref:System.Linq.Enumerable.Zip%2A> para que esto ocurra, así que agregue el código siguiente a continuación:</span><span class="sxs-lookup"><span data-stu-id="9555d-337">The following code uses the <xref:System.Linq.Enumerable.Zip%2A> method to make that happen, so add that code next:</span></span>

[!code-csharp[BuildTuples](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#30 "Build the pairs of sentiment data and predictions")]

<span data-ttu-id="9555d-338">Ahora que ha combinado `SentimentText` y `Sentiment` en una clase, puede mostrar los resultados utilizando el método <xref:System.Console.WriteLine?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="9555d-338">Now that you've combined the `SentimentText` and `Sentiment` into a class, you can display the results using the <xref:System.Console.WriteLine?displayProperty=nameWithType> method:</span></span>

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#31 "Display the predictions")]

<span data-ttu-id="9555d-339">Debido a que los nombres de elementos de tupla inferidos son una característica nueva en C# 7.1 y la versión de lenguaje predeterminada del proyecto es C# 7.0, debe cambiar la versión del lenguaje a C# 7.1 o superior.</span><span class="sxs-lookup"><span data-stu-id="9555d-339">Because inferred tuple element names are a new feature in C# 7.1 and the default language version of the project is C# 7.0, you need to change the language version to C# 7.1 or higher.</span></span>
<span data-ttu-id="9555d-340">Para ello, haga clic con el botón derecho en el nodo del proyecto en el **Explorador de soluciones** y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="9555d-340">To do that, right-click on the project node in **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="9555d-341">Seleccione la pestaña **Compilar** y, después, el botón **Opciones avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="9555d-341">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="9555d-342">En la lista desplegable, seleccione **C# 7.1** (o una versión superior).</span><span class="sxs-lookup"><span data-stu-id="9555d-342">In the dropdown, select  **C# 7.1** (or a higher version).</span></span> <span data-ttu-id="9555d-343">Seleccione el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9555d-343">Select the **OK** button.</span></span>

## <a name="results"></a><span data-ttu-id="9555d-344">Resultados</span><span class="sxs-lookup"><span data-stu-id="9555d-344">Results</span></span>

<span data-ttu-id="9555d-345">Los resultados deberían ser similares a los indicados a continuación.</span><span class="sxs-lookup"><span data-stu-id="9555d-345">Your results should be similar to the following.</span></span> <span data-ttu-id="9555d-346">A medida que la canalización procesa, muestra mensajes.</span><span class="sxs-lookup"><span data-stu-id="9555d-346">As the pipeline processes, it displays messages.</span></span> <span data-ttu-id="9555d-347">Puede ver las advertencias o mensajes de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="9555d-347">You may see warnings, or processing messages.</span></span> <span data-ttu-id="9555d-348">Se han quitado de los siguientes resultados para mayor claridad.</span><span class="sxs-lookup"><span data-stu-id="9555d-348">These have been removed from the following results for clarity.</span></span>

```console
Model quality metrics evaluation
--------------------------------
Accuracy: 94.44%
Auc: 98.77%
F1Score: 94.74%
=============== End of model evaluation ===============

=============== Prediction Test of model with a single sample and test dataset ===============

Sentiment: This is a very rude movie | Prediction: Toxic | Probability: 0.5297049
=============== End of Predictions ===============

=============== New iteration of Model ===============
=============== Create and Train the Model ===============
=============== End of training ===============


The model is saved to: C:\Tutorial\SentimentAnalysis\bin\Debug\netcoreapp2.1\Data\Model.zip

=============== Prediction Test of loaded model with a multiple sample ===============

Sentiment: This is a very rude movie | Prediction: Toxic | Probability: 0.4585565
Sentiment: I love this article. | Prediction: Not Toxic | Probability: 0.09454837

```

<span data-ttu-id="9555d-349">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="9555d-349">Congratulations!</span></span> <span data-ttu-id="9555d-350">Ya ha creado correctamente un modelo de aprendizaje automático para clasificar y predecir los sentimientos de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="9555d-350">You've now successfully built a machine learning model for classifying and predicting messages sentiment.</span></span> <span data-ttu-id="9555d-351">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).</span><span class="sxs-lookup"><span data-stu-id="9555d-351">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9555d-352">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="9555d-352">Next steps</span></span>

<span data-ttu-id="9555d-353">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="9555d-353">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="9555d-354">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="9555d-354">Understand the problem</span></span>
> * <span data-ttu-id="9555d-355">Seleccionar el algoritmo de aprendizaje automático adecuado</span><span class="sxs-lookup"><span data-stu-id="9555d-355">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="9555d-356">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="9555d-356">Prepare your data</span></span>
> * <span data-ttu-id="9555d-357">Transformar los datos</span><span class="sxs-lookup"><span data-stu-id="9555d-357">Transform the data</span></span>
> * <span data-ttu-id="9555d-358">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="9555d-358">Train the model</span></span>
> * <span data-ttu-id="9555d-359">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="9555d-359">Evaluate the model</span></span>
> * <span data-ttu-id="9555d-360">Predecir con el modelo entrenado</span><span class="sxs-lookup"><span data-stu-id="9555d-360">Predict with the trained model</span></span>
> * <span data-ttu-id="9555d-361">Implementar y predecir con un modelo cargado</span><span class="sxs-lookup"><span data-stu-id="9555d-361">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="9555d-362">Siga con el siguiente tutorial para obtener más información</span><span class="sxs-lookup"><span data-stu-id="9555d-362">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="9555d-363">Clasificación de problemas</span><span class="sxs-lookup"><span data-stu-id="9555d-363">Issue Classification</span></span>](github-issue-classification.md)
