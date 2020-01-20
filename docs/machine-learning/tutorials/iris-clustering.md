---
title: 'Tutorial: Clasificación de flores de iris (agrupación en clústeres k-means)'
description: Obtenga información sobre cómo usar ML.NET en un escenario de agrupación en clústeres
author: pkulikov
ms.date: 11/15/2019
ms.topic: tutorial
ms.custom: mvc, title-hack-0516
ms.openlocfilehash: cc3a1ae984289eb01ad8fdee9741f3f9788196c7
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716230"
---
# <a name="tutorial-categorize-iris-flowers-using-k-means-clustering-with-mlnet"></a><span data-ttu-id="72abd-103">Tutorial: Clasificación de flores de iris mediante la agrupación en clústeres k-means con ML.NET</span><span class="sxs-lookup"><span data-stu-id="72abd-103">Tutorial: Categorize iris flowers using k-means clustering with ML.NET</span></span>

<span data-ttu-id="72abd-104">En este tutorial se muestra cómo usar ML.NET para crear un [modelo de agrupación en clústeres](../resources/tasks.md#clustering) para el [conjunto de datos de flores de iris](https://en.wikipedia.org/wiki/Iris_flower_data_set).</span><span class="sxs-lookup"><span data-stu-id="72abd-104">This tutorial illustrates how to use ML.NET to build a [clustering model](../resources/tasks.md#clustering) for the [iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set).</span></span>

<span data-ttu-id="72abd-105">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="72abd-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="72abd-106">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="72abd-106">Understand the problem</span></span>
> - <span data-ttu-id="72abd-107">Seleccionar la tarea de aprendizaje automático adecuada</span><span class="sxs-lookup"><span data-stu-id="72abd-107">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="72abd-108">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="72abd-108">Prepare the data</span></span>
> - <span data-ttu-id="72abd-109">Cargar y transformar los datos</span><span class="sxs-lookup"><span data-stu-id="72abd-109">Load and transform the data</span></span>
> - <span data-ttu-id="72abd-110">Elegir un algoritmo de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="72abd-110">Choose a learning algorithm</span></span>
> - <span data-ttu-id="72abd-111">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="72abd-111">Train the model</span></span>
> - <span data-ttu-id="72abd-112">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="72abd-112">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="72abd-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="72abd-113">Prerequisites</span></span>

- <span data-ttu-id="72abd-114">[Visual Studio 2017, versión 15.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.</span><span class="sxs-lookup"><span data-stu-id="72abd-114">[Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="72abd-115">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="72abd-115">Understand the problem</span></span>

<span data-ttu-id="72abd-116">Este problema consiste en dividir el conjunto de flores de iris en grupos diferentes según las características de la flor.</span><span class="sxs-lookup"><span data-stu-id="72abd-116">This problem is about dividing the set of iris flowers in different groups based on the flower features.</span></span> <span data-ttu-id="72abd-117">Esas características son la longitud y el ancho del sépalo, y la longitud y ancho del pétalo.</span><span class="sxs-lookup"><span data-stu-id="72abd-117">Those features are the length and width of a sepal and the length and width of a petal.</span></span> <span data-ttu-id="72abd-118">Para este tutorial, se supone que el tipo de cada flor es desconocido.</span><span class="sxs-lookup"><span data-stu-id="72abd-118">For this tutorial, assume that the type of each flower is unknown.</span></span> <span data-ttu-id="72abd-119">Le interesa conocer la estructura de un conjunto de datos a partir de las características y predecir cómo se ajusta una instancia de datos a esta estructura.</span><span class="sxs-lookup"><span data-stu-id="72abd-119">You want to learn the structure of a data set from the features and predict how a data instance fits this structure.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="72abd-120">Seleccionar la tarea de aprendizaje automático adecuada</span><span class="sxs-lookup"><span data-stu-id="72abd-120">Select the appropriate machine learning task</span></span>

<span data-ttu-id="72abd-121">Como no se sabe a qué grupo pertenece cada flor, seleccione la tarea de [aprendizaje automático no supervisado](../resources/glossary.md#unsupervised-machine-learning).</span><span class="sxs-lookup"><span data-stu-id="72abd-121">As you don't know to which group each flower belongs to, you choose the [unsupervised machine learning](../resources/glossary.md#unsupervised-machine-learning) task.</span></span> <span data-ttu-id="72abd-122">Para dividir un conjunto de datos en grupos de manera que los elementos del mismo grupo sean más similares entre sí que con los de otros grupos, use una tarea de aprendizaje automático de [agrupación en clústeres](../resources/tasks.md#clustering).</span><span class="sxs-lookup"><span data-stu-id="72abd-122">To divide a data set in groups in such a way that elements in the same group are more similar to each other than to those in other groups, use a [clustering](../resources/tasks.md#clustering) machine learning task.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="72abd-123">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="72abd-123">Create a console application</span></span>

1. <span data-ttu-id="72abd-124">Abra Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="72abd-124">Open Visual Studio.</span></span> <span data-ttu-id="72abd-125">Seleccione **Archivo** > **Nuevo** > **Proyecto** de la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="72abd-125">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="72abd-126">En el cuadro de diálogo **Nuevo proyecto**, seleccione el nodo **Visual C#** seguido del nodo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="72abd-126">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="72abd-127">Después, seleccione la plantilla del proyecto **Aplicación de consola (.NET Core)** .</span><span class="sxs-lookup"><span data-stu-id="72abd-127">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="72abd-128">En el cuadro de texto **Nombre**, escriba "IrisFlowerClustering" y después haga clic en el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="72abd-128">In the **Name** text box, type "IrisFlowerClustering" and then select the **OK** button.</span></span>

1. <span data-ttu-id="72abd-129">Cree un directorio denominado *Datos* en el proyecto para almacenar el conjunto de datos y los archivos del modelo:</span><span class="sxs-lookup"><span data-stu-id="72abd-129">Create a directory named *Data* in your project to store the data set and model files:</span></span>

    <span data-ttu-id="72abd-130">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **Nueva carpeta**.</span><span class="sxs-lookup"><span data-stu-id="72abd-130">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="72abd-131">Escriba "Datos" y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="72abd-131">Type "Data" and hit Enter.</span></span>

1. <span data-ttu-id="72abd-132">Instale el paquete NuGet **Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="72abd-132">Install the **Microsoft.ML** NuGet package:</span></span>

    <span data-ttu-id="72abd-133">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="72abd-133">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="72abd-134">Elija "nuget.org" como origen del paquete, seleccione la pestaña **Examinar**, busque **Microsoft.ML** y seleccione el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="72abd-134">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML** and select the **Install** button.</span></span> <span data-ttu-id="72abd-135">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="72abd-135">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-the-data"></a><span data-ttu-id="72abd-136">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="72abd-136">Prepare the data</span></span>

1. <span data-ttu-id="72abd-137">Descargue el conjunto de datos [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) y guárdelo en la carpeta *Datos* que ha creado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="72abd-137">Download the [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) data set and save it to the *Data* folder you've created at the previous step.</span></span> <span data-ttu-id="72abd-138">Para obtener más información sobre el conjunto de datos de iris, vea la página de Wikipedia [Conjunto de datos de flor de Iris](https://en.wikipedia.org/wiki/Iris_flower_data_set) y la página [Iris Data Set](https://archive.ics.uci.edu/ml/datasets/Iris) (Conjunto de datos Iris), que es el origen del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="72abd-138">For more information about the iris data set, see the [Iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set) Wikipedia page and the [Iris Data Set](https://archive.ics.uci.edu/ml/datasets/Iris) page, which is the source of the data set.</span></span>

1. <span data-ttu-id="72abd-139">En el **Explorador de soluciones**, haga clic con el botón derecho en el archivo *iris.data* y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="72abd-139">In **Solution Explorer**, right-click the *iris.data* file and select **Properties**.</span></span> <span data-ttu-id="72abd-140">En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.</span><span class="sxs-lookup"><span data-stu-id="72abd-140">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="72abd-141">El archivo *iris.data* contiene cinco columnas que representan lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="72abd-141">The *iris.data* file contains five columns that represent:</span></span>

- <span data-ttu-id="72abd-142">La longitud del sépalo en centímetros.</span><span class="sxs-lookup"><span data-stu-id="72abd-142">sepal length in centimetres</span></span>
- <span data-ttu-id="72abd-143">El ancho del sépalo en centímetros.</span><span class="sxs-lookup"><span data-stu-id="72abd-143">sepal width in centimetres</span></span>
- <span data-ttu-id="72abd-144">La longitud del pétalo en centímetros.</span><span class="sxs-lookup"><span data-stu-id="72abd-144">petal length in centimetres</span></span>
- <span data-ttu-id="72abd-145">El ancho del pétalo en centímetros.</span><span class="sxs-lookup"><span data-stu-id="72abd-145">petal width in centimetres</span></span>
- <span data-ttu-id="72abd-146">El tipo de flor de iris.</span><span class="sxs-lookup"><span data-stu-id="72abd-146">type of iris flower</span></span>

<span data-ttu-id="72abd-147">Para el ejemplo de agrupación en clústeres, en este tutorial se ignora la última columna.</span><span class="sxs-lookup"><span data-stu-id="72abd-147">For the sake of the clustering example, this tutorial ignores the last column.</span></span>

## <a name="create-data-classes"></a><span data-ttu-id="72abd-148">Crear clases de datos</span><span class="sxs-lookup"><span data-stu-id="72abd-148">Create data classes</span></span>

<span data-ttu-id="72abd-149">Cree clases para los datos de entrada y las predicciones:</span><span class="sxs-lookup"><span data-stu-id="72abd-149">Create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="72abd-150">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="72abd-150">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="72abd-151">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *IrisData.cs*.</span><span class="sxs-lookup"><span data-stu-id="72abd-151">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *IrisData.cs*.</span></span> <span data-ttu-id="72abd-152">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="72abd-152">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="72abd-153">Agregue la directiva `using` siguiente al archivo nuevo:</span><span class="sxs-lookup"><span data-stu-id="72abd-153">Add the following `using` directive to the new file:</span></span>

   [!code-csharp[Add necessary usings](~/samples/machine-learning/tutorials/IrisFlowerClustering/IrisData.cs#Usings)]

<span data-ttu-id="72abd-154">Quite la definición de clase existente y agregue el código siguiente, que define dos clases `IrisData` y `ClusterPrediction`, al archivo *IrisData.cs*:</span><span class="sxs-lookup"><span data-stu-id="72abd-154">Remove the existing class definition and add the following code, which defines the classes `IrisData` and `ClusterPrediction`, to the *IrisData.cs* file:</span></span>

[!code-csharp[Define data classes](~/samples/machine-learning/tutorials/IrisFlowerClustering/IrisData.cs#ClassDefinitions)]

<span data-ttu-id="72abd-155">`IrisData` es la clase de datos de entrada y tiene definiciones para cada una de las características del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="72abd-155">`IrisData` is the input data class and has definitions for each feature from the data set.</span></span> <span data-ttu-id="72abd-156">Use el atributo [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute) para especificar los índices de las columnas de origen en el archivo de conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="72abd-156">Use the [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute) attribute to specify the indices of the source columns in the data set file.</span></span>

<span data-ttu-id="72abd-157">La clase `ClusterPrediction` representa el resultado del modelo de agrupación en clústeres aplicado a una instancia de `IrisData`.</span><span class="sxs-lookup"><span data-stu-id="72abd-157">The `ClusterPrediction` class represents the output of the clustering model applied to an `IrisData` instance.</span></span> <span data-ttu-id="72abd-158">Use el atributo [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute) para enlazar los campos `PredictedClusterId` y `Distances` a las columnas **PredictedLabel** y **Score** respectivamente.</span><span class="sxs-lookup"><span data-stu-id="72abd-158">Use the [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute to bind the `PredictedClusterId` and `Distances` fields to the **PredictedLabel** and **Score** columns respectively.</span></span> <span data-ttu-id="72abd-159">En el caso de la tarea de agrupación en clústeres, esas columnas tienen el significado siguiente:</span><span class="sxs-lookup"><span data-stu-id="72abd-159">In case of the clustering task those columns have the following meaning:</span></span>

- <span data-ttu-id="72abd-160">La columna **PredictedLabel** contiene el identificador del clúster previsto.</span><span class="sxs-lookup"><span data-stu-id="72abd-160">**PredictedLabel** column contains the ID of the predicted cluster.</span></span>
- <span data-ttu-id="72abd-161">La columna **Score** contiene una matriz con las distancias euclidianas cuadradas a los centroides de clúster.</span><span class="sxs-lookup"><span data-stu-id="72abd-161">**Score** column contains an array with squared Euclidean distances to the cluster centroids.</span></span> <span data-ttu-id="72abd-162">La longitud de la matriz es igual al número de clústeres.</span><span class="sxs-lookup"><span data-stu-id="72abd-162">The array length is equal to the number of clusters.</span></span>

> [!NOTE]
> <span data-ttu-id="72abd-163">Use el tipo `float` para representar los valores de punto flotante en las clases de entrada y predicción de datos.</span><span class="sxs-lookup"><span data-stu-id="72abd-163">Use the `float` type to represent floating-point values in the input and prediction data classes.</span></span>

## <a name="define-data-and-model-paths"></a><span data-ttu-id="72abd-164">Definir rutas de acceso de datos y modelos</span><span class="sxs-lookup"><span data-stu-id="72abd-164">Define data and model paths</span></span>

<span data-ttu-id="72abd-165">Vuelva al archivo *Program.cs* y agregue dos campos para contener las rutas de acceso al archivo de conjuntos de datos y al archivo en el que se guarda el modelo:</span><span class="sxs-lookup"><span data-stu-id="72abd-165">Go back to the *Program.cs* file and add two fields to hold the paths to the data set file and to the file to save the model:</span></span>

- <span data-ttu-id="72abd-166">`_dataPath` contiene la ruta de acceso al archivo con el conjunto de datos utilizado para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="72abd-166">`_dataPath` contains the path to the file with the data set used to train the model.</span></span>
- <span data-ttu-id="72abd-167">`_modelPath` contiene la ruta de acceso al archivo en el que se almacena el modelo entrenado.</span><span class="sxs-lookup"><span data-stu-id="72abd-167">`_modelPath` contains the path to the file where the trained model is stored.</span></span>

<span data-ttu-id="72abd-168">Agregue el código siguiente justo encima del método `Main` para especificar las rutas de acceso:</span><span class="sxs-lookup"><span data-stu-id="72abd-168">Add the following code right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Initialize paths](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#Paths)]

<span data-ttu-id="72abd-169">Para que el código anterior se compile, agregue las directivas `using` siguientes a la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="72abd-169">To make the preceding code compile, add the following `using` directives at the top of the *Program.cs* file:</span></span>

[!code-csharp[Add usings for paths](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#UsingsForPaths)]

## <a name="create-ml-context"></a><span data-ttu-id="72abd-170">Creación del contexto de ML</span><span class="sxs-lookup"><span data-stu-id="72abd-170">Create ML context</span></span>

<span data-ttu-id="72abd-171">Agregue las directivas `using` adicionales siguientes a la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="72abd-171">Add the following additional `using` directives to the top of the *Program.cs* file:</span></span>

[!code-csharp[Add Microsoft.ML usings](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#MLUsings)]

<span data-ttu-id="72abd-172">En el método `Main`, reemplace la línea `Console.WriteLine("Hello World!");` con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="72abd-172">In the `Main` method, replace the `Console.WriteLine("Hello World!");` line with the following code:</span></span>

[!code-csharp[Create ML context](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreateContext)]

<span data-ttu-id="72abd-173">La clase <xref:Microsoft.ML.MLContext?displayProperty=nameWithType> representa el entorno de aprendizaje automático y proporciona mecanismos para puntos de entrada y de registro para la carga de datos, entrenamiento del modelo, predicción y otras tareas.</span><span class="sxs-lookup"><span data-stu-id="72abd-173">The <xref:Microsoft.ML.MLContext?displayProperty=nameWithType> class represents the machine learning environment and provides mechanisms for logging and entry points for data loading, model training, prediction, and other tasks.</span></span> <span data-ttu-id="72abd-174">Esto es comparable conceptualmente a usar `DbContext` en Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="72abd-174">This is comparable conceptually to using `DbContext` in Entity Framework.</span></span>

## <a name="set-up-data-loading"></a><span data-ttu-id="72abd-175">Configuración de la carga de datos</span><span class="sxs-lookup"><span data-stu-id="72abd-175">Set up data loading</span></span>

<span data-ttu-id="72abd-176">Agregue el código siguiente al método `Main` para configurar la manera de cargar los datos:</span><span class="sxs-lookup"><span data-stu-id="72abd-176">Add the following code to the `Main` method to set up the way to load data:</span></span>

[!code-csharp[Create text loader](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreateDataView)]

<span data-ttu-id="72abd-177">El [`MLContext.Data.LoadFromTextFile` método de extensión](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) genérico deduce el esquema del conjunto de datos del tipo `IrisData` proporcionado y devuelve <xref:Microsoft.ML.IDataView>, que se puede usar como entrada para los transformadores.</span><span class="sxs-lookup"><span data-stu-id="72abd-177">The generic [`MLContext.Data.LoadFromTextFile` extension method](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) infers the data set schema from the provided `IrisData` type and returns <xref:Microsoft.ML.IDataView> which can be used as input for transformers.</span></span>

## <a name="create-a-learning-pipeline"></a><span data-ttu-id="72abd-178">Crear una canalización de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="72abd-178">Create a learning pipeline</span></span>

<span data-ttu-id="72abd-179">Para este tutorial, la canalización de aprendizaje de la tarea de agrupación en clústeres consta de los dos pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="72abd-179">For this tutorial, the learning pipeline of the clustering task comprises two following steps:</span></span>

- <span data-ttu-id="72abd-180">concatenar las columnas cargadas en una columna **Características**, que usa un instructor de agrupación en clústeres;</span><span class="sxs-lookup"><span data-stu-id="72abd-180">concatenate loaded columns into one **Features** column, which is used by a clustering trainer;</span></span>
- <span data-ttu-id="72abd-181">usar un instructor <xref:Microsoft.ML.Trainers.KMeansTrainer> para entrenar el modelo mediante el algoritmo de agrupación en clústeres k-means++.</span><span class="sxs-lookup"><span data-stu-id="72abd-181">use a <xref:Microsoft.ML.Trainers.KMeansTrainer> trainer to train the model using the k-means++ clustering algorithm.</span></span>

<span data-ttu-id="72abd-182">Agregue el código siguiente al método `Main`:</span><span class="sxs-lookup"><span data-stu-id="72abd-182">Add the following code to the `Main` method:</span></span>

[!code-csharp[Create pipeline](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreatePipeline)]

<span data-ttu-id="72abd-183">En el código se especifica que el conjunto de datos se debe dividir en tres clústeres.</span><span class="sxs-lookup"><span data-stu-id="72abd-183">The code specifies that the data set should be split in three clusters.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="72abd-184">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="72abd-184">Train the model</span></span>

<span data-ttu-id="72abd-185">Los pasos que se agregaron en las secciones anteriores prepararon la canalización para el aprendizaje, pero no se ha ejecutado ninguno.</span><span class="sxs-lookup"><span data-stu-id="72abd-185">The steps added in the preceding sections prepared the pipeline for training, however, none have been executed.</span></span> <span data-ttu-id="72abd-186">Agregue la línea siguiente al método `Main` para realizar la carga de datos y el entrenamiento del modelo:</span><span class="sxs-lookup"><span data-stu-id="72abd-186">Add the following line to the `Main` method to perform data loading and model training:</span></span>

[!code-csharp[Train the model](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#TrainModel)]

### <a name="save-the-model"></a><span data-ttu-id="72abd-187">Guardado del modelo</span><span class="sxs-lookup"><span data-stu-id="72abd-187">Save the model</span></span>

<span data-ttu-id="72abd-188">En este punto, tiene un modelo que se puede integrar en cualquiera de las aplicaciones de .NET nuevas o existentes.</span><span class="sxs-lookup"><span data-stu-id="72abd-188">At this point, you have a model that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="72abd-189">Para guardar el modelo en un archivo .zip, agregue el código siguiente al método `Main`:</span><span class="sxs-lookup"><span data-stu-id="72abd-189">To save your model to a .zip file, add the following code to the `Main` method:</span></span>

[!code-csharp[Save the model](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#SaveModel)]

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="72abd-190">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="72abd-190">Use the model for predictions</span></span>

<span data-ttu-id="72abd-191">Para realizar predicciones, use la clase <xref:Microsoft.ML.PredictionEngine%602>, que toma instancias del tipo de entrada a través de la canalización de transformador y genera instancias del tipo de salida.</span><span class="sxs-lookup"><span data-stu-id="72abd-191">To make predictions, use the <xref:Microsoft.ML.PredictionEngine%602> class that takes instances of the input type through the transformer pipeline and produces instances of the output type.</span></span> <span data-ttu-id="72abd-192">Agregue la línea siguiente al método `Main` para crear una instancia de esa clase:</span><span class="sxs-lookup"><span data-stu-id="72abd-192">Add the following line to the `Main` method to create an instance of that class:</span></span>

[!code-csharp[Create predictor](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#Predictor)]

<span data-ttu-id="72abd-193">[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) es una API de conveniencia, que le permite realizar una predicción en una única instancia de datos.</span><span class="sxs-lookup"><span data-stu-id="72abd-193">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to perform a prediction on a single instance of data.</span></span> <span data-ttu-id="72abd-194">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) no es seguro para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="72abd-194">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="72abd-195">Es aceptable usarlo en entornos de un solo subproceso o prototipo.</span><span class="sxs-lookup"><span data-stu-id="72abd-195">It's acceptable to use in single-threaded or prototype environments.</span></span> <span data-ttu-id="72abd-196">Para mejorar el rendimiento y la seguridad para subprocesos en entornos de producción, use el servicio `PredictionEnginePool`, que crea un [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) de objetos de [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) para su uso en toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="72abd-196">For improved performance and thread safety in production environments, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span> <span data-ttu-id="72abd-197">Consulte esta guía sobre cómo [usar `PredictionEnginePool` en una API web de ASP.NET Core](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span><span class="sxs-lookup"><span data-stu-id="72abd-197">See this guide on how to [use `PredictionEnginePool` in an ASP.NET Core Web API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span></span>

> [!NOTE]
> <span data-ttu-id="72abd-198">La extensión del servicio `PredictionEnginePool` está actualmente en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="72abd-198">`PredictionEnginePool` service extension is currently in preview.</span></span>

<span data-ttu-id="72abd-199">Cree la clase `TestIrisData` para guardar las instancias de datos de prueba:</span><span class="sxs-lookup"><span data-stu-id="72abd-199">Create the `TestIrisData` class to house test data instances:</span></span>

1. <span data-ttu-id="72abd-200">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="72abd-200">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="72abd-201">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *TestIrisData.cs*.</span><span class="sxs-lookup"><span data-stu-id="72abd-201">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TestIrisData.cs*.</span></span> <span data-ttu-id="72abd-202">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="72abd-202">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="72abd-203">Modifique la clase para que sea estática, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="72abd-203">Modify the class to be static like in the following example:</span></span>

   [!code-csharp[Make class static](~/samples/machine-learning/tutorials/IrisFlowerClustering/TestIrisData.cs#Static)]

<span data-ttu-id="72abd-204">En este tutorial se presenta una instancia de datos de iris dentro de esta clase.</span><span class="sxs-lookup"><span data-stu-id="72abd-204">This tutorial introduces one iris data instance within this class.</span></span> <span data-ttu-id="72abd-205">Puede agregar otros escenarios para experimentar con el modelo.</span><span class="sxs-lookup"><span data-stu-id="72abd-205">You can add other scenarios to experiment with the model.</span></span> <span data-ttu-id="72abd-206">Agregue el código siguiente a la clase `TestIrisData`:</span><span class="sxs-lookup"><span data-stu-id="72abd-206">Add the following code into the `TestIrisData` class:</span></span>

[!code-csharp[Test data](~/samples/machine-learning/tutorials/IrisFlowerClustering/TestIrisData.cs#TestData)]

<span data-ttu-id="72abd-207">Para determinar a qué clúster pertenece el elemento especificado, vuelva al archivo *Program.cs* y agregue el código siguiente al método `Main`:</span><span class="sxs-lookup"><span data-stu-id="72abd-207">To find out the cluster to which the specified item belongs to, go back to the *Program.cs* file and add the following code into the `Main` method:</span></span>

[!code-csharp[Predict and output results](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#PredictionExample)]

<span data-ttu-id="72abd-208">Ejecute el programa para ver qué clúster contiene la instancia de datos especificada y las distancias cuadradas desde esa instancia a los centroides de clúster.</span><span class="sxs-lookup"><span data-stu-id="72abd-208">Run the program to see which cluster contains the specified data instance and squared distances from that instance to the cluster centroids.</span></span> <span data-ttu-id="72abd-209">Los resultados deberían ser similares a los indicados a continuación:</span><span class="sxs-lookup"><span data-stu-id="72abd-209">Your results should be similar to the following:</span></span>

```text
Cluster: 2
Distances: 11.69127 0.02159119 25.59896
```

<span data-ttu-id="72abd-210">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="72abd-210">Congratulations!</span></span> <span data-ttu-id="72abd-211">Ha creado correctamente un modelo de aprendizaje automático para la agrupación en clústeres de iris y lo ha usado para realizar predicciones.</span><span class="sxs-lookup"><span data-stu-id="72abd-211">You've now successfully built a machine learning model for iris clustering and used it to make predictions.</span></span> <span data-ttu-id="72abd-212">Puede encontrar el código fuente de este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisFlowerClustering) de GitHub.</span><span class="sxs-lookup"><span data-stu-id="72abd-212">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisFlowerClustering) GitHub repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="72abd-213">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="72abd-213">Next steps</span></span>

<span data-ttu-id="72abd-214">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="72abd-214">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="72abd-215">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="72abd-215">Understand the problem</span></span>
> - <span data-ttu-id="72abd-216">Seleccionar la tarea de aprendizaje automático adecuada</span><span class="sxs-lookup"><span data-stu-id="72abd-216">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="72abd-217">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="72abd-217">Prepare the data</span></span>
> - <span data-ttu-id="72abd-218">Cargar y transformar los datos</span><span class="sxs-lookup"><span data-stu-id="72abd-218">Load and transform the data</span></span>
> - <span data-ttu-id="72abd-219">Elegir un algoritmo de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="72abd-219">Choose a learning algorithm</span></span>
> - <span data-ttu-id="72abd-220">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="72abd-220">Train the model</span></span>
> - <span data-ttu-id="72abd-221">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="72abd-221">Use the model for predictions</span></span>

<span data-ttu-id="72abd-222">Visite nuestro repositorio de GitHub para obtener más información y encontrar más ejemplos.</span><span class="sxs-lookup"><span data-stu-id="72abd-222">Check out our GitHub repository to continue learning and find more samples.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="72abd-223">Repositorio de GitHub de dotnet/machinelearning</span><span class="sxs-lookup"><span data-stu-id="72abd-223">dotnet/machinelearning GitHub repository</span></span>](https://github.com/dotnet/machinelearning/)
