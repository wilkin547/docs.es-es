---
title: Tutorial Structured Streaming con .NET para Apache Spark
description: En este tutorial, aprenderá a usar .NET para Apache Spark para Spark Structured Streaming.
author: mamccrea
ms.author: mamccrea
ms.date: 12/04/2019
ms.topic: tutorial
ms.openlocfilehash: 125ef834da8e42c99c8080a3d5414a7927ce7636
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "79186511"
---
# <a name="tutorial-structured-streaming-with-net-for-apache-spark"></a><span data-ttu-id="2d29d-103">Tutorial: Structured Streaming con .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="2d29d-103">Tutorial: Structured Streaming with .NET for Apache Spark</span></span>

<span data-ttu-id="2d29d-104">En este tutorial aprenderá a invocar Spark Structured Streaming mediante .NET para Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="2d29d-104">This tutorial teaches you how to invoke Spark Structured Streaming using .NET for Apache Spark.</span></span> <span data-ttu-id="2d29d-105">Spark Structured Streaming es la compatibilidad de Apache Spark con el procesamiento de flujos de datos en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="2d29d-105">Spark Structured Streaming is Apache Spark's support for processing real-time data streams.</span></span> <span data-ttu-id="2d29d-106">El procesamiento de flujos se refiere a la realización de análisis de datos activos a medida que se producen.</span><span class="sxs-lookup"><span data-stu-id="2d29d-106">Stream processing means analyzing live data as it's being produced.</span></span>

<span data-ttu-id="2d29d-107">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="2d29d-107">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="2d29d-108">Crear y ejecutar una aplicación de .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="2d29d-108">Create and run a .NET for Apache Spark application</span></span>
> * <span data-ttu-id="2d29d-109">Usar netcat para crear un flujo de datos</span><span class="sxs-lookup"><span data-stu-id="2d29d-109">Use netcat to create a data stream</span></span>
> * <span data-ttu-id="2d29d-110">Usar funciones definidas por el usuario y SparkSQL para analizar datos de streaming</span><span class="sxs-lookup"><span data-stu-id="2d29d-110">Use user-defined functions and SparkSQL to analyze streaming data</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2d29d-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2d29d-111">Prerequisites</span></span>

<span data-ttu-id="2d29d-112">Si esta es su primera aplicación de .NET para Apache Spark, comience con el [tutorial de introducción](get-started.md) para familiarizarse con los aspectos básicos.</span><span class="sxs-lookup"><span data-stu-id="2d29d-112">If this is your first .NET for Apache Spark application, start with the [Getting Started tutorial](get-started.md) to become familiar with the basics.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="2d29d-113">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="2d29d-113">Create a console application</span></span>

1. <span data-ttu-id="2d29d-114">En el símbolo del sistema, ejecute los comandos siguientes para crear una aplicación de consola:</span><span class="sxs-lookup"><span data-stu-id="2d29d-114">In your command prompt, run the following commands to create a new console application:</span></span>

   ```dotnetcli
   dotnet new console -o mySparkStreamingApp
   cd mySparkStreamingApp
   ```

   <span data-ttu-id="2d29d-115">El comando `dotnet` crea una aplicación `new` de tipo `console` de forma automática.</span><span class="sxs-lookup"><span data-stu-id="2d29d-115">The `dotnet` command creates a `new` application of type `console` for you.</span></span> <span data-ttu-id="2d29d-116">El parámetro `-o` crea un directorio denominado *mySparkStreamingApp* donde se almacena la aplicación y lo rellena con los archivos necesarios.</span><span class="sxs-lookup"><span data-stu-id="2d29d-116">The `-o` parameter creates a directory named *mySparkStreamingApp* where your app is stored and populates it with the required files.</span></span> <span data-ttu-id="2d29d-117">El comando `cd mySparkStreamingApp` cambia el directorio al directorio de la aplicación que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="2d29d-117">The `cd mySparkStreamingApp` command changes the directory to the app directory you just created.</span></span>

1. <span data-ttu-id="2d29d-118">Para usar .NET para Apache Spark en una aplicación, instale el paquete Microsoft.Spark.</span><span class="sxs-lookup"><span data-stu-id="2d29d-118">To use .NET for Apache Spark in an app, install the Microsoft.Spark package.</span></span> <span data-ttu-id="2d29d-119">En la consola, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="2d29d-119">In your console, run the following command:</span></span>

   ```dotnetcli
   dotnet add package Microsoft.Spark
   ```

## <a name="establish-and-connect-to-a-data-stream"></a><span data-ttu-id="2d29d-120">Establecimiento y conexión a un flujo de datos</span><span class="sxs-lookup"><span data-stu-id="2d29d-120">Establish and connect to a data stream</span></span>

<span data-ttu-id="2d29d-121">Una forma popular de probar el procesamiento de flujos es a través de **netcat**.</span><span class="sxs-lookup"><span data-stu-id="2d29d-121">One popular way to test stream processing is through **netcat**.</span></span> <span data-ttu-id="2d29d-122">netcat (también conocido como *nc*) le permite leer desde conexiones de red y escribir en ellas.</span><span class="sxs-lookup"><span data-stu-id="2d29d-122">netcat (also known as *nc*) allows you to read from and write to network connections.</span></span> <span data-ttu-id="2d29d-123">Establezca una conexión de red con netcat a través de una ventana de terminal.</span><span class="sxs-lookup"><span data-stu-id="2d29d-123">You establish a network connection with netcat through a terminal window.</span></span>

### <a name="create-a-data-stream-with-netcat"></a><span data-ttu-id="2d29d-124">Creación de un flujo de datos con netcat</span><span class="sxs-lookup"><span data-stu-id="2d29d-124">Create a data stream with netcat</span></span>

1. <span data-ttu-id="2d29d-125">[Descargue netcat](https://sourceforge.net/projects/nc110/files/).</span><span class="sxs-lookup"><span data-stu-id="2d29d-125">[Download netcat](https://sourceforge.net/projects/nc110/files/).</span></span> <span data-ttu-id="2d29d-126">A continuación, extraiga el archivo de la descarga de zip y anexe el directorio que extrajo a su variable de entorno "PATH".</span><span class="sxs-lookup"><span data-stu-id="2d29d-126">Then, extract the file from the zip download and append the directory you extracted to your "PATH" environment variable.</span></span>

2. <span data-ttu-id="2d29d-127">Para iniciar una nueva conexión, abra una nueva consola y ejecute el siguiente comando que se conecte a localhost en el puerto 9999.</span><span class="sxs-lookup"><span data-stu-id="2d29d-127">To start a new connection, open a new console and run the following command which connects to localhost on port 9999.</span></span>

   <span data-ttu-id="2d29d-128">En Windows:</span><span class="sxs-lookup"><span data-stu-id="2d29d-128">On Windows:</span></span>

   ```console
   nc -vvv -l -p 9999
   ```

   <span data-ttu-id="2d29d-129">En Linux:</span><span class="sxs-lookup"><span data-stu-id="2d29d-129">On Linux:</span></span>

   ```console
   nc -lk 9999
   ```

   <span data-ttu-id="2d29d-130">El programa de Spark escucha la entrada que escribe en este símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="2d29d-130">Your Spark program listens for the input you type into this command prompt.</span></span>

### <a name="create-a-sparksession"></a><span data-ttu-id="2d29d-131">Creación de una SparkSession</span><span class="sxs-lookup"><span data-stu-id="2d29d-131">Create a SparkSession</span></span>

1. <span data-ttu-id="2d29d-132">Agregue las instrucciones `using` adicionales siguientes a la parte superior del archivo *Program.cs* en *mySparkStreamingApp*:</span><span class="sxs-lookup"><span data-stu-id="2d29d-132">Add the following additional `using` statements to the top of the *Program.cs* file in *mySparkStreamingApp*:</span></span>

   ```csharp
   using System;
   using Microsoft.Spark.Sql;
   using Microsoft.Spark.Sql.Streaming;
   using static Microsoft.Spark.Sql.Functions;
   ```

1. <span data-ttu-id="2d29d-133">Agregue el código siguiente al método `Main` para crear una nueva `SparkSession`.</span><span class="sxs-lookup"><span data-stu-id="2d29d-133">Add the following code to your `Main` method to create a new `SparkSession`.</span></span> <span data-ttu-id="2d29d-134">La sesión de Spark es el punto de entrada para programar Spark con la API de DataFrame y DataSet.</span><span class="sxs-lookup"><span data-stu-id="2d29d-134">The Spark Session is the entry point to programming Spark with the Dataset and DataFrame API.</span></span>

   ```csharp
   SparkSession spark = SparkSession
        .Builder()
        .AppName("Streaming example with a UDF")
        .GetOrCreate();
   ```

   <span data-ttu-id="2d29d-135">Llamar al objeto *spark* creado anteriormente le permite tener acceso a la funcionalidad de DataFrame y Spark a través del programa.</span><span class="sxs-lookup"><span data-stu-id="2d29d-135">Calling the *spark* object created above allows you to access Spark and DataFrame functionality throughout your program.</span></span>

### <a name="connect-to-a-stream-with-readstream"></a><span data-ttu-id="2d29d-136">Conexión a un flujo con ReadStream ()</span><span class="sxs-lookup"><span data-stu-id="2d29d-136">Connect to a stream with ReadStream()</span></span>

<span data-ttu-id="2d29d-137">El método `ReadStream()` devuelve un `DataStreamReader` que se puede usar para leer datos de streaming como `DataFrame`.</span><span class="sxs-lookup"><span data-stu-id="2d29d-137">The `ReadStream()` method returns a `DataStreamReader` that can be used to read streaming data in as a `DataFrame`.</span></span> <span data-ttu-id="2d29d-138">Incluya la información del host y el puerto para indicar a su aplicación Spark dónde se deben esperar sus datos de streaming.</span><span class="sxs-lookup"><span data-stu-id="2d29d-138">Include the host and port information to tell your Spark app where to expect its streaming data.</span></span>

```csharp
DataFrame lines = spark
    .ReadStream()
    .Format("socket")
    .Option("host", hostname)
    .Option("port", port)
    .Load();
```

## <a name="register-a-user-defined-function"></a><span data-ttu-id="2d29d-139">Registro de una función definida por el usuario</span><span class="sxs-lookup"><span data-stu-id="2d29d-139">Register a user-defined function</span></span>

<span data-ttu-id="2d29d-140">Puede usar UDF, *funciones definidas por el usuario*, en aplicaciones Spark para realizar cálculos y análisis de los datos.</span><span class="sxs-lookup"><span data-stu-id="2d29d-140">You can use UDFs, *user-defined functions*, in Spark applications to perform calculations and analysis on your data.</span></span>

<span data-ttu-id="2d29d-141">Agregue el siguiente código a su método `Main` para registrar una UDF llamada `udfArray`.</span><span class="sxs-lookup"><span data-stu-id="2d29d-141">Add the following code to your `Main` method to register a UDF called `udfArray`.</span></span>

```csharp
Func<Column, Column> udfArray =
    Udf<string, string[]>((str) => new string[] { str, $"{str} {str.Length}" });
```

<span data-ttu-id="2d29d-142">Esta UDF procesa cada cadena que recibe del terminal netcat para producir una cadena que incluye la cadena original (contenida en *str*), seguida de la cadena original concatenada con la longitud de la cadena original.</span><span class="sxs-lookup"><span data-stu-id="2d29d-142">This UDF processes each string it receives from the netcat terminal to produce an array that includes the original string (contained in *str*), followed by the original string concatenated with the length of the original string.</span></span>

<span data-ttu-id="2d29d-143">Por ejemplo, al escribir *Hola mundo* en el terminal netcat se produce una matriz donde:</span><span class="sxs-lookup"><span data-stu-id="2d29d-143">For example, entering *Hello world* in the netcat terminal produces an array where:</span></span>

* <span data-ttu-id="2d29d-144">matriz\[0] = Hola mundo</span><span class="sxs-lookup"><span data-stu-id="2d29d-144">array\[0] = Hello world</span></span>
* <span data-ttu-id="2d29d-145">matriz\[1] = Hola mundo 11</span><span class="sxs-lookup"><span data-stu-id="2d29d-145">array\[1] = Hello world 11</span></span>

## <a name="use-sparksql"></a><span data-ttu-id="2d29d-146">Uso de SparkSQL</span><span class="sxs-lookup"><span data-stu-id="2d29d-146">Use SparkSQL</span></span>

<span data-ttu-id="2d29d-147">Use SparkSQL para realizar diversas funciones en los datos almacenados en DataFrame.</span><span class="sxs-lookup"><span data-stu-id="2d29d-147">Use SparkSQL to perform various functions on the data stored in your DataFrame.</span></span> <span data-ttu-id="2d29d-148">Es habitual combinar UDF y SparkSQL para aplicar una UDF a cada fila de un DataFrame.</span><span class="sxs-lookup"><span data-stu-id="2d29d-148">It's common to combine UDFs and SparkSQL to apply a UDF to each row of a DataFrame.</span></span>

```csharp
DataFrame arrayDF = lines.Select(Explode(udfArray(lines["value"])));
```

<span data-ttu-id="2d29d-149">Este fragmento de código aplica *udfArray* a cada valor del DataFrame, que representa cada cadena leída del terminal netcat.</span><span class="sxs-lookup"><span data-stu-id="2d29d-149">This code snippet applies *udfArray* to each value in your DataFrame, which represents each string read from your netcat terminal.</span></span> <span data-ttu-id="2d29d-150">Aplique el método SparkSQL <xref:Microsoft.Spark.Sql.Functions.Explode%2A> para colocar cada entrada de la matriz en su propia fila.</span><span class="sxs-lookup"><span data-stu-id="2d29d-150">Apply the SparkSQL method <xref:Microsoft.Spark.Sql.Functions.Explode%2A> to put each entry of your array in its own row.</span></span> <span data-ttu-id="2d29d-151">Por último, use <xref:Microsoft.Spark.Sql.DataFrame.Select%2A> para colocar las columnas que ha producido en el nuevo DataFrame *arrayDF.*</span><span class="sxs-lookup"><span data-stu-id="2d29d-151">Finally, use <xref:Microsoft.Spark.Sql.DataFrame.Select%2A> to place the columns you've produced in the new DataFrame *arrayDF.*</span></span>

## <a name="display-your-stream"></a><span data-ttu-id="2d29d-152">Presentación del flujo</span><span class="sxs-lookup"><span data-stu-id="2d29d-152">Display your stream</span></span>

<span data-ttu-id="2d29d-153">Use <xref:Microsoft.Spark.Sql.DataFrame.WriteStream> para establecer las características de su salida, como la impresión de resultados en la consola y la presentación solamente de la salida más reciente.</span><span class="sxs-lookup"><span data-stu-id="2d29d-153">Use <xref:Microsoft.Spark.Sql.DataFrame.WriteStream> to establish characteristics of your output, such as printing results to the console and displaying only the most recent output.</span></span>

```csharp
StreamingQuery query = arrayDf
    .WriteStream()
    .Format("console")
    .Start();
```

## <a name="run-your-code"></a><span data-ttu-id="2d29d-154">Ejecución del código</span><span class="sxs-lookup"><span data-stu-id="2d29d-154">Run your code</span></span>

<span data-ttu-id="2d29d-155">Structured Streaming en Spark procesa datos a través de una serie de pequeños **lotes**.</span><span class="sxs-lookup"><span data-stu-id="2d29d-155">Structured streaming in Spark processes data through a series of small **batches**.</span></span>  <span data-ttu-id="2d29d-156">Al ejecutar su programa, el símbolo del sistema donde establece la conexión netcat le permite empezar a escribir.</span><span class="sxs-lookup"><span data-stu-id="2d29d-156">When you run your program, the command prompt where you establish the netcat connection allows you to start typing.</span></span> <span data-ttu-id="2d29d-157">Cada vez que presiona la tecla Entrar tras escribir datos en ese símbolo del sistema, Spark considera su entrada un lote y ejecuta la UDF.</span><span class="sxs-lookup"><span data-stu-id="2d29d-157">Each time you press the Enter key after typing data in that command prompt, Spark considers your entry a batch and runs the UDF.</span></span>

### <a name="use-spark-submit-to-run-your-app"></a><span data-ttu-id="2d29d-158">Uso de spark-submit para ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="2d29d-158">Use spark-submit to run your app</span></span>

<span data-ttu-id="2d29d-159">Una vez iniciada una nueva sesión de netcat, abra un nuevo terminal y ejecute el comando `spark-submit`, similar al comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="2d29d-159">After starting a new netcat session, open a new terminal and run your `spark-submit` command, similar to the following command:</span></span>

```powershell
spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local /path/to/microsoft-spark-<version>.jar Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredNetworkCharacterCount localhost 9999
```

> [!NOTE]
> <span data-ttu-id="2d29d-160">Asegúrese de actualizar el comando anterior con la ruta de acceso real a su archivo jar de Microsoft Spark.</span><span class="sxs-lookup"><span data-stu-id="2d29d-160">Be sure to update the above command with the actual path to your Microsoft Spark jar file.</span></span> <span data-ttu-id="2d29d-161">El comando anterior también da por hecho que su servidor netcat se ejecuta en el puerto localhost 9999.</span><span class="sxs-lookup"><span data-stu-id="2d29d-161">The above command also assumes your netcat server is running on localhost port 9999.</span></span>

## <a name="get-the-code"></a><span data-ttu-id="2d29d-162">Obtención del código</span><span class="sxs-lookup"><span data-stu-id="2d29d-162">Get the code</span></span>

<span data-ttu-id="2d29d-163">En este tutorial se usa el ejemplo [StructuredNetworkCharacterCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkCharacterCount.cs), pero hay otros tres ejemplos de procesamiento de flujos completo en GitHub:</span><span class="sxs-lookup"><span data-stu-id="2d29d-163">This tutorial uses the [StructuredNetworkCharacterCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkCharacterCount.cs) example, but there are three other full stream processing examples on GitHub:</span></span>

* <span data-ttu-id="2d29d-164">[StructuredNetworkWordCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs): recuento de palabras en datos de streaming de cualquier origen</span><span class="sxs-lookup"><span data-stu-id="2d29d-164">[StructuredNetworkWordCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs): word count on data streamed from any source</span></span>
* <span data-ttu-id="2d29d-165">[StructuredNetworkWordCountWindowed.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCountWindowed.cs): recuento de palabras en datos con lógica de ventanas</span><span class="sxs-lookup"><span data-stu-id="2d29d-165">[StructuredNetworkWordCountWindowed.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCountWindowed.cs): word count on data with windowing logic</span></span>
* <span data-ttu-id="2d29d-166">[StructuredKafkaWordCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs): recuento de palabras en datos de streaming de Kafka</span><span class="sxs-lookup"><span data-stu-id="2d29d-166">[StructuredKafkaWordCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs): word count on data streamed from Kafka</span></span>

## <a name="next-steps"></a><span data-ttu-id="2d29d-167">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="2d29d-167">Next steps</span></span>

<span data-ttu-id="2d29d-168">Avance al siguiente artículo para aprender a implementar su aplicación de .NET para Apache Spark en Databricks.</span><span class="sxs-lookup"><span data-stu-id="2d29d-168">Advance to the next article to learn how to deploy your .NET for Apache Spark application to Databricks.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="2d29d-169">Tutorial: Implementación de una aplicación de .NET para Apache Spark en Databricks</span><span class="sxs-lookup"><span data-stu-id="2d29d-169">Tutorial: Deploy a .NET for Apache Spark application to Databricks</span></span>](databricks-deployment.md)
