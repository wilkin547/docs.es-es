---
title: Uso de ML.NET en un escenario de clasificación de problemas multiclase de GitHub
description: Descubra cómo usar ML.NET en un escenario de clasificación multiclase para clasificar los problemas de GitHub y asignarlos a un área determinada.
ms.date: 02/01/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 79c0ae1ba38b410c0709659a4e5ee1ac2308b983
ms.sourcegitcommit: facefcacd7ae2e5645e463bc841df213c505ffd4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2019
ms.locfileid: "55739428"
---
# <a name="tutorial-use-mlnet-in-a-multiclass-classification-scenario-to-classify-github-issues"></a><span data-ttu-id="513c0-103">Tutorial: Uso de ML.NET en un escenario de clasificación multiclase para clasificar problemas de GitHub</span><span class="sxs-lookup"><span data-stu-id="513c0-103">Tutorial: Use ML.NET in a multiclass classification scenario to classify GitHub issues</span></span>

<span data-ttu-id="513c0-104">En este tutorial de ejemplo se muestra cómo utilizar ML.NET para crear un clasificador de problemas de GitHub a través de una aplicación de consola de .NET Core con C# en Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="513c0-104">This sample tutorial illustrates using ML.NET to create a GitHub issue classifier via a .NET Core console application using C# in Visual Studio 2017.</span></span>

<span data-ttu-id="513c0-105">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="513c0-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="513c0-106">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="513c0-106">Understand the problem</span></span>
> * <span data-ttu-id="513c0-107">Seleccionar el algoritmo de aprendizaje automático adecuado</span><span class="sxs-lookup"><span data-stu-id="513c0-107">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="513c0-108">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="513c0-108">Prepare your data</span></span>
> * <span data-ttu-id="513c0-109">Extraer características y transformar los datos</span><span class="sxs-lookup"><span data-stu-id="513c0-109">Extract Features and transform the data</span></span>
> * <span data-ttu-id="513c0-110">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="513c0-110">Train the model</span></span>
> * <span data-ttu-id="513c0-111">Evaluar el modelo con otro conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="513c0-111">Evaluate the model with a different dataset</span></span>
> * <span data-ttu-id="513c0-112">Predecir una única instancia del resultado de datos de prueba con el modelo entrenado</span><span class="sxs-lookup"><span data-stu-id="513c0-112">Predict a single instance of test data outcome with the trained model</span></span>
> * <span data-ttu-id="513c0-113">Predecir una única instancia de datos de prueba con un modelo cargado</span><span class="sxs-lookup"><span data-stu-id="513c0-113">Predict a single instance of test data with a loaded model</span></span>

> [!NOTE]
> <span data-ttu-id="513c0-114">Este tema hace referencia a ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios.</span><span class="sxs-lookup"><span data-stu-id="513c0-114">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="513c0-115">Para obtener más información, visite [la introducción de ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="513c0-115">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

## <a name="github-issue-sample-overview"></a><span data-ttu-id="513c0-116">Información general sobre el ejemplo de problema de GitHub</span><span class="sxs-lookup"><span data-stu-id="513c0-116">GitHub issue sample overview</span></span>

<span data-ttu-id="513c0-117">El ejemplo es una aplicación de consola que utiliza ML.NET para entrenar un modelo que clasifica y predice el área de etiqueta de un problema de GitHub.</span><span class="sxs-lookup"><span data-stu-id="513c0-117">The sample is a console app that uses ML.NET to train a model that classifies and predicts the Area label for a GitHub issue.</span></span> <span data-ttu-id="513c0-118">También se evalúa el modelo con un segundo conjunto de datos para realizar el análisis de calidad.</span><span class="sxs-lookup"><span data-stu-id="513c0-118">It also evaluates the model with a second dataset for quality analysis.</span></span> <span data-ttu-id="513c0-119">Los conjuntos de datos del problema proceden del repositorio de GitHub dotnet/corefx.</span><span class="sxs-lookup"><span data-stu-id="513c0-119">The issue datasets are from the dotnet/corefx GitHub repo.</span></span>

<span data-ttu-id="513c0-120">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification).</span><span class="sxs-lookup"><span data-stu-id="513c0-120">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="513c0-121">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="513c0-121">Prerequisites</span></span>

* <span data-ttu-id="513c0-122">[Visual Studio 2017 15.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.</span><span class="sxs-lookup"><span data-stu-id="513c0-122">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* <span data-ttu-id="513c0-123">[Archivo de problemas de GitHub delimitado por pestañas (issues_train.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv).</span><span class="sxs-lookup"><span data-stu-id="513c0-123">The [Github issues tab separated file (issues_train.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv).</span></span>
* <span data-ttu-id="513c0-124">[Prueba de problemas de GitHub delimitado por pestañas (issues_test.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv).</span><span class="sxs-lookup"><span data-stu-id="513c0-124">The [Github issues test tab separated file (issues_test.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv).</span></span>

## <a name="machine-learning-workflow"></a><span data-ttu-id="513c0-125">Flujo de trabajo del aprendizaje automático</span><span class="sxs-lookup"><span data-stu-id="513c0-125">Machine learning workflow</span></span>

<span data-ttu-id="513c0-126">En este tutorial se sigue un flujo de trabajo de aprendizaje automático que permite que el proceso avance de manera ordenada.</span><span class="sxs-lookup"><span data-stu-id="513c0-126">This tutorial follows a machine learning workflow that enables the process to move in an orderly fashion.</span></span>

<span data-ttu-id="513c0-127">Las fases del flujo de trabajo son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="513c0-127">The workflow phases are as follows:</span></span>

1. <span data-ttu-id="513c0-128">**Entender el problema**</span><span class="sxs-lookup"><span data-stu-id="513c0-128">**Understand the problem**</span></span>
2. <span data-ttu-id="513c0-129">**Preparar los datos**</span><span class="sxs-lookup"><span data-stu-id="513c0-129">**Prepare your data**</span></span>
   * <span data-ttu-id="513c0-130">**Cargar los datos**</span><span class="sxs-lookup"><span data-stu-id="513c0-130">**Load the data**</span></span>
   * <span data-ttu-id="513c0-131">**Extraer características (transformar los datos)**</span><span class="sxs-lookup"><span data-stu-id="513c0-131">**Extract features (Transform your data)**</span></span>
3. <span data-ttu-id="513c0-132">**Compilar y entrenar**</span><span class="sxs-lookup"><span data-stu-id="513c0-132">**Build and train**</span></span> 
   * <span data-ttu-id="513c0-133">**Entrenar el modelo**</span><span class="sxs-lookup"><span data-stu-id="513c0-133">**Train the model**</span></span>
   * <span data-ttu-id="513c0-134">**Evaluar el modelo**</span><span class="sxs-lookup"><span data-stu-id="513c0-134">**Evaluate the model**</span></span>
4. <span data-ttu-id="513c0-135">**Run**</span><span class="sxs-lookup"><span data-stu-id="513c0-135">**Run**</span></span>
   * <span data-ttu-id="513c0-136">**Consumo del modelo**</span><span class="sxs-lookup"><span data-stu-id="513c0-136">**Model consumption**</span></span>

### <a name="understand-the-problem"></a><span data-ttu-id="513c0-137">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="513c0-137">Understand the problem</span></span>

<span data-ttu-id="513c0-138">Primero debe entender el problema, de manera que pueda dividirlo en partes que admitan la compilación y el entrenamiento del problema.</span><span class="sxs-lookup"><span data-stu-id="513c0-138">You first need to understand the problem, so you can break it down to parts that can support building and training the model.</span></span> <span data-ttu-id="513c0-139">Desglosar el problema en partes le permite predecir y evaluar los resultados.</span><span class="sxs-lookup"><span data-stu-id="513c0-139">Breaking  down the problem allows you to predict and evaluate the results.</span></span>

<span data-ttu-id="513c0-140">El problema de este tutorial es comprender a qué área pertenecen los problemas de GitHub entrantes, de modo que se puedan etiquetar correctamente para priorizarlos y programarlos.</span><span class="sxs-lookup"><span data-stu-id="513c0-140">The problem for this tutorial is to understand what area incoming GitHub issues belong to in order to label them correctly for prioritization and scheduling.</span></span>

<span data-ttu-id="513c0-141">Puede desglosar el problema en los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="513c0-141">You can break down the problem to the following parts:</span></span>

* <span data-ttu-id="513c0-142">texto del título del problema</span><span class="sxs-lookup"><span data-stu-id="513c0-142">the issue title text</span></span>
* <span data-ttu-id="513c0-143">texto de la descripción del problema</span><span class="sxs-lookup"><span data-stu-id="513c0-143">the issue description text</span></span>
* <span data-ttu-id="513c0-144">valor de área para los datos de entrenamiento del modelo</span><span class="sxs-lookup"><span data-stu-id="513c0-144">an area value for the model training data</span></span>
* <span data-ttu-id="513c0-145">valor de predicción del área que se puede evaluar y usar de forma operativa</span><span class="sxs-lookup"><span data-stu-id="513c0-145">a predicted area value that you can evaluate and then use operationally</span></span>

<span data-ttu-id="513c0-146">Después, deberá **determinar** el área, lo que lo ayudará con la selección de tareas de aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="513c0-146">You then need to **determine** the area, which helps you with the machine learning task selection.</span></span>

## <a name="select-the-appropriate-machine-learning-algorithm"></a><span data-ttu-id="513c0-147">Seleccionar el algoritmo de aprendizaje automático adecuado</span><span class="sxs-lookup"><span data-stu-id="513c0-147">Select the appropriate machine learning algorithm</span></span>

<span data-ttu-id="513c0-148">Con este problema, tiene constancia de los siguientes hechos:</span><span class="sxs-lookup"><span data-stu-id="513c0-148">With this problem, you know the following facts:</span></span>

<span data-ttu-id="513c0-149">Datos de entrenamiento:</span><span class="sxs-lookup"><span data-stu-id="513c0-149">Training data:</span></span>

<span data-ttu-id="513c0-150">Los problemas de GitHub se pueden etiquetar en varias áreas (**Área**), tal como se muestra en los siguientes ejemplos:</span><span class="sxs-lookup"><span data-stu-id="513c0-150">GitHub issues can be labeled in several areas (**Area**) as in the following examples:</span></span>

* <span data-ttu-id="513c0-151">area-System.Numerics</span><span class="sxs-lookup"><span data-stu-id="513c0-151">area-System.Numerics</span></span>
* <span data-ttu-id="513c0-152">area-System.Xml</span><span class="sxs-lookup"><span data-stu-id="513c0-152">area-System.Xml</span></span>
* <span data-ttu-id="513c0-153">area-Infrastructure</span><span class="sxs-lookup"><span data-stu-id="513c0-153">area-Infrastructure</span></span>
* <span data-ttu-id="513c0-154">area-System.Linq</span><span class="sxs-lookup"><span data-stu-id="513c0-154">area-System.Linq</span></span>
* <span data-ttu-id="513c0-155">area-System.IO</span><span class="sxs-lookup"><span data-stu-id="513c0-155">area-System.IO</span></span>

<span data-ttu-id="513c0-156">Prediga el **área** de un nuevo problema de GitHub, como en los siguientes ejemplos:</span><span class="sxs-lookup"><span data-stu-id="513c0-156">Predict the **Area** of a new GitHub Issue such as in the following examples:</span></span>

* <span data-ttu-id="513c0-157">Contract.Assert en comparación con Debug.Assert</span><span class="sxs-lookup"><span data-stu-id="513c0-157">Contract.Assert vs Debug.Assert</span></span>
* <span data-ttu-id="513c0-158">Establecimiento de los campos como de solo lectura en System.Xml</span><span class="sxs-lookup"><span data-stu-id="513c0-158">Make fields readonly in System.Xml</span></span>

<span data-ttu-id="513c0-159">El algoritmo de aprendizaje automático de clasificación es ideal para este escenario.</span><span class="sxs-lookup"><span data-stu-id="513c0-159">The classification machine learning algorithm is best suited for this scenario.</span></span>

### <a name="about-the-classification-learning-algorithm"></a><span data-ttu-id="513c0-160">Acerca del algoritmo de aprendizaje de clasificación</span><span class="sxs-lookup"><span data-stu-id="513c0-160">About the classification learning algorithm</span></span>

<span data-ttu-id="513c0-161">La clasificación es un algoritmo de aprendizaje automático que usa datos para **determinar** la categoría, el tipo o la clase de un elemento o fila de datos.</span><span class="sxs-lookup"><span data-stu-id="513c0-161">Classification is a machine learning algorithm that uses data to **determine** the category, type, or class of an item or row of data.</span></span> <span data-ttu-id="513c0-162">Por ejemplo, puede utilizar la clasificación para:</span><span class="sxs-lookup"><span data-stu-id="513c0-162">For example, you can use classification to:</span></span>

* <span data-ttu-id="513c0-163">Identificar un sentimiento como positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="513c0-163">Identify sentiment as positive or negative.</span></span>
* <span data-ttu-id="513c0-164">Clasificar correo electrónico como correo no deseado o correo válido.</span><span class="sxs-lookup"><span data-stu-id="513c0-164">Classify email as spam, junk, or good.</span></span>
* <span data-ttu-id="513c0-165">Determinar si la muestra de laboratorio de un paciente es cancerosa.</span><span class="sxs-lookup"><span data-stu-id="513c0-165">Determine whether a patient's lab sample is cancerous.</span></span>
* <span data-ttu-id="513c0-166">Categorizar a los clientes por su propensión a responder a una campaña de ventas.</span><span class="sxs-lookup"><span data-stu-id="513c0-166">Categorize customers by their propensity to respond to a sales campaign.</span></span>

<span data-ttu-id="513c0-167">Los casos de uso del algoritmo de aprendizaje de clasificación son a menudo de uno de los tipos siguientes:</span><span class="sxs-lookup"><span data-stu-id="513c0-167">Classification learning algorithm use cases are frequently one of the following types:</span></span>

* <span data-ttu-id="513c0-168">Binario: A o B.</span><span class="sxs-lookup"><span data-stu-id="513c0-168">Binary: either A or B.</span></span>
* <span data-ttu-id="513c0-169">Multiclase: varias categorías que se pueden predecir mediante el uso de un único modelo.</span><span class="sxs-lookup"><span data-stu-id="513c0-169">Multiclass: multiple categories that can be predicted by using a single model.</span></span>

<span data-ttu-id="513c0-170">Para este tipo de problema, use un algoritmo de aprendizaje de clasificación multiclase, ya que la predicción de categoría de problema puede ser una de varias categorías (multiclase) en lugar de solo dos (binaria).</span><span class="sxs-lookup"><span data-stu-id="513c0-170">For this type of problem, use a Multiclass classification learning algorithm, since your issue category prediction can be one of multiple categories (multiclass) rather than just two (binary).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="513c0-171">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="513c0-171">Create a console application</span></span>

### <a name="create-a-project"></a><span data-ttu-id="513c0-172">Crear un proyecto</span><span class="sxs-lookup"><span data-stu-id="513c0-172">Create a project</span></span>

1. <span data-ttu-id="513c0-173">Abra Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="513c0-173">Open Visual Studio 2017.</span></span> <span data-ttu-id="513c0-174">Seleccione **Archivo** > **Nuevo** > **Proyecto** de la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="513c0-174">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="513c0-175">En el cuadro de diálogo **Nuevo proyecto**, seleccione el nodo **Visual C#** seguido del nodo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="513c0-175">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="513c0-176">Después, seleccione la plantilla del proyecto **Aplicación de consola (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="513c0-176">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="513c0-177">En el cuadro de texto **Nombre**, escriba "SentimentAnalysis" y después haga clic en el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="513c0-177">In the **Name** text box, type "SentimentAnalysis" and then select the **OK** button.</span></span>

2. <span data-ttu-id="513c0-178">Cree un directorio denominado *Datos* en el proyecto para guardar los archivos del conjunto de datos:</span><span class="sxs-lookup"><span data-stu-id="513c0-178">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="513c0-179">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **Nueva carpeta**.</span><span class="sxs-lookup"><span data-stu-id="513c0-179">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="513c0-180">Escriba "Datos" y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="513c0-180">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="513c0-181">En el proyecto, cree un directorio denominado *Modelos* para guardar el modelo:</span><span class="sxs-lookup"><span data-stu-id="513c0-181">Create a directory named *Models* in your project to save your model:</span></span>

    <span data-ttu-id="513c0-182">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **Nueva carpeta**.</span><span class="sxs-lookup"><span data-stu-id="513c0-182">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="513c0-183">Escriba "Modelos" y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="513c0-183">Type "Models" and hit Enter.</span></span>

4. <span data-ttu-id="513c0-184">Instale el **paquete NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="513c0-184">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="513c0-185">En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="513c0-185">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="513c0-186">Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.ML**, seleccione ese paquete en la lista y seleccione el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="513c0-186">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="513c0-187">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="513c0-187">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="513c0-188">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="513c0-188">Prepare your data</span></span>

1. <span data-ttu-id="513c0-189">Descargue los conjuntos de datos [issues_train.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) e [issues_test.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) y guárdelos en la carpeta *Datos* que ha creado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="513c0-189">Download the [issues_train.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) and the [issues_test.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) data sets and save them to the *Data* folder previously created.</span></span> <span data-ttu-id="513c0-190">El primer conjunto de datos entrena el modelo de aprendizaje automático y el segundo puede usarse para evaluar su grado de precisión.</span><span class="sxs-lookup"><span data-stu-id="513c0-190">The first dataset trains the machine learning model and the second can be used to evaluate how accurate your model is.</span></span>

2. <span data-ttu-id="513c0-191">En el Explorador de soluciones, haga clic con el botón secundario en cada uno de los archivos \*.tsv y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="513c0-191">In Solution Explorer, right-click each of the \*.tsv files and select **Properties**.</span></span> <span data-ttu-id="513c0-192">En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.</span><span class="sxs-lookup"><span data-stu-id="513c0-192">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="513c0-193">Crear clases y definir rutas de acceso</span><span class="sxs-lookup"><span data-stu-id="513c0-193">Create classes and define paths</span></span>

<span data-ttu-id="513c0-194">Agregue las siguientes instrucciones `using` adicionales a la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="513c0-194">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddUsings)]

<span data-ttu-id="513c0-195">Cree tres campos globales para contener las rutas de acceso a los archivos descargados recientemente y variables globales para `MLContext`, `DataView`, `PredictionEngine` y `TextLoader`:</span><span class="sxs-lookup"><span data-stu-id="513c0-195">Create three global fields to hold the paths to the recently downloaded files, and global variables for the `MLContext`,`DataView`, `PredictionEngine`, and `TextLoader`:</span></span>

* <span data-ttu-id="513c0-196">`_trainDataPath` tiene la ruta de acceso al conjunto de datos utilizado para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="513c0-196">`_trainDataPath` has the path to the dataset used to train the model.</span></span>
* <span data-ttu-id="513c0-197">`_testDataPath` tiene la ruta de acceso al conjunto de datos utilizado para evaluar el modelo.</span><span class="sxs-lookup"><span data-stu-id="513c0-197">`_testDataPath` has the path to the dataset used to evaluate the model.</span></span>
* <span data-ttu-id="513c0-198">`_modelPath` tiene la ruta de acceso donde se guarda el modelo entrenado.</span><span class="sxs-lookup"><span data-stu-id="513c0-198">`_modelPath` has the path where the trained model is saved.</span></span>
* <span data-ttu-id="513c0-199">`_mlContext` es el elemento <xref:Microsoft.ML.MLContext> que proporciona el contexto de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="513c0-199">`_mlContext` is the <xref:Microsoft.ML.MLContext> that provides processing context.</span></span>
* <span data-ttu-id="513c0-200">`_trainingDataView` es el elemento <xref:Microsoft.ML.Data.IDataView> que se usa para procesar el conjunto de datos de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="513c0-200">`_trainingDataView` is the <xref:Microsoft.ML.Data.IDataView> used to process the training dataset.</span></span>
* <span data-ttu-id="513c0-201">`_predEngine` es el elemento <xref:Microsoft.ML.PredictionEngine%602> que se usa para las predicciones únicas.</span><span class="sxs-lookup"><span data-stu-id="513c0-201">`_predEngine` is the <xref:Microsoft.ML.PredictionEngine%602> used for single predictions.</span></span>
* <span data-ttu-id="513c0-202">`_reader` es el <xref:Microsoft.ML.Data.TextLoader> utilizado para cargar y transformar los conjuntos de datos.</span><span class="sxs-lookup"><span data-stu-id="513c0-202">`_reader` is the <xref:Microsoft.ML.Data.TextLoader> used to load and transform the datasets.</span></span>

<span data-ttu-id="513c0-203">Agregue el código siguiente a la línea justo encima del método `Main` para especificar esas rutas de acceso y otras variables:</span><span class="sxs-lookup"><span data-stu-id="513c0-203">Add the following code to the line right above the `Main` method to specify those paths and the other variables:</span></span>

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DeclareGlobalVariables)]

<span data-ttu-id="513c0-204">Cree algunas clases para los datos de entrada y las predicciones.</span><span class="sxs-lookup"><span data-stu-id="513c0-204">Create some classes for your input data and predictions.</span></span> <span data-ttu-id="513c0-205">Agregue una nueva clase a su proyecto:</span><span class="sxs-lookup"><span data-stu-id="513c0-205">Add a new class to your project:</span></span>

1. <span data-ttu-id="513c0-206">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="513c0-206">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="513c0-207">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *GitHubIssueData.cs*.</span><span class="sxs-lookup"><span data-stu-id="513c0-207">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *GitHubIssueData.cs*.</span></span> <span data-ttu-id="513c0-208">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="513c0-208">Then, select the **Add** button.</span></span>

    <span data-ttu-id="513c0-209">Se abre el archivo *GitHubIssueData.cs* en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="513c0-209">The *GitHubIssueData.cs* file opens in the code editor.</span></span> <span data-ttu-id="513c0-210">Agregue la siguiente instrucción `using` a la parte superior de *GitHubIssueData.cs*:</span><span class="sxs-lookup"><span data-stu-id="513c0-210">Add the following `using` statement to the top of *GitHubIssueData.cs*:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#AddUsings)]

<span data-ttu-id="513c0-211">Quite la definición de clase existente y agregue el código siguiente, que tiene dos clases `GitHubIssue` y `IssuePrediction`, al archivo *GitHubIssueData.cs*:</span><span class="sxs-lookup"><span data-stu-id="513c0-211">Remove the existing class definition and add the following code, which has two classes `GitHubIssue` and `IssuePrediction`, to the *GitHubIssueData.cs* file:</span></span>

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#DeclareTypes)]

<span data-ttu-id="513c0-212">`GitHubIssue` es la clase de conjunto de datos de entrada y contiene los siguientes campos de <xref:System.String>:</span><span class="sxs-lookup"><span data-stu-id="513c0-212">`GitHubIssue` is the input dataset class and has the following <xref:System.String> fields:</span></span>

* <span data-ttu-id="513c0-213">`ID` contiene un valor para el id. del problema de GitHub</span><span class="sxs-lookup"><span data-stu-id="513c0-213">`ID` contains a value for the GitHub issue ID</span></span>
* <span data-ttu-id="513c0-214">`Area` contiene un valor para la etiqueta `Area`</span><span class="sxs-lookup"><span data-stu-id="513c0-214">`Area` contains a value for the `Area` label</span></span>
* <span data-ttu-id="513c0-215">`Title` contiene el título del problema de GitHub</span><span class="sxs-lookup"><span data-stu-id="513c0-215">`Title` contains the GitHub issue title</span></span>
* <span data-ttu-id="513c0-216">`Description` contiene la descripción del problema de GitHub</span><span class="sxs-lookup"><span data-stu-id="513c0-216">`Description` contains the GitHub issue description</span></span>

<span data-ttu-id="513c0-217">`IssuePrediction` es la clase usada para la predicción una vez entrenado el modelo.</span><span class="sxs-lookup"><span data-stu-id="513c0-217">`IssuePrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="513c0-218">Tiene un solo elemento `string` (`Area`) y un atributo `PredictedLabel` `ColumnName`.</span><span class="sxs-lookup"><span data-stu-id="513c0-218">It has a single `string` (`Area`) and a `PredictedLabel` `ColumnName` attribute.</span></span> <span data-ttu-id="513c0-219">`Label` se usa para crear y entrenar el modelo, y se usa también con un segundo conjunto de datos para evaluar el modelo.</span><span class="sxs-lookup"><span data-stu-id="513c0-219">The `Label` is used to create and train the model, and it's also used with a second dataset to evaluate the model.</span></span> <span data-ttu-id="513c0-220">`PredictedLabel` se usa durante la predicción y la evaluación.</span><span class="sxs-lookup"><span data-stu-id="513c0-220">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="513c0-221">Para la evaluación, se utiliza una entrada con los datos de entrenamiento, los valores de predicción y el modelo.</span><span class="sxs-lookup"><span data-stu-id="513c0-221">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="513c0-222">Cuando se crea un modelo con ML.NET, empieza creando un elemento <xref:Microsoft.ML.MLContext>.</span><span class="sxs-lookup"><span data-stu-id="513c0-222">When building a model with ML.NET, you start by creating an <xref:Microsoft.ML.MLContext>.</span></span> <span data-ttu-id="513c0-223">`MLContext` es comparable conceptualmente a usar `DbContext` en Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="513c0-223">`MLContext` is comparable conceptually to using `DbContext` in Entity Framework.</span></span> <span data-ttu-id="513c0-224">El entorno proporciona un contexto para el trabajo de ML que puede usarse para el seguimiento y registro de excepciones.</span><span class="sxs-lookup"><span data-stu-id="513c0-224">The environment provides a context for your ML job that can be used for exception tracking and logging.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="513c0-225">Inicializar variables en Main</span><span class="sxs-lookup"><span data-stu-id="513c0-225">Initialize variables in Main</span></span>

<span data-ttu-id="513c0-226">Inicialice la variante global `_mlContext` con una nueva instancia de `MLContext` usando una inicialización aleatoria (`seed: 0`) para obtener resultados repetibles o deterministas en varios entrenamientos.</span><span class="sxs-lookup"><span data-stu-id="513c0-226">Initialize the `_mlContext` global variable  with a new instance of `MLContext` with a random seed (`seed: 0`) for repeatable/deterministic results across multiple trainings.</span></span>  <span data-ttu-id="513c0-227">Reemplace la línea `Console.WriteLine("Hello World!")` por el código siguiente en el método `Main`:</span><span class="sxs-lookup"><span data-stu-id="513c0-227">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateMLContext)]

## <a name="load-the-data"></a><span data-ttu-id="513c0-228">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="513c0-228">Load the data</span></span>

<span data-ttu-id="513c0-229">A continuación, inicialice la variable global `_trainingDataView` <xref:Microsoft.ML.Data.IDataView> y cargue los datos con el parámetro `_trainDataPath`.</span><span class="sxs-lookup"><span data-stu-id="513c0-229">Next, initialize the `_trainingDataView` <xref:Microsoft.ML.Data.IDataView> global variable and load the data with the `_trainDataPath` parameter.</span></span>

 <span data-ttu-id="513c0-230">Como la entrada y salida de [`Transforms`](../basic-concepts-model-training-in-mldotnet.md#transformer), `DataView` es el tipo de canalización de datos fundamentales, comparable con `IEnumerable` para `LINQ`.</span><span class="sxs-lookup"><span data-stu-id="513c0-230">As the input and output of [`Transforms`](../basic-concepts-model-training-in-mldotnet.md#transformer), a `DataView` is the fundamental data pipeline type, comparable to `IEnumerable` for `LINQ`.</span></span>

<span data-ttu-id="513c0-231">En ML.NET, los datos son similares a `SQL view`.</span><span class="sxs-lookup"><span data-stu-id="513c0-231">In ML.NET, data is similar to a `SQL view`.</span></span> <span data-ttu-id="513c0-232">Se evalúan lentamente, se esquematizan y son heterogéneos.</span><span class="sxs-lookup"><span data-stu-id="513c0-232">It is lazily evaluated, schematized, and heterogenous.</span></span> <span data-ttu-id="513c0-233">El objeto es la primera parte de la canalización y carga los datos.</span><span class="sxs-lookup"><span data-stu-id="513c0-233">The object is the first part of the pipeline, and loads the data.</span></span> <span data-ttu-id="513c0-234">Para este tutorial, carga un conjunto de datos con los títulos y descripciones de los problemas, así como la etiqueta de GitHub del área correspondiente.</span><span class="sxs-lookup"><span data-stu-id="513c0-234">For this tutorial, it loads a dataset with issue titles, descriptions, and corresponding area GitHub label.</span></span> <span data-ttu-id="513c0-235">El elemento `DataView` se usa para crear y entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="513c0-235">The `DataView` is used to create and train the model.</span></span>

<span data-ttu-id="513c0-236">Puesto que el tipo de modelo de datos `GitHubIssue` que ha creado anteriormente coincide con el esquema del conjunto de datos, puede combinar la inicialización, la asignación y la carga del conjunto de datos en una línea de código.</span><span class="sxs-lookup"><span data-stu-id="513c0-236">Since your previously created `GitHubIssue` data model type matches the dataset schema, you can combine the initialization, mapping, and dataset loading into one line of code.</span></span>

<span data-ttu-id="513c0-237">La primera parte de la línea (`CreateTextReader<GitHubIssue>(hasHeader: true)`) crea un elemento <xref:Microsoft.ML.Data.TextLoader> mediante la inferencia del esquema del conjunto de datos del tipo de modelo de datos `GitHubIssue` y el uso del encabezado del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="513c0-237">The first part of the line (`CreateTextReader<GitHubIssue>(hasHeader: true)`) creates a <xref:Microsoft.ML.Data.TextLoader> by inferring the dataset schema from the `GitHubIssue` data model type and using the dataset header.</span></span>

<span data-ttu-id="513c0-238">Ha definido el esquema de datos anteriormente al crear la clase `GitHubIssue`.</span><span class="sxs-lookup"><span data-stu-id="513c0-238">You defined the data schema previously when you created the `GitHubIssue` class.</span></span> <span data-ttu-id="513c0-239">Para su esquema:</span><span class="sxs-lookup"><span data-stu-id="513c0-239">For your schema:</span></span>

* <span data-ttu-id="513c0-240">`ID`, la primera columna (id. de problema de GitHub).</span><span class="sxs-lookup"><span data-stu-id="513c0-240">the first column `ID` (GitHub Issue ID)</span></span>
* <span data-ttu-id="513c0-241">`Area`, la segunda columna (la predicción para el entrenamiento).</span><span class="sxs-lookup"><span data-stu-id="513c0-241">the second column `Area` (the prediction for training)</span></span>
* <span data-ttu-id="513c0-242">`Title`, la tercera columna (título del problema de GitHub), es la primera [característica](../resources/glossary.md##feature) usada para predecir el `Area`.</span><span class="sxs-lookup"><span data-stu-id="513c0-242">the third column `Title` (GitHub issue title) is the first [feature](../resources/glossary.md##feature)  used for predicting the `Area`</span></span>
* <span data-ttu-id="513c0-243">`Description`, la cuarta columna, es la segunda característica usada para predecir el `Area`.</span><span class="sxs-lookup"><span data-stu-id="513c0-243">the fourth column  `Description` is the second feature used for predicting the `Area`</span></span>

<span data-ttu-id="513c0-244">La segunda parte de la línea (`.Read(_trainDataPath)`) usa el método <xref:Microsoft.ML.Data.TextLoader.Read%2A> para cargar el archivo de texto del entrenamiento usando `_trainDataPath` en la variable global `IDataView` (`_trainingDataView`).</span><span class="sxs-lookup"><span data-stu-id="513c0-244">The second part of the line  (`.Read(_trainDataPath)`) uses <xref:Microsoft.ML.Data.TextLoader.Read%2A> method to load the training text file using `_trainDataPath` into the `IDataView` (`_trainingDataView`) global variable.</span></span>  

<span data-ttu-id="513c0-245">Para inicializar y cargar la variable global `_trainingDataView` con el fin de volver a usarla para la canalización, agregue el siguiente código después de la inicialización de `mlContext`:</span><span class="sxs-lookup"><span data-stu-id="513c0-245">To initialize and load the `_trainingDataView` global variable in order to use it for the pipeline, add the following code after the  `mlContext` initialization:</span></span>

[!code-csharp[LoadTrainData](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTrainData)]


<span data-ttu-id="513c0-246">Agregue lo siguiente como la siguiente línea de código en el método `Main`:</span><span class="sxs-lookup"><span data-stu-id="513c0-246">Add the following as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallProcessData](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallProcessData)]

<span data-ttu-id="513c0-247">El método `ProcessData` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="513c0-247">The `ProcessData` method executes the following tasks:</span></span>

* <span data-ttu-id="513c0-248">Extrae y transforma los datos.</span><span class="sxs-lookup"><span data-stu-id="513c0-248">Extracts and transforms the data.</span></span>
* <span data-ttu-id="513c0-249">Devuelve la canalización de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="513c0-249">Returns the processing pipeline.</span></span>

<span data-ttu-id="513c0-250">Cree el método `ProcessData`, justo después del método `Main`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="513c0-250">Create the `ProcessData` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static EstimatorChain<ITransformer> ProcessData()
{

}
```

## <a name="extract-features-and-transform-the-data"></a><span data-ttu-id="513c0-251">Extraer características y transformar los datos</span><span class="sxs-lookup"><span data-stu-id="513c0-251">Extract Features and transform the data</span></span>

<span data-ttu-id="513c0-252">El procesamiento previo y la limpieza de datos son tareas importantes que se producen antes de que un conjunto de datos se utilice de forma eficaz para el aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="513c0-252">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span> <span data-ttu-id="513c0-253">Los datos sin procesar contienen a menudo ruido y son poco de fiar; además, es posible que les falten valores.</span><span class="sxs-lookup"><span data-stu-id="513c0-253">Raw data is often noisy and unreliable, and may be missing values.</span></span> <span data-ttu-id="513c0-254">El uso de datos sin estas tareas de modelado puede producir resultados engañosos.</span><span class="sxs-lookup"><span data-stu-id="513c0-254">Using data without these modeling tasks can produce misleading results.</span></span>

<span data-ttu-id="513c0-255">Las tuberías de transformación de ML.NET componen un conjunto `transforms` personalización que se aplica a sus datos antes del entrenamiento o la prueba.</span><span class="sxs-lookup"><span data-stu-id="513c0-255">ML.NET's transform pipelines compose a custom `transforms`set that is applied to your data before training or testing.</span></span> <span data-ttu-id="513c0-256">El propósito principal de las transformaciones es la [caracterización](../resources/glossary.md#feature-engineering) de datos.</span><span class="sxs-lookup"><span data-stu-id="513c0-256">The transforms' primary purpose is data [featurization](../resources/glossary.md#feature-engineering).</span></span> <span data-ttu-id="513c0-257">Los algoritmos de aprendizaje automático comprenden los datos [caracterizados](../resources/glossary.md#feature), por lo que el paso siguiente es transformar nuestro datos textuales en un formato que reconozcan nuestros algoritmos de ML.</span><span class="sxs-lookup"><span data-stu-id="513c0-257">Machine learning algorithms understand [featurized](../resources/glossary.md#feature) data, so the next step is to transform our textual data into a format that our ML algorithms recognize.</span></span> <span data-ttu-id="513c0-258">Ese formato es un [vector numérico](../resources/glossary.md#numerical-feature-vector).</span><span class="sxs-lookup"><span data-stu-id="513c0-258">That format is a [numeric vector](../resources/glossary.md#numerical-feature-vector).</span></span>

<span data-ttu-id="513c0-259">En los pasos siguientes se hace referencia a las columnas con los nombres definidos en la clase `GitHubIssue`.</span><span class="sxs-lookup"><span data-stu-id="513c0-259">In the next steps, we refer to the columns by the names defined in the `GitHubIssue` class.</span></span>

<span data-ttu-id="513c0-260">Si el modelo se ha entrenado y evaluado, de forma predeterminada, los valores de la columna **Label** se consideran valores correctos para predecir.</span><span class="sxs-lookup"><span data-stu-id="513c0-260">When the model is trained and evaluated, by default, the values in the **Label** column are considered as correct values to be predicted.</span></span> <span data-ttu-id="513c0-261">Para predecir la etiqueta de área de GitHub para `GitHubIssue`, debe copiar la columna `Area` en la columna **Etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="513c0-261">As we want to predict the Area GitHub label for a `GitHubIssue`, copy the `Area` column into the **Label** column.</span></span> <span data-ttu-id="513c0-262">Para ello, use `MLContext.Transforms.Conversion.MapValueToKey`, que es un contenedor para la clase de transformación <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="513c0-262">To do that, use the `MLContext.Transforms.Conversion.MapValueToKey`, which is a wrapper for the <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A> transformation class.</span></span>  <span data-ttu-id="513c0-263">`MapValueToKey` devuelve un elemento <xref:Microsoft.ML.Data.EstimatorChain%601> que será efectivamente una canalización.</span><span class="sxs-lookup"><span data-stu-id="513c0-263">The `MapValueToKey` returns an <xref:Microsoft.ML.Data.EstimatorChain%601> that will effectively be a pipeline.</span></span> <span data-ttu-id="513c0-264">Asigne un nombre a `pipeline`, ya que luego anexará el entrenador a `EstimatorChain`.</span><span class="sxs-lookup"><span data-stu-id="513c0-264">Name this `pipeline` as you will then append the trainer to the `EstimatorChain`.</span></span> <span data-ttu-id="513c0-265">Agregue esta línea de código:</span><span class="sxs-lookup"><span data-stu-id="513c0-265">Add the next line of code:</span></span>

[!code-csharp[MapValueToKey](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#MapValueToKey)]

 <span data-ttu-id="513c0-266">Con la caracterización, se asignan diferentes valores clave numéricos a distintos valores de cada una de las columnas. El algoritmo de aprendizaje automático aprovecha este proceso.</span><span class="sxs-lookup"><span data-stu-id="513c0-266">Featurizing assigns different numeric key values to the different values in each of the columns and is used by the machine learning algorithm.</span></span> <span data-ttu-id="513c0-267">A continuación, llame a `mlContext.Transforms.Text.FeaturizeText`, que caracteriza las columnas de texto (`Title` y `Description`) en un vector numérico para cada elemento `TitleFeaturized` y `DescriptionFeaturized` al que se llama.</span><span class="sxs-lookup"><span data-stu-id="513c0-267">Next, call `mlContext.Transforms.Text.FeaturizeText` which featurizes the text (`Title` and `Description`) columns into a numeric vector for each called `TitleFeaturized` and `DescriptionFeaturized`.</span></span> <span data-ttu-id="513c0-268">Anexe la caracterización para ambas columnas a la canalización usando el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="513c0-268">Append the featurization for both columns to the pipeline with the following code:</span></span>

[!code-csharp[FeaturizeText](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#FeaturizeText)]

<span data-ttu-id="513c0-269">En el último paso para la preparación de los datos, se combinan todas las columnas de característica en la columna **Características** mediante la clase de transformación `Concatenate`.</span><span class="sxs-lookup"><span data-stu-id="513c0-269">The last step in data preparation combines all of the feature columns into the **Features** column using the `Concatenate` transformation class.</span></span> <span data-ttu-id="513c0-270">De forma predeterminada, un algoritmo de aprendizaje solo procesa las características de la columna **Features**.</span><span class="sxs-lookup"><span data-stu-id="513c0-270">By default, a learning algorithm processes only features from the **Features** column.</span></span> <span data-ttu-id="513c0-271">Anexe esta transformación a la canalización usando el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="513c0-271">Append this transformation to the pipeline with the following code:</span></span>

[!code-csharp[Concatenate](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Concatenate)]

 <span data-ttu-id="513c0-272">A continuación, anexe <xref:Microsoft.ML.Data.EstimatorChain`1.AppendCacheCheckpoint%2A> para almacenar en caché el objeto DataView, de modo que pueda obtener un mayor rendimiento al iterar los datos varias veces con la caché, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="513c0-272">Next, append a <xref:Microsoft.ML.Data.EstimatorChain`1.AppendCacheCheckpoint%2A> to cache the DataView so when you iterate over the data multiple times using the cache might get better performance, as with the following code:</span></span>

[!code-csharp[AppendCache](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AppendCache)]

<span data-ttu-id="513c0-273">Devuelva la canalización al final del método `ProcessData`.</span><span class="sxs-lookup"><span data-stu-id="513c0-273">Return the pipeline at the end of the `ProcessData` method.</span></span>

[!code-csharp[ReturnPipeline](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnPipeline)]

<span data-ttu-id="513c0-274">En este paso se controla el preprocesamiento y la caracterización.</span><span class="sxs-lookup"><span data-stu-id="513c0-274">This step handles preprocessing/featurization.</span></span> <span data-ttu-id="513c0-275">El uso de componentes adicionales disponibles en ML.NET permite conseguir mejores resultados con el modelo.</span><span class="sxs-lookup"><span data-stu-id="513c0-275">Using additional components available in ML.NET can enable better results with your model.</span></span>

## <a name="build-and-train-the-model"></a><span data-ttu-id="513c0-276">Creación y entrenamiento del modelo</span><span class="sxs-lookup"><span data-stu-id="513c0-276">Build and train the model</span></span>

<span data-ttu-id="513c0-277">Agregue la siguiente llamada al método `BuildAndTrainModel` como siguiente línea de código del método `Main`:</span><span class="sxs-lookup"><span data-stu-id="513c0-277">Add the following call to the `BuildAndTrainModel`method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallBuildAndTrainModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallBuildAndTrainModel)]

<span data-ttu-id="513c0-278">El método `BuildAndTrainModel` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="513c0-278">The `BuildAndTrainModel` method executes the following tasks:</span></span>

* <span data-ttu-id="513c0-279">Crea la clase de algoritmo de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="513c0-279">Creates the training algorithm class.</span></span>
* <span data-ttu-id="513c0-280">Entrena el modelo.</span><span class="sxs-lookup"><span data-stu-id="513c0-280">Trains the model.</span></span>
* <span data-ttu-id="513c0-281">Predice el área según los datos de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="513c0-281">Predicts area based on training data.</span></span>
* <span data-ttu-id="513c0-282">Guarda el modelo en un archivo `.zip`.</span><span class="sxs-lookup"><span data-stu-id="513c0-282">Saves the model to a `.zip` file.</span></span>
* <span data-ttu-id="513c0-283">Devuelve el modelo.</span><span class="sxs-lookup"><span data-stu-id="513c0-283">Returns the model.</span></span>

<span data-ttu-id="513c0-284">Cree el método `BuildAndTrainModel`, justo después del método `Main`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="513c0-284">Create the `BuildAndTrainModel` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static EstimatorChain<KeyToValueMappingTransformer> BuildAndTrainModel(IDataView trainingDataView, EstimatorChain<ITransformer> pipeline)
{

}
```

<span data-ttu-id="513c0-285">Tenga en cuenta que se pasan dos parámetros al método BuildAndTrainModel; un elemento `IDataView` para el conjunto de datos de entrenamiento (`trainingDataView`) y un elemento <xref:Microsoft.ML.Data.EstimatorChain%601> para la canalización de procesamiento creada en ProcessData (`pipeline`).</span><span class="sxs-lookup"><span data-stu-id="513c0-285">Notice that two parameters are passed into the BuildAndTrainModel method; an `IDataView` for the training dataset (`trainingDataView`), and a <xref:Microsoft.ML.Data.EstimatorChain%601> for the processing pipeline created in ProcessData (`pipeline`).</span></span>

 <span data-ttu-id="513c0-286">Agregue el código siguiente a la primera línea del método `BuildAndTrainModel`:</span><span class="sxs-lookup"><span data-stu-id="513c0-286">Add the following code as the first line of the `BuildAndTrainModel` method:</span></span>

### <a name="choose-a-learning-algorithm"></a><span data-ttu-id="513c0-287">Elegir un algoritmo de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="513c0-287">Choose a learning algorithm</span></span>

<span data-ttu-id="513c0-288">Para agregar el algoritmo de aprendizaje, use el objeto <xref:Microsoft.ML.Trainers.SdcaMultiClassTrainer>.</span><span class="sxs-lookup"><span data-stu-id="513c0-288">To add the learning algorithm, use the <xref:Microsoft.ML.Trainers.SdcaMultiClassTrainer> object.</span></span>  <span data-ttu-id="513c0-289">`SdcaMultiClassTrainer` se anexa a `pipeline` y acepta los elementos `Title` y `Description` (`Features`) caracterizados y los parámetros de entrada de `Label` para aprender de los datos históricos.</span><span class="sxs-lookup"><span data-stu-id="513c0-289">The `SdcaMultiClassTrainer` is appended to the `pipeline` and accepts the featurized `Title` and `Description` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span>

<span data-ttu-id="513c0-290">Agregue el código siguiente al método `BuildAndTrainModel`:</span><span class="sxs-lookup"><span data-stu-id="513c0-290">Add the following code to the `BuildAndTrainModel` method:</span></span>

[!code-csharp[SdcaMultiClassTrainer](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#SdcaMultiClassTrainer)]

<span data-ttu-id="513c0-291">Ahora que ha creado un algoritmo de aprendizaje, anéxelo a `pipeline`.</span><span class="sxs-lookup"><span data-stu-id="513c0-291">Now that you've created a learning algorithm, append it to the `pipeline`.</span></span> <span data-ttu-id="513c0-292">También deberá asignar la etiqueta al valor para devolverlo a su estado de lectura original.</span><span class="sxs-lookup"><span data-stu-id="513c0-292">You also need to map the label to the value to return to its original readable state.</span></span> <span data-ttu-id="513c0-293">Realice una de estas acciones con el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="513c0-293">Do both of those actions with the following code:</span></span>

[!code-csharp[AddTrainer](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTrainer)]

### <a name="train-the-model"></a><span data-ttu-id="513c0-294">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="513c0-294">Train the model</span></span>

<span data-ttu-id="513c0-295">Se entrena el modelo, <xref:Microsoft.ML.Data.TransformerChain%601>, en función del conjunto de datos que se haya cargado y transformado.</span><span class="sxs-lookup"><span data-stu-id="513c0-295">You train the model, <xref:Microsoft.ML.Data.TransformerChain%601>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="513c0-296">Una vez que se ha definido el estimador, entrenará el modelo mediante <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> proporcionando al mismo tiempo los datos de entrenamiento ya cargados.</span><span class="sxs-lookup"><span data-stu-id="513c0-296">Once the estimator has been defined, you train your model using the <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> while providing the already loaded training data.</span></span> <span data-ttu-id="513c0-297">Este método devuelve un modelo que se usa para las predicciones.</span><span class="sxs-lookup"><span data-stu-id="513c0-297">This  method returns a model to use for predictions.</span></span> <span data-ttu-id="513c0-298">`trainingPipeline.Fit()` entrena la canalización y devuelve `Transformer` según la `DataView` que se pasa.</span><span class="sxs-lookup"><span data-stu-id="513c0-298">`trainingPipeline.Fit()` trains the pipeline and returns a `Transformer` based on the `DataView` passed in.</span></span> <span data-ttu-id="513c0-299">El experimento no se ejecuta hasta que se ejecute el método `.Fit()`.</span><span class="sxs-lookup"><span data-stu-id="513c0-299">The experiment is not executed until the `.Fit()` method runs.</span></span>

<span data-ttu-id="513c0-300">Agregue el código siguiente al método `BuildAndTrainModel`:</span><span class="sxs-lookup"><span data-stu-id="513c0-300">Add the following code to the `BuildAndTrainModel` method:</span></span>

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#TrainModel)]

<span data-ttu-id="513c0-301">Aunque `model` es un elemento `transformer` que opera en muchas filas de datos, la necesidad de predicciones sobre ejemplos individuales es un escenario de producción muy común.</span><span class="sxs-lookup"><span data-stu-id="513c0-301">While the `model` is a `transformer` that operates on many rows of data, a need for predictions on individual examples is a common production scenario.</span></span> <span data-ttu-id="513c0-302"><xref:Microsoft.ML.PredictionEngine%602> es un contenedor que se devuelve del método `CreatePredictionEngine`.</span><span class="sxs-lookup"><span data-stu-id="513c0-302">The <xref:Microsoft.ML.PredictionEngine%602> is a wrapper that is returned from the `CreatePredictionEngine` method.</span></span> <span data-ttu-id="513c0-303">Vamos a agregar el código siguiente para crear `PredictionEngine` como la línea siguiente en el método `BuildAndTrainModel`:</span><span class="sxs-lookup"><span data-stu-id="513c0-303">Let's add the following code to create the `PredictionEngine` as the next line in the `BuildAndTrainModel` Method:</span></span>

[!code-csharp[CreatePredictionEngine1](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine1)]

<span data-ttu-id="513c0-304">Agregue un problema de GitHub para probar la predicción del modelo entrenado en el método `Predict` mediante la creación de una instancia de `GitHubIssue`:</span><span class="sxs-lookup"><span data-stu-id="513c0-304">Add a GitHub issue to test the trained model's prediction in the `Predict` method by creating an instance of `GitHubIssue`:</span></span>

[!code-csharp[CreateTestIssue1](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateTestIssue1)]

<span data-ttu-id="513c0-305">Puede usarlo para predecir la etiqueta `Area` de una instancia única de los datos del problema.</span><span class="sxs-lookup"><span data-stu-id="513c0-305">You can use that to predict the `Area` label of a single instance of the issue data.</span></span> <span data-ttu-id="513c0-306">Para obtener una predicción, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> en los datos.</span><span class="sxs-lookup"><span data-stu-id="513c0-306">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="513c0-307">Los datos de entrada son una cadena y el modelo incluye la caracterización.</span><span class="sxs-lookup"><span data-stu-id="513c0-307">The input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="513c0-308">La canalización está sincronizada durante el entrenamiento y la predicción.</span><span class="sxs-lookup"><span data-stu-id="513c0-308">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="513c0-309">No fue necesario escribir el código de preprocesamiento o caracterización específicamente para las predicciones, y la misma API se encarga de las predicciones por lotes y puntuales.</span><span class="sxs-lookup"><span data-stu-id="513c0-309">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Predict)]

### <a name="using-the-model-prediction"></a><span data-ttu-id="513c0-310">Uso del modelo: predicción</span><span class="sxs-lookup"><span data-stu-id="513c0-310">Using the model: prediction</span></span>

<span data-ttu-id="513c0-311">Muestre `GitHubIssue` y la predicción de la etiqueta `Area` correspondiente para compartir los resultados y actuar en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="513c0-311">Display `GitHubIssue` and corresponding `Area` label prediction in order to share the results and act on them accordingly.</span></span>  <span data-ttu-id="513c0-312">Cree una visualización para los resultados mediante el código <xref:System.Console.WriteLine?displayProperty=nameWithType> siguiente:</span><span class="sxs-lookup"><span data-stu-id="513c0-312">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputPrediction](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#OutputPrediction)]

### <a name="return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="513c0-313">Devolución del modelo entrenado para su uso para la evaluación</span><span class="sxs-lookup"><span data-stu-id="513c0-313">Return the model trained to use for evaluation</span></span>

<span data-ttu-id="513c0-314">Devuelva el modelo al final del método `BuildAndTrainModel`.</span><span class="sxs-lookup"><span data-stu-id="513c0-314">Return the model at the end of the `BuildAndTrainModel` method.</span></span>

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnModel)]

## <a name="evaluate-the-model"></a><span data-ttu-id="513c0-315">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="513c0-315">Evaluate the model</span></span>

<span data-ttu-id="513c0-316">Ahora que ha creado y entrenado el modelo, debe evaluarlo con otro conjunto de datos para el control de calidad y la validación.</span><span class="sxs-lookup"><span data-stu-id="513c0-316">Now that you've created and trained the model, you need to evaluate it with a different dataset for quality assurance and validation.</span></span> <span data-ttu-id="513c0-317">En el método `Evaluate`, el modelo creado en `BuildAndTrainModel` se pasa para ser evaluado.</span><span class="sxs-lookup"><span data-stu-id="513c0-317">In the `Evaluate` method, the model created in `BuildAndTrainModel` is passed in to be evaluated.</span></span> <span data-ttu-id="513c0-318">Cree el método `Evaluate`, justo después de `BuildAndTrainModel`, como en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="513c0-318">Create the `Evaluate` method, just after `BuildAndTrainModel`, as in the following code:</span></span>

```csharp
public static void Evaluate()
{

}
```

<span data-ttu-id="513c0-319">El método `Evaluate` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="513c0-319">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="513c0-320">Carga el conjunto de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="513c0-320">Loads the test dataset.</span></span>
* <span data-ttu-id="513c0-321">Crea el evaluador multiclase.</span><span class="sxs-lookup"><span data-stu-id="513c0-321">Creates the multiclass evaluator.</span></span>
* <span data-ttu-id="513c0-322">Evalúa el modelo y crea métricas.</span><span class="sxs-lookup"><span data-stu-id="513c0-322">Evaluates the model and create metrics.</span></span>
* <span data-ttu-id="513c0-323">Muestra las métricas.</span><span class="sxs-lookup"><span data-stu-id="513c0-323">Displays the metrics.</span></span>

<span data-ttu-id="513c0-324">Agregue una llamada al método nuevo desde el método `Main`, justo debajo de la llamada al método `BuildAndTrainModel`, utilizando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="513c0-324">Add a call to the new method from the `Main` method, right under the `BuildAndTrainModel` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallEvaluate)]

<span data-ttu-id="513c0-325">Como hizo anteriormente con el conjunto de datos de entrenamiento, puede combinar la inicialización, la asignación y la carga del conjunto de datos de prueba en una línea de código.</span><span class="sxs-lookup"><span data-stu-id="513c0-325">As you did previously with the training dataset, you can combine the initialization, mapping, and test dataset loading into one line of code.</span></span> <span data-ttu-id="513c0-326">Puede evaluar el modelo utilizando este conjunto de datos como una comprobación de calidad.</span><span class="sxs-lookup"><span data-stu-id="513c0-326">You can evaluate the model using this dataset as a quality check.</span></span> <span data-ttu-id="513c0-327">Agregue el código siguiente al método `Evaluate`:</span><span class="sxs-lookup"><span data-stu-id="513c0-327">Add the following code to the `Evaluate` method:</span></span>

[!code-csharp[LoadTestDataset](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTestDataset)]

<span data-ttu-id="513c0-328">`MulticlassClassificationContext.Evaluate` es un contenedor para el método <xref:Microsoft.ML.MulticlassClassificationContext.Evaluate%2A> que calcula las métricas de calidad del modelo que usa el conjunto de datos especificado.</span><span class="sxs-lookup"><span data-stu-id="513c0-328">The `MulticlassClassificationContext.Evaluate` is a wrapper for the <xref:Microsoft.ML.MulticlassClassificationContext.Evaluate%2A> method that computes the quality metrics for the model using the specified dataset.</span></span> <span data-ttu-id="513c0-329">Devuelve un objeto <xref:Microsoft.ML.Data.MultiClassClassifierMetrics> que contiene las métricas totales calculadas por evaluadores de clasificación multiclase.</span><span class="sxs-lookup"><span data-stu-id="513c0-329">It returns a <xref:Microsoft.ML.Data.MultiClassClassifierMetrics> object that contains the overall metrics computed by multiclass classification evaluators.</span></span>
<span data-ttu-id="513c0-330">Para mostrar las métricas a fin de determinar la calidad del modelo, primero tendrá que obtenerlas.</span><span class="sxs-lookup"><span data-stu-id="513c0-330">To display the metrics to determine the quality of the model, you need to get them first.</span></span>
<span data-ttu-id="513c0-331">Tenga en cuenta el uso del método `Transform` de la variable global de aprendizaje automático `_trainedModel` (un transformador) para especificar características y devolver predicciones.</span><span class="sxs-lookup"><span data-stu-id="513c0-331">Notice the use of the `Transform` method of the machine learning `_trainedModel` global variable (a transformer) to input the features and return predictions.</span></span> <span data-ttu-id="513c0-332">Agregue el código siguiente al método `Evaluate` como la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="513c0-332">Add the following code to the `Evaluate` method as the next line:</span></span>

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Evaluate)]

<span data-ttu-id="513c0-333">Las siguientes métricas se evalúan para la clasificación multiclase:</span><span class="sxs-lookup"><span data-stu-id="513c0-333">The following metrics are evaluated for multiclass classification:</span></span>

* <span data-ttu-id="513c0-334">Microprecisión: todos los pares de ejemplo y clase contribuyen del mismo modo a la métrica de precisión.</span><span class="sxs-lookup"><span data-stu-id="513c0-334">Micro Accuracy - Every sample-class pair contributes equally to the accuracy metric.</span></span>  <span data-ttu-id="513c0-335">Le recomendamos que la microprecisión esté lo más cerca posible de 1.</span><span class="sxs-lookup"><span data-stu-id="513c0-335">You want Micro Accuracy to be as close to 1 as possible.</span></span>

* <span data-ttu-id="513c0-336">Macroprecisión: todas las clases contribuyen del mismo modo a la métrica de precisión.</span><span class="sxs-lookup"><span data-stu-id="513c0-336">Macro Accuracy - Every class contributes equally to the accuracy metric.</span></span> <span data-ttu-id="513c0-337">Las clases minoritarias tienen el mismo peso que las clases más grandes.</span><span class="sxs-lookup"><span data-stu-id="513c0-337">Minority classes are given equal weight as the larger classes.</span></span> <span data-ttu-id="513c0-338">Le recomendamos que la macroprecisión esté lo más cerca posible de 1.</span><span class="sxs-lookup"><span data-stu-id="513c0-338">You want Macro Accuracy to be as close to 1 as possible.</span></span>

* <span data-ttu-id="513c0-339">Pérdida de registro: vea [Pérdida de registro](../resources/glossary.md#log-loss).</span><span class="sxs-lookup"><span data-stu-id="513c0-339">Log-loss - see [Log Loss](../resources/glossary.md#log-loss).</span></span> <span data-ttu-id="513c0-340">Le recomendamos que la pérdida logarítmica esté lo más cerca posible de 0.</span><span class="sxs-lookup"><span data-stu-id="513c0-340">You want Log-loss to be as close to zero as possible.</span></span>

* <span data-ttu-id="513c0-341">Reducción de la pérdida de registro: parte de [-inf, 100], donde 100 equivale a una predicción perfecta, y 0 indica una predicción aproximada.</span><span class="sxs-lookup"><span data-stu-id="513c0-341">Log-loss reduction - Ranges from [-inf, 100], where 100 is perfect predictions and 0 indicates mean predictions.</span></span> <span data-ttu-id="513c0-342">Le recomendamos que la reducción de la pérdida de registro esté lo más cerca posible de 0.</span><span class="sxs-lookup"><span data-stu-id="513c0-342">You want Log-loss reduction to be as close to zero as possible.</span></span>

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="513c0-343">Mostrar las métricas para la validación del modelo</span><span class="sxs-lookup"><span data-stu-id="513c0-343">Displaying the metrics for model validation</span></span>

<span data-ttu-id="513c0-344">Utilice el código siguiente para mostrar las métricas, compartir los resultados y, a continuación, trabajar con ellos:</span><span class="sxs-lookup"><span data-stu-id="513c0-344">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayMetrics)]

### <a name="save-the-trained-and-evaluated-model"></a><span data-ttu-id="513c0-345">Guardar el modelo entrenado y evaluado</span><span class="sxs-lookup"><span data-stu-id="513c0-345">Save the trained and evaluated model</span></span>

<span data-ttu-id="513c0-346">En este punto, tiene un modelo de tipo <xref:Microsoft.ML.Data.TransformerChain%601> que se puede integrar en cualquiera de las aplicaciones de .NET nuevas o existentes.</span><span class="sxs-lookup"><span data-stu-id="513c0-346">At this point, you have a model of type <xref:Microsoft.ML.Data.TransformerChain%601> that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="513c0-347">Para guardar el modelo entrenado en un archivo .zip, agregue el siguiente código para llamar al método `SaveModelAsFile` como la línea siguiente en `BuildAndTrainModel`:</span><span class="sxs-lookup"><span data-stu-id="513c0-347">To save your trained model to a .zip file, add the following code to call the `SaveModelAsFile` method as the next line in `BuildAndTrainModel`:</span></span>

[!code-csharp[CallSaveModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallSaveModel)]

## <a name="save-the-model-as-a-zip-file"></a><span data-ttu-id="513c0-348">Almacenamiento del modelo como un archivo ZIP</span><span class="sxs-lookup"><span data-stu-id="513c0-348">Save the model as a .zip file</span></span>

<span data-ttu-id="513c0-349">Cree el método `SaveModelAsFile`, justo después del método `Evaluate`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="513c0-349">Create the `SaveModelAsFile` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="513c0-350">El método `SaveModelAsFile` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="513c0-350">The `SaveModelAsFile` method executes the following tasks:</span></span>

* <span data-ttu-id="513c0-351">Guarda el modelo como un archivo .zip.</span><span class="sxs-lookup"><span data-stu-id="513c0-351">Saves the model as a .zip file.</span></span>

<span data-ttu-id="513c0-352">A continuación, cree un método para guardar el modelo para que se pueda volver a usar y consumir en otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="513c0-352">Next, create a method to save the model so that it can be reused and consumed in other applications.</span></span> <span data-ttu-id="513c0-353">`ITransformer` tiene un método <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> que toma el campo global `_modelPath` y <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="513c0-353">The `ITransformer` has a <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> method that takes in the `_modelPath` global field, and a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="513c0-354">Para guardar el modelo como un archivo ZIP, creará `FileStream` inmediatamente antes de llamar al método `SaveTo`.</span><span class="sxs-lookup"><span data-stu-id="513c0-354">To save the model as a zip file, you'll create the `FileStream` immediately before calling the `SaveTo` method.</span></span> <span data-ttu-id="513c0-355">Agregue el código siguiente al método `SaveModelAsFile` como la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="513c0-355">Add the following code to the `SaveModelAsFile` method as the next line:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#SaveModel)]

<span data-ttu-id="513c0-356">También podría mostrar dónde se escribió el archivo mediante la escritura de un mensaje de consola con `_modelPath`, utilizando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="513c0-356">You could also display where the file was written by writing a console message with the `_modelPath`, using the following code:</span></span>

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="predict-the-test-data-outcome-with-the-saved-model"></a><span data-ttu-id="513c0-357">Predicción de los resultados de datos de prueba con el modelo guardado</span><span class="sxs-lookup"><span data-stu-id="513c0-357">Predict the test data outcome with the saved model</span></span>

<span data-ttu-id="513c0-358">Agregue una llamada al método nuevo desde el método `Main`, justo debajo de la llamada al método `Evaluate`, utilizando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="513c0-358">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallPredictIssue](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallPredictIssue)]

<span data-ttu-id="513c0-359">Cree el método `PredictIssue`, justo después del método `Evaluate` (y justo antes del método `SaveModelAsFile`) con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="513c0-359">Create the `PredictIssue` method, just after the `Evaluate` method (and just before the `SaveModelAsFile` method), using the following code:</span></span>

```csharp
private static void PredictIssue()
{

}
```

<span data-ttu-id="513c0-360">El método `PredictIssue` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="513c0-360">The `PredictIssue` method executes the following tasks:</span></span>

* <span data-ttu-id="513c0-361">Crea un único problema de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="513c0-361">Creates a single issue of test data.</span></span>
* <span data-ttu-id="513c0-362">Predice el área según los datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="513c0-362">Predicts Area based on test data.</span></span>
* <span data-ttu-id="513c0-363">Combina datos de prueba y predicciones para la generación de informes.</span><span class="sxs-lookup"><span data-stu-id="513c0-363">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="513c0-364">Muestra los resultados de la predicción.</span><span class="sxs-lookup"><span data-stu-id="513c0-364">Displays the predicted results.</span></span>

<span data-ttu-id="513c0-365">En primer lugar, cargue el modelo que ha guardado anteriormente con el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="513c0-365">First, load the model that you saved previously with the following code:</span></span>

[!code-csharp[LoadModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadModel)]

<span data-ttu-id="513c0-366">Agregue un problema de GitHub para probar la predicción del modelo entrenado en el método `Predict` mediante la creación de una instancia de `GitHubIssue`:</span><span class="sxs-lookup"><span data-stu-id="513c0-366">Add a GitHub issue to test the trained model's prediction in the `Predict` method by creating an instance of `GitHubIssue`:</span></span>

[!code-csharp[AddTestIssue](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTestIssue)]

[!code-csharp[CreatePredictionEngine](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine)]
  
<span data-ttu-id="513c0-367">Ahora que tiene un modelo, puede usarlo para predecir la etiqueta Área de GitHub de una única instancia de los datos del problema de GitHub.</span><span class="sxs-lookup"><span data-stu-id="513c0-367">Now that you have a model, you can use that to predict the Area GitHub label of a single instance of the GitHub issue data.</span></span> <span data-ttu-id="513c0-368">Para obtener una predicción, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> en los datos.</span><span class="sxs-lookup"><span data-stu-id="513c0-368">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="513c0-369">Los datos de entrada son una cadena y el modelo incluye la caracterización.</span><span class="sxs-lookup"><span data-stu-id="513c0-369">The input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="513c0-370">La canalización está sincronizada durante el entrenamiento y la predicción.</span><span class="sxs-lookup"><span data-stu-id="513c0-370">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="513c0-371">No fue necesario escribir el código de preprocesamiento o caracterización específicamente para las predicciones, y la misma API se encarga de las predicciones por lotes y puntuales.</span><span class="sxs-lookup"><span data-stu-id="513c0-371">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span> <span data-ttu-id="513c0-372">Agregue el código siguiente al método `PredictIssue` para las predicciones:</span><span class="sxs-lookup"><span data-stu-id="513c0-372">Add the following code to the `PredictIssue` method for the predictions:</span></span>

[!code-csharp[PredictIssue](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#PredictIssue)]

### <a name="using-the-loaded-model-for-prediction"></a><span data-ttu-id="513c0-373">Uso del modelo cargado para la predicción</span><span class="sxs-lookup"><span data-stu-id="513c0-373">Using the loaded model for prediction</span></span>

<span data-ttu-id="513c0-374">Muestre `Area` para poder categorizar el problema y actuar en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="513c0-374">Display `Area` in order to categorize the issue and act on it accordingly.</span></span> <span data-ttu-id="513c0-375">Cree una visualización para los resultados mediante el código <xref:System.Console.WriteLine?displayProperty=nameWithType> siguiente:</span><span class="sxs-lookup"><span data-stu-id="513c0-375">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[DisplayResults](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayResults)]

## <a name="results"></a><span data-ttu-id="513c0-376">Resultados</span><span class="sxs-lookup"><span data-stu-id="513c0-376">Results</span></span>

<span data-ttu-id="513c0-377">Los resultados deberían ser similares a los indicados a continuación.</span><span class="sxs-lookup"><span data-stu-id="513c0-377">Your results should be similar to the following.</span></span> <span data-ttu-id="513c0-378">A medida que la canalización procesa, muestra mensajes.</span><span class="sxs-lookup"><span data-stu-id="513c0-378">As the pipeline processes, it displays messages.</span></span> <span data-ttu-id="513c0-379">Puede ver las advertencias o mensajes de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="513c0-379">You may see warnings, or processing messages.</span></span> <span data-ttu-id="513c0-380">Estos mensajes se han quitado de los resultados siguientes para mayor claridad.</span><span class="sxs-lookup"><span data-stu-id="513c0-380">These messages have been removed from the following results for clarity.</span></span>

```console
=============== Single Prediction just-trained-model - Result: area-System.Net ===============
The model is saved to C:\Users\johalex\dotnet-samples\samples\machine-learning\tutorials\GitHubIssueClassification\bin\Debug\netcoreapp2.0\..\..\..\Models\model.zip
*************************************************************************************************************
*       Metrics for Multi-class Classification model - Test Data
*------------------------------------------------------------------------------------------------------------
*       MicroAccuracy:    0.74
*       MacroAccuracy:    0.687
*       LogLoss:          .932
*       LogLossReduction: 63.852
*************************************************************************************************************
=============== Single Prediction - Result: area-System.Data ===============
```

<span data-ttu-id="513c0-381">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="513c0-381">Congratulations!</span></span> <span data-ttu-id="513c0-382">Ya ha creado correctamente un modelo de aprendizaje automático para clasificar y predecir una etiqueta Área de un problema de GitHub.</span><span class="sxs-lookup"><span data-stu-id="513c0-382">You've now successfully built a machine learning model for classifying and predicting an Area label for a GitHub issue.</span></span> <span data-ttu-id="513c0-383">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification).</span><span class="sxs-lookup"><span data-stu-id="513c0-383">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="513c0-384">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="513c0-384">Next steps</span></span>

<span data-ttu-id="513c0-385">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="513c0-385">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="513c0-386">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="513c0-386">Understand the problem</span></span>
> * <span data-ttu-id="513c0-387">Seleccionar el algoritmo de aprendizaje automático adecuado</span><span class="sxs-lookup"><span data-stu-id="513c0-387">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="513c0-388">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="513c0-388">Prepare your data</span></span>
> * <span data-ttu-id="513c0-389">Extraer características y transformar los datos</span><span class="sxs-lookup"><span data-stu-id="513c0-389">Extract Features and transform the data</span></span>
> * <span data-ttu-id="513c0-390">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="513c0-390">Train the model</span></span>
> * <span data-ttu-id="513c0-391">Evaluar el modelo con otro conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="513c0-391">Evaluate the model with a different dataset</span></span>
> * <span data-ttu-id="513c0-392">Predecir una única instancia del resultado de datos de prueba con el modelo entrenado</span><span class="sxs-lookup"><span data-stu-id="513c0-392">Predict a single instance of test data outcome with the trained model</span></span>
> * <span data-ttu-id="513c0-393">Predecir una única instancia de datos de prueba con un modelo cargado</span><span class="sxs-lookup"><span data-stu-id="513c0-393">Predict a single instance of test data with a loaded model</span></span>

<span data-ttu-id="513c0-394">Siga con el siguiente tutorial para obtener más información</span><span class="sxs-lookup"><span data-stu-id="513c0-394">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="513c0-395">Predictor de tarifa de taxi</span><span class="sxs-lookup"><span data-stu-id="513c0-395">Taxi Fare Predictor</span></span>](taxi-fare.md)
