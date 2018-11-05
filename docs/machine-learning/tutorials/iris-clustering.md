---
title: Uso de ML.NET para agrupar flores de iris en clústeres (agrupación en clústeres)
description: Obtenga información sobre cómo usar ML.NET en un escenario de agrupación en clústeres
author: pkulikov
ms.author: johalex
ms.date: 07/02/2018
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: bb41fd317507c14b46aea94e1ce576e390932a65
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/19/2018
ms.locfileid: "49453195"
---
# <a name="tutorial-use-mlnet-to-cluster-iris-flowers-clustering"></a><span data-ttu-id="d14f3-103">Tutorial: Uso de ML.NET para agrupar flores de iris en clústeres (agrupación en clústeres)</span><span class="sxs-lookup"><span data-stu-id="d14f3-103">Tutorial: Use ML.NET to cluster iris flowers (clustering)</span></span>

> [!NOTE]
> <span data-ttu-id="d14f3-104">Este tema hace referencia a ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios.</span><span class="sxs-lookup"><span data-stu-id="d14f3-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="d14f3-105">Para obtener más información, vea [la introducción de ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="d14f3-105">For more information, see the [ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="d14f3-106">En este tutorial se muestra cómo usar ML.NET para crear un [modelo de agrupación en clústeres](../resources/tasks.md#clustering) para el [conjunto de datos de flores de iris](https://en.wikipedia.org/wiki/Iris_flower_data_set).</span><span class="sxs-lookup"><span data-stu-id="d14f3-106">This tutorial illustrates how to use ML.NET to build a [clustering model](../resources/tasks.md#clustering) for the [iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set).</span></span>

<span data-ttu-id="d14f3-107">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="d14f3-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="d14f3-108">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="d14f3-108">Understand the problem</span></span>
> - <span data-ttu-id="d14f3-109">Seleccionar la tarea de aprendizaje automático adecuada</span><span class="sxs-lookup"><span data-stu-id="d14f3-109">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="d14f3-110">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="d14f3-110">Prepare the data</span></span>
> - <span data-ttu-id="d14f3-111">Cargar y transformar los datos</span><span class="sxs-lookup"><span data-stu-id="d14f3-111">Load and transform the data</span></span>
> - <span data-ttu-id="d14f3-112">Elegir un algoritmo de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="d14f3-112">Choose a learning algorithm</span></span>
> - <span data-ttu-id="d14f3-113">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="d14f3-113">Train the model</span></span>
> - <span data-ttu-id="d14f3-114">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="d14f3-114">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d14f3-115">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d14f3-115">Prerequisites</span></span>

- <span data-ttu-id="d14f3-116">[Visual Studio 2017 15.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.</span><span class="sxs-lookup"><span data-stu-id="d14f3-116">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="d14f3-117">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="d14f3-117">Understand the problem</span></span>

<span data-ttu-id="d14f3-118">Este problema consiste en dividir el conjunto de flores de iris en grupos diferentes según las características de la flor.</span><span class="sxs-lookup"><span data-stu-id="d14f3-118">This problem is about dividing the set of iris flowers in different groups based on the flower features.</span></span> <span data-ttu-id="d14f3-119">Esas características son la longitud y el ancho del sépalo, y la longitud y ancho del pétalo.</span><span class="sxs-lookup"><span data-stu-id="d14f3-119">Those features are the length and width of a sepal and the length and width of a petal.</span></span> <span data-ttu-id="d14f3-120">Para este tutorial, se supone que el tipo de cada flor es desconocido.</span><span class="sxs-lookup"><span data-stu-id="d14f3-120">For this tutorial, assume that the type of each flower is unknown.</span></span> <span data-ttu-id="d14f3-121">Le interesa conocer la estructura de un conjunto de datos a partir de las características y predecir cómo se ajusta una instancia de datos a esta estructura.</span><span class="sxs-lookup"><span data-stu-id="d14f3-121">You want to learn the structure of a data set from the features and predict how a data instance fits this structure.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="d14f3-122">Seleccionar la tarea de aprendizaje automático adecuada</span><span class="sxs-lookup"><span data-stu-id="d14f3-122">Select the appropriate machine learning task</span></span>

<span data-ttu-id="d14f3-123">Como no se sabe a qué grupo pertenece cada flor, seleccione la tarea de [aprendizaje automático no supervisado](../resources/glossary.md#unsupervised-machine-learning).</span><span class="sxs-lookup"><span data-stu-id="d14f3-123">As you don't know to which group each flower belongs to, you choose the [unsupervised machine learning](../resources/glossary.md#unsupervised-machine-learning) task.</span></span> <span data-ttu-id="d14f3-124">Para dividir un conjunto de datos en grupos de manera que los elementos del mismo grupo sean más similares entre sí que con los de otros grupos, use una tarea de aprendizaje automático de [agrupación en clústeres](../resources/tasks.md#clustering).</span><span class="sxs-lookup"><span data-stu-id="d14f3-124">To divide a data set in groups in such a way that elements in the same group are more similar to each other than to those in other groups, use a [clustering](../resources/tasks.md#clustering) machine learning task.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="d14f3-125">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="d14f3-125">Create a console application</span></span>

1. <span data-ttu-id="d14f3-126">Abra Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="d14f3-126">Open Visual Studio 2017.</span></span> <span data-ttu-id="d14f3-127">Seleccione **Archivo** > **Nuevo** > **Proyecto** de la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="d14f3-127">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="d14f3-128">En el cuadro de diálogo **Nuevo proyecto**, seleccione el nodo **Visual C#** seguido del nodo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="d14f3-128">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="d14f3-129">Después, seleccione la plantilla del proyecto **Aplicación de consola (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="d14f3-129">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="d14f3-130">En el cuadro de texto **Nombre**, escriba "IrisClustering" y después haga clic en el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d14f3-130">In the **Name** text box, type "IrisClustering" and then select the **OK** button.</span></span>

1. <span data-ttu-id="d14f3-131">Cree un directorio denominado *Datos* en el proyecto para almacenar el conjunto de datos y los archivos del modelo:</span><span class="sxs-lookup"><span data-stu-id="d14f3-131">Create a directory named *Data* in your project to store the data set and model files:</span></span>

    <span data-ttu-id="d14f3-132">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **Nueva carpeta**.</span><span class="sxs-lookup"><span data-stu-id="d14f3-132">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="d14f3-133">Escriba "Datos" y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="d14f3-133">Type "Data" and hit Enter.</span></span>

1. <span data-ttu-id="d14f3-134">Instale el paquete NuGet **Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="d14f3-134">Install the **Microsoft.ML** NuGet package:</span></span>

    <span data-ttu-id="d14f3-135">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="d14f3-135">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="d14f3-136">Elija "nuget.org" como origen del paquete, seleccione la pestaña **Examinar**, busque **Microsoft.ML**, seleccione ese paquete en la lista y haga clic en el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="d14f3-136">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="d14f3-137">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="d14f3-137">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-the-data"></a><span data-ttu-id="d14f3-138">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="d14f3-138">Prepare the data</span></span>

1. <span data-ttu-id="d14f3-139">Descargue el conjunto de datos [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) y guárdelo en la carpeta *Datos* que ha creado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="d14f3-139">Download the [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) data set and save it to the *Data* folder you've created at the previous step.</span></span> <span data-ttu-id="d14f3-140">Para obtener más información sobre el conjunto de datos de iris, vea la página de Wikipedia [Conjunto de datos de flor de Iris](https://en.wikipedia.org/wiki/Iris_flower_data_set) y la página [Iris Data Set](http://archive.ics.uci.edu/ml/datasets/Iris) (Conjunto de datos Iris), que es el origen del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="d14f3-140">For more information about the iris data set, see the [Iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set) Wikipedia page and the [Iris Data Set](http://archive.ics.uci.edu/ml/datasets/Iris) page, which is the source of the data set.</span></span>

1. <span data-ttu-id="d14f3-141">En el **Explorador de soluciones**, haga clic con el botón derecho en el archivo *iris.data* y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d14f3-141">In **Solution Explorer**, right-click the *iris.data* file and select **Properties**.</span></span> <span data-ttu-id="d14f3-142">En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.</span><span class="sxs-lookup"><span data-stu-id="d14f3-142">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="d14f3-143">El archivo *iris.data* contiene cinco columnas que representan lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d14f3-143">The *iris.data* file contains five columns that represent:</span></span>

- <span data-ttu-id="d14f3-144">La longitud del sépalo en centímetros.</span><span class="sxs-lookup"><span data-stu-id="d14f3-144">sepal length in centimetres</span></span>
- <span data-ttu-id="d14f3-145">El ancho del sépalo en centímetros.</span><span class="sxs-lookup"><span data-stu-id="d14f3-145">sepal width in centimetres</span></span>
- <span data-ttu-id="d14f3-146">La longitud del pétalo en centímetros.</span><span class="sxs-lookup"><span data-stu-id="d14f3-146">petal length in centimetres</span></span>
- <span data-ttu-id="d14f3-147">El ancho del pétalo en centímetros.</span><span class="sxs-lookup"><span data-stu-id="d14f3-147">petal width in centimetres</span></span>
- <span data-ttu-id="d14f3-148">El tipo de flor de iris.</span><span class="sxs-lookup"><span data-stu-id="d14f3-148">type of iris flower</span></span>

<span data-ttu-id="d14f3-149">Para el ejemplo de agrupación en clústeres, en este tutorial se ignora la última columna.</span><span class="sxs-lookup"><span data-stu-id="d14f3-149">For the sake of the clustering example, this tutorial ignores the last column.</span></span>

## <a name="create-data-classes"></a><span data-ttu-id="d14f3-150">Crear clases de datos</span><span class="sxs-lookup"><span data-stu-id="d14f3-150">Create data classes</span></span>

<span data-ttu-id="d14f3-151">Cree clases para los datos de entrada y las predicciones:</span><span class="sxs-lookup"><span data-stu-id="d14f3-151">Create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="d14f3-152">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="d14f3-152">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="d14f3-153">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *IrisData.cs*.</span><span class="sxs-lookup"><span data-stu-id="d14f3-153">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *IrisData.cs*.</span></span> <span data-ttu-id="d14f3-154">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="d14f3-154">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="d14f3-155">Agregue la directiva `using` siguiente al archivo nuevo:</span><span class="sxs-lookup"><span data-stu-id="d14f3-155">Add the following `using` directive to the new file:</span></span>

   [!code-csharp[Add necessary usings](../../../samples/machine-learning/tutorials/IrisClustering/IrisData.cs#1)]

<span data-ttu-id="d14f3-156">Quite la definición de clase existente y agregue el código siguiente, que define dos clases `IrisData` y `ClusterPrediction`, al archivo *IrisData.cs*:</span><span class="sxs-lookup"><span data-stu-id="d14f3-156">Remove the existing class definition and add the following code, which defines the classes `IrisData` and `ClusterPrediction`, to the *IrisData.cs* file:</span></span>

[!code-csharp[Define data classes](../../../samples/machine-learning/tutorials/IrisClustering/IrisData.cs#2)]

<span data-ttu-id="d14f3-157">`IrisData` es la clase de datos de entrada y tiene definiciones para cada una de las características del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="d14f3-157">`IrisData` is the input data class and has definitions for each feature from the data set.</span></span> <span data-ttu-id="d14f3-158">Use el atributo [Column](xref:Microsoft.ML.Runtime.Api.ColumnAttribute) para especificar los índices de las columnas de origen en el archivo de conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="d14f3-158">Use the [Column](xref:Microsoft.ML.Runtime.Api.ColumnAttribute) attribute to specify the indices of the source columns in the data set file.</span></span>

<span data-ttu-id="d14f3-159">La clase `ClusterPrediction` representa el resultado del modelo de agrupación en clústeres aplicado a una instancia de `IrisData`.</span><span class="sxs-lookup"><span data-stu-id="d14f3-159">The `ClusterPrediction` class represents the output of the clustering model applied to an `IrisData` instance.</span></span> <span data-ttu-id="d14f3-160">Use el atributo [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute) para enlazar los campos `PredictedClusterId` y `Distances` a las columnas **PredictedLabel** y **Score** respectivamente.</span><span class="sxs-lookup"><span data-stu-id="d14f3-160">Use the [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute) attribute to bind the `PredictedClusterId` and `Distances` fields to the **PredictedLabel** and **Score** columns respectively.</span></span> <span data-ttu-id="d14f3-161">En el caso de la tarea de agrupación en clústeres, esas columnas tienen el significado siguiente:</span><span class="sxs-lookup"><span data-stu-id="d14f3-161">In case of the clustering task those columns have the following meaning:</span></span>

- <span data-ttu-id="d14f3-162">La columna **PredictedLabel** contiene el identificador del clúster previsto.</span><span class="sxs-lookup"><span data-stu-id="d14f3-162">**PredictedLabel** column contains the ID of the predicted cluster.</span></span>
- <span data-ttu-id="d14f3-163">La columna **Score** contiene una matriz con las distancias euclidianas cuadradas a los centroides de clúster.</span><span class="sxs-lookup"><span data-stu-id="d14f3-163">**Score** column contains an array with squared Euclidean distances to the cluster centroids.</span></span> <span data-ttu-id="d14f3-164">La longitud de la matriz es igual al número de clústeres.</span><span class="sxs-lookup"><span data-stu-id="d14f3-164">The array length is equal to the number of clusters.</span></span>

> [!NOTE]
> <span data-ttu-id="d14f3-165">Use el tipo `float` para representar los valores de punto flotante en las clases de entrada y predicción de datos.</span><span class="sxs-lookup"><span data-stu-id="d14f3-165">Use the `float` type to represent floating-point values in the input and prediction data classes.</span></span>

## <a name="define-data-and-model-paths"></a><span data-ttu-id="d14f3-166">Definir rutas de acceso de datos y modelos</span><span class="sxs-lookup"><span data-stu-id="d14f3-166">Define data and model paths</span></span>

<span data-ttu-id="d14f3-167">Vuelva al archivo *Program.cs* y agregue dos campos para contener las rutas de acceso al archivo de conjuntos de datos y al archivo en el que se guarda el modelo:</span><span class="sxs-lookup"><span data-stu-id="d14f3-167">Go back to the *Program.cs* file and add two fields to hold the paths to the data set file and to the file to save the model:</span></span>

- <span data-ttu-id="d14f3-168">`_dataPath` contiene la ruta de acceso al archivo con el conjunto de datos utilizado para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="d14f3-168">`_dataPath` contains the path to the file with the data set used to train the model.</span></span>
- <span data-ttu-id="d14f3-169">`_modelPath` contiene la ruta de acceso al archivo en el que se almacena el modelo entrenado.</span><span class="sxs-lookup"><span data-stu-id="d14f3-169">`_modelPath` contains the path to the file where the trained model is stored.</span></span>

<span data-ttu-id="d14f3-170">Agregue el código siguiente justo encima del método `Main` para especificar las rutas de acceso:</span><span class="sxs-lookup"><span data-stu-id="d14f3-170">Add the following code right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Initialize paths](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#1)]

<span data-ttu-id="d14f3-171">Para que el código anterior se compile, agregue las directivas `using` siguientes a la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="d14f3-171">To make the preceding code compile, add the following `using` directives at the top of the *Program.cs* file:</span></span>

[!code-csharp[Add usings for paths](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#2)]

## <a name="create-a-learning-pipeline"></a><span data-ttu-id="d14f3-172">Crear una canalización de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="d14f3-172">Create a learning pipeline</span></span>

<span data-ttu-id="d14f3-173">Agregue las directivas `using` adicionales siguientes a la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="d14f3-173">Add the following additional `using` directives to the top of the *Program.cs* file:</span></span>

[!code-csharp[Add Microsoft.ML usings](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#3)]

<span data-ttu-id="d14f3-174">En el método `Main`, reemplace `Console.WriteLine("Hello World!")` por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="d14f3-174">In the `Main` method, replace the `Console.WriteLine("Hello World!")` with the following code:</span></span>

[!code-csharp[Call the Train method](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#4)]

<span data-ttu-id="d14f3-175">El método `Train` entrena el modelo.</span><span class="sxs-lookup"><span data-stu-id="d14f3-175">The `Train` method trains the model.</span></span> <span data-ttu-id="d14f3-176">Cree ese método justo debajo del método `Main`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="d14f3-176">Create that method just below the `Main` method, using the following code:</span></span>

```csharp
private static PredictionModel<IrisData, ClusterPrediction> Train()
{

}
```

<span data-ttu-id="d14f3-177">La canalización de aprendizaje carga todos los datos y algoritmos necesarios para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="d14f3-177">The learning pipeline loads all of the data and algorithms necessary to train the model.</span></span> <span data-ttu-id="d14f3-178">Agregue el código siguiente al método `Train`:</span><span class="sxs-lookup"><span data-stu-id="d14f3-178">Add the following code into the `Train` method:</span></span>

[!code-csharp[Initialize pipeline](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#5)]

## <a name="load-and-transform-data"></a><span data-ttu-id="d14f3-179">Cargar y transformar datos</span><span class="sxs-lookup"><span data-stu-id="d14f3-179">Load and transform data</span></span>

<span data-ttu-id="d14f3-180">El primer paso que se va a realizar es cargar el conjunto de datos de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="d14f3-180">The first step to perform is to load the training data set.</span></span> <span data-ttu-id="d14f3-181">En nuestro caso, el conjunto de datos de aprendizaje se almacena en el archivo de texto con una ruta de acceso definida por el campo `_dataPath`.</span><span class="sxs-lookup"><span data-stu-id="d14f3-181">In our case, the training data set is stored in the text file with a path defined by the `_dataPath` field.</span></span> <span data-ttu-id="d14f3-182">En el archivo, las columnas se separan mediante una coma (",").</span><span class="sxs-lookup"><span data-stu-id="d14f3-182">Columns in the file are separated by the comma (",").</span></span> <span data-ttu-id="d14f3-183">Agregue el código siguiente al método `Train`:</span><span class="sxs-lookup"><span data-stu-id="d14f3-183">Add the following code into the `Train` method:</span></span>

[!code-csharp[Add step to load data](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#6)]

<span data-ttu-id="d14f3-184">El siguiente paso consiste en combinar todas las columnas de característica en la columna **Features** mediante la clase de transformación <xref:Microsoft.ML.Legacy.Transforms.ColumnConcatenator>.</span><span class="sxs-lookup"><span data-stu-id="d14f3-184">The next step is to combine all of the feature columns into the **Features** column using the <xref:Microsoft.ML.Legacy.Transforms.ColumnConcatenator> transformation class.</span></span> <span data-ttu-id="d14f3-185">De forma predeterminada, un algoritmo de aprendizaje solo procesa las características de la columna **Features**.</span><span class="sxs-lookup"><span data-stu-id="d14f3-185">By default, a learning algorithm processes only features from the **Features** column.</span></span> <span data-ttu-id="d14f3-186">Agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="d14f3-186">Add the following code:</span></span>

[!code-csharp[Add step to concatenate columns](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#7)]

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="d14f3-187">Elegir un algoritmo de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="d14f3-187">Choose a learning algorithm</span></span>

<span data-ttu-id="d14f3-188">Después de agregar los datos a la canalización y transformarlos en el formato de entrada correcto, seleccione un algoritmo de aprendizaje (**aprendiz**).</span><span class="sxs-lookup"><span data-stu-id="d14f3-188">After adding the data to the pipeline and transforming it into the correct input format, you select a learning algorithm (**learner**).</span></span> <span data-ttu-id="d14f3-189">El aprendiz entrena el modelo.</span><span class="sxs-lookup"><span data-stu-id="d14f3-189">The learner trains the model.</span></span> <span data-ttu-id="d14f3-190">ML.NET proporciona un aprendiz <xref:Microsoft.ML.Legacy.Trainers.KMeansPlusPlusClusterer> que implementa el [algoritmo k-means](https://en.wikipedia.org/wiki/K-means_clustering) con un método mejorado para elegir los centroides de clúster iniciales.</span><span class="sxs-lookup"><span data-stu-id="d14f3-190">ML.NET provides a <xref:Microsoft.ML.Legacy.Trainers.KMeansPlusPlusClusterer> learner that implements [k-means algorithm](https://en.wikipedia.org/wiki/K-means_clustering) with an improved method for choosing the initial cluster centroids.</span></span>

<span data-ttu-id="d14f3-191">Agregue el código siguiente al método `Train` después del código de procesamiento de datos que ha agregado en el paso anterior:</span><span class="sxs-lookup"><span data-stu-id="d14f3-191">Add the following code into the `Train` method following the data processing code added in the previous step:</span></span>

[!code-csharp[Add a learner step](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#8)]

<span data-ttu-id="d14f3-192">Use la propiedad <xref:Microsoft.ML.Legacy.Trainers.KMeansPlusPlusClusterer.K?displayProperty=nameWithType> para especificar el número de clústeres.</span><span class="sxs-lookup"><span data-stu-id="d14f3-192">Use the <xref:Microsoft.ML.Legacy.Trainers.KMeansPlusPlusClusterer.K?displayProperty=nameWithType> property to specify number of clusters.</span></span> <span data-ttu-id="d14f3-193">En el código anterior se especifica que el conjunto de datos se debe dividir en tres clústeres.</span><span class="sxs-lookup"><span data-stu-id="d14f3-193">The code above specifies that the data set should be split in three clusters.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="d14f3-194">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="d14f3-194">Train the model</span></span>

<span data-ttu-id="d14f3-195">Los pasos que se agregaron en las secciones anteriores prepararon la canalización para el aprendizaje, pero no se ha ejecutado ninguno.</span><span class="sxs-lookup"><span data-stu-id="d14f3-195">The steps added in the preceding sections prepared the pipeline for training, however, none have been executed.</span></span> <span data-ttu-id="d14f3-196">El método `pipeline.Train<TInput, TOutput>` genera el modelo que usa una instancia del tipo `TInput` para generar una instancia del tipo `TOutput`.</span><span class="sxs-lookup"><span data-stu-id="d14f3-196">The `pipeline.Train<TInput, TOutput>` method produces the model that takes in an instance of the `TInput` type and outputs an instance of the `TOutput` type.</span></span> <span data-ttu-id="d14f3-197">Agregue el código siguiente al método `Train`:</span><span class="sxs-lookup"><span data-stu-id="d14f3-197">Add the following code into the `Train` method:</span></span>

[!code-csharp[Train the model and return](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#9)]

### <a name="save-the-model"></a><span data-ttu-id="d14f3-198">Guardado del modelo</span><span class="sxs-lookup"><span data-stu-id="d14f3-198">Save the model</span></span>

<span data-ttu-id="d14f3-199">En este punto, tiene un modelo que se puede integrar en cualquiera de las aplicaciones de .NET nuevas o existentes.</span><span class="sxs-lookup"><span data-stu-id="d14f3-199">At this point, you have a model that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="d14f3-200">Para guardar el modelo en un archivo .zip, agregue el código siguiente al método `Main` debajo de la llamada al método `Train`:</span><span class="sxs-lookup"><span data-stu-id="d14f3-200">To save your model to a .zip file, add the following code to the `Main` method below the call to the `Train` method:</span></span>

[!code-csharp[Save the model](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#10)]

<span data-ttu-id="d14f3-201">El uso de `await` en el método `Main` implica que el método `Main` debe tener un modificador `async` y devolver un `Task`:</span><span class="sxs-lookup"><span data-stu-id="d14f3-201">Using `await` in the `Main` method means the `Main` method must have the `async` modifier and return a `Task`:</span></span>

[!code-csharp[Make the Main method async](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#11)]

<span data-ttu-id="d14f3-202">También tiene que agregar la directiva `using` siguiente a la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="d14f3-202">You also need to add the following `using` directive at the top of the *Program.cs* file:</span></span>

[!code-csharp[Add System.Threading.Tasks using](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#12)]

<span data-ttu-id="d14f3-203">Debido a que el método `async Main` es una característica agregada en C# 7.1 y la versión de lenguaje predeterminada del proyecto es C# 7.0, debe cambiar la versión del lenguaje a C# 7.1 o superior.</span><span class="sxs-lookup"><span data-stu-id="d14f3-203">Because the `async Main` method is the feature added in C# 7.1 and the default language version of the project is C# 7.0, you need to change the language version to C# 7.1 or higher.</span></span> <span data-ttu-id="d14f3-204">Para ello, haga clic con el botón derecho en el nodo del proyecto en el **Explorador de soluciones** y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d14f3-204">To do that, right-click the project node in **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="d14f3-205">Seleccione la pestaña **Compilar** y, después, el botón **Opciones avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="d14f3-205">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="d14f3-206">En la lista desplegable, seleccione **C# 7.1** (o una versión superior).</span><span class="sxs-lookup"><span data-stu-id="d14f3-206">In the dropdown, select  **C# 7.1** (or a higher version).</span></span> <span data-ttu-id="d14f3-207">Seleccione el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d14f3-207">Select the **OK** button.</span></span>

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="d14f3-208">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="d14f3-208">Use the model for predictions</span></span>

<span data-ttu-id="d14f3-209">Cree la clase `TestIrisData` para guardar las instancias de datos de prueba:</span><span class="sxs-lookup"><span data-stu-id="d14f3-209">Create the `TestIrisData` class to house test data instances:</span></span>

1. <span data-ttu-id="d14f3-210">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="d14f3-210">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="d14f3-211">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *TestIrisData.cs*.</span><span class="sxs-lookup"><span data-stu-id="d14f3-211">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TestIrisData.cs*.</span></span> <span data-ttu-id="d14f3-212">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="d14f3-212">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="d14f3-213">Modifique la clase para que sea estática, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d14f3-213">Modify the class to be static like in the following example:</span></span>

   [!code-csharp[Make class static](../../../samples/machine-learning/tutorials/IrisClustering/TestIrisData.cs#1)]

<span data-ttu-id="d14f3-214">En este tutorial se presenta una instancia de datos de iris dentro de esta clase.</span><span class="sxs-lookup"><span data-stu-id="d14f3-214">This tutorial introduces one iris data instance within this class.</span></span> <span data-ttu-id="d14f3-215">Puede agregar otros escenarios para experimentar con el modelo.</span><span class="sxs-lookup"><span data-stu-id="d14f3-215">You can add other scenarios to experiment with the model.</span></span> <span data-ttu-id="d14f3-216">Agregue el código siguiente a la clase `TestIrisData`:</span><span class="sxs-lookup"><span data-stu-id="d14f3-216">Add the following code into the `TestIrisData` class:</span></span>

[!code-csharp[Test data](../../../samples/machine-learning/tutorials/IrisClustering/TestIrisData.cs#2)]

<span data-ttu-id="d14f3-217">Para determinar a qué clúster pertenece el elemento especificado, vuelva al archivo *Program.cs* y agregue el código siguiente al método `Main`:</span><span class="sxs-lookup"><span data-stu-id="d14f3-217">To find out the cluster to which the specified item belongs to, go back to the *Program.cs* file and add the following code into the `Main` method:</span></span>

[!code-csharp[Predict and output results](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#13)]

<span data-ttu-id="d14f3-218">Ejecute el programa para ver qué clúster contiene la instancia de datos especificada y las distancias cuadradas desde esa instancia a los centroides de clúster.</span><span class="sxs-lookup"><span data-stu-id="d14f3-218">Run the program to see which cluster contains the specified data instance and squared distances from that instance to the cluster centroids.</span></span> <span data-ttu-id="d14f3-219">Los resultados deberían ser similares a los indicados a continuación.</span><span class="sxs-lookup"><span data-stu-id="d14f3-219">Your results should be similar to the following.</span></span> <span data-ttu-id="d14f3-220">A medida que se procesa la canalización, es posible que se muestren advertencias o mensajes de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="d14f3-220">As the pipeline processes, it might display warnings or processing messages.</span></span> <span data-ttu-id="d14f3-221">Se han quitado de los resultados siguientes para mayor claridad.</span><span class="sxs-lookup"><span data-stu-id="d14f3-221">These have been removed from the following output for clarity.</span></span>

```text
Cluster: 2
Distances: 0.4192338 0.0008847713 0.9660053
```

<span data-ttu-id="d14f3-222">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="d14f3-222">Congratulations!</span></span> <span data-ttu-id="d14f3-223">Ha creado correctamente un modelo de aprendizaje automático para la agrupación en clústeres de iris y lo ha usado para realizar predicciones.</span><span class="sxs-lookup"><span data-stu-id="d14f3-223">You've now successfully built a machine learning model for iris clustering and used it to make predictions.</span></span> <span data-ttu-id="d14f3-224">Puede encontrar el código fuente de este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisClustering) de GitHub.</span><span class="sxs-lookup"><span data-stu-id="d14f3-224">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisClustering) GitHub repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d14f3-225">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="d14f3-225">Next steps</span></span>

<span data-ttu-id="d14f3-226">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="d14f3-226">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="d14f3-227">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="d14f3-227">Understand the problem</span></span>
> - <span data-ttu-id="d14f3-228">Seleccionar la tarea de aprendizaje automático adecuada</span><span class="sxs-lookup"><span data-stu-id="d14f3-228">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="d14f3-229">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="d14f3-229">Prepare the data</span></span>
> - <span data-ttu-id="d14f3-230">Cargar y transformar los datos</span><span class="sxs-lookup"><span data-stu-id="d14f3-230">Load and transform the data</span></span>
> - <span data-ttu-id="d14f3-231">Elegir un algoritmo de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="d14f3-231">Choose a learning algorithm</span></span>
> - <span data-ttu-id="d14f3-232">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="d14f3-232">Train the model</span></span>
> - <span data-ttu-id="d14f3-233">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="d14f3-233">Use the model for predictions</span></span>

<span data-ttu-id="d14f3-234">Visite nuestro repositorio de GitHub para obtener más información y encontrar más ejemplos.</span><span class="sxs-lookup"><span data-stu-id="d14f3-234">Check out our GitHub repository to continue learning and find more samples.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="d14f3-235">Repositorio de GitHub de dotnet/machinelearning</span><span class="sxs-lookup"><span data-stu-id="d14f3-235">dotnet/machinelearning GitHub repository</span></span>](https://github.com/dotnet/machinelearning/)
