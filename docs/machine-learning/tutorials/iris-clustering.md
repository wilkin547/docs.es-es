---
title: 'Agrupación de flores de iris mediante un aprendiz de agrupación en clústeres: ML.NET'
description: Obtenga información sobre cómo usar ML.NET en un escenario de agrupación en clústeres
author: pkulikov
ms.author: johalex
ms.date: 04/08/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 86eba0c7a3eaeed008d41ff950bf2fd7e0e5fb57
ms.sourcegitcommit: 859b2ba0c74a1a5a4ad0d59a3c3af23450995981
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/11/2019
ms.locfileid: "59481345"
---
# <a name="tutorial-cluster-iris-flowers-using-a-clustering-learner-with-mlnet"></a><span data-ttu-id="f0492-103">Tutorial: Agrupación de flores de iris mediante un aprendiz de agrupación en clústeres con ML.NET</span><span class="sxs-lookup"><span data-stu-id="f0492-103">Tutorial: Cluster iris flowers using a clustering learner with ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="f0492-104">Este tema hace referencia a ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios.</span><span class="sxs-lookup"><span data-stu-id="f0492-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="f0492-105">Para obtener más información, vea [la introducción de ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="f0492-105">For more information, see the [ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="f0492-106">En este tutorial y en el ejemplo relacionado actualmente se usa **ML.NET 1.0 RC (versión candidata para lanzamiento) (versión `1.0.0-preview`)**.</span><span class="sxs-lookup"><span data-stu-id="f0492-106">This tutorial and related sample are currently using **ML.NET 1.0 RC (Release Candidate) (version `1.0.0-preview`)**.</span></span> <span data-ttu-id="f0492-107">Para obtener más información, consulte las notas de la versión en el [repositorio de GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="f0492-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="f0492-108">En este tutorial se muestra cómo usar ML.NET para crear un [modelo de agrupación en clústeres](../resources/tasks.md#clustering) para el [conjunto de datos de flores de iris](https://en.wikipedia.org/wiki/Iris_flower_data_set).</span><span class="sxs-lookup"><span data-stu-id="f0492-108">This tutorial illustrates how to use ML.NET to build a [clustering model](../resources/tasks.md#clustering) for the [iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set).</span></span>

<span data-ttu-id="f0492-109">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="f0492-109">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="f0492-110">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="f0492-110">Understand the problem</span></span>
> - <span data-ttu-id="f0492-111">Seleccionar la tarea de aprendizaje automático adecuada</span><span class="sxs-lookup"><span data-stu-id="f0492-111">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="f0492-112">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="f0492-112">Prepare the data</span></span>
> - <span data-ttu-id="f0492-113">Cargar y transformar los datos</span><span class="sxs-lookup"><span data-stu-id="f0492-113">Load and transform the data</span></span>
> - <span data-ttu-id="f0492-114">Elegir un algoritmo de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="f0492-114">Choose a learning algorithm</span></span>
> - <span data-ttu-id="f0492-115">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="f0492-115">Train the model</span></span>
> - <span data-ttu-id="f0492-116">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="f0492-116">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f0492-117">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f0492-117">Prerequisites</span></span>

- <span data-ttu-id="f0492-118">[Visual Studio 2017 15.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.</span><span class="sxs-lookup"><span data-stu-id="f0492-118">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="f0492-119">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="f0492-119">Understand the problem</span></span>

<span data-ttu-id="f0492-120">Este problema consiste en dividir el conjunto de flores de iris en grupos diferentes según las características de la flor.</span><span class="sxs-lookup"><span data-stu-id="f0492-120">This problem is about dividing the set of iris flowers in different groups based on the flower features.</span></span> <span data-ttu-id="f0492-121">Esas características son la longitud y el ancho del sépalo, y la longitud y ancho del pétalo.</span><span class="sxs-lookup"><span data-stu-id="f0492-121">Those features are the length and width of a sepal and the length and width of a petal.</span></span> <span data-ttu-id="f0492-122">Para este tutorial, se supone que el tipo de cada flor es desconocido.</span><span class="sxs-lookup"><span data-stu-id="f0492-122">For this tutorial, assume that the type of each flower is unknown.</span></span> <span data-ttu-id="f0492-123">Le interesa conocer la estructura de un conjunto de datos a partir de las características y predecir cómo se ajusta una instancia de datos a esta estructura.</span><span class="sxs-lookup"><span data-stu-id="f0492-123">You want to learn the structure of a data set from the features and predict how a data instance fits this structure.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="f0492-124">Seleccionar la tarea de aprendizaje automático adecuada</span><span class="sxs-lookup"><span data-stu-id="f0492-124">Select the appropriate machine learning task</span></span>

<span data-ttu-id="f0492-125">Como no se sabe a qué grupo pertenece cada flor, seleccione la tarea de [aprendizaje automático no supervisado](../resources/glossary.md#unsupervised-machine-learning).</span><span class="sxs-lookup"><span data-stu-id="f0492-125">As you don't know to which group each flower belongs to, you choose the [unsupervised machine learning](../resources/glossary.md#unsupervised-machine-learning) task.</span></span> <span data-ttu-id="f0492-126">Para dividir un conjunto de datos en grupos de manera que los elementos del mismo grupo sean más similares entre sí que con los de otros grupos, use una tarea de aprendizaje automático de [agrupación en clústeres](../resources/tasks.md#clustering).</span><span class="sxs-lookup"><span data-stu-id="f0492-126">To divide a data set in groups in such a way that elements in the same group are more similar to each other than to those in other groups, use a [clustering](../resources/tasks.md#clustering) machine learning task.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="f0492-127">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="f0492-127">Create a console application</span></span>

1. <span data-ttu-id="f0492-128">Abra Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="f0492-128">Open Visual Studio 2017.</span></span> <span data-ttu-id="f0492-129">Seleccione **Archivo** > **Nuevo** > **Proyecto** de la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="f0492-129">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="f0492-130">En el cuadro de diálogo **Nuevo proyecto**, seleccione el nodo **Visual C#** seguido del nodo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="f0492-130">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="f0492-131">Después, seleccione la plantilla del proyecto **Aplicación de consola (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="f0492-131">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="f0492-132">En el cuadro de texto **Nombre**, escriba "IrisFlowerClustering" y después haga clic en el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f0492-132">In the **Name** text box, type "IrisFlowerClustering" and then select the **OK** button.</span></span>

1. <span data-ttu-id="f0492-133">Cree un directorio denominado *Datos* en el proyecto para almacenar el conjunto de datos y los archivos del modelo:</span><span class="sxs-lookup"><span data-stu-id="f0492-133">Create a directory named *Data* in your project to store the data set and model files:</span></span>

    <span data-ttu-id="f0492-134">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **Nueva carpeta**.</span><span class="sxs-lookup"><span data-stu-id="f0492-134">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="f0492-135">Escriba "Datos" y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="f0492-135">Type "Data" and hit Enter.</span></span>

1. <span data-ttu-id="f0492-136">Instale el paquete NuGet **Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="f0492-136">Install the **Microsoft.ML** NuGet package:</span></span>

    <span data-ttu-id="f0492-137">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="f0492-137">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="f0492-138">Elija "nuget.org" como origen del paquete, seleccione la pestaña **Examinar**, busque **Microsoft.ML**, seleccione ese paquete en la lista y haga clic en el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="f0492-138">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="f0492-139">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="f0492-139">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-the-data"></a><span data-ttu-id="f0492-140">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="f0492-140">Prepare the data</span></span>

1. <span data-ttu-id="f0492-141">Descargue el conjunto de datos [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) y guárdelo en la carpeta *Datos* que ha creado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="f0492-141">Download the [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) data set and save it to the *Data* folder you've created at the previous step.</span></span> <span data-ttu-id="f0492-142">Para obtener más información sobre el conjunto de datos de iris, vea la página de Wikipedia [Conjunto de datos de flor de Iris](https://en.wikipedia.org/wiki/Iris_flower_data_set) y la página [Iris Data Set](https://archive.ics.uci.edu/ml/datasets/Iris) (Conjunto de datos Iris), que es el origen del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="f0492-142">For more information about the iris data set, see the [Iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set) Wikipedia page and the [Iris Data Set](https://archive.ics.uci.edu/ml/datasets/Iris) page, which is the source of the data set.</span></span>

1. <span data-ttu-id="f0492-143">En el **Explorador de soluciones**, haga clic con el botón derecho en el archivo *iris.data* y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f0492-143">In **Solution Explorer**, right-click the *iris.data* file and select **Properties**.</span></span> <span data-ttu-id="f0492-144">En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.</span><span class="sxs-lookup"><span data-stu-id="f0492-144">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="f0492-145">El archivo *iris.data* contiene cinco columnas que representan lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f0492-145">The *iris.data* file contains five columns that represent:</span></span>

- <span data-ttu-id="f0492-146">La longitud del sépalo en centímetros.</span><span class="sxs-lookup"><span data-stu-id="f0492-146">sepal length in centimetres</span></span>
- <span data-ttu-id="f0492-147">El ancho del sépalo en centímetros.</span><span class="sxs-lookup"><span data-stu-id="f0492-147">sepal width in centimetres</span></span>
- <span data-ttu-id="f0492-148">La longitud del pétalo en centímetros.</span><span class="sxs-lookup"><span data-stu-id="f0492-148">petal length in centimetres</span></span>
- <span data-ttu-id="f0492-149">El ancho del pétalo en centímetros.</span><span class="sxs-lookup"><span data-stu-id="f0492-149">petal width in centimetres</span></span>
- <span data-ttu-id="f0492-150">El tipo de flor de iris.</span><span class="sxs-lookup"><span data-stu-id="f0492-150">type of iris flower</span></span>

<span data-ttu-id="f0492-151">Para el ejemplo de agrupación en clústeres, en este tutorial se ignora la última columna.</span><span class="sxs-lookup"><span data-stu-id="f0492-151">For the sake of the clustering example, this tutorial ignores the last column.</span></span>

## <a name="create-data-classes"></a><span data-ttu-id="f0492-152">Crear clases de datos</span><span class="sxs-lookup"><span data-stu-id="f0492-152">Create data classes</span></span>

<span data-ttu-id="f0492-153">Cree clases para los datos de entrada y las predicciones:</span><span class="sxs-lookup"><span data-stu-id="f0492-153">Create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="f0492-154">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="f0492-154">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="f0492-155">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *IrisData.cs*.</span><span class="sxs-lookup"><span data-stu-id="f0492-155">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *IrisData.cs*.</span></span> <span data-ttu-id="f0492-156">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f0492-156">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="f0492-157">Agregue la directiva `using` siguiente al archivo nuevo:</span><span class="sxs-lookup"><span data-stu-id="f0492-157">Add the following `using` directive to the new file:</span></span>

   [!code-csharp[Add necessary usings](~/samples/machine-learning/tutorials/IrisFlowerClustering/IrisData.cs#Usings)]

<span data-ttu-id="f0492-158">Quite la definición de clase existente y agregue el código siguiente, que define dos clases `IrisData` y `ClusterPrediction`, al archivo *IrisData.cs*:</span><span class="sxs-lookup"><span data-stu-id="f0492-158">Remove the existing class definition and add the following code, which defines the classes `IrisData` and `ClusterPrediction`, to the *IrisData.cs* file:</span></span>

[!code-csharp[Define data classes](~/samples/machine-learning/tutorials/IrisFlowerClustering/IrisData.cs#ClassDefinitions)]

`IrisData` <span data-ttu-id="f0492-159">es la clase de datos de entrada y tiene definiciones para cada una de las características del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="f0492-159">is the input data class and has definitions for each feature from the data set.</span></span> <span data-ttu-id="f0492-160">Use el atributo [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute) para especificar los índices de las columnas de origen en el archivo de conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="f0492-160">Use the [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute) attribute to specify the indices of the source columns in the data set file.</span></span>

<span data-ttu-id="f0492-161">La clase `ClusterPrediction` representa el resultado del modelo de agrupación en clústeres aplicado a una instancia de `IrisData`.</span><span class="sxs-lookup"><span data-stu-id="f0492-161">The `ClusterPrediction` class represents the output of the clustering model applied to an `IrisData` instance.</span></span> <span data-ttu-id="f0492-162">Use el atributo [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute) para enlazar los campos `PredictedClusterId` y `Distances` a las columnas **PredictedLabel** y **Score** respectivamente.</span><span class="sxs-lookup"><span data-stu-id="f0492-162">Use the [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute to bind the `PredictedClusterId` and `Distances` fields to the **PredictedLabel** and **Score** columns respectively.</span></span> <span data-ttu-id="f0492-163">En el caso de la tarea de agrupación en clústeres, esas columnas tienen el significado siguiente:</span><span class="sxs-lookup"><span data-stu-id="f0492-163">In case of the clustering task those columns have the following meaning:</span></span>

- <span data-ttu-id="f0492-164">La columna **PredictedLabel** contiene el identificador del clúster previsto.</span><span class="sxs-lookup"><span data-stu-id="f0492-164">**PredictedLabel** column contains the ID of the predicted cluster.</span></span>
- <span data-ttu-id="f0492-165">La columna **Score** contiene una matriz con las distancias euclidianas cuadradas a los centroides de clúster.</span><span class="sxs-lookup"><span data-stu-id="f0492-165">**Score** column contains an array with squared Euclidean distances to the cluster centroids.</span></span> <span data-ttu-id="f0492-166">La longitud de la matriz es igual al número de clústeres.</span><span class="sxs-lookup"><span data-stu-id="f0492-166">The array length is equal to the number of clusters.</span></span>

> [!NOTE]
> <span data-ttu-id="f0492-167">Use el tipo `float` para representar los valores de punto flotante en las clases de entrada y predicción de datos.</span><span class="sxs-lookup"><span data-stu-id="f0492-167">Use the `float` type to represent floating-point values in the input and prediction data classes.</span></span>

## <a name="define-data-and-model-paths"></a><span data-ttu-id="f0492-168">Definir rutas de acceso de datos y modelos</span><span class="sxs-lookup"><span data-stu-id="f0492-168">Define data and model paths</span></span>

<span data-ttu-id="f0492-169">Vuelva al archivo *Program.cs* y agregue dos campos para contener las rutas de acceso al archivo de conjuntos de datos y al archivo en el que se guarda el modelo:</span><span class="sxs-lookup"><span data-stu-id="f0492-169">Go back to the *Program.cs* file and add two fields to hold the paths to the data set file and to the file to save the model:</span></span>

- `_dataPath` <span data-ttu-id="f0492-170">contiene la ruta de acceso al archivo con el conjunto de datos utilizado para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="f0492-170">contains the path to the file with the data set used to train the model.</span></span>
- `_modelPath` <span data-ttu-id="f0492-171">contiene la ruta de acceso al archivo en el que se almacena el modelo entrenado.</span><span class="sxs-lookup"><span data-stu-id="f0492-171">contains the path to the file where the trained model is stored.</span></span>

<span data-ttu-id="f0492-172">Agregue el código siguiente justo encima del método `Main` para especificar las rutas de acceso:</span><span class="sxs-lookup"><span data-stu-id="f0492-172">Add the following code right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Initialize paths](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#Paths)]

<span data-ttu-id="f0492-173">Para que el código anterior se compile, agregue las directivas `using` siguientes a la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="f0492-173">To make the preceding code compile, add the following `using` directives at the top of the *Program.cs* file:</span></span>

[!code-csharp[Add usings for paths](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#UsingsForPaths)]

## <a name="create-ml-context"></a><span data-ttu-id="f0492-174">Creación del contexto de ML</span><span class="sxs-lookup"><span data-stu-id="f0492-174">Create ML context</span></span>

<span data-ttu-id="f0492-175">Agregue las directivas `using` adicionales siguientes a la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="f0492-175">Add the following additional `using` directives to the top of the *Program.cs* file:</span></span>

[!code-csharp[Add Microsoft.ML usings](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#MLUsings)]

<span data-ttu-id="f0492-176">En el método `Main`, reemplace la línea `Console.WriteLine("Hello World!");` con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="f0492-176">In the `Main` method, replace the `Console.WriteLine("Hello World!");` line with the following code:</span></span>

[!code-csharp[Create ML context](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreateContext)]

<span data-ttu-id="f0492-177">La clase <xref:Microsoft.ML.MLContext?displayProperty=nameWithType> representa el entorno de aprendizaje automático y proporciona mecanismos para puntos de entrada y de registro para la carga de datos, entrenamiento del modelo, predicción y otras tareas.</span><span class="sxs-lookup"><span data-stu-id="f0492-177">The <xref:Microsoft.ML.MLContext?displayProperty=nameWithType> class represents the machine learning environment and provides mechanisms for logging and entry points for data loading, model training, prediction, and other tasks.</span></span> <span data-ttu-id="f0492-178">Esto es comparable conceptualmente a usar `DbContext` en Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="f0492-178">This is comparable conceptually to using `DbContext` in Entity Framework.</span></span>

## <a name="setup-data-loading"></a><span data-ttu-id="f0492-179">Configuración de la carga de datos</span><span class="sxs-lookup"><span data-stu-id="f0492-179">Setup data loading</span></span>

<span data-ttu-id="f0492-180">Agregue el código siguiente al método `Main` para configurar la manera de cargar los datos:</span><span class="sxs-lookup"><span data-stu-id="f0492-180">Add the following code to the `Main` method to setup the way to load data:</span></span>

[!code-csharp[Create text loader](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreateDataView)]

<span data-ttu-id="f0492-181">El [`MLContext.Data.LoadFromTextFile` método de extensión](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) genérico deduce el esquema del conjunto de datos del tipo `IrisData` proporcionado y devuelve <xref:Microsoft.ML.IDataView>, que se puede usar como entrada para los transformadores.</span><span class="sxs-lookup"><span data-stu-id="f0492-181">The generic [`MLContext.Data.LoadFromTextFile` extension method](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) infers the data set schema from the provided `IrisData` type and returns <xref:Microsoft.ML.IDataView> which can be used as input for transformers.</span></span>

## <a name="create-a-learning-pipeline"></a><span data-ttu-id="f0492-182">Crear una canalización de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="f0492-182">Create a learning pipeline</span></span>

<span data-ttu-id="f0492-183">Para este tutorial, la canalización de aprendizaje de la tarea de agrupación en clústeres consta de los dos pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f0492-183">For this tutorial, the learning pipeline of the clustering task comprises two following steps:</span></span>

- <span data-ttu-id="f0492-184">concatenar las columnas cargadas en una columna **Características**, que usa un instructor de agrupación en clústeres;</span><span class="sxs-lookup"><span data-stu-id="f0492-184">concatenate loaded columns into one **Features** column, which is used by a clustering trainer;</span></span>
- <span data-ttu-id="f0492-185">usar un instructor <xref:Microsoft.ML.Trainers.KMeansTrainer> para entrenar el modelo mediante el algoritmo de agrupación en clústeres k-means++.</span><span class="sxs-lookup"><span data-stu-id="f0492-185">use a <xref:Microsoft.ML.Trainers.KMeansTrainer> trainer to train the model using the k-means++ clustering algorithm.</span></span>

<span data-ttu-id="f0492-186">Agregue el código siguiente al método `Main`:</span><span class="sxs-lookup"><span data-stu-id="f0492-186">Add the following code to the `Main` method:</span></span>

[!code-csharp[Create pipeline](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreatePipeline)]

<span data-ttu-id="f0492-187">En el código se especifica que el conjunto de datos se debe dividir en tres clústeres.</span><span class="sxs-lookup"><span data-stu-id="f0492-187">The code specifies that the data set should be split in three clusters.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="f0492-188">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="f0492-188">Train the model</span></span>

<span data-ttu-id="f0492-189">Los pasos que se agregaron en las secciones anteriores prepararon la canalización para el aprendizaje, pero no se ha ejecutado ninguno.</span><span class="sxs-lookup"><span data-stu-id="f0492-189">The steps added in the preceding sections prepared the pipeline for training, however, none have been executed.</span></span> <span data-ttu-id="f0492-190">Agregue la línea siguiente al método `Main` para realizar la carga de datos y el entrenamiento del modelo:</span><span class="sxs-lookup"><span data-stu-id="f0492-190">Add the following line to the `Main` method to perform data loading and model training:</span></span>

[!code-csharp[Train the model](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#TrainModel)]

### <a name="save-the-model"></a><span data-ttu-id="f0492-191">Guardado del modelo</span><span class="sxs-lookup"><span data-stu-id="f0492-191">Save the model</span></span>

<span data-ttu-id="f0492-192">En este punto, tiene un modelo que se puede integrar en cualquiera de las aplicaciones de .NET nuevas o existentes.</span><span class="sxs-lookup"><span data-stu-id="f0492-192">At this point, you have a model that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="f0492-193">Para guardar el modelo en un archivo .zip, agregue el código siguiente al método `Main`:</span><span class="sxs-lookup"><span data-stu-id="f0492-193">To save your model to a .zip file, add the following code to the `Main` method:</span></span>

[!code-csharp[Save the model](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#SaveModel)]

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="f0492-194">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="f0492-194">Use the model for predictions</span></span>

<span data-ttu-id="f0492-195">Para realizar predicciones, use la clase <xref:Microsoft.ML.PredictionEngine%602>, que toma instancias del tipo de entrada a través de la canalización de transformador y genera instancias del tipo de salida.</span><span class="sxs-lookup"><span data-stu-id="f0492-195">To make predictions, use the <xref:Microsoft.ML.PredictionEngine%602> class that takes instances of the input type through the transformer pipeline and produces instances of the output type.</span></span> <span data-ttu-id="f0492-196">Agregue la línea siguiente al método `Main` para crear una instancia de esa clase:</span><span class="sxs-lookup"><span data-stu-id="f0492-196">Add the following line to the `Main` method to create an instance of that class:</span></span>

[!code-csharp[Create predictor](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#Predictor)]

<span data-ttu-id="f0492-197">Cree la clase `TestIrisData` para guardar las instancias de datos de prueba:</span><span class="sxs-lookup"><span data-stu-id="f0492-197">Create the `TestIrisData` class to house test data instances:</span></span>

1. <span data-ttu-id="f0492-198">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="f0492-198">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="f0492-199">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *TestIrisData.cs*.</span><span class="sxs-lookup"><span data-stu-id="f0492-199">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TestIrisData.cs*.</span></span> <span data-ttu-id="f0492-200">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f0492-200">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="f0492-201">Modifique la clase para que sea estática, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f0492-201">Modify the class to be static like in the following example:</span></span>

   [!code-csharp[Make class static](~/samples/machine-learning/tutorials/IrisFlowerClustering/TestIrisData.cs#Static)]

<span data-ttu-id="f0492-202">En este tutorial se presenta una instancia de datos de iris dentro de esta clase.</span><span class="sxs-lookup"><span data-stu-id="f0492-202">This tutorial introduces one iris data instance within this class.</span></span> <span data-ttu-id="f0492-203">Puede agregar otros escenarios para experimentar con el modelo.</span><span class="sxs-lookup"><span data-stu-id="f0492-203">You can add other scenarios to experiment with the model.</span></span> <span data-ttu-id="f0492-204">Agregue el código siguiente a la clase `TestIrisData`:</span><span class="sxs-lookup"><span data-stu-id="f0492-204">Add the following code into the `TestIrisData` class:</span></span>

[!code-csharp[Test data](~/samples/machine-learning/tutorials/IrisFlowerClustering/TestIrisData.cs#TestData)]

<span data-ttu-id="f0492-205">Para determinar a qué clúster pertenece el elemento especificado, vuelva al archivo *Program.cs* y agregue el código siguiente al método `Main`:</span><span class="sxs-lookup"><span data-stu-id="f0492-205">To find out the cluster to which the specified item belongs to, go back to the *Program.cs* file and add the following code into the `Main` method:</span></span>

[!code-csharp[Predict and output results](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#PredictionExample)]

<span data-ttu-id="f0492-206">Ejecute el programa para ver qué clúster contiene la instancia de datos especificada y las distancias cuadradas desde esa instancia a los centroides de clúster.</span><span class="sxs-lookup"><span data-stu-id="f0492-206">Run the program to see which cluster contains the specified data instance and squared distances from that instance to the cluster centroids.</span></span> <span data-ttu-id="f0492-207">Los resultados deberían ser similares a los indicados a continuación:</span><span class="sxs-lookup"><span data-stu-id="f0492-207">Your results should be similar to the following:</span></span>

```text
Cluster: 2
Distances: 11.69127 0.02159119 25.59896
```

<span data-ttu-id="f0492-208">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="f0492-208">Congratulations!</span></span> <span data-ttu-id="f0492-209">Ha creado correctamente un modelo de aprendizaje automático para la agrupación en clústeres de iris y lo ha usado para realizar predicciones.</span><span class="sxs-lookup"><span data-stu-id="f0492-209">You've now successfully built a machine learning model for iris clustering and used it to make predictions.</span></span> <span data-ttu-id="f0492-210">Puede encontrar el código fuente de este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisFlowerClustering) de GitHub.</span><span class="sxs-lookup"><span data-stu-id="f0492-210">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisFlowerClustering) GitHub repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f0492-211">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="f0492-211">Next steps</span></span>

<span data-ttu-id="f0492-212">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="f0492-212">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="f0492-213">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="f0492-213">Understand the problem</span></span>
> - <span data-ttu-id="f0492-214">Seleccionar la tarea de aprendizaje automático adecuada</span><span class="sxs-lookup"><span data-stu-id="f0492-214">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="f0492-215">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="f0492-215">Prepare the data</span></span>
> - <span data-ttu-id="f0492-216">Cargar y transformar los datos</span><span class="sxs-lookup"><span data-stu-id="f0492-216">Load and transform the data</span></span>
> - <span data-ttu-id="f0492-217">Elegir un algoritmo de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="f0492-217">Choose a learning algorithm</span></span>
> - <span data-ttu-id="f0492-218">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="f0492-218">Train the model</span></span>
> - <span data-ttu-id="f0492-219">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="f0492-219">Use the model for predictions</span></span>

<span data-ttu-id="f0492-220">Visite nuestro repositorio de GitHub para obtener más información y encontrar más ejemplos.</span><span class="sxs-lookup"><span data-stu-id="f0492-220">Check out our GitHub repository to continue learning and find more samples.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="f0492-221">Repositorio dotnet/machinelearning de GitHub</span><span class="sxs-lookup"><span data-stu-id="f0492-221">dotnet/machinelearning GitHub repository</span></span>](https://github.com/dotnet/machinelearning/)
