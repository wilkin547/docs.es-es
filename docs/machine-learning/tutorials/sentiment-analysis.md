---
title: 'Tutorial: Análisis de comentarios del sitio web: clasificación binaria'
description: En este tutorial se muestra cómo crear una aplicación de consola de .NET Core que clasifica las opiniones de los comentarios del sitio web y toma las medidas oportunas. El clasificador binario de opiniones usa C# en Visual Studio.
ms.date: 09/30/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 47b9a9fe37cbcacab3797ed7fb1398b0c524d746
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "78241135"
---
# <a name="tutorial-analyze-sentiment-of-website-comments-with-binary-classification-in-mlnet"></a><span data-ttu-id="ff4b2-104">Tutorial: Análisis de opinión de los comentarios del sitio web con clasificación binaria de ML.NET</span><span class="sxs-lookup"><span data-stu-id="ff4b2-104">Tutorial: Analyze sentiment of website comments with binary classification in ML.NET</span></span>

<span data-ttu-id="ff4b2-105">En este tutorial se muestra cómo crear una aplicación de consola de .NET Core que clasifica las opiniones de los comentarios del sitio web y toma las medidas oportunas.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-105">This tutorial shows you how to create a .NET Core console application that classifies sentiment from website comments and takes the appropriate action.</span></span> <span data-ttu-id="ff4b2-106">El clasificador binario de opiniones utiliza C# en Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-106">The binary sentiment classifier uses C# in Visual Studio 2017.</span></span>

<span data-ttu-id="ff4b2-107">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="ff4b2-108">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="ff4b2-108">Create a console application</span></span>
> - <span data-ttu-id="ff4b2-109">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="ff4b2-109">Prepare data</span></span>
> - <span data-ttu-id="ff4b2-110">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="ff4b2-110">Load the data</span></span>
> - <span data-ttu-id="ff4b2-111">Creación y entrenamiento del modelo</span><span class="sxs-lookup"><span data-stu-id="ff4b2-111">Build and train the model</span></span>
> - <span data-ttu-id="ff4b2-112">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="ff4b2-112">Evaluate the model</span></span>
> - <span data-ttu-id="ff4b2-113">Uso del modelo para realizar una predicción</span><span class="sxs-lookup"><span data-stu-id="ff4b2-113">Use the model to make a prediction</span></span>
> - <span data-ttu-id="ff4b2-114">Ver los resultados</span><span class="sxs-lookup"><span data-stu-id="ff4b2-114">See the results</span></span>

<span data-ttu-id="ff4b2-115">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).</span><span class="sxs-lookup"><span data-stu-id="ff4b2-115">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ff4b2-116">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ff4b2-116">Prerequisites</span></span>

- <span data-ttu-id="ff4b2-117">[Visual Studio 2017, versión 15.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada</span><span class="sxs-lookup"><span data-stu-id="ff4b2-117">[Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the ".NET Core cross-platform development" workload installed</span></span>

- <span data-ttu-id="ff4b2-118">[Conjunto de datos de frases con etiqueta de opinión de UCI](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) (archivo ZIP)</span><span class="sxs-lookup"><span data-stu-id="ff4b2-118">[UCI Sentiment Labeled Sentences dataset](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) (ZIP file)</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="ff4b2-119">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="ff4b2-119">Create a console application</span></span>

1. <span data-ttu-id="ff4b2-120">Cree una **aplicación de consola de .NET Core** denominada "SentimentAnalysis".</span><span class="sxs-lookup"><span data-stu-id="ff4b2-120">Create a **.NET Core Console Application** called "SentimentAnalysis".</span></span>

2. <span data-ttu-id="ff4b2-121">Cree un directorio denominado *Datos* en el proyecto para guardar los archivos de conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-121">Create a directory named *Data* in your project to save your data set files.</span></span>

3. <span data-ttu-id="ff4b2-122">Instale el **paquete NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-122">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="ff4b2-123">En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-123">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="ff4b2-124">Elija "nuget.org" como origen del paquete y luego seleccione la pestaña **Examinar**. Busque **Microsoft.ML**, seleccione el paquete que desee y luego, el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-124">Choose "nuget.org" as the package source, and then select the **Browse** tab. Search for **Microsoft.ML**, select the package you want, and then select the **Install** button.</span></span> <span data-ttu-id="ff4b2-125">Acepte los términos de licencia del paquete que elija para continuar con la instalación.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-125">Proceed with the installation by agreeing to the license terms for the package you choose.</span></span> <span data-ttu-id="ff4b2-126">Haga lo mismo con el paquete NuGet **Microsoft.ML.FastTree**.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-126">Do the same for the **Microsoft.ML.FastTree** NuGet package.</span></span>

## <a name="prepare-your-data"></a><span data-ttu-id="ff4b2-127">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="ff4b2-127">Prepare your data</span></span>

> [!NOTE]
> <span data-ttu-id="ff4b2-128">Los conjuntos de datos de este tutorial proceden de "From Group to Individual Labels using Deep Features", Kotzias et.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-128">The datasets for this tutorial are from the 'From Group to Individual Labels using Deep Features', Kotzias et.</span></span> <span data-ttu-id="ff4b2-129">al,.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-129">al,.</span></span> <span data-ttu-id="ff4b2-130">KDD 2015, and hosted at the UCI Machine Learning Repository - Dua, D. and Karra Taniskidou, E. (2017).</span><span class="sxs-lookup"><span data-stu-id="ff4b2-130">KDD 2015, and hosted at the UCI Machine Learning Repository - Dua, D. and Karra Taniskidou, E. (2017).</span></span> <span data-ttu-id="ff4b2-131">UCI Machine Learning Repository [http://archive.ics.uci.edu/ml ].</span><span class="sxs-lookup"><span data-stu-id="ff4b2-131">UCI Machine Learning Repository [http://archive.ics.uci.edu/ml].</span></span> <span data-ttu-id="ff4b2-132">Irvine, CA: University of California, School of Information and Computer Science.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-132">Irvine, CA: University of California, School of Information and Computer Science.</span></span>

1. <span data-ttu-id="ff4b2-133">Descargue el [archivo ZIP de conjunto de datos de frases con etiqueta de opinión de UCI](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) y descomprímalo.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-133">Download [UCI Sentiment Labeled Sentences dataset ZIP file](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip), and unzip.</span></span>

2. <span data-ttu-id="ff4b2-134">Copie el archivo `yelp_labelled.txt` en el directorio *Datos* que ha creado.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-134">Copy the `yelp_labelled.txt` file into the *Data* directory you created.</span></span>

3. <span data-ttu-id="ff4b2-135">En el Explorador de soluciones, haga clic con el botón derecho en el archivo `yelp_labeled.txt` y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-135">In Solution Explorer, right-click the `yelp_labeled.txt` file and select **Properties**.</span></span> <span data-ttu-id="ff4b2-136">En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-136">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="ff4b2-137">Crear clases y definir rutas de acceso</span><span class="sxs-lookup"><span data-stu-id="ff4b2-137">Create classes and define paths</span></span>

1. <span data-ttu-id="ff4b2-138">Agregue las siguientes instrucciones `using` adicionales a la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-138">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

    [!code-csharp[AddUsings](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#AddUsings "Add necessary usings")]

1. <span data-ttu-id="ff4b2-139">Agregue el código siguiente a la línea por encima del método `Main` para crear un campo que incluya la ruta de acceso del archivo del conjunto de datos descargado recientemente:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-139">Add the following code to the line right above the `Main` method, to create a field to hold the recently downloaded dataset file path:</span></span>

    [!code-csharp[Declare global variables](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#DeclareGlobalVariables "Declare global variables")]

1. <span data-ttu-id="ff4b2-140">Luego, cree clases para los datos de entrada y las predicciones.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-140">Next, create classes for your input data and predictions.</span></span> <span data-ttu-id="ff4b2-141">Agregue una nueva clase a su proyecto:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-141">Add a new class to your project:</span></span>

    - <span data-ttu-id="ff4b2-142">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-142">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

    - <span data-ttu-id="ff4b2-143">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-143">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="ff4b2-144">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-144">Then, select the **Add** button.</span></span>

1. <span data-ttu-id="ff4b2-145">Se abre el archivo *SentimentData.cs* en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-145">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="ff4b2-146">Agregue la siguiente instrucción `using` a la parte superior de *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-146">Add the following `using` statement to the top of *SentimentData.cs*:</span></span>

    [!code-csharp[AddUsings](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/SentimentData.cs#AddUsings "Add necessary usings")]

1. <span data-ttu-id="ff4b2-147">Quite la definición de clase existente y agregue el código siguiente, que tiene dos clases `SentimentData` y `SentimentPrediction`, al archivo *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-147">Remove the existing class definition and add the following code, which has two classes `SentimentData` and `SentimentPrediction`, to the *SentimentData.cs* file:</span></span>

    [!code-csharp[DeclareTypes](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/SentimentData.cs#DeclareTypes "Declare data record types")]

### <a name="how-the-data-was-prepared"></a><span data-ttu-id="ff4b2-148">¿Cómo se han preparado los datos?</span><span class="sxs-lookup"><span data-stu-id="ff4b2-148">How the data was prepared</span></span>

<span data-ttu-id="ff4b2-149">La clase de conjunto de datos de entrada, `SentimentData`, tiene un `string` para comentarios del usuario (`SentimentText`) y un valor `bool` (`Sentiment`) de 1 (positivo) o de 0 (negativo) para las opiniones.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-149">The input dataset class, `SentimentData`, has a `string` for user comments (`SentimentText`) and a `bool` (`Sentiment`) value of either 1 (positive) or 0 (negative) for sentiment.</span></span> <span data-ttu-id="ff4b2-150">Ambos campos tienen atributos [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) adjuntos a ellos, que describe el orden de archivo de datos de cada campo.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-150">Both fields have [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) attributes attached to them, which describes the data file order of each field.</span></span>  <span data-ttu-id="ff4b2-151">Además, la propiedad `Sentiment` tiene un atributo [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A) que lo designa como campo `Label`.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-151">In addition, the `Sentiment` property has a [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A) attribute to designate it as the `Label` field.</span></span> <span data-ttu-id="ff4b2-152">El archivo de ejemplo siguiente no tiene una fila de encabezado y se ve así:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-152">The following example file doesn't have a header row, and looks like this:</span></span>

|<span data-ttu-id="ff4b2-153">SentimentText</span><span class="sxs-lookup"><span data-stu-id="ff4b2-153">SentimentText</span></span>                         |<span data-ttu-id="ff4b2-154">Opinión (etiqueta)</span><span class="sxs-lookup"><span data-stu-id="ff4b2-154">Sentiment (Label)</span></span> |
|--------------------------------------|----------|
|<span data-ttu-id="ff4b2-155">La camarera era algo lenta en el servicio.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-155">Waitress was a little slow in service.</span></span>|    <span data-ttu-id="ff4b2-156">0</span><span class="sxs-lookup"><span data-stu-id="ff4b2-156">0</span></span>     |
|<span data-ttu-id="ff4b2-157">La corteza no es buena.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-157">Crust is not good.</span></span>                    |    <span data-ttu-id="ff4b2-158">0</span><span class="sxs-lookup"><span data-stu-id="ff4b2-158">0</span></span>     |
|<span data-ttu-id="ff4b2-159">¡Ah! Me encantó el lugar.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-159">Wow... Loved this place.</span></span>              |    <span data-ttu-id="ff4b2-160">1</span><span class="sxs-lookup"><span data-stu-id="ff4b2-160">1</span></span>     |
|<span data-ttu-id="ff4b2-161">El servicio fue muy rápido.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-161">Service was very prompt.</span></span>              |    <span data-ttu-id="ff4b2-162">1</span><span class="sxs-lookup"><span data-stu-id="ff4b2-162">1</span></span>     |

<span data-ttu-id="ff4b2-163">`SentimentPrediction` es la clase de predicción que se utiliza tras el entrenamiento del modelo.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-163">`SentimentPrediction` is the prediction class used after model training.</span></span> <span data-ttu-id="ff4b2-164">Hereda de `SentimentData` para que la entrada `SentimentText` pueda mostrarse junto con la predicción de salida.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-164">It inherits from `SentimentData` so that the input `SentimentText` can be displayed along with the output prediction.</span></span> <span data-ttu-id="ff4b2-165">El booleano `Prediction` es el valor que predice el modelo cuando se proporciona con la nueva entrada `SentimentText`.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-165">The `Prediction` boolean is the value that the model predicts when supplied with new input `SentimentText`.</span></span>

<span data-ttu-id="ff4b2-166">La clase de salida `SentimentPrediction` contiene otras dos propiedades calculadas por el modelo: `Score`, el resultado sin formato calculado por el modelo y `Probability`, la puntuación calibrada de la probabilidad de que el texto tenga un sentimiento positivo.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-166">The output class `SentimentPrediction` contains two other properties calculated by the model: `Score` - the raw score calculated by the model, and `Probability` - the score calibrated to the likelihood of the text having positive sentiment.</span></span>

<span data-ttu-id="ff4b2-167">Para este tutorial, la propiedad más importante es `Prediction`.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-167">For this tutorial, the most important property is `Prediction`.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="ff4b2-168">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="ff4b2-168">Load the data</span></span>

<span data-ttu-id="ff4b2-169">Los datos de ML.NET se representan como una [clase IDataView](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="ff4b2-169">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="ff4b2-170">`IDataView` es una manera flexible y eficiente de describir datos tabulares (numéricos y de texto).</span><span class="sxs-lookup"><span data-stu-id="ff4b2-170">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="ff4b2-171">Los datos se pueden cargar desde un archivo de texto o en tiempo real (por ejemplo, archivos de registro o base de datos SQL) en un objeto `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-171">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

<span data-ttu-id="ff4b2-172">La [clase MLContext](xref:Microsoft.ML.MLContext) es un punto de partida para todas las operaciones de ML.NET.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-172">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations.</span></span> <span data-ttu-id="ff4b2-173">La inicialización de `mlContext` crea un entorno de ML.NET que se puede compartir entre los objetos del flujo de trabajo de creación de modelos.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-173">Initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="ff4b2-174">Como concepto, se parece a `DBContext` en Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-174">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

<span data-ttu-id="ff4b2-175">Prepare la aplicación y luego cargue datos:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-175">You prepare the app, and then load data:</span></span>

1. <span data-ttu-id="ff4b2-176">Reemplace la línea `Console.WriteLine("Hello World!")` del método `Main` por el siguiente código para declarar e inicializar la variable mlContext:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-176">Replace the `Console.WriteLine("Hello World!")` line in the `Main` method with the following code to declare and initialize the mlContext variable:</span></span>

    [!code-csharp[CreateMLContext](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CreateMLContext "Create the ML Context")]

2. <span data-ttu-id="ff4b2-177">Agregue lo siguiente como la siguiente línea de código en el método `Main()`:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-177">Add the following as the next line of code in the `Main()` method:</span></span>

    [!code-csharp[CallLoadData](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CallLoadData)]

3. <span data-ttu-id="ff4b2-178">Cree el método `LoadData()`, justo después del método `Main()`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-178">Create the `LoadData()` method, just after the `Main()` method, using the following code:</span></span>

    ```csharp
    public static TrainTestData LoadData(MLContext mlContext)
    {

    }
    ```

    <span data-ttu-id="ff4b2-179">El método `LoadData()` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-179">The `LoadData()` method executes the following tasks:</span></span>

    - <span data-ttu-id="ff4b2-180">Carga los datos.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-180">Loads the data.</span></span>
    - <span data-ttu-id="ff4b2-181">Divide el conjunto de datos cargado en conjuntos de datos de entrenamiento y prueba.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-181">Splits the loaded dataset into train and test datasets.</span></span>
    - <span data-ttu-id="ff4b2-182">Devuelve los conjuntos de datos divididos en entrenamiento y prueba.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-182">Returns the split train and test datasets.</span></span>

4. <span data-ttu-id="ff4b2-183">Agregue el código siguiente a la primera línea del método `LoadData()`:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-183">Add the following code as the first line of the `LoadData()` method:</span></span>

    [!code-csharp[LoadData](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#LoadData "loading dataset")]

    <span data-ttu-id="ff4b2-184">[LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) define el esquema de datos y lee en el archivo.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-184">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) defines the data schema and reads in the file.</span></span> <span data-ttu-id="ff4b2-185">Toma las variables de ruta de acceso de datos y devuelve `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-185">It takes in the data path variables and returns an `IDataView`.</span></span>

### <a name="split-the-dataset-for-model-training-and-testing"></a><span data-ttu-id="ff4b2-186">División del conjunto de datos para el entrenamiento y la prueba del modelo</span><span class="sxs-lookup"><span data-stu-id="ff4b2-186">Split the dataset for model training and testing</span></span>

<span data-ttu-id="ff4b2-187">Al preparar un modelo, se utiliza parte del conjunto de datos para entrenarlo y parte del conjunto de datos para probar la precisión del modelo.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-187">When preparing a model, you use part of the dataset to train it and part of the dataset to test the model's accuracy.</span></span>

1. <span data-ttu-id="ff4b2-188">Para dividir los datos cargados en los conjuntos de datos necesarios, agregue el código siguiente como la siguiente línea en el método `LoadData()`:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-188">To split the loaded data into the needed datasets, add the following code as the next line in the `LoadData()` method:</span></span>

    [!code-csharp[SplitData](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#SplitData "Split the Data")]

    <span data-ttu-id="ff4b2-189">El código anterior usa el método [TrainTestSplit()](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit%2A) para dividir el conjunto de datos cargado en conjuntos de datos de entrenamiento y de prueba, que devuelve en la clase [TrainTestData](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData).</span><span class="sxs-lookup"><span data-stu-id="ff4b2-189">The previous code uses the [TrainTestSplit()](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit%2A) method to split the loaded dataset into train and test datasets and return them in the [TrainTestData](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData) class.</span></span> <span data-ttu-id="ff4b2-190">Especifique el porcentaje de datos del conjunto de prueba con el parámetro `testFraction`.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-190">Specify the test set percentage of data with the `testFraction`parameter.</span></span> <span data-ttu-id="ff4b2-191">El valor predeterminado es 10 %; en este caso se usa 20 % para evaluar más datos.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-191">The default is 10%, in this case you use 20% to evaluate more data.</span></span>

2. <span data-ttu-id="ff4b2-192">Devuelva el `splitDataView` al final del método `LoadData()`:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-192">Return the `splitDataView` at the end of the `LoadData()` method:</span></span>

    [!code-csharp[ReturnSplitData](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#ReturnSplitData)]

## <a name="build-and-train-the-model"></a><span data-ttu-id="ff4b2-193">Creación y entrenamiento del modelo</span><span class="sxs-lookup"><span data-stu-id="ff4b2-193">Build and train the model</span></span>

1. <span data-ttu-id="ff4b2-194">Agregue la siguiente llamada al método `BuildAndTrainModel` como siguiente línea de código del método `Main()`:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-194">Add the following call to the `BuildAndTrainModel`method as the next line of code in the `Main()` method:</span></span>

    [!code-csharp[CallBuildAndTrainModel](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CallBuildAndTrainModel)]

    <span data-ttu-id="ff4b2-195">El método `BuildAndTrainModel()` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-195">The `BuildAndTrainModel()` method executes the following tasks:</span></span>

    - <span data-ttu-id="ff4b2-196">Extrae y transforma los datos.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-196">Extracts and transforms the data.</span></span>
    - <span data-ttu-id="ff4b2-197">Entrena el modelo.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-197">Trains the model.</span></span>
    - <span data-ttu-id="ff4b2-198">Predice sentimientos en función de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-198">Predicts sentiment based on test data.</span></span>
    - <span data-ttu-id="ff4b2-199">Devuelve el modelo.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-199">Returns the model.</span></span>

2. <span data-ttu-id="ff4b2-200">Cree el método `BuildAndTrainModel()`, justo después del método `Main()`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-200">Create the `BuildAndTrainModel()` method, just after the `Main()` method, using the following code:</span></span>

    ```csharp
    public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView splitTrainSet)
    {

    }
    ```

### <a name="extract-and-transform-the-data"></a><span data-ttu-id="ff4b2-201">Extraer y transformar los datos</span><span class="sxs-lookup"><span data-stu-id="ff4b2-201">Extract and transform the data</span></span>

1. <span data-ttu-id="ff4b2-202">Llame a `FeaturizeText` como siguiente línea de código:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-202">Call `FeaturizeText` as the next line of code:</span></span>

    [!code-csharp[FeaturizeText](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#FeaturizeText "Featurize the text")]

    <span data-ttu-id="ff4b2-203">El método `FeaturizeText()` del código anterior convierte la columna de texto (`SentimentText`) en una columna de tipo de clave numérico `Features` que el algoritmo de aprendizaje automático utiliza y agrega como nueva columna de conjunto de datos:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-203">The `FeaturizeText()` method in the previous code converts the text column (`SentimentText`) into a numeric key type `Features` column used by the machine learning algorithm and adds it as a new dataset column:</span></span>

    |<span data-ttu-id="ff4b2-204">SentimentText</span><span class="sxs-lookup"><span data-stu-id="ff4b2-204">SentimentText</span></span>                         |<span data-ttu-id="ff4b2-205">Opinión</span><span class="sxs-lookup"><span data-stu-id="ff4b2-205">Sentiment</span></span> |<span data-ttu-id="ff4b2-206">Características</span><span class="sxs-lookup"><span data-stu-id="ff4b2-206">Features</span></span>              |
    |--------------------------------------|----------|----------------------|
    |<span data-ttu-id="ff4b2-207">La camarera era algo lenta en el servicio.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-207">Waitress was a little slow in service.</span></span>|    <span data-ttu-id="ff4b2-208">0</span><span class="sxs-lookup"><span data-stu-id="ff4b2-208">0</span></span>     |<span data-ttu-id="ff4b2-209">[0,76, 0,65, 0,44, …]</span><span class="sxs-lookup"><span data-stu-id="ff4b2-209">[0.76, 0.65, 0.44, …]</span></span> |
    |<span data-ttu-id="ff4b2-210">La corteza no es buena.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-210">Crust is not good.</span></span>                    |    <span data-ttu-id="ff4b2-211">0</span><span class="sxs-lookup"><span data-stu-id="ff4b2-211">0</span></span>     |<span data-ttu-id="ff4b2-212">[0,98, 0,43, 0,54, …]</span><span class="sxs-lookup"><span data-stu-id="ff4b2-212">[0.98, 0.43, 0.54, …]</span></span> |
    |<span data-ttu-id="ff4b2-213">¡Ah! Me encantó el lugar.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-213">Wow... Loved this place.</span></span>              |    <span data-ttu-id="ff4b2-214">1</span><span class="sxs-lookup"><span data-stu-id="ff4b2-214">1</span></span>     |<span data-ttu-id="ff4b2-215">[0,35, 0,73, 0,46, …]</span><span class="sxs-lookup"><span data-stu-id="ff4b2-215">[0.35, 0.73, 0.46, …]</span></span> |
    |<span data-ttu-id="ff4b2-216">El servicio fue muy rápido.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-216">Service was very prompt.</span></span>              |    <span data-ttu-id="ff4b2-217">1</span><span class="sxs-lookup"><span data-stu-id="ff4b2-217">1</span></span>     |<span data-ttu-id="ff4b2-218">[0,39, 0, 0,75, …]</span><span class="sxs-lookup"><span data-stu-id="ff4b2-218">[0.39, 0, 0.75, …]</span></span>    |

### <a name="add-a-learning-algorithm"></a><span data-ttu-id="ff4b2-219">Incorporación de un algoritmo de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="ff4b2-219">Add a learning algorithm</span></span>

<span data-ttu-id="ff4b2-220">Esta aplicación usa un algoritmo de clasificación que clasifica elementos o filas de datos.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-220">This app uses a classification algorithm that categorizes items or rows of data.</span></span> <span data-ttu-id="ff4b2-221">La aplicación clasifica los comentarios del sitio web como positivos o negativos, así que use la tarea de clasificación binaria.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-221">The app categorizes website comments as either positive or negative, so use the binary classification task.</span></span>

<span data-ttu-id="ff4b2-222">Anexe la tarea de aprendizaje automático a las definiciones de transformación de datos agregando lo siguiente como siguiente línea de código en `BuildAndTrainModel()`:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-222">Append the machine learning task to the data transformation definitions by adding the following as the next line of code in `BuildAndTrainModel()`:</span></span>

[!code-csharp[SdcaLogisticRegressionBinaryTrainer](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#AddTrainer "Add a SdcaLogisticRegressionBinaryTrainer")]

<span data-ttu-id="ff4b2-223">[SdcaLogisticRegressionBinaryTrainer](xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer) es el algoritmo de entrenamiento de clasificación.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-223">The [SdcaLogisticRegressionBinaryTrainer](xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer) is your classification training algorithm.</span></span> <span data-ttu-id="ff4b2-224">Se anexa a `estimator` y acepta `SentimentText` (`Features`) caracterizado y los parámetros de entrada `Label` para aprender de los datos históricos.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-224">This is appended to the `estimator` and accepts the featurized `SentimentText` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span>

### <a name="train-the-model"></a><span data-ttu-id="ff4b2-225">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="ff4b2-225">Train the model</span></span>

<span data-ttu-id="ff4b2-226">Ajuste el modelo a los datos `splitTrainSet` y devuelva el modelo entrenado. Para ello, agregue lo que se indica a continuación como la siguiente línea de código en el método `BuildAndTrainModel()`:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-226">Fit the model to the `splitTrainSet` data and return the trained model by adding the following as the next line of code in the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[TrainModel](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#TrainModel "Train the model")]

<span data-ttu-id="ff4b2-227">El método [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) entrena el modelo al transformar el conjunto de datos y aplicar el aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-227">The [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) method trains your model by transforming the dataset and applying the training.</span></span>

### <a name="return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="ff4b2-228">Devolución del modelo entrenado para su uso para la evaluación</span><span class="sxs-lookup"><span data-stu-id="ff4b2-228">Return the model trained to use for evaluation</span></span>

 <span data-ttu-id="ff4b2-229">Devuelva el modelo al final del método `BuildAndTrainModel()`:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-229">Return the model at the end of the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[ReturnModel](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#ReturnModel "Return the model")]

## <a name="evaluate-the-model"></a><span data-ttu-id="ff4b2-230">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="ff4b2-230">Evaluate the model</span></span>

<span data-ttu-id="ff4b2-231">Cuando el modelo haya sido entrenado, use sus datos de prueba para validar el rendimiento del modelo.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-231">After your model is trained, use your test data validate the model's performance.</span></span>

1. <span data-ttu-id="ff4b2-232">Cree el método `Evaluate()`, justo después de `BuildAndTrainModel()`, con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-232">Create the `Evaluate()` method, just after `BuildAndTrainModel()`, with the following code:</span></span>

    ```csharp
    public static void Evaluate(MLContext mlContext, ITransformer model, IDataView splitTestSet)
    {

    }
    ```

    <span data-ttu-id="ff4b2-233">El método `Evaluate()` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-233">The `Evaluate()` method executes the following tasks:</span></span>

    - <span data-ttu-id="ff4b2-234">Carga el conjunto de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-234">Loads the test dataset.</span></span>
    - <span data-ttu-id="ff4b2-235">Crea el evaluador BinaryClassification.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-235">Creates the BinaryClassification evaluator.</span></span>
    - <span data-ttu-id="ff4b2-236">Evalúa el modelo y crea las métricas.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-236">Evaluates the model and creates metrics.</span></span>
    - <span data-ttu-id="ff4b2-237">Muestra las métricas.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-237">Displays the metrics.</span></span>

2. <span data-ttu-id="ff4b2-238">Agregue una llamada al método nuevo desde el método `Main()`, justo debajo de la llamada al método `BuildAndTrainModel()`, utilizando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-238">Add a call to the new method from the `Main()` method, right under the `BuildAndTrainModel()` method call, using the following code:</span></span>

    [!code-csharp[CallEvaluate](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CallEvaluate "Call the Evaluate method")]

3. <span data-ttu-id="ff4b2-239">Transforme los datos `splitTestSet` mediante la adición del código siguiente a `Evaluate()`:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-239">Transform the `splitTestSet` data by adding the following code to `Evaluate()`:</span></span>

    [!code-csharp[PredictWithTransformer](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#TransformData "Predict using the Transformer")]

    <span data-ttu-id="ff4b2-240">El código anterior usa el método [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) para realizar predicciones para varias filas de entrada de un conjunto de datos de prueba especificado.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-240">The previous code uses the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method to make predictions for multiple provided input rows of a test dataset.</span></span>

4. <span data-ttu-id="ff4b2-241">Para evaluar el modelo, agregue lo que se indica a continuación como la siguiente línea de código en el método `Evaluate()`:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-241">Evaluate the model by adding the following as the next line of code in the `Evaluate()` method:</span></span>

    [!code-csharp[ComputeMetrics](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#Evaluate "Compute Metrics")]

<span data-ttu-id="ff4b2-242">Cuando haya establecido el conjunto de predicción (`predictions`), el método [Evaluate()](xref:Microsoft.ML.BinaryClassificationCatalog.Evaluate%2A) evalúa el modelo, que compara los valores de predicción con el valor real de `Labels` en el conjunto de datos de prueba y devuelve un objeto [CalibratedBinaryClassificationMetrics](xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics) sobre cómo se ejecuta el modelo.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-242">Once you have the prediction set (`predictions`), the [Evaluate()](xref:Microsoft.ML.BinaryClassificationCatalog.Evaluate%2A) method assesses the model, which compares the predicted values with the actual `Labels` in the test dataset and returns a [CalibratedBinaryClassificationMetrics](xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics) object on how the model is performing.</span></span>

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="ff4b2-243">Mostrar las métricas para la validación del modelo</span><span class="sxs-lookup"><span data-stu-id="ff4b2-243">Displaying the metrics for model validation</span></span>

<span data-ttu-id="ff4b2-244">Use el siguiente código para mostrar las métricas:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-244">Use the following code to display the metrics:</span></span>

[!code-csharp[DisplayMetrics](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#DisplayMetrics "Display selected metrics")]

- <span data-ttu-id="ff4b2-245">La métrica `Accuracy` obtiene la precisión de un modelo, que corresponde a la proporción de predicciones correctas en el conjunto de pruebas.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-245">The `Accuracy` metric gets the accuracy of a model, which is the proportion of correct predictions in the test set.</span></span>

- <span data-ttu-id="ff4b2-246">La métrica `AreaUnderRocCurve` indica el nivel de confianza del modelo en clasificar correctamente las clases positivas y negativas.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-246">The `AreaUnderRocCurve` metric indicates how confident the model is correctly classifying the positive and negative classes.</span></span> <span data-ttu-id="ff4b2-247">Se desea que `AreaUnderRocCurve` esté lo más cerca de uno posible.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-247">You want the `AreaUnderRocCurve` to be as close to one as possible.</span></span>

- <span data-ttu-id="ff4b2-248">La métrica `F1Score` obtiene la puntuación F1 del modelo, que es una medida del equilibrio entre [precisión](../resources/glossary.md#precision) y [recuperación](../resources/glossary.md#recall).</span><span class="sxs-lookup"><span data-stu-id="ff4b2-248">The `F1Score` metric gets the model's F1 score, which is a measure of balance between [precision](../resources/glossary.md#precision) and [recall](../resources/glossary.md#recall).</span></span>  <span data-ttu-id="ff4b2-249">Se desea que `F1Score` esté lo más cerca de uno posible.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-249">You want the `F1Score` to be as close to one as possible.</span></span>

### <a name="predict-the-test-data-outcome"></a><span data-ttu-id="ff4b2-250">Predicción del resultado de datos de prueba</span><span class="sxs-lookup"><span data-stu-id="ff4b2-250">Predict the test data outcome</span></span>

1. <span data-ttu-id="ff4b2-251">Cree el método `UseModelWithSingleItem()`, justo después del método `Evaluate()`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-251">Create the `UseModelWithSingleItem()` method, just after the `Evaluate()` method, using the following code:</span></span>

    ```csharp
    private static void UseModelWithSingleItem(MLContext mlContext, ITransformer model)
    {

    }
    ```

    <span data-ttu-id="ff4b2-252">El método `UseModelWithSingleItem()` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-252">The `UseModelWithSingleItem()` method executes the following tasks:</span></span>

    - <span data-ttu-id="ff4b2-253">Crea un único comentario de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-253">Creates a single comment of test data.</span></span>
    - <span data-ttu-id="ff4b2-254">Predice sentimientos en función de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-254">Predicts sentiment based on test data.</span></span>
    - <span data-ttu-id="ff4b2-255">Combina datos de prueba y predicciones para la generación de informes.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-255">Combines test data and predictions for reporting.</span></span>
    - <span data-ttu-id="ff4b2-256">Muestra los resultados de la predicción.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-256">Displays the predicted results.</span></span>

2. <span data-ttu-id="ff4b2-257">Agregue una llamada al método nuevo desde el método `Main()`, justo debajo de la llamada al método `Evaluate()`, utilizando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-257">Add a call to the new method from the `Main()` method, right under the `Evaluate()` method call, using the following code:</span></span>

    [!code-csharp[CallUseModelWithSingleItem](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CallUseModelWithSingleItem "Call the UseModelWithSingleItem method")]

3. <span data-ttu-id="ff4b2-258">Agregue el código siguiente como primera línea en el método `UseModelWithSingleItem()`:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-258">Add the following code to create as the first line in the `UseModelWithSingleItem()` Method:</span></span>

    [!code-csharp[CreatePredictionEngine](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CreatePredictionEngine1 "Create the PredictionEngine")]

    <span data-ttu-id="ff4b2-259">[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) es una API de conveniencia, que le permite realizar una predicción en una única instancia de datos.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-259">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to perform a prediction on a single instance of data.</span></span> <span data-ttu-id="ff4b2-260">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) no es seguro para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-260">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="ff4b2-261">Es aceptable usarlo en entornos de un solo subproceso o prototipo.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-261">It's acceptable to use in single-threaded or prototype environments.</span></span> <span data-ttu-id="ff4b2-262">Para mejorar el rendimiento y la seguridad para subprocesos en entornos de producción, use el servicio `PredictionEnginePool`, que crea un [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) de objetos de [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) para su uso en toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-262">For improved performance and thread safety in production environments, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span> <span data-ttu-id="ff4b2-263">Consulte esta guía sobre cómo [usar `PredictionEnginePool` en una API web de ASP.NET Core](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span><span class="sxs-lookup"><span data-stu-id="ff4b2-263">See this guide on how to [use `PredictionEnginePool` in an ASP.NET Core Web API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span></span>

    > [!NOTE]
    > <span data-ttu-id="ff4b2-264">La extensión del servicio `PredictionEnginePool` está actualmente en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-264">`PredictionEnginePool` service extension is currently in preview.</span></span>

4. <span data-ttu-id="ff4b2-265">Agregue un comentario para probar la predicción del modelo entrenado en el método `UseModelWithSingleItem()` mediante la creación de una instancia de `SentimentData`:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-265">Add a comment to test the trained model's prediction in the `UseModelWithSingleItem()` method by creating an instance of `SentimentData`:</span></span>

    [!code-csharp[PredictionData](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CreateTestIssue1 "Create test data for single prediction")]

5. <span data-ttu-id="ff4b2-266">Pase los datos del comentario de prueba a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) agregando lo siguiente como siguientes líneas de código al método `UseModelWithSingleItem()`:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-266">Pass the test comment data to the [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) by adding the following as the next lines of code in the `UseModelWithSingleItem()` method:</span></span>

    [!code-csharp[Predict](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#Predict "Create a prediction of sentiment")]

    <span data-ttu-id="ff4b2-267">La función [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) realiza una predicción sobre una sola fila de datos.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-267">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single row of data.</span></span>

6. <span data-ttu-id="ff4b2-268">Muestre `SentimentText` y la predicción de opiniones correspondiente con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-268">Display `SentimentText` and corresponding sentiment prediction using the following code:</span></span>

    [!code-csharp[OutputPrediction](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#OutputPrediction "Display prediction output")]

## <a name="use-the-model-for-prediction"></a><span data-ttu-id="ff4b2-269">Uso del modelo de predicción</span><span class="sxs-lookup"><span data-stu-id="ff4b2-269">Use the model for prediction</span></span>

### <a name="deploy-and-predict-batch-items"></a><span data-ttu-id="ff4b2-270">Implementación y predicción de elementos por lotes</span><span class="sxs-lookup"><span data-stu-id="ff4b2-270">Deploy and predict batch items</span></span>

1. <span data-ttu-id="ff4b2-271">Cree el método `UseModelWithBatchItems()`, justo después del método `UseModelWithSingleItem()`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-271">Create the `UseModelWithBatchItems()` method, just after the `UseModelWithSingleItem()` method, using the following code:</span></span>

    ```csharp
    public static void UseModelWithBatchItems(MLContext mlContext, ITransformer model)
    {

    }
    ```

    <span data-ttu-id="ff4b2-272">El método `UseModelWithBatchItems()` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-272">The `UseModelWithBatchItems()` method executes the following tasks:</span></span>

    - <span data-ttu-id="ff4b2-273">Crea datos de prueba por lotes.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-273">Creates batch test data.</span></span>
    - <span data-ttu-id="ff4b2-274">Predice sentimientos en función de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-274">Predicts sentiment based on test data.</span></span>
    - <span data-ttu-id="ff4b2-275">Combina datos de prueba y predicciones para la generación de informes.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-275">Combines test data and predictions for reporting.</span></span>
    - <span data-ttu-id="ff4b2-276">Muestra los resultados de la predicción.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-276">Displays the predicted results.</span></span>

2. <span data-ttu-id="ff4b2-277">Agregue una llamada al método nuevo desde el método `Main`, justo debajo de la llamada al método `UseModelWithSingleItem()`, utilizando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-277">Add a call to the new method from the `Main` method, right under the `UseModelWithSingleItem()` method call, using the following code:</span></span>

    [!code-csharp[CallPredictModelBatchItems](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CallUseModelWithBatchItems "Call the CallUseModelWithBatchItems method")]

3. <span data-ttu-id="ff4b2-278">Agregue algunos comentarios para probar las predicciones del modelo entrenado en el método `UseModelWithBatchItems()`:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-278">Add some comments to test the trained model's predictions in the `UseModelWithBatchItems()` method:</span></span>

    [!code-csharp[PredictionData](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CreateTestIssues "Create test data for predictions")]

### <a name="predict-comment-sentiment"></a><span data-ttu-id="ff4b2-279">Predicción de opiniones de comentarios</span><span class="sxs-lookup"><span data-stu-id="ff4b2-279">Predict comment sentiment</span></span>

<span data-ttu-id="ff4b2-280">Use el modelo para predecir la opinión de datos de comentario con el método [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A):</span><span class="sxs-lookup"><span data-stu-id="ff4b2-280">Use the model to predict the comment data sentiment using the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method:</span></span>

[!code-csharp[Predict](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#Prediction "Create predictions of sentiments")]

### <a name="combine-and-display-the-predictions"></a><span data-ttu-id="ff4b2-281">Combinación y presentación de las predicciones</span><span class="sxs-lookup"><span data-stu-id="ff4b2-281">Combine and display the predictions</span></span>

<span data-ttu-id="ff4b2-282">Cree un encabezado para las predicciones con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-282">Create a header for the predictions using the following code:</span></span>

[!code-csharp[OutputHeaders](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#AddInfoMessage "Display prediction outputs")]

<span data-ttu-id="ff4b2-283">Dado que `SentimentPrediction` se hereda de `SentimentData`, el método `Transform()` rellena `SentimentText` con los campos de predicción.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-283">Because `SentimentPrediction` is inherited from `SentimentData`, the `Transform()` method populated `SentimentText` with the predicted fields.</span></span> <span data-ttu-id="ff4b2-284">A medida que el proceso ML.NET se ejecuta, cada componente agrega columnas, y esto facilita la presentación de los resultados:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-284">As the ML.NET process processes, each component adds columns, and this makes it easy to display the results:</span></span>

[!code-csharp[DisplayPredictions](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#DisplayResults "Display the predictions")]

## <a name="results"></a><span data-ttu-id="ff4b2-285">Resultados</span><span class="sxs-lookup"><span data-stu-id="ff4b2-285">Results</span></span>

<span data-ttu-id="ff4b2-286">Los resultados deberían ser similares a los indicados a continuación.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-286">Your results should be similar to the following.</span></span> <span data-ttu-id="ff4b2-287">Durante el procesamiento, se muestran mensajes.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-287">During processing, messages are displayed.</span></span> <span data-ttu-id="ff4b2-288">Puede ver las advertencias o mensajes de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-288">You may see warnings, or processing messages.</span></span> <span data-ttu-id="ff4b2-289">Se han quitado de los siguientes resultados para mayor claridad.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-289">These have been removed from the following results for clarity.</span></span>

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

<span data-ttu-id="ff4b2-290">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="ff4b2-290">Congratulations!</span></span> <span data-ttu-id="ff4b2-291">Ya ha creado correctamente un modelo de aprendizaje automático para clasificar y predecir los sentimientos de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-291">You've now successfully built a machine learning model for classifying and predicting messages sentiment.</span></span>

<span data-ttu-id="ff4b2-292">La creación de modelos correctos es un proceso iterativo.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-292">Building successful models is an iterative process.</span></span> <span data-ttu-id="ff4b2-293">Este modelo tiene una calidad inicial más baja, ya que el tutorial utiliza pequeños conjuntos de datos para proporcionar un entrenamiento rápido del modelo.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-293">This model has initial lower quality as the tutorial uses small datasets to provide quick model training.</span></span> <span data-ttu-id="ff4b2-294">Si no está satisfecho con la calidad del modelo, puede intentar mejorarlo proporcionando conjuntos de datos de entrenamiento más grandes o eligiendo distintos algoritmos de entrenamiento con distintos [hiperparámetros](../resources/glossary.md#hyperparameter) para cada algoritmo.</span><span class="sxs-lookup"><span data-stu-id="ff4b2-294">If you aren't satisfied with the model quality, you can try to improve it by providing larger training datasets or by choosing different training algorithms with different [hyper-parameters](../resources/glossary.md#hyperparameter) for each algorithm.</span></span>

<span data-ttu-id="ff4b2-295">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).</span><span class="sxs-lookup"><span data-stu-id="ff4b2-295">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ff4b2-296">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="ff4b2-296">Next steps</span></span>

<span data-ttu-id="ff4b2-297">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="ff4b2-297">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="ff4b2-298">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="ff4b2-298">Create a console application</span></span>
> - <span data-ttu-id="ff4b2-299">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="ff4b2-299">Prepare data</span></span>
> - <span data-ttu-id="ff4b2-300">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="ff4b2-300">Load the data</span></span>
> - <span data-ttu-id="ff4b2-301">Creación y entrenamiento del modelo</span><span class="sxs-lookup"><span data-stu-id="ff4b2-301">Build and train the model</span></span>
> - <span data-ttu-id="ff4b2-302">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="ff4b2-302">Evaluate the model</span></span>
> - <span data-ttu-id="ff4b2-303">Uso del modelo para realizar una predicción</span><span class="sxs-lookup"><span data-stu-id="ff4b2-303">Use the model to make a prediction</span></span>
> - <span data-ttu-id="ff4b2-304">Ver los resultados</span><span class="sxs-lookup"><span data-stu-id="ff4b2-304">See the results</span></span>

<span data-ttu-id="ff4b2-305">Siga con el siguiente tutorial para obtener más información</span><span class="sxs-lookup"><span data-stu-id="ff4b2-305">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="ff4b2-306">Clasificación de problemas</span><span class="sxs-lookup"><span data-stu-id="ff4b2-306">Issue Classification</span></span>](github-issue-classification.md)
