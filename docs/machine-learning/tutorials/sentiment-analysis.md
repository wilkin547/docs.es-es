---
title: 'Tutorial: Análisis de comentarios del sitio web: clasificación binaria'
description: En este tutorial se muestra cómo crear una aplicación de consola de .NET Core que clasifica las opiniones de los comentarios del sitio web y toma las medidas oportunas. El clasificador binario de opiniones usa C# en Visual Studio.
ms.date: 06/30/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: b193752437c3e84476858bb3b70ba642d8562769
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803253"
---
# <a name="tutorial-analyze-sentiment-of-website-comments-with-binary-classification-in-mlnet"></a><span data-ttu-id="690ca-104">Tutorial: Análisis de opinión de los comentarios del sitio web con clasificación binaria de ML.NET</span><span class="sxs-lookup"><span data-stu-id="690ca-104">Tutorial: Analyze sentiment of website comments with binary classification in ML.NET</span></span>

<span data-ttu-id="690ca-105">En este tutorial se muestra cómo crear una aplicación de consola de .NET Core que clasifica las opiniones de los comentarios del sitio web y toma las medidas oportunas.</span><span class="sxs-lookup"><span data-stu-id="690ca-105">This tutorial shows you how to create a .NET Core console application that classifies sentiment from website comments and takes the appropriate action.</span></span> <span data-ttu-id="690ca-106">El clasificador binario de opiniones utiliza C# en Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="690ca-106">The binary sentiment classifier uses C# in Visual Studio 2017.</span></span>

<span data-ttu-id="690ca-107">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="690ca-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="690ca-108">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="690ca-108">Create a console application</span></span>
> - <span data-ttu-id="690ca-109">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="690ca-109">Prepare data</span></span>
> - <span data-ttu-id="690ca-110">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="690ca-110">Load the data</span></span>
> - <span data-ttu-id="690ca-111">Creación y entrenamiento del modelo</span><span class="sxs-lookup"><span data-stu-id="690ca-111">Build and train the model</span></span>
> - <span data-ttu-id="690ca-112">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="690ca-112">Evaluate the model</span></span>
> - <span data-ttu-id="690ca-113">Uso del modelo para realizar una predicción</span><span class="sxs-lookup"><span data-stu-id="690ca-113">Use the model to make a prediction</span></span>
> - <span data-ttu-id="690ca-114">Ver los resultados</span><span class="sxs-lookup"><span data-stu-id="690ca-114">See the results</span></span>

<span data-ttu-id="690ca-115">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).</span><span class="sxs-lookup"><span data-stu-id="690ca-115">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="690ca-116">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="690ca-116">Prerequisites</span></span>

- <span data-ttu-id="690ca-117">[Visual Studio 2017, versión 15.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada</span><span class="sxs-lookup"><span data-stu-id="690ca-117">[Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the ".NET Core cross-platform development" workload installed</span></span>

- <span data-ttu-id="690ca-118">[Conjunto de datos de frases con etiqueta de opinión de UCI](http://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) (archivo ZIP)</span><span class="sxs-lookup"><span data-stu-id="690ca-118">[UCI Sentiment Labeled Sentences dataset](http://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) (ZIP file)</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="690ca-119">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="690ca-119">Create a console application</span></span>

1. <span data-ttu-id="690ca-120">Cree una **aplicación de consola de .NET Core** denominada "SentimentAnalysis".</span><span class="sxs-lookup"><span data-stu-id="690ca-120">Create a **.NET Core Console Application** called "SentimentAnalysis".</span></span>

2. <span data-ttu-id="690ca-121">Cree un directorio denominado *Datos* en el proyecto para guardar los archivos de conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="690ca-121">Create a directory named *Data* in your project to save your data set files.</span></span>

3. <span data-ttu-id="690ca-122">Instale el **paquete NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="690ca-122">Install the **Microsoft.ML NuGet Package**:</span></span>

    [!INCLUDE [mlnet-current-nuget-version](../../../includes/mlnet-current-nuget-version.md)]

    <span data-ttu-id="690ca-123">En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="690ca-123">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="690ca-124">Elija "nuget.org" como origen del paquete y luego seleccione la pestaña **Examinar**. Busque **Microsoft.ML**, seleccione el paquete que desee y luego, el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="690ca-124">Choose "nuget.org" as the package source, and then select the **Browse** tab. Search for **Microsoft.ML**, select the package you want, and then select the **Install** button.</span></span> <span data-ttu-id="690ca-125">Acepte los términos de licencia del paquete que elija para continuar con la instalación.</span><span class="sxs-lookup"><span data-stu-id="690ca-125">Proceed with the installation by agreeing to the license terms for the package you choose.</span></span>

## <a name="prepare-your-data"></a><span data-ttu-id="690ca-126">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="690ca-126">Prepare your data</span></span>

> [!NOTE]
> <span data-ttu-id="690ca-127">Los conjuntos de datos de este tutorial proceden de "From Group to Individual Labels using Deep Features", Kotzias et.</span><span class="sxs-lookup"><span data-stu-id="690ca-127">The datasets for this tutorial are from the 'From Group to Individual Labels using Deep Features', Kotzias et.</span></span> <span data-ttu-id="690ca-128">al,.</span><span class="sxs-lookup"><span data-stu-id="690ca-128">al,.</span></span> <span data-ttu-id="690ca-129">KDD 2015, and hosted at the UCI Machine Learning Repository - Dua, D. and Karra Taniskidou, E. (2017).</span><span class="sxs-lookup"><span data-stu-id="690ca-129">KDD 2015, and hosted at the UCI Machine Learning Repository - Dua, D. and Karra Taniskidou, E. (2017).</span></span> <span data-ttu-id="690ca-130">UCI Machine Learning Repository [http://archive.ics.uci.edu/ml ].</span><span class="sxs-lookup"><span data-stu-id="690ca-130">UCI Machine Learning Repository [http://archive.ics.uci.edu/ml].</span></span> <span data-ttu-id="690ca-131">Irvine, CA: University of California, School of Information and Computer Science.</span><span class="sxs-lookup"><span data-stu-id="690ca-131">Irvine, CA: University of California, School of Information and Computer Science.</span></span>

1. <span data-ttu-id="690ca-132">Descargue el [archivo ZIP de conjunto de datos de frases con etiqueta de opinión de UCI](http://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) y descomprímalo.</span><span class="sxs-lookup"><span data-stu-id="690ca-132">Download [UCI Sentiment Labeled Sentences dataset ZIP file](http://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip), and unzip.</span></span>

2. <span data-ttu-id="690ca-133">Copie el archivo `yelp_labelled.txt` en el directorio *Datos* que ha creado.</span><span class="sxs-lookup"><span data-stu-id="690ca-133">Copy the `yelp_labelled.txt` file into the *Data* directory you created.</span></span>

3. <span data-ttu-id="690ca-134">En el Explorador de soluciones, haga clic con el botón derecho en el archivo `yelp_labeled.txt` y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="690ca-134">In Solution Explorer, right-click the `yelp_labeled.txt` file and select **Properties**.</span></span> <span data-ttu-id="690ca-135">En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.</span><span class="sxs-lookup"><span data-stu-id="690ca-135">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="690ca-136">Crear clases y definir rutas de acceso</span><span class="sxs-lookup"><span data-stu-id="690ca-136">Create classes and define paths</span></span>

1. <span data-ttu-id="690ca-137">Agregue las siguientes instrucciones `using` adicionales a la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="690ca-137">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

    [!code-csharp[AddUsings](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#AddUsings "Add necessary usings")]

1. <span data-ttu-id="690ca-138">Agregue el código siguiente a la línea por encima del método `Main` para crear un campo que incluya la ruta de acceso del archivo del conjunto de datos descargado recientemente:</span><span class="sxs-lookup"><span data-stu-id="690ca-138">Add the following code to the line right above the `Main` method, to create a field to hold the recently downloaded dataset file path:</span></span>

    [!code-csharp[Declare global variables](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#DeclareGlobalVariables "Declare global variables")]

1. <span data-ttu-id="690ca-139">Luego, cree clases para los datos de entrada y las predicciones.</span><span class="sxs-lookup"><span data-stu-id="690ca-139">Next, create classes for your input data and predictions.</span></span> <span data-ttu-id="690ca-140">Agregue una nueva clase a su proyecto:</span><span class="sxs-lookup"><span data-stu-id="690ca-140">Add a new class to your project:</span></span>

    - <span data-ttu-id="690ca-141">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="690ca-141">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

    - <span data-ttu-id="690ca-142">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="690ca-142">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="690ca-143">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="690ca-143">Then, select the **Add** button.</span></span>

1. <span data-ttu-id="690ca-144">Se abre el archivo *SentimentData.cs* en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="690ca-144">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="690ca-145">Agregue la siguiente instrucción `using` a la parte superior de *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="690ca-145">Add the following `using` statement to the top of *SentimentData.cs*:</span></span>

    [!code-csharp[AddUsings](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/SentimentData.cs#AddUsings "Add necessary usings")]

1. <span data-ttu-id="690ca-146">Quite la definición de clase existente y agregue el código siguiente, que tiene dos clases `SentimentData` y `SentimentPrediction`, al archivo *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="690ca-146">Remove the existing class definition and add the following code, which has two classes `SentimentData` and `SentimentPrediction`, to the *SentimentData.cs* file:</span></span>

    [!code-csharp[DeclareTypes](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/SentimentData.cs#DeclareTypes "Declare data record types")]

### <a name="how-the-data-was-prepared"></a><span data-ttu-id="690ca-147">¿Cómo se han preparado los datos?</span><span class="sxs-lookup"><span data-stu-id="690ca-147">How the data was prepared</span></span>

<span data-ttu-id="690ca-148">La clase de conjunto de datos de entrada, `SentimentData`, tiene un `string` para comentarios del usuario (`SentimentText`) y un valor `bool` (`Sentiment`) de 1 (positivo) o de 0 (negativo) para las opiniones.</span><span class="sxs-lookup"><span data-stu-id="690ca-148">The input dataset class, `SentimentData`, has a `string` for user comments (`SentimentText`) and a `bool` (`Sentiment`) value of either 1 (positive) or 0 (negative) for sentiment.</span></span> <span data-ttu-id="690ca-149">Ambos campos tienen atributos [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) adjuntos a ellos, que describe el orden de archivo de datos de cada campo.</span><span class="sxs-lookup"><span data-stu-id="690ca-149">Both fields have [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) attributes attached to them, which describes the data file order of each field.</span></span>  <span data-ttu-id="690ca-150">Además, la propiedad `Sentiment` tiene un atributo [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A) que lo designa como campo `Label`.</span><span class="sxs-lookup"><span data-stu-id="690ca-150">In addition, the `Sentiment` property has a [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A) attribute to designate it as the `Label` field.</span></span> <span data-ttu-id="690ca-151">El archivo de ejemplo siguiente no tiene una fila de encabezado y se ve así:</span><span class="sxs-lookup"><span data-stu-id="690ca-151">The following example file doesn't have a header row, and looks like this:</span></span>

|<span data-ttu-id="690ca-152">SentimentText</span><span class="sxs-lookup"><span data-stu-id="690ca-152">SentimentText</span></span>                         |<span data-ttu-id="690ca-153">Opinión (etiqueta)</span><span class="sxs-lookup"><span data-stu-id="690ca-153">Sentiment (Label)</span></span> |
|--------------------------------------|----------|
|<span data-ttu-id="690ca-154">La camarera era algo lenta en el servicio.</span><span class="sxs-lookup"><span data-stu-id="690ca-154">Waitress was a little slow in service.</span></span>|    <span data-ttu-id="690ca-155">0</span><span class="sxs-lookup"><span data-stu-id="690ca-155">0</span></span>     |
|<span data-ttu-id="690ca-156">La corteza no es buena.</span><span class="sxs-lookup"><span data-stu-id="690ca-156">Crust is not good.</span></span>                    |    <span data-ttu-id="690ca-157">0</span><span class="sxs-lookup"><span data-stu-id="690ca-157">0</span></span>     |
|<span data-ttu-id="690ca-158">¡Ah! Me encantó el lugar.</span><span class="sxs-lookup"><span data-stu-id="690ca-158">Wow... Loved this place.</span></span>              |    <span data-ttu-id="690ca-159">1</span><span class="sxs-lookup"><span data-stu-id="690ca-159">1</span></span>     |
|<span data-ttu-id="690ca-160">El servicio fue muy rápido.</span><span class="sxs-lookup"><span data-stu-id="690ca-160">Service was very prompt.</span></span>              |    <span data-ttu-id="690ca-161">1</span><span class="sxs-lookup"><span data-stu-id="690ca-161">1</span></span>     |

<span data-ttu-id="690ca-162">`SentimentPrediction` es la clase de predicción que se utiliza tras el entrenamiento del modelo.</span><span class="sxs-lookup"><span data-stu-id="690ca-162">`SentimentPrediction` is the prediction class used after model training.</span></span> <span data-ttu-id="690ca-163">Hereda de `SentimentData` para que la entrada `SentimentText` pueda mostrarse junto con la predicción de salida.</span><span class="sxs-lookup"><span data-stu-id="690ca-163">It inherits from `SentimentData` so that the input `SentimentText` can be displayed along with the output prediction.</span></span> <span data-ttu-id="690ca-164">El booleano `Prediction` es el valor que predice el modelo cuando se proporciona con la nueva entrada `SentimentText`.</span><span class="sxs-lookup"><span data-stu-id="690ca-164">The `Prediction` boolean is the value that the model predicts when supplied with new input `SentimentText`.</span></span>

<span data-ttu-id="690ca-165">La clase de salida `SentimentPrediction` contiene otras dos propiedades calculadas por el modelo: `Score`, el resultado sin formato calculado por el modelo y `Probability`, la puntuación calibrada de la probabilidad de que el texto tenga un sentimiento positivo.</span><span class="sxs-lookup"><span data-stu-id="690ca-165">The output class `SentimentPrediction` contains two other properties calculated by the model: `Score` - the raw score calculated by the model, and `Probability` - the score calibrated to the likelihood of the text having positive sentiment.</span></span>

<span data-ttu-id="690ca-166">Para este tutorial, la propiedad más importante es `Prediction`.</span><span class="sxs-lookup"><span data-stu-id="690ca-166">For this tutorial, the most important property is `Prediction`.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="690ca-167">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="690ca-167">Load the data</span></span>

<span data-ttu-id="690ca-168">Los datos de ML.NET se representan como una [clase IDataView](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="690ca-168">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="690ca-169">`IDataView` es una manera flexible y eficiente de describir datos tabulares (numéricos y de texto).</span><span class="sxs-lookup"><span data-stu-id="690ca-169">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="690ca-170">Los datos se pueden cargar desde un archivo de texto o en tiempo real (por ejemplo, archivos de registro o base de datos SQL) en un objeto `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="690ca-170">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

<span data-ttu-id="690ca-171">La [clase MLContext](xref:Microsoft.ML.MLContext) es un punto de partida para todas las operaciones de ML.NET.</span><span class="sxs-lookup"><span data-stu-id="690ca-171">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations.</span></span> <span data-ttu-id="690ca-172">La inicialización de `mlContext` crea un entorno de ML.NET que se puede compartir entre los objetos del flujo de trabajo de creación de modelos.</span><span class="sxs-lookup"><span data-stu-id="690ca-172">Initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="690ca-173">Como concepto, se parece a `DBContext` en Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="690ca-173">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

<span data-ttu-id="690ca-174">Prepare la aplicación y luego cargue datos:</span><span class="sxs-lookup"><span data-stu-id="690ca-174">You prepare the app, and then load data:</span></span>

1. <span data-ttu-id="690ca-175">Reemplace la línea `Console.WriteLine("Hello World!")` del método `Main` por el siguiente código para declarar e inicializar la variable mlContext:</span><span class="sxs-lookup"><span data-stu-id="690ca-175">Replace the `Console.WriteLine("Hello World!")` line in the `Main` method with the following code to declare and initialize the mlContext variable:</span></span>

    [!code-csharp[CreateMLContext](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CreateMLContext "Create the ML Context")]

2. <span data-ttu-id="690ca-176">Agregue lo siguiente como la siguiente línea de código en el método `Main()`:</span><span class="sxs-lookup"><span data-stu-id="690ca-176">Add the following as the next line of code in the `Main()` method:</span></span>

    [!code-csharp[CallLoadData](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CallLoadData)]

3. <span data-ttu-id="690ca-177">Cree el método `LoadData()`, justo después del método `Main()`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="690ca-177">Create the `LoadData()` method, just after the `Main()` method, using the following code:</span></span>

    ```csharp
    public static TrainTestData LoadData(MLContext mlContext)
    {

    }
    ```

    <span data-ttu-id="690ca-178">El método `LoadData()` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="690ca-178">The `LoadData()` method executes the following tasks:</span></span>

    - <span data-ttu-id="690ca-179">Carga los datos.</span><span class="sxs-lookup"><span data-stu-id="690ca-179">Loads the data.</span></span>
    - <span data-ttu-id="690ca-180">Divide el conjunto de datos cargado en conjuntos de datos de entrenamiento y prueba.</span><span class="sxs-lookup"><span data-stu-id="690ca-180">Splits the loaded dataset into train and test datasets.</span></span>
    - <span data-ttu-id="690ca-181">Devuelve los conjuntos de datos divididos en entrenamiento y prueba.</span><span class="sxs-lookup"><span data-stu-id="690ca-181">Returns the split train and test datasets.</span></span>

4. <span data-ttu-id="690ca-182">Agregue el código siguiente a la primera línea del método `LoadData()`:</span><span class="sxs-lookup"><span data-stu-id="690ca-182">Add the following code as the first line of the `LoadData()` method:</span></span>

    [!code-csharp[LoadData](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#LoadData "loading dataset")]

    <span data-ttu-id="690ca-183">El método [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) define el esquema de datos y lee en el archivo.</span><span class="sxs-lookup"><span data-stu-id="690ca-183">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) method defines the data schema and reads in the file.</span></span> <span data-ttu-id="690ca-184">Toma las variables de ruta de acceso de datos y devuelve `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="690ca-184">It takes in the data path variables and returns an `IDataView`.</span></span>

### <a name="split-the-dataset-for-model-training-and-testing"></a><span data-ttu-id="690ca-185">División del conjunto de datos para el entrenamiento y la prueba del modelo</span><span class="sxs-lookup"><span data-stu-id="690ca-185">Split the dataset for model training and testing</span></span>

<span data-ttu-id="690ca-186">Al preparar un modelo, se utiliza parte del conjunto de datos para entrenarlo y parte del conjunto de datos para probar la precisión del modelo.</span><span class="sxs-lookup"><span data-stu-id="690ca-186">When preparing a model, you use part of the dataset to train it and part of the dataset to test the model's accuracy.</span></span>

1. <span data-ttu-id="690ca-187">Para dividir los datos cargados en los conjuntos de datos necesarios, agregue el código siguiente como la siguiente línea en el método `LoadData()`:</span><span class="sxs-lookup"><span data-stu-id="690ca-187">To split the loaded data into the needed datasets, add the following code as the next line in the `LoadData()` method:</span></span>

    [!code-csharp[SplitData](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#SplitData "Split the Data")]

    <span data-ttu-id="690ca-188">El código anterior usa el método [TrainTestSplit()](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit%2A) para dividir el conjunto de datos cargado en conjuntos de datos de entrenamiento y de prueba, que devuelve en la clase <xref:Microsoft.ML.DataOperationsCatalog.TrainTestData>.</span><span class="sxs-lookup"><span data-stu-id="690ca-188">The previous code uses the [TrainTestSplit()](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit%2A) method to split the loaded dataset into train and test datasets and return them in the <xref:Microsoft.ML.DataOperationsCatalog.TrainTestData> class.</span></span> <span data-ttu-id="690ca-189">Especifique el porcentaje de datos del conjunto de prueba con el parámetro `testFraction`.</span><span class="sxs-lookup"><span data-stu-id="690ca-189">Specify the test set percentage of data with the `testFraction`parameter.</span></span> <span data-ttu-id="690ca-190">El valor predeterminado es 10 %; en este caso se usa 20 % para evaluar más datos.</span><span class="sxs-lookup"><span data-stu-id="690ca-190">The default is 10%, in this case you use 20% to evaluate more data.</span></span>

2. <span data-ttu-id="690ca-191">Devuelva el `splitDataView` al final del método `LoadData()`:</span><span class="sxs-lookup"><span data-stu-id="690ca-191">Return the `splitDataView` at the end of the `LoadData()` method:</span></span>

    [!code-csharp[ReturnSplitData](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#ReturnSplitData)]

## <a name="build-and-train-the-model"></a><span data-ttu-id="690ca-192">Creación y entrenamiento del modelo</span><span class="sxs-lookup"><span data-stu-id="690ca-192">Build and train the model</span></span>

1. <span data-ttu-id="690ca-193">Agregue la siguiente llamada al método `BuildAndTrainModel` como siguiente línea de código del método `Main()`:</span><span class="sxs-lookup"><span data-stu-id="690ca-193">Add the following call to the `BuildAndTrainModel`method as the next line of code in the `Main()` method:</span></span>

    [!code-csharp[CallBuildAndTrainModel](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CallBuildAndTrainModel)]

    <span data-ttu-id="690ca-194">El método `BuildAndTrainModel()` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="690ca-194">The `BuildAndTrainModel()` method executes the following tasks:</span></span>

    - <span data-ttu-id="690ca-195">Extrae y transforma los datos.</span><span class="sxs-lookup"><span data-stu-id="690ca-195">Extracts and transforms the data.</span></span>
    - <span data-ttu-id="690ca-196">Entrena el modelo.</span><span class="sxs-lookup"><span data-stu-id="690ca-196">Trains the model.</span></span>
    - <span data-ttu-id="690ca-197">Predice sentimientos en función de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="690ca-197">Predicts sentiment based on test data.</span></span>
    - <span data-ttu-id="690ca-198">Devuelve el modelo.</span><span class="sxs-lookup"><span data-stu-id="690ca-198">Returns the model.</span></span>

2. <span data-ttu-id="690ca-199">Cree el método `BuildAndTrainModel()`, justo después del método `Main()`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="690ca-199">Create the `BuildAndTrainModel()` method, just after the `Main()` method, using the following code:</span></span>

    ```csharp
    public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView splitTrainSet)
    {

    }
    ```

### <a name="extract-and-transform-the-data"></a><span data-ttu-id="690ca-200">Extraer y transformar los datos</span><span class="sxs-lookup"><span data-stu-id="690ca-200">Extract and transform the data</span></span>

1. <span data-ttu-id="690ca-201">Llame a `FeaturizeText` como siguiente línea de código:</span><span class="sxs-lookup"><span data-stu-id="690ca-201">Call `FeaturizeText` as the next line of code:</span></span>

    [!code-csharp[FeaturizeText](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#FeaturizeText "Featurize the text")]

    <span data-ttu-id="690ca-202">El método `FeaturizeText()` del código anterior convierte la columna de texto (`SentimentText`) en una columna de tipo de clave numérico `Features` que el algoritmo de aprendizaje automático utiliza y agrega como nueva columna de conjunto de datos:</span><span class="sxs-lookup"><span data-stu-id="690ca-202">The `FeaturizeText()` method in the previous code converts the text column (`SentimentText`) into a numeric key type `Features` column used by the machine learning algorithm and adds it as a new dataset column:</span></span>

    |<span data-ttu-id="690ca-203">SentimentText</span><span class="sxs-lookup"><span data-stu-id="690ca-203">SentimentText</span></span>                         |<span data-ttu-id="690ca-204">Opinión</span><span class="sxs-lookup"><span data-stu-id="690ca-204">Sentiment</span></span> |<span data-ttu-id="690ca-205">Características</span><span class="sxs-lookup"><span data-stu-id="690ca-205">Features</span></span>              |
    |--------------------------------------|----------|----------------------|
    |<span data-ttu-id="690ca-206">La camarera era algo lenta en el servicio.</span><span class="sxs-lookup"><span data-stu-id="690ca-206">Waitress was a little slow in service.</span></span>|    <span data-ttu-id="690ca-207">0</span><span class="sxs-lookup"><span data-stu-id="690ca-207">0</span></span>     |<span data-ttu-id="690ca-208">[0,76, 0,65, 0,44, …]</span><span class="sxs-lookup"><span data-stu-id="690ca-208">[0.76, 0.65, 0.44, …]</span></span> |
    |<span data-ttu-id="690ca-209">La corteza no es buena.</span><span class="sxs-lookup"><span data-stu-id="690ca-209">Crust is not good.</span></span>                    |    <span data-ttu-id="690ca-210">0</span><span class="sxs-lookup"><span data-stu-id="690ca-210">0</span></span>     |<span data-ttu-id="690ca-211">[0,98, 0,43, 0,54, …]</span><span class="sxs-lookup"><span data-stu-id="690ca-211">[0.98, 0.43, 0.54, …]</span></span> |
    |<span data-ttu-id="690ca-212">¡Ah! Me encantó el lugar.</span><span class="sxs-lookup"><span data-stu-id="690ca-212">Wow... Loved this place.</span></span>              |    <span data-ttu-id="690ca-213">1</span><span class="sxs-lookup"><span data-stu-id="690ca-213">1</span></span>     |<span data-ttu-id="690ca-214">[0,35, 0,73, 0,46, …]</span><span class="sxs-lookup"><span data-stu-id="690ca-214">[0.35, 0.73, 0.46, …]</span></span> |
    |<span data-ttu-id="690ca-215">El servicio fue muy rápido.</span><span class="sxs-lookup"><span data-stu-id="690ca-215">Service was very prompt.</span></span>              |    <span data-ttu-id="690ca-216">1</span><span class="sxs-lookup"><span data-stu-id="690ca-216">1</span></span>     |<span data-ttu-id="690ca-217">[0,39, 0, 0,75, …]</span><span class="sxs-lookup"><span data-stu-id="690ca-217">[0.39, 0, 0.75, …]</span></span>    |

### <a name="add-a-learning-algorithm"></a><span data-ttu-id="690ca-218">Incorporación de un algoritmo de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="690ca-218">Add a learning algorithm</span></span>

<span data-ttu-id="690ca-219">Esta aplicación usa un algoritmo de clasificación que clasifica elementos o filas de datos.</span><span class="sxs-lookup"><span data-stu-id="690ca-219">This app uses a classification algorithm that categorizes items or rows of data.</span></span> <span data-ttu-id="690ca-220">La aplicación clasifica los comentarios del sitio web como positivos o negativos, así que use la tarea de clasificación binaria.</span><span class="sxs-lookup"><span data-stu-id="690ca-220">The app categorizes website comments as either positive or negative, so use the binary classification task.</span></span>

<span data-ttu-id="690ca-221">Anexe la tarea de aprendizaje automático a las definiciones de transformación de datos agregando lo siguiente como siguiente línea de código en `BuildAndTrainModel()`:</span><span class="sxs-lookup"><span data-stu-id="690ca-221">Append the machine learning task to the data transformation definitions by adding the following as the next line of code in `BuildAndTrainModel()`:</span></span>

[!code-csharp[SdcaLogisticRegressionBinaryTrainer](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#AddTrainer "Add a SdcaLogisticRegressionBinaryTrainer")]

<span data-ttu-id="690ca-222">[SdcaLogisticRegressionBinaryTrainer](xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer) es el algoritmo de entrenamiento de clasificación.</span><span class="sxs-lookup"><span data-stu-id="690ca-222">The [SdcaLogisticRegressionBinaryTrainer](xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer) is your classification training algorithm.</span></span> <span data-ttu-id="690ca-223">Se anexa a `estimator` y acepta `SentimentText` (`Features`) caracterizado y los parámetros de entrada `Label` para aprender de los datos históricos.</span><span class="sxs-lookup"><span data-stu-id="690ca-223">This is appended to the `estimator` and accepts the featurized `SentimentText` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span>

### <a name="train-the-model"></a><span data-ttu-id="690ca-224">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="690ca-224">Train the model</span></span>

<span data-ttu-id="690ca-225">Ajuste el modelo a los datos `splitTrainSet` y devuelva el modelo entrenado. Para ello, agregue lo que se indica a continuación como la siguiente línea de código en el método `BuildAndTrainModel()`:</span><span class="sxs-lookup"><span data-stu-id="690ca-225">Fit the model to the `splitTrainSet` data and return the trained model by adding the following as the next line of code in the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[TrainModel](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#TrainModel "Train the model")]

<span data-ttu-id="690ca-226">El método [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) entrena el modelo al transformar el conjunto de datos y aplicar el aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="690ca-226">The [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) method trains your model by transforming the dataset and applying the training.</span></span>

### <a name="return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="690ca-227">Devolución del modelo entrenado para su uso para la evaluación</span><span class="sxs-lookup"><span data-stu-id="690ca-227">Return the model trained to use for evaluation</span></span>

 <span data-ttu-id="690ca-228">Devuelva el modelo al final del método `BuildAndTrainModel()`:</span><span class="sxs-lookup"><span data-stu-id="690ca-228">Return the model at the end of the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[ReturnModel](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#ReturnModel "Return the model")]

## <a name="evaluate-the-model"></a><span data-ttu-id="690ca-229">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="690ca-229">Evaluate the model</span></span>

<span data-ttu-id="690ca-230">Cuando el modelo haya sido entrenado, use sus datos de prueba para validar el rendimiento del modelo.</span><span class="sxs-lookup"><span data-stu-id="690ca-230">After your model is trained, use your test data validate the model's performance.</span></span>

1. <span data-ttu-id="690ca-231">Cree el método `Evaluate()`, justo después de `BuildAndTrainModel()`, con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="690ca-231">Create the `Evaluate()` method, just after `BuildAndTrainModel()`, with the following code:</span></span>

    ```csharp
    public static void Evaluate(MLContext mlContext, ITransformer model, IDataView splitTestSet)
    {

    }
    ```

    <span data-ttu-id="690ca-232">El método `Evaluate()` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="690ca-232">The `Evaluate()` method executes the following tasks:</span></span>

    - <span data-ttu-id="690ca-233">Carga el conjunto de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="690ca-233">Loads the test dataset.</span></span>
    - <span data-ttu-id="690ca-234">Crea el evaluador BinaryClassification.</span><span class="sxs-lookup"><span data-stu-id="690ca-234">Creates the BinaryClassification evaluator.</span></span>
    - <span data-ttu-id="690ca-235">Evalúa el modelo y crea las métricas.</span><span class="sxs-lookup"><span data-stu-id="690ca-235">Evaluates the model and creates metrics.</span></span>
    - <span data-ttu-id="690ca-236">Muestra las métricas.</span><span class="sxs-lookup"><span data-stu-id="690ca-236">Displays the metrics.</span></span>

2. <span data-ttu-id="690ca-237">Agregue una llamada al método nuevo desde el método `Main()`, justo debajo de la llamada al método `BuildAndTrainModel()`, utilizando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="690ca-237">Add a call to the new method from the `Main()` method, right under the `BuildAndTrainModel()` method call, using the following code:</span></span>

    [!code-csharp[CallEvaluate](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CallEvaluate "Call the Evaluate method")]

3. <span data-ttu-id="690ca-238">Transforme los datos `splitTestSet` mediante la adición del código siguiente a `Evaluate()`:</span><span class="sxs-lookup"><span data-stu-id="690ca-238">Transform the `splitTestSet` data by adding the following code to `Evaluate()`:</span></span>

    [!code-csharp[PredictWithTransformer](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#TransformData "Predict using the Transformer")]

    <span data-ttu-id="690ca-239">El código anterior usa el método [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) para realizar predicciones para varias filas de entrada de un conjunto de datos de prueba especificado.</span><span class="sxs-lookup"><span data-stu-id="690ca-239">The previous code uses the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method to make predictions for multiple provided input rows of a test dataset.</span></span>

4. <span data-ttu-id="690ca-240">Para evaluar el modelo, agregue lo que se indica a continuación como la siguiente línea de código en el método `Evaluate()`:</span><span class="sxs-lookup"><span data-stu-id="690ca-240">Evaluate the model by adding the following as the next line of code in the `Evaluate()` method:</span></span>

    [!code-csharp[ComputeMetrics](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#Evaluate "Compute Metrics")]

<span data-ttu-id="690ca-241">Cuando haya establecido el conjunto de predicción (`predictions`), el método [Evaluate()](xref:Microsoft.ML.BinaryClassificationCatalog.Evaluate%2A) evalúa el modelo, que compara los valores de predicción con el valor real de `Labels` en el conjunto de datos de prueba y devuelve un objeto [CalibratedBinaryClassificationMetrics](xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics) sobre cómo se ejecuta el modelo.</span><span class="sxs-lookup"><span data-stu-id="690ca-241">Once you have the prediction set (`predictions`), the [Evaluate()](xref:Microsoft.ML.BinaryClassificationCatalog.Evaluate%2A) method assesses the model, which compares the predicted values with the actual `Labels` in the test dataset and returns a [CalibratedBinaryClassificationMetrics](xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics) object on how the model is performing.</span></span>

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="690ca-242">Mostrar las métricas para la validación del modelo</span><span class="sxs-lookup"><span data-stu-id="690ca-242">Displaying the metrics for model validation</span></span>

<span data-ttu-id="690ca-243">Use el siguiente código para mostrar las métricas:</span><span class="sxs-lookup"><span data-stu-id="690ca-243">Use the following code to display the metrics:</span></span>

[!code-csharp[DisplayMetrics](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#DisplayMetrics "Display selected metrics")]

- <span data-ttu-id="690ca-244">La métrica `Accuracy` obtiene la precisión de un modelo, que corresponde a la proporción de predicciones correctas en el conjunto de pruebas.</span><span class="sxs-lookup"><span data-stu-id="690ca-244">The `Accuracy` metric gets the accuracy of a model, which is the proportion of correct predictions in the test set.</span></span>

- <span data-ttu-id="690ca-245">La métrica `AreaUnderRocCurve` indica el nivel de confianza del modelo en clasificar correctamente las clases positivas y negativas.</span><span class="sxs-lookup"><span data-stu-id="690ca-245">The `AreaUnderRocCurve` metric indicates how confident the model is correctly classifying the positive and negative classes.</span></span> <span data-ttu-id="690ca-246">Se desea que `AreaUnderRocCurve` esté lo más cerca de uno posible.</span><span class="sxs-lookup"><span data-stu-id="690ca-246">You want the `AreaUnderRocCurve` to be as close to one as possible.</span></span>

- <span data-ttu-id="690ca-247">La métrica `F1Score` obtiene la puntuación F1 del modelo, que es una medida del equilibrio entre [precisión](../resources/glossary.md#precision) y [recuperación](../resources/glossary.md#recall).</span><span class="sxs-lookup"><span data-stu-id="690ca-247">The `F1Score` metric gets the model's F1 score, which is a measure of balance between [precision](../resources/glossary.md#precision) and [recall](../resources/glossary.md#recall).</span></span>  <span data-ttu-id="690ca-248">Se desea que `F1Score` esté lo más cerca de uno posible.</span><span class="sxs-lookup"><span data-stu-id="690ca-248">You want the `F1Score` to be as close to one as possible.</span></span>

### <a name="predict-the-test-data-outcome"></a><span data-ttu-id="690ca-249">Predicción del resultado de datos de prueba</span><span class="sxs-lookup"><span data-stu-id="690ca-249">Predict the test data outcome</span></span>

1. <span data-ttu-id="690ca-250">Cree el método `UseModelWithSingleItem()`, justo después del método `Evaluate()`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="690ca-250">Create the `UseModelWithSingleItem()` method, just after the `Evaluate()` method, using the following code:</span></span>

    ```csharp
    private static void UseModelWithSingleItem(MLContext mlContext, ITransformer model)
    {

    }
    ```

    <span data-ttu-id="690ca-251">El método `UseModelWithSingleItem()` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="690ca-251">The `UseModelWithSingleItem()` method executes the following tasks:</span></span>

    - <span data-ttu-id="690ca-252">Crea un único comentario de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="690ca-252">Creates a single comment of test data.</span></span>
    - <span data-ttu-id="690ca-253">Predice sentimientos en función de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="690ca-253">Predicts sentiment based on test data.</span></span>
    - <span data-ttu-id="690ca-254">Combina datos de prueba y predicciones para la generación de informes.</span><span class="sxs-lookup"><span data-stu-id="690ca-254">Combines test data and predictions for reporting.</span></span>
    - <span data-ttu-id="690ca-255">Muestra los resultados de la predicción.</span><span class="sxs-lookup"><span data-stu-id="690ca-255">Displays the predicted results.</span></span>

2. <span data-ttu-id="690ca-256">Agregue una llamada al método nuevo desde el método `Main()`, justo debajo de la llamada al método `Evaluate()`, utilizando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="690ca-256">Add a call to the new method from the `Main()` method, right under the `Evaluate()` method call, using the following code:</span></span>

    [!code-csharp[CallUseModelWithSingleItem](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CallUseModelWithSingleItem "Call the UseModelWithSingleItem method")]

3. <span data-ttu-id="690ca-257">Agregue el código siguiente como primera línea en el método `UseModelWithSingleItem()`:</span><span class="sxs-lookup"><span data-stu-id="690ca-257">Add the following code to create as the first line in the `UseModelWithSingleItem()` Method:</span></span>

    [!code-csharp[CreatePredictionEngine](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CreatePredictionEngine1 "Create the PredictionEngine")]

    <span data-ttu-id="690ca-258">[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) es una API de conveniencia, que le permite realizar una predicción en una única instancia de datos.</span><span class="sxs-lookup"><span data-stu-id="690ca-258">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to perform a prediction on a single instance of data.</span></span> <span data-ttu-id="690ca-259">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) no es seguro para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="690ca-259">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="690ca-260">Es aceptable usarlo en entornos de un solo subproceso o prototipo.</span><span class="sxs-lookup"><span data-stu-id="690ca-260">It's acceptable to use in single-threaded or prototype environments.</span></span> <span data-ttu-id="690ca-261">Para mejorar el rendimiento y la seguridad para subprocesos en entornos de producción, use el servicio `PredictionEnginePool`, que crea un [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) de objetos de [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) para su uso en toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="690ca-261">For improved performance and thread safety in production environments, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span> <span data-ttu-id="690ca-262">Consulte esta guía sobre cómo [usar `PredictionEnginePool` en una API web de ASP.NET Core](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span><span class="sxs-lookup"><span data-stu-id="690ca-262">See this guide on how to [use `PredictionEnginePool` in an ASP.NET Core Web API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span></span>

    > [!NOTE]
    > <span data-ttu-id="690ca-263">La extensión del servicio `PredictionEnginePool` está actualmente en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="690ca-263">`PredictionEnginePool` service extension is currently in preview.</span></span>

4. <span data-ttu-id="690ca-264">Agregue un comentario para probar la predicción del modelo entrenado en el método `UseModelWithSingleItem()` mediante la creación de una instancia de `SentimentData`:</span><span class="sxs-lookup"><span data-stu-id="690ca-264">Add a comment to test the trained model's prediction in the `UseModelWithSingleItem()` method by creating an instance of `SentimentData`:</span></span>

    [!code-csharp[PredictionData](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CreateTestIssue1 "Create test data for single prediction")]

5. <span data-ttu-id="690ca-265">Pase los datos del comentario de prueba a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) agregando lo siguiente como siguientes líneas de código al método `UseModelWithSingleItem()`:</span><span class="sxs-lookup"><span data-stu-id="690ca-265">Pass the test comment data to the [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) by adding the following as the next lines of code in the `UseModelWithSingleItem()` method:</span></span>

    [!code-csharp[Predict](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#Predict "Create a prediction of sentiment")]

    <span data-ttu-id="690ca-266">La función [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) realiza una predicción sobre una sola fila de datos.</span><span class="sxs-lookup"><span data-stu-id="690ca-266">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single row of data.</span></span>

6. <span data-ttu-id="690ca-267">Muestre `SentimentText` y la predicción de opiniones correspondiente con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="690ca-267">Display `SentimentText` and corresponding sentiment prediction using the following code:</span></span>

    [!code-csharp[OutputPrediction](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#OutputPrediction "Display prediction output")]

## <a name="use-the-model-for-prediction"></a><span data-ttu-id="690ca-268">Uso del modelo de predicción</span><span class="sxs-lookup"><span data-stu-id="690ca-268">Use the model for prediction</span></span>

### <a name="deploy-and-predict-batch-items"></a><span data-ttu-id="690ca-269">Implementación y predicción de elementos por lotes</span><span class="sxs-lookup"><span data-stu-id="690ca-269">Deploy and predict batch items</span></span>

1. <span data-ttu-id="690ca-270">Cree el método `UseModelWithBatchItems()`, justo después del método `UseModelWithSingleItem()`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="690ca-270">Create the `UseModelWithBatchItems()` method, just after the `UseModelWithSingleItem()` method, using the following code:</span></span>

    ```csharp
    public static void UseModelWithBatchItems(MLContext mlContext, ITransformer model)
    {

    }
    ```

    <span data-ttu-id="690ca-271">El método `UseModelWithBatchItems()` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="690ca-271">The `UseModelWithBatchItems()` method executes the following tasks:</span></span>

    - <span data-ttu-id="690ca-272">Crea datos de prueba por lotes.</span><span class="sxs-lookup"><span data-stu-id="690ca-272">Creates batch test data.</span></span>
    - <span data-ttu-id="690ca-273">Predice sentimientos en función de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="690ca-273">Predicts sentiment based on test data.</span></span>
    - <span data-ttu-id="690ca-274">Combina datos de prueba y predicciones para la generación de informes.</span><span class="sxs-lookup"><span data-stu-id="690ca-274">Combines test data and predictions for reporting.</span></span>
    - <span data-ttu-id="690ca-275">Muestra los resultados de la predicción.</span><span class="sxs-lookup"><span data-stu-id="690ca-275">Displays the predicted results.</span></span>

2. <span data-ttu-id="690ca-276">Agregue una llamada al método nuevo desde el método `Main`, justo debajo de la llamada al método `UseModelWithSingleItem()`, utilizando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="690ca-276">Add a call to the new method from the `Main` method, right under the `UseModelWithSingleItem()` method call, using the following code:</span></span>

    [!code-csharp[CallPredictModelBatchItems](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CallUseModelWithBatchItems "Call the CallUseModelWithBatchItems method")]

3. <span data-ttu-id="690ca-277">Agregue algunos comentarios para probar las predicciones del modelo entrenado en el método `UseModelWithBatchItems()`:</span><span class="sxs-lookup"><span data-stu-id="690ca-277">Add some comments to test the trained model's predictions in the `UseModelWithBatchItems()` method:</span></span>

    [!code-csharp[PredictionData](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CreateTestIssues "Create test data for predictions")]

### <a name="predict-comment-sentiment"></a><span data-ttu-id="690ca-278">Predicción de opiniones de comentarios</span><span class="sxs-lookup"><span data-stu-id="690ca-278">Predict comment sentiment</span></span>

<span data-ttu-id="690ca-279">Use el modelo para predecir la opinión de datos de comentario con el método [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A):</span><span class="sxs-lookup"><span data-stu-id="690ca-279">Use the model to predict the comment data sentiment using the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method:</span></span>

[!code-csharp[Predict](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#Prediction "Create predictions of sentiments")]

### <a name="combine-and-display-the-predictions"></a><span data-ttu-id="690ca-280">Combinación y presentación de las predicciones</span><span class="sxs-lookup"><span data-stu-id="690ca-280">Combine and display the predictions</span></span>

<span data-ttu-id="690ca-281">Cree un encabezado para las predicciones con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="690ca-281">Create a header for the predictions using the following code:</span></span>

[!code-csharp[OutputHeaders](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#AddInfoMessage "Display prediction outputs")]

<span data-ttu-id="690ca-282">Dado que `SentimentPrediction` se hereda de `SentimentData`, el método `Transform()` rellena `SentimentText` con los campos de predicción.</span><span class="sxs-lookup"><span data-stu-id="690ca-282">Because `SentimentPrediction` is inherited from `SentimentData`, the `Transform()` method populated `SentimentText` with the predicted fields.</span></span> <span data-ttu-id="690ca-283">A medida que el proceso ML.NET se ejecuta, cada componente agrega columnas, y esto facilita la presentación de los resultados:</span><span class="sxs-lookup"><span data-stu-id="690ca-283">As the ML.NET process processes, each component adds columns, and this makes it easy to display the results:</span></span>

[!code-csharp[DisplayPredictions](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#DisplayResults "Display the predictions")]

## <a name="results"></a><span data-ttu-id="690ca-284">Resultados</span><span class="sxs-lookup"><span data-stu-id="690ca-284">Results</span></span>

<span data-ttu-id="690ca-285">Los resultados deberían ser similares a los indicados a continuación.</span><span class="sxs-lookup"><span data-stu-id="690ca-285">Your results should be similar to the following.</span></span> <span data-ttu-id="690ca-286">Durante el procesamiento, se muestran mensajes.</span><span class="sxs-lookup"><span data-stu-id="690ca-286">During processing, messages are displayed.</span></span> <span data-ttu-id="690ca-287">Puede ver las advertencias o mensajes de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="690ca-287">You may see warnings, or processing messages.</span></span> <span data-ttu-id="690ca-288">Se han quitado de los siguientes resultados para mayor claridad.</span><span class="sxs-lookup"><span data-stu-id="690ca-288">These have been removed from the following results for clarity.</span></span>

```console
Model quality metrics evaluation
--------------------------------
Accuracy: 83.96%
Auc: 90.51%
F1Score: 84.04%

=============== End of model evaluation ===============

=============== Prediction Test of model with a single sample and test dataset ===============

Sentiment: This was a very bad steak | Prediction: Negative | Probability: 0.1027377
=============== End of Predictions ===============

=============== Prediction Test of loaded model with a multiple samples ===============

Sentiment: This was a horrible meal | Prediction: Negative | Probability: 0.1369192
Sentiment: I love this spaghetti. | Prediction: Positive | Probability: 0.9960636
=============== End of predictions ===============

=============== End of process ===============
Press any key to continue . . .

```

<span data-ttu-id="690ca-289">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="690ca-289">Congratulations!</span></span> <span data-ttu-id="690ca-290">Ya ha creado correctamente un modelo de aprendizaje automático para clasificar y predecir los sentimientos de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="690ca-290">You've now successfully built a machine learning model for classifying and predicting messages sentiment.</span></span>

<span data-ttu-id="690ca-291">La creación de modelos correctos es un proceso iterativo.</span><span class="sxs-lookup"><span data-stu-id="690ca-291">Building successful models is an iterative process.</span></span> <span data-ttu-id="690ca-292">Este modelo tiene una calidad inicial más baja, ya que el tutorial utiliza pequeños conjuntos de datos para proporcionar un entrenamiento rápido del modelo.</span><span class="sxs-lookup"><span data-stu-id="690ca-292">This model has initial lower quality as the tutorial uses small datasets to provide quick model training.</span></span> <span data-ttu-id="690ca-293">Si no está satisfecho con la calidad del modelo, puede intentar mejorarlo proporcionando conjuntos de datos de entrenamiento más grandes o eligiendo distintos algoritmos de entrenamiento con distintos [hiperparámetros](../resources/glossary.md#hyperparameter) para cada algoritmo.</span><span class="sxs-lookup"><span data-stu-id="690ca-293">If you aren't satisfied with the model quality, you can try to improve it by providing larger training datasets or by choosing different training algorithms with different [hyper-parameters](../resources/glossary.md#hyperparameter) for each algorithm.</span></span>

<span data-ttu-id="690ca-294">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).</span><span class="sxs-lookup"><span data-stu-id="690ca-294">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="690ca-295">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="690ca-295">Next steps</span></span>

<span data-ttu-id="690ca-296">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="690ca-296">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="690ca-297">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="690ca-297">Create a console application</span></span>
> - <span data-ttu-id="690ca-298">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="690ca-298">Prepare data</span></span>
> - <span data-ttu-id="690ca-299">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="690ca-299">Load the data</span></span>
> - <span data-ttu-id="690ca-300">Creación y entrenamiento del modelo</span><span class="sxs-lookup"><span data-stu-id="690ca-300">Build and train the model</span></span>
> - <span data-ttu-id="690ca-301">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="690ca-301">Evaluate the model</span></span>
> - <span data-ttu-id="690ca-302">Uso del modelo para realizar una predicción</span><span class="sxs-lookup"><span data-stu-id="690ca-302">Use the model to make a prediction</span></span>
> - <span data-ttu-id="690ca-303">Ver los resultados</span><span class="sxs-lookup"><span data-stu-id="690ca-303">See the results</span></span>

<span data-ttu-id="690ca-304">Siga con el siguiente tutorial para obtener más información</span><span class="sxs-lookup"><span data-stu-id="690ca-304">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="690ca-305">Clasificación de problemas</span><span class="sxs-lookup"><span data-stu-id="690ca-305">Issue Classification</span></span>](github-issue-classification.md)
