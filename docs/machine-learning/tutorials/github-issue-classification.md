---
title: Uso de ML.NET en un escenario de clasificación de problemas multiclase de GitHub
description: Descubra cómo usar ML.NET en un escenario de clasificación multiclase para clasificar los problemas de GitHub y asignarlos a un área determinada.
ms.date: 02/14/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 80f4e322ee94e9c3a41bd1c3945383f89f4347d0
ms.sourcegitcommit: 0069cb3de8eed4e92b2195d29e5769a76111acdd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2019
ms.locfileid: "56333526"
---
# <a name="tutorial-use-mlnet-in-a-multiclass-classification-scenario-to-classify-github-issues"></a><span data-ttu-id="5af49-103">Tutorial: Uso de ML.NET en un escenario de clasificación multiclase para clasificar problemas de GitHub</span><span class="sxs-lookup"><span data-stu-id="5af49-103">Tutorial: Use ML.NET in a multiclass classification scenario to classify GitHub issues</span></span>

<span data-ttu-id="5af49-104">En este tutorial de ejemplo se muestra cómo utilizar ML.NET para crear un clasificador de problemas de GitHub a través de una aplicación de consola de .NET Core con C# en Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="5af49-104">This sample tutorial illustrates using ML.NET to create a GitHub issue classifier via a .NET Core console application using C# in Visual Studio 2017.</span></span>

<span data-ttu-id="5af49-105">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="5af49-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="5af49-106">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="5af49-106">Understand the problem</span></span>
> * <span data-ttu-id="5af49-107">Seleccionar el algoritmo de aprendizaje automático adecuado</span><span class="sxs-lookup"><span data-stu-id="5af49-107">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="5af49-108">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="5af49-108">Prepare your data</span></span>
> * <span data-ttu-id="5af49-109">Transformar los datos</span><span class="sxs-lookup"><span data-stu-id="5af49-109">Transform the data</span></span>
> * <span data-ttu-id="5af49-110">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="5af49-110">Train the model</span></span>
> * <span data-ttu-id="5af49-111">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="5af49-111">Evaluate the model</span></span>
> * <span data-ttu-id="5af49-112">Predecir con el modelo entrenado</span><span class="sxs-lookup"><span data-stu-id="5af49-112">Predict with the trained model</span></span>
> * <span data-ttu-id="5af49-113">Implementar y predecir con un modelo cargado</span><span class="sxs-lookup"><span data-stu-id="5af49-113">Deploy and Predict with a loaded model</span></span>

> [!NOTE]
> <span data-ttu-id="5af49-114">Este tema hace referencia a ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios.</span><span class="sxs-lookup"><span data-stu-id="5af49-114">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="5af49-115">Para obtener más información, visite [la introducción de ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="5af49-115">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

## <a name="github-issue-sample-overview"></a><span data-ttu-id="5af49-116">Información general sobre el ejemplo de problema de GitHub</span><span class="sxs-lookup"><span data-stu-id="5af49-116">GitHub issue sample overview</span></span>

<span data-ttu-id="5af49-117">El ejemplo es una aplicación de consola que utiliza ML.NET para entrenar un modelo que clasifica y predice el área de etiqueta de un problema de GitHub.</span><span class="sxs-lookup"><span data-stu-id="5af49-117">The sample is a console app that uses ML.NET to train a model that classifies and predicts the Area label for a GitHub issue.</span></span> <span data-ttu-id="5af49-118">También se evalúa el modelo con un segundo conjunto de datos para realizar el análisis de calidad.</span><span class="sxs-lookup"><span data-stu-id="5af49-118">It also evaluates the model with a second dataset for quality analysis.</span></span> <span data-ttu-id="5af49-119">Los conjuntos de datos del problema proceden del repositorio de GitHub dotnet/corefx.</span><span class="sxs-lookup"><span data-stu-id="5af49-119">The issue datasets are from the dotnet/corefx GitHub repo.</span></span>

<span data-ttu-id="5af49-120">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification).</span><span class="sxs-lookup"><span data-stu-id="5af49-120">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5af49-121">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5af49-121">Prerequisites</span></span>

* <span data-ttu-id="5af49-122">[Visual Studio 2017 15.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.</span><span class="sxs-lookup"><span data-stu-id="5af49-122">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* <span data-ttu-id="5af49-123">[Archivo de problemas de GitHub delimitado por pestañas (issues_train.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv).</span><span class="sxs-lookup"><span data-stu-id="5af49-123">The [Github issues tab separated file (issues_train.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv).</span></span>
* <span data-ttu-id="5af49-124">[Prueba de problemas de GitHub delimitado por pestañas (issues_test.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv).</span><span class="sxs-lookup"><span data-stu-id="5af49-124">The [Github issues test tab separated file (issues_test.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv).</span></span>

## <a name="machine-learning-workflow"></a><span data-ttu-id="5af49-125">Flujo de trabajo del aprendizaje automático</span><span class="sxs-lookup"><span data-stu-id="5af49-125">Machine learning workflow</span></span>

<span data-ttu-id="5af49-126">En este tutorial se sigue un flujo de trabajo de aprendizaje automático que permite que el proceso avance de manera ordenada.</span><span class="sxs-lookup"><span data-stu-id="5af49-126">This tutorial follows a machine learning workflow that enables the process to move in an orderly fashion.</span></span>

<span data-ttu-id="5af49-127">Las fases del flujo de trabajo son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="5af49-127">The workflow phases are as follows:</span></span>

1. <span data-ttu-id="5af49-128">**Entender el problema**</span><span class="sxs-lookup"><span data-stu-id="5af49-128">**Understand the problem**</span></span>
2. <span data-ttu-id="5af49-129">**Preparar los datos**</span><span class="sxs-lookup"><span data-stu-id="5af49-129">**Prepare your data**</span></span>
   * <span data-ttu-id="5af49-130">**Cargar los datos**</span><span class="sxs-lookup"><span data-stu-id="5af49-130">**Load the data**</span></span>
   * <span data-ttu-id="5af49-131">**Extraer características (transformar los datos)**</span><span class="sxs-lookup"><span data-stu-id="5af49-131">**Extract features (Transform your data)**</span></span>
3. <span data-ttu-id="5af49-132">**Compilar y entrenar**</span><span class="sxs-lookup"><span data-stu-id="5af49-132">**Build and train**</span></span> 
   * <span data-ttu-id="5af49-133">**Entrenar el modelo**</span><span class="sxs-lookup"><span data-stu-id="5af49-133">**Train the model**</span></span>
   * <span data-ttu-id="5af49-134">**Evaluar el modelo**</span><span class="sxs-lookup"><span data-stu-id="5af49-134">**Evaluate the model**</span></span>
4. <span data-ttu-id="5af49-135">**Implementar el modelo**</span><span class="sxs-lookup"><span data-stu-id="5af49-135">**Deploy Model**</span></span>
   * <span data-ttu-id="5af49-136">**Usar el modelo para la predicción**</span><span class="sxs-lookup"><span data-stu-id="5af49-136">**Use the Model to predict**</span></span>

### <a name="understand-the-problem"></a><span data-ttu-id="5af49-137">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="5af49-137">Understand the problem</span></span>

<span data-ttu-id="5af49-138">Primero debe entender el problema, de manera que pueda dividirlo en partes que admitan la compilación y el entrenamiento del problema.</span><span class="sxs-lookup"><span data-stu-id="5af49-138">You first need to understand the problem, so you can break it down to parts that can support building and training the model.</span></span> <span data-ttu-id="5af49-139">Desglosar el problema en partes le permite predecir y evaluar los resultados.</span><span class="sxs-lookup"><span data-stu-id="5af49-139">Breaking  down the problem allows you to predict and evaluate the results.</span></span>

<span data-ttu-id="5af49-140">El problema de este tutorial es comprender a qué área pertenecen los problemas de GitHub entrantes, de modo que se puedan etiquetar correctamente para priorizarlos y programarlos.</span><span class="sxs-lookup"><span data-stu-id="5af49-140">The problem for this tutorial is to understand what area incoming GitHub issues belong to in order to label them correctly for prioritization and scheduling.</span></span>

<span data-ttu-id="5af49-141">Puede desglosar el problema en los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="5af49-141">You can break down the problem to the following parts:</span></span>

* <span data-ttu-id="5af49-142">texto del título del problema</span><span class="sxs-lookup"><span data-stu-id="5af49-142">the issue title text</span></span>
* <span data-ttu-id="5af49-143">texto de la descripción del problema</span><span class="sxs-lookup"><span data-stu-id="5af49-143">the issue description text</span></span>
* <span data-ttu-id="5af49-144">valor de área para los datos de entrenamiento del modelo</span><span class="sxs-lookup"><span data-stu-id="5af49-144">an area value for the model training data</span></span>
* <span data-ttu-id="5af49-145">valor de predicción del área que se puede evaluar y usar de forma operativa</span><span class="sxs-lookup"><span data-stu-id="5af49-145">a predicted area value that you can evaluate and then use operationally</span></span>

<span data-ttu-id="5af49-146">Después, deberá **determinar** el área, lo que lo ayudará con la selección de tareas de aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="5af49-146">You then need to **determine** the area, which helps you with the machine learning task selection.</span></span>

## <a name="select-the-appropriate-machine-learning-algorithm"></a><span data-ttu-id="5af49-147">Seleccionar el algoritmo de aprendizaje automático adecuado</span><span class="sxs-lookup"><span data-stu-id="5af49-147">Select the appropriate machine learning algorithm</span></span>

<span data-ttu-id="5af49-148">Con este problema, tiene constancia de los siguientes hechos:</span><span class="sxs-lookup"><span data-stu-id="5af49-148">With this problem, you know the following facts:</span></span>

<span data-ttu-id="5af49-149">Datos de entrenamiento:</span><span class="sxs-lookup"><span data-stu-id="5af49-149">Training data:</span></span>

<span data-ttu-id="5af49-150">Los problemas de GitHub se pueden etiquetar en varias áreas (**Área**), tal como se muestra en los siguientes ejemplos:</span><span class="sxs-lookup"><span data-stu-id="5af49-150">GitHub issues can be labeled in several areas (**Area**) as in the following examples:</span></span>

* <span data-ttu-id="5af49-151">area-System.Numerics</span><span class="sxs-lookup"><span data-stu-id="5af49-151">area-System.Numerics</span></span>
* <span data-ttu-id="5af49-152">area-System.Xml</span><span class="sxs-lookup"><span data-stu-id="5af49-152">area-System.Xml</span></span>
* <span data-ttu-id="5af49-153">area-Infrastructure</span><span class="sxs-lookup"><span data-stu-id="5af49-153">area-Infrastructure</span></span>
* <span data-ttu-id="5af49-154">area-System.Linq</span><span class="sxs-lookup"><span data-stu-id="5af49-154">area-System.Linq</span></span>
* <span data-ttu-id="5af49-155">area-System.IO</span><span class="sxs-lookup"><span data-stu-id="5af49-155">area-System.IO</span></span>

<span data-ttu-id="5af49-156">Prediga el **área** de un nuevo problema de GitHub, como en los siguientes ejemplos:</span><span class="sxs-lookup"><span data-stu-id="5af49-156">Predict the **Area** of a new GitHub Issue such as in the following examples:</span></span>

* <span data-ttu-id="5af49-157">Contract.Assert en comparación con Debug.Assert</span><span class="sxs-lookup"><span data-stu-id="5af49-157">Contract.Assert vs Debug.Assert</span></span>
* <span data-ttu-id="5af49-158">Establecimiento de los campos como de solo lectura en System.Xml</span><span class="sxs-lookup"><span data-stu-id="5af49-158">Make fields readonly in System.Xml</span></span>

<span data-ttu-id="5af49-159">El algoritmo de aprendizaje automático de clasificación es ideal para este escenario.</span><span class="sxs-lookup"><span data-stu-id="5af49-159">The classification machine learning algorithm is best suited for this scenario.</span></span>

### <a name="about-the-classification-learning-algorithm"></a><span data-ttu-id="5af49-160">Acerca del algoritmo de aprendizaje de clasificación</span><span class="sxs-lookup"><span data-stu-id="5af49-160">About the classification learning algorithm</span></span>

<span data-ttu-id="5af49-161">La clasificación es un algoritmo de aprendizaje automático que usa datos para **determinar** la categoría, el tipo o la clase de un elemento o fila de datos.</span><span class="sxs-lookup"><span data-stu-id="5af49-161">Classification is a machine learning algorithm that uses data to **determine** the category, type, or class of an item or row of data.</span></span> <span data-ttu-id="5af49-162">Por ejemplo, puede utilizar la clasificación para:</span><span class="sxs-lookup"><span data-stu-id="5af49-162">For example, you can use classification to:</span></span>

* <span data-ttu-id="5af49-163">Identificar un sentimiento como positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="5af49-163">Identify sentiment as positive or negative.</span></span>
* <span data-ttu-id="5af49-164">Clasificar correo electrónico como correo no deseado o correo válido.</span><span class="sxs-lookup"><span data-stu-id="5af49-164">Classify email as spam, junk, or good.</span></span>
* <span data-ttu-id="5af49-165">Determinar si la muestra de laboratorio de un paciente es cancerosa.</span><span class="sxs-lookup"><span data-stu-id="5af49-165">Determine whether a patient's lab sample is cancerous.</span></span>
* <span data-ttu-id="5af49-166">Categorizar a los clientes por su propensión a responder a una campaña de ventas.</span><span class="sxs-lookup"><span data-stu-id="5af49-166">Categorize customers by their propensity to respond to a sales campaign.</span></span>

<span data-ttu-id="5af49-167">Los casos de uso del algoritmo de aprendizaje de clasificación son a menudo de uno de los tipos siguientes:</span><span class="sxs-lookup"><span data-stu-id="5af49-167">Classification learning algorithm use cases are frequently one of the following types:</span></span>

* <span data-ttu-id="5af49-168">Binario: A o B.</span><span class="sxs-lookup"><span data-stu-id="5af49-168">Binary: either A or B.</span></span>
* <span data-ttu-id="5af49-169">Multiclase: varias categorías que se pueden predecir mediante el uso de un único modelo.</span><span class="sxs-lookup"><span data-stu-id="5af49-169">Multiclass: multiple categories that can be predicted by using a single model.</span></span>

<span data-ttu-id="5af49-170">Para este tipo de problema, use un algoritmo de aprendizaje de clasificación multiclase, ya que la predicción de categoría de problema puede ser una de varias categorías (multiclase) en lugar de solo dos (binaria).</span><span class="sxs-lookup"><span data-stu-id="5af49-170">For this type of problem, use a Multiclass classification learning algorithm, since your issue category prediction can be one of multiple categories (multiclass) rather than just two (binary).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="5af49-171">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="5af49-171">Create a console application</span></span>

### <a name="create-a-project"></a><span data-ttu-id="5af49-172">Crear un proyecto</span><span class="sxs-lookup"><span data-stu-id="5af49-172">Create a project</span></span>

1. <span data-ttu-id="5af49-173">Abra Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="5af49-173">Open Visual Studio 2017.</span></span> <span data-ttu-id="5af49-174">Seleccione **Archivo** > **Nuevo** > **Proyecto** de la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="5af49-174">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="5af49-175">En el cuadro de diálogo **Nuevo proyecto**, seleccione el nodo **Visual C#** seguido del nodo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="5af49-175">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="5af49-176">Después, seleccione la plantilla del proyecto **Aplicación de consola (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="5af49-176">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="5af49-177">En el cuadro de texto **Nombre**, escriba "SentimentAnalysis" y después haga clic en el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5af49-177">In the **Name** text box, type "SentimentAnalysis" and then select the **OK** button.</span></span>

2. <span data-ttu-id="5af49-178">Cree un directorio denominado *Datos* en el proyecto para guardar los archivos del conjunto de datos:</span><span class="sxs-lookup"><span data-stu-id="5af49-178">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="5af49-179">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **Nueva carpeta**.</span><span class="sxs-lookup"><span data-stu-id="5af49-179">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="5af49-180">Escriba "Datos" y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="5af49-180">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="5af49-181">En el proyecto, cree un directorio denominado *Modelos* para guardar el modelo:</span><span class="sxs-lookup"><span data-stu-id="5af49-181">Create a directory named *Models* in your project to save your model:</span></span>

    <span data-ttu-id="5af49-182">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **Nueva carpeta**.</span><span class="sxs-lookup"><span data-stu-id="5af49-182">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="5af49-183">Escriba "Modelos" y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="5af49-183">Type "Models" and hit Enter.</span></span>

4. <span data-ttu-id="5af49-184">Instale el **paquete NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="5af49-184">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="5af49-185">En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="5af49-185">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="5af49-186">Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.ML**, seleccione ese paquete en la lista y seleccione el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="5af49-186">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="5af49-187">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="5af49-187">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="5af49-188">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="5af49-188">Prepare your data</span></span>

1. <span data-ttu-id="5af49-189">Descargue los conjuntos de datos [issues_train.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) e [issues_test.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) y guárdelos en la carpeta *Datos* que ha creado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="5af49-189">Download the [issues_train.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) and the [issues_test.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) data sets and save them to the *Data* folder previously created.</span></span> <span data-ttu-id="5af49-190">El primer conjunto de datos entrena el modelo de aprendizaje automático y el segundo puede usarse para evaluar su grado de precisión.</span><span class="sxs-lookup"><span data-stu-id="5af49-190">The first dataset trains the machine learning model and the second can be used to evaluate how accurate your model is.</span></span>

2. <span data-ttu-id="5af49-191">En el Explorador de soluciones, haga clic con el botón secundario en cada uno de los archivos \*.tsv y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5af49-191">In Solution Explorer, right-click each of the \*.tsv files and select **Properties**.</span></span> <span data-ttu-id="5af49-192">En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.</span><span class="sxs-lookup"><span data-stu-id="5af49-192">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="5af49-193">Crear clases y definir rutas de acceso</span><span class="sxs-lookup"><span data-stu-id="5af49-193">Create classes and define paths</span></span>

<span data-ttu-id="5af49-194">Agregue las siguientes instrucciones `using` adicionales a la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="5af49-194">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddUsings)]

<span data-ttu-id="5af49-195">Cree tres campos globales para contener las rutas de acceso a los archivos descargados recientemente y variables globales para `MLContext`, `DataView`, `PredictionEngine` y `TextLoader`:</span><span class="sxs-lookup"><span data-stu-id="5af49-195">Create three global fields to hold the paths to the recently downloaded files, and global variables for the `MLContext`,`DataView`, `PredictionEngine`, and `TextLoader`:</span></span>

* <span data-ttu-id="5af49-196">`_trainDataPath` tiene la ruta de acceso al conjunto de datos utilizado para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="5af49-196">`_trainDataPath` has the path to the dataset used to train the model.</span></span>
* <span data-ttu-id="5af49-197">`_testDataPath` tiene la ruta de acceso al conjunto de datos utilizado para evaluar el modelo.</span><span class="sxs-lookup"><span data-stu-id="5af49-197">`_testDataPath` has the path to the dataset used to evaluate the model.</span></span>
* <span data-ttu-id="5af49-198">`_modelPath` tiene la ruta de acceso donde se guarda el modelo entrenado.</span><span class="sxs-lookup"><span data-stu-id="5af49-198">`_modelPath` has the path where the trained model is saved.</span></span>
* <span data-ttu-id="5af49-199">`_mlContext` es el elemento <xref:Microsoft.ML.MLContext> que proporciona el contexto de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="5af49-199">`_mlContext` is the <xref:Microsoft.ML.MLContext> that provides processing context.</span></span>
* <span data-ttu-id="5af49-200">`_trainingDataView` es el elemento <xref:Microsoft.Data.DataView.IDataView> que se usa para procesar el conjunto de datos de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="5af49-200">`_trainingDataView` is the <xref:Microsoft.Data.DataView.IDataView> used to process the training dataset.</span></span>
* <span data-ttu-id="5af49-201">`_predEngine` es el elemento <xref:Microsoft.ML.PredictionEngine%602> que se usa para las predicciones únicas.</span><span class="sxs-lookup"><span data-stu-id="5af49-201">`_predEngine` is the <xref:Microsoft.ML.PredictionEngine%602> used for single predictions.</span></span>
* <span data-ttu-id="5af49-202">`_reader` es el <xref:Microsoft.ML.Data.TextLoader> utilizado para cargar y transformar los conjuntos de datos.</span><span class="sxs-lookup"><span data-stu-id="5af49-202">`_reader` is the <xref:Microsoft.ML.Data.TextLoader> used to load and transform the datasets.</span></span>

<span data-ttu-id="5af49-203">Agregue el código siguiente a la línea justo encima del método `Main` para especificar esas rutas de acceso y otras variables:</span><span class="sxs-lookup"><span data-stu-id="5af49-203">Add the following code to the line right above the `Main` method to specify those paths and the other variables:</span></span>

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DeclareGlobalVariables)]

<span data-ttu-id="5af49-204">Cree algunas clases para los datos de entrada y las predicciones.</span><span class="sxs-lookup"><span data-stu-id="5af49-204">Create some classes for your input data and predictions.</span></span> <span data-ttu-id="5af49-205">Agregue una nueva clase a su proyecto:</span><span class="sxs-lookup"><span data-stu-id="5af49-205">Add a new class to your project:</span></span>

1. <span data-ttu-id="5af49-206">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="5af49-206">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="5af49-207">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *GitHubIssueData.cs*.</span><span class="sxs-lookup"><span data-stu-id="5af49-207">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *GitHubIssueData.cs*.</span></span> <span data-ttu-id="5af49-208">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="5af49-208">Then, select the **Add** button.</span></span>

    <span data-ttu-id="5af49-209">Se abre el archivo *GitHubIssueData.cs* en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="5af49-209">The *GitHubIssueData.cs* file opens in the code editor.</span></span> <span data-ttu-id="5af49-210">Agregue la siguiente instrucción `using` a la parte superior de *GitHubIssueData.cs*:</span><span class="sxs-lookup"><span data-stu-id="5af49-210">Add the following `using` statement to the top of *GitHubIssueData.cs*:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#AddUsings)]

<span data-ttu-id="5af49-211">Quite la definición de clase existente y agregue el código siguiente, que tiene dos clases `GitHubIssue` y `IssuePrediction`, al archivo *GitHubIssueData.cs*:</span><span class="sxs-lookup"><span data-stu-id="5af49-211">Remove the existing class definition and add the following code, which has two classes `GitHubIssue` and `IssuePrediction`, to the *GitHubIssueData.cs* file:</span></span>

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#DeclareTypes)]

<span data-ttu-id="5af49-212">`GitHubIssue` es la clase de conjunto de datos de entrada y contiene los siguientes campos de <xref:System.String>:</span><span class="sxs-lookup"><span data-stu-id="5af49-212">`GitHubIssue` is the input dataset class and has the following <xref:System.String> fields:</span></span>

* <span data-ttu-id="5af49-213">`ID` contiene un valor para el id. del problema de GitHub</span><span class="sxs-lookup"><span data-stu-id="5af49-213">`ID` contains a value for the GitHub issue ID</span></span>
* <span data-ttu-id="5af49-214">`Area` contiene un valor para la etiqueta `Area`</span><span class="sxs-lookup"><span data-stu-id="5af49-214">`Area` contains a value for the `Area` label</span></span>
* <span data-ttu-id="5af49-215">`Title` contiene el título del problema de GitHub</span><span class="sxs-lookup"><span data-stu-id="5af49-215">`Title` contains the GitHub issue title</span></span>
* <span data-ttu-id="5af49-216">`Description` contiene la descripción del problema de GitHub</span><span class="sxs-lookup"><span data-stu-id="5af49-216">`Description` contains the GitHub issue description</span></span>

<span data-ttu-id="5af49-217">`IssuePrediction` es la clase usada para la predicción una vez entrenado el modelo.</span><span class="sxs-lookup"><span data-stu-id="5af49-217">`IssuePrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="5af49-218">Tiene un solo elemento `string` (`Area`) y un atributo `PredictedLabel` `ColumnName`.</span><span class="sxs-lookup"><span data-stu-id="5af49-218">It has a single `string` (`Area`) and a `PredictedLabel` `ColumnName` attribute.</span></span> <span data-ttu-id="5af49-219">`Label` se usa para crear y entrenar el modelo, y se usa también con un segundo conjunto de datos para evaluar el modelo.</span><span class="sxs-lookup"><span data-stu-id="5af49-219">The `Label` is used to create and train the model, and it's also used with a second dataset to evaluate the model.</span></span> <span data-ttu-id="5af49-220">`PredictedLabel` se usa durante la predicción y la evaluación.</span><span class="sxs-lookup"><span data-stu-id="5af49-220">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="5af49-221">Para la evaluación, se utiliza una entrada con los datos de entrenamiento, los valores de predicción y el modelo.</span><span class="sxs-lookup"><span data-stu-id="5af49-221">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="5af49-222">Cuando se crea un modelo con ML.NET, empieza creando un elemento <xref:Microsoft.ML.MLContext>.</span><span class="sxs-lookup"><span data-stu-id="5af49-222">When building a model with ML.NET, you start by creating an <xref:Microsoft.ML.MLContext>.</span></span> <span data-ttu-id="5af49-223">`MLContext` es comparable conceptualmente a usar `DbContext` en Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="5af49-223">`MLContext` is comparable conceptually to using `DbContext` in Entity Framework.</span></span> <span data-ttu-id="5af49-224">El entorno proporciona un contexto para el trabajo de ML que puede usarse para el seguimiento y registro de excepciones.</span><span class="sxs-lookup"><span data-stu-id="5af49-224">The environment provides a context for your ML job that can be used for exception tracking and logging.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="5af49-225">Inicializar variables en Main</span><span class="sxs-lookup"><span data-stu-id="5af49-225">Initialize variables in Main</span></span>

<span data-ttu-id="5af49-226">Inicialice la variante global `_mlContext` con una nueva instancia de `MLContext` usando una inicialización aleatoria (`seed: 0`) para obtener resultados repetibles o deterministas en varios entrenamientos.</span><span class="sxs-lookup"><span data-stu-id="5af49-226">Initialize the `_mlContext` global variable  with a new instance of `MLContext` with a random seed (`seed: 0`) for repeatable/deterministic results across multiple trainings.</span></span>  <span data-ttu-id="5af49-227">Reemplace la línea `Console.WriteLine("Hello World!")` por el código siguiente en el método `Main`:</span><span class="sxs-lookup"><span data-stu-id="5af49-227">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateMLContext)]

## <a name="load-the-data"></a><span data-ttu-id="5af49-228">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="5af49-228">Load the data</span></span>

<span data-ttu-id="5af49-229">A continuación, inicialice la variable global `_trainingDataView` <xref:Microsoft.Data.DataView.IDataView> y cargue los datos con el parámetro `_trainDataPath`.</span><span class="sxs-lookup"><span data-stu-id="5af49-229">Next, initialize the `_trainingDataView` <xref:Microsoft.Data.DataView.IDataView> global variable and load the data with the `_trainDataPath` parameter.</span></span>

 <span data-ttu-id="5af49-230">Como la entrada y salida de [`Transforms`](../basic-concepts-model-training-in-mldotnet.md#transformer), `DataView` es el tipo de canalización de datos fundamentales, comparable con `IEnumerable` para `LINQ`.</span><span class="sxs-lookup"><span data-stu-id="5af49-230">As the input and output of [`Transforms`](../basic-concepts-model-training-in-mldotnet.md#transformer), a `DataView` is the fundamental data pipeline type, comparable to `IEnumerable` for `LINQ`.</span></span>

<span data-ttu-id="5af49-231">En ML.NET, los datos son similares a `SQL view`.</span><span class="sxs-lookup"><span data-stu-id="5af49-231">In ML.NET, data is similar to a `SQL view`.</span></span> <span data-ttu-id="5af49-232">Se evalúan lentamente, se esquematizan y son heterogéneos.</span><span class="sxs-lookup"><span data-stu-id="5af49-232">It is lazily evaluated, schematized, and heterogenous.</span></span> <span data-ttu-id="5af49-233">El objeto es la primera parte de la canalización y carga los datos.</span><span class="sxs-lookup"><span data-stu-id="5af49-233">The object is the first part of the pipeline, and loads the data.</span></span> <span data-ttu-id="5af49-234">Para este tutorial, carga un conjunto de datos con los títulos y descripciones de los problemas, así como la etiqueta de GitHub del área correspondiente.</span><span class="sxs-lookup"><span data-stu-id="5af49-234">For this tutorial, it loads a dataset with issue titles, descriptions, and corresponding area GitHub label.</span></span> <span data-ttu-id="5af49-235">El elemento `DataView` se usa para crear y entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="5af49-235">The `DataView` is used to create and train the model.</span></span>

<span data-ttu-id="5af49-236">Puesto que el tipo de modelo de datos `GitHubIssue` que ha creado anteriormente coincide con el esquema del conjunto de datos, puede combinar la inicialización, la asignación y la carga del conjunto de datos en una línea de código.</span><span class="sxs-lookup"><span data-stu-id="5af49-236">Since your previously created `GitHubIssue` data model type matches the dataset schema, you can combine the initialization, mapping, and dataset loading into one line of code.</span></span>

<span data-ttu-id="5af49-237">La primera parte de la línea (`CreateTextLoader<GitHubIssue>(hasHeader: true)`) crea un elemento <xref:Microsoft.ML.Data.TextLoader> mediante la inferencia del esquema del conjunto de datos del tipo de modelo de datos `GitHubIssue` y el uso del encabezado del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="5af49-237">The first part of the line (`CreateTextLoader<GitHubIssue>(hasHeader: true)`) creates a <xref:Microsoft.ML.Data.TextLoader> by inferring the dataset schema from the `GitHubIssue` data model type and using the dataset header.</span></span>

<span data-ttu-id="5af49-238">Ha definido el esquema de datos anteriormente al crear la clase `GitHubIssue`.</span><span class="sxs-lookup"><span data-stu-id="5af49-238">You defined the data schema previously when you created the `GitHubIssue` class.</span></span> <span data-ttu-id="5af49-239">Para su esquema:</span><span class="sxs-lookup"><span data-stu-id="5af49-239">For your schema:</span></span>

* <span data-ttu-id="5af49-240">`ID`, la primera columna (id. de problema de GitHub).</span><span class="sxs-lookup"><span data-stu-id="5af49-240">the first column `ID` (GitHub Issue ID)</span></span>
* <span data-ttu-id="5af49-241">`Area`, la segunda columna (la predicción para el entrenamiento).</span><span class="sxs-lookup"><span data-stu-id="5af49-241">the second column `Area` (the prediction for training)</span></span>
* <span data-ttu-id="5af49-242">`Title`, la tercera columna (título del problema de GitHub), es la primera [característica](../resources/glossary.md##feature) usada para predecir el `Area`.</span><span class="sxs-lookup"><span data-stu-id="5af49-242">the third column `Title` (GitHub issue title) is the first [feature](../resources/glossary.md##feature)  used for predicting the `Area`</span></span>
* <span data-ttu-id="5af49-243">`Description`, la cuarta columna, es la segunda característica usada para predecir el `Area`.</span><span class="sxs-lookup"><span data-stu-id="5af49-243">the fourth column  `Description` is the second feature used for predicting the `Area`</span></span>

<span data-ttu-id="5af49-244">La segunda parte de la línea (`.Read(_trainDataPath)`) usa el método <xref:Microsoft.ML.Data.TextLoader.Read%2A> para cargar el archivo de texto del entrenamiento usando `_trainDataPath` en la variable global `IDataView` (`_trainingDataView`).</span><span class="sxs-lookup"><span data-stu-id="5af49-244">The second part of the line  (`.Read(_trainDataPath)`) uses <xref:Microsoft.ML.Data.TextLoader.Read%2A> method to load the training text file using `_trainDataPath` into the `IDataView` (`_trainingDataView`) global variable.</span></span>  

<span data-ttu-id="5af49-245">Para inicializar y cargar la variable global `_trainingDataView` con el fin de volver a usarla para la canalización, agregue el siguiente código después de la inicialización de `mlContext`:</span><span class="sxs-lookup"><span data-stu-id="5af49-245">To initialize and load the `_trainingDataView` global variable in order to use it for the pipeline, add the following code after the  `mlContext` initialization:</span></span>

[!code-csharp[LoadTrainData](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTrainData)]


<span data-ttu-id="5af49-246">Agregue lo siguiente como la siguiente línea de código en el método `Main`:</span><span class="sxs-lookup"><span data-stu-id="5af49-246">Add the following as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallProcessData](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallProcessData)]

<span data-ttu-id="5af49-247">El método `ProcessData` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="5af49-247">The `ProcessData` method executes the following tasks:</span></span>

* <span data-ttu-id="5af49-248">Extrae y transforma los datos.</span><span class="sxs-lookup"><span data-stu-id="5af49-248">Extracts and transforms the data.</span></span>
* <span data-ttu-id="5af49-249">Devuelve la canalización de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="5af49-249">Returns the processing pipeline.</span></span>

<span data-ttu-id="5af49-250">Cree el método `ProcessData`, justo después del método `Main`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="5af49-250">Create the `ProcessData` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static EstimatorChain<ITransformer> ProcessData()
{

}
```

## <a name="extract-features-and-transform-the-data"></a><span data-ttu-id="5af49-251">Extraer características y transformar los datos</span><span class="sxs-lookup"><span data-stu-id="5af49-251">Extract Features and transform the data</span></span>

<span data-ttu-id="5af49-252">El procesamiento previo y la limpieza de datos son tareas importantes que se producen antes de que un conjunto de datos se utilice de forma eficaz para el aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="5af49-252">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span> <span data-ttu-id="5af49-253">Los datos sin procesar contienen a menudo ruido y son poco de fiar; además, es posible que les falten valores.</span><span class="sxs-lookup"><span data-stu-id="5af49-253">Raw data is often noisy and unreliable, and may be missing values.</span></span> <span data-ttu-id="5af49-254">El uso de datos sin estas tareas de modelado puede producir resultados engañosos.</span><span class="sxs-lookup"><span data-stu-id="5af49-254">Using data without these modeling tasks can produce misleading results.</span></span>

<span data-ttu-id="5af49-255">Las tuberías de transformación de ML.NET componen un conjunto `transforms` personalización que se aplica a sus datos antes del entrenamiento o la prueba.</span><span class="sxs-lookup"><span data-stu-id="5af49-255">ML.NET's transform pipelines compose a custom `transforms`set that is applied to your data before training or testing.</span></span> <span data-ttu-id="5af49-256">El propósito principal de las transformaciones es la [caracterización](../resources/glossary.md#feature-engineering) de datos.</span><span class="sxs-lookup"><span data-stu-id="5af49-256">The transforms' primary purpose is data [featurization](../resources/glossary.md#feature-engineering).</span></span> <span data-ttu-id="5af49-257">Los algoritmos de aprendizaje automático comprenden los datos [caracterizados](../resources/glossary.md#feature), por lo que el paso siguiente es transformar nuestro datos textuales en un formato que reconozcan nuestros algoritmos de ML.</span><span class="sxs-lookup"><span data-stu-id="5af49-257">Machine learning algorithms understand [featurized](../resources/glossary.md#feature) data, so the next step is to transform our textual data into a format that our ML algorithms recognize.</span></span> <span data-ttu-id="5af49-258">Ese formato es un [vector numérico](../resources/glossary.md#numerical-feature-vector).</span><span class="sxs-lookup"><span data-stu-id="5af49-258">That format is a [numeric vector](../resources/glossary.md#numerical-feature-vector).</span></span>

<span data-ttu-id="5af49-259">En los pasos siguientes se hace referencia a las columnas con los nombres definidos en la clase `GitHubIssue`.</span><span class="sxs-lookup"><span data-stu-id="5af49-259">In the next steps, we refer to the columns by the names defined in the `GitHubIssue` class.</span></span>

<span data-ttu-id="5af49-260">Si el modelo se ha entrenado y evaluado, de forma predeterminada, los valores de la columna **Label** se consideran valores correctos para predecir.</span><span class="sxs-lookup"><span data-stu-id="5af49-260">When the model is trained and evaluated, by default, the values in the **Label** column are considered as correct values to be predicted.</span></span> <span data-ttu-id="5af49-261">Para predecir la etiqueta de área de GitHub para `GitHubIssue`, debe copiar la columna `Area` en la columna **Etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="5af49-261">As we want to predict the Area GitHub label for a `GitHubIssue`, copy the `Area` column into the **Label** column.</span></span> <span data-ttu-id="5af49-262">Para ello, use `MLContext.Transforms.Conversion.MapValueToKey`, que es un contenedor para la clase de transformación <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="5af49-262">To do that, use the `MLContext.Transforms.Conversion.MapValueToKey`, which is a wrapper for the <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A> transformation class.</span></span>  <span data-ttu-id="5af49-263">`MapValueToKey` devuelve un elemento <xref:Microsoft.ML.Data.EstimatorChain%601> que será efectivamente una canalización.</span><span class="sxs-lookup"><span data-stu-id="5af49-263">The `MapValueToKey` returns an <xref:Microsoft.ML.Data.EstimatorChain%601> that will effectively be a pipeline.</span></span> <span data-ttu-id="5af49-264">Asigne un nombre a `pipeline`, ya que luego anexará el entrenador a `EstimatorChain`.</span><span class="sxs-lookup"><span data-stu-id="5af49-264">Name this `pipeline` as you will then append the trainer to the `EstimatorChain`.</span></span> <span data-ttu-id="5af49-265">Agregue esta línea de código:</span><span class="sxs-lookup"><span data-stu-id="5af49-265">Add the next line of code:</span></span>

[!code-csharp[MapValueToKey](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#MapValueToKey)]

 <span data-ttu-id="5af49-266">Con la caracterización, se asignan diferentes valores clave numéricos a distintos valores de cada una de las columnas. El algoritmo de aprendizaje automático aprovecha este proceso.</span><span class="sxs-lookup"><span data-stu-id="5af49-266">Featurizing assigns different numeric key values to the different values in each of the columns and is used by the machine learning algorithm.</span></span> <span data-ttu-id="5af49-267">A continuación, llame a `mlContext.Transforms.Text.FeaturizeText`, que caracteriza las columnas de texto (`Title` y `Description`) en un vector numérico para cada elemento `TitleFeaturized` y `DescriptionFeaturized` al que se llama.</span><span class="sxs-lookup"><span data-stu-id="5af49-267">Next, call `mlContext.Transforms.Text.FeaturizeText` which featurizes the text (`Title` and `Description`) columns into a numeric vector for each called `TitleFeaturized` and `DescriptionFeaturized`.</span></span> <span data-ttu-id="5af49-268">Anexe la caracterización para ambas columnas a la canalización usando el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="5af49-268">Append the featurization for both columns to the pipeline with the following code:</span></span>

[!code-csharp[FeaturizeText](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#FeaturizeText)]

>[!WARNING]
> <span data-ttu-id="5af49-269">En la versión 0.10 de ML.NET se ha cambiado el orden de los parámetros de transformación.</span><span class="sxs-lookup"><span data-stu-id="5af49-269">ML.NET Version 0.10 has changed the order of the Transform parameters.</span></span> <span data-ttu-id="5af49-270">Esto no generará un error hasta que realice la compilación.</span><span class="sxs-lookup"><span data-stu-id="5af49-270">This will not error out until you build.</span></span> <span data-ttu-id="5af49-271">Use los nombres de parámetro para las transformaciones, como se muestra en el fragmento de código anterior.</span><span class="sxs-lookup"><span data-stu-id="5af49-271">Use the parameter names for Transforms as illustrated in the previous code snippet.</span></span>

<span data-ttu-id="5af49-272">En el último paso para la preparación de los datos, se combinan todas las columnas de característica en la columna **Características** mediante la clase de transformación `Concatenate`.</span><span class="sxs-lookup"><span data-stu-id="5af49-272">The last step in data preparation combines all of the feature columns into the **Features** column using the `Concatenate` transformation class.</span></span> <span data-ttu-id="5af49-273">De forma predeterminada, un algoritmo de aprendizaje solo procesa las características de la columna **Features**.</span><span class="sxs-lookup"><span data-stu-id="5af49-273">By default, a learning algorithm processes only features from the **Features** column.</span></span> <span data-ttu-id="5af49-274">Anexe esta transformación a la canalización usando el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="5af49-274">Append this transformation to the pipeline with the following code:</span></span>

[!code-csharp[Concatenate](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Concatenate)]

 <span data-ttu-id="5af49-275">A continuación, anexe <xref:Microsoft.ML.Data.EstimatorChain`1.AppendCacheCheckpoint%2A> para almacenar en caché el objeto DataView, de modo que pueda obtener un mayor rendimiento al iterar los datos varias veces con la caché, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="5af49-275">Next, append a <xref:Microsoft.ML.Data.EstimatorChain`1.AppendCacheCheckpoint%2A> to cache the DataView so when you iterate over the data multiple times using the cache might get better performance, as with the following code:</span></span>

[!code-csharp[AppendCache](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AppendCache)]

<span data-ttu-id="5af49-276">Devuelva la canalización al final del método `ProcessData`.</span><span class="sxs-lookup"><span data-stu-id="5af49-276">Return the pipeline at the end of the `ProcessData` method.</span></span>

[!code-csharp[ReturnPipeline](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnPipeline)]

<span data-ttu-id="5af49-277">En este paso se controla el preprocesamiento y la caracterización.</span><span class="sxs-lookup"><span data-stu-id="5af49-277">This step handles preprocessing/featurization.</span></span> <span data-ttu-id="5af49-278">El uso de componentes adicionales disponibles en ML.NET permite conseguir mejores resultados con el modelo.</span><span class="sxs-lookup"><span data-stu-id="5af49-278">Using additional components available in ML.NET can enable better results with your model.</span></span>

## <a name="build-and-train-the-model"></a><span data-ttu-id="5af49-279">Creación y entrenamiento del modelo</span><span class="sxs-lookup"><span data-stu-id="5af49-279">Build and train the model</span></span>

<span data-ttu-id="5af49-280">Agregue la siguiente llamada al método `BuildAndTrainModel` como siguiente línea de código del método `Main`:</span><span class="sxs-lookup"><span data-stu-id="5af49-280">Add the following call to the `BuildAndTrainModel`method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallBuildAndTrainModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallBuildAndTrainModel)]

<span data-ttu-id="5af49-281">El método `BuildAndTrainModel` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="5af49-281">The `BuildAndTrainModel` method executes the following tasks:</span></span>

* <span data-ttu-id="5af49-282">Crea la clase de algoritmo de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="5af49-282">Creates the training algorithm class.</span></span>
* <span data-ttu-id="5af49-283">Entrena el modelo.</span><span class="sxs-lookup"><span data-stu-id="5af49-283">Trains the model.</span></span>
* <span data-ttu-id="5af49-284">Predice el área según los datos de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="5af49-284">Predicts area based on training data.</span></span>
* <span data-ttu-id="5af49-285">Guarda el modelo en un archivo `.zip`.</span><span class="sxs-lookup"><span data-stu-id="5af49-285">Saves the model to a `.zip` file.</span></span>
* <span data-ttu-id="5af49-286">Devuelve el modelo.</span><span class="sxs-lookup"><span data-stu-id="5af49-286">Returns the model.</span></span>

<span data-ttu-id="5af49-287">Cree el método `BuildAndTrainModel`, justo después del método `Main`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="5af49-287">Create the `BuildAndTrainModel` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static EstimatorChain<KeyToValueMappingTransformer> BuildAndTrainModel(IDataView trainingDataView, EstimatorChain<ITransformer> pipeline)
{

}
```

<span data-ttu-id="5af49-288">Tenga en cuenta que se pasan dos parámetros al método BuildAndTrainModel; un elemento `IDataView` para el conjunto de datos de entrenamiento (`trainingDataView`) y un elemento <xref:Microsoft.ML.Data.EstimatorChain%601> para la canalización de procesamiento creada en ProcessData (`pipeline`).</span><span class="sxs-lookup"><span data-stu-id="5af49-288">Notice that two parameters are passed into the BuildAndTrainModel method; an `IDataView` for the training dataset (`trainingDataView`), and a <xref:Microsoft.ML.Data.EstimatorChain%601> for the processing pipeline created in ProcessData (`pipeline`).</span></span>

 <span data-ttu-id="5af49-289">Agregue el código siguiente a la primera línea del método `BuildAndTrainModel`:</span><span class="sxs-lookup"><span data-stu-id="5af49-289">Add the following code as the first line of the `BuildAndTrainModel` method:</span></span>

### <a name="choose-a-learning-algorithm"></a><span data-ttu-id="5af49-290">Elegir un algoritmo de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="5af49-290">Choose a learning algorithm</span></span>

<span data-ttu-id="5af49-291">Para agregar el algoritmo de aprendizaje, llame al método contenedor `mlContext.MulticlassClassification.Trainers.StochasticDualCoordinateAscent`, que devuelve un objeto <xref:Microsoft.ML.Trainers.SdcaMultiClassTrainer>.</span><span class="sxs-lookup"><span data-stu-id="5af49-291">To add the learning algorithm, call the `mlContext.MulticlassClassification.Trainers.StochasticDualCoordinateAscent` wrapper method which returns a <xref:Microsoft.ML.Trainers.SdcaMultiClassTrainer> object.</span></span>  <span data-ttu-id="5af49-292">`SdcaMultiClassTrainer` se anexa a `pipeline` y acepta los elementos `Title` y `Description` (`Features`) caracterizados y los parámetros de entrada de `Label` para aprender de los datos históricos.</span><span class="sxs-lookup"><span data-stu-id="5af49-292">The `SdcaMultiClassTrainer` is appended to the `pipeline` and accepts the featurized `Title` and `Description` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span> <span data-ttu-id="5af49-293">También deberá asignar la etiqueta al valor para devolverlo a su estado de lectura original.</span><span class="sxs-lookup"><span data-stu-id="5af49-293">You also need to map the label to the value to return to its original readable state.</span></span> <span data-ttu-id="5af49-294">Realice una de estas acciones con el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="5af49-294">Do both of those actions with the following code:</span></span>

[!code-csharp[AddTrainer](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTrainer)]

### <a name="train-the-model"></a><span data-ttu-id="5af49-295">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="5af49-295">Train the model</span></span>

<span data-ttu-id="5af49-296">Se entrena el modelo, <xref:Microsoft.ML.Data.TransformerChain%601>, en función del conjunto de datos que se haya cargado y transformado.</span><span class="sxs-lookup"><span data-stu-id="5af49-296">You train the model, <xref:Microsoft.ML.Data.TransformerChain%601>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="5af49-297">Una vez que se ha definido el estimador, entrenará el modelo mediante <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> proporcionando al mismo tiempo los datos de entrenamiento ya cargados.</span><span class="sxs-lookup"><span data-stu-id="5af49-297">Once the estimator has been defined, you train your model using the <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> while providing the already loaded training data.</span></span> <span data-ttu-id="5af49-298">Este método devuelve un modelo que se usa para las predicciones.</span><span class="sxs-lookup"><span data-stu-id="5af49-298">This  method returns a model to use for predictions.</span></span> <span data-ttu-id="5af49-299">`trainingPipeline.Fit()` entrena la canalización y devuelve `Transformer` según la `DataView` que se pasa.</span><span class="sxs-lookup"><span data-stu-id="5af49-299">`trainingPipeline.Fit()` trains the pipeline and returns a `Transformer` based on the `DataView` passed in.</span></span> <span data-ttu-id="5af49-300">El experimento no se ejecuta hasta que se ejecute el método `.Fit()`.</span><span class="sxs-lookup"><span data-stu-id="5af49-300">The experiment is not executed until the `.Fit()` method runs.</span></span>

<span data-ttu-id="5af49-301">Agregue el código siguiente al método `BuildAndTrainModel`:</span><span class="sxs-lookup"><span data-stu-id="5af49-301">Add the following code to the `BuildAndTrainModel` method:</span></span>

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#TrainModel)]

<span data-ttu-id="5af49-302">Aunque `model` es un elemento `transformer` que opera en muchas filas de datos, la necesidad de predicciones sobre ejemplos individuales es un escenario de producción muy común.</span><span class="sxs-lookup"><span data-stu-id="5af49-302">While the `model` is a `transformer` that operates on many rows of data, a need for predictions on individual examples is a common production scenario.</span></span> <span data-ttu-id="5af49-303"><xref:Microsoft.ML.PredictionEngine%602> es un contenedor que se devuelve del método `CreatePredictionEngine`.</span><span class="sxs-lookup"><span data-stu-id="5af49-303">The <xref:Microsoft.ML.PredictionEngine%602> is a wrapper that is returned from the `CreatePredictionEngine` method.</span></span> <span data-ttu-id="5af49-304">Vamos a agregar el código siguiente para crear `PredictionEngine` como la línea siguiente en el método `BuildAndTrainModel`:</span><span class="sxs-lookup"><span data-stu-id="5af49-304">Let's add the following code to create the `PredictionEngine` as the next line in the `BuildAndTrainModel` Method:</span></span>

[!code-csharp[CreatePredictionEngine1](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine1)]

### <a name="predict-with-the-trained-model"></a><span data-ttu-id="5af49-305">Predecir con el modelo entrenado</span><span class="sxs-lookup"><span data-stu-id="5af49-305">Predict with the trained model</span></span>

<span data-ttu-id="5af49-306">Agregue un problema de GitHub para probar la predicción del modelo entrenado en el método `Predict` mediante la creación de una instancia de `GitHubIssue`:</span><span class="sxs-lookup"><span data-stu-id="5af49-306">Add a GitHub issue to test the trained model's prediction in the `Predict` method by creating an instance of `GitHubIssue`:</span></span>

[!code-csharp[CreateTestIssue1](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateTestIssue1)]

<span data-ttu-id="5af49-307">Puede usarlo para predecir la etiqueta `Area` de una instancia única de los datos del problema.</span><span class="sxs-lookup"><span data-stu-id="5af49-307">You can use that to predict the `Area` label of a single instance of the issue data.</span></span> <span data-ttu-id="5af49-308">Para obtener una predicción, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> en los datos.</span><span class="sxs-lookup"><span data-stu-id="5af49-308">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="5af49-309">Los datos de entrada son una cadena y el modelo incluye la caracterización.</span><span class="sxs-lookup"><span data-stu-id="5af49-309">The input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="5af49-310">La canalización está sincronizada durante el entrenamiento y la predicción.</span><span class="sxs-lookup"><span data-stu-id="5af49-310">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="5af49-311">No fue necesario escribir el código de preprocesamiento o caracterización específicamente para las predicciones, y la misma API se encarga de las predicciones por lotes y puntuales.</span><span class="sxs-lookup"><span data-stu-id="5af49-311">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Predict)]

### <a name="using-the-model-prediction-results"></a><span data-ttu-id="5af49-312">Uso del modelo: resultados de la predicción</span><span class="sxs-lookup"><span data-stu-id="5af49-312">Using the model: prediction results</span></span>

<span data-ttu-id="5af49-313">Muestre `GitHubIssue` y la predicción de la etiqueta `Area` correspondiente para compartir los resultados y actuar en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="5af49-313">Display `GitHubIssue` and corresponding `Area` label prediction in order to share the results and act on them accordingly.</span></span>  <span data-ttu-id="5af49-314">Cree una visualización para los resultados mediante el código <xref:System.Console.WriteLine?displayProperty=nameWithType> siguiente:</span><span class="sxs-lookup"><span data-stu-id="5af49-314">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputPrediction](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#OutputPrediction)]

### <a name="return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="5af49-315">Devolución del modelo entrenado para su uso para la evaluación</span><span class="sxs-lookup"><span data-stu-id="5af49-315">Return the model trained to use for evaluation</span></span>

<span data-ttu-id="5af49-316">Devuelva el modelo al final del método `BuildAndTrainModel`.</span><span class="sxs-lookup"><span data-stu-id="5af49-316">Return the model at the end of the `BuildAndTrainModel` method.</span></span>

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnModel)]

## <a name="evaluate-the-model"></a><span data-ttu-id="5af49-317">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="5af49-317">Evaluate the model</span></span>

<span data-ttu-id="5af49-318">Ahora que ha creado y entrenado el modelo, debe evaluarlo con otro conjunto de datos para el control de calidad y la validación.</span><span class="sxs-lookup"><span data-stu-id="5af49-318">Now that you've created and trained the model, you need to evaluate it with a different dataset for quality assurance and validation.</span></span> <span data-ttu-id="5af49-319">En el método `Evaluate`, el modelo creado en `BuildAndTrainModel` se pasa para ser evaluado.</span><span class="sxs-lookup"><span data-stu-id="5af49-319">In the `Evaluate` method, the model created in `BuildAndTrainModel` is passed in to be evaluated.</span></span> <span data-ttu-id="5af49-320">Cree el método `Evaluate`, justo después de `BuildAndTrainModel`, como en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="5af49-320">Create the `Evaluate` method, just after `BuildAndTrainModel`, as in the following code:</span></span>

```csharp
public static void Evaluate()
{

}
```

<span data-ttu-id="5af49-321">El método `Evaluate` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="5af49-321">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="5af49-322">Carga el conjunto de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="5af49-322">Loads the test dataset.</span></span>
* <span data-ttu-id="5af49-323">Crea el evaluador multiclase.</span><span class="sxs-lookup"><span data-stu-id="5af49-323">Creates the multiclass evaluator.</span></span>
* <span data-ttu-id="5af49-324">Evalúa el modelo y crea métricas.</span><span class="sxs-lookup"><span data-stu-id="5af49-324">Evaluates the model and create metrics.</span></span>
* <span data-ttu-id="5af49-325">Muestra las métricas.</span><span class="sxs-lookup"><span data-stu-id="5af49-325">Displays the metrics.</span></span>

<span data-ttu-id="5af49-326">Agregue una llamada al método nuevo desde el método `Main`, justo debajo de la llamada al método `BuildAndTrainModel`, utilizando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="5af49-326">Add a call to the new method from the `Main` method, right under the `BuildAndTrainModel` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallEvaluate)]

<span data-ttu-id="5af49-327">Como hizo anteriormente con el conjunto de datos de entrenamiento, puede combinar la inicialización, la asignación y la carga del conjunto de datos de prueba en una línea de código.</span><span class="sxs-lookup"><span data-stu-id="5af49-327">As you did previously with the training dataset, you can combine the initialization, mapping, and test dataset loading into one line of code.</span></span> <span data-ttu-id="5af49-328">Puede evaluar el modelo utilizando este conjunto de datos como una comprobación de calidad.</span><span class="sxs-lookup"><span data-stu-id="5af49-328">You can evaluate the model using this dataset as a quality check.</span></span> <span data-ttu-id="5af49-329">Agregue el código siguiente al método `Evaluate`:</span><span class="sxs-lookup"><span data-stu-id="5af49-329">Add the following code to the `Evaluate` method:</span></span>

[!code-csharp[LoadTestDataset](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTestDataset)]

<span data-ttu-id="5af49-330">`MulticlassClassificationContext.Evaluate` es un contenedor para el método <xref:Microsoft.ML.MulticlassClassificationCatalog.Evaluate%2A> que calcula las métricas de calidad del modelo que usa el conjunto de datos especificado.</span><span class="sxs-lookup"><span data-stu-id="5af49-330">The `MulticlassClassificationContext.Evaluate` is a wrapper for the <xref:Microsoft.ML.MulticlassClassificationCatalog.Evaluate%2A> method that computes the quality metrics for the model using the specified dataset.</span></span> <span data-ttu-id="5af49-331">Devuelve un objeto <xref:Microsoft.ML.Data.MultiClassClassifierMetrics> que contiene las métricas totales calculadas por evaluadores de clasificación multiclase.</span><span class="sxs-lookup"><span data-stu-id="5af49-331">It returns a <xref:Microsoft.ML.Data.MultiClassClassifierMetrics> object that contains the overall metrics computed by multiclass classification evaluators.</span></span>
<span data-ttu-id="5af49-332">Para mostrar las métricas a fin de determinar la calidad del modelo, primero tendrá que obtenerlas.</span><span class="sxs-lookup"><span data-stu-id="5af49-332">To display the metrics to determine the quality of the model, you need to get them first.</span></span>
<span data-ttu-id="5af49-333">Tenga en cuenta el uso del método `Transform` de la variable global de aprendizaje automático `_trainedModel` (un transformador) para especificar características y devolver predicciones.</span><span class="sxs-lookup"><span data-stu-id="5af49-333">Notice the use of the `Transform` method of the machine learning `_trainedModel` global variable (a transformer) to input the features and return predictions.</span></span> <span data-ttu-id="5af49-334">Agregue el código siguiente al método `Evaluate` como la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="5af49-334">Add the following code to the `Evaluate` method as the next line:</span></span>

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Evaluate)]

<span data-ttu-id="5af49-335">Las siguientes métricas se evalúan para la clasificación multiclase:</span><span class="sxs-lookup"><span data-stu-id="5af49-335">The following metrics are evaluated for multiclass classification:</span></span>

* <span data-ttu-id="5af49-336">Microprecisión: todos los pares de ejemplo y clase contribuyen del mismo modo a la métrica de precisión.</span><span class="sxs-lookup"><span data-stu-id="5af49-336">Micro Accuracy - Every sample-class pair contributes equally to the accuracy metric.</span></span>  <span data-ttu-id="5af49-337">Le recomendamos que la microprecisión esté lo más cerca posible de 1.</span><span class="sxs-lookup"><span data-stu-id="5af49-337">You want Micro Accuracy to be as close to 1 as possible.</span></span>

* <span data-ttu-id="5af49-338">Macroprecisión: todas las clases contribuyen del mismo modo a la métrica de precisión.</span><span class="sxs-lookup"><span data-stu-id="5af49-338">Macro Accuracy - Every class contributes equally to the accuracy metric.</span></span> <span data-ttu-id="5af49-339">Las clases minoritarias tienen el mismo peso que las clases más grandes.</span><span class="sxs-lookup"><span data-stu-id="5af49-339">Minority classes are given equal weight as the larger classes.</span></span> <span data-ttu-id="5af49-340">Le recomendamos que la macroprecisión esté lo más cerca posible de 1.</span><span class="sxs-lookup"><span data-stu-id="5af49-340">You want Macro Accuracy to be as close to 1 as possible.</span></span>

* <span data-ttu-id="5af49-341">Pérdida de registro: vea [Pérdida de registro](../resources/glossary.md#log-loss).</span><span class="sxs-lookup"><span data-stu-id="5af49-341">Log-loss - see [Log Loss](../resources/glossary.md#log-loss).</span></span> <span data-ttu-id="5af49-342">Le recomendamos que la pérdida logarítmica esté lo más cerca posible de 0.</span><span class="sxs-lookup"><span data-stu-id="5af49-342">You want Log-loss to be as close to zero as possible.</span></span>

* <span data-ttu-id="5af49-343">Reducción de la pérdida de registro: parte de [-inf, 100], donde 100 equivale a una predicción perfecta, y 0 indica una predicción aproximada.</span><span class="sxs-lookup"><span data-stu-id="5af49-343">Log-loss reduction - Ranges from [-inf, 100], where 100 is perfect predictions and 0 indicates mean predictions.</span></span> <span data-ttu-id="5af49-344">Le recomendamos que la reducción de la pérdida de registro esté lo más cerca posible de 0.</span><span class="sxs-lookup"><span data-stu-id="5af49-344">You want Log-loss reduction to be as close to zero as possible.</span></span>

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="5af49-345">Mostrar las métricas para la validación del modelo</span><span class="sxs-lookup"><span data-stu-id="5af49-345">Displaying the metrics for model validation</span></span>

<span data-ttu-id="5af49-346">Utilice el código siguiente para mostrar las métricas, compartir los resultados y, a continuación, trabajar con ellos:</span><span class="sxs-lookup"><span data-stu-id="5af49-346">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayMetrics)]

### <a name="save-the-trained-and-evaluated-model"></a><span data-ttu-id="5af49-347">Guardar el modelo entrenado y evaluado</span><span class="sxs-lookup"><span data-stu-id="5af49-347">Save the trained and evaluated model</span></span>

<span data-ttu-id="5af49-348">En este punto, tiene un modelo de tipo <xref:Microsoft.ML.Data.TransformerChain%601> que se puede integrar en cualquiera de las aplicaciones de .NET nuevas o existentes.</span><span class="sxs-lookup"><span data-stu-id="5af49-348">At this point, you have a model of type <xref:Microsoft.ML.Data.TransformerChain%601> that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="5af49-349">Para guardar el modelo entrenado en un archivo .zip, agregue el siguiente código para llamar al método `SaveModelAsFile` como la línea siguiente en `BuildAndTrainModel`:</span><span class="sxs-lookup"><span data-stu-id="5af49-349">To save your trained model to a .zip file, add the following code to call the `SaveModelAsFile` method as the next line in `BuildAndTrainModel`:</span></span>

[!code-csharp[CallSaveModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallSaveModel)]

## <a name="save-the-model-as-a-zip-file"></a><span data-ttu-id="5af49-350">Almacenamiento del modelo como un archivo ZIP</span><span class="sxs-lookup"><span data-stu-id="5af49-350">Save the model as a .zip file</span></span>

<span data-ttu-id="5af49-351">Cree el método `SaveModelAsFile`, justo después del método `Evaluate`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="5af49-351">Create the `SaveModelAsFile` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="5af49-352">El método `SaveModelAsFile` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="5af49-352">The `SaveModelAsFile` method executes the following tasks:</span></span>

* <span data-ttu-id="5af49-353">Guarda el modelo como un archivo .zip.</span><span class="sxs-lookup"><span data-stu-id="5af49-353">Saves the model as a .zip file.</span></span>

<span data-ttu-id="5af49-354">A continuación, cree un método para guardar el modelo para que se pueda volver a usar y consumir en otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="5af49-354">Next, create a method to save the model so that it can be reused and consumed in other applications.</span></span> <span data-ttu-id="5af49-355">`ITransformer` tiene un método <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> que toma el campo global `_modelPath` y <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="5af49-355">The `ITransformer` has a <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> method that takes in the `_modelPath` global field, and a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="5af49-356">Para guardar el modelo como un archivo ZIP, creará `FileStream` inmediatamente antes de llamar al método `SaveTo`.</span><span class="sxs-lookup"><span data-stu-id="5af49-356">To save the model as a zip file, you'll create the `FileStream` immediately before calling the `SaveTo` method.</span></span> <span data-ttu-id="5af49-357">Agregue el código siguiente al método `SaveModelAsFile` como la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="5af49-357">Add the following code to the `SaveModelAsFile` method as the next line:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#SaveModel)]

<span data-ttu-id="5af49-358">También podría mostrar dónde se escribió el archivo mediante la escritura de un mensaje de consola con `_modelPath`, utilizando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="5af49-358">You could also display where the file was written by writing a console message with the `_modelPath`, using the following code:</span></span>

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="deploy-and-predict-with-a-loaded-model"></a><span data-ttu-id="5af49-359">Implementar y predecir con un modelo cargado</span><span class="sxs-lookup"><span data-stu-id="5af49-359">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="5af49-360">Agregue una llamada al método nuevo desde el método `Main`, justo debajo de la llamada al método `Evaluate`, utilizando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="5af49-360">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallPredictIssue](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallPredictIssue)]

<span data-ttu-id="5af49-361">Cree el método `PredictIssue`, justo después del método `Evaluate` (y justo antes del método `SaveModelAsFile`) con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="5af49-361">Create the `PredictIssue` method, just after the `Evaluate` method (and just before the `SaveModelAsFile` method), using the following code:</span></span>

```csharp
private static void PredictIssue()
{

}
```

<span data-ttu-id="5af49-362">El método `PredictIssue` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="5af49-362">The `PredictIssue` method executes the following tasks:</span></span>

* <span data-ttu-id="5af49-363">Crea un único problema de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="5af49-363">Creates a single issue of test data.</span></span>
* <span data-ttu-id="5af49-364">Predice el área según los datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="5af49-364">Predicts Area based on test data.</span></span>
* <span data-ttu-id="5af49-365">Combina datos de prueba y predicciones para la generación de informes.</span><span class="sxs-lookup"><span data-stu-id="5af49-365">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="5af49-366">Muestra los resultados de la predicción.</span><span class="sxs-lookup"><span data-stu-id="5af49-366">Displays the predicted results.</span></span>

<span data-ttu-id="5af49-367">En primer lugar, cargue el modelo que ha guardado anteriormente con el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="5af49-367">First, load the model that you saved previously with the following code:</span></span>

[!code-csharp[LoadModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadModel)]

<span data-ttu-id="5af49-368">Agregue un problema de GitHub para probar la predicción del modelo entrenado en el método `Predict` mediante la creación de una instancia de `GitHubIssue`:</span><span class="sxs-lookup"><span data-stu-id="5af49-368">Add a GitHub issue to test the trained model's prediction in the `Predict` method by creating an instance of `GitHubIssue`:</span></span>

[!code-csharp[AddTestIssue](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTestIssue)]

[!code-csharp[CreatePredictionEngine](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine)]
  
<span data-ttu-id="5af49-369">Ahora que tiene un modelo, puede usarlo para predecir la etiqueta Área de GitHub de una única instancia de los datos del problema de GitHub.</span><span class="sxs-lookup"><span data-stu-id="5af49-369">Now that you have a model, you can use that to predict the Area GitHub label of a single instance of the GitHub issue data.</span></span> <span data-ttu-id="5af49-370">Para obtener una predicción, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> en los datos.</span><span class="sxs-lookup"><span data-stu-id="5af49-370">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="5af49-371">Los datos de entrada son una cadena y el modelo incluye la caracterización.</span><span class="sxs-lookup"><span data-stu-id="5af49-371">The input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="5af49-372">La canalización está sincronizada durante el entrenamiento y la predicción.</span><span class="sxs-lookup"><span data-stu-id="5af49-372">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="5af49-373">No fue necesario escribir el código de preprocesamiento o caracterización específicamente para las predicciones, y la misma API se encarga de las predicciones por lotes y puntuales.</span><span class="sxs-lookup"><span data-stu-id="5af49-373">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span> <span data-ttu-id="5af49-374">Agregue el código siguiente al método `PredictIssue` para las predicciones:</span><span class="sxs-lookup"><span data-stu-id="5af49-374">Add the following code to the `PredictIssue` method for the predictions:</span></span>

[!code-csharp[PredictIssue](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#PredictIssue)]

### <a name="using-the-loaded-model-for-prediction"></a><span data-ttu-id="5af49-375">Uso del modelo cargado para la predicción</span><span class="sxs-lookup"><span data-stu-id="5af49-375">Using the loaded model for prediction</span></span>

<span data-ttu-id="5af49-376">Muestre `Area` para poder categorizar el problema y actuar en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="5af49-376">Display `Area` in order to categorize the issue and act on it accordingly.</span></span> <span data-ttu-id="5af49-377">Cree una visualización para los resultados mediante el código <xref:System.Console.WriteLine?displayProperty=nameWithType> siguiente:</span><span class="sxs-lookup"><span data-stu-id="5af49-377">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[DisplayResults](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayResults)]

## <a name="results"></a><span data-ttu-id="5af49-378">Resultados</span><span class="sxs-lookup"><span data-stu-id="5af49-378">Results</span></span>

<span data-ttu-id="5af49-379">Los resultados deberían ser similares a los indicados a continuación.</span><span class="sxs-lookup"><span data-stu-id="5af49-379">Your results should be similar to the following.</span></span> <span data-ttu-id="5af49-380">A medida que la canalización procesa, muestra mensajes.</span><span class="sxs-lookup"><span data-stu-id="5af49-380">As the pipeline processes, it displays messages.</span></span> <span data-ttu-id="5af49-381">Puede ver las advertencias o mensajes de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="5af49-381">You may see warnings, or processing messages.</span></span> <span data-ttu-id="5af49-382">Estos mensajes se han quitado de los resultados siguientes para mayor claridad.</span><span class="sxs-lookup"><span data-stu-id="5af49-382">These messages have been removed from the following results for clarity.</span></span>

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

<span data-ttu-id="5af49-383">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="5af49-383">Congratulations!</span></span> <span data-ttu-id="5af49-384">Ya ha creado correctamente un modelo de aprendizaje automático para clasificar y predecir una etiqueta Área de un problema de GitHub.</span><span class="sxs-lookup"><span data-stu-id="5af49-384">You've now successfully built a machine learning model for classifying and predicting an Area label for a GitHub issue.</span></span> <span data-ttu-id="5af49-385">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification).</span><span class="sxs-lookup"><span data-stu-id="5af49-385">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5af49-386">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="5af49-386">Next steps</span></span>

<span data-ttu-id="5af49-387">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="5af49-387">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="5af49-388">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="5af49-388">Understand the problem</span></span>
> * <span data-ttu-id="5af49-389">Seleccionar el algoritmo de aprendizaje automático adecuado</span><span class="sxs-lookup"><span data-stu-id="5af49-389">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="5af49-390">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="5af49-390">Prepare your data</span></span>
> * <span data-ttu-id="5af49-391">Transformar los datos</span><span class="sxs-lookup"><span data-stu-id="5af49-391">Transform the data</span></span>
> * <span data-ttu-id="5af49-392">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="5af49-392">Train the model</span></span>
> * <span data-ttu-id="5af49-393">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="5af49-393">Evaluate the model</span></span>
> * <span data-ttu-id="5af49-394">Predecir con el modelo entrenado</span><span class="sxs-lookup"><span data-stu-id="5af49-394">Predict with the trained model</span></span>
> * <span data-ttu-id="5af49-395">Implementar y predecir con un modelo cargado</span><span class="sxs-lookup"><span data-stu-id="5af49-395">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="5af49-396">Siga con el siguiente tutorial para obtener más información</span><span class="sxs-lookup"><span data-stu-id="5af49-396">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="5af49-397">Predictor de tarifa de taxi</span><span class="sxs-lookup"><span data-stu-id="5af49-397">Taxi Fare Predictor</span></span>](taxi-fare.md)
