---
title: 'Tutorial: Compilar una recomendación de películas'
description: Este tutorial muestra cómo compilar una recomendación de películas con ML.NET en una consola de aplicación de .NET Core. Los pasos utilizan C# y Visual Studio 2019.
author: briacht
ms.author: johalex
ms.date: 05/06/2019
ms.custom: mvc
ms.topic: tutorial
ms.openlocfilehash: 5d459d8b28298250f3b815e33ff4d85ac54f79c2
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063370"
---
# <a name="tutorial-create-a-movie-recommender-with-mlnet"></a><span data-ttu-id="a0cd7-104">Tutorial: Creación de un recomendador de películas con ML.NET</span><span class="sxs-lookup"><span data-stu-id="a0cd7-104">Tutorial: Create a Movie Recommender with ML.NET</span></span>

<span data-ttu-id="a0cd7-105">Este tutorial muestra cómo compilar una recomendación de películas con ML.NET en una consola de aplicación de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-105">This tutorial shows you how to build a movie recommender with ML.NET in a .NET Core console application.</span></span> <span data-ttu-id="a0cd7-106">Los pasos utilizan C# y Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-106">The steps use C# and Visual Studio 2019.</span></span>

<span data-ttu-id="a0cd7-107">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="a0cd7-108">Seleccionar un algoritmo de Machine Learning</span><span class="sxs-lookup"><span data-stu-id="a0cd7-108">Select a machine learning algorithm</span></span>
> * <span data-ttu-id="a0cd7-109">Preparar y cargar los datos</span><span class="sxs-lookup"><span data-stu-id="a0cd7-109">Prepare and load your data</span></span>
> * <span data-ttu-id="a0cd7-110">Compilar y entrenar un modelo</span><span class="sxs-lookup"><span data-stu-id="a0cd7-110">Build and train a model</span></span>
> * <span data-ttu-id="a0cd7-111">Evaluar un modelo</span><span class="sxs-lookup"><span data-stu-id="a0cd7-111">Evaluate a model</span></span>
> * <span data-ttu-id="a0cd7-112">Implementar y consumir un modelo</span><span class="sxs-lookup"><span data-stu-id="a0cd7-112">Deploy and consume a model</span></span>

<span data-ttu-id="a0cd7-113">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/MovieRecommendation).</span><span class="sxs-lookup"><span data-stu-id="a0cd7-113">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/MovieRecommendation) repository.</span></span>

## <a name="machine-learning-workflow"></a><span data-ttu-id="a0cd7-114">Flujo de trabajo del aprendizaje automático</span><span class="sxs-lookup"><span data-stu-id="a0cd7-114">Machine learning workflow</span></span>

<span data-ttu-id="a0cd7-115">Usará los pasos siguientes para realizar la tarea, así como cualquier otra tarea de ML.NET:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-115">You will use the following steps to accomplish your task, as well as any other ML.NET task:</span></span>

1. [<span data-ttu-id="a0cd7-116">Cargar los datos</span><span class="sxs-lookup"><span data-stu-id="a0cd7-116">Load your data</span></span>](#load-your-data)
2. [<span data-ttu-id="a0cd7-117">Compilar y entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="a0cd7-117">Build and train your model</span></span>](#build-and-train-your-model)
3. [<span data-ttu-id="a0cd7-118">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="a0cd7-118">Evaluate your model</span></span>](#evaluate-your-model)
4. [<span data-ttu-id="a0cd7-119">Usar el modelo</span><span class="sxs-lookup"><span data-stu-id="a0cd7-119">Use your model</span></span>](#use-your-model)

## <a name="prerequisites"></a><span data-ttu-id="a0cd7-120">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a0cd7-120">Prerequisites</span></span>

* <span data-ttu-id="a0cd7-121">[Visual Studio 2017 15.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-121">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="a0cd7-122">Seleccionar la tarea de aprendizaje automático adecuada</span><span class="sxs-lookup"><span data-stu-id="a0cd7-122">Select the appropriate machine learning task</span></span>

<span data-ttu-id="a0cd7-123">Hay varias maneras de enfocar los problemas vinculados a las recomendaciones, como recomendar una lista de películas o recomendar una lista de productos relacionados. En este caso, predecirá qué clasificación (de 1 a 5) asignará un usuario a una película concreta y recomendará esa película si es superior a un umbral definido (cuanto mayor sea la clasificación, más probable será que a un usuario le guste una película concreta).</span><span class="sxs-lookup"><span data-stu-id="a0cd7-123">There are several ways to approach recommendation problems, such as recommending a list of movies or recommending a list of related products, but in this case you will predict what rating (1-5) a user will give to a particular movie and recommend that movie if it's higher than a defined threshold (the higher the rating, the higher the likelihood of a user liking a particular movie).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="a0cd7-124">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="a0cd7-124">Create a console application</span></span>

### <a name="create-a-project"></a><span data-ttu-id="a0cd7-125">Crear un proyecto</span><span class="sxs-lookup"><span data-stu-id="a0cd7-125">Create a project</span></span>

1. <span data-ttu-id="a0cd7-126">Abra Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-126">Open Visual Studio 2017.</span></span> <span data-ttu-id="a0cd7-127">Seleccione **Archivo** > **Nuevo** > **Proyecto** de la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-127">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="a0cd7-128">En el cuadro de diálogo **Nuevo proyecto**, seleccione el nodo **Visual C#** seguido del nodo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-128">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="a0cd7-129">Después, seleccione la plantilla del proyecto **Aplicación de consola (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-129">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="a0cd7-130">En el cuadro de texto **Nombre**, escriba "MovieRecommender" y haga clic en el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-130">In the **Name** text box, type "MovieRecommender" and then select the **OK** button.</span></span>

2. <span data-ttu-id="a0cd7-131">Cree un directorio denominado *Datos* en el proyecto para almacenar el conjunto de datos:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-131">Create a directory named *Data* in your project to store the data set:</span></span>

    <span data-ttu-id="a0cd7-132">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **Nueva carpeta**.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-132">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="a0cd7-133">Escriba "Datos" y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-133">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="a0cd7-134">Instale los paquetes NuGet **Microsoft.ML** y **Microsoft.ML.Recommender**:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-134">Install the **Microsoft.ML** and **Microsoft.ML.Recommender** NuGet Packages:</span></span>

    <span data-ttu-id="a0cd7-135">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-135">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="a0cd7-136">Elija "nuget.org" como origen del paquete, seleccione la pestaña **Examinar**, busque **Microsoft.ML**, seleccione el paquete **1.0.0** en la lista y seleccione el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-136">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select the **1.0.0** package in the list, and select the **Install** button.</span></span> <span data-ttu-id="a0cd7-137">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-137">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span> <span data-ttu-id="a0cd7-138">Repita estos pasos para **Microsoft.ML.Recommender v0.12.0**.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-138">Repeat these steps for **Microsoft.ML.Recommender v0.12.0**.</span></span>

4. <span data-ttu-id="a0cd7-139">Agregue las instrucciones `using` siguientes en la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-139">Add the following `using` statements at the top of your *Program.cs* file:</span></span>

    [!code-csharp[UsingStatements](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#UsingStatements "Add necessary usings")]

### <a name="download-your-data"></a><span data-ttu-id="a0cd7-140">Descarga de los datos</span><span class="sxs-lookup"><span data-stu-id="a0cd7-140">Download your data</span></span>

1. <span data-ttu-id="a0cd7-141">Descargue los dos conjuntos de datos y guárdelos en la carpeta *Datos* que creó anteriormente:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-141">Download the two datasets and save them to the *Data* folder you previously created:</span></span>

   * <span data-ttu-id="a0cd7-142">Haga clic con el botón derecho en [*recommendation-ratings-train.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-train.csv) y seleccione "Save Link (or Target) As…" ("Guardar vínculo (o destino) como…").</span><span class="sxs-lookup"><span data-stu-id="a0cd7-142">Right click on [*recommendation-ratings-train.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-train.csv) and select "Save Link (or Target) As..."</span></span>
   * <span data-ttu-id="a0cd7-143">Haga clic con el botón derecho en [*recommendation-ratings-test.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-test.csv) y seleccione "Save Link (or Target) As…" ("Guardar vínculo (o destino) como…").</span><span class="sxs-lookup"><span data-stu-id="a0cd7-143">Right click on [*recommendation-ratings-test.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-test.csv) and select "Save Link (or Target) As..."</span></span>

     <span data-ttu-id="a0cd7-144">Asegúrese de guardar los archivos \*.csv en la carpeta *Datos*. Si los guarda en otro lugar, recuerde que debe mover los archivos \*.csv a la carpeta *Datos*.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-144">Make sure you either save the \*.csv files to the *Data* folder, or after you save it elsewhere, move the \*.csv files to the *Data* folder.</span></span>

2. <span data-ttu-id="a0cd7-145">En el Explorador de soluciones, haga clic con el botón secundario en cada uno de los archivos \*.csv y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-145">In Solution Explorer, right-click each of the \*.csv files and select **Properties**.</span></span> <span data-ttu-id="a0cd7-146">En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-146">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

   ![copiar si es posterior en VS](./media/movie-recommendation/copytoout.gif)

## <a name="load-your-data"></a><span data-ttu-id="a0cd7-148">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="a0cd7-148">Load your data</span></span>

<span data-ttu-id="a0cd7-149">El primer paso en el proceso de ML.NET consiste en preparar y cargar los datos de entrenamiento y prueba del modelo.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-149">The first step in the ML.NET process is to prepare and load your model training and testing data.</span></span>

<span data-ttu-id="a0cd7-150">Los datos de las clasificaciones de recomendación se dividen en conjuntos de datos `Train` y `Test`.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-150">The recommendation ratings data is split into `Train` and `Test` datasets.</span></span> <span data-ttu-id="a0cd7-151">Los datos `Train` se usan para ajustar el modelo,</span><span class="sxs-lookup"><span data-stu-id="a0cd7-151">The `Train` data is used to fit your model.</span></span> <span data-ttu-id="a0cd7-152">mientras que los datos `Test` sirven para realizar predicciones con el modelo entrenado y evaluar el rendimiento del modelo.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-152">The `Test` data is used to make predictions with your trained model and evaluate model performance.</span></span> <span data-ttu-id="a0cd7-153">Los datos `Train` y `Test` suelen dividirse con una proporción de 80/20.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-153">It's common to have an 80/20 split with `Train` and `Test` data.</span></span>

<span data-ttu-id="a0cd7-154">A continuación se muestra una vista previa de los datos de los archivos \*.csv:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-154">Below is a preview of the data from your \*.csv files:</span></span>

![vista previa de los datos](./media/movie-recommendation/csv-dataset-preview.png)

<span data-ttu-id="a0cd7-156">En los archivos \*.csv, hay cuatro columnas:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-156">In the \*.csv files, there are four columns:</span></span>

* `userId`
* `movieId`
* `rating`
* `timestamp`

<span data-ttu-id="a0cd7-157">En Machine Learning, las columnas que se usan para realizar una predicción se denominan [Features](../resources/glossary.md#feature) (Características), mientras que la columna con la predicción devuelta recibe el nombre de [Label](../resources/glossary.md#label) (Etiqueta).</span><span class="sxs-lookup"><span data-stu-id="a0cd7-157">In machine learning, the columns that are used to make a prediction are called [Features](../resources/glossary.md#feature), and the column with the returned prediction is called the [Label](../resources/glossary.md#label).</span></span>

<span data-ttu-id="a0cd7-158">En su caso, quiere predecir clasificaciones de películas, por lo que la columna de clasificación es `Label`.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-158">You want to predict movie ratings, so the rating column is the `Label`.</span></span> <span data-ttu-id="a0cd7-159">Las otras tres columnas (`userId`, `movieId` y `timestamp`) son `Features` que se usan para predecir la `Label`.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-159">The other three columns, `userId`, `movieId`, and `timestamp` are all `Features` used to predict the `Label`.</span></span>

| <span data-ttu-id="a0cd7-160">Características</span><span class="sxs-lookup"><span data-stu-id="a0cd7-160">Features</span></span>      | <span data-ttu-id="a0cd7-161">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="a0cd7-161">Label</span></span>         |
| ------------- |:-------------:|
| `userId`        |    `rating`     |
| `movieId`      |               |
| `timestamp`     |               |

<span data-ttu-id="a0cd7-162">Usted decide qué `Features` se usan para predecir la `Label`.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-162">It's up to you to decide which `Features` are used to predict the `Label`.</span></span> <span data-ttu-id="a0cd7-163">También puede usar métodos como la [importancia de la permutación de las características](../how-to-guides/determine-global-feature-importance-in-model.md) para ayudar a seleccionar las mejores `Features`.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-163">You can also use methods like [Feature Permutation Importance](../how-to-guides/determine-global-feature-importance-in-model.md) to help with selecting the best `Features`.</span></span>

<span data-ttu-id="a0cd7-164">En este caso, debe eliminar la columna `timestamp` como `Feature` porque la marca de tiempo no afecta realmente a la manera en que un usuario clasifica una película determinada y, por tanto, no contribuye a realizar una predicción más exacta:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-164">In this case, you should eliminate the `timestamp` column as a `Feature` because the timestamp does not really affect how a user rates a given movie and thus would not contribute to making a more accurate prediction:</span></span>

| <span data-ttu-id="a0cd7-165">Características</span><span class="sxs-lookup"><span data-stu-id="a0cd7-165">Features</span></span>      | <span data-ttu-id="a0cd7-166">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="a0cd7-166">Label</span></span>         |
| ------------- |:-------------:|
| `userId`        |    `rating`     |
| `movieId`      |               |

<span data-ttu-id="a0cd7-167">Después, debe definir la estructura de datos para la clase de entrada.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-167">Next you must define your data structure for the input class.</span></span>

<span data-ttu-id="a0cd7-168">Agregue una nueva clase a su proyecto:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-168">Add a new class to your project:</span></span>

1. <span data-ttu-id="a0cd7-169">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar > Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-169">In **Solution Explorer**, right-click the project, and then select **Add > New Item**.</span></span>

2. <span data-ttu-id="a0cd7-170">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *MovieRatingData.cs*.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-170">In the **Add New Item dialog box**, select **Class** and change the **Name** field to *MovieRatingData.cs*.</span></span> <span data-ttu-id="a0cd7-171">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-171">Then, select the **Add** button.</span></span>

<span data-ttu-id="a0cd7-172">Se abre el archivo *MovieRatingData.cs* en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-172">The *MovieRatingData.cs* file opens in the code editor.</span></span> <span data-ttu-id="a0cd7-173">Agregue la siguiente instrucción `using` a la parte superior de *MovieRatingData.cs*:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-173">Add the following `using` statement to the top of *MovieRatingData.cs*:</span></span>

```csharp
using Microsoft.ML.Data;
```

<span data-ttu-id="a0cd7-174">Cree una clase denominada `MovieRating`. Para ello, quite la definición de clase existente y agregue el siguiente código en *MovieRatingData.cs*:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-174">Create a class called `MovieRating` by removing the existing class definition and adding the following code in *MovieRatingData.cs*:</span></span>

[!code-csharp[MovieRatingClass](~/samples/machine-learning/tutorials/MovieRecommendation/MovieRatingData.cs#MovieRatingClass "Add the Movie Rating class")]

<span data-ttu-id="a0cd7-175">`MovieRating` especifica una clase de datos de entrada.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-175">`MovieRating` specifies an input data class.</span></span> <span data-ttu-id="a0cd7-176">El atributo [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) especifica qué columnas (por índice de columna) del conjunto de datos se deben cargar.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-176">The [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) attribute specifies which columns (by column index) in the dataset should be loaded.</span></span> <span data-ttu-id="a0cd7-177">Las columnas `userId` y `movieId` son las `Features` (las entradas que proporcionará al modelo para predecir la `Label`), y la columna de clasificación es la `Label` que predecirá (la salida del modelo).</span><span class="sxs-lookup"><span data-stu-id="a0cd7-177">The `userId` and `movieId` columns are your `Features` (the inputs you will give the model to predict the `Label`), and the rating column is the `Label` that you will predict (the output of the model).</span></span>

<span data-ttu-id="a0cd7-178">Cree otra clase (`MovieRatingPrediction`) para representar los resultados predichos. Para ello, agregue el código siguiente después de la clase `MovieRating` en *MovieRatingData.cs*:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-178">Create another class, `MovieRatingPrediction`, to represent predicted results by adding the following code after the `MovieRating` class in *MovieRatingData.cs*:</span></span>

[!code-csharp[PredictionClass](~/samples/machine-learning/tutorials/MovieRecommendation/MovieRatingData.cs#PredictionClass "Add the Movie Prediction Class")]

<span data-ttu-id="a0cd7-179">En *Program.cs*, reemplace `Console.WriteLine("Hello World!")` por el código siguiente dentro de `Main()`:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-179">In *Program.cs*, replace the `Console.WriteLine("Hello World!")` with the following code inside `Main()`:</span></span>

[!code-csharp[MLContext](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#MLContext "Add MLContext")]

<span data-ttu-id="a0cd7-180">La [clase MLContext](xref:Microsoft.ML.MLContext) es un punto de partida para todas las operaciones de ML.NET. Al inicializar `mlContext`, se crea un entorno de ML.NET que se puede compartir entre los objetos del flujo de trabajo de creación de modelos.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-180">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="a0cd7-181">Como concepto, se parece a `DBContext` en Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-181">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

<span data-ttu-id="a0cd7-182">Después de `Main()`, cree un método denominado `LoadData()`:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-182">After `Main()`, create a method called `LoadData()`:</span></span>

```csharp
public static (IDataView training, IDataView test) LoadData(MLContext mlContext)
{

}
```

> [!NOTE]
> <span data-ttu-id="a0cd7-183">Este método generará un error hasta que agregue una instrucción return en los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-183">This method will give you an error until you add a return statement in the following steps.</span></span>

<span data-ttu-id="a0cd7-184">Inicialice las variables de ruta de acceso de datos, cargue los datos de los archivos \*.csv y devuelva los datos `Train` y `Test` como objetos `IDataView`. Para ello, agregue lo que se indica a continuación como la siguiente línea de código en `LoadData()`:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-184">Initialize your data path variables, load the data from the \*.csv files, and return the `Train` and `Test` data as `IDataView` objects by adding the following as the next line of code in `LoadData()`:</span></span>

[!code-csharp[LoadData](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#LoadData "Load data from data paths")]

<span data-ttu-id="a0cd7-185">Los datos de ML.NET se representan como una [clase IDataView](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="a0cd7-185">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="a0cd7-186">`IDataView` es una manera flexible y eficiente de describir datos tabulares (numéricos y de texto).</span><span class="sxs-lookup"><span data-stu-id="a0cd7-186">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="a0cd7-187">Los datos se pueden cargar desde un archivo de texto o en tiempo real (por ejemplo, archivos de registro o base de datos SQL) en un objeto `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-187">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

<span data-ttu-id="a0cd7-188">[LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) define el esquema de datos y lee en el archivo.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-188">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) defines the data schema and reads in the file.</span></span> <span data-ttu-id="a0cd7-189">Toma las variables de ruta de acceso de datos y devuelve `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-189">It takes in the data path variables and returns an `IDataView`.</span></span> <span data-ttu-id="a0cd7-190">En este caso, usted proporciona la ruta de acceso a los archivos `Test` y `Train` e indica el encabezado del archivo de texto (para que pueda usar correctamente los nombres de columna) y el separador de datos de caracteres de coma (el separador predeterminado es el tabulador).</span><span class="sxs-lookup"><span data-stu-id="a0cd7-190">In this case, you provide the path for your `Test` and `Train` files and indicate both the text file header (so it can use the column names properly) and the comma character data separator (the default separator is a tab).</span></span>

<span data-ttu-id="a0cd7-191">Agregue lo que se indica a continuación como las dos siguientes líneas de código en el método `Main()` para llamar al método `LoadData()` y devolver los datos `Train` y `Test`:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-191">Add the following as the next two lines of code in the `Main()` method to call your `LoadData()` method and return the `Train` and `Test` data:</span></span>

[!code-csharp[LoadDataMain](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#LoadDataMain "Add LoadData method to Main")]

## <a name="build-and-train-your-model"></a><span data-ttu-id="a0cd7-192">Compilación y entrenamiento del modelo</span><span class="sxs-lookup"><span data-stu-id="a0cd7-192">Build and train your model</span></span>

<span data-ttu-id="a0cd7-193">En ML.NET hay tres conceptos principales: [Data](../resources/glossary.md#data) (datos), [Transformers](../resources/glossary.md#transformer) (transformadores) y [Estimators](../resources/glossary.md#estimator) (estimadores).</span><span class="sxs-lookup"><span data-stu-id="a0cd7-193">There are three major concepts in ML.NET: [Data](../resources/glossary.md#data), [Transformers](../resources/glossary.md#transformer), and [Estimators](../resources/glossary.md#estimator).</span></span>

<span data-ttu-id="a0cd7-194">Los algoritmos de entrenamiento de Machine Learning requieren datos en un formato determinado.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-194">Machine learning training algorithms require data in a certain format.</span></span> <span data-ttu-id="a0cd7-195">Los `Transformers` se usan para transformar datos tabulares a un formato compatible.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-195">`Transformers` are used to transform tabular data to a compatible format.</span></span>

![imagen de transformador](./media/movie-recommendation/transformer.png)

<span data-ttu-id="a0cd7-197">Para crear `Transformers` en ML.NET, debe crear `Estimators`.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-197">You create `Transformers` in ML.NET by creating `Estimators`.</span></span> <span data-ttu-id="a0cd7-198">Los `Estimators` toman datos y devuelven `Transformers`.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-198">`Estimators` take in data and return `Transformers`.</span></span>

![imagen de estimador](./media/movie-recommendation/estimator.png)

<span data-ttu-id="a0cd7-200">El algoritmo de entrenamiento de recomendación que usará para entrenar el modelo es un ejemplo de un `Estimator`.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-200">The recommendation training algorithm you will use for training your model is an example of an `Estimator`.</span></span>

<span data-ttu-id="a0cd7-201">Compile un `Estimator` con los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-201">Build an `Estimator` with the following steps:</span></span>

<span data-ttu-id="a0cd7-202">Cree el método `BuildAndTrainModel()`, justo después del método `LoadData()`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-202">Create the `BuildAndTrainModel()` method, just after the `LoadData()` method, using the following code:</span></span>

```csharp
public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView trainingDataView)
{

}
```

> [!NOTE]
> <span data-ttu-id="a0cd7-203">Este método generará un error hasta que agregue una instrucción return en los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-203">This method will give you an error until you add a return statement in the following steps.</span></span>

<span data-ttu-id="a0cd7-204">Defina las transformaciones de datos mediante la adición del código siguiente a `BuildAndTrainModel()`:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-204">Define the data transformations by adding the following code to `BuildAndTrainModel()`:</span></span>

[!code-csharp[DataTransformations](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#DataTransformations "Define data transformations")]

<span data-ttu-id="a0cd7-205">Puesto que `userId` y `movieId` representan usuarios y títulos de películas, en lugar de valores reales, debe usar el método [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) para transformar cada `userId` y `movieId` en una columna `Feature` de tipo de clave numérica (un formato que aceptan los algoritmos de recomendación) y agregarlos como nuevas columnas del conjunto de datos:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-205">Since `userId` and `movieId` represent users and movie titles, not real values, you use the [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) method to transform each `userId` and each `movieId` into a numeric key type `Feature` column (a format accepted by recommendation algorithms) and add them as new dataset columns:</span></span>

| <span data-ttu-id="a0cd7-206">userId</span><span class="sxs-lookup"><span data-stu-id="a0cd7-206">userId</span></span> | <span data-ttu-id="a0cd7-207">movieId</span><span class="sxs-lookup"><span data-stu-id="a0cd7-207">movieId</span></span> | <span data-ttu-id="a0cd7-208">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="a0cd7-208">Label</span></span> | <span data-ttu-id="a0cd7-209">userIdEncoded</span><span class="sxs-lookup"><span data-stu-id="a0cd7-209">userIdEncoded</span></span> | <span data-ttu-id="a0cd7-210">movieIdEncoded</span><span class="sxs-lookup"><span data-stu-id="a0cd7-210">movieIdEncoded</span></span> |
| ------------- |:-------------:| -----:|-----:|-----:|
| <span data-ttu-id="a0cd7-211">1</span><span class="sxs-lookup"><span data-stu-id="a0cd7-211">1</span></span> | <span data-ttu-id="a0cd7-212">1</span><span class="sxs-lookup"><span data-stu-id="a0cd7-212">1</span></span> | <span data-ttu-id="a0cd7-213">4</span><span class="sxs-lookup"><span data-stu-id="a0cd7-213">4</span></span> | <span data-ttu-id="a0cd7-214">userKey1</span><span class="sxs-lookup"><span data-stu-id="a0cd7-214">userKey1</span></span> | <span data-ttu-id="a0cd7-215">movieKey1</span><span class="sxs-lookup"><span data-stu-id="a0cd7-215">movieKey1</span></span> |
| <span data-ttu-id="a0cd7-216">1</span><span class="sxs-lookup"><span data-stu-id="a0cd7-216">1</span></span> | <span data-ttu-id="a0cd7-217">3</span><span class="sxs-lookup"><span data-stu-id="a0cd7-217">3</span></span> | <span data-ttu-id="a0cd7-218">4</span><span class="sxs-lookup"><span data-stu-id="a0cd7-218">4</span></span> | <span data-ttu-id="a0cd7-219">userKey1</span><span class="sxs-lookup"><span data-stu-id="a0cd7-219">userKey1</span></span> | <span data-ttu-id="a0cd7-220">movieKey2</span><span class="sxs-lookup"><span data-stu-id="a0cd7-220">movieKey2</span></span> |
| <span data-ttu-id="a0cd7-221">1</span><span class="sxs-lookup"><span data-stu-id="a0cd7-221">1</span></span> | <span data-ttu-id="a0cd7-222">6</span><span class="sxs-lookup"><span data-stu-id="a0cd7-222">6</span></span> | <span data-ttu-id="a0cd7-223">4</span><span class="sxs-lookup"><span data-stu-id="a0cd7-223">4</span></span> | <span data-ttu-id="a0cd7-224">userKey1</span><span class="sxs-lookup"><span data-stu-id="a0cd7-224">userKey1</span></span> | <span data-ttu-id="a0cd7-225">movieKey3</span><span class="sxs-lookup"><span data-stu-id="a0cd7-225">movieKey3</span></span> |

<span data-ttu-id="a0cd7-226">Elija el algoritmo de Machine Learning y anéxelo a las definiciones de transformación de datos. Para ello, agregue lo que se indica a continuación como la siguiente línea de código en `BuildAndTrainModel()`:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-226">Choose the machine learning algorithm and append it to the data transformation definitions by adding the following as the next line of code in `BuildAndTrainModel()`:</span></span>

[!code-csharp[AddAlgorithm](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#AddAlgorithm "Add the training algorithm with options")]

<span data-ttu-id="a0cd7-227">[MatrixFactorizationTrainer](xref:Microsoft.ML.RecommendationCatalog.RecommendationTrainers.MatrixFactorization%28Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options%29) es el algoritmo de entrenamiento de recomendación.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-227">The [MatrixFactorizationTrainer](xref:Microsoft.ML.RecommendationCatalog.RecommendationTrainers.MatrixFactorization%28Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options%29) is your recommendation training algorithm.</span></span>  <span data-ttu-id="a0cd7-228">La [factorización matricial](https://en.wikipedia.org/wiki/Matrix_factorization_(recommender_systems)) es una manera común de enfocar la recomendación cuando se dispone de datos que muestran cómo los usuarios clasificaron anteriormente los productos, que es el caso de los conjuntos de datos de este tutorial.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-228">[Matrix Factorization](https://en.wikipedia.org/wiki/Matrix_factorization_(recommender_systems)) is a common approach to recommendation when you have data on how users have rated products in the past, which is the case for the datasets in this tutorial.</span></span> <span data-ttu-id="a0cd7-229">Existen otros algoritmos de recomendación para cuando se dispone de datos diferentes (vea más adelante la sección [Otros algoritmos de recomendación](#other-recommendation-algorithms) para obtener más información).</span><span class="sxs-lookup"><span data-stu-id="a0cd7-229">There are other recommendation algorithms for when you have different data available (see the [Other recommendation algorithms](#other-recommendation-algorithms) section below to learn more).</span></span>

<span data-ttu-id="a0cd7-230">En este caso, el algoritmo `Matrix Factorization` usa un método denominado "filtrado de colaboración", que presupone que si el Usuario 1 tiene la misma opinión que el Usuario 2 en un tema determinado, lo más probable es que el Usuario 1 piense lo mismo que el Usuario 2 sobre otro tema.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-230">In this case, the `Matrix Factorization` algorithm uses a method called "collaborative filtering", which assumes that if User 1 has the same opinion as User 2 on a certain issue, then User 1 is more likely to feel the same way as User 2 about a different issue.</span></span>

<span data-ttu-id="a0cd7-231">Por ejemplo, si el Usuario 1 y el Usuario 2 clasifican las películas de forma similar, lo más probable es que el Usuario 2 disfrute de una película que el Usuario 1 ha visto y ha clasificado con una puntuación alta:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-231">For instance, if User 1 and User 2 rate movies similarly, then User 2 is more likely to enjoy a movie that User 1 has watched and rated highly:</span></span>

| | `Incredibles 2 (2018)` | `The Avengers (2012)` | `Guardians of the Galaxy (2014)` |
| -------------:|-------------:| -----:|-----:|
| <span data-ttu-id="a0cd7-232">Usuario 1</span><span class="sxs-lookup"><span data-stu-id="a0cd7-232">User 1</span></span> | <span data-ttu-id="a0cd7-233">Ha visto la película y le ha gustado</span><span class="sxs-lookup"><span data-stu-id="a0cd7-233">Watched and liked movie</span></span> | <span data-ttu-id="a0cd7-234">Ha visto la película y le ha gustado</span><span class="sxs-lookup"><span data-stu-id="a0cd7-234">Watched and liked movie</span></span> | <span data-ttu-id="a0cd7-235">Ha visto la película y le ha gustado</span><span class="sxs-lookup"><span data-stu-id="a0cd7-235">Watched and liked movie</span></span> |
| <span data-ttu-id="a0cd7-236">Usuario 2</span><span class="sxs-lookup"><span data-stu-id="a0cd7-236">User 2</span></span> | <span data-ttu-id="a0cd7-237">Ha visto la película y le ha gustado</span><span class="sxs-lookup"><span data-stu-id="a0cd7-237">Watched and liked movie</span></span> | <span data-ttu-id="a0cd7-238">Ha visto la película y le ha gustado</span><span class="sxs-lookup"><span data-stu-id="a0cd7-238">Watched and liked movie</span></span> | <span data-ttu-id="a0cd7-239">No ha visto la película. RECOMENDARLA</span><span class="sxs-lookup"><span data-stu-id="a0cd7-239">Has not watched -- RECOMMEND movie</span></span> |

<span data-ttu-id="a0cd7-240">El instructor `Matrix Factorization` tiene varias [opciones](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options), sobre las que puede informarse más adelante en la sección [Hiperparámetros de algoritmo](#algorithm-hyperparameters).</span><span class="sxs-lookup"><span data-stu-id="a0cd7-240">The `Matrix Factorization` trainer has several [Options](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options), which you can read more about in the [Algorithm hyperparameters](#algorithm-hyperparameters) section below.</span></span>

<span data-ttu-id="a0cd7-241">Ajuste el modelo a los datos `Train` y devuelva el modelo entrenado. Para ello, agregue lo que se indica a continuación como la siguiente línea de código en el método `BuildAndTrainModel()`:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-241">Fit the model to the `Train` data and return the trained model by adding the following as the next line of code in the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[FitModel](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#FitModel "Call the Fit method and return back the trained model")]

<span data-ttu-id="a0cd7-242">El método [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) entrena el modelo con el conjunto de datos de entrenamiento proporcionado.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-242">The [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) method trains your model with the provided training dataset.</span></span> <span data-ttu-id="a0cd7-243">Técnicamente, ejecuta las definiciones de `Estimator`, para lo que transforma los datos y aplica el entrenamiento, y devuelve el modelo entrenado, que es un `Transformer`.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-243">Technically, it executes the `Estimator` definitions by transforming the data and applying the training, and it returns back the trained model, which is a `Transformer`.</span></span>

<span data-ttu-id="a0cd7-244">Agregue lo que se indica a continuación como la siguiente líneas de código en el método `Main()` para llamar al método `BuildAndTrainModel()` y devolver el modelo entrenado:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-244">Add the following as the next line of code in the `Main()` method to call your `BuildAndTrainModel()` method and return the trained model:</span></span>

[!code-csharp[BuildTrainModelMain](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#BuildTrainModelMain "Add BuildAndTrainModel method in Main")]

## <a name="evaluate-your-model"></a><span data-ttu-id="a0cd7-245">Evaluación del modelo</span><span class="sxs-lookup"><span data-stu-id="a0cd7-245">Evaluate your model</span></span>

<span data-ttu-id="a0cd7-246">Una vez que haya entrenado el modelo, use los datos de prueba para evaluar el rendimiento del modelo.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-246">Once you have trained your model, use your test data to evaluate how your model is performing.</span></span>

<span data-ttu-id="a0cd7-247">Cree el método `EvaluateModel()`, justo después del método `BuildAndTrainModel()`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-247">Create the `EvaluateModel()` method, just after the `BuildAndTrainModel()` method, using the following code:</span></span>

```csharp
public static void EvaluateModel(MLContext mlContext, IDataView testDataView, ITransformer model)
{

}
```

<span data-ttu-id="a0cd7-248">Transforme los datos `Test` mediante la adición del código siguiente a `EvaluateModel()`: [!code-csharp[Transform](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#Transform "Transform the test data")]</span><span class="sxs-lookup"><span data-stu-id="a0cd7-248">Transform the `Test` data by adding the following code to `EvaluateModel()`: [!code-csharp[Transform](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#Transform "Transform the test data")]</span></span>

<span data-ttu-id="a0cd7-249">El método [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) realiza predicciones para varias filas de entrada proporcionadas de un conjunto de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-249">The [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method makes predictions for multiple provided input rows of a test dataset.</span></span>

<span data-ttu-id="a0cd7-250">Para evaluar el modelo, agregue lo que se indica a continuación como la siguiente línea de código en el método `EvaluateModel()`:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-250">Evaluate the model by adding the following as the next line of code in the `EvaluateModel()` method:</span></span>

[!code-csharp[Evaluate](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#Evaluate "Evaluate the model using predictions from the test data")]

<span data-ttu-id="a0cd7-251">Una vez que se ha establecido la predicción, el método [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) valora el modelo, que compara los valores predichos con las `Labels` reales del conjunto de datos de prueba y devuelve métricas sobre el rendimiento del modelo.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-251">Once you have the prediction set, the [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) method assesses the model, which compares the predicted values with the actual `Labels` in the test dataset and returns metrics on how the model is performing.</span></span>

<span data-ttu-id="a0cd7-252">Imprima las métricas de evaluación en la consola. Para ello, agregue lo que se indica a continuación como la siguiente línea de código en el método `EvaluateModel()`:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-252">Print your evaluation metrics to the console by adding the following as the next line of code in the `EvaluateModel()` method:</span></span>

[!code-csharp[PrintMetrics](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#PrintMetrics "Print the evaluation metrics")]

<span data-ttu-id="a0cd7-253">Agregue lo que se indica a continuación como la siguiente línea de código en el método `Main()` para llamar al método `EvaluateModel()`:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-253">Add the following as the next line of code in the `Main()` method to call your `EvaluateModel()` method:</span></span>

[!code-csharp[EvaluateModelMain](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#EvaluateModelMain "Add EvaluateModel method in Main")]

<span data-ttu-id="a0cd7-254">Por el momento, la salida debe ser similar a la del texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-254">The output so far should look similar to the following text:</span></span>

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

<span data-ttu-id="a0cd7-255">En esta salida, hay 20 iteraciones.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-255">In this output, there are 20 iterations.</span></span> <span data-ttu-id="a0cd7-256">En cada iteración, la medida de error disminuye y converge cada vez más hacia 0.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-256">In each iteration, the measure of error decreases and converges closer and closer to 0.</span></span>

<span data-ttu-id="a0cd7-257">El valor `root of mean squared error` (RMS o RMSE) se usa para medir las diferencias entre los valores previstos por un modelo y los valores observados en un conjunto de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-257">The `root of mean squared error` (RMS or RMSE) is used to measure the differences between the model predicted values and the test dataset observed values.</span></span> <span data-ttu-id="a0cd7-258">Técnicamente, es la raíz cuadrada de la media de los cuadrados de los errores.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-258">Technically it's the square root of the average of the squares of the errors.</span></span> <span data-ttu-id="a0cd7-259">Cuanto menor sea su valor, mejor será el modelo.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-259">The lower it is, the better the model is.</span></span>

<span data-ttu-id="a0cd7-260">`R Squared` indica en qué grado los datos se ajustan a un modelo.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-260">`R Squared` indicates how well data fits a model.</span></span> <span data-ttu-id="a0cd7-261">Va de 0 a 1.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-261">Ranges from 0 to 1.</span></span> <span data-ttu-id="a0cd7-262">Un valor de 0 significa que los datos son aleatorios o no pueden ajustarse al modelo.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-262">A value of 0 means that the data is random or otherwise can't be fit to the model.</span></span> <span data-ttu-id="a0cd7-263">Un valor de 1 significa que el modelo coincide exactamente con los datos.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-263">A value of 1 means that the model exactly matches the data.</span></span> <span data-ttu-id="a0cd7-264">Le interesa que la puntuación de `R Squared` esté lo más cerca posible de 1.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-264">You want your `R Squared` score to be as close to 1 as possible.</span></span>

<span data-ttu-id="a0cd7-265">La creación de modelos correctos es un proceso iterativo.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-265">Building successful models is an iterative process.</span></span> <span data-ttu-id="a0cd7-266">Este modelo tiene una calidad inicial más baja, ya que el tutorial utiliza pequeños conjuntos de datos para proporcionar un entrenamiento rápido del modelo.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-266">This model has initial lower quality as the tutorial uses small datasets to provide quick model training.</span></span> <span data-ttu-id="a0cd7-267">Si no está satisfecho con la calidad del modelo, puede intentar mejorarlo proporcionando conjuntos de datos de entrenamiento más grandes o eligiendo algoritmos de entrenamiento distintos con diferentes hiperparámetros para cada algoritmo.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-267">If you aren't satisfied with the model quality, you can try to improve it by providing larger training datasets or by choosing different training algorithms with different hyper-parameters for each algorithm.</span></span> <span data-ttu-id="a0cd7-268">Para más información, revise la sección [Mejora del modelo](#improve-your-model) a continuación.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-268">For more information, check out the [Improve your model](#improve-your-model) section below.</span></span>

## <a name="use-your-model"></a><span data-ttu-id="a0cd7-269">Uso del modelo</span><span class="sxs-lookup"><span data-stu-id="a0cd7-269">Use your model</span></span>

<span data-ttu-id="a0cd7-270">Ahora puede usar el modelo entrenado para realizar predicciones sobre datos nuevos.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-270">Now you can use your trained model to make predictions on new data.</span></span>

<span data-ttu-id="a0cd7-271">Cree el método `UseModelForSinglePrediction()`, justo después del método `EvaluateModel()`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-271">Create the `UseModelForSinglePrediction()` method, just after the `EvaluateModel()` method, using the following code:</span></span>

```csharp
public static void UseModelForSinglePrediction(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="a0cd7-272">Use `PredictionEngine` para predecir la clasificación. Para ello, agregue el código siguiente a `UseModelForSinglePrediction()`:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-272">Use the `PredictionEngine` to predict the rating by adding the following code to `UseModelForSinglePrediction()`:</span></span>

[!code-csharp[PredictionEngine](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#PredictionEngine "Create Prediction Engine")]

<span data-ttu-id="a0cd7-273">La [clase PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) es una API de conveniencia, que permite pasar una instancia única de datos y, después, realizar una predicción en esta instancia única de datos.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-273">The [PredictionEngine class](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to pass a single instance of data and then perform a prediction on this single instance of data.</span></span>

<span data-ttu-id="a0cd7-274">Cree una instancia de `MovieRating` denominada `testInput` y pásela al motor de predicción. Para ello, agregue lo que se indica a continuación como las siguientes líneas de código en el método `UseModelForSinglePrediction()`:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-274">Create an instance of `MovieRating` called `testInput` and pass it to the Prediction Engine by adding the following as the next lines of code in the `UseModelForSinglePrediction()` method:</span></span>

[!code-csharp[MakeSinglePrediction](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#MakeSinglePrediction "Make a single prediction with the Prediction Engine")]

<span data-ttu-id="a0cd7-275">La función [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) realiza una predicción en una sola columna de datos.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-275">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single column of data.</span></span>

<span data-ttu-id="a0cd7-276">Después, puede usar `Score`, o la clasificación predicha, para determinar si quiere recomendar la película con el movieId 10 al usuario 6.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-276">You can then use the `Score`, or the predicted rating, to determine whether you want to recommend the movie with movieId 10 to user 6.</span></span> <span data-ttu-id="a0cd7-277">Cuanto más alto sea `Score`, más probable será que a un usuario le guste una película concreta.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-277">The higher the `Score`, the higher the likelihood of a user liking a particular movie.</span></span> <span data-ttu-id="a0cd7-278">En este caso, supongamos que recomienda películas con una clasificación predicha superior a 3,5.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-278">In this case, let’s say that you recommend movies with a predicted rating of > 3.5.</span></span>

<span data-ttu-id="a0cd7-279">Para imprimir los resultados, agregue lo que se indica a continuación como las siguientes líneas de código en el método `UseModelForSinglePrediction()`:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-279">To print the results, add the following as the next lines of code in the `UseModelForSinglePrediction()` method:</span></span>

[!code-csharp[PrintResults](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#PrintResults "Print the recommendation prediction results")]

<span data-ttu-id="a0cd7-280">Agregue lo que se indica a continuación como la siguiente línea de código en el método `Main()` para llamar al método `UseModelForSinglePrediction()`:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-280">Add the following as the next line of code in the `Main()` method to call your `UseModelForSinglePrediction()` method:</span></span>

[!code-csharp[UseModelMain](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#UseModelMain "Add UseModelForSinglePrediction method in Main")]

<span data-ttu-id="a0cd7-281">La salida de este método debe ser similar a la del texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-281">The output of this method should look similar to the following text:</span></span>

```console
=============== Making a prediction ===============
Movie 10 is recommended for user 6
```

### <a name="save-your-model"></a><span data-ttu-id="a0cd7-282">Guardado del modelo</span><span class="sxs-lookup"><span data-stu-id="a0cd7-282">Save your model</span></span>

<span data-ttu-id="a0cd7-283">Para usar el modelo con el objeto de realizar predicciones en aplicaciones de usuario final, primero debe guardarlo.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-283">To use your model to make predictions in end-user applications, you must first save the model.</span></span>

<span data-ttu-id="a0cd7-284">Cree el método `SaveModel()`, justo después del método `UseModelForSinglePrediction()`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-284">Create the `SaveModel()` method, just after the `UseModelForSinglePrediction()` method, using the following code:</span></span>

```csharp
public static void SaveModel(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="a0cd7-285">Para guardar el modelo entrenado, agregue el código siguiente en el método `SaveModel()`:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-285">Save your trained model by adding the following code in the `SaveModel()` method:</span></span>

[!code-csharp[SaveModel](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#SaveModel "Save the model to a zip file")]

<span data-ttu-id="a0cd7-286">Este método guarda el modelo entrenado en un archivo .zip (en la carpeta "Datos"), que puede usarse después en otras aplicaciones .NET para realizar predicciones.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-286">This method saves your trained model to a .zip file (in the "Data" folder), which can then be used in other .NET applications to make predictions.</span></span>

<span data-ttu-id="a0cd7-287">Agregue lo que se indica a continuación como la siguiente línea de código en el método `Main()` para llamar al método `SaveModel()`:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-287">Add the following as the next line of code in the `Main()` method to call your `SaveModel()` method:</span></span>

[!code-csharp[SaveModelMain](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#SaveModelMain "Create SaveModel method in Main")]

### <a name="use-your-saved-model"></a><span data-ttu-id="a0cd7-288">Uso del modelo guardado</span><span class="sxs-lookup"><span data-stu-id="a0cd7-288">Use your saved model</span></span>

<span data-ttu-id="a0cd7-289">Una vez que haya guardado el modelo entrenado, puede consumirlo en diversos entornos (vea la ["Guía de procedimientos"](../how-to-guides/consuming-model-ml-net.md) para saber cómo poner en marcha un modelo de Machine Learning entrenado en aplicaciones).</span><span class="sxs-lookup"><span data-stu-id="a0cd7-289">Once you have saved your trained model, you can consume the model in different environments (see the ["How-to guide"](../how-to-guides/consuming-model-ml-net.md) to learn how to operationalize a trained machine learning model in apps).</span></span>

## <a name="results"></a><span data-ttu-id="a0cd7-290">Resultados</span><span class="sxs-lookup"><span data-stu-id="a0cd7-290">Results</span></span>

<span data-ttu-id="a0cd7-291">Después de seguir los pasos anteriores, ejecute la aplicación de consola (CTRL + F5).</span><span class="sxs-lookup"><span data-stu-id="a0cd7-291">After following the steps above, run your console app (Ctrl + F5).</span></span> <span data-ttu-id="a0cd7-292">Los resultados de la predicción anterior deben ser similares a lo que se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-292">Your results from the single prediction above should be similar to the following.</span></span> <span data-ttu-id="a0cd7-293">Es posible que vea advertencias o mensajes de procesamiento, si bien se han quitado de los resultados siguientes para mayor claridad.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-293">You may see warnings or processing messages, but these messages have been removed from the following results for clarity.</span></span>

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

<span data-ttu-id="a0cd7-294">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="a0cd7-294">Congratulations!</span></span> <span data-ttu-id="a0cd7-295">Ha compilado correctamente un modelo de Machine Learning para la recomendación de películas.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-295">You've now successfully built a machine learning model for recommending movies.</span></span> <span data-ttu-id="a0cd7-296">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/MovieRecommendation).</span><span class="sxs-lookup"><span data-stu-id="a0cd7-296">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/MovieRecommendation) repository.</span></span>

## <a name="improve-your-model"></a><span data-ttu-id="a0cd7-297">Mejora del código</span><span class="sxs-lookup"><span data-stu-id="a0cd7-297">Improve your model</span></span>

<span data-ttu-id="a0cd7-298">Hay varias maneras de mejorar el rendimiento del modelo para obtener predicciones más precisas.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-298">There are several ways that you can improve the performance of your model so that you can get more accurate predictions.</span></span>

### <a name="data"></a><span data-ttu-id="a0cd7-299">Datos</span><span class="sxs-lookup"><span data-stu-id="a0cd7-299">Data</span></span>

<span data-ttu-id="a0cd7-300">El hecho de agregar más datos de entrenamiento con suficientes ejemplos para cada usuario e identificador de película puede ayudar a mejorar la calidad del modelo de recomendación.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-300">Adding more training data that has enough samples for each user and movie id can help improve the quality of the recommendation model.</span></span>

<span data-ttu-id="a0cd7-301">La [validación cruzada](../how-to-guides/train-cross-validation-ml-net.md) es una técnica para evaluar modelos que divide aleatoriamente los datos en subconjuntos (en lugar de extraer datos de prueba del conjunto de datos, como ha hecho en este tutorial) y toma algunos grupos como datos de entrenamiento y otros como datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-301">[Cross validation](../how-to-guides/train-cross-validation-ml-net.md) is a technique for evaluating models that randomly splits up data into subsets (instead of extracting out test data from the dataset like you did in this tutorial) and takes some of the groups as train data and some of the groups as test data.</span></span> <span data-ttu-id="a0cd7-302">Este método supera en lo que respecta a la calidad del modelo la división en entrenamiento/prueba.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-302">This method outperforms making a train-test split in terms of model quality.</span></span>

### <a name="features"></a><span data-ttu-id="a0cd7-303">Características</span><span class="sxs-lookup"><span data-stu-id="a0cd7-303">Features</span></span>

<span data-ttu-id="a0cd7-304">En este tutorial, solo ha usado las tres `Features` (`user id`, `movie id` y `rating`) que proporciona el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-304">In this tutorial, you only use the three `Features` (`user id`, `movie id`, and `rating`) that are provided by the dataset.</span></span>

<span data-ttu-id="a0cd7-305">Aunque es un buen comienzo, tal vez le interese agregar otros atributos o `Features` (por ejemplo, edad, sexo, ubicación geográfica, etc.) si se incluyen en el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-305">While this is a good start, in reality you might want to add other attributes or `Features` (for example, age, gender, geo-location, etc.) if they are included in the dataset.</span></span> <span data-ttu-id="a0cd7-306">El hecho de agregar `Features` más pertinentes puede ayudar a mejorar el rendimiento del modelo de recomendación.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-306">Adding more relevant `Features` can help improve the performance of your recommendation model.</span></span>

<span data-ttu-id="a0cd7-307">Si no está seguro de qué `Features` pueden ser más pertinentes para la tarea de Machine Learning, puede usar el Cálculo de la contribución de las características (FCC) y la [importancia de la permutación de las características](../how-to-guides/determine-global-feature-importance-in-model.md), que proporciona ML.NET para descubrir las `Features` más influyentes.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-307">If you are unsure about which `Features` might be the most relevant for your machine learning task, you can also make use of Feature Contribution Calculation (FCC) and [Feature Permutation Importance](../how-to-guides/determine-global-feature-importance-in-model.md), which ML.NET provides to discover the most influential `Features`.</span></span>

### <a name="algorithm-hyperparameters"></a><span data-ttu-id="a0cd7-308">Hiperparámetros de algoritmo</span><span class="sxs-lookup"><span data-stu-id="a0cd7-308">Algorithm hyperparameters</span></span>

<span data-ttu-id="a0cd7-309">Aunque ML.NET proporciona algoritmos de entrenamiento predeterminados de calidad, puede ajustar aún más el rendimiento si cambia los [hiperparámetros](../resources/glossary.md#hyperparameter) del algoritmo.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-309">While ML.NET provides good default training algorithms, you can further fine-tune performance by changing the algorithm's [hyperparameters](../resources/glossary.md#hyperparameter).</span></span>

<span data-ttu-id="a0cd7-310">Para `Matrix Factorization`, puede experimentar con hiperparámetros como [NumberOfIterations](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.NumberOfIterations) y [ApproximationRank](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.ApproximationRank) para ver si así obtiene mejores resultados.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-310">For `Matrix Factorization`, you can experiment with hyperparameters such as [NumberOfIterations](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.NumberOfIterations) and [ApproximationRank](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.ApproximationRank) to see if that gives you better results.</span></span>

<span data-ttu-id="a0cd7-311">Por ejemplo, en este tutorial, las opciones de algoritmo son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-311">For instance, in this tutorial the algorithm options are:</span></span>

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

### <a name="other-recommendation-algorithms"></a><span data-ttu-id="a0cd7-312">Otros algoritmos de recomendación</span><span class="sxs-lookup"><span data-stu-id="a0cd7-312">Other Recommendation Algorithms</span></span>

<span data-ttu-id="a0cd7-313">El algoritmo de factorización matricial con filtrado de colaboración es solo un enfoque para realizar recomendaciones de películas.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-313">The matrix factorization algorithm with collaborative filtering is only one approach for performing movie recommendations.</span></span> <span data-ttu-id="a0cd7-314">En muchos casos, es posible que no tenga a su disposición los datos de las clasificaciones y que solo cuente con el historial de películas de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-314">In many cases, you may not have the ratings data available and only have movie history available from users.</span></span> <span data-ttu-id="a0cd7-315">En otros casos, podría disponer de más datos que la clasificación del usuario.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-315">In other cases, you may have more than just the user’s rating data.</span></span>

| <span data-ttu-id="a0cd7-316">Algoritmo</span><span class="sxs-lookup"><span data-stu-id="a0cd7-316">Algorithm</span></span>       | <span data-ttu-id="a0cd7-317">Escenario</span><span class="sxs-lookup"><span data-stu-id="a0cd7-317">Scenario</span></span>           | <span data-ttu-id="a0cd7-318">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a0cd7-318">Sample</span></span>  |
| ------------- |:-------------:| -----:|
| <span data-ttu-id="a0cd7-319">Factorización matricial de una clase</span><span class="sxs-lookup"><span data-stu-id="a0cd7-319">One Class Matrix Factorization</span></span> | <span data-ttu-id="a0cd7-320">Úselo cuando solo tenga los valores userId y movieId.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-320">Use this when you only have userId and movieId.</span></span> <span data-ttu-id="a0cd7-321">Este tipo de recomendación se basa en el escenario de compra conjunta, es decir, en los productos que se suelen comprar juntos. Esto significa que se recomendará a los clientes un conjunto de productos en función de su propio historial de pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-321">This style of recommendation is based upon the co-purchase scenario, or products frequently bought together, which means it will recommend to customers a set of products based upon their own purchase order history.</span></span> | [<span data-ttu-id="a0cd7-322">>Pruébelo</span><span class="sxs-lookup"><span data-stu-id="a0cd7-322">>Try it out</span></span>](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/MatrixFactorization_ProductRecommendation) |
| <span data-ttu-id="a0cd7-323">Máquinas de factorización con reconocimiento de campo</span><span class="sxs-lookup"><span data-stu-id="a0cd7-323">Field Aware Factorization Machines</span></span> | <span data-ttu-id="a0cd7-324">Úselo para realizar recomendaciones cuando disponga de más características que userId, productId y la clasificación (por ejemplo, la descripción o el precio del producto).</span><span class="sxs-lookup"><span data-stu-id="a0cd7-324">Use this to make recommendations when you have more Features beyond userId, productId, and rating (such as product description or product price).</span></span> <span data-ttu-id="a0cd7-325">Este método también usa un enfoque de filtrado de colaboración.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-325">This method also uses a collaborative filtering approach.</span></span> | [<span data-ttu-id="a0cd7-326">>Pruébelo</span><span class="sxs-lookup"><span data-stu-id="a0cd7-326">>Try it out</span></span>](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/end-to-end-apps/Recommendation-MovieRecommender) |

### <a name="new-user-scenario"></a><span data-ttu-id="a0cd7-327">Escenario de nuevo usuario</span><span class="sxs-lookup"><span data-stu-id="a0cd7-327">New user scenario</span></span>

<span data-ttu-id="a0cd7-328">Un problema común en el filtrado de colaboración es el "arranque en frío", que es cuando tiene un nuevo usuario sin ningún dato anterior a partir del cual pueda realizar inferencias.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-328">One common problem in collaborative filtering is the cold start problem, which is when you have a new user with no previous data to draw inferences from.</span></span> <span data-ttu-id="a0cd7-329">Por lo general, para solucionarlo se les pide a los nuevos usuarios que creen un perfil y, por ejemplo, clasifiquen películas que ya han visto.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-329">This problem is often solved by asking new users to create a profile and, for instance, rate movies they have seen in the past.</span></span> <span data-ttu-id="a0cd7-330">Aunque este método supone una relativa carga para el usuario, proporciona algunos datos iniciales para los usuarios nuevos que carecen de historial de clasificaciones.</span><span class="sxs-lookup"><span data-stu-id="a0cd7-330">While this method puts some burden on the user, it provides some starting data for new users with no rating history.</span></span>

## <a name="resources"></a><span data-ttu-id="a0cd7-331">Recursos</span><span class="sxs-lookup"><span data-stu-id="a0cd7-331">Resources</span></span>

<span data-ttu-id="a0cd7-332">Los datos que se han usado en este tutorial se han tomado del [conjunto de datos MovieLens](http://files.grouplens.org/datasets/movielens/).</span><span class="sxs-lookup"><span data-stu-id="a0cd7-332">The data used in this tutorial is derived from [MovieLens Dataset](http://files.grouplens.org/datasets/movielens/).</span></span>

## <a name="next-steps"></a><span data-ttu-id="a0cd7-333">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a0cd7-333">Next steps</span></span>

<span data-ttu-id="a0cd7-334">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="a0cd7-334">In this tutorial, you learned how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="a0cd7-335">Seleccionar un algoritmo de Machine Learning</span><span class="sxs-lookup"><span data-stu-id="a0cd7-335">Select a machine learning algorithm</span></span>
> * <span data-ttu-id="a0cd7-336">Preparar y cargar los datos</span><span class="sxs-lookup"><span data-stu-id="a0cd7-336">Prepare and load your data</span></span>
> * <span data-ttu-id="a0cd7-337">Compilar y entrenar un modelo</span><span class="sxs-lookup"><span data-stu-id="a0cd7-337">Build and train a model</span></span>
> * <span data-ttu-id="a0cd7-338">Evaluar un modelo</span><span class="sxs-lookup"><span data-stu-id="a0cd7-338">Evaluate a model</span></span>
> * <span data-ttu-id="a0cd7-339">Implementar y consumir un modelo</span><span class="sxs-lookup"><span data-stu-id="a0cd7-339">Deploy and consume a model</span></span>

<span data-ttu-id="a0cd7-340">Siga con el siguiente tutorial para obtener más información</span><span class="sxs-lookup"><span data-stu-id="a0cd7-340">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="a0cd7-341">Análisis de sentimiento</span><span class="sxs-lookup"><span data-stu-id="a0cd7-341">Sentiment Analysis</span></span>](sentiment-analysis.md)
