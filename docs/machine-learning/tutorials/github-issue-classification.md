---
title: 'Tutorial: Clasificación de incidencias de soporte técnico (clasificación multiclase)'
description: Descubra cómo usar ML.NET en un escenario de clasificación multiclase para clasificar los problemas de GitHub y asignarlos a un área determinada.
ms.date: 07/31/2019
ms.topic: tutorial
ms.custom: mvc, title-hack-0516
ms.openlocfilehash: 3bb556cc591ee35fc14c548e7f53bad58a786e99
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "68710303"
---
# <a name="tutorial-categorize-support-issues-using-multiclass-classification-with-ml-net"></a><span data-ttu-id="2d8c6-103">Tutorial: Clasificación multiclase de incidencias de soporte técnico con ML.NET</span><span class="sxs-lookup"><span data-stu-id="2d8c6-103">Tutorial: Categorize support issues using multiclass classification with ML .NET</span></span>

<span data-ttu-id="2d8c6-104">Este tutorial de ejemplo ilustra el uso de ML.NET para crear un clasificador de problemas de GitHub para entrenar un modelo que clasifica y predice la etiqueta de área para un problema de GitHub a través de una aplicación de consola de .NET Core con C# en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-104">This sample tutorial illustrates using ML.NET to create a GitHub issue classifier to train a model that classifies and predicts the Area label for a GitHub issue via a .NET Core console application using C# in Visual Studio.</span></span>

<span data-ttu-id="2d8c6-105">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="2d8c6-106">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="2d8c6-106">Prepare your data</span></span>
> * <span data-ttu-id="2d8c6-107">Transformar los datos</span><span class="sxs-lookup"><span data-stu-id="2d8c6-107">Transform the data</span></span>
> * <span data-ttu-id="2d8c6-108">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="2d8c6-108">Train the model</span></span>
> * <span data-ttu-id="2d8c6-109">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="2d8c6-109">Evaluate the model</span></span>
> * <span data-ttu-id="2d8c6-110">Predecir con el modelo entrenado</span><span class="sxs-lookup"><span data-stu-id="2d8c6-110">Predict with the trained model</span></span>
> * <span data-ttu-id="2d8c6-111">Implementar y predecir con un modelo cargado</span><span class="sxs-lookup"><span data-stu-id="2d8c6-111">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="2d8c6-112">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification).</span><span class="sxs-lookup"><span data-stu-id="2d8c6-112">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2d8c6-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2d8c6-113">Prerequisites</span></span>

* <span data-ttu-id="2d8c6-114">[Visual Studio 2017 15.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-114">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* <span data-ttu-id="2d8c6-115">[Archivo de problemas de GitHub delimitado por pestañas (issues_train.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv).</span><span class="sxs-lookup"><span data-stu-id="2d8c6-115">The [Github issues tab separated file (issues_train.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv).</span></span>
* <span data-ttu-id="2d8c6-116">[Prueba de problemas de GitHub delimitado por pestañas (issues_test.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv).</span><span class="sxs-lookup"><span data-stu-id="2d8c6-116">The [Github issues test tab separated file (issues_test.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="2d8c6-117">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="2d8c6-117">Create a console application</span></span>

### <a name="create-a-project"></a><span data-ttu-id="2d8c6-118">Crear un proyecto</span><span class="sxs-lookup"><span data-stu-id="2d8c6-118">Create a project</span></span>

1. <span data-ttu-id="2d8c6-119">Abra Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-119">Open Visual Studio 2017.</span></span> <span data-ttu-id="2d8c6-120">Seleccione **Archivo** > **Nuevo** > **Proyecto** de la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-120">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="2d8c6-121">En el cuadro de diálogo **Nuevo proyecto**, seleccione el nodo **Visual C#** seguido del nodo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-121">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="2d8c6-122">Después, seleccione la plantilla del proyecto **Aplicación de consola (.NET Core)** .</span><span class="sxs-lookup"><span data-stu-id="2d8c6-122">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="2d8c6-123">En el cuadro de texto **Nombre**, escriba "GitHubIssueClassification" y, luego, seleccione el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-123">In the **Name** text box, type "GitHubIssueClassification" and then select the **OK** button.</span></span>

2. <span data-ttu-id="2d8c6-124">Cree un directorio denominado *Datos* en el proyecto para guardar los archivos del conjunto de datos:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-124">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="2d8c6-125">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **Nueva carpeta**.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-125">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="2d8c6-126">Escriba "Datos" y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-126">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="2d8c6-127">En el proyecto, cree un directorio denominado *Modelos* para guardar el modelo:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-127">Create a directory named *Models* in your project to save your model:</span></span>

    <span data-ttu-id="2d8c6-128">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **Nueva carpeta**.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-128">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="2d8c6-129">Escriba "Modelos" y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-129">Type "Models" and hit Enter.</span></span>

4. <span data-ttu-id="2d8c6-130">Instale el **paquete NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-130">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="2d8c6-131">En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-131">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="2d8c6-132">Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.ML**, seleccione el paquete **v 1.0.0** en la lista de paquetes y seleccione el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-132">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select the **v 1.0.0** package in the list, and select the **Install** button.</span></span> <span data-ttu-id="2d8c6-133">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-133">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="2d8c6-134">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="2d8c6-134">Prepare your data</span></span>

1. <span data-ttu-id="2d8c6-135">Descargue los conjuntos de datos [issues_train.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) e [issues_test.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) y guárdelos en la carpeta *Datos* que ha creado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-135">Download the [issues_train.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) and the [issues_test.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) data sets and save them to the *Data* folder previously created.</span></span> <span data-ttu-id="2d8c6-136">El primer conjunto de datos entrena el modelo de aprendizaje automático y el segundo puede usarse para evaluar su grado de precisión.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-136">The first dataset trains the machine learning model and the second can be used to evaluate how accurate your model is.</span></span>

2. <span data-ttu-id="2d8c6-137">En el Explorador de soluciones, haga clic con el botón secundario en cada uno de los archivos \*.tsv y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-137">In Solution Explorer, right-click each of the \*.tsv files and select **Properties**.</span></span> <span data-ttu-id="2d8c6-138">En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-138">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="2d8c6-139">Crear clases y definir rutas de acceso</span><span class="sxs-lookup"><span data-stu-id="2d8c6-139">Create classes and define paths</span></span>

<span data-ttu-id="2d8c6-140">Agregue las siguientes instrucciones `using` adicionales a la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-140">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddUsings)]

<span data-ttu-id="2d8c6-141">Cree tres campos globales para contener las rutas de acceso a los archivos descargados recientemente y variables globales para `MLContext`,`DataView` y `PredictionEngine`:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-141">Create three global fields to hold the paths to the recently downloaded files, and global variables for the `MLContext`,`DataView`, and `PredictionEngine`:</span></span>

* <span data-ttu-id="2d8c6-142">`_trainDataPath` tiene la ruta de acceso al conjunto de datos utilizado para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-142">`_trainDataPath` has the path to the dataset used to train the model.</span></span>
* <span data-ttu-id="2d8c6-143">`_testDataPath` tiene la ruta de acceso al conjunto de datos utilizado para evaluar el modelo.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-143">`_testDataPath` has the path to the dataset used to evaluate the model.</span></span>
* <span data-ttu-id="2d8c6-144">`_modelPath` tiene la ruta de acceso donde se guarda el modelo entrenado.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-144">`_modelPath` has the path where the trained model is saved.</span></span>
* <span data-ttu-id="2d8c6-145">`_mlContext` es el elemento <xref:Microsoft.ML.MLContext> que proporciona el contexto de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-145">`_mlContext` is the <xref:Microsoft.ML.MLContext> that provides processing context.</span></span>
* <span data-ttu-id="2d8c6-146">`_trainingDataView` es el elemento <xref:Microsoft.ML.IDataView> que se usa para procesar el conjunto de datos de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-146">`_trainingDataView` is the <xref:Microsoft.ML.IDataView> used to process the training dataset.</span></span>
* <span data-ttu-id="2d8c6-147">`_predEngine` es el elemento <xref:Microsoft.ML.PredictionEngine%602> que se usa para las predicciones únicas.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-147">`_predEngine` is the <xref:Microsoft.ML.PredictionEngine%602> used for single predictions.</span></span>

<span data-ttu-id="2d8c6-148">Agregue el código siguiente a la línea justo encima del método `Main` para especificar esas rutas de acceso y otras variables:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-148">Add the following code to the line right above the `Main` method to specify those paths and the other variables:</span></span>

[!code-csharp[DeclareGlobalVariables](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DeclareGlobalVariables)]

<span data-ttu-id="2d8c6-149">Cree algunas clases para los datos de entrada y las predicciones.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-149">Create some classes for your input data and predictions.</span></span> <span data-ttu-id="2d8c6-150">Agregue una nueva clase a su proyecto:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-150">Add a new class to your project:</span></span>

1. <span data-ttu-id="2d8c6-151">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-151">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="2d8c6-152">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *GitHubIssueData.cs*.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-152">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *GitHubIssueData.cs*.</span></span> <span data-ttu-id="2d8c6-153">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-153">Then, select the **Add** button.</span></span>

    <span data-ttu-id="2d8c6-154">Se abre el archivo *GitHubIssueData.cs* en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-154">The *GitHubIssueData.cs* file opens in the code editor.</span></span> <span data-ttu-id="2d8c6-155">Agregue la siguiente instrucción `using` a la parte superior de *GitHubIssueData.cs*:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-155">Add the following `using` statement to the top of *GitHubIssueData.cs*:</span></span>

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#AddUsings)]

<span data-ttu-id="2d8c6-156">Quite la definición de clase existente y agregue el código siguiente, que tiene dos clases `GitHubIssue` y `IssuePrediction`, al archivo *GitHubIssueData.cs*:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-156">Remove the existing class definition and add the following code, which has two classes `GitHubIssue` and `IssuePrediction`, to the *GitHubIssueData.cs* file:</span></span>

[!code-csharp[DeclareGlobalVariables](~/samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#DeclareTypes)]

<span data-ttu-id="2d8c6-157">`label` es la columna que quiere predecir.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-157">The `label` is the column you want to predict.</span></span> <span data-ttu-id="2d8c6-158">Los valores de `Features` identificados son las entradas que se proporcionan al modelo para predecir la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-158">The identified `Features` are the inputs you give the model to predict the Label.</span></span>

<span data-ttu-id="2d8c6-159">Use [LoadColumnAttribute](xref:Microsoft.ML.Data.LoadColumnAttribute) para especificar los índices de las columnas de origen en el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-159">Use the [LoadColumnAttribute](xref:Microsoft.ML.Data.LoadColumnAttribute) to specify the indices of the source columns in the data set.</span></span>

<span data-ttu-id="2d8c6-160">`GitHubIssue` es la clase de conjunto de datos de entrada y contiene los siguientes campos de <xref:System.String>:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-160">`GitHubIssue` is the input dataset class and has the following <xref:System.String> fields:</span></span>

* <span data-ttu-id="2d8c6-161">`ID`, la primera columna (id. de problema de GitHub).</span><span class="sxs-lookup"><span data-stu-id="2d8c6-161">the first column `ID` (GitHub Issue ID)</span></span>
* <span data-ttu-id="2d8c6-162">`Area`, la segunda columna (la predicción para el entrenamiento).</span><span class="sxs-lookup"><span data-stu-id="2d8c6-162">the second column `Area` (the prediction for training)</span></span>
* <span data-ttu-id="2d8c6-163">`Title`, la tercera columna (título del problema de GitHub) es el primer `feature` usado para predecir el `Area`</span><span class="sxs-lookup"><span data-stu-id="2d8c6-163">the third column `Title` (GitHub issue title) is the first `feature` used for predicting the `Area`</span></span>
* <span data-ttu-id="2d8c6-164">`Description`, la cuarta columna es el segundo `feature` usado para predecir el `Area`</span><span class="sxs-lookup"><span data-stu-id="2d8c6-164">the fourth column  `Description` is the second `feature` used for predicting the `Area`</span></span>

<span data-ttu-id="2d8c6-165">`IssuePrediction` es la clase usada para la predicción una vez entrenado el modelo.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-165">`IssuePrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="2d8c6-166">Tiene un solo elemento `string` (`Area`) y un atributo `PredictedLabel` `ColumnName`.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-166">It has a single `string` (`Area`) and a `PredictedLabel` `ColumnName` attribute.</span></span>  <span data-ttu-id="2d8c6-167">`PredictedLabel` se usa durante la predicción y la evaluación.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-167">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="2d8c6-168">Para la evaluación, se utiliza una entrada con los datos de entrenamiento, los valores de predicción y el modelo.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-168">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="2d8c6-169">Todas las operaciones de ML.NET se inician en la clase [MLContext](xref:Microsoft.ML.MLContext).</span><span class="sxs-lookup"><span data-stu-id="2d8c6-169">All ML.NET operations start in the [MLContext](xref:Microsoft.ML.MLContext) class.</span></span> <span data-ttu-id="2d8c6-170">La inicialización de `mlContext` crea un entorno de ML.NET que se puede compartir entre los objetos del flujo de trabajo de creación de modelos.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-170">Initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="2d8c6-171">Es similar, conceptualmente, al `DBContext` en `Entity Framework`.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-171">It's similar, conceptually, to `DBContext` in `Entity Framework`.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="2d8c6-172">Inicializar variables en Main</span><span class="sxs-lookup"><span data-stu-id="2d8c6-172">Initialize variables in Main</span></span>

<span data-ttu-id="2d8c6-173">Inicialice la variante global `_mlContext` con una nueva instancia de `MLContext` usando una inicialización aleatoria (`seed: 0`) para obtener resultados repetibles o deterministas en varios entrenamientos.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-173">Initialize the `_mlContext` global variable  with a new instance of `MLContext` with a random seed (`seed: 0`) for repeatable/deterministic results across multiple trainings.</span></span>  <span data-ttu-id="2d8c6-174">Reemplace la línea `Console.WriteLine("Hello World!")` por el código siguiente en el método `Main`:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-174">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateMLContext)]

## <a name="load-the-data"></a><span data-ttu-id="2d8c6-175">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="2d8c6-175">Load the data</span></span>

<span data-ttu-id="2d8c6-176">ML.NET utiliza la [clase IDataView](xref:Microsoft.ML.IDataView) como una forma flexible y eficiente de describir datos tabulares de texto o numéricos.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-176">ML.NET uses the [IDataView class](xref:Microsoft.ML.IDataView) as a flexible, efficient way of describing numeric or text tabular data.</span></span> <span data-ttu-id="2d8c6-177">`IDataView` puede cargar archivos de texto o en tiempo real (por ejemplo, una base de datos SQL o archivos de registro).</span><span class="sxs-lookup"><span data-stu-id="2d8c6-177">`IDataView` can load either text files or in real time (for example, SQL database or log files).</span></span>

<span data-ttu-id="2d8c6-178">Para inicializar y cargar la variable global `_trainingDataView` con el fin de volver a usarla para la canalización, agregue el siguiente código después de la inicialización de `mlContext`:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-178">To initialize and load the `_trainingDataView` global variable in order to use it for the pipeline, add the following code after the  `mlContext` initialization:</span></span>

[!code-csharp[LoadTrainData](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTrainData)]

<span data-ttu-id="2d8c6-179">[LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) define el esquema de datos y lee en el archivo.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-179">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) defines the data schema and reads in the file.</span></span> <span data-ttu-id="2d8c6-180">Toma las variables de ruta de acceso de datos y devuelve `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-180">It takes in the data path variables and returns an `IDataView`.</span></span>

<span data-ttu-id="2d8c6-181">Agregue lo siguiente como la siguiente línea de código en el método `Main`:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-181">Add the following as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallProcessData](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallProcessData)]

<span data-ttu-id="2d8c6-182">El método `ProcessData` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-182">The `ProcessData` method executes the following tasks:</span></span>

* <span data-ttu-id="2d8c6-183">Extrae y transforma los datos.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-183">Extracts and transforms the data.</span></span>
* <span data-ttu-id="2d8c6-184">Devuelve la canalización de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-184">Returns the processing pipeline.</span></span>

<span data-ttu-id="2d8c6-185">Cree el método `ProcessData`, justo después del método `Main`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-185">Create the `ProcessData` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static IEstimator<ITransformer> ProcessData()
{

}
```

## <a name="extract-features-and-transform-the-data"></a><span data-ttu-id="2d8c6-186">Extraer características y transformar los datos</span><span class="sxs-lookup"><span data-stu-id="2d8c6-186">Extract Features and transform the data</span></span>

<span data-ttu-id="2d8c6-187">Como quiere predecir la etiqueta de GitHub de área para un `GitHubIssue`, utilice el método [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) para transformar la columna `Area` en una columna `Label` de tipo de clave numérico (un formato admitido por los algoritmos de clasificación) y agréguela como nueva columna de conjunto de datos:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-187">As you want to predict the Area GitHub label for a `GitHubIssue`, use the [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) method to transform the `Area` column into a numeric key type `Label` column (a format accepted by classification algorithms) and add it as a new dataset column:</span></span>

[!code-csharp[MapValueToKey](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#MapValueToKey)]

<span data-ttu-id="2d8c6-188">A continuación, llame a `mlContext.Transforms.Text.FeaturizeText` que transforma las columnas de texto (`Title` y `Description`) en un vector numérico para cada una de nombre `TitleFeaturized` y `DescriptionFeaturized`.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-188">Next, call `mlContext.Transforms.Text.FeaturizeText` which transforms the text (`Title` and `Description`) columns into a numeric vector for each called `TitleFeaturized` and `DescriptionFeaturized`.</span></span> <span data-ttu-id="2d8c6-189">Anexe la caracterización para ambas columnas a la canalización usando el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-189">Append the featurization for both columns to the pipeline with the following code:</span></span>

[!code-csharp[FeaturizeText](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#FeaturizeText)]

<span data-ttu-id="2d8c6-190">El último paso de preparación de datos combina todas las columnas de característica en la columna **Características** con el método [Concatenate()](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate%2A).</span><span class="sxs-lookup"><span data-stu-id="2d8c6-190">The last step in data preparation combines all of the feature columns into the **Features** column using the [Concatenate()](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate%2A) method.</span></span> <span data-ttu-id="2d8c6-191">De forma predeterminada, un algoritmo de aprendizaje solo procesa las características de la columna **Features**.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-191">By default, a learning algorithm processes only features from the **Features** column.</span></span> <span data-ttu-id="2d8c6-192">Anexe esta transformación a la canalización usando el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-192">Append this transformation to the pipeline with the following code:</span></span>

[!code-csharp[Concatenate](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Concatenate)]

 <span data-ttu-id="2d8c6-193">A continuación, anexe <xref:Microsoft.ML.Data.EstimatorChain%601.AppendCacheCheckpoint%2A> para almacenar en caché el objeto DataView, de modo que pueda obtener un mayor rendimiento al iterar los datos varias veces con la caché, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-193">Next, append a <xref:Microsoft.ML.Data.EstimatorChain%601.AppendCacheCheckpoint%2A> to cache the DataView so when you iterate over the data multiple times using the cache might get better performance, as with the following code:</span></span>

[!code-csharp[AppendCache](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AppendCache)]

> [!WARNING]
> <span data-ttu-id="2d8c6-194">Use AppendCacheCheckpoint para conjuntos de datos pequeños o medianos para reducir el tiempo de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-194">Use AppendCacheCheckpoint for small/medium datasets to lower training time.</span></span> <span data-ttu-id="2d8c6-195">NO lo use (quite. AppendCacheCheckpoint()) al tratar con grandes conjuntos de datos.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-195">Do NOT use it (remove .AppendCacheCheckpoint()) when handling very large datasets.</span></span>

<span data-ttu-id="2d8c6-196">Devuelva la canalización al final del método `ProcessData`.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-196">Return the pipeline at the end of the `ProcessData` method.</span></span>

[!code-csharp[ReturnPipeline](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnPipeline)]

<span data-ttu-id="2d8c6-197">En este paso se controla el preprocesamiento y la caracterización.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-197">This step handles preprocessing/featurization.</span></span> <span data-ttu-id="2d8c6-198">El uso de componentes adicionales disponibles en ML.NET permite conseguir mejores resultados con el modelo.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-198">Using additional components available in ML.NET can enable better results with your model.</span></span>

## <a name="build-and-train-the-model"></a><span data-ttu-id="2d8c6-199">Creación y entrenamiento del modelo</span><span class="sxs-lookup"><span data-stu-id="2d8c6-199">Build and train the model</span></span>

<span data-ttu-id="2d8c6-200">Agregue la siguiente llamada al método `BuildAndTrainModel` como siguiente línea de código del método `Main`:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-200">Add the following call to the `BuildAndTrainModel`method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallBuildAndTrainModel](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallBuildAndTrainModel)]

<span data-ttu-id="2d8c6-201">El método `BuildAndTrainModel` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-201">The `BuildAndTrainModel` method executes the following tasks:</span></span>

* <span data-ttu-id="2d8c6-202">Crea la clase de algoritmo de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-202">Creates the training algorithm class.</span></span>
* <span data-ttu-id="2d8c6-203">Entrena el modelo.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-203">Trains the model.</span></span>
* <span data-ttu-id="2d8c6-204">Predice el área según los datos de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-204">Predicts area based on training data.</span></span>
* <span data-ttu-id="2d8c6-205">Devuelve el modelo.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-205">Returns the model.</span></span>

<span data-ttu-id="2d8c6-206">Cree el método `BuildAndTrainModel`, justo después del método `Main`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-206">Create the `BuildAndTrainModel` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static IEstimator<ITransformer> BuildAndTrainModel(IDataView trainingDataView, IEstimator<ITransformer> pipeline)
{

}
```

### <a name="about-the-classification-task"></a><span data-ttu-id="2d8c6-207">Acerca de la tarea de clasificación</span><span class="sxs-lookup"><span data-stu-id="2d8c6-207">About the classification task</span></span>

<span data-ttu-id="2d8c6-208">La clasificación es una tarea de aprendizaje automático que usa datos para **determinar** la categoría, el tipo o la clase de un elemento o fila de datos y suele ser uno de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-208">Classification is a machine learning task that uses data to **determine** the category, type, or class of an item or row of data and is frequently one of the following types:</span></span>

* <span data-ttu-id="2d8c6-209">Binario: A o B.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-209">Binary: either A or B.</span></span>
* <span data-ttu-id="2d8c6-210">Multiclase: varias categorías que se pueden predecir mediante el uso de un único modelo.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-210">Multiclass: multiple categories that can be predicted by using a single model.</span></span>

<span data-ttu-id="2d8c6-211">Para este tipo de problema, use un algoritmo de aprendizaje de clasificación multiclase, ya que la predicción de categoría de problema puede ser una de varias categorías (multiclase) en lugar de solo dos (binaria).</span><span class="sxs-lookup"><span data-stu-id="2d8c6-211">For this type of problem, use a Multiclass classification learning algorithm, since your issue category prediction can be one of multiple categories (multiclass) rather than just two (binary).</span></span>

<span data-ttu-id="2d8c6-212">Anexe el algoritmo de aprendizaje automático a las definiciones de transformación de datos agregando lo siguiente como primera línea de código en `BuildAndTrainModel()`:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-212">Append the machine learning algorithm to the data transformation definitions by adding the following as the first line of code in `BuildAndTrainModel()`:</span></span>

[!code-csharp[AddTrainer](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTrainer)]

<span data-ttu-id="2d8c6-213">[SdcaMaximumEntropy](xref:Microsoft.ML.Trainers.SdcaMaximumEntropyMulticlassTrainer) es el algoritmo de entrenamiento de clasificación multiclase.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-213">The [SdcaMaximumEntropy](xref:Microsoft.ML.Trainers.SdcaMaximumEntropyMulticlassTrainer) is your multiclass classification training algorithm.</span></span> <span data-ttu-id="2d8c6-214">Se anexa a `pipeline` y acepta `Title` y `Description` (`Features`) caracterizados y los parámetros de entrada `Label` para aprender de los datos históricos.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-214">This is appended to the `pipeline` and accepts the featurized `Title` and `Description` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span>

### <a name="train-the-model"></a><span data-ttu-id="2d8c6-215">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="2d8c6-215">Train the model</span></span>

<span data-ttu-id="2d8c6-216">Ajuste el modelo a los datos `splitTrainSet` y devuelva el modelo entrenado. Para ello, agregue lo que se indica a continuación como la siguiente línea de código en el método `BuildAndTrainModel()`:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-216">Fit the model to the `splitTrainSet` data and return the trained model by adding the following as the next line of code in the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[TrainModel](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#TrainModel)]

<span data-ttu-id="2d8c6-217">El método `Fit()` entrena el modelo transformando el conjunto de datos y aplicando el entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-217">The `Fit()`method trains your model by transforming the dataset and applying the training.</span></span>

<span data-ttu-id="2d8c6-218">[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) es una API de conveniencia, que le permite pasar datos y luego realizar una predicción en una única instancia de datos.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-218">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to pass in and then perform a prediction on a single instance of data.</span></span> <span data-ttu-id="2d8c6-219">Agregue esto como siguiente línea en el método `BuildAndTrainModel()`:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-219">Add this as the next line in the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[CreatePredictionEngine1](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine1)]

### <a name="predict-with-the-trained-model"></a><span data-ttu-id="2d8c6-220">Predecir con el modelo entrenado</span><span class="sxs-lookup"><span data-stu-id="2d8c6-220">Predict with the trained model</span></span>

<span data-ttu-id="2d8c6-221">Agregue un problema de GitHub para probar la predicción del modelo entrenado en el método `Predict` mediante la creación de una instancia de `GitHubIssue`:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-221">Add a GitHub issue to test the trained model's prediction in the `Predict` method by creating an instance of `GitHubIssue`:</span></span>

[!code-csharp[CreateTestIssue1](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateTestIssue1)]

<span data-ttu-id="2d8c6-222">El uso de la función [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) realiza una predicción en una sola fila de datos:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-222">Use the [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single row of data:</span></span>

[!code-csharp[Predict](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Predict)]

### <a name="using-the-model-prediction-results"></a><span data-ttu-id="2d8c6-223">Uso del modelo: resultados de la predicción</span><span class="sxs-lookup"><span data-stu-id="2d8c6-223">Using the model: prediction results</span></span>

<span data-ttu-id="2d8c6-224">Muestre `GitHubIssue` y la predicción de la etiqueta `Area` correspondiente para compartir los resultados y actuar en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-224">Display `GitHubIssue` and corresponding `Area` label prediction in order to share the results and act on them accordingly.</span></span>  <span data-ttu-id="2d8c6-225">Cree una visualización para los resultados mediante el código <xref:System.Console.WriteLine?displayProperty=nameWithType> siguiente:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-225">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputPrediction](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#OutputPrediction)]

### <a name="return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="2d8c6-226">Devolución del modelo entrenado para su uso para la evaluación</span><span class="sxs-lookup"><span data-stu-id="2d8c6-226">Return the model trained to use for evaluation</span></span>

<span data-ttu-id="2d8c6-227">Devuelva el modelo al final del método `BuildAndTrainModel`.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-227">Return the model at the end of the `BuildAndTrainModel` method.</span></span>

[!code-csharp[ReturnModel](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnModel)]

## <a name="evaluate-the-model"></a><span data-ttu-id="2d8c6-228">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="2d8c6-228">Evaluate the model</span></span>

<span data-ttu-id="2d8c6-229">Ahora que ha creado y entrenado el modelo, debe evaluarlo con otro conjunto de datos para el control de calidad y la validación.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-229">Now that you've created and trained the model, you need to evaluate it with a different dataset for quality assurance and validation.</span></span> <span data-ttu-id="2d8c6-230">En el método `Evaluate`, el modelo creado en `BuildAndTrainModel` se pasa para ser evaluado.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-230">In the `Evaluate` method, the model created in `BuildAndTrainModel` is passed in to be evaluated.</span></span> <span data-ttu-id="2d8c6-231">Cree el método `Evaluate`, justo después de `BuildAndTrainModel`, como en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-231">Create the `Evaluate` method, just after `BuildAndTrainModel`, as in the following code:</span></span>

```csharp
public static void Evaluate(DataViewSchema trainingDataViewSchema)
{

}
```

<span data-ttu-id="2d8c6-232">El método `Evaluate` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-232">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="2d8c6-233">Carga el conjunto de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-233">Loads the test dataset.</span></span>
* <span data-ttu-id="2d8c6-234">Crea el evaluador multiclase.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-234">Creates the multiclass evaluator.</span></span>
* <span data-ttu-id="2d8c6-235">Evalúa el modelo y crea métricas.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-235">Evaluates the model and create metrics.</span></span>
* <span data-ttu-id="2d8c6-236">Muestra las métricas.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-236">Displays the metrics.</span></span>

<span data-ttu-id="2d8c6-237">Agregue una llamada al método nuevo desde el método `Main`, justo debajo de la llamada al método `BuildAndTrainModel`, utilizando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-237">Add a call to the new method from the `Main` method, right under the `BuildAndTrainModel` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallEvaluate)]

<span data-ttu-id="2d8c6-238">Como hizo anteriormente con el conjunto de datos de entrenamiento, cargue el conjunto de datos de prueba agregando el código siguiente al método `Evaluate`:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-238">As you did previously with the training dataset, load the test dataset by adding the following code to the `Evaluate` method:</span></span>

[!code-csharp[LoadTestDataset](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTestDataset)]

<span data-ttu-id="2d8c6-239">El método [Evaluate()](xref:Microsoft.ML.MulticlassClassificationCatalog.Evaluate%2A) calcula las métricas de calidad del modelo utilizando el conjunto de datos especificado.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-239">The [Evaluate()](xref:Microsoft.ML.MulticlassClassificationCatalog.Evaluate%2A) method computes the quality metrics for the model using the specified dataset.</span></span> <span data-ttu-id="2d8c6-240">Devuelve un objeto <xref:Microsoft.ML.Data.MulticlassClassificationMetrics> que contiene las métricas totales calculadas por evaluadores de clasificación multiclase.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-240">It returns a <xref:Microsoft.ML.Data.MulticlassClassificationMetrics> object that contains the overall metrics computed by multiclass classification evaluators.</span></span>
<span data-ttu-id="2d8c6-241">Para mostrar las métricas a fin de determinar la calidad del modelo, primero tendrá que obtenerlas.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-241">To display the metrics to determine the quality of the model, you need to get them first.</span></span>
<span data-ttu-id="2d8c6-242">Observe el uso del método [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) de la variable global `_trainedModel` de aprendizaje automático (una [ITransformer](xref:Microsoft.ML.ITransformer)) que da entrada a las características y devuelve predicciones.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-242">Notice the use of the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method of the machine learning `_trainedModel` global variable (an [ITransformer](xref:Microsoft.ML.ITransformer)) to input the features and return predictions.</span></span> <span data-ttu-id="2d8c6-243">Agregue el código siguiente al método `Evaluate` como la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-243">Add the following code to the `Evaluate` method as the next line:</span></span>

[!code-csharp[Evaluate](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Evaluate)]

<span data-ttu-id="2d8c6-244">Las siguientes métricas se evalúan para la clasificación multiclase:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-244">The following metrics are evaluated for multiclass classification:</span></span>

* <span data-ttu-id="2d8c6-245">Microprecisión: todos los pares de ejemplo y clase contribuyen del mismo modo a la métrica de precisión.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-245">Micro Accuracy - Every sample-class pair contributes equally to the accuracy metric.</span></span>  <span data-ttu-id="2d8c6-246">Le recomendamos que la microprecisión esté lo más cerca posible de 1.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-246">You want Micro Accuracy to be as close to 1 as possible.</span></span>

* <span data-ttu-id="2d8c6-247">Macroprecisión: todas las clases contribuyen del mismo modo a la métrica de precisión.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-247">Macro Accuracy - Every class contributes equally to the accuracy metric.</span></span> <span data-ttu-id="2d8c6-248">Las clases minoritarias tienen el mismo peso que las clases más grandes.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-248">Minority classes are given equal weight as the larger classes.</span></span> <span data-ttu-id="2d8c6-249">Le recomendamos que la macroprecisión esté lo más cerca posible de 1.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-249">You want Macro Accuracy to be as close to 1 as possible.</span></span>

* <span data-ttu-id="2d8c6-250">Pérdida de registro: vea [Pérdida de registro](../resources/glossary.md#log-loss).</span><span class="sxs-lookup"><span data-stu-id="2d8c6-250">Log-loss - see [Log Loss](../resources/glossary.md#log-loss).</span></span> <span data-ttu-id="2d8c6-251">Le recomendamos que la pérdida logarítmica esté lo más cerca posible de 0.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-251">You want Log-loss to be as close to zero as possible.</span></span>

* <span data-ttu-id="2d8c6-252">Reducción de la pérdida de registro: parte de [-inf, 100], donde 100 equivale a una predicción perfecta, y 0 indica una predicción aproximada.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-252">Log-loss reduction - Ranges from [-inf, 100], where 100 is perfect predictions and 0 indicates mean predictions.</span></span> <span data-ttu-id="2d8c6-253">Le recomendamos que la reducción de la pérdida de registro esté lo más cerca posible de 0.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-253">You want Log-loss reduction to be as close to zero as possible.</span></span>

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="2d8c6-254">Mostrar las métricas para la validación del modelo</span><span class="sxs-lookup"><span data-stu-id="2d8c6-254">Displaying the metrics for model validation</span></span>

<span data-ttu-id="2d8c6-255">Utilice el código siguiente para mostrar las métricas, compartir los resultados y, a continuación, trabajar con ellos:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-255">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayMetrics)]

### <a name="save-the-model-to-a-file"></a><span data-ttu-id="2d8c6-256">Guardar el modelo en un archivo</span><span class="sxs-lookup"><span data-stu-id="2d8c6-256">Save the model to a file</span></span>

<span data-ttu-id="2d8c6-257">Una vez que esté satisfecho con el modelo, guárdelo en un archivo para hacer predicciones más adelante o en otra aplicación.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-257">Once satisfied with your model, save it to a file to make predictions at a later time or in another application.</span></span> <span data-ttu-id="2d8c6-258">Agregue el código siguiente al método `Evaluate` .</span><span class="sxs-lookup"><span data-stu-id="2d8c6-258">Add the following code to the `Evaluate` method.</span></span> 

[!code-csharp[SnippetCallSaveModel](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#SnippetCallSaveModel)]

<span data-ttu-id="2d8c6-259">Cree el método `SaveModelAsFile` debajo del método `Evaluate`.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-259">Create the `SaveModelAsFile` method below your `Evaluate` method.</span></span>

```csharp
private static void SaveModelAsFile(MLContext mlContext,DataViewSchema trainingDataViewSchema, ITransformer model)
{

}
```

<span data-ttu-id="2d8c6-260">Agregue el código siguiente al método `SaveModelAsFile`.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-260">Add the following code to your `SaveModelAsFile` method.</span></span> <span data-ttu-id="2d8c6-261">Este código usa el método [`Save`](xref:Microsoft.ML.ModelOperationsCatalog.Save*) para serializar y almacenar el modelo entrenado como archivo ZIP.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-261">This code uses the [`Save`](xref:Microsoft.ML.ModelOperationsCatalog.Save*) method to serialize and store the trained model as a zip file.</span></span>

[!code-csharp[SnippetSaveModel](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#SnippetSaveModel)]

## <a name="deploy-and-predict-with-a-model"></a><span data-ttu-id="2d8c6-262">Implementación y predicción con un modelo</span><span class="sxs-lookup"><span data-stu-id="2d8c6-262">Deploy and Predict with a model</span></span>

<span data-ttu-id="2d8c6-263">Agregue una llamada al método nuevo desde el método `Main`, justo debajo de la llamada al método `Evaluate`, utilizando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-263">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallPredictIssue](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallPredictIssue)]

<span data-ttu-id="2d8c6-264">Cree el método `PredictIssue`, justo después del método `Evaluate` (y justo antes del método `SaveModelAsFile`) con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-264">Create the `PredictIssue` method, just after the `Evaluate` method (and just before the `SaveModelAsFile` method), using the following code:</span></span>

```csharp
private static void PredictIssue()
{

}
```

<span data-ttu-id="2d8c6-265">El método `PredictIssue` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-265">The `PredictIssue` method executes the following tasks:</span></span>

* <span data-ttu-id="2d8c6-266">Carga el modelo guardado</span><span class="sxs-lookup"><span data-stu-id="2d8c6-266">Loads the saved model</span></span>
* <span data-ttu-id="2d8c6-267">Crea un único problema de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-267">Creates a single issue of test data.</span></span>
* <span data-ttu-id="2d8c6-268">Predice el área según los datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-268">Predicts Area based on test data.</span></span>
* <span data-ttu-id="2d8c6-269">Combina datos de prueba y predicciones para la generación de informes.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-269">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="2d8c6-270">Muestra los resultados de la predicción.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-270">Displays the predicted results.</span></span>

<span data-ttu-id="2d8c6-271">Cargue el modelo guardado en la aplicación agregando el código siguiente al método `PredictIssue`:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-271">Load the saved model into your application by adding the following code to the `PredictIssue` method:</span></span>

[!code-csharp[SnippetLoadModel](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#SnippetLoadModel)]

<span data-ttu-id="2d8c6-272">Agregue un problema de GitHub para probar la predicción del modelo entrenado en el método `Predict` mediante la creación de una instancia de `GitHubIssue`:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-272">Add a GitHub issue to test the trained model's prediction in the `Predict` method by creating an instance of `GitHubIssue`:</span></span>

[!code-csharp[AddTestIssue](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTestIssue)]

<span data-ttu-id="2d8c6-273">Como hizo anteriormente, cree una instancia de `PredictionEngine` con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-273">As you did previously, create a `PredictionEngine` instance with the following code:</span></span>

[!code-csharp[CreatePredictionEngine](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine)]
  
<span data-ttu-id="2d8c6-274">Use `PredictionEngine` para predecir la etiqueta de GitHub de área agregando el código siguiente al método `PredictIssue` para la predicción:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-274">Use the `PredictionEngine` to predict the Area GitHub label by adding the following code to the `PredictIssue` method for the prediction:</span></span>

[!code-csharp[PredictIssue](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#PredictIssue)]

### <a name="using-the-loaded-model-for-prediction"></a><span data-ttu-id="2d8c6-275">Uso del modelo cargado para la predicción</span><span class="sxs-lookup"><span data-stu-id="2d8c6-275">Using the loaded model for prediction</span></span>

<span data-ttu-id="2d8c6-276">Muestre `Area` para poder categorizar el problema y actuar en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-276">Display `Area` in order to categorize the issue and act on it accordingly.</span></span> <span data-ttu-id="2d8c6-277">Cree una visualización para los resultados mediante el código <xref:System.Console.WriteLine?displayProperty=nameWithType> siguiente:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-277">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[DisplayResults](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayResults)]

## <a name="results"></a><span data-ttu-id="2d8c6-278">Resultados</span><span class="sxs-lookup"><span data-stu-id="2d8c6-278">Results</span></span>

<span data-ttu-id="2d8c6-279">Los resultados deberían ser similares a los indicados a continuación.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-279">Your results should be similar to the following.</span></span> <span data-ttu-id="2d8c6-280">A medida que la canalización procesa, muestra mensajes.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-280">As the pipeline processes, it displays messages.</span></span> <span data-ttu-id="2d8c6-281">Puede ver las advertencias o mensajes de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-281">You may see warnings, or processing messages.</span></span> <span data-ttu-id="2d8c6-282">Estos mensajes se han quitado de los resultados siguientes para mayor claridad.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-282">These messages have been removed from the following results for clarity.</span></span>

```console
=============== Single Prediction just-trained-model - Result: area-System.Net ===============
*************************************************************************************************************
*       Metrics for Multi-class Classification model - Test Data
*------------------------------------------------------------------------------------------------------------
*       MicroAccuracy:    0.738
*       MacroAccuracy:    0.668
*       LogLoss:          .919
*       LogLossReduction: .643
*************************************************************************************************************
=============== Single Prediction - Result: area-System.Data ===============
```

<span data-ttu-id="2d8c6-283">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="2d8c6-283">Congratulations!</span></span> <span data-ttu-id="2d8c6-284">Ya ha creado correctamente un modelo de aprendizaje automático para clasificar y predecir una etiqueta Área de un problema de GitHub.</span><span class="sxs-lookup"><span data-stu-id="2d8c6-284">You've now successfully built a machine learning model for classifying and predicting an Area label for a GitHub issue.</span></span> <span data-ttu-id="2d8c6-285">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification).</span><span class="sxs-lookup"><span data-stu-id="2d8c6-285">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2d8c6-286">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="2d8c6-286">Next steps</span></span>

<span data-ttu-id="2d8c6-287">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="2d8c6-287">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="2d8c6-288">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="2d8c6-288">Prepare your data</span></span>
> * <span data-ttu-id="2d8c6-289">Transformar los datos</span><span class="sxs-lookup"><span data-stu-id="2d8c6-289">Transform the data</span></span>
> * <span data-ttu-id="2d8c6-290">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="2d8c6-290">Train the model</span></span>
> * <span data-ttu-id="2d8c6-291">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="2d8c6-291">Evaluate the model</span></span>
> * <span data-ttu-id="2d8c6-292">Predecir con el modelo entrenado</span><span class="sxs-lookup"><span data-stu-id="2d8c6-292">Predict with the trained model</span></span>
> * <span data-ttu-id="2d8c6-293">Implementar y predecir con un modelo cargado</span><span class="sxs-lookup"><span data-stu-id="2d8c6-293">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="2d8c6-294">Siga con el siguiente tutorial para obtener más información</span><span class="sxs-lookup"><span data-stu-id="2d8c6-294">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="2d8c6-295">Predictor de tarifa de taxi</span><span class="sxs-lookup"><span data-stu-id="2d8c6-295">Taxi Fare Predictor</span></span>](taxi-fare.md)
