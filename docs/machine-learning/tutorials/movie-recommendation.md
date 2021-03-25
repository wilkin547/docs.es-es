---
title: 'Tutorial: Creación de un recomendador de películas (factorización matricial)'
description: Este tutorial muestra cómo compilar una recomendación de películas con ML.NET en una consola de aplicación de .NET Core. Los pasos utilizan C# y Visual Studio 2019.
author: briacht
ms.date: 06/30/2020
ms.custom: mvc, title-hack-0516
ms.topic: tutorial
ms.openlocfilehash: 2df774110d3355bf75a14e211555984a12cf7fa4
ms.sourcegitcommit: b27645cb378d4e8137a267e5467ff31409acf6c0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2021
ms.locfileid: "103231399"
---
# <a name="tutorial-build-a-movie-recommender-using-matrix-factorization-with-mlnet"></a><span data-ttu-id="37c5c-104">Tutorial: Creación de un recomendador de películas mediante factorización matricial con ML.NET</span><span class="sxs-lookup"><span data-stu-id="37c5c-104">Tutorial: Build a movie recommender using matrix factorization with ML.NET</span></span>

<span data-ttu-id="37c5c-105">Este tutorial muestra cómo compilar una recomendación de películas con ML.NET en una consola de aplicación de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="37c5c-105">This tutorial shows you how to build a movie recommender with ML.NET in a .NET Core console application.</span></span> <span data-ttu-id="37c5c-106">Los pasos utilizan C# y Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="37c5c-106">The steps use C# and Visual Studio 2019.</span></span>

<span data-ttu-id="37c5c-107">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="37c5c-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="37c5c-108">Seleccionar un algoritmo de Machine Learning</span><span class="sxs-lookup"><span data-stu-id="37c5c-108">Select a machine learning algorithm</span></span>
> * <span data-ttu-id="37c5c-109">Preparar y cargar los datos</span><span class="sxs-lookup"><span data-stu-id="37c5c-109">Prepare and load your data</span></span>
> * <span data-ttu-id="37c5c-110">Compilar y entrenar un modelo</span><span class="sxs-lookup"><span data-stu-id="37c5c-110">Build and train a model</span></span>
> * <span data-ttu-id="37c5c-111">Evaluar un modelo</span><span class="sxs-lookup"><span data-stu-id="37c5c-111">Evaluate a model</span></span>
> * <span data-ttu-id="37c5c-112">Implementar y consumir un modelo</span><span class="sxs-lookup"><span data-stu-id="37c5c-112">Deploy and consume a model</span></span>

<span data-ttu-id="37c5c-113">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/MovieRecommendation).</span><span class="sxs-lookup"><span data-stu-id="37c5c-113">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/MovieRecommendation) repository.</span></span>

## <a name="machine-learning-workflow"></a><span data-ttu-id="37c5c-114">Flujo de trabajo del aprendizaje automático</span><span class="sxs-lookup"><span data-stu-id="37c5c-114">Machine learning workflow</span></span>

<span data-ttu-id="37c5c-115">Usará los pasos siguientes para realizar la tarea, así como cualquier otra tarea de ML.NET:</span><span class="sxs-lookup"><span data-stu-id="37c5c-115">You will use the following steps to accomplish your task, as well as any other ML.NET task:</span></span>

1. [<span data-ttu-id="37c5c-116">Cargar los datos</span><span class="sxs-lookup"><span data-stu-id="37c5c-116">Load your data</span></span>](#load-your-data)
2. [<span data-ttu-id="37c5c-117">Compilar y entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="37c5c-117">Build and train your model</span></span>](#build-and-train-your-model)
3. [<span data-ttu-id="37c5c-118">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="37c5c-118">Evaluate your model</span></span>](#evaluate-your-model)
4. [<span data-ttu-id="37c5c-119">Usar el modelo</span><span class="sxs-lookup"><span data-stu-id="37c5c-119">Use your model</span></span>](#use-your-model)

## <a name="prerequisites"></a><span data-ttu-id="37c5c-120">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="37c5c-120">Prerequisites</span></span>

* <span data-ttu-id="37c5c-121">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o posterior, o bien Visual Studio 2017 versión 15.6 o posterior con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.</span><span class="sxs-lookup"><span data-stu-id="37c5c-121">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or later or Visual Studio 2017 version 15.6 or later with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="37c5c-122">Seleccionar la tarea de aprendizaje automático adecuada</span><span class="sxs-lookup"><span data-stu-id="37c5c-122">Select the appropriate machine learning task</span></span>

<span data-ttu-id="37c5c-123">Hay varias maneras de enfocar los problemas vinculados a las recomendaciones, como recomendar una lista de películas o recomendar una lista de productos relacionados. En este caso, predecirá qué clasificación (de 1 a 5) asignará un usuario a una película concreta y recomendará esa película si es superior a un umbral definido (cuanto mayor sea la clasificación, más probable será que a un usuario le guste una película concreta).</span><span class="sxs-lookup"><span data-stu-id="37c5c-123">There are several ways to approach recommendation problems, such as recommending a list of movies or recommending a list of related products, but in this case you will predict what rating (1-5) a user will give to a particular movie and recommend that movie if it's higher than a defined threshold (the higher the rating, the higher the likelihood of a user liking a particular movie).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="37c5c-124">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="37c5c-124">Create a console application</span></span>

### <a name="create-a-project"></a><span data-ttu-id="37c5c-125">Crear un proyecto</span><span class="sxs-lookup"><span data-stu-id="37c5c-125">Create a project</span></span>

1. <span data-ttu-id="37c5c-126">Abra Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="37c5c-126">Open Visual Studio 2017.</span></span> <span data-ttu-id="37c5c-127">Seleccione **Archivo** > **Nuevo** > **Proyecto** de la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="37c5c-127">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="37c5c-128">En el cuadro de diálogo **Nuevo proyecto**, seleccione el nodo **Visual C#** seguido del nodo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="37c5c-128">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="37c5c-129">Después, seleccione la plantilla del proyecto **Aplicación de consola (.NET Core)** .</span><span class="sxs-lookup"><span data-stu-id="37c5c-129">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="37c5c-130">En el cuadro de texto **Nombre**, escriba "MovieRecommender" y haga clic en el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="37c5c-130">In the **Name** text box, type "MovieRecommender" and then select the **OK** button.</span></span>

2. <span data-ttu-id="37c5c-131">Cree un directorio denominado *Datos* en el proyecto para almacenar el conjunto de datos:</span><span class="sxs-lookup"><span data-stu-id="37c5c-131">Create a directory named *Data* in your project to store the data set:</span></span>

    <span data-ttu-id="37c5c-132">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **Nueva carpeta**.</span><span class="sxs-lookup"><span data-stu-id="37c5c-132">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="37c5c-133">Escriba "Datos" y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="37c5c-133">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="37c5c-134">Instale los paquetes NuGet **Microsoft.ML** y **Microsoft.ML.Recommender**:</span><span class="sxs-lookup"><span data-stu-id="37c5c-134">Install the **Microsoft.ML** and **Microsoft.ML.Recommender** NuGet Packages:</span></span>

    [!INCLUDE [mlnet-current-nuget-version](../../../includes/mlnet-current-nuget-version.md)]

    <span data-ttu-id="37c5c-135">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="37c5c-135">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="37c5c-136">Elija "nuget.org" como origen del paquete, seleccione la pestaña **Examinar**, busque **Microsoft.ML**, seleccione el paquete en la lista y seleccione el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="37c5c-136">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select the package in the list, and select the **Install** button.</span></span> <span data-ttu-id="37c5c-137">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="37c5c-137">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span> <span data-ttu-id="37c5c-138">Repita estos pasos para **Microsoft.ML.Recommender**.</span><span class="sxs-lookup"><span data-stu-id="37c5c-138">Repeat these steps for **Microsoft.ML.Recommender**.</span></span>

4. <span data-ttu-id="37c5c-139">Agregue las instrucciones `using` siguientes en la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="37c5c-139">Add the following `using` statements at the top of your *Program.cs* file:</span></span>

    [!code-csharp[UsingStatements](./snippets/movie-recommendation/csharp/Program.cs#UsingStatements "Add necessary usings")]

### <a name="download-your-data"></a><span data-ttu-id="37c5c-140">Descarga de los datos</span><span class="sxs-lookup"><span data-stu-id="37c5c-140">Download your data</span></span>

1. <span data-ttu-id="37c5c-141">Descargue los dos conjuntos de datos y guárdelos en la carpeta *Datos* que creó anteriormente:</span><span class="sxs-lookup"><span data-stu-id="37c5c-141">Download the two datasets and save them to the *Data* folder you previously created:</span></span>

   * <span data-ttu-id="37c5c-142">Haga clic con el botón derecho en [*recommendation-ratings-train.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-train.csv) y seleccione "Save Link (or Target) As…" ("Guardar vínculo (o destino) como…").</span><span class="sxs-lookup"><span data-stu-id="37c5c-142">Right click on [*recommendation-ratings-train.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-train.csv) and select "Save Link (or Target) As..."</span></span>
   * <span data-ttu-id="37c5c-143">Haga clic con el botón derecho en [*recommendation-ratings-test.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-test.csv) y seleccione "Save Link (or Target) As…" ("Guardar vínculo (o destino) como…").</span><span class="sxs-lookup"><span data-stu-id="37c5c-143">Right click on [*recommendation-ratings-test.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-test.csv) and select "Save Link (or Target) As..."</span></span>

     <span data-ttu-id="37c5c-144">Asegúrese de guardar los archivos \*.csv en la carpeta *Datos*. Si los guarda en otro lugar, recuerde que debe mover los archivos \*.csv a la carpeta *Datos*.</span><span class="sxs-lookup"><span data-stu-id="37c5c-144">Make sure you either save the \*.csv files to the *Data* folder, or after you save it elsewhere, move the \*.csv files to the *Data* folder.</span></span>

2. <span data-ttu-id="37c5c-145">En el Explorador de soluciones, haga clic con el botón secundario en cada uno de los archivos \*.csv y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="37c5c-145">In Solution Explorer, right-click each of the \*.csv files and select **Properties**.</span></span> <span data-ttu-id="37c5c-146">En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.</span><span class="sxs-lookup"><span data-stu-id="37c5c-146">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

   ![GIF de un usuario que selecciona Copiar si es posterior en VS.](./media/movie-recommendation/copy-to-output-if-newer.gif)

## <a name="load-your-data"></a><span data-ttu-id="37c5c-148">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="37c5c-148">Load your data</span></span>

<span data-ttu-id="37c5c-149">El primer paso en el proceso de ML.NET consiste en preparar y cargar los datos de entrenamiento y prueba del modelo.</span><span class="sxs-lookup"><span data-stu-id="37c5c-149">The first step in the ML.NET process is to prepare and load your model training and testing data.</span></span>

<span data-ttu-id="37c5c-150">Los datos de las clasificaciones de recomendación se dividen en conjuntos de datos `Train` y `Test`.</span><span class="sxs-lookup"><span data-stu-id="37c5c-150">The recommendation ratings data is split into `Train` and `Test` datasets.</span></span> <span data-ttu-id="37c5c-151">Los datos `Train` se usan para ajustar el modelo,</span><span class="sxs-lookup"><span data-stu-id="37c5c-151">The `Train` data is used to fit your model.</span></span> <span data-ttu-id="37c5c-152">mientras que los datos `Test` sirven para realizar predicciones con el modelo entrenado y evaluar el rendimiento del modelo.</span><span class="sxs-lookup"><span data-stu-id="37c5c-152">The `Test` data is used to make predictions with your trained model and evaluate model performance.</span></span> <span data-ttu-id="37c5c-153">Los datos `Train` y `Test` suelen dividirse con una proporción de 80/20.</span><span class="sxs-lookup"><span data-stu-id="37c5c-153">It's common to have an 80/20 split with `Train` and `Test` data.</span></span>

<span data-ttu-id="37c5c-154">A continuación se muestra una vista previa de los datos de los archivos \*.csv:</span><span class="sxs-lookup"><span data-stu-id="37c5c-154">Below is a preview of the data from your \*.csv files:</span></span>

![Captura de pantalla de la vista previa del conjunto de datos CSV.](./media/movie-recommendation/csv-file-dataset-preview.png)

<span data-ttu-id="37c5c-156">En los archivos \*.csv, hay cuatro columnas:</span><span class="sxs-lookup"><span data-stu-id="37c5c-156">In the \*.csv files, there are four columns:</span></span>

* `userId`
* `movieId`
* `rating`
* `timestamp`

<span data-ttu-id="37c5c-157">En Machine Learning, las columnas que se usan para realizar una predicción se denominan [Features](../resources/glossary.md#feature) (Características), mientras que la columna con la predicción devuelta recibe el nombre de [Label](../resources/glossary.md#label) (Etiqueta).</span><span class="sxs-lookup"><span data-stu-id="37c5c-157">In machine learning, the columns that are used to make a prediction are called [Features](../resources/glossary.md#feature), and the column with the returned prediction is called the [Label](../resources/glossary.md#label).</span></span>

<span data-ttu-id="37c5c-158">En su caso, quiere predecir clasificaciones de películas, por lo que la columna de clasificación es `Label`.</span><span class="sxs-lookup"><span data-stu-id="37c5c-158">You want to predict movie ratings, so the rating column is the `Label`.</span></span> <span data-ttu-id="37c5c-159">Las otras tres columnas (`userId`, `movieId` y `timestamp`) son `Features` que se usan para predecir la `Label`.</span><span class="sxs-lookup"><span data-stu-id="37c5c-159">The other three columns, `userId`, `movieId`, and `timestamp` are all `Features` used to predict the `Label`.</span></span>

| <span data-ttu-id="37c5c-160">Características</span><span class="sxs-lookup"><span data-stu-id="37c5c-160">Features</span></span>      | <span data-ttu-id="37c5c-161">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="37c5c-161">Label</span></span>         |
| ------------- |:-------------:|
| `userId`        |    `rating`     |
| `movieId`      |               |
| `timestamp`     |               |

<span data-ttu-id="37c5c-162">Usted decide qué `Features` se usan para predecir la `Label`.</span><span class="sxs-lookup"><span data-stu-id="37c5c-162">It's up to you to decide which `Features` are used to predict the `Label`.</span></span> <span data-ttu-id="37c5c-163">También puede usar métodos como la [importancia de la característica de permutación](../how-to-guides/explain-machine-learning-model-permutation-feature-importance-ml-net.md) para ayudar a seleccionar las mejores `Features`.</span><span class="sxs-lookup"><span data-stu-id="37c5c-163">You can also use methods like [permutation feature importance](../how-to-guides/explain-machine-learning-model-permutation-feature-importance-ml-net.md) to help with selecting the best `Features`.</span></span>

<span data-ttu-id="37c5c-164">En este caso, debe eliminar la columna `timestamp` como `Feature` porque la marca de tiempo no afecta realmente a la manera en que un usuario clasifica una película determinada y, por tanto, no contribuye a realizar una predicción más exacta:</span><span class="sxs-lookup"><span data-stu-id="37c5c-164">In this case, you should eliminate the `timestamp` column as a `Feature` because the timestamp does not really affect how a user rates a given movie and thus would not contribute to making a more accurate prediction:</span></span>

| <span data-ttu-id="37c5c-165">Características</span><span class="sxs-lookup"><span data-stu-id="37c5c-165">Features</span></span>      | <span data-ttu-id="37c5c-166">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="37c5c-166">Label</span></span>         |
| ------------- |:-------------:|
| `userId`        |    `rating`     |
| `movieId`      |               |

<span data-ttu-id="37c5c-167">Después, debe definir la estructura de datos para la clase de entrada.</span><span class="sxs-lookup"><span data-stu-id="37c5c-167">Next you must define your data structure for the input class.</span></span>

<span data-ttu-id="37c5c-168">Agregue una nueva clase a su proyecto:</span><span class="sxs-lookup"><span data-stu-id="37c5c-168">Add a new class to your project:</span></span>

1. <span data-ttu-id="37c5c-169">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar > Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="37c5c-169">In **Solution Explorer**, right-click the project, and then select **Add > New Item**.</span></span>

2. <span data-ttu-id="37c5c-170">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *MovieRatingData.cs*.</span><span class="sxs-lookup"><span data-stu-id="37c5c-170">In the **Add New Item dialog box**, select **Class** and change the **Name** field to *MovieRatingData.cs*.</span></span> <span data-ttu-id="37c5c-171">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="37c5c-171">Then, select the **Add** button.</span></span>

<span data-ttu-id="37c5c-172">Se abre el archivo *MovieRatingData.cs* en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="37c5c-172">The *MovieRatingData.cs* file opens in the code editor.</span></span> <span data-ttu-id="37c5c-173">Agregue la siguiente instrucción `using` a la parte superior de *MovieRatingData.cs*:</span><span class="sxs-lookup"><span data-stu-id="37c5c-173">Add the following `using` statement to the top of *MovieRatingData.cs*:</span></span>

```csharp
using Microsoft.ML.Data;
```

<span data-ttu-id="37c5c-174">Cree una clase denominada `MovieRating`. Para ello, quite la definición de clase existente y agregue el siguiente código en *MovieRatingData.cs*:</span><span class="sxs-lookup"><span data-stu-id="37c5c-174">Create a class called `MovieRating` by removing the existing class definition and adding the following code in *MovieRatingData.cs*:</span></span>

[!code-csharp[MovieRatingClass](./snippets/movie-recommendation/csharp/MovieRatingData.cs#MovieRatingClass "Add the Movie Rating class")]

<span data-ttu-id="37c5c-175">`MovieRating` especifica una clase de datos de entrada.</span><span class="sxs-lookup"><span data-stu-id="37c5c-175">`MovieRating` specifies an input data class.</span></span> <span data-ttu-id="37c5c-176">El atributo [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) especifica qué columnas (por índice de columna) del conjunto de datos se deben cargar.</span><span class="sxs-lookup"><span data-stu-id="37c5c-176">The [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) attribute specifies which columns (by column index) in the dataset should be loaded.</span></span> <span data-ttu-id="37c5c-177">Las columnas `userId` y `movieId` son las `Features` (las entradas que proporcionará al modelo para predecir la `Label`), y la columna de clasificación es la `Label` que predecirá (la salida del modelo).</span><span class="sxs-lookup"><span data-stu-id="37c5c-177">The `userId` and `movieId` columns are your `Features` (the inputs you will give the model to predict the `Label`), and the rating column is the `Label` that you will predict (the output of the model).</span></span>

<span data-ttu-id="37c5c-178">Cree otra clase (`MovieRatingPrediction`) para representar los resultados predichos. Para ello, agregue el código siguiente después de la clase `MovieRating` en *MovieRatingData.cs*:</span><span class="sxs-lookup"><span data-stu-id="37c5c-178">Create another class, `MovieRatingPrediction`, to represent predicted results by adding the following code after the `MovieRating` class in *MovieRatingData.cs*:</span></span>

[!code-csharp[PredictionClass](./snippets/movie-recommendation/csharp/MovieRatingData.cs#PredictionClass "Add the Movie Prediction Class")]

<span data-ttu-id="37c5c-179">En *Program.cs*, reemplace `Console.WriteLine("Hello World!")` por el código siguiente dentro de `Main()`:</span><span class="sxs-lookup"><span data-stu-id="37c5c-179">In *Program.cs*, replace the `Console.WriteLine("Hello World!")` with the following code inside `Main()`:</span></span>

[!code-csharp[MLContext](./snippets/movie-recommendation/csharp/Program.cs#MLContext "Add MLContext")]

<span data-ttu-id="37c5c-180">La [clase MLContext](xref:Microsoft.ML.MLContext) es un punto de partida para todas las operaciones de ML.NET. Al inicializar `mlContext`, se crea un entorno de ML.NET que se puede compartir entre los objetos del flujo de trabajo de creación de modelos.</span><span class="sxs-lookup"><span data-stu-id="37c5c-180">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="37c5c-181">Como concepto, se parece a `DBContext` en Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="37c5c-181">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

<span data-ttu-id="37c5c-182">Después de `Main()`, cree un método denominado `LoadData()`:</span><span class="sxs-lookup"><span data-stu-id="37c5c-182">After `Main()`, create a method called `LoadData()`:</span></span>

```csharp
public static (IDataView training, IDataView test) LoadData(MLContext mlContext)
{

}
```

> [!NOTE]
> <span data-ttu-id="37c5c-183">Este método generará un error hasta que agregue una instrucción return en los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="37c5c-183">This method will give you an error until you add a return statement in the following steps.</span></span>

<span data-ttu-id="37c5c-184">Inicialice las variables de ruta de acceso de datos, cargue los datos de los archivos \*.csv y devuelva los datos `Train` y `Test` como objetos `IDataView`. Para ello, agregue lo que se indica a continuación como la siguiente línea de código en `LoadData()`:</span><span class="sxs-lookup"><span data-stu-id="37c5c-184">Initialize your data path variables, load the data from the \*.csv files, and return the `Train` and `Test` data as `IDataView` objects by adding the following as the next line of code in `LoadData()`:</span></span>

[!code-csharp[LoadData](./snippets/movie-recommendation/csharp/Program.cs#LoadData "Load data from data paths")]

<span data-ttu-id="37c5c-185">Los datos de ML.NET se representan como una [clase IDataView](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="37c5c-185">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="37c5c-186">`IDataView` es una manera flexible y eficiente de describir datos tabulares (numéricos y de texto).</span><span class="sxs-lookup"><span data-stu-id="37c5c-186">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="37c5c-187">Los datos se pueden cargar desde un archivo de texto o en tiempo real (por ejemplo, archivos de registro o base de datos SQL) en un objeto `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="37c5c-187">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

<span data-ttu-id="37c5c-188">[LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) define el esquema de datos y lee en el archivo.</span><span class="sxs-lookup"><span data-stu-id="37c5c-188">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) defines the data schema and reads in the file.</span></span> <span data-ttu-id="37c5c-189">Toma las variables de ruta de acceso de datos y devuelve `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="37c5c-189">It takes in the data path variables and returns an `IDataView`.</span></span> <span data-ttu-id="37c5c-190">En este caso, usted proporciona la ruta de acceso a los archivos `Test` y `Train` e indica el encabezado del archivo de texto (para que pueda usar correctamente los nombres de columna) y el separador de datos de caracteres de coma (el separador predeterminado es el tabulador).</span><span class="sxs-lookup"><span data-stu-id="37c5c-190">In this case, you provide the path for your `Test` and `Train` files and indicate both the text file header (so it can use the column names properly) and the comma character data separator (the default separator is a tab).</span></span>

<span data-ttu-id="37c5c-191">Agregue este código en el método `Main()` para llamar al método `LoadData()` y devolver los datos `Train` y `Test`:</span><span class="sxs-lookup"><span data-stu-id="37c5c-191">Add the following code in the `Main()` method to call your `LoadData()` method and return the `Train` and `Test` data:</span></span>

[!code-csharp[LoadDataMain](./snippets/movie-recommendation/csharp/Program.cs#LoadDataMain "Add LoadData method to Main")]

## <a name="build-and-train-your-model"></a><span data-ttu-id="37c5c-192">Compilación y entrenamiento del modelo</span><span class="sxs-lookup"><span data-stu-id="37c5c-192">Build and train your model</span></span>

<span data-ttu-id="37c5c-193">Cree el método `BuildAndTrainModel()`, justo después del método `LoadData()`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="37c5c-193">Create the `BuildAndTrainModel()` method, just after the `LoadData()` method, using the following code:</span></span>

```csharp
public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView trainingDataView)
{

}
```

> [!NOTE]
> <span data-ttu-id="37c5c-194">Este método generará un error hasta que agregue una instrucción return en los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="37c5c-194">This method will give you an error until you add a return statement in the following steps.</span></span>

<span data-ttu-id="37c5c-195">Defina las transformaciones de datos mediante la adición del código siguiente a `BuildAndTrainModel()`:</span><span class="sxs-lookup"><span data-stu-id="37c5c-195">Define the data transformations by adding the following code to `BuildAndTrainModel()`:</span></span>

[!code-csharp[DataTransformations](./snippets/movie-recommendation/csharp/Program.cs#DataTransformations "Define data transformations")]

<span data-ttu-id="37c5c-196">Puesto que `userId` y `movieId` representan usuarios y títulos de películas, en lugar de valores reales, debe usar el método [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) para transformar cada `userId` y `movieId` en una columna `Feature` de tipo de clave numérica (un formato que aceptan los algoritmos de recomendación) y agregarlos como nuevas columnas del conjunto de datos:</span><span class="sxs-lookup"><span data-stu-id="37c5c-196">Since `userId` and `movieId` represent users and movie titles, not real values, you use the [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) method to transform each `userId` and each `movieId` into a numeric key type `Feature` column (a format accepted by recommendation algorithms) and add them as new dataset columns:</span></span>

| <span data-ttu-id="37c5c-197">userId</span><span class="sxs-lookup"><span data-stu-id="37c5c-197">userId</span></span> | <span data-ttu-id="37c5c-198">movieId</span><span class="sxs-lookup"><span data-stu-id="37c5c-198">movieId</span></span> | <span data-ttu-id="37c5c-199">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="37c5c-199">Label</span></span> | <span data-ttu-id="37c5c-200">userIdEncoded</span><span class="sxs-lookup"><span data-stu-id="37c5c-200">userIdEncoded</span></span> | <span data-ttu-id="37c5c-201">movieIdEncoded</span><span class="sxs-lookup"><span data-stu-id="37c5c-201">movieIdEncoded</span></span> |
| ------------- |:-------------:| -----:|-----:|-----:|
| <span data-ttu-id="37c5c-202">1</span><span class="sxs-lookup"><span data-stu-id="37c5c-202">1</span></span> | <span data-ttu-id="37c5c-203">1</span><span class="sxs-lookup"><span data-stu-id="37c5c-203">1</span></span> | <span data-ttu-id="37c5c-204">4</span><span class="sxs-lookup"><span data-stu-id="37c5c-204">4</span></span> | <span data-ttu-id="37c5c-205">userKey1</span><span class="sxs-lookup"><span data-stu-id="37c5c-205">userKey1</span></span> | <span data-ttu-id="37c5c-206">movieKey1</span><span class="sxs-lookup"><span data-stu-id="37c5c-206">movieKey1</span></span> |
| <span data-ttu-id="37c5c-207">1</span><span class="sxs-lookup"><span data-stu-id="37c5c-207">1</span></span> | <span data-ttu-id="37c5c-208">3</span><span class="sxs-lookup"><span data-stu-id="37c5c-208">3</span></span> | <span data-ttu-id="37c5c-209">4</span><span class="sxs-lookup"><span data-stu-id="37c5c-209">4</span></span> | <span data-ttu-id="37c5c-210">userKey1</span><span class="sxs-lookup"><span data-stu-id="37c5c-210">userKey1</span></span> | <span data-ttu-id="37c5c-211">movieKey2</span><span class="sxs-lookup"><span data-stu-id="37c5c-211">movieKey2</span></span> |
| <span data-ttu-id="37c5c-212">1</span><span class="sxs-lookup"><span data-stu-id="37c5c-212">1</span></span> | <span data-ttu-id="37c5c-213">6</span><span class="sxs-lookup"><span data-stu-id="37c5c-213">6</span></span> | <span data-ttu-id="37c5c-214">4</span><span class="sxs-lookup"><span data-stu-id="37c5c-214">4</span></span> | <span data-ttu-id="37c5c-215">userKey1</span><span class="sxs-lookup"><span data-stu-id="37c5c-215">userKey1</span></span> | <span data-ttu-id="37c5c-216">movieKey3</span><span class="sxs-lookup"><span data-stu-id="37c5c-216">movieKey3</span></span> |

<span data-ttu-id="37c5c-217">Elija el algoritmo de Machine Learning y anéxelo a las definiciones de transformación de datos. Para ello, agregue lo que se indica a continuación como la siguiente línea de código en `BuildAndTrainModel()`:</span><span class="sxs-lookup"><span data-stu-id="37c5c-217">Choose the machine learning algorithm and append it to the data transformation definitions by adding the following as the next line of code in `BuildAndTrainModel()`:</span></span>

[!code-csharp[AddAlgorithm](./snippets/movie-recommendation/csharp/Program.cs#AddAlgorithm "Add the training algorithm with options")]

<span data-ttu-id="37c5c-218">[MatrixFactorizationTrainer](xref:Microsoft.ML.RecommendationCatalog.RecommendationTrainers.MatrixFactorization%28Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options%29) es el algoritmo de entrenamiento de recomendación.</span><span class="sxs-lookup"><span data-stu-id="37c5c-218">The [MatrixFactorizationTrainer](xref:Microsoft.ML.RecommendationCatalog.RecommendationTrainers.MatrixFactorization%28Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options%29) is your recommendation training algorithm.</span></span>  <span data-ttu-id="37c5c-219">La [factorización matricial](https://en.wikipedia.org/wiki/Matrix_factorization_(recommender_systems)) es una manera común de enfocar la recomendación cuando se dispone de datos que muestran cómo los usuarios clasificaron anteriormente los productos, que es el caso de los conjuntos de datos de este tutorial.</span><span class="sxs-lookup"><span data-stu-id="37c5c-219">[Matrix Factorization](https://en.wikipedia.org/wiki/Matrix_factorization_(recommender_systems)) is a common approach to recommendation when you have data on how users have rated products in the past, which is the case for the datasets in this tutorial.</span></span> <span data-ttu-id="37c5c-220">Existen otros algoritmos de recomendación para cuando se dispone de datos diferentes (vea más adelante la sección [Otros algoritmos de recomendación](#other-recommendation-algorithms) para obtener más información).</span><span class="sxs-lookup"><span data-stu-id="37c5c-220">There are other recommendation algorithms for when you have different data available (see the [Other recommendation algorithms](#other-recommendation-algorithms) section below to learn more).</span></span>

<span data-ttu-id="37c5c-221">En este caso, el algoritmo `Matrix Factorization` usa un método denominado "filtrado de colaboración", que presupone que si el Usuario 1 tiene la misma opinión que el Usuario 2 en un tema determinado, lo más probable es que el Usuario 1 piense lo mismo que el Usuario 2 sobre otro tema.</span><span class="sxs-lookup"><span data-stu-id="37c5c-221">In this case, the `Matrix Factorization` algorithm uses a method called "collaborative filtering", which assumes that if User 1 has the same opinion as User 2 on a certain issue, then User 1 is more likely to feel the same way as User 2 about a different issue.</span></span>

<span data-ttu-id="37c5c-222">Por ejemplo, si el Usuario 1 y el Usuario 2 clasifican las películas de forma similar, lo más probable es que el Usuario 2 disfrute de una película que el Usuario 1 ha visto y ha clasificado con una puntuación alta:</span><span class="sxs-lookup"><span data-stu-id="37c5c-222">For instance, if User 1 and User 2 rate movies similarly, then User 2 is more likely to enjoy a movie that User 1 has watched and rated highly:</span></span>

| | `Incredibles 2 (2018)` | `The Avengers (2012)` | `Guardians of the Galaxy (2014)` |
| -------------:|-------------:| -----:|-----:|
| <span data-ttu-id="37c5c-223">Usuario 1</span><span class="sxs-lookup"><span data-stu-id="37c5c-223">User 1</span></span> | <span data-ttu-id="37c5c-224">Ha visto la película y le ha gustado</span><span class="sxs-lookup"><span data-stu-id="37c5c-224">Watched and liked movie</span></span> | <span data-ttu-id="37c5c-225">Ha visto la película y le ha gustado</span><span class="sxs-lookup"><span data-stu-id="37c5c-225">Watched and liked movie</span></span> | <span data-ttu-id="37c5c-226">Ha visto la película y le ha gustado</span><span class="sxs-lookup"><span data-stu-id="37c5c-226">Watched and liked movie</span></span> |
| <span data-ttu-id="37c5c-227">Usuario 2</span><span class="sxs-lookup"><span data-stu-id="37c5c-227">User 2</span></span> | <span data-ttu-id="37c5c-228">Ha visto la película y le ha gustado</span><span class="sxs-lookup"><span data-stu-id="37c5c-228">Watched and liked movie</span></span> | <span data-ttu-id="37c5c-229">Ha visto la película y le ha gustado</span><span class="sxs-lookup"><span data-stu-id="37c5c-229">Watched and liked movie</span></span> | <span data-ttu-id="37c5c-230">No ha visto la película. RECOMENDARLA</span><span class="sxs-lookup"><span data-stu-id="37c5c-230">Has not watched -- RECOMMEND movie</span></span> |

<span data-ttu-id="37c5c-231">El instructor `Matrix Factorization` tiene varias [opciones](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options), sobre las que puede informarse más adelante en la sección [Hiperparámetros de algoritmo](#algorithm-hyperparameters).</span><span class="sxs-lookup"><span data-stu-id="37c5c-231">The `Matrix Factorization` trainer has several [Options](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options), which you can read more about in the [Algorithm hyperparameters](#algorithm-hyperparameters) section below.</span></span>

<span data-ttu-id="37c5c-232">Ajuste el modelo a los datos `Train` y devuelva el modelo entrenado. Para ello, agregue lo que se indica a continuación como la siguiente línea de código en el método `BuildAndTrainModel()`:</span><span class="sxs-lookup"><span data-stu-id="37c5c-232">Fit the model to the `Train` data and return the trained model by adding the following as the next line of code in the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[FitModel](./snippets/movie-recommendation/csharp/Program.cs#FitModel "Call the Fit method and return back the trained model")]

<span data-ttu-id="37c5c-233">El método [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) entrena el modelo con el conjunto de datos de entrenamiento proporcionado.</span><span class="sxs-lookup"><span data-stu-id="37c5c-233">The [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) method trains your model with the provided training dataset.</span></span> <span data-ttu-id="37c5c-234">Técnicamente, ejecuta las definiciones de `Estimator`, para lo que transforma los datos y aplica el entrenamiento, y devuelve el modelo entrenado, que es un `Transformer`.</span><span class="sxs-lookup"><span data-stu-id="37c5c-234">Technically, it executes the `Estimator` definitions by transforming the data and applying the training, and it returns back the trained model, which is a `Transformer`.</span></span>

<span data-ttu-id="37c5c-235">Para obtener más información sobre el flujo de trabajo de entrenamiento de modelos en ML.NET, vea [¿Qué es ML.NET y cómo funciona?](../how-does-mldotnet-work.md#code-workflow).</span><span class="sxs-lookup"><span data-stu-id="37c5c-235">For more information on the model training workflow in ML.NET, see [What is ML.NET and how does it work?](../how-does-mldotnet-work.md#code-workflow).</span></span>

<span data-ttu-id="37c5c-236">Agregue lo que se indica a continuación como la siguiente líneas de código en el método `Main()` para llamar al método `BuildAndTrainModel()` y devolver el modelo entrenado:</span><span class="sxs-lookup"><span data-stu-id="37c5c-236">Add the following as the next line of code in the `Main()` method to call your `BuildAndTrainModel()` method and return the trained model:</span></span>

[!code-csharp[BuildTrainModelMain](./snippets/movie-recommendation/csharp/Program.cs#BuildTrainModelMain "Add BuildAndTrainModel method in Main")]

## <a name="evaluate-your-model"></a><span data-ttu-id="37c5c-237">Evaluación del modelo</span><span class="sxs-lookup"><span data-stu-id="37c5c-237">Evaluate your model</span></span>

<span data-ttu-id="37c5c-238">Una vez que haya entrenado el modelo, use los datos de prueba para evaluar el rendimiento del modelo.</span><span class="sxs-lookup"><span data-stu-id="37c5c-238">Once you have trained your model, use your test data to evaluate how your model is performing.</span></span>

<span data-ttu-id="37c5c-239">Cree el método `EvaluateModel()`, justo después del método `BuildAndTrainModel()`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="37c5c-239">Create the `EvaluateModel()` method, just after the `BuildAndTrainModel()` method, using the following code:</span></span>

```csharp
public static void EvaluateModel(MLContext mlContext, IDataView testDataView, ITransformer model)
{

}
```

<span data-ttu-id="37c5c-240">Transforme los datos `Test` mediante la adición del código siguiente a `EvaluateModel()`:</span><span class="sxs-lookup"><span data-stu-id="37c5c-240">Transform the `Test` data by adding the following code to `EvaluateModel()`:</span></span>

[!code-csharp[Transform](./snippets/movie-recommendation/csharp/Program.cs#Transform "Transform the test data")]

<span data-ttu-id="37c5c-241">El método [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) realiza predicciones para varias filas de entrada proporcionadas de un conjunto de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="37c5c-241">The [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method makes predictions for multiple provided input rows of a test dataset.</span></span>

<span data-ttu-id="37c5c-242">Para evaluar el modelo, agregue lo que se indica a continuación como la siguiente línea de código en el método `EvaluateModel()`:</span><span class="sxs-lookup"><span data-stu-id="37c5c-242">Evaluate the model by adding the following as the next line of code in the `EvaluateModel()` method:</span></span>

[!code-csharp[Evaluate](./snippets/movie-recommendation/csharp/Program.cs#Evaluate "Evaluate the model using predictions from the test data")]

<span data-ttu-id="37c5c-243">Una vez que se ha establecido la predicción, el método [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) valora el modelo, que compara los valores predichos con las `Labels` reales del conjunto de datos de prueba y devuelve métricas sobre el rendimiento del modelo.</span><span class="sxs-lookup"><span data-stu-id="37c5c-243">Once you have the prediction set, the [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) method assesses the model, which compares the predicted values with the actual `Labels` in the test dataset and returns metrics on how the model is performing.</span></span>

<span data-ttu-id="37c5c-244">Imprima las métricas de evaluación en la consola. Para ello, agregue lo que se indica a continuación como la siguiente línea de código en el método `EvaluateModel()`:</span><span class="sxs-lookup"><span data-stu-id="37c5c-244">Print your evaluation metrics to the console by adding the following as the next line of code in the `EvaluateModel()` method:</span></span>

[!code-csharp[PrintMetrics](./snippets/movie-recommendation/csharp/Program.cs#PrintMetrics "Print the evaluation metrics")]

<span data-ttu-id="37c5c-245">Agregue lo que se indica a continuación como la siguiente línea de código en el método `Main()` para llamar al método `EvaluateModel()`:</span><span class="sxs-lookup"><span data-stu-id="37c5c-245">Add the following as the next line of code in the `Main()` method to call your `EvaluateModel()` method:</span></span>

[!code-csharp[EvaluateModelMain](./snippets/movie-recommendation/csharp/Program.cs#EvaluateModelMain "Add EvaluateModel method in Main")]

<span data-ttu-id="37c5c-246">Por el momento, la salida debe ser similar a la del texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="37c5c-246">The output so far should look similar to the following text:</span></span>

```console
=============== Training the model ===============
iter      tr_rmse          obj
   0       1.5403   3.1262e+05
   1       0.9221   1.6030e+05
   2       0.8687   1.5046e+05
   3       0.8416   1.4584e+05
   4       0.8142   1.4209e+05
   5       0.7849   1.3907e+05
   6       0.7544   1.3594e+05
   7       0.7266   1.3361e+05
   8       0.6987   1.3110e+05
   9       0.6751   1.2948e+05
  10       0.6530   1.2766e+05
  11       0.6350   1.2644e+05
  12       0.6197   1.2541e+05
  13       0.6067   1.2470e+05
  14       0.5953   1.2382e+05
  15       0.5871   1.2342e+05
  16       0.5781   1.2279e+05
  17       0.5713   1.2240e+05
  18       0.5660   1.2230e+05
  19       0.5592   1.2179e+05
=============== Evaluating the model ===============
Rms: 0.994051469730769
RSquared: 0.412556298844873
```

<span data-ttu-id="37c5c-247">En esta salida, hay 20 iteraciones.</span><span class="sxs-lookup"><span data-stu-id="37c5c-247">In this output, there are 20 iterations.</span></span> <span data-ttu-id="37c5c-248">En cada iteración, la medida de error disminuye y converge cada vez más hacia 0.</span><span class="sxs-lookup"><span data-stu-id="37c5c-248">In each iteration, the measure of error decreases and converges closer and closer to 0.</span></span>

<span data-ttu-id="37c5c-249">El valor `root of mean squared error` (RMS o RMSE) se usa para medir las diferencias entre los valores previstos por un modelo y los valores observados en un conjunto de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="37c5c-249">The `root of mean squared error` (RMS or RMSE) is used to measure the differences between the model predicted values and the test dataset observed values.</span></span> <span data-ttu-id="37c5c-250">Técnicamente, es la raíz cuadrada de la media de los cuadrados de los errores.</span><span class="sxs-lookup"><span data-stu-id="37c5c-250">Technically it's the square root of the average of the squares of the errors.</span></span> <span data-ttu-id="37c5c-251">Cuanto menor sea su valor, mejor será el modelo.</span><span class="sxs-lookup"><span data-stu-id="37c5c-251">The lower it is, the better the model is.</span></span>

<span data-ttu-id="37c5c-252">`R Squared` indica en qué grado los datos se ajustan a un modelo.</span><span class="sxs-lookup"><span data-stu-id="37c5c-252">`R Squared` indicates how well data fits a model.</span></span> <span data-ttu-id="37c5c-253">Va de 0 a 1.</span><span class="sxs-lookup"><span data-stu-id="37c5c-253">Ranges from 0 to 1.</span></span> <span data-ttu-id="37c5c-254">Un valor de 0 significa que los datos son aleatorios o no pueden ajustarse al modelo.</span><span class="sxs-lookup"><span data-stu-id="37c5c-254">A value of 0 means that the data is random or otherwise can't be fit to the model.</span></span> <span data-ttu-id="37c5c-255">Un valor de 1 significa que el modelo coincide exactamente con los datos.</span><span class="sxs-lookup"><span data-stu-id="37c5c-255">A value of 1 means that the model exactly matches the data.</span></span> <span data-ttu-id="37c5c-256">Le interesa que la puntuación de `R Squared` esté lo más cerca posible de 1.</span><span class="sxs-lookup"><span data-stu-id="37c5c-256">You want your `R Squared` score to be as close to 1 as possible.</span></span>

<span data-ttu-id="37c5c-257">La creación de modelos correctos es un proceso iterativo.</span><span class="sxs-lookup"><span data-stu-id="37c5c-257">Building successful models is an iterative process.</span></span> <span data-ttu-id="37c5c-258">Este modelo tiene una calidad inicial más baja, ya que el tutorial utiliza pequeños conjuntos de datos para proporcionar un entrenamiento rápido del modelo.</span><span class="sxs-lookup"><span data-stu-id="37c5c-258">This model has initial lower quality as the tutorial uses small datasets to provide quick model training.</span></span> <span data-ttu-id="37c5c-259">Si no está satisfecho con la calidad del modelo, puede intentar mejorarlo proporcionando conjuntos de datos de entrenamiento más grandes o eligiendo algoritmos de entrenamiento distintos con diferentes hiperparámetros para cada algoritmo.</span><span class="sxs-lookup"><span data-stu-id="37c5c-259">If you aren't satisfied with the model quality, you can try to improve it by providing larger training datasets or by choosing different training algorithms with different hyper-parameters for each algorithm.</span></span> <span data-ttu-id="37c5c-260">Para más información, revise la sección [Mejora del modelo](#improve-your-model) a continuación.</span><span class="sxs-lookup"><span data-stu-id="37c5c-260">For more information, check out the [Improve your model](#improve-your-model) section below.</span></span>

## <a name="use-your-model"></a><span data-ttu-id="37c5c-261">Uso del modelo</span><span class="sxs-lookup"><span data-stu-id="37c5c-261">Use your model</span></span>

<span data-ttu-id="37c5c-262">Ahora puede usar el modelo entrenado para realizar predicciones sobre datos nuevos.</span><span class="sxs-lookup"><span data-stu-id="37c5c-262">Now you can use your trained model to make predictions on new data.</span></span>

<span data-ttu-id="37c5c-263">Cree el método `UseModelForSinglePrediction()`, justo después del método `EvaluateModel()`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="37c5c-263">Create the `UseModelForSinglePrediction()` method, just after the `EvaluateModel()` method, using the following code:</span></span>

```csharp
public static void UseModelForSinglePrediction(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="37c5c-264">Use `PredictionEngine` para predecir la clasificación. Para ello, agregue el código siguiente a `UseModelForSinglePrediction()`:</span><span class="sxs-lookup"><span data-stu-id="37c5c-264">Use the `PredictionEngine` to predict the rating by adding the following code to `UseModelForSinglePrediction()`:</span></span>

[!code-csharp[PredictionEngine](./snippets/movie-recommendation/csharp/Program.cs#PredictionEngine "Create Prediction Engine")]

<span data-ttu-id="37c5c-265">[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) es una API de conveniencia, que le permite realizar una predicción en una única instancia de datos.</span><span class="sxs-lookup"><span data-stu-id="37c5c-265">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to perform a prediction on a single instance of data.</span></span> <span data-ttu-id="37c5c-266">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) no es seguro para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="37c5c-266">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="37c5c-267">Es aceptable usarlo en entornos de un solo subproceso o prototipo.</span><span class="sxs-lookup"><span data-stu-id="37c5c-267">It's acceptable to use in single-threaded or prototype environments.</span></span> <span data-ttu-id="37c5c-268">Para mejorar el rendimiento y la seguridad para subprocesos en entornos de producción, use el servicio `PredictionEnginePool`, que crea un [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) de objetos de [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) para su uso en toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="37c5c-268">For improved performance and thread safety in production environments, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span> <span data-ttu-id="37c5c-269">Consulte esta guía sobre cómo [usar `PredictionEnginePool` en una API web de ASP.NET Core](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span><span class="sxs-lookup"><span data-stu-id="37c5c-269">See this guide on how to [use `PredictionEnginePool` in an ASP.NET Core Web API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span></span>

> [!NOTE]
> <span data-ttu-id="37c5c-270">La extensión del servicio `PredictionEnginePool` está actualmente en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="37c5c-270">`PredictionEnginePool` service extension is currently in preview.</span></span>

<span data-ttu-id="37c5c-271">Cree una instancia de `MovieRating` denominada `testInput` y pásela al motor de predicción. Para ello, agregue lo que se indica a continuación como las siguientes líneas de código en el método `UseModelForSinglePrediction()`:</span><span class="sxs-lookup"><span data-stu-id="37c5c-271">Create an instance of `MovieRating` called `testInput` and pass it to the Prediction Engine by adding the following as the next lines of code in the `UseModelForSinglePrediction()` method:</span></span>

[!code-csharp[MakeSinglePrediction](./snippets/movie-recommendation/csharp/Program.cs#MakeSinglePrediction "Make a single prediction with the Prediction Engine")]

<span data-ttu-id="37c5c-272">La función [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) realiza una predicción en una sola columna de datos.</span><span class="sxs-lookup"><span data-stu-id="37c5c-272">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single column of data.</span></span>

<span data-ttu-id="37c5c-273">Después, puede usar `Score`, o la clasificación predicha, para determinar si quiere recomendar la película con el movieId 10 al usuario 6.</span><span class="sxs-lookup"><span data-stu-id="37c5c-273">You can then use the `Score`, or the predicted rating, to determine whether you want to recommend the movie with movieId 10 to user 6.</span></span> <span data-ttu-id="37c5c-274">Cuanto más alto sea `Score`, más probable será que a un usuario le guste una película concreta.</span><span class="sxs-lookup"><span data-stu-id="37c5c-274">The higher the `Score`, the higher the likelihood of a user liking a particular movie.</span></span> <span data-ttu-id="37c5c-275">En este caso, supongamos que recomienda películas con una clasificación predicha superior a 3,5.</span><span class="sxs-lookup"><span data-stu-id="37c5c-275">In this case, let’s say that you recommend movies with a predicted rating of > 3.5.</span></span>

<span data-ttu-id="37c5c-276">Para imprimir los resultados, agregue lo que se indica a continuación como las siguientes líneas de código en el método `UseModelForSinglePrediction()`:</span><span class="sxs-lookup"><span data-stu-id="37c5c-276">To print the results, add the following as the next lines of code in the `UseModelForSinglePrediction()` method:</span></span>

[!code-csharp[PrintResults](./snippets/movie-recommendation/csharp/Program.cs#PrintResults "Print the recommendation prediction results")]

<span data-ttu-id="37c5c-277">Agregue lo que se indica a continuación como la siguiente línea de código en el método `Main()` para llamar al método `UseModelForSinglePrediction()`:</span><span class="sxs-lookup"><span data-stu-id="37c5c-277">Add the following as the next line of code in the `Main()` method to call your `UseModelForSinglePrediction()` method:</span></span>

[!code-csharp[UseModelMain](./snippets/movie-recommendation/csharp/Program.cs#UseModelMain "Add UseModelForSinglePrediction method in Main")]

<span data-ttu-id="37c5c-278">La salida de este método debe ser similar a la del texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="37c5c-278">The output of this method should look similar to the following text:</span></span>

```console
=============== Making a prediction ===============
Movie 10 is recommended for user 6
```

### <a name="save-your-model"></a><span data-ttu-id="37c5c-279">Guardado del modelo</span><span class="sxs-lookup"><span data-stu-id="37c5c-279">Save your model</span></span>

<span data-ttu-id="37c5c-280">Para usar el modelo con el objeto de realizar predicciones en aplicaciones de usuario final, primero debe guardarlo.</span><span class="sxs-lookup"><span data-stu-id="37c5c-280">To use your model to make predictions in end-user applications, you must first save the model.</span></span>

<span data-ttu-id="37c5c-281">Cree el método `SaveModel()`, justo después del método `UseModelForSinglePrediction()`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="37c5c-281">Create the `SaveModel()` method, just after the `UseModelForSinglePrediction()` method, using the following code:</span></span>

```csharp
public static void SaveModel(MLContext mlContext, DataViewSchema trainingDataViewSchema, ITransformer model)
{

}
```

<span data-ttu-id="37c5c-282">Para guardar el modelo entrenado, agregue el código siguiente en el método `SaveModel()`:</span><span class="sxs-lookup"><span data-stu-id="37c5c-282">Save your trained model by adding the following code in the `SaveModel()` method:</span></span>

[!code-csharp[SaveModel](./snippets/movie-recommendation/csharp/Program.cs#SaveModel "Save the model to a zip file")]

<span data-ttu-id="37c5c-283">Este método guarda el modelo entrenado en un archivo .zip (en la carpeta "Datos"), que puede usarse después en otras aplicaciones .NET para realizar predicciones.</span><span class="sxs-lookup"><span data-stu-id="37c5c-283">This method saves your trained model to a .zip file (in the "Data" folder), which can then be used in other .NET applications to make predictions.</span></span>

<span data-ttu-id="37c5c-284">Agregue lo que se indica a continuación como la siguiente línea de código en el método `Main()` para llamar al método `SaveModel()`:</span><span class="sxs-lookup"><span data-stu-id="37c5c-284">Add the following as the next line of code in the `Main()` method to call your `SaveModel()` method:</span></span>

[!code-csharp[SaveModelMain](./snippets/movie-recommendation/csharp/Program.cs#SaveModelMain "Create SaveModel method in Main")]

### <a name="use-your-saved-model"></a><span data-ttu-id="37c5c-285">Uso del modelo guardado</span><span class="sxs-lookup"><span data-stu-id="37c5c-285">Use your saved model</span></span>

<span data-ttu-id="37c5c-286">Una vez que haya guardado el modelo entrenado, puede usarlo en entornos diferentes.</span><span class="sxs-lookup"><span data-stu-id="37c5c-286">Once you have saved your trained model, you can consume the model in different environments.</span></span> <span data-ttu-id="37c5c-287">Consulte [Guardar y cargar modelos entrenados](../how-to-guides/save-load-machine-learning-models-ml-net.md) para obtener información sobre cómo poner en marcha un modelo de aprendizaje automático entrenado en aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="37c5c-287">See [Save and load trained models](../how-to-guides/save-load-machine-learning-models-ml-net.md) to learn how to operationalize a trained machine learning model in apps.</span></span>

## <a name="results"></a><span data-ttu-id="37c5c-288">Resultados</span><span class="sxs-lookup"><span data-stu-id="37c5c-288">Results</span></span>

<span data-ttu-id="37c5c-289">Después de seguir los pasos anteriores, ejecute la aplicación de consola (CTRL + F5).</span><span class="sxs-lookup"><span data-stu-id="37c5c-289">After following the steps above, run your console app (Ctrl + F5).</span></span> <span data-ttu-id="37c5c-290">Los resultados de la predicción anterior deben ser similares a lo que se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="37c5c-290">Your results from the single prediction above should be similar to the following.</span></span> <span data-ttu-id="37c5c-291">Es posible que vea advertencias o mensajes de procesamiento, si bien se han quitado de los resultados siguientes para mayor claridad.</span><span class="sxs-lookup"><span data-stu-id="37c5c-291">You may see warnings or processing messages, but these messages have been removed from the following results for clarity.</span></span>

```console
=============== Training the model ===============
iter      tr_rmse          obj
   0       1.5382   3.1213e+05
   1       0.9223   1.6051e+05
   2       0.8691   1.5050e+05
   3       0.8413   1.4576e+05
   4       0.8145   1.4208e+05
   5       0.7848   1.3895e+05
   6       0.7552   1.3613e+05
   7       0.7259   1.3357e+05
   8       0.6987   1.3121e+05
   9       0.6747   1.2949e+05
  10       0.6533   1.2766e+05
  11       0.6353   1.2636e+05
  12       0.6209   1.2561e+05
  13       0.6072   1.2462e+05
  14       0.5965   1.2394e+05
  15       0.5868   1.2352e+05
  16       0.5782   1.2279e+05
  17       0.5713   1.2227e+05
  18       0.5637   1.2190e+05
  19       0.5604   1.2178e+05
=============== Evaluating the model ===============
Rms: 0.977175077487166
RSquared: 0.43233349213192
=============== Making a prediction ===============
Movie 10 is recommended for user 6
=============== Saving the model to a file ===============
```

<span data-ttu-id="37c5c-292">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="37c5c-292">Congratulations!</span></span> <span data-ttu-id="37c5c-293">Ha compilado correctamente un modelo de Machine Learning para la recomendación de películas.</span><span class="sxs-lookup"><span data-stu-id="37c5c-293">You've now successfully built a machine learning model for recommending movies.</span></span> <span data-ttu-id="37c5c-294">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/MovieRecommendation).</span><span class="sxs-lookup"><span data-stu-id="37c5c-294">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/MovieRecommendation) repository.</span></span>

## <a name="improve-your-model"></a><span data-ttu-id="37c5c-295">Mejora del código</span><span class="sxs-lookup"><span data-stu-id="37c5c-295">Improve your model</span></span>

<span data-ttu-id="37c5c-296">Hay varias maneras de mejorar el rendimiento del modelo para obtener predicciones más precisas.</span><span class="sxs-lookup"><span data-stu-id="37c5c-296">There are several ways that you can improve the performance of your model so that you can get more accurate predictions.</span></span>

### <a name="data"></a><span data-ttu-id="37c5c-297">Datos</span><span class="sxs-lookup"><span data-stu-id="37c5c-297">Data</span></span>

<span data-ttu-id="37c5c-298">El hecho de agregar más datos de entrenamiento con suficientes ejemplos para cada usuario e identificador de película puede ayudar a mejorar la calidad del modelo de recomendación.</span><span class="sxs-lookup"><span data-stu-id="37c5c-298">Adding more training data that has enough samples for each user and movie id can help improve the quality of the recommendation model.</span></span>

<span data-ttu-id="37c5c-299">La [validación cruzada](../how-to-guides/train-machine-learning-model-cross-validation-ml-net.md) es una técnica para evaluar modelos que divide aleatoriamente los datos en subconjuntos (en lugar de extraer datos de prueba del conjunto de datos, como ha hecho en este tutorial) y toma algunos grupos como datos de entrenamiento y otros como datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="37c5c-299">[Cross validation](../how-to-guides/train-machine-learning-model-cross-validation-ml-net.md) is a technique for evaluating models that randomly splits up data into subsets (instead of extracting out test data from the dataset like you did in this tutorial) and takes some of the groups as train data and some of the groups as test data.</span></span> <span data-ttu-id="37c5c-300">Este método supera en lo que respecta a la calidad del modelo la división en entrenamiento/prueba.</span><span class="sxs-lookup"><span data-stu-id="37c5c-300">This method outperforms making a train-test split in terms of model quality.</span></span>

### <a name="features"></a><span data-ttu-id="37c5c-301">Características</span><span class="sxs-lookup"><span data-stu-id="37c5c-301">Features</span></span>

<span data-ttu-id="37c5c-302">En este tutorial, solo ha usado las tres `Features` (`user id`, `movie id` y `rating`) que proporciona el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="37c5c-302">In this tutorial, you only use the three `Features` (`user id`, `movie id`, and `rating`) that are provided by the dataset.</span></span>

<span data-ttu-id="37c5c-303">Aunque es un buen comienzo, tal vez le interese agregar otros atributos o `Features` (por ejemplo, edad, sexo, ubicación geográfica, etc.) si se incluyen en el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="37c5c-303">While this is a good start, in reality you might want to add other attributes or `Features` (for example, age, gender, geo-location, etc.) if they are included in the dataset.</span></span> <span data-ttu-id="37c5c-304">El hecho de agregar `Features` más pertinentes puede ayudar a mejorar el rendimiento del modelo de recomendación.</span><span class="sxs-lookup"><span data-stu-id="37c5c-304">Adding more relevant `Features` can help improve the performance of your recommendation model.</span></span>

<span data-ttu-id="37c5c-305">Si no está seguro de qué `Features` pueden ser más pertinentes para la tarea de aprendizaje automático, puede usar el Cálculo de la contribución de las características (FCC) y la [importancia de la característica de permutación](../how-to-guides/explain-machine-learning-model-permutation-feature-importance-ml-net.md), que proporciona ML.NET para descubrir las `Features` más influyentes.</span><span class="sxs-lookup"><span data-stu-id="37c5c-305">If you are unsure about which `Features` might be the most relevant for your machine learning task, you can also make use of Feature Contribution Calculation (FCC) and [permutation feature importance](../how-to-guides/explain-machine-learning-model-permutation-feature-importance-ml-net.md), which ML.NET provides to discover the most influential `Features`.</span></span>

### <a name="algorithm-hyperparameters"></a><span data-ttu-id="37c5c-306">Hiperparámetros de algoritmo</span><span class="sxs-lookup"><span data-stu-id="37c5c-306">Algorithm hyperparameters</span></span>

<span data-ttu-id="37c5c-307">Aunque ML.NET proporciona algoritmos de entrenamiento predeterminados de calidad, puede ajustar aún más el rendimiento si cambia los [hiperparámetros](../resources/glossary.md#hyperparameter) del algoritmo.</span><span class="sxs-lookup"><span data-stu-id="37c5c-307">While ML.NET provides good default training algorithms, you can further fine-tune performance by changing the algorithm's [hyperparameters](../resources/glossary.md#hyperparameter).</span></span>

<span data-ttu-id="37c5c-308">Para `Matrix Factorization`, puede experimentar con hiperparámetros como [NumberOfIterations](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.NumberOfIterations) y [ApproximationRank](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.ApproximationRank) para ver si así obtiene mejores resultados.</span><span class="sxs-lookup"><span data-stu-id="37c5c-308">For `Matrix Factorization`, you can experiment with hyperparameters such as [NumberOfIterations](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.NumberOfIterations) and [ApproximationRank](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.ApproximationRank) to see if that gives you better results.</span></span>

<span data-ttu-id="37c5c-309">Por ejemplo, en este tutorial, las opciones de algoritmo son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="37c5c-309">For instance, in this tutorial the algorithm options are:</span></span>

```csharp
var options = new MatrixFactorizationTrainer.Options
{
    MatrixColumnIndexColumnName = "userIdEncoded",
    MatrixRowIndexColumnName = "movieIdEncoded",
    LabelColumnName = "Label",
    NumberOfIterations = 20,
    ApproximationRank = 100
};
```

### <a name="other-recommendation-algorithms"></a><span data-ttu-id="37c5c-310">Otros algoritmos de recomendación</span><span class="sxs-lookup"><span data-stu-id="37c5c-310">Other Recommendation Algorithms</span></span>

<span data-ttu-id="37c5c-311">El algoritmo de factorización matricial con filtrado de colaboración es solo un enfoque para realizar recomendaciones de películas.</span><span class="sxs-lookup"><span data-stu-id="37c5c-311">The matrix factorization algorithm with collaborative filtering is only one approach for performing movie recommendations.</span></span> <span data-ttu-id="37c5c-312">En muchos casos, es posible que no tenga a su disposición los datos de las clasificaciones y que solo cuente con el historial de películas de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="37c5c-312">In many cases, you may not have the ratings data available and only have movie history available from users.</span></span> <span data-ttu-id="37c5c-313">En otros casos, podría disponer de más datos que la clasificación del usuario.</span><span class="sxs-lookup"><span data-stu-id="37c5c-313">In other cases, you may have more than just the user’s rating data.</span></span>

| <span data-ttu-id="37c5c-314">Algoritmo</span><span class="sxs-lookup"><span data-stu-id="37c5c-314">Algorithm</span></span>       | <span data-ttu-id="37c5c-315">Escenario</span><span class="sxs-lookup"><span data-stu-id="37c5c-315">Scenario</span></span>           | <span data-ttu-id="37c5c-316">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="37c5c-316">Sample</span></span>  |
| ------------- |:-------------:| -----:|
| <span data-ttu-id="37c5c-317">Factorización matricial de una clase</span><span class="sxs-lookup"><span data-stu-id="37c5c-317">One Class Matrix Factorization</span></span> | <span data-ttu-id="37c5c-318">Úselo cuando solo tenga los valores userId y movieId.</span><span class="sxs-lookup"><span data-stu-id="37c5c-318">Use this when you only have userId and movieId.</span></span> <span data-ttu-id="37c5c-319">Este tipo de recomendación se basa en el escenario de compra conjunta, es decir, en los productos que se suelen comprar juntos. Esto significa que se recomendará a los clientes un conjunto de productos en función de su propio historial de pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="37c5c-319">This style of recommendation is based upon the co-purchase scenario, or products frequently bought together, which means it will recommend to customers a set of products based upon their own purchase order history.</span></span> | [<span data-ttu-id="37c5c-320">>Pruébelo</span><span class="sxs-lookup"><span data-stu-id="37c5c-320">>Try it out</span></span>](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/MatrixFactorization_ProductRecommendation) |
| <span data-ttu-id="37c5c-321">Máquinas de factorización con reconocimiento de campo</span><span class="sxs-lookup"><span data-stu-id="37c5c-321">Field Aware Factorization Machines</span></span> | <span data-ttu-id="37c5c-322">Úselo para realizar recomendaciones cuando disponga de más características que userId, productId y la clasificación (por ejemplo, la descripción o el precio del producto).</span><span class="sxs-lookup"><span data-stu-id="37c5c-322">Use this to make recommendations when you have more Features beyond userId, productId, and rating (such as product description or product price).</span></span> <span data-ttu-id="37c5c-323">Este método también usa un enfoque de filtrado de colaboración.</span><span class="sxs-lookup"><span data-stu-id="37c5c-323">This method also uses a collaborative filtering approach.</span></span> | [<span data-ttu-id="37c5c-324">>Pruébelo</span><span class="sxs-lookup"><span data-stu-id="37c5c-324">>Try it out</span></span>](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/end-to-end-apps/Recommendation-MovieRecommender) |

### <a name="new-user-scenario"></a><span data-ttu-id="37c5c-325">Escenario de nuevo usuario</span><span class="sxs-lookup"><span data-stu-id="37c5c-325">New user scenario</span></span>

<span data-ttu-id="37c5c-326">Un problema común en el filtrado de colaboración es el "arranque en frío", que es cuando tiene un nuevo usuario sin ningún dato anterior a partir del cual pueda realizar inferencias.</span><span class="sxs-lookup"><span data-stu-id="37c5c-326">One common problem in collaborative filtering is the cold start problem, which is when you have a new user with no previous data to draw inferences from.</span></span> <span data-ttu-id="37c5c-327">Por lo general, para solucionarlo se les pide a los nuevos usuarios que creen un perfil y, por ejemplo, clasifiquen películas que ya han visto.</span><span class="sxs-lookup"><span data-stu-id="37c5c-327">This problem is often solved by asking new users to create a profile and, for instance, rate movies they have seen in the past.</span></span> <span data-ttu-id="37c5c-328">Aunque este método supone una relativa carga para el usuario, proporciona algunos datos iniciales para los usuarios nuevos que carecen de historial de clasificaciones.</span><span class="sxs-lookup"><span data-stu-id="37c5c-328">While this method puts some burden on the user, it provides some starting data for new users with no rating history.</span></span>

## <a name="resources"></a><span data-ttu-id="37c5c-329">Recursos</span><span class="sxs-lookup"><span data-stu-id="37c5c-329">Resources</span></span>

<span data-ttu-id="37c5c-330">Los datos que se han usado en este tutorial se han tomado del [conjunto de datos MovieLens](http://files.grouplens.org/datasets/movielens/).</span><span class="sxs-lookup"><span data-stu-id="37c5c-330">The data used in this tutorial is derived from [MovieLens Dataset](http://files.grouplens.org/datasets/movielens/).</span></span>

## <a name="next-steps"></a><span data-ttu-id="37c5c-331">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="37c5c-331">Next steps</span></span>

<span data-ttu-id="37c5c-332">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="37c5c-332">In this tutorial, you learned how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="37c5c-333">Seleccionar un algoritmo de Machine Learning</span><span class="sxs-lookup"><span data-stu-id="37c5c-333">Select a machine learning algorithm</span></span>
> * <span data-ttu-id="37c5c-334">Preparar y cargar los datos</span><span class="sxs-lookup"><span data-stu-id="37c5c-334">Prepare and load your data</span></span>
> * <span data-ttu-id="37c5c-335">Compilar y entrenar un modelo</span><span class="sxs-lookup"><span data-stu-id="37c5c-335">Build and train a model</span></span>
> * <span data-ttu-id="37c5c-336">Evaluar un modelo</span><span class="sxs-lookup"><span data-stu-id="37c5c-336">Evaluate a model</span></span>
> * <span data-ttu-id="37c5c-337">Implementar y consumir un modelo</span><span class="sxs-lookup"><span data-stu-id="37c5c-337">Deploy and consume a model</span></span>

<span data-ttu-id="37c5c-338">Siga con el siguiente tutorial para obtener más información</span><span class="sxs-lookup"><span data-stu-id="37c5c-338">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="37c5c-339">Análisis de sentimiento</span><span class="sxs-lookup"><span data-stu-id="37c5c-339">Sentiment Analysis</span></span>](sentiment-analysis.md)
