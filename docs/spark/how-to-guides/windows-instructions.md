---
title: Compilación de una aplicación de .NET para Apache Spark en Windows
description: Aprenda a compilar una aplicación de .NET para Apache Spark en Windows.
ms.date: 06/25/2020
ms.topic: conceptual
ms.custom: how-to
ms.openlocfilehash: d4755ff94ffc1f678bc078e382e353c203caba87
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812255"
---
# <a name="learn-how-to-build-your-net-for-apache-spark-application-on-windows"></a><span data-ttu-id="6acbb-103">Aprenda a compilar una aplicación de .NET para Apache Spark en Windows</span><span class="sxs-lookup"><span data-stu-id="6acbb-103">Learn how to build your .NET for Apache Spark application on Windows</span></span>

<span data-ttu-id="6acbb-104">En este artículo se enseña cómo crear aplicaciones de .NET para Apache Spark en Windows.</span><span class="sxs-lookup"><span data-stu-id="6acbb-104">This article teaches you how to build your .NET for Apache Spark applications on Windows.</span></span>

[!INCLUDE [spark-preview-note](../../../includes/spark-preview-note.md)]

## <a name="prerequisites"></a><span data-ttu-id="6acbb-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6acbb-105">Prerequisites</span></span>

<span data-ttu-id="6acbb-106">Si ya cumple con todos los requisitos previos siguientes, vaya a los pasos de [compilación](#build).</span><span class="sxs-lookup"><span data-stu-id="6acbb-106">If you already have all of the following prerequisites, skip to the [build](#build) steps.</span></span>

  1. <span data-ttu-id="6acbb-107">Descargue e instale el **[SDK de .NET Core](https://dotnet.microsoft.com/download/dotnet-core/2.1)** . Al instalar el SDK, se agregará la cadena de herramientas `dotnet` a la variable de entorno PATH.</span><span class="sxs-lookup"><span data-stu-id="6acbb-107">Download and install the **[.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1)** - installing the SDK will add the `dotnet` toolchain to your path.</span></span> <span data-ttu-id="6acbb-108">Se admiten las versiones de .NET Core 2.1, 2.2 y 3.1.</span><span class="sxs-lookup"><span data-stu-id="6acbb-108">.NET Core 2.1, 2.2 and 3.1 are supported.</span></span>
  2. <span data-ttu-id="6acbb-109">Instale **[Visual Studio 2019](https://www.visualstudio.com/downloads/)** (versión 16.3 o posterior).</span><span class="sxs-lookup"><span data-stu-id="6acbb-109">Install **[Visual Studio 2019](https://www.visualstudio.com/downloads/)** (Version 16.3 or later).</span></span> <span data-ttu-id="6acbb-110">La versión Community es completamente gratis.</span><span class="sxs-lookup"><span data-stu-id="6acbb-110">The Community version is completely free.</span></span> <span data-ttu-id="6acbb-111">Al configurar la instalación, incluya al menos estos componentes:</span><span class="sxs-lookup"><span data-stu-id="6acbb-111">When configuring your installation, include these components at minimum:</span></span>
     * <span data-ttu-id="6acbb-112">Desarrollo de escritorio de .NET</span><span class="sxs-lookup"><span data-stu-id="6acbb-112">.NET desktop development</span></span>
       * <span data-ttu-id="6acbb-113">Todos los componentes necesarios</span><span class="sxs-lookup"><span data-stu-id="6acbb-113">All Required Components</span></span>
         * <span data-ttu-id="6acbb-114">Herramientas de desarrollo de .NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="6acbb-114">.NET Framework 4.6.1 Development Tools</span></span>
     * <span data-ttu-id="6acbb-115">Desarrollo multiplataforma de .NET Core</span><span class="sxs-lookup"><span data-stu-id="6acbb-115">.NET Core cross-platform development</span></span>
       * <span data-ttu-id="6acbb-116">Todos los componentes necesarios</span><span class="sxs-lookup"><span data-stu-id="6acbb-116">All Required Components</span></span>
  3. <span data-ttu-id="6acbb-117">Instale **[Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)** .</span><span class="sxs-lookup"><span data-stu-id="6acbb-117">Install **[Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)**.</span></span>
     - <span data-ttu-id="6acbb-118">Seleccione la versión adecuada según su sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="6acbb-118">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="6acbb-119">Por ejemplo, *jdk-8u201-windows-x64.exe* si el equipo es Windows x64.</span><span class="sxs-lookup"><span data-stu-id="6acbb-119">For example, *jdk-8u201-windows-x64.exe* for Windows x64 machine.</span></span>
     - <span data-ttu-id="6acbb-120">Use el instalador para realizar la instalación y compruebe que puede ejecutar `java` desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="6acbb-120">Install using the installer and verify you are able to run `java` from your command line.</span></span>
  4. <span data-ttu-id="6acbb-121">Instale **[Apache Maven 3.6.0+](https://maven.apache.org/download.cgi)** .</span><span class="sxs-lookup"><span data-stu-id="6acbb-121">Install **[Apache Maven 3.6.0+](https://maven.apache.org/download.cgi)**.</span></span>
     - <span data-ttu-id="6acbb-122">Descargue [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.zip).</span><span class="sxs-lookup"><span data-stu-id="6acbb-122">Download [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.zip).</span></span>
     - <span data-ttu-id="6acbb-123">Extraiga en un directorio local.</span><span class="sxs-lookup"><span data-stu-id="6acbb-123">Extract to a local directory.</span></span> <span data-ttu-id="6acbb-124">Por ejemplo, \*C:\bin\apache-maven-3.6.0\*.</span><span class="sxs-lookup"><span data-stu-id="6acbb-124">For example, \*C:\bin\apache-maven-3.6.0\*.</span></span>
     - <span data-ttu-id="6acbb-125">Agregue Apache Maven a la [variable de entorno PATH](https://www.java.com/en/download/help/path.xml).</span><span class="sxs-lookup"><span data-stu-id="6acbb-125">Add Apache Maven to your [PATH environment variable](https://www.java.com/en/download/help/path.xml).</span></span> <span data-ttu-id="6acbb-126">Por ejemplo, *C:\bin\apache-maven-3.6.0\bin*.</span><span class="sxs-lookup"><span data-stu-id="6acbb-126">For example, *C:\bin\apache-maven-3.6.0\bin*.</span></span>
     - <span data-ttu-id="6acbb-127">Confirme que puede ejecutar `mvn` desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="6acbb-127">Verify you are able to run `mvn` from your command-line.</span></span>
  5. <span data-ttu-id="6acbb-128">Instale **[Apache Spark 2.3+](https://spark.apache.org/downloads.html)** .</span><span class="sxs-lookup"><span data-stu-id="6acbb-128">Install **[Apache Spark 2.3+](https://spark.apache.org/downloads.html)**.</span></span>
     - <span data-ttu-id="6acbb-129">Descargue [Apache Spark 2.3+](https://spark.apache.org/downloads.html) y extráigalo en una carpeta local (por ejemplo, *C:\bin\spark-2.3.2-bin-hadoop2.7\*), mediante [7-zip](https://www.7-zip.org/). (Las versiones compatibles de Spark son 2.3.* , 2.4.0, 2.4.1, 2.4.3 y 2.4.4)</span><span class="sxs-lookup"><span data-stu-id="6acbb-129">Download [Apache Spark 2.3+](https://spark.apache.org/downloads.html) and extract it into a local folder (for example, *C:\bin\spark-2.3.2-bin-hadoop2.7\*) using [7-zip](https://www.7-zip.org/). (The supported spark versions are 2.3.*, 2.4.0, 2.4.1, 2.4.3 and 2.4.4)</span></span>
     - <span data-ttu-id="6acbb-130">Agregue una [variable de entorno nueva](https://www.java.com/en/download/help/path.xml) `SPARK_HOME`.</span><span class="sxs-lookup"><span data-stu-id="6acbb-130">Add a [new environment variable](https://www.java.com/en/download/help/path.xml) `SPARK_HOME`.</span></span> <span data-ttu-id="6acbb-131">Por ejemplo, \*C:\bin\spark-2.3.2-bin-hadoop2.7\*.</span><span class="sxs-lookup"><span data-stu-id="6acbb-131">For example, \*C:\bin\spark-2.3.2-bin-hadoop2.7\*.</span></span>

       ```powershell
       set SPARK_HOME=C:\bin\spark-2.3.2-bin-hadoop2.7\
       ```

     - <span data-ttu-id="6acbb-132">Agregue Apache Spark a la [variable de entorno PATH](https://www.java.com/en/download/help/path.xml).</span><span class="sxs-lookup"><span data-stu-id="6acbb-132">Add Apache Spark to your [PATH environment variable](https://www.java.com/en/download/help/path.xml).</span></span> <span data-ttu-id="6acbb-133">Por ejemplo, *C:\bin\spark-2.3.2-bin-hadoop2.7\bin*.</span><span class="sxs-lookup"><span data-stu-id="6acbb-133">For example, *C:\bin\spark-2.3.2-bin-hadoop2.7\bin*.</span></span>

       ```powershell
       set PATH=%SPARK_HOME%\bin;%PATH%
       ```

     - <span data-ttu-id="6acbb-134">Confirme que puede ejecutar `spark-shell` desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="6acbb-134">Verify you are able to run `spark-shell` from your command-line.</span></span>
        <span data-ttu-id="6acbb-135">Salida de la consola de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6acbb-135">Sample console output:</span></span>

        ```output
        Welcome to
              ____              __
             / __/__  ___ _____/ /__
            _\ \/ _ \/ _ `/ __/  '_/
           /___/ .__/\_,_/_/ /_/\_\   version 2.3.2
              /_/

        Using Scala version 2.11.8 (Java HotSpot(TM) 64-Bit Server VM, Java 1.8.0_201)
        Type in expressions to have them evaluated.
        Type :help for more information.

        scala> sc
        res0: org.apache.spark.SparkContext = org.apache.spark.SparkContext@6eaa6b0c
        ```

        </details>

  6. <span data-ttu-id="6acbb-136">Instale **[WinUtils](https://github.com/steveloughran/winutils)** .</span><span class="sxs-lookup"><span data-stu-id="6acbb-136">Install **[WinUtils](https://github.com/steveloughran/winutils)**.</span></span>
     - <span data-ttu-id="6acbb-137">Descargue el archivo binario `winutils.exe` del [repositorio de WinUtils](https://github.com/steveloughran/winutils).</span><span class="sxs-lookup"><span data-stu-id="6acbb-137">Download `winutils.exe` binary from [WinUtils repository](https://github.com/steveloughran/winutils).</span></span> <span data-ttu-id="6acbb-138">Debe seleccionar la versión de Hadoop con la que se ha compilado la distribución de Spark.</span><span class="sxs-lookup"><span data-stu-id="6acbb-138">You should select the version of Hadoop the Spark distribution was compiled with.</span></span> <span data-ttu-id="6acbb-139">Por ejemplo, use hadoop-2.7.1 para Spark 2.3.2.</span><span class="sxs-lookup"><span data-stu-id="6acbb-139">For exammple, use hadoop-2.7.1 for Spark 2.3.2.</span></span>
     - <span data-ttu-id="6acbb-140">Guarde el archivo binario `winutils.exe` en el directorio que elija.</span><span class="sxs-lookup"><span data-stu-id="6acbb-140">Save `winutils.exe` binary to a directory of your choice.</span></span> <span data-ttu-id="6acbb-141">Por ejemplo, *C:\hadoop\bin*.</span><span class="sxs-lookup"><span data-stu-id="6acbb-141">For example, *C:\hadoop\bin*.</span></span>
     - <span data-ttu-id="6acbb-142">Establezca `HADOOP_HOME` para reflejar el directorio con winutils.exe (sin bin).</span><span class="sxs-lookup"><span data-stu-id="6acbb-142">Set `HADOOP_HOME` to reflect the directory with winutils.exe (without bin).</span></span> <span data-ttu-id="6acbb-143">Por ejemplo, con la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="6acbb-143">For instance, using command-line:</span></span>

       ```powershell
       set HADOOP_HOME=C:\hadoop
       ```

     - <span data-ttu-id="6acbb-144">Establezca la variable de entorno PATH para que incluya `%HADOOP_HOME%\bin`.</span><span class="sxs-lookup"><span data-stu-id="6acbb-144">Set PATH environment variable to include `%HADOOP_HOME%\bin`.</span></span> <span data-ttu-id="6acbb-145">Por ejemplo, con la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="6acbb-145">For instance, using command line:</span></span>

       ```powershell
       set PATH=%HADOOP_HOME%\bin;%PATH%
       ```

<span data-ttu-id="6acbb-146">Asegúrese de que puede ejecutar `dotnet`, `java`, `mvn`, `spark-shell` desde la línea de comandos antes de pasar a la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="6acbb-146">Make sure you are able to run `dotnet`, `java`, `mvn`, `spark-shell` from your command line before you move to the next section.</span></span> <span data-ttu-id="6acbb-147">¿Cree que hay una mejor manera de hacerlo?</span><span class="sxs-lookup"><span data-stu-id="6acbb-147">Feel there is a better way?</span></span> <span data-ttu-id="6acbb-148">[Abra una incidencia](https://github.com/dotnet/spark/issues) y háganos llegar sus comentarios.</span><span class="sxs-lookup"><span data-stu-id="6acbb-148">[Open an issue](https://github.com/dotnet/spark/issues) and feel free to contribute.</span></span>

> [!NOTE]
> <span data-ttu-id="6acbb-149">Es posible que sea necesaria una instancia nueva de la línea de comandos si se actualizaran las variables de entorno.</span><span class="sxs-lookup"><span data-stu-id="6acbb-149">A new instance of the command line may be required if any environment variables were updated.</span></span>

## <a name="build"></a><span data-ttu-id="6acbb-150">Compilar</span><span class="sxs-lookup"><span data-stu-id="6acbb-150">Build</span></span>

<span data-ttu-id="6acbb-151">En el resto de esta guía, deberá haber clonado el repositorio de .NET para Apache Spark en la máquina.</span><span class="sxs-lookup"><span data-stu-id="6acbb-151">For the remainder of this guide, you will need to have cloned the .NET for Apache Spark repository into your machine.</span></span> <span data-ttu-id="6acbb-152">Puede elegir cualquier ubicación para el repositorio clonado.</span><span class="sxs-lookup"><span data-stu-id="6acbb-152">You can choose any location for the cloned repository.</span></span> <span data-ttu-id="6acbb-153">Por ejemplo, \*C:\github\dotnet-spark\*.</span><span class="sxs-lookup"><span data-stu-id="6acbb-153">For example, \*C:\github\dotnet-spark\*.</span></span>

```bash
git clone https://github.com/dotnet/spark.git C:\github\dotnet-spark
```

### <a name="build-net-for-apache-spark-scala-extensions-layer"></a><span data-ttu-id="6acbb-154">Creación de la capa de extensiones de Scala de .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="6acbb-154">Build .NET for Apache Spark Scala extensions layer</span></span>

<span data-ttu-id="6acbb-155">Cuando se envía una aplicación de .NET, .NET para Apache Spark escribe en Scala la lógica necesaria que informa a Apache Spark cómo administrar las solicitudes (por ejemplo, solicitud para crear una sesión de Spark, solicitud para transferir datos desde el lado de .NET al lado de JVM, etc.).</span><span class="sxs-lookup"><span data-stu-id="6acbb-155">When you submit a .NET application, .NET for Apache Spark has the necessary logic written in Scala that informs Apache Spark how to handle your requests (for example, request to create a new Spark Session, request to transfer data from .NET side to JVM side etc.).</span></span> <span data-ttu-id="6acbb-156">Esta lógica se puede encontrar en el [código fuente de Scala de .NET para Spark](https://github.com/dotnet/spark/tree/master/src/scala).</span><span class="sxs-lookup"><span data-stu-id="6acbb-156">This logic can be found in the [.NET for Spark Scala Source Code](https://github.com/dotnet/spark/tree/master/src/scala).</span></span>

<span data-ttu-id="6acbb-157">Independientemente de si usa .NET Framework o .NET Core, tendrá que crear la capa de extensiones de Scala de .NET para Apache Spark:</span><span class="sxs-lookup"><span data-stu-id="6acbb-157">Regardless of whether you are using .NET Framework or .NET Core, you will need to build the .NET for Apache Spark Scala extension layer:</span></span>

```powershell
cd src\scala
mvn clean package
```

<span data-ttu-id="6acbb-158">Debería ver los archivos JAR creados para las versiones compatibles de Spark:</span><span class="sxs-lookup"><span data-stu-id="6acbb-158">You should see JARs created for the supported Spark versions:</span></span>

* `microsoft-spark-2.3.x\target\microsoft-spark-2.3.x-<version>.jar`
* `microsoft-spark-2.4.x\target\microsoft-spark-2.4.x-<version>.jar`

### <a name="build-the-net-for-spark-sample-applications"></a><span data-ttu-id="6acbb-159">Compilación de las aplicaciones de ejemplo de .NET para Spark</span><span class="sxs-lookup"><span data-stu-id="6acbb-159">Build the .NET for Spark sample applications</span></span>

<span data-ttu-id="6acbb-160">En esta sección se explica cómo compilar las [aplicaciones de ejemplo](https://github.com/dotnet/spark/tree/master/examples) de .NET para Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="6acbb-160">This section explains how to build the [sample applications](https://github.com/dotnet/spark/tree/master/examples) for .NET for Apache Spark.</span></span> <span data-ttu-id="6acbb-161">Estos pasos lo ayudarán a comprender el proceso general de compilación de cualquier aplicación de .NET para Spark.</span><span class="sxs-lookup"><span data-stu-id="6acbb-161">These steps will help in understanding the overall building process for any .NET for Spark application.</span></span>

#### <a name="using-visual-studio-for-net-framework"></a><span data-ttu-id="6acbb-162">Uso de Visual Studio para .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6acbb-162">Using Visual Studio for .NET Framework</span></span>

  1. <span data-ttu-id="6acbb-163">Abra `src\csharp\Microsoft.Spark.sln` en Visual Studio y compile el proyecto `Microsoft.Spark.CSharp.Examples` en la carpeta `examples` (a su vez, esto compilará también el proyecto de enlaces de .NET).</span><span class="sxs-lookup"><span data-stu-id="6acbb-163">Open `src\csharp\Microsoft.Spark.sln` in Visual Studio and build the `Microsoft.Spark.CSharp.Examples` project under the `examples` folder (this will in turn build the .NET bindings project as well).</span></span> <span data-ttu-id="6acbb-164">Si quiere, puede escribir su propio código en el proyecto `Microsoft.Spark.Examples` (en este ejemplo, "input_file.json" es un archivo JSON con los datos con los que quiere crear la trama de datos):</span><span class="sxs-lookup"><span data-stu-id="6acbb-164">If you want, you can write your own code in the `Microsoft.Spark.Examples` project (the 'input_file.json' in this example is a json file with the data you want to create the dataframe with):</span></span>
  
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

     <span data-ttu-id="6acbb-165">Una vez que la compilación se realice correctamente, verá los archivos binarios adecuados en el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="6acbb-165">Once the build is successful, you will see the appropriate binaries produced in the output directory.</span></span>
     <span data-ttu-id="6acbb-166">Salida de la consola de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6acbb-166">Sample console output:</span></span>

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

#### <a name="using-net-core-cli-for-net-core"></a><span data-ttu-id="6acbb-167">Uso de la CLI de .NET Core para .NET Core</span><span class="sxs-lookup"><span data-stu-id="6acbb-167">Using .NET Core CLI for .NET Core</span></span>

> [!NOTE]
> <span data-ttu-id="6acbb-168">Actualmente, estamos trabajando en automatizar las compilaciones de .NET Core de .NET para Spark.</span><span class="sxs-lookup"><span data-stu-id="6acbb-168">We are currently working on automating .NET Core builds for Spark .NET.</span></span> <span data-ttu-id="6acbb-169">Hasta entonces, agradecemos su paciencia al realizar algunos de los pasos manualmente.</span><span class="sxs-lookup"><span data-stu-id="6acbb-169">Until then, we appreciate your patience in performing some of the steps manually.</span></span>

  1. <span data-ttu-id="6acbb-170">Compile el trabajo:</span><span class="sxs-lookup"><span data-stu-id="6acbb-170">Build the worker:</span></span>

      ```powershell
      cd C:\github\dotnet-spark\src\csharp\Microsoft.Spark.Worker\
      dotnet publish -f netcoreapp2.1 -r win10-x64
      ```

      <span data-ttu-id="6acbb-171">Salida de la consola de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6acbb-171">Sample console output:</span></span>

      ```powershell
      PS C:\github\dotnet-spark\src\csharp\Microsoft.Spark.Worker> dotnet publish -f netcoreapp2.1 -r win10-x64
      Microsoft (R) Build Engine version 16.0.462+g62fb89029d for .NET Core
      Copyright (C) Microsoft Corporation. All rights reserved.

        Restore completed in 299.95 ms for C:\github\dotnet-spark\src\csharp\Microsoft.Spark\Microsoft.Spark.csproj.
        Restore completed in 306.62 ms for C:\github\dotnet-spark\src\csharp\Microsoft.Spark.Worker\Microsoft.Spark.Worker.csproj.
        Microsoft.Spark -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark\Debug\netstandard2.0\Microsoft.Spark.dll
        Microsoft.Spark.Worker -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\Microsoft.Spark.Worker.dll
        Microsoft.Spark.Worker -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\publish\
      ```

  2. <span data-ttu-id="6acbb-172">Compile los ejemplos:</span><span class="sxs-lookup"><span data-stu-id="6acbb-172">Build the samples:</span></span>

      ```powershell
      cd C:\github\dotnet-spark\examples\Microsoft.Spark.CSharp.Examples\
      dotnet publish -f netcoreapp2.1 -r win10-x64
      ```

      <span data-ttu-id="6acbb-173">Salida de la consola de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6acbb-173">Sample console output:</span></span>

      ```powershell
      PS C:\github\dotnet-spark\examples\Microsoft.Spark.CSharp.Examples> dotnet publish -f netcoreapp2.1 -r win10-x64
      Microsoft (R) Build Engine version 16.0.462+g62fb89029d for .NET Core
      Copyright (C) Microsoft Corporation. All rights reserved.

        Restore completed in 44.22 ms for C:\github\dotnet-spark\src\csharp\Microsoft.Spark\Microsoft.Spark.csproj.
        Restore completed in 336.94 ms for C:\github\dotnet-spark\examples\Microsoft.Spark.CSharp.Examples\Microsoft.Spark.CSharp.Examples.csproj.
        Microsoft.Spark -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark\Debug\netstandard2.0\Microsoft.Spark.dll
        Microsoft.Spark.CSharp.Examples -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\Microsoft.Spark.CSharp.Examples.dll
        Microsoft.Spark.CSharp.Examples -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\publish\
      ```

## <a name="run-the-net-for-spark-sample-applications"></a><span data-ttu-id="6acbb-174">Ejecución de las aplicaciones de ejemplo de .NET para Spark</span><span class="sxs-lookup"><span data-stu-id="6acbb-174">Run the .NET for Spark sample applications</span></span>

<span data-ttu-id="6acbb-175">Una vez que se compilan los ejemplos, su ejecución se realizará a través de `spark-submit` independientemente de si el destino es .NET Framework o .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6acbb-175">Once you build the samples, running them will be through `spark-submit` regardless of whether you are targeting .NET Framework or .NET Core.</span></span> <span data-ttu-id="6acbb-176">Asegúrese de haber seguido la sección de [requisitos previos](#prerequisites) y de haber instalado Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="6acbb-176">Make sure you have followed the [prerequisites](#prerequisites) section and installed Apache Spark.</span></span>

  1. <span data-ttu-id="6acbb-177">Establezca la variable de entorno `DOTNET_WORKER_DIR` o `PATH` para incluir la ruta de acceso en la que se ha generado el binario `Microsoft.Spark.Worker` (por ejemplo, *C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.Worker\Debug\net461* para .NET Framework, *C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\publish* para .NET Core):</span><span class="sxs-lookup"><span data-stu-id="6acbb-177">Set the `DOTNET_WORKER_DIR` or `PATH` environment variable to include the path where the `Microsoft.Spark.Worker` binary has been generated (for example, *C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.Worker\Debug\net461* for .NET Framework, *C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\publish* for .NET Core):</span></span>

      ```powershell
      set DOTNET_WORKER_DIR=C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\publish
      ```
  
  2. <span data-ttu-id="6acbb-178">Abra Powershell y vaya al directorio en el que se haya generado el archivo binario de la aplicación (por ejemplo, *C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\net461* para .NET Framework, *C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\publish* para .NET Core):</span><span class="sxs-lookup"><span data-stu-id="6acbb-178">Open Powershell and go to the directory where your app binary has been generated (for example, *C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\net461* for .NET Framework, *C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\publish* for .NET Core):</span></span>

      ```powershell
      cd C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\publish
      ```

  3. <span data-ttu-id="6acbb-179">La ejecución de la aplicación sigue la estructura básica:</span><span class="sxs-lookup"><span data-stu-id="6acbb-179">Running your app follows the basic structure:</span></span>

     ```powershell
     spark-submit.cmd `
       [--jars <any-jars-your-app-is-dependent-on>] `
       --class org.apache.spark.deploy.dotnet.DotnetRunner `
       --master local `
       <path-to-microsoft-spark-jar> `
       <path-to-your-app-exe> <argument(s)-to-your-app>
     ```

     <span data-ttu-id="6acbb-180">Estos son algunos ejemplos que se pueden ejecutar:</span><span class="sxs-lookup"><span data-stu-id="6acbb-180">Here are some examples you can run:</span></span>

     - <span data-ttu-id="6acbb-181">**[Microsoft.Spark.Examples.Sql.Batch.Basic](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/Basic.cs)**</span><span class="sxs-lookup"><span data-stu-id="6acbb-181">**[Microsoft.Spark.Examples.Sql.Batch.Basic](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/Basic.cs)**</span></span>

         ```powershell
         spark-submit.cmd `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Batch.Basic %SPARK_HOME%\examples\src\main\resources\people.json
         ```

     - <span data-ttu-id="6acbb-182">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredNetworkWordCount](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="6acbb-182">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredNetworkWordCount](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs)**</span></span>

         ```powershell
         spark-submit.cmd `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredNetworkWordCount localhost 9999
         ```

     - <span data-ttu-id="6acbb-183">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (accesible por Maven)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="6acbb-183">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (maven accessible)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span></span>

         ```powershell
         spark-submit.cmd `
         --packages org.apache.spark:spark-sql-kafka-0-10_2.11:2.3.2 `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
         ```

     - <span data-ttu-id="6acbb-184">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (proporcionado por jars)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="6acbb-184">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (jars provided)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span></span>

         ```powershell
         spark-submit.cmd
         --jars path\to\net.jpountz.lz4\lz4-1.3.0.jar,path\to\org.apache.kafka\kafka-clients-0.10.0.1.jar,path\to\org.apache.spark\spark-sql-kafka-0-10_2.11-2.3.2.jar,`path\to\org.slf4j\slf4j-api-1.7.6.jar,path\to\org.spark-project.spark\unused-1.0.0.jar,path\to\org.xerial.snappy\snappy-java-1.1.2.6.jar `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
          ```
