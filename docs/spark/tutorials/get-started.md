---
title: Introducción a .NET para Apache Spark
description: Sepa cómo ejecutar una aplicación .NET para Apache Spark con .NET Core en Windows.
ms.date: 11/04/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 679ee7660e96504768a781e1e384acab80362736
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743200"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a><span data-ttu-id="e5163-103">Tutorial: Introducción a .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="e5163-103">Tutorial: Get started with .NET for Apache Spark</span></span>

<span data-ttu-id="e5163-104">En este tutorial aprenderá a ejecutar una aplicación .NET para Apache Spark con .NET Core en Windows.</span><span class="sxs-lookup"><span data-stu-id="e5163-104">This tutorial teaches you how to run a .NET for Apache Spark app using .NET Core on Windows.</span></span>

<span data-ttu-id="e5163-105">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="e5163-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="e5163-106">Preparar el entorno de Windows para .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="e5163-106">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="e5163-107">Implementar la primer aplicación .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="e5163-107">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="e5163-108">Compilar y ejecutar una aplicación .NET para Apache Spark sencilla</span><span class="sxs-lookup"><span data-stu-id="e5163-108">Build and run your simple .NET for Apache Spark application</span></span>

## <a name="prepare-your-environment"></a><span data-ttu-id="e5163-109">Preparación del entorno</span><span class="sxs-lookup"><span data-stu-id="e5163-109">Prepare your environment</span></span>

<span data-ttu-id="e5163-110">Antes de comenzar a escribir la aplicación, debe configurar algunas dependencias de requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="e5163-110">Before you begin writing your app, you need to set up some prerequisite dependencies.</span></span> <span data-ttu-id="e5163-111">Si puede ejecutar `dotnet`, `java`, `mvn`, `spark-shell` desde el entorno de línea de comandos, el entorno ya está preparado y puede ir directamente a la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="e5163-111">If you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line environment, then your environment is already prepared and you can skip to the next section.</span></span> <span data-ttu-id="e5163-112">Si no puede ejecutar alguno o ninguno de los comandos, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="e5163-112">If you cannot run any or all of the commands, do the following steps.</span></span>

### <a name="1-install-net"></a><span data-ttu-id="e5163-113">1. Instalación de .NET</span><span class="sxs-lookup"><span data-stu-id="e5163-113">1. Install .NET</span></span>

<span data-ttu-id="e5163-114">Para empezar a compilar aplicaciones .NET, debe descargar e instalar el SDK (kit de desarrollo de software) de .NET.</span><span class="sxs-lookup"><span data-stu-id="e5163-114">To start building .NET apps, you need to download and install the .NET SDK (Software Development Kit).</span></span>

<span data-ttu-id="e5163-115">Descargue e instale el [SDK de .NET Core](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span><span class="sxs-lookup"><span data-stu-id="e5163-115">Download and install the [.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span> <span data-ttu-id="e5163-116">Al instalar el SDK, se agrega la cadena de herramientas `dotnet` a la variable de entorno PATH.</span><span class="sxs-lookup"><span data-stu-id="e5163-116">Installing the SDK adds the `dotnet` toolchain to your PATH.</span></span>

<span data-ttu-id="e5163-117">Una vez instalado el SDK de .NET Core, abra un símbolo del sistema nuevo y ejecute `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="e5163-117">Once you've installed the .NET Core SDK, open a new command prompt and run `dotnet`.</span></span>

<span data-ttu-id="e5163-118">Si el comando se ejecuta e imprime información sobre cómo usar dotnet, puede pasar al paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="e5163-118">If the command runs and prints out information about how to use dotnet, can move to the next step.</span></span> <span data-ttu-id="e5163-119">Si recibe un error `'dotnet' is not recognized as an internal or external command`, asegúrese de que ha abierto un símbolo del sistema **nuevo** antes de ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="e5163-119">If you receive a `'dotnet' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt before running the command.</span></span>

### <a name="2-install-java"></a><span data-ttu-id="e5163-120">2. Instalación de Java</span><span class="sxs-lookup"><span data-stu-id="e5163-120">2. Install Java</span></span>

<span data-ttu-id="e5163-121">Instale [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).</span><span class="sxs-lookup"><span data-stu-id="e5163-121">Install [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).</span></span>

<span data-ttu-id="e5163-122">Seleccione la versión adecuada según su sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="e5163-122">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="e5163-123">Así, por ejemplo, seleccione **jdk-8u201-windows-x64.exe** si el equipo es Windows x64.</span><span class="sxs-lookup"><span data-stu-id="e5163-123">For example, select **jdk-8u201-windows-x64.exe** for a Windows x64 machine.</span></span> <span data-ttu-id="e5163-124">Después, use el comando `java` para comprobar la instalación.</span><span class="sxs-lookup"><span data-stu-id="e5163-124">Then, use the command `java` to verify the installation.</span></span>

![Descarga de Java](https://dotnet.microsoft.com/static/images/java-jdk-downloads-windows.png?v=6BbJHoNyDO-PyYVciImr5wzh2AW_YHNcyb3p093AwPA)

### <a name="3-install-7-zip"></a><span data-ttu-id="e5163-126">3. Instalación de 7-zip</span><span class="sxs-lookup"><span data-stu-id="e5163-126">3. Install 7-zip</span></span>

<span data-ttu-id="e5163-127">Apache Spark se descarga como un archivo .tgz comprimido.</span><span class="sxs-lookup"><span data-stu-id="e5163-127">Apache Spark is downloaded as a compressed .tgz file.</span></span> <span data-ttu-id="e5163-128">Use un programa de extracción, como 7-zip, para extraer el archivo.</span><span class="sxs-lookup"><span data-stu-id="e5163-128">Use an extraction program, like 7-zip, to extract the file.</span></span>

* <span data-ttu-id="e5163-129">Visite [la página de descargas de 7-zip](https://www.7-zip.org/).</span><span class="sxs-lookup"><span data-stu-id="e5163-129">Visit [7-Zip downloads](https://www.7-zip.org/).</span></span>
* <span data-ttu-id="e5163-130">En la primera tabla de la página, seleccione la descarga x86 de 32 bits o x64 de 64 bits, en función del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="e5163-130">In the first table on the page, select the 32-bit x86 or 64-bit x64 download, depending on your operating system.</span></span>
* <span data-ttu-id="e5163-131">Una vez completada la descarga, ejecute el instalador.</span><span class="sxs-lookup"><span data-stu-id="e5163-131">When the download completes, run the installer.</span></span>

![Descarga de 7Zip](https://dotnet.microsoft.com/static/images/7-zip-downloads.png?v=W6qWtFC1tTMKv3YGXz7lBa9F3M22uWyTvkMmunyroNk)

### <a name="4-install-apache-spark"></a><span data-ttu-id="e5163-133">4. Instalación de Apache Spark</span><span class="sxs-lookup"><span data-stu-id="e5163-133">4. Install Apache Spark</span></span>

<span data-ttu-id="e5163-134">[Descargue e instale](https://spark.apache.org/downloads.html) Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="e5163-134">[Download and install Apache Spark](https://spark.apache.org/downloads.html).</span></span> <span data-ttu-id="e5163-135">Tendrá que seleccionar entre la versión 2.3.\* o 2.4.0, 2.4.1, 2.4.3, o bien 2.4.4 (.NET para Apache Spark no es compatible con otras versiones de Apache Spark).</span><span class="sxs-lookup"><span data-stu-id="e5163-135">You'll need to select from version 2.3.\* or 2.4.0, 2.4.1, 2.4.3, or 2.4.4 (.NET for Apache Spark is not compatible with other versions of Apache Spark).</span></span>

<span data-ttu-id="e5163-136">En los comandos que se usan en los pasos siguientes se supone que ha [descargado e instalado Apache Spark 2.4.1](https://archive.apache.org/dist/spark/spark-2.4.1/spark-2.4.1-bin-hadoop2.7.tgz).</span><span class="sxs-lookup"><span data-stu-id="e5163-136">The commands used in the following steps assume you have [downloaded and installed Apache Spark 2.4.1](https://archive.apache.org/dist/spark/spark-2.4.1/spark-2.4.1-bin-hadoop2.7.tgz).</span></span> <span data-ttu-id="e5163-137">Si prefiere usar otra versión, reemplace **2.4.1** por el número de versión adecuado.</span><span class="sxs-lookup"><span data-stu-id="e5163-137">If you wish to use a different version, replace **2.4.1** with the appropriate version number.</span></span> <span data-ttu-id="e5163-138">Después, extraiga el archivo **.tar** y los archivos de Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="e5163-138">Then, extract the **.tar** file and the Apache Spark files.</span></span>

<span data-ttu-id="e5163-139">Para extraer el archivo **.tar** anidado:</span><span class="sxs-lookup"><span data-stu-id="e5163-139">To extract the nested **.tar** file:</span></span>

* <span data-ttu-id="e5163-140">Busque el archivo **spark-2.4.1-bin-hadoop2.7.tgz** que ha descargado.</span><span class="sxs-lookup"><span data-stu-id="e5163-140">Locate the **spark-2.4.1-bin-hadoop2.7.tgz** file that you downloaded.</span></span>
* <span data-ttu-id="e5163-141">Haga clic con el botón derecho en el archivo y seleccione **7-Zip -> Extraer aquí**.</span><span class="sxs-lookup"><span data-stu-id="e5163-141">Right click on the file and select **7-Zip -> Extract here**.</span></span>
* <span data-ttu-id="e5163-142">Se creará **spark-2.4.1-bin-hadoop2.7.tar** junto con el archivo **.tgz** que ha descargado.</span><span class="sxs-lookup"><span data-stu-id="e5163-142">**spark-2.4.1-bin-hadoop2.7.tar** is created alongside the **.tgz** file you downloaded.</span></span>

<span data-ttu-id="e5163-143">Para extraer los archivos de Apache Spark:</span><span class="sxs-lookup"><span data-stu-id="e5163-143">To extract the Apache Spark files:</span></span>

* <span data-ttu-id="e5163-144">Haga clic con el botón derecho en **spark-2.4.1-bin-hadoop2.7.tar** y seleccione **7-Zip -> Extraer archivos...**</span><span class="sxs-lookup"><span data-stu-id="e5163-144">Right click on **spark-2.4.1-bin-hadoop2.7.tar** and select **7-Zip -> Extract files...**</span></span>
* <span data-ttu-id="e5163-145">Escriba **C:\bin** en el campo **Extraer en**.</span><span class="sxs-lookup"><span data-stu-id="e5163-145">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="e5163-146">Desactive la casilla situada debajo del campo **Extraer en**.</span><span class="sxs-lookup"><span data-stu-id="e5163-146">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="e5163-147">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e5163-147">Select **OK**.</span></span>
* <span data-ttu-id="e5163-148">Los archivos de Apache Spark se extraen en C:\bin\spark-2.4.1-bin-hadoop2.7\.</span><span class="sxs-lookup"><span data-stu-id="e5163-148">The Apache Spark files are extracted to C:\bin\spark-2.4.1-bin-hadoop2.7\</span></span>

![Instalación de Spark](https://dotnet.microsoft.com/static/images/spark-extract-with-7-zip.png?v=YvjUv54LIxI9FbALPC3h8zSQdyMtK2-NKbFOliG-f8M)

<span data-ttu-id="e5163-150">Ejecute los comandos siguientes para establecer las variables de entorno que se usan para buscar Apache Spark:</span><span class="sxs-lookup"><span data-stu-id="e5163-150">Run the following commands to set the environment variables used to locate Apache Spark:</span></span>

```console
setx HADOOP_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
setx SPARK_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
```

<span data-ttu-id="e5163-151">Una vez que haya instalado todo y establecido las variables de entorno, abra un símbolo del sistema **nuevo** y ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="e5163-151">Once you've installed everything and set your environment variables, open a **new** command prompt and run the following command:</span></span>

`%SPARK_HOME%\bin\spark-submit --version`

<span data-ttu-id="e5163-152">Si el comando se ejecuta e imprime la información de versión, puede pasar al paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="e5163-152">If the command runs and prints version information, you can move to the next step.</span></span>

<span data-ttu-id="e5163-153">Si recibe un error `'spark-submit' is not recognized as an internal or external command`, asegúrese de que ha abierto un símbolo del sistema **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="e5163-153">If you receive a `'spark-submit' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt.</span></span>

### <a name="5-install-net-for-apache-spark"></a><span data-ttu-id="e5163-154">5. Instalación de .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="e5163-154">5. Install .NET for Apache Spark</span></span>

<span data-ttu-id="e5163-155">Descargue la versión [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) de la página de .NET para Apache Spark en GitHub.</span><span class="sxs-lookup"><span data-stu-id="e5163-155">Download the [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) release from the .NET for Apache Spark GitHub.</span></span> <span data-ttu-id="e5163-156">Por ejemplo, si se encuentra en un equipo Windows y planea usar .NET Core, [descargue la versión Windows x64 netcoreapp2.1](https://github.com/dotnet/spark/releases/download/v0.6.0/Microsoft.Spark.Worker.netcoreapp2.1.win-x64-0.6.0.zip).</span><span class="sxs-lookup"><span data-stu-id="e5163-156">For example if you're on a Windows machine and plan to use .NET Core, [download the Windows x64 netcoreapp2.1 release](https://github.com/dotnet/spark/releases/download/v0.6.0/Microsoft.Spark.Worker.netcoreapp2.1.win-x64-0.6.0.zip).</span></span>

<span data-ttu-id="e5163-157">Para extraer Microsoft.Spark.Worker:</span><span class="sxs-lookup"><span data-stu-id="e5163-157">To extract the Microsoft.Spark.Worker:</span></span>

* <span data-ttu-id="e5163-158">Busque el archivo **Microsoft.Spark.Worker.netcoreapp2.1.win-x64-0.6.0.zip** que ha descargado.</span><span class="sxs-lookup"><span data-stu-id="e5163-158">Locate the **Microsoft.Spark.Worker.netcoreapp2.1.win-x64-0.6.0.zip** file that you downloaded.</span></span>
* <span data-ttu-id="e5163-159">Haga clic con el botón derecho y seleccione **7-Zip -> Extraer archivos...** .</span><span class="sxs-lookup"><span data-stu-id="e5163-159">Right click and select **7-Zip -> Extract files...**.</span></span>
* <span data-ttu-id="e5163-160">Escriba **C:\bin** en el campo **Extraer en**.</span><span class="sxs-lookup"><span data-stu-id="e5163-160">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="e5163-161">Desactive la casilla situada debajo del campo **Extraer en**.</span><span class="sxs-lookup"><span data-stu-id="e5163-161">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="e5163-162">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e5163-162">Select **OK**.</span></span>

![Instalación de .NET Spark](https://dotnet.microsoft.com/static/images/dotnet-for-spark-extract-with-7-zip.png?v=jwCyum9mL0mGIi4V5zC7yuvLfcj1_nL-QFFD8TClhZk)

### <a name="6-install-winutils"></a><span data-ttu-id="e5163-164">6. Instalación de WinUtils</span><span class="sxs-lookup"><span data-stu-id="e5163-164">6. Install WinUtils</span></span>

<span data-ttu-id="e5163-165">.NET para Apache Spark requiere que se instale WinUtils junto a Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="e5163-165">.NET for Apache Spark requires WinUtils to be installed alongside Apache Spark.</span></span> <span data-ttu-id="e5163-166">[Descargue winutils.exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe).</span><span class="sxs-lookup"><span data-stu-id="e5163-166">[Download winutils.exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe).</span></span> <span data-ttu-id="e5163-167">Después, copie WinUtils en **C:\bin\spark-2.4.1-bin-hadoop2.7\bin**.</span><span class="sxs-lookup"><span data-stu-id="e5163-167">Then, copy WinUtils into **C:\bin\spark-2.4.1-bin-hadoop2.7\bin**.</span></span>

> [!NOTE]
> <span data-ttu-id="e5163-168">Si usa otra versión de Hadoop (anotada al final del nombre de la carpeta de instalación de Spark) [seleccione la versión de WinUtils](https://github.com/steveloughran/winutils) que sea compatible con la versión de Hadoop.</span><span class="sxs-lookup"><span data-stu-id="e5163-168">If you are using a different version of Hadoop, which is annotated at the end of your Spark install folder name, [select the version of WinUtils](https://github.com/steveloughran/winutils) that's compatible with your version of Hadoop.</span></span>

### <a name="7-set-dotnet_worker_dir-and-check-dependencies"></a><span data-ttu-id="e5163-169">7. Establecimiento de DOTNET_WORKER_DIR y comprobación de las dependencias</span><span class="sxs-lookup"><span data-stu-id="e5163-169">7. Set DOTNET_WORKER_DIR and check dependencies</span></span>

<span data-ttu-id="e5163-170">Ejecute el comando siguiente para establecer la variable de entorno `DOTNET_WORKER_DIR`, que las aplicaciones .NET usan para buscar .NET para Apache Spark:</span><span class="sxs-lookup"><span data-stu-id="e5163-170">Run the following command to set the `DOTNET_WORKER_DIR` Environment Variable, which is used by .NET apps to locate .NET for Apache Spark:</span></span>

`setx DOTNET_WORKER_DIR "C:\bin\Microsoft.Spark.Worker-0.6.0"`

<span data-ttu-id="e5163-171">Por último, confirme que puede ejecutar `dotnet`, `java`, `mvn`, `spark-shell` desde la línea de comandos antes de pasar a la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="e5163-171">Finally, double-check that you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line before you move to the next section.</span></span>

## <a name="write-a-net-for-apache-spark-app"></a><span data-ttu-id="e5163-172">Escritura de una aplicación de .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="e5163-172">Write a .NET for Apache Spark app</span></span>

### <a name="1-create-a-console-app"></a><span data-ttu-id="e5163-173">1. Crear una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="e5163-173">1. Create a console app</span></span>

<span data-ttu-id="e5163-174">En el símbolo del sistema, ejecute los comandos siguientes para crear una aplicación de consola:</span><span class="sxs-lookup"><span data-stu-id="e5163-174">In your command prompt, run the following commands to create a new console application:</span></span>

```console
dotnet new console -o mySparkApp
cd mySparkApp
```

<span data-ttu-id="e5163-175">El comando `dotnet` crea una aplicación `new` de tipo `console` de forma automática.</span><span class="sxs-lookup"><span data-stu-id="e5163-175">The `dotnet` command creates a `new` application of type `console` for you.</span></span> <span data-ttu-id="e5163-176">El parámetro `-o` crea un directorio denominado *mySparkApp* donde se almacena la aplicación y lo rellena con los archivos necesarios.</span><span class="sxs-lookup"><span data-stu-id="e5163-176">The `-o` parameter creates a directory named *mySparkApp* where your app is stored and populates it with the required files.</span></span> <span data-ttu-id="e5163-177">El comando `cd mySparkApp` cambia el directorio al directorio de la aplicación que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="e5163-177">The `cd mySparkApp` command changes the directory to the app directory you just created.</span></span>

### <a name="2-install-nuget-package"></a><span data-ttu-id="e5163-178">2. Instalación del paquete NuGet</span><span class="sxs-lookup"><span data-stu-id="e5163-178">2. Install NuGet package</span></span>

<span data-ttu-id="e5163-179">Para usar .NET para Apache Spark en una aplicación, instale el paquete Microsoft.Spark.</span><span class="sxs-lookup"><span data-stu-id="e5163-179">To use .NET for Apache Spark in an app, install the Microsoft.Spark package.</span></span> <span data-ttu-id="e5163-180">En el símbolo del sistema, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e5163-180">In your command prompt, run the following command:</span></span>

`dotnet add package Microsoft.Spark --version 0.6.0`

### <a name="3-code-your-app"></a><span data-ttu-id="e5163-181">3. Diseño del código de la aplicación</span><span class="sxs-lookup"><span data-stu-id="e5163-181">3. Code your app</span></span>

<span data-ttu-id="e5163-182">Abra *Program.cs* en Visual Studio Code o cualquier editor de texto, y reemplace todo el código por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e5163-182">Open *Program.cs* in Visual Studio Code, or any text editor, and replace all of the code with the following:</span></span>

```csharp
using Microsoft.Spark.Sql;

namespace MySparkApp
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a Spark session.
            var spark = SparkSession
                .Builder()
                .AppName("word_count_sample")
                .GetOrCreate();

            // Create initial DataFrame.
            DataFrame dataFrame = spark.Read().Text("input.txt");

            // Count words.
            var words = dataFrame
                .Select(Functions.Split(Functions.Col("value"), " ").Alias("words"))
                .Select(Functions.Explode(Functions.Col("words"))
                .Alias("word"))
                .GroupBy("word")
                .Count()
                .OrderBy(Functions.Col("count").Desc());

            // Show results.
            words.Show();

            // Stop Spark session.
            spark.Stop();
        }
    }
}
```

### <a name="4-add-data-file"></a><span data-ttu-id="e5163-183">4. Adición del archivo de datos</span><span class="sxs-lookup"><span data-stu-id="e5163-183">4. Add data file</span></span>

<span data-ttu-id="e5163-184">La aplicación procesa un archivo que contiene líneas de texto.</span><span class="sxs-lookup"><span data-stu-id="e5163-184">Your app processes a file containing lines of text.</span></span> <span data-ttu-id="e5163-185">Cree un archivo *input.txt* en el directorio *mySparkApp*, con el texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="e5163-185">Create an *input.txt* file in your *mySparkApp* directory, containing the following text:</span></span>

```text
Hello World
This .NET app uses .NET for Apache Spark
This .NET app counts words with Apache Spark
```

## <a name="run-your-net-for-apache-spark-app"></a><span data-ttu-id="e5163-186">Ejecución de la aplicación de .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="e5163-186">Run your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="e5163-187">Ejecute el comando siguiente para compilar la aplicación:</span><span class="sxs-lookup"><span data-stu-id="e5163-187">Run the following command to build your application:</span></span>

   ```dotnetcli
   dotnet build
   ```

2. <span data-ttu-id="e5163-188">Ejecute el comando siguiente para enviar la aplicación para que se ejecute en Apache Spark:</span><span class="sxs-lookup"><span data-stu-id="e5163-188">Run the following command to submit your application to run on Apache Spark:</span></span>

   ```powershell
   %SPARK_HOME%\bin\spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local bin\Debug\netcoreapp3.0\microsoft-spark-2.4.x-0.6.0.jar dotnet bin\Debug\netcoreapp3.0\mySparkApp.dll
   ```

3. <span data-ttu-id="e5163-189">Cuando la aplicación se ejecuta, los datos de recuento de palabras del archivo *input.txt* se escriben en la consola.</span><span class="sxs-lookup"><span data-stu-id="e5163-189">When your app runs, the word count data of the *input.txt* file is written to the console.</span></span>

<span data-ttu-id="e5163-190">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="e5163-190">Congratulations!</span></span> <span data-ttu-id="e5163-191">Ha creado y ejecutado correctamente una aplicación de .NET para Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="e5163-191">You successfully authored and ran a .NET for Apache Spark app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e5163-192">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="e5163-192">Next steps</span></span>

<span data-ttu-id="e5163-193">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="e5163-193">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="e5163-194">Preparar el entorno de Windows para .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="e5163-194">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="e5163-195">Implementar la primer aplicación .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="e5163-195">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="e5163-196">Compilar y ejecutar una aplicación .NET para Apache Spark sencilla</span><span class="sxs-lookup"><span data-stu-id="e5163-196">Build and run your simple .NET for Apache Spark application</span></span>

<span data-ttu-id="e5163-197">Para ver un vídeo en el que se explican los pasos anteriores, consulte la [serie de vídeos .NET para Apache Spark 101](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App).</span><span class="sxs-lookup"><span data-stu-id="e5163-197">To see a video explaining the steps above, checkout the [.NET for Apache Spark 101 video series](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App).</span></span>

<span data-ttu-id="e5163-198">Eche un vistazo a la página de recursos para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="e5163-198">Check out the resources page to learn more.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="e5163-199">Recursos de .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="e5163-199">.NET for Apache Spark Resources</span></span>](../resources/index.md)
