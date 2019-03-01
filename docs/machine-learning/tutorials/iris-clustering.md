---
title: 'Agrupación de flores de iris mediante un aprendiz de agrupación en clústeres: ML.NET'
description: Obtenga información sobre cómo usar ML.NET en un escenario de agrupación en clústeres
author: pkulikov
ms.author: johalex
ms.date: 02/19/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: fcbd75597d6fdce8dceffc9d47d06cc13dd11570
ms.sourcegitcommit: 2b986afe4ce9e13bbeec929c9737757eb61de60e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56664476"
---
# <a name="tutorial-cluster-iris-flowers-using-a-clustering-learner-with-mlnet"></a><span data-ttu-id="ffb6b-103">Tutorial: Agrupación de flores de iris mediante un aprendiz de agrupación en clústeres con ML.NET</span><span class="sxs-lookup"><span data-stu-id="ffb6b-103">Tutorial: Cluster iris flowers using a clustering learner with ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="ffb6b-104">Este tema hace referencia a ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="ffb6b-105">Para obtener más información, vea [la introducción de ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="ffb6b-105">For more information, see the [ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="ffb6b-106">En este tutorial se muestra cómo usar ML.NET para crear un [modelo de agrupación en clústeres](../resources/tasks.md#clustering) para el [conjunto de datos de flores de iris](https://en.wikipedia.org/wiki/Iris_flower_data_set).</span><span class="sxs-lookup"><span data-stu-id="ffb6b-106">This tutorial illustrates how to use ML.NET to build a [clustering model](../resources/tasks.md#clustering) for the [iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set).</span></span>

<span data-ttu-id="ffb6b-107">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="ffb6b-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="ffb6b-108">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="ffb6b-108">Understand the problem</span></span>
> - <span data-ttu-id="ffb6b-109">Seleccionar la tarea de aprendizaje automático adecuada</span><span class="sxs-lookup"><span data-stu-id="ffb6b-109">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="ffb6b-110">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="ffb6b-110">Prepare the data</span></span>
> - <span data-ttu-id="ffb6b-111">Cargar y transformar los datos</span><span class="sxs-lookup"><span data-stu-id="ffb6b-111">Load and transform the data</span></span>
> - <span data-ttu-id="ffb6b-112">Elegir un algoritmo de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="ffb6b-112">Choose a learning algorithm</span></span>
> - <span data-ttu-id="ffb6b-113">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="ffb6b-113">Train the model</span></span>
> - <span data-ttu-id="ffb6b-114">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="ffb6b-114">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ffb6b-115">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ffb6b-115">Prerequisites</span></span>

- <span data-ttu-id="ffb6b-116">[Visual Studio 2017 15.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-116">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="ffb6b-117">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="ffb6b-117">Understand the problem</span></span>

<span data-ttu-id="ffb6b-118">Este problema consiste en dividir el conjunto de flores de iris en grupos diferentes según las características de la flor.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-118">This problem is about dividing the set of iris flowers in different groups based on the flower features.</span></span> <span data-ttu-id="ffb6b-119">Esas características son la longitud y el ancho del sépalo, y la longitud y ancho del pétalo.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-119">Those features are the length and width of a sepal and the length and width of a petal.</span></span> <span data-ttu-id="ffb6b-120">Para este tutorial, se supone que el tipo de cada flor es desconocido.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-120">For this tutorial, assume that the type of each flower is unknown.</span></span> <span data-ttu-id="ffb6b-121">Le interesa conocer la estructura de un conjunto de datos a partir de las características y predecir cómo se ajusta una instancia de datos a esta estructura.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-121">You want to learn the structure of a data set from the features and predict how a data instance fits this structure.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="ffb6b-122">Seleccionar la tarea de aprendizaje automático adecuada</span><span class="sxs-lookup"><span data-stu-id="ffb6b-122">Select the appropriate machine learning task</span></span>

<span data-ttu-id="ffb6b-123">Como no se sabe a qué grupo pertenece cada flor, seleccione la tarea de [aprendizaje automático no supervisado](../resources/glossary.md#unsupervised-machine-learning).</span><span class="sxs-lookup"><span data-stu-id="ffb6b-123">As you don't know to which group each flower belongs to, you choose the [unsupervised machine learning](../resources/glossary.md#unsupervised-machine-learning) task.</span></span> <span data-ttu-id="ffb6b-124">Para dividir un conjunto de datos en grupos de manera que los elementos del mismo grupo sean más similares entre sí que con los de otros grupos, use una tarea de aprendizaje automático de [agrupación en clústeres](../resources/tasks.md#clustering).</span><span class="sxs-lookup"><span data-stu-id="ffb6b-124">To divide a data set in groups in such a way that elements in the same group are more similar to each other than to those in other groups, use a [clustering](../resources/tasks.md#clustering) machine learning task.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="ffb6b-125">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="ffb6b-125">Create a console application</span></span>

1. <span data-ttu-id="ffb6b-126">Abra Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-126">Open Visual Studio 2017.</span></span> <span data-ttu-id="ffb6b-127">Seleccione **Archivo** > **Nuevo** > **Proyecto** de la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-127">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="ffb6b-128">En el cuadro de diálogo **Nuevo proyecto**, seleccione el nodo **Visual C#** seguido del nodo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-128">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="ffb6b-129">Después, seleccione la plantilla del proyecto **Aplicación de consola (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-129">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="ffb6b-130">En el cuadro de texto **Nombre**, escriba "IrisFlowerClustering" y después haga clic en el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-130">In the **Name** text box, type "IrisFlowerClustering" and then select the **OK** button.</span></span>

1. <span data-ttu-id="ffb6b-131">Cree un directorio denominado *Datos* en el proyecto para almacenar el conjunto de datos y los archivos del modelo:</span><span class="sxs-lookup"><span data-stu-id="ffb6b-131">Create a directory named *Data* in your project to store the data set and model files:</span></span>

    <span data-ttu-id="ffb6b-132">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **Nueva carpeta**.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-132">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="ffb6b-133">Escriba "Datos" y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-133">Type "Data" and hit Enter.</span></span>

1. <span data-ttu-id="ffb6b-134">Instale el paquete NuGet **Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="ffb6b-134">Install the **Microsoft.ML** NuGet package:</span></span>

    <span data-ttu-id="ffb6b-135">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-135">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="ffb6b-136">Elija "nuget.org" como origen del paquete, seleccione la pestaña **Examinar**, busque **Microsoft.ML**, seleccione ese paquete en la lista y haga clic en el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-136">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="ffb6b-137">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-137">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-the-data"></a><span data-ttu-id="ffb6b-138">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="ffb6b-138">Prepare the data</span></span>

1. <span data-ttu-id="ffb6b-139">Descargue el conjunto de datos [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) y guárdelo en la carpeta *Datos* que ha creado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-139">Download the [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) data set and save it to the *Data* folder you've created at the previous step.</span></span> <span data-ttu-id="ffb6b-140">Para obtener más información sobre el conjunto de datos de iris, vea la página de Wikipedia [Conjunto de datos de flor de Iris](https://en.wikipedia.org/wiki/Iris_flower_data_set) y la página [Iris Data Set](https://archive.ics.uci.edu/ml/datasets/Iris) (Conjunto de datos Iris), que es el origen del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-140">For more information about the iris data set, see the [Iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set) Wikipedia page and the [Iris Data Set](https://archive.ics.uci.edu/ml/datasets/Iris) page, which is the source of the data set.</span></span>

1. <span data-ttu-id="ffb6b-141">En el **Explorador de soluciones**, haga clic con el botón derecho en el archivo *iris.data* y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-141">In **Solution Explorer**, right-click the *iris.data* file and select **Properties**.</span></span> <span data-ttu-id="ffb6b-142">En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-142">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="ffb6b-143">El archivo *iris.data* contiene cinco columnas que representan lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ffb6b-143">The *iris.data* file contains five columns that represent:</span></span>

- <span data-ttu-id="ffb6b-144">La longitud del sépalo en centímetros.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-144">sepal length in centimetres</span></span>
- <span data-ttu-id="ffb6b-145">El ancho del sépalo en centímetros.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-145">sepal width in centimetres</span></span>
- <span data-ttu-id="ffb6b-146">La longitud del pétalo en centímetros.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-146">petal length in centimetres</span></span>
- <span data-ttu-id="ffb6b-147">El ancho del pétalo en centímetros.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-147">petal width in centimetres</span></span>
- <span data-ttu-id="ffb6b-148">El tipo de flor de iris.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-148">type of iris flower</span></span>

<span data-ttu-id="ffb6b-149">Para el ejemplo de agrupación en clústeres, en este tutorial se ignora la última columna.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-149">For the sake of the clustering example, this tutorial ignores the last column.</span></span>

## <a name="create-data-classes"></a><span data-ttu-id="ffb6b-150">Crear clases de datos</span><span class="sxs-lookup"><span data-stu-id="ffb6b-150">Create data classes</span></span>

<span data-ttu-id="ffb6b-151">Cree clases para los datos de entrada y las predicciones:</span><span class="sxs-lookup"><span data-stu-id="ffb6b-151">Create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="ffb6b-152">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-152">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="ffb6b-153">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *IrisData.cs*.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-153">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *IrisData.cs*.</span></span> <span data-ttu-id="ffb6b-154">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-154">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="ffb6b-155">Agregue la directiva `using` siguiente al archivo nuevo:</span><span class="sxs-lookup"><span data-stu-id="ffb6b-155">Add the following `using` directive to the new file:</span></span>

   [!code-csharp[Add necessary usings](~/samples/machine-learning/tutorials/IrisFlowerClustering/IrisData.cs#Usings)]

<span data-ttu-id="ffb6b-156">Quite la definición de clase existente y agregue el código siguiente, que define dos clases `IrisData` y `ClusterPrediction`, al archivo *IrisData.cs*:</span><span class="sxs-lookup"><span data-stu-id="ffb6b-156">Remove the existing class definition and add the following code, which defines the classes `IrisData` and `ClusterPrediction`, to the *IrisData.cs* file:</span></span>

[!code-csharp[Define data classes](~/samples/machine-learning/tutorials/IrisFlowerClustering/IrisData.cs#ClassDefinitions)]

<span data-ttu-id="ffb6b-157">`IrisData` es la clase de datos de entrada y tiene definiciones para cada una de las características del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-157">`IrisData` is the input data class and has definitions for each feature from the data set.</span></span> <span data-ttu-id="ffb6b-158">Use el atributo [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute) para especificar los índices de las columnas de origen en el archivo de conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-158">Use the [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute) attribute to specify the indices of the source columns in the data set file.</span></span>

<span data-ttu-id="ffb6b-159">La clase `ClusterPrediction` representa el resultado del modelo de agrupación en clústeres aplicado a una instancia de `IrisData`.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-159">The `ClusterPrediction` class represents the output of the clustering model applied to an `IrisData` instance.</span></span> <span data-ttu-id="ffb6b-160">Use el atributo [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute) para enlazar los campos `PredictedClusterId` y `Distances` a las columnas **PredictedLabel** y **Score** respectivamente.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-160">Use the [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute to bind the `PredictedClusterId` and `Distances` fields to the **PredictedLabel** and **Score** columns respectively.</span></span> <span data-ttu-id="ffb6b-161">En el caso de la tarea de agrupación en clústeres, esas columnas tienen el significado siguiente:</span><span class="sxs-lookup"><span data-stu-id="ffb6b-161">In case of the clustering task those columns have the following meaning:</span></span>

- <span data-ttu-id="ffb6b-162">La columna **PredictedLabel** contiene el identificador del clúster previsto.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-162">**PredictedLabel** column contains the ID of the predicted cluster.</span></span>
- <span data-ttu-id="ffb6b-163">La columna **Score** contiene una matriz con las distancias euclidianas cuadradas a los centroides de clúster.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-163">**Score** column contains an array with squared Euclidean distances to the cluster centroids.</span></span> <span data-ttu-id="ffb6b-164">La longitud de la matriz es igual al número de clústeres.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-164">The array length is equal to the number of clusters.</span></span>

> [!NOTE]
> <span data-ttu-id="ffb6b-165">Use el tipo `float` para representar los valores de punto flotante en las clases de entrada y predicción de datos.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-165">Use the `float` type to represent floating-point values in the input and prediction data classes.</span></span>

## <a name="define-data-and-model-paths"></a><span data-ttu-id="ffb6b-166">Definir rutas de acceso de datos y modelos</span><span class="sxs-lookup"><span data-stu-id="ffb6b-166">Define data and model paths</span></span>

<span data-ttu-id="ffb6b-167">Vuelva al archivo *Program.cs* y agregue dos campos para contener las rutas de acceso al archivo de conjuntos de datos y al archivo en el que se guarda el modelo:</span><span class="sxs-lookup"><span data-stu-id="ffb6b-167">Go back to the *Program.cs* file and add two fields to hold the paths to the data set file and to the file to save the model:</span></span>

- <span data-ttu-id="ffb6b-168">`_dataPath` contiene la ruta de acceso al archivo con el conjunto de datos utilizado para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-168">`_dataPath` contains the path to the file with the data set used to train the model.</span></span>
- <span data-ttu-id="ffb6b-169">`_modelPath` contiene la ruta de acceso al archivo en el que se almacena el modelo entrenado.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-169">`_modelPath` contains the path to the file where the trained model is stored.</span></span>

<span data-ttu-id="ffb6b-170">Agregue el código siguiente justo encima del método `Main` para especificar las rutas de acceso:</span><span class="sxs-lookup"><span data-stu-id="ffb6b-170">Add the following code right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Initialize paths](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#Paths)]

<span data-ttu-id="ffb6b-171">Para que el código anterior se compile, agregue las directivas `using` siguientes a la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="ffb6b-171">To make the preceding code compile, add the following `using` directives at the top of the *Program.cs* file:</span></span>

[!code-csharp[Add usings for paths](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#UsingsForPaths)]

## <a name="create-ml-context"></a><span data-ttu-id="ffb6b-172">Creación del contexto de ML</span><span class="sxs-lookup"><span data-stu-id="ffb6b-172">Create ML context</span></span>

<span data-ttu-id="ffb6b-173">Agregue las directivas `using` adicionales siguientes a la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="ffb6b-173">Add the following additional `using` directives to the top of the *Program.cs* file:</span></span>

[!code-csharp[Add Microsoft.ML usings](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#MLUsings)]

<span data-ttu-id="ffb6b-174">En el método `Main`, reemplace la línea `Console.WriteLine("Hello World!");` con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="ffb6b-174">In the `Main` method, replace the `Console.WriteLine("Hello World!");` line with the following code:</span></span>

[!code-csharp[Create ML context](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreateContext)]

<span data-ttu-id="ffb6b-175">La clase <xref:Microsoft.ML.MLContext?displayProperty=nameWithType> representa el entorno de aprendizaje automático y proporciona mecanismos para puntos de entrada y de registro para la carga de datos, entrenamiento del modelo, predicción y otras tareas.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-175">The <xref:Microsoft.ML.MLContext?displayProperty=nameWithType> class represents the machine learning environment and provides mechanisms for logging and entry points for data loading, model training, prediction, and other tasks.</span></span> <span data-ttu-id="ffb6b-176">Esto es comparable conceptualmente a usar `DbContext` en Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-176">This is comparable conceptually to using `DbContext` in Entity Framework.</span></span>

## <a name="setup-data-loading"></a><span data-ttu-id="ffb6b-177">Configuración de la carga de datos</span><span class="sxs-lookup"><span data-stu-id="ffb6b-177">Setup data loading</span></span>

<span data-ttu-id="ffb6b-178">Agregue el código siguiente al método `Main` para configurar la manera de cargar los datos:</span><span class="sxs-lookup"><span data-stu-id="ffb6b-178">Add the following code to the `Main` method to setup the way to load data:</span></span>

[!code-csharp[Create text loader](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#SetupTextLoader)]

<span data-ttu-id="ffb6b-179">Use el método [genérico `CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader%60%601(Microsoft.ML.DataOperationsCatalog,System.Boolean,System.Char,System.Boolean,System.Boolean,System.Boolean)) para inferir el esquema del conjunto de datos de la definición de clase `IrisData`.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-179">Use the [generic `CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader%60%601(Microsoft.ML.DataOperationsCatalog,System.Boolean,System.Char,System.Boolean,System.Boolean,System.Boolean)) method to infer the dataset schema from the `IrisData` class definition.</span></span>

<span data-ttu-id="ffb6b-180">Use una instancia de <xref:Microsoft.ML.Data.TextLoader> para crear una instancia de <xref:Microsoft.Data.DataView.IDataView>, que representa el origen de datos para el conjunto de datos de entrenamiento:</span><span class="sxs-lookup"><span data-stu-id="ffb6b-180">Use instantiated <xref:Microsoft.ML.Data.TextLoader> instance to create an <xref:Microsoft.Data.DataView.IDataView> instance, which represents the data source for the training data set:</span></span>

[!code-csharp[Create IDataView](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreateDataView)]

## <a name="create-a-learning-pipeline"></a><span data-ttu-id="ffb6b-181">Crear una canalización de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="ffb6b-181">Create a learning pipeline</span></span>

<span data-ttu-id="ffb6b-182">Para este tutorial, la canalización de aprendizaje de la tarea de agrupación en clústeres consta de los dos pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ffb6b-182">For this tutorial, the learning pipeline of the clustering task comprises two following steps:</span></span>

- <span data-ttu-id="ffb6b-183">concatenar las columnas cargadas en una columna **Características**, que usa un instructor de agrupación en clústeres;</span><span class="sxs-lookup"><span data-stu-id="ffb6b-183">concatenate loaded columns into one **Features** column, which is used by a clustering trainer;</span></span>
- <span data-ttu-id="ffb6b-184">usar un instructor <xref:Microsoft.ML.Trainers.KMeans.KMeansPlusPlusTrainer> para entrenar el modelo mediante el algoritmo de agrupación en clústeres k-means++.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-184">use a <xref:Microsoft.ML.Trainers.KMeans.KMeansPlusPlusTrainer> trainer to train the model using the k-means++ clustering algorithm.</span></span>

<span data-ttu-id="ffb6b-185">Agregue el código siguiente al método `Main`:</span><span class="sxs-lookup"><span data-stu-id="ffb6b-185">Add the following code to the `Main` method:</span></span>

[!code-csharp[Create pipeline](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreatePipeline)]

<span data-ttu-id="ffb6b-186">En el código se especifica que el conjunto de datos se debe dividir en tres clústeres.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-186">The code specifies that the data set should be split in three clusters.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="ffb6b-187">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="ffb6b-187">Train the model</span></span>

<span data-ttu-id="ffb6b-188">Los pasos que se agregaron en las secciones anteriores prepararon la canalización para el aprendizaje, pero no se ha ejecutado ninguno.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-188">The steps added in the preceding sections prepared the pipeline for training, however, none have been executed.</span></span> <span data-ttu-id="ffb6b-189">Agregue la línea siguiente al método `Main` para realizar la carga de datos y el entrenamiento del modelo:</span><span class="sxs-lookup"><span data-stu-id="ffb6b-189">Add the following line to the `Main` method to perform data loading and model training:</span></span>

[!code-csharp[Train the model](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#TrainModel)]

### <a name="save-the-model"></a><span data-ttu-id="ffb6b-190">Guardado del modelo</span><span class="sxs-lookup"><span data-stu-id="ffb6b-190">Save the model</span></span>

<span data-ttu-id="ffb6b-191">En este punto, tiene un modelo que se puede integrar en cualquiera de las aplicaciones de .NET nuevas o existentes.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-191">At this point, you have a model that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="ffb6b-192">Para guardar el modelo en un archivo .zip, agregue el código siguiente al método `Main`:</span><span class="sxs-lookup"><span data-stu-id="ffb6b-192">To save your model to a .zip file, add the following code to the `Main` method:</span></span>

[!code-csharp[Save the model](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#SaveModel)]

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="ffb6b-193">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="ffb6b-193">Use the model for predictions</span></span>

<span data-ttu-id="ffb6b-194">Para realizar predicciones, use la clase <xref:Microsoft.ML.PredictionEngine%602>, que toma instancias del tipo de entrada a través de la canalización de transformador y genera instancias del tipo de salida.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-194">To make predictions, use the <xref:Microsoft.ML.PredictionEngine%602> class that takes instances of the input type through the transformer pipeline and produces instances of the output type.</span></span> <span data-ttu-id="ffb6b-195">Agregue la línea siguiente al método `Main` para crear una instancia de esa clase:</span><span class="sxs-lookup"><span data-stu-id="ffb6b-195">Add the following line to the `Main` method to create an instance of that class:</span></span>

[!code-csharp[Create predictor](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#Predictor)]

<span data-ttu-id="ffb6b-196">Cree la clase `TestIrisData` para guardar las instancias de datos de prueba:</span><span class="sxs-lookup"><span data-stu-id="ffb6b-196">Create the `TestIrisData` class to house test data instances:</span></span>

1. <span data-ttu-id="ffb6b-197">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-197">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="ffb6b-198">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *TestIrisData.cs*.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-198">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TestIrisData.cs*.</span></span> <span data-ttu-id="ffb6b-199">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-199">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="ffb6b-200">Modifique la clase para que sea estática, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ffb6b-200">Modify the class to be static like in the following example:</span></span>

   [!code-csharp[Make class static](~/samples/machine-learning/tutorials/IrisFlowerClustering/TestIrisData.cs#Static)]

<span data-ttu-id="ffb6b-201">En este tutorial se presenta una instancia de datos de iris dentro de esta clase.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-201">This tutorial introduces one iris data instance within this class.</span></span> <span data-ttu-id="ffb6b-202">Puede agregar otros escenarios para experimentar con el modelo.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-202">You can add other scenarios to experiment with the model.</span></span> <span data-ttu-id="ffb6b-203">Agregue el código siguiente a la clase `TestIrisData`:</span><span class="sxs-lookup"><span data-stu-id="ffb6b-203">Add the following code into the `TestIrisData` class:</span></span>

[!code-csharp[Test data](~/samples/machine-learning/tutorials/IrisFlowerClustering/TestIrisData.cs#TestData)]

<span data-ttu-id="ffb6b-204">Para determinar a qué clúster pertenece el elemento especificado, vuelva al archivo *Program.cs* y agregue el código siguiente al método `Main`:</span><span class="sxs-lookup"><span data-stu-id="ffb6b-204">To find out the cluster to which the specified item belongs to, go back to the *Program.cs* file and add the following code into the `Main` method:</span></span>

[!code-csharp[Predict and output results](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#PredictionExample)]

<span data-ttu-id="ffb6b-205">Ejecute el programa para ver qué clúster contiene la instancia de datos especificada y las distancias cuadradas desde esa instancia a los centroides de clúster.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-205">Run the program to see which cluster contains the specified data instance and squared distances from that instance to the cluster centroids.</span></span> <span data-ttu-id="ffb6b-206">Los resultados deberían ser similares a los indicados a continuación:</span><span class="sxs-lookup"><span data-stu-id="ffb6b-206">Your results should be similar to the following:</span></span>

```text
Cluster: 2
Distances: 11.69127 0.02159119 25.59896
```

<span data-ttu-id="ffb6b-207">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="ffb6b-207">Congratulations!</span></span> <span data-ttu-id="ffb6b-208">Ha creado correctamente un modelo de aprendizaje automático para la agrupación en clústeres de iris y lo ha usado para realizar predicciones.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-208">You've now successfully built a machine learning model for iris clustering and used it to make predictions.</span></span> <span data-ttu-id="ffb6b-209">Puede encontrar el código fuente de este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisFlowerClustering) de GitHub.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-209">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisFlowerClustering) GitHub repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ffb6b-210">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="ffb6b-210">Next steps</span></span>

<span data-ttu-id="ffb6b-211">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="ffb6b-211">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="ffb6b-212">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="ffb6b-212">Understand the problem</span></span>
> - <span data-ttu-id="ffb6b-213">Seleccionar la tarea de aprendizaje automático adecuada</span><span class="sxs-lookup"><span data-stu-id="ffb6b-213">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="ffb6b-214">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="ffb6b-214">Prepare the data</span></span>
> - <span data-ttu-id="ffb6b-215">Cargar y transformar los datos</span><span class="sxs-lookup"><span data-stu-id="ffb6b-215">Load and transform the data</span></span>
> - <span data-ttu-id="ffb6b-216">Elegir un algoritmo de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="ffb6b-216">Choose a learning algorithm</span></span>
> - <span data-ttu-id="ffb6b-217">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="ffb6b-217">Train the model</span></span>
> - <span data-ttu-id="ffb6b-218">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="ffb6b-218">Use the model for predictions</span></span>

<span data-ttu-id="ffb6b-219">Visite nuestro repositorio de GitHub para obtener más información y encontrar más ejemplos.</span><span class="sxs-lookup"><span data-stu-id="ffb6b-219">Check out our GitHub repository to continue learning and find more samples.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="ffb6b-220">Repositorio de GitHub de dotnet/machinelearning</span><span class="sxs-lookup"><span data-stu-id="ffb6b-220">dotnet/machinelearning GitHub repository</span></span>](https://github.com/dotnet/machinelearning/)
