---
title: Compilación de una aplicación de .NET para Apache Spark en Windows
description: Aprenda a compilar una aplicación de .NET para Apache Spark en Windows.
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: how-to
ms.openlocfilehash: e3ab62ea8bc493c7e652b66f0e9c7adce7decb56
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104876960"
---
# <a name="learn-how-to-build-your-net-for-apache-spark-application-on-windows"></a><span data-ttu-id="46212-103">Aprenda a compilar una aplicación de .NET para Apache Spark en Windows</span><span class="sxs-lookup"><span data-stu-id="46212-103">Learn how to build your .NET for Apache Spark application on Windows</span></span>

<span data-ttu-id="46212-104">En este artículo se enseña cómo crear aplicaciones de .NET para Apache Spark en Windows.</span><span class="sxs-lookup"><span data-stu-id="46212-104">This article teaches you how to build your .NET for Apache Spark applications on Windows.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="46212-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="46212-105">Prerequisites</span></span>

<span data-ttu-id="46212-106">Si ya cumple con todos los requisitos previos siguientes, vaya a los pasos de [compilación](#build).</span><span class="sxs-lookup"><span data-stu-id="46212-106">If you already have all of the following prerequisites, skip to the [build](#build) steps.</span></span>

  1. <span data-ttu-id="46212-107">Descargue e instale el **[SDK de .NET Core](https://dotnet.microsoft.com/download/dotnet/3.1)** . Al instalar el SDK, se agregará la cadena de herramientas `dotnet` a la variable de entorno PATH.</span><span class="sxs-lookup"><span data-stu-id="46212-107">Download and install the **[.NET Core SDK](https://dotnet.microsoft.com/download/dotnet/3.1)** - installing the SDK will add the `dotnet` toolchain to your path.</span></span> <span data-ttu-id="46212-108">Se admiten las versiones de .NET Core 2.1, 2.2 y 3.1.</span><span class="sxs-lookup"><span data-stu-id="46212-108">.NET Core 2.1, 2.2 and 3.1 are supported.</span></span>
  2. <span data-ttu-id="46212-109">Instale **[Visual Studio 2019](https://www.visualstudio.com/downloads/)** (versión 16.3 o posterior).</span><span class="sxs-lookup"><span data-stu-id="46212-109">Install **[Visual Studio 2019](https://www.visualstudio.com/downloads/)** (Version 16.3 or later).</span></span> <span data-ttu-id="46212-110">La versión Community es completamente gratis.</span><span class="sxs-lookup"><span data-stu-id="46212-110">The Community version is completely free.</span></span> <span data-ttu-id="46212-111">Al configurar la instalación, incluya al menos estos componentes:</span><span class="sxs-lookup"><span data-stu-id="46212-111">When configuring your installation, include these components at minimum:</span></span>
     * <span data-ttu-id="46212-112">Desarrollo de escritorio de .NET</span><span class="sxs-lookup"><span data-stu-id="46212-112">.NET desktop development</span></span>
       * <span data-ttu-id="46212-113">Todos los componentes necesarios</span><span class="sxs-lookup"><span data-stu-id="46212-113">All Required Components</span></span>
         * <span data-ttu-id="46212-114">Herramientas de desarrollo de .NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="46212-114">.NET Framework 4.6.1 Development Tools</span></span>
     * <span data-ttu-id="46212-115">Desarrollo multiplataforma de .NET Core</span><span class="sxs-lookup"><span data-stu-id="46212-115">.NET Core cross-platform development</span></span>
       * <span data-ttu-id="46212-116">Todos los componentes necesarios</span><span class="sxs-lookup"><span data-stu-id="46212-116">All Required Components</span></span>
  3. <span data-ttu-id="46212-117">Instale **[Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)** .</span><span class="sxs-lookup"><span data-stu-id="46212-117">Install **[Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)**.</span></span>
     - <span data-ttu-id="46212-118">Seleccione la versión adecuada según su sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="46212-118">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="46212-119">Por ejemplo, *jdk-8u201-windows-x64.exe* si el equipo es Windows x64.</span><span class="sxs-lookup"><span data-stu-id="46212-119">For example, *jdk-8u201-windows-x64.exe* for Windows x64 machine.</span></span>
     - <span data-ttu-id="46212-120">Use el instalador para realizar la instalación y compruebe que puede ejecutar `java` desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="46212-120">Install using the installer and verify you are able to run `java` from your command line.</span></span>
  4. <span data-ttu-id="46212-121">Instale **[Apache Maven 3.6.0+](https://maven.apache.org/download.cgi)** .</span><span class="sxs-lookup"><span data-stu-id="46212-121">Install **[Apache Maven 3.6.0+](https://maven.apache.org/download.cgi)**.</span></span>
     - <span data-ttu-id="46212-122">Descargue [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.zip).</span><span class="sxs-lookup"><span data-stu-id="46212-122">Download [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.zip).</span></span>
     - <span data-ttu-id="46212-123">Extraiga en un directorio local.</span><span class="sxs-lookup"><span data-stu-id="46212-123">Extract to a local directory.</span></span> <span data-ttu-id="46212-124">Por ejemplo, \*C:\bin\apache-maven-3.6.0\*.</span><span class="sxs-lookup"><span data-stu-id="46212-124">For example, \*C:\bin\apache-maven-3.6.0\*.</span></span>
     - <span data-ttu-id="46212-125">Agregue Apache Maven a la [variable de entorno PATH](https://www.java.com/en/download/help/path.xml).</span><span class="sxs-lookup"><span data-stu-id="46212-125">Add Apache Maven to your [PATH environment variable](https://www.java.com/en/download/help/path.xml).</span></span> <span data-ttu-id="46212-126">Por ejemplo, *C:\bin\apache-maven-3.6.0\bin*.</span><span class="sxs-lookup"><span data-stu-id="46212-126">For example, *C:\bin\apache-maven-3.6.0\bin*.</span></span>
     - <span data-ttu-id="46212-127">Confirme que puede ejecutar `mvn` desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="46212-127">Verify you are able to run `mvn` from your command-line.</span></span>
  5. <span data-ttu-id="46212-128">Instale **[Apache Spark 2.3+](https://spark.apache.org/downloads.html)** .</span><span class="sxs-lookup"><span data-stu-id="46212-128">Install **[Apache Spark 2.3+](https://spark.apache.org/downloads.html)**.</span></span>
     - <span data-ttu-id="46212-129">Descargue [Apache Spark 2.3+](https://spark.apache.org/downloads.html) y extráigalo en una carpeta local (por ejemplo, *C:\bin\spark-3.0.1-bin-hadoop2.7\*), mediante [7-zip](https://www.7-zip.org/). (Las versiones compatibles de Spark son 2.3.* , 2.4.0, 2.4.1, 2.4.3, 2.4.4, 2.4.5, 2.4.6, 2.4.7, 3.0.0 y 3.0.1)</span><span class="sxs-lookup"><span data-stu-id="46212-129">Download [Apache Spark 2.3+](https://spark.apache.org/downloads.html) and extract it into a local folder (for example, *C:\bin\spark-3.0.1-bin-hadoop2.7\*) using [7-zip](https://www.7-zip.org/). (The supported spark versions are 2.3.*, 2.4.0, 2.4.1, 2.4.3, 2.4.4, 2.4.5, 2.4.6, 2.4.7, 3.0.0 and 3.0.1)</span></span>
     - <span data-ttu-id="46212-130">Agregue una [variable de entorno nueva](https://www.java.com/en/download/help/path.xml) `SPARK_HOME`.</span><span class="sxs-lookup"><span data-stu-id="46212-130">Add a [new environment variable](https://www.java.com/en/download/help/path.xml) `SPARK_HOME`.</span></span> <span data-ttu-id="46212-131">Por ejemplo, \*C:\bin\spark-3.0.1-bin-hadoop2.7\*.</span><span class="sxs-lookup"><span data-stu-id="46212-131">For example, \*C:\bin\spark-3.0.1-bin-hadoop2.7\*.</span></span>

       ```powershell
       set SPARK_HOME=C:\bin\spark-3.0.1-bin-hadoop2.7\
       ```

     - <span data-ttu-id="46212-132">Agregue Apache Spark a la [variable de entorno PATH](https://www.java.com/en/download/help/path.xml).</span><span class="sxs-lookup"><span data-stu-id="46212-132">Add Apache Spark to your [PATH environment variable](https://www.java.com/en/download/help/path.xml).</span></span> <span data-ttu-id="46212-133">Por ejemplo, *C:\bin\spark-3.0.1-bin-hadoop2.7\bin*.</span><span class="sxs-lookup"><span data-stu-id="46212-133">For example, *C:\bin\spark-3.0.1-bin-hadoop2.7\bin*.</span></span>

       ```powershell
       set PATH=%SPARK_HOME%\bin;%PATH%
       ```

     - <span data-ttu-id="46212-134">Confirme que puede ejecutar `spark-shell` desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="46212-134">Verify you are able to run `spark-shell` from your command-line.</span></span>
        <span data-ttu-id="46212-135">Salida de la consola de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="46212-135">Sample console output:</span></span>

        ```output
        Welcome to
              ____              __
             / __/__  ___ _____/ /__
            _\ \/ _ \/ _ `/ __/  '_/
           /___/ .__/\_,_/_/ /_/\_\   version 3.0.1
              /_/

        Using Scala version 2.12.10 (Java HotSpot(TM) 64-Bit Server VM, Java 1.8.0_201)
        Type in expressions to have them evaluated.
        Type :help for more information.

        scala> sc
        res0: org.apache.spark.SparkContext = org.apache.spark.SparkContext@6eaa6b0c
        ```

        </details>

  6. <span data-ttu-id="46212-136">Instale **[WinUtils](https://github.com/steveloughran/winutils)** .</span><span class="sxs-lookup"><span data-stu-id="46212-136">Install **[WinUtils](https://github.com/steveloughran/winutils)**.</span></span>
     - <span data-ttu-id="46212-137">Descargue el archivo binario `winutils.exe` del [repositorio de WinUtils](https://github.com/steveloughran/winutils).</span><span class="sxs-lookup"><span data-stu-id="46212-137">Download `winutils.exe` binary from [WinUtils repository](https://github.com/steveloughran/winutils).</span></span> <span data-ttu-id="46212-138">Debe seleccionar la versión de Hadoop con la que se ha compilado la distribución de Spark.</span><span class="sxs-lookup"><span data-stu-id="46212-138">You should select the version of Hadoop the Spark distribution was compiled with.</span></span> <span data-ttu-id="46212-139">Por ejemplo, use hadoop-2.7.1 para Spark 3.0.1.</span><span class="sxs-lookup"><span data-stu-id="46212-139">For exammple, use hadoop-2.7.1 for Spark 3.0.1.</span></span>
     - <span data-ttu-id="46212-140">Guarde el archivo binario `winutils.exe` en el directorio que elija.</span><span class="sxs-lookup"><span data-stu-id="46212-140">Save `winutils.exe` binary to a directory of your choice.</span></span> <span data-ttu-id="46212-141">Por ejemplo, *C:\hadoop\bin*.</span><span class="sxs-lookup"><span data-stu-id="46212-141">For example, *C:\hadoop\bin*.</span></span>
     - <span data-ttu-id="46212-142">Establezca `HADOOP_HOME` para reflejar el directorio con winutils.exe (sin bin).</span><span class="sxs-lookup"><span data-stu-id="46212-142">Set `HADOOP_HOME` to reflect the directory with winutils.exe (without bin).</span></span> <span data-ttu-id="46212-143">Por ejemplo, con la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="46212-143">For instance, using command-line:</span></span>

       ```powershell
       set HADOOP_HOME=C:\hadoop
       ```

     - <span data-ttu-id="46212-144">Establezca la variable de entorno PATH para que incluya `%HADOOP_HOME%\bin`.</span><span class="sxs-lookup"><span data-stu-id="46212-144">Set PATH environment variable to include `%HADOOP_HOME%\bin`.</span></span> <span data-ttu-id="46212-145">Por ejemplo, con la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="46212-145">For instance, using command line:</span></span>

       ```powershell
       set PATH=%HADOOP_HOME%\bin;%PATH%
       ```

<span data-ttu-id="46212-146">Asegúrese de que puede ejecutar `dotnet`, `java`, `mvn`, `spark-shell` desde la línea de comandos antes de pasar a la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="46212-146">Make sure you are able to run `dotnet`, `java`, `mvn`, `spark-shell` from your command line before you move to the next section.</span></span> <span data-ttu-id="46212-147">¿Cree que hay una mejor manera de hacerlo?</span><span class="sxs-lookup"><span data-stu-id="46212-147">Feel there is a better way?</span></span> <span data-ttu-id="46212-148">[Abra una incidencia](https://github.com/dotnet/spark/issues) y háganos llegar sus comentarios.</span><span class="sxs-lookup"><span data-stu-id="46212-148">[Open an issue](https://github.com/dotnet/spark/issues) and feel free to contribute.</span></span>

> [!NOTE]
> <span data-ttu-id="46212-149">Es posible que sea necesaria una instancia nueva de la línea de comandos si se actualizaran las variables de entorno.</span><span class="sxs-lookup"><span data-stu-id="46212-149">A new instance of the command line may be required if any environment variables were updated.</span></span>

## <a name="build"></a><span data-ttu-id="46212-150">Compilar</span><span class="sxs-lookup"><span data-stu-id="46212-150">Build</span></span>

<span data-ttu-id="46212-151">En el resto de esta guía, deberá haber clonado el repositorio de .NET para Apache Spark en la máquina.</span><span class="sxs-lookup"><span data-stu-id="46212-151">For the remainder of this guide, you will need to have cloned the .NET for Apache Spark repository into your machine.</span></span> <span data-ttu-id="46212-152">Puede elegir cualquier ubicación para el repositorio clonado.</span><span class="sxs-lookup"><span data-stu-id="46212-152">You can choose any location for the cloned repository.</span></span> <span data-ttu-id="46212-153">Por ejemplo, \*C:\github\dotnet-spark\*.</span><span class="sxs-lookup"><span data-stu-id="46212-153">For example, \*C:\github\dotnet-spark\*.</span></span>

```bash
git clone https://github.com/dotnet/spark.git C:\github\dotnet-spark
```

### <a name="build-net-for-apache-spark-scala-extensions-layer"></a><span data-ttu-id="46212-154">Creación de la capa de extensiones de Scala de .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="46212-154">Build .NET for Apache Spark Scala extensions layer</span></span>

<span data-ttu-id="46212-155">Cuando se envía una aplicación de .NET, .NET para Apache Spark escribe en Scala la lógica necesaria que informa a Apache Spark cómo administrar las solicitudes (por ejemplo, solicitud para crear una sesión de Spark, solicitud para transferir datos desde el lado de .NET al lado de JVM, etc.).</span><span class="sxs-lookup"><span data-stu-id="46212-155">When you submit a .NET application, .NET for Apache Spark has the necessary logic written in Scala that informs Apache Spark how to handle your requests (for example, request to create a new Spark Session, request to transfer data from .NET side to JVM side etc.).</span></span> <span data-ttu-id="46212-156">Esta lógica se puede encontrar en el [código fuente de Scala de .NET para Spark](https://github.com/dotnet/spark/tree/main/src/scala).</span><span class="sxs-lookup"><span data-stu-id="46212-156">This logic can be found in the [.NET for Spark Scala Source Code](https://github.com/dotnet/spark/tree/main/src/scala).</span></span>

<span data-ttu-id="46212-157">Independientemente de si usa .NET Framework o .NET Core, tendrá que crear la capa de extensiones de Scala de .NET para Apache Spark:</span><span class="sxs-lookup"><span data-stu-id="46212-157">Regardless of whether you are using .NET Framework or .NET Core, you will need to build the .NET for Apache Spark Scala extension layer:</span></span>

```powershell
cd src\scala
mvn clean package
```

<span data-ttu-id="46212-158">Debería ver los archivos JAR creados para las versiones compatibles de Spark:</span><span class="sxs-lookup"><span data-stu-id="46212-158">You should see JARs created for the supported Spark versions:</span></span>

* `microsoft-spark-2-3\target\microsoft-spark-2-3_2.11-<spark-dotnet-version>.jar`
* `microsoft-spark-2-4\target\microsoft-spark-2-4_2.11-<spark-dotnet-version>.jar`
* `microsoft-spark-3-0\target\microsoft-spark-3-0_2.12-<spark-dotnet-version>.jar`

### <a name="build-the-net-for-spark-sample-applications"></a><span data-ttu-id="46212-159">Compilación de las aplicaciones de ejemplo de .NET para Spark</span><span class="sxs-lookup"><span data-stu-id="46212-159">Build the .NET for Spark sample applications</span></span>

<span data-ttu-id="46212-160">En esta sección se explica cómo compilar las [aplicaciones de ejemplo](https://github.com/dotnet/spark/tree/main/examples) de .NET para Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="46212-160">This section explains how to build the [sample applications](https://github.com/dotnet/spark/tree/main/examples) for .NET for Apache Spark.</span></span> <span data-ttu-id="46212-161">Estos pasos lo ayudarán a comprender el proceso general de compilación de cualquier aplicación de .NET para Spark.</span><span class="sxs-lookup"><span data-stu-id="46212-161">These steps will help in understanding the overall building process for any .NET for Spark application.</span></span>

#### <a name="using-visual-studio-for-net-framework"></a><span data-ttu-id="46212-162">Uso de Visual Studio para .NET Framework</span><span class="sxs-lookup"><span data-stu-id="46212-162">Using Visual Studio for .NET Framework</span></span>

  1. <span data-ttu-id="46212-163">Abra `src\csharp\Microsoft.Spark.sln` en Visual Studio y compile el proyecto `Microsoft.Spark.CSharp.Examples` en la carpeta `examples` (a su vez, esto compilará también el proyecto de enlaces de .NET).</span><span class="sxs-lookup"><span data-stu-id="46212-163">Open `src\csharp\Microsoft.Spark.sln` in Visual Studio and build the `Microsoft.Spark.CSharp.Examples` project under the `examples` folder (this will in turn build the .NET bindings project as well).</span></span> <span data-ttu-id="46212-164">Si quiere, puede escribir su propio código en el proyecto `Microsoft.Spark.Examples` (en este ejemplo, "input_file.json" es un archivo JSON con los datos con los que quiere crear la trama de datos):</span><span class="sxs-lookup"><span data-stu-id="46212-164">If you want, you can write your own code in the `Microsoft.Spark.Examples` project (the 'input_file.json' in this example is a json file with the data you want to create the dataframe with):</span></span>
  
      ```csharp
        // Instantiate a session
        var spark = SparkSession
            .Builder()
            .AppName("Hello Spark!")
            .GetOrCreate();

        // Create initial DataFrame
        DataFrame df = spark.Read().Json(input_file.json);

        // Print schema
        df.PrintSchema();

        // Apply a filter and show results
        df.Filter(df["age"] > 21).Show();
      ```

     <span data-ttu-id="46212-165">Una vez que la compilación se realice correctamente, verá los archivos binarios adecuados en el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="46212-165">Once the build is successful, you will see the appropriate binaries produced in the output directory.</span></span>
     <span data-ttu-id="46212-166">Salida de la consola de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="46212-166">Sample console output:</span></span>

      ```powershell
            Directory: C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\net461


        Mode                LastWriteTime         Length Name
        ----                -------------         ------ ----
        -a----         3/6/2019  12:18 AM         125440 Apache.Arrow.dll
        -a----        3/16/2019  12:00 AM          13824 Microsoft.Spark.CSharp.Examples.exe
        -a----        3/16/2019  12:00 AM          19423 Microsoft.Spark.CSharp.Examples.exe.config
        -a----        3/16/2019  12:00 AM           2720 Microsoft.Spark.CSharp.Examples.pdb
        -a----        3/16/2019  12:00 AM         143360 Microsoft.Spark.dll
        -a----        3/16/2019  12:00 AM          63388 Microsoft.Spark.pdb
        -a----        3/16/2019  12:00 AM          34304 Microsoft.Spark.Worker.exe
        -a----        3/16/2019  12:00 AM          19423 Microsoft.Spark.Worker.exe.config
        -a----        3/16/2019  12:00 AM          11900 Microsoft.Spark.Worker.pdb
        -a----        3/16/2019  12:00 AM          23552 Microsoft.Spark.Worker.xml
        -a----        3/16/2019  12:00 AM         332363 Microsoft.Spark.xml
        ------------------------------------------- More framework files -------------------------------------
      ```

#### <a name="using-net-core-cli-for-net-core"></a><span data-ttu-id="46212-167">Uso de la CLI de .NET Core para .NET Core</span><span class="sxs-lookup"><span data-stu-id="46212-167">Using .NET Core CLI for .NET Core</span></span>

> [!NOTE]
> <span data-ttu-id="46212-168">Actualmente, estamos trabajando en automatizar las compilaciones de .NET Core de .NET para Spark.</span><span class="sxs-lookup"><span data-stu-id="46212-168">We are currently working on automating .NET Core builds for Spark .NET.</span></span> <span data-ttu-id="46212-169">Hasta entonces, agradecemos su paciencia al realizar algunos de los pasos manualmente.</span><span class="sxs-lookup"><span data-stu-id="46212-169">Until then, we appreciate your patience in performing some of the steps manually.</span></span>

  1. <span data-ttu-id="46212-170">Compile el trabajo:</span><span class="sxs-lookup"><span data-stu-id="46212-170">Build the worker:</span></span>

      ```powershell
      cd C:\github\dotnet-spark\src\csharp\Microsoft.Spark.Worker\
      dotnet publish -f netcoreapp3.1 -r win-x64
      ```

      <span data-ttu-id="46212-171">Salida de la consola de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="46212-171">Sample console output:</span></span>

      ```powershell
      PS C:\github\dotnet-spark\src\csharp\Microsoft.Spark.Worker> dotnet publish -f netcoreapp3.1 -r win-x64
      Microsoft (R) Build Engine version 16.6.0+5ff7b0c9e for .NET Core
      Copyright (C) Microsoft Corporation. All rights reserved.

        Restore completed in 299.95 ms for C:\github\dotnet-spark\src\csharp\Microsoft.Spark\Microsoft.Spark.csproj.
        Restore completed in 306.62 ms for C:\github\dotnet-spark\src\csharp\Microsoft.Spark.Worker\Microsoft.Spark.Worker.csproj.
        Microsoft.Spark -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark\Debug\netstandard2.1\Microsoft.Spark.dll
        Microsoft.Spark.Worker -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\x64\Debug\netcoreapp3.1\win-x64\Microsoft.Spark.Worker.dll
        Microsoft.Spark.Worker -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\x64\Debug\netcoreapp3.1\win-x64\publish\
      ```

  2. <span data-ttu-id="46212-172">Compile los ejemplos:</span><span class="sxs-lookup"><span data-stu-id="46212-172">Build the samples:</span></span>

      ```powershell
      cd C:\github\dotnet-spark\examples\Microsoft.Spark.CSharp.Examples\
      dotnet publish -f netcoreapp3.1 -r win-x64
      ```

      <span data-ttu-id="46212-173">Salida de la consola de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="46212-173">Sample console output:</span></span>

      ```powershell
      PS C:\github\dotnet-spark\examples\Microsoft.Spark.CSharp.Examples> dotnet publish -f netcoreapp3.1 -r win-x64
      Microsoft (R) Build Engine version 16.6.0+5ff7b0c9e for .NET Core
      Copyright (C) Microsoft Corporation. All rights reserved.

        Restore completed in 44.22 ms for C:\github\dotnet-spark\src\csharp\Microsoft.Spark\Microsoft.Spark.csproj.
        Restore completed in 336.94 ms for C:\github\dotnet-spark\examples\Microsoft.Spark.CSharp.Examples\Microsoft.Spark.CSharp.Examples.csproj.
        Microsoft.Spark -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark\Debug\netstandard2.1\Microsoft.Spark.dll
        Microsoft.Spark.CSharp.Examples -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\x64\Debug\netcoreapp3.1\win-x64\Microsoft.Spark.CSharp.Examples.dll
        Microsoft.Spark.CSharp.Examples -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\x64\Debug\netcoreapp3.1\win-x64\publish\
      ```

## <a name="run-the-net-for-spark-sample-applications"></a><span data-ttu-id="46212-174">Ejecución de las aplicaciones de ejemplo de .NET para Spark</span><span class="sxs-lookup"><span data-stu-id="46212-174">Run the .NET for Spark sample applications</span></span>

<span data-ttu-id="46212-175">Una vez que se compilan los ejemplos, su ejecución se realizará a través de `spark-submit` independientemente de si el destino es .NET Framework o .NET Core.</span><span class="sxs-lookup"><span data-stu-id="46212-175">Once you build the samples, running them will be through `spark-submit` regardless of whether you are targeting .NET Framework or .NET Core.</span></span> <span data-ttu-id="46212-176">Asegúrese de haber seguido la sección de [requisitos previos](#prerequisites) y de haber instalado Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="46212-176">Make sure you have followed the [prerequisites](#prerequisites) section and installed Apache Spark.</span></span>

  1. <span data-ttu-id="46212-177">Establezca la variable de entorno `DOTNET_WORKER_DIR` o `PATH` para incluir la ruta de acceso en la que se ha generado el binario `Microsoft.Spark.Worker` (por ejemplo, *C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.Worker\Debug\net461* para .NET Framework, *C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\x64\Debug\netcoreapp3.1\win-x64\publish* para .NET Core):</span><span class="sxs-lookup"><span data-stu-id="46212-177">Set the `DOTNET_WORKER_DIR` or `PATH` environment variable to include the path where the `Microsoft.Spark.Worker` binary has been generated (for example, *C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.Worker\Debug\net461* for .NET Framework, *C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\x64\Debug\netcoreapp3.1\win-x64\publish* for .NET Core):</span></span>

      ```powershell
      set DOTNET_WORKER_DIR=C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\x64\Debug\netcoreapp3.1\win-x64\publish
      ```
  
  2. <span data-ttu-id="46212-178">Abra PowerShell y vaya al directorio en el que se haya generado el archivo binario de la aplicación (por ejemplo, *C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\net461* para .NET Framework, *C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\x64\Debug\netcoreapp3.1\win-x64\publish* para .NET Core):</span><span class="sxs-lookup"><span data-stu-id="46212-178">Open PowerShell and go to the directory where your app binary has been generated (for example, *C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\net461* for .NET Framework, *C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\x64\Debug\netcoreapp3.1\win-x64\publish* for .NET Core):</span></span>

      ```powershell
      cd C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\x64\Debug\netcoreapp3.1\win-x64\publish
      ```

  3. <span data-ttu-id="46212-179">La ejecución de la aplicación sigue la estructura básica:</span><span class="sxs-lookup"><span data-stu-id="46212-179">Running your app follows the basic structure:</span></span>

     ```powershell
     spark-submit.cmd `
       [--jars <any-jars-your-app-is-dependent-on>] `
       --class org.apache.spark.deploy.dotnet.DotnetRunner `
       --master local `
       <path-to-microsoft-spark-jar> `
       <path-to-your-app-exe> <argument(s)-to-your-app>
     ```

     <span data-ttu-id="46212-180">Estos son algunos ejemplos que se pueden ejecutar:</span><span class="sxs-lookup"><span data-stu-id="46212-180">Here are some examples you can run:</span></span>

     - <span data-ttu-id="46212-181">**[Microsoft.Spark.Examples.Sql.Batch.Basic](https://github.com/dotnet/spark/blob/main/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/Basic.cs)**</span><span class="sxs-lookup"><span data-stu-id="46212-181">**[Microsoft.Spark.Examples.Sql.Batch.Basic](https://github.com/dotnet/spark/blob/main/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/Basic.cs)**</span></span>

         ```powershell
         spark-submit.cmd `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Batch.Basic %SPARK_HOME%\examples\src\main\resources\people.json
         ```

     - <span data-ttu-id="46212-182">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredNetworkWordCount](https://github.com/dotnet/spark/blob/main/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="46212-182">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredNetworkWordCount](https://github.com/dotnet/spark/blob/main/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs)**</span></span>

         ```powershell
         spark-submit.cmd `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredNetworkWordCount localhost 9999
         ```

     - <span data-ttu-id="46212-183">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (accesible por Maven)](https://github.com/dotnet/spark/blob/main/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="46212-183">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (maven accessible)](https://github.com/dotnet/spark/blob/main/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span></span>

         ```powershell
         spark-submit.cmd `
         --packages org.apache.spark:spark-sql-kafka-0-10_2.11:2.3.2 `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
         ```

     - <span data-ttu-id="46212-184">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (proporcionado por jars)](https://github.com/dotnet/spark/blob/main/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="46212-184">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (jars provided)](https://github.com/dotnet/spark/blob/main/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span></span>

         ```powershell
         spark-submit.cmd
         --jars path\to\net.jpountz.lz4\lz4-1.3.0.jar,path\to\org.apache.kafka\kafka-clients-0.10.0.1.jar,path\to\org.apache.spark\spark-sql-kafka-0-10_2.11-2.3.2.jar,`path\to\org.slf4j\slf4j-api-1.7.6.jar,path\to\org.spark-project.spark\unused-1.0.0.jar,path\to\org.xerial.snappy\snappy-java-1.1.2.6.jar `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
          ```
