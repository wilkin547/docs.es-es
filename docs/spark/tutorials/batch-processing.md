---
title: Tutorial de procesamiento por lotes con .NET para Apache Spark
description: Aprenda a realizar el procesamiento por lotes con .NET para Apache Spark.
author: mamccrea
ms.author: mamccrea
ms.date: 12/13/2019
ms.topic: tutorial
ms.openlocfilehash: 460c37e66c2c0a8a9b197a9abaff9eead842bdeb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "79187552"
---
# <a name="tutorial-do-batch-processing-with-net-for-apache-spark"></a><span data-ttu-id="a6358-103">Tutorial: Procesamiento por lotes con .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="a6358-103">Tutorial: Do batch processing with .NET for Apache Spark</span></span>

<span data-ttu-id="a6358-104">En este tutorial, aprenderá a realizar el procesamiento por lotes con .NET para Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="a6358-104">In this tutorial, you learn how to do batch processing using .NET for Apache Spark.</span></span> <span data-ttu-id="a6358-105">El procesamiento por lotes es la transformación de datos en reposo, lo que significa que los datos de origen ya se han cargado en el almacenamiento de datos.</span><span class="sxs-lookup"><span data-stu-id="a6358-105">Batch processing is the transformation of data at rest, meaning that the source data has already been loaded into data storage.</span></span>

<span data-ttu-id="a6358-106">El procesamiento por lotes se realiza normalmente sobre grandes conjuntos de valores planos que se deben preparar para su posterior análisis.</span><span class="sxs-lookup"><span data-stu-id="a6358-106">Batch processing is generally performed over large, flat datasets that need to be prepared for further analysis.</span></span> <span data-ttu-id="a6358-107">El procesamiento de registros y el almacenamiento de datos son escenarios comunes de procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="a6358-107">Log processing and data warehousing are common batch processing scenarios.</span></span> <span data-ttu-id="a6358-108">En este escenario, se analiza la información sobre los proyectos de GitHub, como el número de veces que se han bifurcado proyectos diferentes o cómo de recientemente se han actualización los proyectos.</span><span class="sxs-lookup"><span data-stu-id="a6358-108">In this scenario, you analyze information about GitHub projects, such as the number of time different projects have been forked or how recently projects have been updated.</span></span>

<span data-ttu-id="a6358-109">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="a6358-109">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="a6358-110">Crear y ejecutar una aplicación de .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="a6358-110">Create and run a .NET for Apache Spark application</span></span>
> * <span data-ttu-id="a6358-111">Leer datos en DataFrame y prepararlos para su análisis</span><span class="sxs-lookup"><span data-stu-id="a6358-111">Read data into a DataFrame and prepare it for analysis</span></span>
> * <span data-ttu-id="a6358-112">Procesar los datos mediante Spark SQL</span><span class="sxs-lookup"><span data-stu-id="a6358-112">Process the data using Spark SQL</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a6358-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a6358-113">Prerequisites</span></span>

<span data-ttu-id="a6358-114">Si esta es la primera vez que usa .NET para Apache Spark, consulte el tutorial [Introducción a .NET para Apache Spark](../tutorials/get-started.md) para aprender a preparar el entorno y ejecutar la primera aplicación .NET para Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="a6358-114">If this is your first time using .NET for Apache Spark, check out the [Get started with .NET for Apache Spark](../tutorials/get-started.md) tutorial to learn how to prepare your environment and run your first .NET for Apache Spark application.</span></span>

## <a name="download-the-sample-data"></a><span data-ttu-id="a6358-115">Descarga de los datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="a6358-115">Download the sample data</span></span>

<span data-ttu-id="a6358-116">[GHTorrent](http://ghtorrent.org/) supervisa todos los eventos públicos de GitHub, como información sobre los proyectos, confirmaciones y monitores, y almacena los eventos y su estructura en bases de datos.</span><span class="sxs-lookup"><span data-stu-id="a6358-116">[GHTorrent](http://ghtorrent.org/) monitors all public GitHub events, such as info about projects, commits, and watchers, and stores the events and their structure in databases.</span></span> <span data-ttu-id="a6358-117">Los datos recopilados en distintos períodos de tiempo están disponibles como archivos descargables.</span><span class="sxs-lookup"><span data-stu-id="a6358-117">Data collected over different time periods is available as downloadable archives.</span></span> <span data-ttu-id="a6358-118">Dado que los archivos de volcado de memoria son muy grandes, en esta guía se usa una [versión truncada del archivo de volcado](https://github.com/dotnet/spark/tree/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/projects_smaller.csv) que se puede descargar desde GitHub.</span><span class="sxs-lookup"><span data-stu-id="a6358-118">Because the dump files are very large, this guide uses a [truncated version of the dump file](https://github.com/dotnet/spark/tree/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/projects_smaller.csv) that can be downloaded from GitHub.</span></span>

> [!NOTE]
> <span data-ttu-id="a6358-119">El conjunto de datos de GHTorrent se distribuye con un esquema de licencia dual ([Creative Commons +](https://wiki.creativecommons.org/wiki/CCPlus)).</span><span class="sxs-lookup"><span data-stu-id="a6358-119">The GHTorrent dataset is distributed under a dual licensing scheme ([Creative Commons +](https://wiki.creativecommons.org/wiki/CCPlus)).</span></span> <span data-ttu-id="a6358-120">En el caso de usos no comerciales (por ejemplo, para educación, investigación o personales), el conjunto de datos se distribuye con la [licencia CC-BY-SA](https://creativecommons.org/licenses/by-sa/4.0/).</span><span class="sxs-lookup"><span data-stu-id="a6358-120">For non-commercial uses (including, but not limited to, educational, research or personal uses), the dataset is distributed under the [CC-BY-SA license](https://creativecommons.org/licenses/by-sa/4.0/).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="a6358-121">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="a6358-121">Create a console application</span></span>

1. <span data-ttu-id="a6358-122">En el símbolo del sistema, ejecute los comandos siguientes para crear una aplicación de consola:</span><span class="sxs-lookup"><span data-stu-id="a6358-122">In your command prompt, run the following commands to create a new console application:</span></span>

   ```dotnetcli
   dotnet new console -o mySparkBatchApp
   cd mySparkBatchApp
   ```

   <span data-ttu-id="a6358-123">El comando `dotnet` crea una aplicación `new` de tipo `console` de forma automática.</span><span class="sxs-lookup"><span data-stu-id="a6358-123">The `dotnet` command creates a `new` application of type `console` for you.</span></span> <span data-ttu-id="a6358-124">El parámetro `-o` crea un directorio llamado *mySparkBatchApp* donde se almacena la aplicación y lo rellena con los archivos necesarios.</span><span class="sxs-lookup"><span data-stu-id="a6358-124">The `-o` parameter creates a directory named *mySparkBatchApp* where your app is stored and populates it with the required files.</span></span> <span data-ttu-id="a6358-125">El comando `cd mySparkBatchApp` cambia el directorio al directorio de la aplicación que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="a6358-125">The `cd mySparkBatchApp` command changes the directory to the app directory you just created.</span></span>

1. <span data-ttu-id="a6358-126">Para usar .NET para Apache Spark en una aplicación, instale el paquete Microsoft.Spark.</span><span class="sxs-lookup"><span data-stu-id="a6358-126">To use .NET for Apache Spark in an app, install the Microsoft.Spark package.</span></span> <span data-ttu-id="a6358-127">En la consola, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a6358-127">In your console, run the following command:</span></span>

   ```dotnetcli
   dotnet add package Microsoft.Spark
   ```

## <a name="create-a-sparksession"></a><span data-ttu-id="a6358-128">Creación de una SparkSession</span><span class="sxs-lookup"><span data-stu-id="a6358-128">Create a SparkSession</span></span>

1. <span data-ttu-id="a6358-129">Agregue las siguientes instrucciones `using` adicionales a la parte superior del archivo *Program.cs* en *mySparkBatchApp*.</span><span class="sxs-lookup"><span data-stu-id="a6358-129">Add the following additional `using` statements to the top of the *Program.cs* file in *mySparkBatchApp*.</span></span>

   ```csharp
   using System;
   using Microsoft.Spark.Sql;
   using static Microsoft.Spark.Sql.Functions;
   ```

1. <span data-ttu-id="a6358-130">Agregue el código siguiente al espacio de nombres del proyecto.</span><span class="sxs-lookup"><span data-stu-id="a6358-130">Add the following code to your project namespace.</span></span> <span data-ttu-id="a6358-131">*s_referenceData* se usa más adelante en el programa para filtrar por la fecha.</span><span class="sxs-lookup"><span data-stu-id="a6358-131">*s_referenceData* is used later in the program to filter based on date.</span></span>

   ```csharp
   static readonly DateTime s_referenceDate = new DateTime(2015, 10, 20);
   ```

1. <span data-ttu-id="a6358-132">Agregue el código siguiente dentro del método Main para establecer un nuevo objeto SparkSession.</span><span class="sxs-lookup"><span data-stu-id="a6358-132">Add the following code inside your Main method to establish a new SparkSession.</span></span> <span data-ttu-id="a6358-133">SparkSession es el punto de entrada para programar Spark con la API DataFrame y DataSet.</span><span class="sxs-lookup"><span data-stu-id="a6358-133">The SparkSession is the entry point to programming Spark with the Dataset and DataFrame API.</span></span> <span data-ttu-id="a6358-134">Al llamar al objeto `spark`, puede acceder a la funcionalidad de Spark y DataFrame en todo el programa.</span><span class="sxs-lookup"><span data-stu-id="a6358-134">By calling the `spark` object, you can access Spark and DataFrame functionality throughout your program.</span></span>

   ```csharp
   SparkSession spark = SparkSession
        .Builder()
        .AppName("GitHub and Spark Batch")
        .GetOrCreate();
   ```

## <a name="prepare-the-data"></a><span data-ttu-id="a6358-135">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="a6358-135">Prepare the data</span></span>

1. <span data-ttu-id="a6358-136">Lea el archivo de entrada en un objeto `DataFrame`, que es una recopilación distribuida de datos organizados en columnas con nombre.</span><span class="sxs-lookup"><span data-stu-id="a6358-136">Read the input file into a `DataFrame`, which is a distributed collection of data organized into named columns.</span></span> <span data-ttu-id="a6358-137">Puede establecer las columnas para los datos mediante <xref:Microsoft.Spark.Sql.DataFrame.Schema%2A>.</span><span class="sxs-lookup"><span data-stu-id="a6358-137">You can set the columns for your data through <xref:Microsoft.Spark.Sql.DataFrame.Schema%2A>.</span></span> <span data-ttu-id="a6358-138">Use el método <xref:Microsoft.Spark.Sql.DataFrame.Show%2A> para mostrar los datos en DataFrame.</span><span class="sxs-lookup"><span data-stu-id="a6358-138">Use the <xref:Microsoft.Spark.Sql.DataFrame.Show%2A> method to display the data in your DataFrame.</span></span> <span data-ttu-id="a6358-139">Asegúrese de actualizar la ruta de acceso del archivo CSV a la ubicación de los datos de GitHub que descargó.</span><span class="sxs-lookup"><span data-stu-id="a6358-139">Be sure to update the CSV file path to the location of the GitHub data you downloaded.</span></span>

   ```csharp
   DataFrame projectsDf = spark
       .Read()
       .Schema("id INT, url STRING, owner_id INT, " +
       "name STRING, descriptor STRING, language STRING, " +
       "created_at STRING, forked_from INT, deleted STRING" +
       "updated_at STRING")
       .Csv("filepath");

   projectsDf.Show();
   ```

1. <span data-ttu-id="a6358-140">Use el método <xref:Microsoft.Spark.Sql.DataFrame.Na%2A> para colocar filas con valores NA (NULL) y el método <xref:Microsoft.Spark.Sql.DataFrame.Drop%2A> para quitar ciertas columnas de los datos.</span><span class="sxs-lookup"><span data-stu-id="a6358-140">Use the <xref:Microsoft.Spark.Sql.DataFrame.Na%2A> method to drop rows with NA (null) values, and the <xref:Microsoft.Spark.Sql.DataFrame.Drop%2A> method to remove certain columns from your data.</span></span> <span data-ttu-id="a6358-141">Esto ayuda a evitar errores si intenta analizar datos nulos o columnas que no son de interés para el análisis final.</span><span class="sxs-lookup"><span data-stu-id="a6358-141">This helps prevent errors if you try to analyze null data or columns that are not relevant to your final analysis.</span></span>

   ```csharp
   // Drop any rows with NA values
   DataFrameNaFunctions dropEmptyProjects = projectsDf.Na();
   DataFrame cleanedProjects = dropEmptyProjects.Drop("any");

   // Remove unnecessary columns
   cleanedProjects = cleanedProjects.Drop("id", "url", "owner_id");
   cleanedProjects.Show();
   ```

## <a name="analyze-the-data"></a><span data-ttu-id="a6358-142">Análisis de los datos</span><span class="sxs-lookup"><span data-stu-id="a6358-142">Analyze the data</span></span>

<span data-ttu-id="a6358-143">Spark SQL permite realizar llamadas SQL en los datos.</span><span class="sxs-lookup"><span data-stu-id="a6358-143">Spark SQL allows you to make SQL calls on your data.</span></span> <span data-ttu-id="a6358-144">Es habitual combinar funciones definidas por el usuario y Spark SQL para aplicar una función definida por el usuario a todas las filas de DataFrame.</span><span class="sxs-lookup"><span data-stu-id="a6358-144">It's common to combine user-defined functions and Spark SQL to apply a user-defined function to all rows of your DataFrame.</span></span>

<span data-ttu-id="a6358-145">Puede llamar específicamente a `spark.Sql` para imitar las llamadas SQL estándar que se observan en otros tipos de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a6358-145">You can specifically call `spark.Sql` to mimic standard SQL calls seen in other types of apps.</span></span> <span data-ttu-id="a6358-146">También puede llamar a métodos como <xref:Microsoft.Spark.Sql.DataFrame.GroupBy%2A> y <xref:Microsoft.Spark.Sql.DataFrame.Agg%2A> para combinar, filtrar y realizar cálculos en los datos de forma específica.</span><span class="sxs-lookup"><span data-stu-id="a6358-146">You can also call methods like <xref:Microsoft.Spark.Sql.DataFrame.GroupBy%2A> and <xref:Microsoft.Spark.Sql.DataFrame.Agg%2A> to specifically combine, filter, and perform calculations on your data.</span></span>

<span data-ttu-id="a6358-147">El objetivo de esta aplicación es obtener información detallada sobre los datos de los proyectos de GitHub.</span><span class="sxs-lookup"><span data-stu-id="a6358-147">The goal of this app is to gain some insights about the GitHub projects data.</span></span> <span data-ttu-id="a6358-148">Agregue los siguientes fragmentos de código al programa para analizar los datos.</span><span class="sxs-lookup"><span data-stu-id="a6358-148">Add the following code snippets to your program to analyze the data.</span></span>

1. <span data-ttu-id="a6358-149">Al agregar el siguiente bloque de código se busca el número de veces que se ha bifurcado cada idioma.</span><span class="sxs-lookup"><span data-stu-id="a6358-149">Add the following block of code finds the number of times each language has been forked.</span></span> <span data-ttu-id="a6358-150">En primer lugar, los datos se agrupan por idioma.</span><span class="sxs-lookup"><span data-stu-id="a6358-150">First, the data is grouped by language.</span></span> <span data-ttu-id="a6358-151">A continuación, se toma el número promedio de bifurcaciones de cada idioma.</span><span class="sxs-lookup"><span data-stu-id="a6358-151">Then, the average number of forks from each language is taken.</span></span>

   ```csharp
   // Average number of times each language has been forked
   DataFrame groupedDF = cleanedProjects
       .GroupBy("language")
       .Agg(Avg(cleanedProjects["forked_from"]);
   ```

1. <span data-ttu-id="a6358-152">Agregue el siguiente bloque de código para ordenar el promedio de bifurcaciones en orden descendente para ver los idiomas más bifurcados.</span><span class="sxs-lookup"><span data-stu-id="a6358-152">Add the following block of code to order the average number of forks in descending order to see which languages are the most forked.</span></span> <span data-ttu-id="a6358-153">Es decir, el mayor número de bifurcaciones aparecerá en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="a6358-153">That is, the largest number of forks will appear first.</span></span>

   ```csharp
   // Sort by most forked languages first
   groupedDF.OrderBy(Desc("avg(forked_from)")).Show();
   ```

1. <span data-ttu-id="a6358-154">El siguiente bloque de código muestra cómo de recientemente se han actualizado los proyectos.</span><span class="sxs-lookup"><span data-stu-id="a6358-154">The next block of code shows you how recently projects have been updated.</span></span> <span data-ttu-id="a6358-155">Registre una nueva función definida por el usuario llamada *MyUDF* y compárela con una fecha, *s_referenceDate*, que se declaró al principio del tutorial.</span><span class="sxs-lookup"><span data-stu-id="a6358-155">You register a new user-defined function called *MyUDF* and compare it with a date, *s_referenceDate*, which was declared at the beginning of the tutorial.</span></span> <span data-ttu-id="a6358-156">La fecha de cada proyecto se compara con la fecha de referencia.</span><span class="sxs-lookup"><span data-stu-id="a6358-156">The date for each project is compared against the reference date.</span></span> <span data-ttu-id="a6358-157">A continuación, Spark SQL se usa para llamar a la función definida por el usuario en cada fila de los datos para analizar cada proyecto del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="a6358-157">Then, Spark SQL is used to call the UDF on each row of the data to analyze each project in the data set.</span></span>

   ```csharp
   spark.Udf().Register<string, bool>(
       "MyUDF",
       (date) => DateTime.TryParse(date, out DateTime convertedDate) &&
           (convertedDate > s_referenceDate);
   cleanedProjects.CreateOrReplaceTempView("dateView");

   DataFrame dateDf = spark.Sql(
       "SELECT *, MyUDF(dateView.updated_at) AS datebefore FROM dateView");
   dateDf.Show();
   ```

1. <span data-ttu-id="a6358-158">Llame a `spark.Stop()` para finalizar el objeto SparkSession.</span><span class="sxs-lookup"><span data-stu-id="a6358-158">Call `spark.Stop()` to end the SparkSession.</span></span>

## <a name="use-spark-submit-to-run-your-app"></a><span data-ttu-id="a6358-159">Uso de spark-submit para ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="a6358-159">Use spark-submit to run your app</span></span>

1. <span data-ttu-id="a6358-160">Use el comando siguiente para compilar la aplicación .NET:</span><span class="sxs-lookup"><span data-stu-id="a6358-160">Use the following command to build your .NET app:</span></span>

   ```dotnetcli
   dotnet build
   ```

1. <span data-ttu-id="a6358-161">Ejecute la aplicación con `spark-submit`.</span><span class="sxs-lookup"><span data-stu-id="a6358-161">Run your app with `spark-submit`.</span></span> <span data-ttu-id="a6358-162">Asegúrese de actualizar el siguiente comando con las rutas de acceso reales a su archivo .jar de Microsoft Spark.</span><span class="sxs-lookup"><span data-stu-id="a6358-162">Be sure to update the following command with the actual paths to your Microsoft Spark jar file.</span></span>

   ```console
   spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local /<path>/to/microsoft-spark-<version>.jar dotnet /<path>/to/netcoreapp<version>/GitHubProjects.dll
   ```

## <a name="get-the-code"></a><span data-ttu-id="a6358-163">Obtención del código</span><span class="sxs-lookup"><span data-stu-id="a6358-163">Get the code</span></span>

<span data-ttu-id="a6358-164">Puede ver la [solución completa](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/GitHubProjects.cs) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="a6358-164">You can see the [full solution](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/GitHubProjects.cs) on GitHub.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a6358-165">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a6358-165">Next steps</span></span>

<span data-ttu-id="a6358-166">Avance al siguiente artículo para aprender a procesar datos de streaming con .NET para Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="a6358-166">Advance to the next article to learn how to process streaming data with .NET for Apache Spark.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="a6358-167">Tutorial: Streaming estructurado con .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="a6358-167">Tutorial: Structured Streaming with .NET for Apache Spark</span></span>](streaming.md)
