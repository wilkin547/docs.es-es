---
title: Tutorial de análisis de sentimiento con .NET para Apache Spark y ML.NET
description: En este tutorial, aprenderá a usar ML.NET con .NET para Apache Spark con fin de realizar análisis de sentimiento.
author: mamccrea
ms.author: mamccrea
ms.date: 10/09/2020
ms.topic: tutorial
ms.openlocfilehash: 1c2c966a4ff50a9d2f6951e20d909c5c20c75bfb
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688246"
---
# <a name="tutorial-sentiment-analysis-with-net-for-apache-spark-and-mlnet"></a><span data-ttu-id="e92d0-103">Tutorial: Análisis de sentimiento con .NET para Apache Spark y ML.NET</span><span class="sxs-lookup"><span data-stu-id="e92d0-103">Tutorial: Sentiment analysis with .NET for Apache Spark and ML.NET</span></span>

<span data-ttu-id="e92d0-104">En este tutorial aprenderá a realizar análisis de sentimiento de las reseñas en línea con ML.NET y .NET para Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="e92d0-104">This tutorial teaches you how to do sentiment analysis of online reviews using ML.NET and .NET for Apache Spark.</span></span> <span data-ttu-id="e92d0-105">[ML.NET](http://dot.net/ml) es un marco de aprendizaje automático gratuito multiplataforma y de código abierto.</span><span class="sxs-lookup"><span data-stu-id="e92d0-105">[ML.NET](http://dot.net/ml) is a free, cross-platform, open-source machine learning framework.</span></span> <span data-ttu-id="e92d0-106">Puede usar ML.NET con .NET para Apache Spark para escalar el entrenamiento y la predicción de los algoritmos de aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="e92d0-106">You can use ML.NET with .NET for Apache Spark to scale the training and prediction of machine learning algorithms.</span></span>

<span data-ttu-id="e92d0-107">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="e92d0-107">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="e92d0-108">Crear un modelo de análisis de sentimiento mediante la herramienta Model Builder de ML.NET disponible en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e92d0-108">Create a sentiment analysis model using ML.NET Model Builder in Visual Studio.</span></span>
> * <span data-ttu-id="e92d0-109">Crear una aplicación de consola de .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="e92d0-109">Create a .NET for Apache Spark console app.</span></span>
> * <span data-ttu-id="e92d0-110">Escribir e implementar una función definida por el usuario</span><span class="sxs-lookup"><span data-stu-id="e92d0-110">Write and implement a user-defined function.</span></span>
> * <span data-ttu-id="e92d0-111">Ejecutar una aplicación de consola de .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="e92d0-111">Run a .NET for Apache Spark console app.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e92d0-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="e92d0-112">Prerequisites</span></span>

* <span data-ttu-id="e92d0-113">Si nunca ha desarrollado una aplicación de .NET para Apache Spark, comience con el [tutorial de introducción](get-started.md) para familiarizarse con los aspectos básicos.</span><span class="sxs-lookup"><span data-stu-id="e92d0-113">If you haven't developed a .NET for Apache Spark application before, start with the [Getting Started tutorial](get-started.md) to become familiar with the basics.</span></span> <span data-ttu-id="e92d0-114">Complete todos los requisitos previos del tutorial de introducción antes de continuar con este tutorial.</span><span class="sxs-lookup"><span data-stu-id="e92d0-114">Complete all of the prerequisites for the Getting Started tutorial before you continue with this tutorial.</span></span>

* <span data-ttu-id="e92d0-115">En este tutorial se usa la herramienta Model Builder de ML.NET (versión preliminar), una interfaz visual que está disponible en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e92d0-115">This tutorial uses the ML.NET Model Builder (preview), a visual interface available in Visual Studio.</span></span> <span data-ttu-id="e92d0-116">Si aún no tiene Visual Studio, puede [descargar la versión Community de Visual Studio](https://visualstudio.microsoft.com/downloads/) de forma gratuita.</span><span class="sxs-lookup"><span data-stu-id="e92d0-116">If you don't already have Visual Studio, you can [download the Community version of Visual Studio](https://visualstudio.microsoft.com/downloads/) for free.</span></span>

* <span data-ttu-id="e92d0-117">[Descargue e instale](https://marketplace.visualstudio.com/items?itemName=MLNET.07) la herramienta Model Builder de ML.NET (versión preliminar).</span><span class="sxs-lookup"><span data-stu-id="e92d0-117">[Download and install](https://marketplace.visualstudio.com/items?itemName=MLNET.07) ML.NET Model Builder (preview).</span></span>

* <span data-ttu-id="e92d0-118">Descargue los conjuntos de datos de reseñas de Yelp [yelptest. csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptest.csv) y [yelptrain.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptrain.csv).</span><span class="sxs-lookup"><span data-stu-id="e92d0-118">Download the [yelptest.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptest.csv) and [yelptrain.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptrain.csv) Yelp review datasets.</span></span>

## <a name="review-the-data"></a><span data-ttu-id="e92d0-119">Revisión de los datos</span><span class="sxs-lookup"><span data-stu-id="e92d0-119">Review the data</span></span>

<span data-ttu-id="e92d0-120">El conjunto de datos de reseñas de Yelp contiene reseñás en línea de Yelp sobre varios servicios.</span><span class="sxs-lookup"><span data-stu-id="e92d0-120">The Yelp reviews dataset contains online Yelp reviews about various services.</span></span> <span data-ttu-id="e92d0-121">Abra [yelptrain.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptrain.csv) y observe la estructura de los datos.</span><span class="sxs-lookup"><span data-stu-id="e92d0-121">Open [yelptrain.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptrain.csv) and notice the structure of the data.</span></span> <span data-ttu-id="e92d0-122">La primera columna contiene el texto de la reseña, y la segunda, puntuaciones de opinión.</span><span class="sxs-lookup"><span data-stu-id="e92d0-122">The first column contains review text, and the second column contains sentiment scores.</span></span> <span data-ttu-id="e92d0-123">Si la puntuación de opinión es 1, la reseña es positiva y, si es 0, la reseña es negativa.</span><span class="sxs-lookup"><span data-stu-id="e92d0-123">If the sentiment score is 1, the review is positive, and if the sentiment score is 0, the review is negative.</span></span>

<span data-ttu-id="e92d0-124">La siguiente tabla contiene datos de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e92d0-124">The following table contains sample data:</span></span>

|<span data-ttu-id="e92d0-125">ReviewText</span><span class="sxs-lookup"><span data-stu-id="e92d0-125">ReviewText</span></span>|<span data-ttu-id="e92d0-126">Opinión</span><span class="sxs-lookup"><span data-stu-id="e92d0-126">Sentiment</span></span>|
|-|-|
|<span data-ttu-id="e92d0-127">¡Ah! Me encantó el lugar.</span><span class="sxs-lookup"><span data-stu-id="e92d0-127">Wow... Loved this place.</span></span>|    <span data-ttu-id="e92d0-128">1</span><span class="sxs-lookup"><span data-stu-id="e92d0-128">1</span></span>|
|<span data-ttu-id="e92d0-129">La corteza no es buena.</span><span class="sxs-lookup"><span data-stu-id="e92d0-129">Crust is not good.</span></span>|    <span data-ttu-id="e92d0-130">0</span><span class="sxs-lookup"><span data-stu-id="e92d0-130">0</span></span>|

## <a name="build-your-machine-learning-model"></a><span data-ttu-id="e92d0-131">Compilación de un modelo de Machine Learning propio</span><span class="sxs-lookup"><span data-stu-id="e92d0-131">Build your machine learning model</span></span>

1. <span data-ttu-id="e92d0-132">Abra Visual Studio y cree una aplicación de consola C# (.NET Core).</span><span class="sxs-lookup"><span data-stu-id="e92d0-132">Open Visual Studio and create a new C# Console App (.NET Core).</span></span> <span data-ttu-id="e92d0-133">Asigne al proyecto el nombre *MLSparkModel*.</span><span class="sxs-lookup"><span data-stu-id="e92d0-133">Name the project *MLSparkModel*.</span></span>

1. <span data-ttu-id="e92d0-134">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto *MLSparkModel*.</span><span class="sxs-lookup"><span data-stu-id="e92d0-134">In **Solution Explorer**, right-click the *MLSparkModel* project.</span></span> <span data-ttu-id="e92d0-135">A continuación, seleccione **Agregar > Machine Learning**.</span><span class="sxs-lookup"><span data-stu-id="e92d0-135">Then select **Add > Machine Learning**.</span></span>

1. <span data-ttu-id="e92d0-136">En la herramienta Model Builder de ML.NET, seleccione el icono de escenario **Sentiment Analysis** (Análisis de sentimiento).</span><span class="sxs-lookup"><span data-stu-id="e92d0-136">From the ML.NET Model Builder, select the **Sentiment Analysis** scenario tile.</span></span>

1. <span data-ttu-id="e92d0-137">En la página **Add data** (Agregar datos), cargue el conjunto de datos *yelptrain.csv*.</span><span class="sxs-lookup"><span data-stu-id="e92d0-137">On the **Add data** page, upload the *yelptrain.csv* data set.</span></span>

1. <span data-ttu-id="e92d0-138">Elija *Sentiment* (Sentimiento) en la lista desplegable **Columns to Predict** (Columnas para predecir).</span><span class="sxs-lookup"><span data-stu-id="e92d0-138">Choose *Sentiment* from the **Columns to Predict** dropdown.</span></span>

1. <span data-ttu-id="e92d0-139">En la página **Train** (Entrenar), establezca la hora de entrenamiento en *60 segundos* y seleccione **Start training** (Iniciar entrenamiento).</span><span class="sxs-lookup"><span data-stu-id="e92d0-139">On the **Train** page, set the time to train to *60 seconds* and select **Start training**.</span></span> <span data-ttu-id="e92d0-140">Observe el estado del entrenamiento en **Progress** (Progreso).</span><span class="sxs-lookup"><span data-stu-id="e92d0-140">Notice the status of your training under **Progress**.</span></span>

1. <span data-ttu-id="e92d0-141">Una vez que Model Builder finaliza el entrenamiento, **evalúe** los resultados del entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="e92d0-141">Once Model Builder is finished training, **Evaluate** the training results.</span></span> <span data-ttu-id="e92d0-142">Puede escribir frases en el cuadro de texto que aparece a continuación **Try your model** (Probar el modelo) y seleccionar **Predict** (Predecir) para ver el resultado.</span><span class="sxs-lookup"><span data-stu-id="e92d0-142">You can type phrases into the text box below **Try your model** and select **Predict** to see the output.</span></span>

1. <span data-ttu-id="e92d0-143">Seleccione **Code** (Código) y, a continuación, seleccione **Add Projects** (Agregar proyectos) para agregar el modelo de aprendizaje automático a la solución.</span><span class="sxs-lookup"><span data-stu-id="e92d0-143">Select **Code** and then select **Add Projects** to add the ML model to the solution.</span></span>

1. <span data-ttu-id="e92d0-144">Tenga en cuenta que se agregan dos proyectos a las soluciones: **MLSparkModelML.ConsoleApp** y **MLSparkModelML.Model**.</span><span class="sxs-lookup"><span data-stu-id="e92d0-144">Notice that two projects are added to your solutions: **MLSparkModelML.ConsoleApp** and **MLSparkModelML.Model**.</span></span>

1. <span data-ttu-id="e92d0-145">Haga doble clic en el proyecto *MLSpark* de C# y observe que se ha agregado la siguiente referencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="e92d0-145">Double-click on your *MLSpark* C# project and notice that the following project reference has been added.</span></span>

   ```xml
   <ItemGroup>
       <ProjectReference Include="..\MLSparkModelML.Model\MLSparkModelML.Model.csproj" />
   </ItemGroup>
   ```

## <a name="create-a-console-app"></a><span data-ttu-id="e92d0-146">Crear una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="e92d0-146">Create a console app</span></span>

<span data-ttu-id="e92d0-147">Model Builder crea una aplicación de consola automáticamente.</span><span class="sxs-lookup"><span data-stu-id="e92d0-147">Model Builder creates a console app for you.</span></span>

1. <span data-ttu-id="e92d0-148">Haga clic con el botón derecho en **MLSparkModelML.Console** en el Explorador de soluciones y seleccione **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="e92d0-148">Right-click on **MLSparkModelML.Console** in Solution Explorer, and select **Manage NuGet Packages**.</span></span>

1. <span data-ttu-id="e92d0-149">Busque **Microsoft.Spark** e instale el paquete.</span><span class="sxs-lookup"><span data-stu-id="e92d0-149">Search for **Microsoft.Spark** and install the package.</span></span> <span data-ttu-id="e92d0-150">Model Builder instala automáticamente **Microsoft.ML**.</span><span class="sxs-lookup"><span data-stu-id="e92d0-150">**Microsoft.ML** is automatically installed for you by Model Builder.</span></span>

### <a name="create-a-sparksession"></a><span data-ttu-id="e92d0-151">Creación de una SparkSession</span><span class="sxs-lookup"><span data-stu-id="e92d0-151">Create a SparkSession</span></span>

1. <span data-ttu-id="e92d0-152">Abra el archivo *Program.cs* de **MLSparkModelML.ConsoleApp**.</span><span class="sxs-lookup"><span data-stu-id="e92d0-152">Open the *Program.cs* file for **MLSparkModelML.ConsoleApp**.</span></span> <span data-ttu-id="e92d0-153">Model Builder generó automáticamente ese archivo.</span><span class="sxs-lookup"><span data-stu-id="e92d0-153">This file was autogenerated by Model Builder.</span></span> <span data-ttu-id="e92d0-154">Elimine las instrucciones `using`, el contenido del método Main() y la región `CreateSingleDataSample`.</span><span class="sxs-lookup"><span data-stu-id="e92d0-154">Delete the `using` statements, the contents of the Main() method, and the `CreateSingleDataSample` region.</span></span>

1. <span data-ttu-id="e92d0-155">Agregue las siguientes instrucciones `using` adicionales a la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="e92d0-155">Add the following additional `using` statements to the top of the *Program.cs*:</span></span>

   ```csharp
   using System;
   using System.Collections.Generic;
   using Microsoft.ML;
   using Microsoft.ML.Data;
   using Microsoft.Spark.Sql;
   using MLSparkModelML.Model;
   ```

1. <span data-ttu-id="e92d0-156">Cambie `DATA_FILEPATH` a la ruta de acceso de *yelptest.csv*.</span><span class="sxs-lookup"><span data-stu-id="e92d0-156">Change the `DATA_FILEPATH` to the path of your *yelptest.csv*.</span></span>

1. <span data-ttu-id="e92d0-157">Agregue el código siguiente al método `Main` para crear una nueva `SparkSession`.</span><span class="sxs-lookup"><span data-stu-id="e92d0-157">Add the following code to your `Main` method to create a new `SparkSession`.</span></span> <span data-ttu-id="e92d0-158">La sesión de Spark es el punto de entrada para programar Spark con la API de DataFrame y DataSet.</span><span class="sxs-lookup"><span data-stu-id="e92d0-158">The Spark Session is the entry point to programming Spark with the Dataset and DataFrame API.</span></span>

   ```csharp
   SparkSession spark = SparkSession
        .Builder()
        .AppName(".NET for Apache Spark Sentiment Analysis")
        .GetOrCreate();
   ```

   <span data-ttu-id="e92d0-159">Llamar al objeto *spark* creado anteriormente le permite tener acceso a la funcionalidad de DataFrame y Spark a través del programa.</span><span class="sxs-lookup"><span data-stu-id="e92d0-159">Calling the *spark* object created above allows you to access Spark and DataFrame functionality throughout your program.</span></span>

### <a name="create-a-dataframe-and-print-to-console"></a><span data-ttu-id="e92d0-160">Creación de un objeto DataFrame e impresión en la consola</span><span class="sxs-lookup"><span data-stu-id="e92d0-160">Create a DataFrame and print to console</span></span>

<span data-ttu-id="e92d0-161">Lea los datos de reseñas de Yelp del archivo *yelptest.csv* como `DataFrame`.</span><span class="sxs-lookup"><span data-stu-id="e92d0-161">Read in the Yelp review data from the *yelptest.csv* file as a `DataFrame`.</span></span> <span data-ttu-id="e92d0-162">Incluya las opciones `header` y `inferSchema`.</span><span class="sxs-lookup"><span data-stu-id="e92d0-162">Include `header` and `inferSchema` options.</span></span> <span data-ttu-id="e92d0-163">La opción `header` lee la primera línea de *yelptest.csv* como nombres de columna en lugar de como datos.</span><span class="sxs-lookup"><span data-stu-id="e92d0-163">The `header` option reads the first line of *yelptest.csv* as column names instead of data.</span></span> <span data-ttu-id="e92d0-164">La opción `inferSchema` deduce los tipos de columna en función de los datos.</span><span class="sxs-lookup"><span data-stu-id="e92d0-164">The `inferSchema` option infers column types based on the data.</span></span>

```csharp
DataFrame df = spark
    .ReadStream()
    .Option("header", true)
    .Option("inferSchema", true)
    .Csv(DATA_FILEPATH);

df.Show();
```

### <a name="register-a-user-defined-function"></a><span data-ttu-id="e92d0-165">Registro de una función definida por el usuario</span><span class="sxs-lookup"><span data-stu-id="e92d0-165">Register a user-defined function</span></span>

<span data-ttu-id="e92d0-166">Puede usar UDF, *funciones definidas por el usuario*, en aplicaciones Spark para realizar cálculos y análisis de los datos.</span><span class="sxs-lookup"><span data-stu-id="e92d0-166">You can use UDFs, *user-defined functions*, in Spark applications to do calculations and analysis on your data.</span></span> <span data-ttu-id="e92d0-167">En este tutorial, usará ML.NET con UDF para evaluar cada reseña de Yelp.</span><span class="sxs-lookup"><span data-stu-id="e92d0-167">In this tutorial, you use ML.NET with a UDF to evaluate each Yelp review.</span></span>

<span data-ttu-id="e92d0-168">Agregue el siguiente código a su método `Main` para registrar una UDF llamada `MLudf`.</span><span class="sxs-lookup"><span data-stu-id="e92d0-168">Add the following code to your `Main` method to register a UDF called `MLudf`.</span></span>

```csharp
spark.Udf()
    .Register<string, bool>("MLudf", predict);
```

<span data-ttu-id="e92d0-169">Esta función UDF toma una cadena de reseña de Yelp como entrada y genera valores "true" o "false" para las opiniones positivas o negativas, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="e92d0-169">This UDF takes a Yelp review string as input, and outputs true or false for positive or negative sentiments, respectively.</span></span> <span data-ttu-id="e92d0-170">Usa el método *predict()* que se define en un paso posterior.</span><span class="sxs-lookup"><span data-stu-id="e92d0-170">It uses the *predict()* method that you define in a later step.</span></span>

### <a name="use-spark-sql-to-call-the-udf"></a><span data-ttu-id="e92d0-171">Uso de Spark SQL para llamar a la función UDF</span><span class="sxs-lookup"><span data-stu-id="e92d0-171">Use Spark SQL to call the UDF</span></span>

<span data-ttu-id="e92d0-172">Ahora que ha leído los datos y ha incorporado el aprendizaje automático, use Spark SQL para llamar a la función UDF que ejecutará el análisis de sentimiento en cada fila del objeto DataFrame.</span><span class="sxs-lookup"><span data-stu-id="e92d0-172">Now that you've read in your data and incorporated ML, use Spark SQL to call the UDF that will run sentiment analysis on each row of your DataFrame.</span></span> <span data-ttu-id="e92d0-173">Agregue el código siguiente al método `Main`:</span><span class="sxs-lookup"><span data-stu-id="e92d0-173">Add the following code to your `Main` method:</span></span>

```csharp
// Use Spark SQL to call ML.NET UDF
// Display results of sentiment analysis on reviews
df.CreateOrReplaceTempView("Reviews");
DataFrame sqlDf = spark.Sql("SELECT ReviewText, MLudf(ReviewText) FROM Reviews");
sqlDf.Show();

// Print out first 20 rows of data
// Prevent data getting cut off by setting truncate = 0
sqlDf.Show(20, 0, false);

spark.Stop();
```

### <a name="create-predict-method"></a><span data-ttu-id="e92d0-174">Creación del método predict()</span><span class="sxs-lookup"><span data-stu-id="e92d0-174">Create predict() method</span></span>

<span data-ttu-id="e92d0-175">Agregue el código siguiente al método `Main()`.</span><span class="sxs-lookup"><span data-stu-id="e92d0-175">Add the following code before your `Main()` method.</span></span> <span data-ttu-id="e92d0-176">Este código es similar al que genera Model Builder en *ConsumeModel.cs*.</span><span class="sxs-lookup"><span data-stu-id="e92d0-176">This code is similar to what is produced by Model Builder in *ConsumeModel.cs*.</span></span> <span data-ttu-id="e92d0-177">Al mover este método a la consola, se carga el modelo cada vez que se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e92d0-177">Moving this method to your console loads the model loading each time you run your app.</span></span>

```csharp
private static readonly PredictionEngine<ModelInput, ModelOutput> _predictionEngine;

static Program()
{
    MLContext mlContext = new MLContext();
    ITransformer model = mlContext.Model.Load("MLModel.zip", out DataViewSchema schema);
    _predictionEngine = mlContext.Model.CreatePredictionEngine<ModelInput, ModelOutput>(model);
}

static bool predict(string text)
{
    ModelInput input = new ModelInput
    {
        ReviewText = text
    };

    return _predictionEngine.Predict(input).Prediction;
}
```

## <a name="add-the-model-to-your-console-app"></a><span data-ttu-id="e92d0-178">Incorporación del modelo a la aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="e92d0-178">Add the model to your console app</span></span>

<span data-ttu-id="e92d0-179">En el Explorador de soluciones, copie el archivo *MLModel.zip* del proyecto **MLSparkModelML.Model** y péguelo en el proyecto **MLSparkModelML.ConsoleApp**.</span><span class="sxs-lookup"><span data-stu-id="e92d0-179">In Solution Explorer, copy the *MLModel.zip* file from the **MLSparkModelML.Model** project and paste it in the **MLSparkModelML.ConsoleApp** project.</span></span> <span data-ttu-id="e92d0-180">Se agrega automáticamente una referencia en *MLSparkModelML.ConsoleApp. csproj*.</span><span class="sxs-lookup"><span data-stu-id="e92d0-180">A reference is automatically added in *MLSparkModelML.ConsoleApp.csproj*.</span></span>

## <a name="run-your-code"></a><span data-ttu-id="e92d0-181">Ejecución del código</span><span class="sxs-lookup"><span data-stu-id="e92d0-181">Run your code</span></span>

<span data-ttu-id="e92d0-182">Use `spark-submit` para ejecutar el código.</span><span class="sxs-lookup"><span data-stu-id="e92d0-182">Use `spark-submit` to run your code.</span></span> <span data-ttu-id="e92d0-183">Vaya a la carpeta raíz de la aplicación de consola mediante el símbolo del sistema y ejecute los siguientes comandos.</span><span class="sxs-lookup"><span data-stu-id="e92d0-183">Navigate to your console app's root folder using the command prompt and run the following commands.</span></span>

<span data-ttu-id="e92d0-184">En primer lugar, limpie y publique la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e92d0-184">First, clean and publish your app.</span></span>

```dotnetcli
dotnet clean
dotnet publish
```

<span data-ttu-id="e92d0-185">Después, vaya a la carpeta de publicación de la aplicación de consola y ejecute el siguiente comando: `spark-submit`.</span><span class="sxs-lookup"><span data-stu-id="e92d0-185">Then navigate to the console app's publish folder and run the following `spark-submit` command.</span></span> <span data-ttu-id="e92d0-186">Asegúrese de actualizar el comando anterior con la ruta de acceso real al archivo .jar de Microsoft Spark.</span><span class="sxs-lookup"><span data-stu-id="e92d0-186">Remember to update the command with the actual path of your Microsoft Spark jar file.</span></span>

```dotnetcli
%SPARK_HOME%\bin\spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local microsoft-spark-2-4_2.11-1.0.0.jar dotnet MLSparkModelML.ConsoleApp.dll
```

## <a name="get-the-code"></a><span data-ttu-id="e92d0-187">Obtención del código</span><span class="sxs-lookup"><span data-stu-id="e92d0-187">Get the code</span></span>

<span data-ttu-id="e92d0-188">Este tutorial es similar al código del ejemplo del [análisis de sentimiento con macrodatos](https://github.com/dotnet/spark/tree/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment).</span><span class="sxs-lookup"><span data-stu-id="e92d0-188">This tutorial is similar to the code from the [Sentiment Analysis with Big Data](https://github.com/dotnet/spark/tree/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment) example.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e92d0-189">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="e92d0-189">Next steps</span></span>

<span data-ttu-id="e92d0-190">Avance al siguiente artículo para aprender a realizar flujos estructurados con .NET para Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="e92d0-190">Advance to the next article to learn how to do Structured Streaming with .NET for Apache Spark.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="e92d0-191">Tutorial: Streaming estructurado con .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="e92d0-191">Tutorial: Structured Streaming with .NET for Apache Spark</span></span>](streaming.md)
