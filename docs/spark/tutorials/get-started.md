---
title: Introducción a .NET para Apache Spark
description: Descubra cómo ejecutar una aplicación .NET para Apache Spark con .NET Core en Windows, macOS y Ubuntu.
ms.date: 06/25/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: d7297b11a2b5b21420fcb2f0f9ae823cb29b88d1
ms.sourcegitcommit: ae2e8a61a93c5cf3f0035c59e6b064fa2f812d14
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "89359004"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a><span data-ttu-id="37b9a-103">Tutorial: Introducción a .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="37b9a-103">Tutorial: Get started with .NET for Apache Spark</span></span>

<span data-ttu-id="37b9a-104">En este tutorial aprenderá a ejecutar una aplicación .NET para Apache Spark con .NET Core en Windows, macOS y Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="37b9a-104">This tutorial teaches you how to run a .NET for Apache Spark app using .NET Core on Windows, macOS, and Ubuntu.</span></span>

<span data-ttu-id="37b9a-105">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="37b9a-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="37b9a-106">Preparar el entorno de .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="37b9a-106">Prepare your environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="37b9a-107">Implementar la primer aplicación .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="37b9a-107">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="37b9a-108">Compilar y ejecutar una aplicación .NET para Apache Spark sencilla</span><span class="sxs-lookup"><span data-stu-id="37b9a-108">Build and run your simple .NET for Apache Spark application</span></span>

[!INCLUDE [spark-preview-note](../../../includes/spark-preview-note.md)]

## <a name="prepare-your-environment"></a><span data-ttu-id="37b9a-109">Preparación del entorno</span><span class="sxs-lookup"><span data-stu-id="37b9a-109">Prepare your environment</span></span>

<span data-ttu-id="37b9a-110">Antes de comenzar a escribir la aplicación, debe configurar algunas dependencias de requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="37b9a-110">Before you begin writing your app, you need to set up some prerequisite dependencies.</span></span> <span data-ttu-id="37b9a-111">Si puede ejecutar `dotnet`, `java`, `mvn`, `spark-shell` desde el entorno de línea de comandos, el entorno ya está preparado y puede ir directamente a la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="37b9a-111">If you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line environment, then your environment is already prepared and you can skip to the next section.</span></span> <span data-ttu-id="37b9a-112">Si no puede ejecutar alguno o ninguno de los comandos, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="37b9a-112">If you cannot run any or all of the commands, do the following steps.</span></span>

### <a name="1-install-net"></a><span data-ttu-id="37b9a-113">1. Instalación de .NET</span><span class="sxs-lookup"><span data-stu-id="37b9a-113">1. Install .NET</span></span>

<span data-ttu-id="37b9a-114">Para empezar a compilar aplicaciones .NET, debe descargar e instalar el SDK (kit de desarrollo de software) de .NET.</span><span class="sxs-lookup"><span data-stu-id="37b9a-114">To start building .NET apps, you need to download and install the .NET SDK (Software Development Kit).</span></span>

<span data-ttu-id="37b9a-115">Descargue e instale el [SDK de .NET Core](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span><span class="sxs-lookup"><span data-stu-id="37b9a-115">Download and install the [.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span> <span data-ttu-id="37b9a-116">Al instalar el SDK, se agrega la cadena de herramientas `dotnet` a la variable de entorno PATH.</span><span class="sxs-lookup"><span data-stu-id="37b9a-116">Installing the SDK adds the `dotnet` toolchain to your PATH.</span></span>

<span data-ttu-id="37b9a-117">Una vez instalado el SDK de .NET Core, abra un símbolo del sistema o terminal nuevo y ejecute `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="37b9a-117">Once you've installed the .NET Core SDK, open a new command prompt or terminal and run `dotnet`.</span></span>

<span data-ttu-id="37b9a-118">Si el comando se ejecuta e imprime información sobre cómo usar dotnet, puede pasar al paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="37b9a-118">If the command runs and prints out information about how to use dotnet, can move to the next step.</span></span> <span data-ttu-id="37b9a-119">Si recibe un error `'dotnet' is not recognized as an internal or external command`, asegúrese de que ha abierto un símbolo del sistema o terminal **nuevo** antes de ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="37b9a-119">If you receive a `'dotnet' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt or terminal before running the command.</span></span>

### <a name="2-install-java"></a><span data-ttu-id="37b9a-120">2. Instalación de Java</span><span class="sxs-lookup"><span data-stu-id="37b9a-120">2. Install Java</span></span>

<span data-ttu-id="37b9a-121">Instale [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) para Windows y MacOS, o bien [OpenJDK 8](https://openjdk.java.net/install/) para Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="37b9a-121">Install [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) for Windows and macOS, or [OpenJDK 8](https://openjdk.java.net/install/) for Ubuntu.</span></span>

<span data-ttu-id="37b9a-122">Seleccione la versión adecuada según su sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="37b9a-122">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="37b9a-123">Por ejemplo, seleccione **jdk-8u201-windows-x64.exe** para una máquina Windows x64 (tal como se muestra debajo) o **jdk-8u231-macosx-x64.dmg** para macOS.</span><span class="sxs-lookup"><span data-stu-id="37b9a-123">For example, select **jdk-8u201-windows-x64.exe** for a Windows x64 machine (as shown below) or **jdk-8u231-macosx-x64.dmg** for macOS.</span></span> <span data-ttu-id="37b9a-124">Después, use el comando `java` para comprobar la instalación.</span><span class="sxs-lookup"><span data-stu-id="37b9a-124">Then, use the command `java` to verify the installation.</span></span>

![Descarga de Java](https://dotnet.microsoft.com/static/images/java-jdk-downloads-windows.png?v=6BbJHoNyDO-PyYVciImr5wzh2AW_YHNcyb3p093AwPA)

### <a name="3-install-compression-software"></a><span data-ttu-id="37b9a-126">3. Instalación de software de compresión</span><span class="sxs-lookup"><span data-stu-id="37b9a-126">3. Install compression software</span></span>

<span data-ttu-id="37b9a-127">Apache Spark se descarga como un archivo .tgz comprimido.</span><span class="sxs-lookup"><span data-stu-id="37b9a-127">Apache Spark is downloaded as a compressed .tgz file.</span></span> <span data-ttu-id="37b9a-128">Use un programa de extracción, como[7-Zip](https://www.7-zip.org/) o [WinZip](https://www.winzip.com/), para extraer el archivo.</span><span class="sxs-lookup"><span data-stu-id="37b9a-128">Use an extraction program, like [7-Zip](https://www.7-zip.org/) or [WinZip](https://www.winzip.com/), to extract the file.</span></span>

### <a name="4-install-apache-spark"></a><span data-ttu-id="37b9a-129">4. Instalación de Apache Spark</span><span class="sxs-lookup"><span data-stu-id="37b9a-129">4. Install Apache Spark</span></span>

<span data-ttu-id="37b9a-130">[Descargue e instale](https://spark.apache.org/downloads.html) Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="37b9a-130">[Download and install Apache Spark](https://spark.apache.org/downloads.html).</span></span> <span data-ttu-id="37b9a-131">Tendrá que seleccionar entre la versión 2.3.\* o 2.4.0, 2.4.1, 2.4.3, o bien 2.4.4 (.NET para Apache Spark no es compatible con otras versiones de Apache Spark).</span><span class="sxs-lookup"><span data-stu-id="37b9a-131">You'll need to select from version 2.3.\* or 2.4.0, 2.4.1, 2.4.3, or 2.4.4 (.NET for Apache Spark is not compatible with other versions of Apache Spark).</span></span>

<span data-ttu-id="37b9a-132">En los comandos que se usan en los pasos siguientes se supone que ha [descargado e instalado Apache Spark 2.4.1](https://archive.apache.org/dist/spark/spark-2.4.1/spark-2.4.1-bin-hadoop2.7.tgz).</span><span class="sxs-lookup"><span data-stu-id="37b9a-132">The commands used in the following steps assume you have [downloaded and installed Apache Spark 2.4.1](https://archive.apache.org/dist/spark/spark-2.4.1/spark-2.4.1-bin-hadoop2.7.tgz).</span></span> <span data-ttu-id="37b9a-133">Si prefiere usar otra versión, reemplace **2.4.1** por el número de versión adecuado.</span><span class="sxs-lookup"><span data-stu-id="37b9a-133">If you wish to use a different version, replace **2.4.1** with the appropriate version number.</span></span> <span data-ttu-id="37b9a-134">Después, extraiga el archivo **.tar** y los archivos de Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="37b9a-134">Then, extract the **.tar** file and the Apache Spark files.</span></span>

<span data-ttu-id="37b9a-135">Para extraer el archivo **.tar** anidado:</span><span class="sxs-lookup"><span data-stu-id="37b9a-135">To extract the nested **.tar** file:</span></span>

* <span data-ttu-id="37b9a-136">Busque el archivo **spark-2.4.1-bin-hadoop2.7.tgz** que ha descargado.</span><span class="sxs-lookup"><span data-stu-id="37b9a-136">Locate the **spark-2.4.1-bin-hadoop2.7.tgz** file that you downloaded.</span></span>
* <span data-ttu-id="37b9a-137">Haga clic con el botón derecho en el archivo y seleccione **7-Zip -> Extraer aquí**.</span><span class="sxs-lookup"><span data-stu-id="37b9a-137">Right click on the file and select **7-Zip -> Extract here**.</span></span>
* <span data-ttu-id="37b9a-138">Se creará **spark-2.4.1-bin-hadoop2.7.tar** junto con el archivo **.tgz** que ha descargado.</span><span class="sxs-lookup"><span data-stu-id="37b9a-138">**spark-2.4.1-bin-hadoop2.7.tar** is created alongside the **.tgz** file you downloaded.</span></span>

<span data-ttu-id="37b9a-139">Para extraer los archivos de Apache Spark:</span><span class="sxs-lookup"><span data-stu-id="37b9a-139">To extract the Apache Spark files:</span></span>

* <span data-ttu-id="37b9a-140">Haga clic con el botón derecho en **spark-2.4.1-bin-hadoop2.7.tar** y seleccione **7-Zip -> Extraer archivos...**</span><span class="sxs-lookup"><span data-stu-id="37b9a-140">Right click on **spark-2.4.1-bin-hadoop2.7.tar** and select **7-Zip -> Extract files...**</span></span>
* <span data-ttu-id="37b9a-141">Escriba **C:\bin** en el campo **Extraer en**.</span><span class="sxs-lookup"><span data-stu-id="37b9a-141">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="37b9a-142">Desactive la casilla situada debajo del campo **Extraer en**.</span><span class="sxs-lookup"><span data-stu-id="37b9a-142">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="37b9a-143">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="37b9a-143">Select **OK**.</span></span>
* <span data-ttu-id="37b9a-144">Los archivos de Apache Spark se extraen en C:\bin\spark-2.4.1-bin-hadoop2.7\.</span><span class="sxs-lookup"><span data-stu-id="37b9a-144">The Apache Spark files are extracted to C:\bin\spark-2.4.1-bin-hadoop2.7\</span></span>

![Instalación de Spark](https://dotnet.microsoft.com/static/images/spark-extract-with-7-zip.png?v=YvjUv54LIxI9FbALPC3h8zSQdyMtK2-NKbFOliG-f8M)

<span data-ttu-id="37b9a-146">Ejecute los comandos siguientes para establecer las variables de entorno que se usan para buscar Apache Spark en **Windows**:</span><span class="sxs-lookup"><span data-stu-id="37b9a-146">Run the following commands to set the environment variables used to locate Apache Spark on **Windows**:</span></span>

```console
setx HADOOP_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
setx SPARK_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
```

<span data-ttu-id="37b9a-147">Ejecute los comandos siguientes para establecer las variables de entorno que se usan para buscar Apache Spark en **macOS** y **Ubuntu**:</span><span class="sxs-lookup"><span data-stu-id="37b9a-147">Run the following commands to set the environment variables used to locate Apache Spark on **macOS** and **Ubuntu**:</span></span>

```bash
export SPARK_HOME=~/bin/spark-2.4.1-bin-hadoop2.7/
export PATH="$SPARK_HOME/bin:$PATH"
source ~/.bashrc
```

<span data-ttu-id="37b9a-148">Una vez que se haya instalado todo y establecido las variables de entorno, abra un símbolo del sistema o terminal **nuevo** y ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="37b9a-148">Once you've installed everything and set your environment variables, open a **new** command prompt or terminal and run the following command:</span></span>

`%SPARK_HOME%\bin\spark-submit --version`

<span data-ttu-id="37b9a-149">Si el comando se ejecuta e imprime la información de versión, puede pasar al paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="37b9a-149">If the command runs and prints version information, you can move to the next step.</span></span>

<span data-ttu-id="37b9a-150">Si recibe un error `'spark-submit' is not recognized as an internal or external command`, asegúrese de que ha abierto un símbolo del sistema **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="37b9a-150">If you receive a `'spark-submit' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt.</span></span>

### <a name="5-install-net-for-apache-spark"></a><span data-ttu-id="37b9a-151">5. Instalación de .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="37b9a-151">5. Install .NET for Apache Spark</span></span>

<span data-ttu-id="37b9a-152">Descargue la versión [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) de la página de .NET para Apache Spark en GitHub.</span><span class="sxs-lookup"><span data-stu-id="37b9a-152">Download the [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) release from the .NET for Apache Spark GitHub.</span></span> <span data-ttu-id="37b9a-153">Por ejemplo, si se encuentra en una máquina Windows y planea usar .NET Core, [descargue la versión Windows x64 netcoreapp3.1](https://github.com/dotnet/spark/releases/download/v0.8.0/Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip).</span><span class="sxs-lookup"><span data-stu-id="37b9a-153">For example if you're on a Windows machine and plan to use .NET Core, [download the Windows x64 netcoreapp3.1 release](https://github.com/dotnet/spark/releases/download/v0.8.0/Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip).</span></span>

<span data-ttu-id="37b9a-154">Para extraer Microsoft.Spark.Worker:</span><span class="sxs-lookup"><span data-stu-id="37b9a-154">To extract the Microsoft.Spark.Worker:</span></span>

* <span data-ttu-id="37b9a-155">Busque el archivo **Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip** que ha descargado.</span><span class="sxs-lookup"><span data-stu-id="37b9a-155">Locate the **Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip** file that you downloaded.</span></span>
* <span data-ttu-id="37b9a-156">Haga clic con el botón derecho y seleccione **7-Zip -> Extraer archivos...** .</span><span class="sxs-lookup"><span data-stu-id="37b9a-156">Right click and select **7-Zip -> Extract files...**.</span></span>
* <span data-ttu-id="37b9a-157">Escriba **C:\bin** en el campo **Extraer en**.</span><span class="sxs-lookup"><span data-stu-id="37b9a-157">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="37b9a-158">Desactive la casilla situada debajo del campo **Extraer en**.</span><span class="sxs-lookup"><span data-stu-id="37b9a-158">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="37b9a-159">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="37b9a-159">Select **OK**.</span></span>

![Instalación de .NET Spark](https://dotnet.microsoft.com/static/images/dotnet-for-spark-extract-with-7-zip.png?v=jwCyum9mL0mGIi4V5zC7yuvLfcj1_nL-QFFD8TClhZk)

### <a name="6-install-winutils-windows-only"></a><span data-ttu-id="37b9a-161">6. Instalación de WinUtils (solo Windows)</span><span class="sxs-lookup"><span data-stu-id="37b9a-161">6. Install WinUtils (Windows only)</span></span>

<span data-ttu-id="37b9a-162">.NET para Apache Spark requiere que se instale WinUtils junto a Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="37b9a-162">.NET for Apache Spark requires WinUtils to be installed alongside Apache Spark.</span></span> <span data-ttu-id="37b9a-163">[Descargue winutils.exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe).</span><span class="sxs-lookup"><span data-stu-id="37b9a-163">[Download winutils.exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe).</span></span> <span data-ttu-id="37b9a-164">Después, copie WinUtils en **C:\bin\spark-2.4.1-bin-hadoop2.7\bin**.</span><span class="sxs-lookup"><span data-stu-id="37b9a-164">Then, copy WinUtils into **C:\bin\spark-2.4.1-bin-hadoop2.7\bin**.</span></span>

> [!NOTE]
> <span data-ttu-id="37b9a-165">Si usa otra versión de Hadoop (anotada al final del nombre de la carpeta de instalación de Spark) [seleccione la versión de WinUtils](https://github.com/steveloughran/winutils) que sea compatible con la versión de Hadoop.</span><span class="sxs-lookup"><span data-stu-id="37b9a-165">If you are using a different version of Hadoop, which is annotated at the end of your Spark install folder name, [select the version of WinUtils](https://github.com/steveloughran/winutils) that's compatible with your version of Hadoop.</span></span>

### <a name="7-set-dotnet_worker_dir-and-check-dependencies"></a><span data-ttu-id="37b9a-166">7. Establecimiento de DOTNET_WORKER_DIR y comprobación de las dependencias</span><span class="sxs-lookup"><span data-stu-id="37b9a-166">7. Set DOTNET_WORKER_DIR and check dependencies</span></span>

<span data-ttu-id="37b9a-167">Ejecute uno de los comandos siguientes para establecer la Variable de entorno `DOTNET_WORKER_DIR`, que las aplicaciones .NET usan con el fin de buscar .NET para Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="37b9a-167">Run one of the following commands to set the `DOTNET_WORKER_DIR` Environment Variable, which is used by .NET apps to locate .NET for Apache Spark.</span></span>

<span data-ttu-id="37b9a-168">En **Windows**, cree una [variable de entorno nueva](https://www.java.com/en/download/help/path.xml) llamada `DOTNET_WORKER_DIR` y establézcala en el directorio donde se ha descargado y extraído Microsoft.Spark.Worker (por ejemplo, `C:\bin\Microsoft.Spark.Worker\`).</span><span class="sxs-lookup"><span data-stu-id="37b9a-168">On **Windows**, create a [new environment variable](https://www.java.com/en/download/help/path.xml) `DOTNET_WORKER_DIR` and set it to the directory where you downloaded and extracted the Microsoft.Spark.Worker (for example, `C:\bin\Microsoft.Spark.Worker\`).</span></span>

<span data-ttu-id="37b9a-169">En **macOS**, cree una variable de entorno nueva mediante `export DOTNET_WORKER_DIR <your_path>` y establézcala en el directorio donde se ha descargado y extraído Microsoft.Spark.Worker (por ejemplo, *~/bin/Microsoft.Spark.Worker/* ).</span><span class="sxs-lookup"><span data-stu-id="37b9a-169">On **macOS**, create a new environment variable using `export DOTNET_WORKER_DIR <your_path>` and set it to the directory where you downloaded and extracted the Microsoft.Spark.Worker (for example, *~/bin/Microsoft.Spark.Worker/*).</span></span>

<span data-ttu-id="37b9a-170">En **Ubuntu**, cree una [variable de entorno nueva](https://help.ubuntu.com/community/EnvironmentVariables) llamada `DOTNET_WORKER_DIR` y establézcala en el directorio donde se ha descargado y extraído Microsoft.Spark.Worker (por ejemplo, *~/bin/Microsoft.Spark.Worker*).</span><span class="sxs-lookup"><span data-stu-id="37b9a-170">On **Ubuntu**, create a [new environment variable](https://help.ubuntu.com/community/EnvironmentVariables) `DOTNET_WORKER_DIR` and set it to the directory where you downloaded and extracted the Microsoft.Spark.Worker (for example, *~/bin/Microsoft.Spark.Worker*).</span></span>

<span data-ttu-id="37b9a-171">Por último, confirme que puede ejecutar `dotnet`, `java`, `mvn`, `spark-shell` desde la línea de comandos antes de pasar a la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="37b9a-171">Finally, double-check that you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line before you move to the next section.</span></span>

## <a name="write-a-net-for-apache-spark-app"></a><span data-ttu-id="37b9a-172">Escritura de una aplicación de .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="37b9a-172">Write a .NET for Apache Spark app</span></span>

### <a name="1-create-a-console-app"></a><span data-ttu-id="37b9a-173">1. Crear una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="37b9a-173">1. Create a console app</span></span>

<span data-ttu-id="37b9a-174">En el símbolo del sistema o terminal, ejecute los comandos siguientes para crear una aplicación de consola nueva:</span><span class="sxs-lookup"><span data-stu-id="37b9a-174">In your command prompt or terminal, run the following commands to create a new console application:</span></span>

```dotnetcli
dotnet new console -o mySparkApp
cd mySparkApp
```

<span data-ttu-id="37b9a-175">El comando `dotnet` crea una aplicación `new` de tipo `console` de forma automática.</span><span class="sxs-lookup"><span data-stu-id="37b9a-175">The `dotnet` command creates a `new` application of type `console` for you.</span></span> <span data-ttu-id="37b9a-176">El parámetro `-o` crea un directorio denominado *mySparkApp* donde se almacena la aplicación y lo rellena con los archivos necesarios.</span><span class="sxs-lookup"><span data-stu-id="37b9a-176">The `-o` parameter creates a directory named *mySparkApp* where your app is stored and populates it with the required files.</span></span> <span data-ttu-id="37b9a-177">El comando `cd mySparkApp` cambia el directorio al directorio de la aplicación que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="37b9a-177">The `cd mySparkApp` command changes the directory to the app directory you just created.</span></span>

### <a name="2-install-nuget-package"></a><span data-ttu-id="37b9a-178">2. Instalación del paquete NuGet</span><span class="sxs-lookup"><span data-stu-id="37b9a-178">2. Install NuGet package</span></span>

<span data-ttu-id="37b9a-179">Para usar .NET para Apache Spark en una aplicación, instale el paquete Microsoft.Spark.</span><span class="sxs-lookup"><span data-stu-id="37b9a-179">To use .NET for Apache Spark in an app, install the Microsoft.Spark package.</span></span> <span data-ttu-id="37b9a-180">En el símbolo del sistema o terminal, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="37b9a-180">In your command prompt or terminal, run the following command:</span></span>

`dotnet add package Microsoft.Spark --version 0.8.0`

### <a name="3-code-your-app"></a><span data-ttu-id="37b9a-181">3. Diseño del código de la aplicación</span><span class="sxs-lookup"><span data-stu-id="37b9a-181">3. Code your app</span></span>

<span data-ttu-id="37b9a-182">Abra *Program.cs* en Visual Studio Code o cualquier editor de texto, y reemplace todo el código por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="37b9a-182">Open *Program.cs* in Visual Studio Code, or any text editor, and replace all of the code with the following:</span></span>

```csharp
using Microsoft.Spark.Sql;

namespace MySparkApp
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a Spark session.
            SparkSession spark = SparkSession
                .Builder()
                .AppName("word_count_sample")
                .GetOrCreate();

            // Create initial DataFrame.
            DataFrame dataFrame = spark.Read().Text("input.txt");

            // Count words.
            DataFrame words = dataFrame
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

### <a name="4-create-and-add-a-data-file"></a><span data-ttu-id="37b9a-183">4. Creación y adición de un archivo de datos</span><span class="sxs-lookup"><span data-stu-id="37b9a-183">4. Create and add a data file</span></span>

<span data-ttu-id="37b9a-184">Abra el símbolo del sistema o terminal y vaya a la carpeta de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="37b9a-184">Open your command prompt or terminal and navigate into your app folder.</span></span>

```bash
cd <your-app-output-directory>
```

<span data-ttu-id="37b9a-185">La aplicación procesa un archivo que contiene líneas de texto.</span><span class="sxs-lookup"><span data-stu-id="37b9a-185">Your app processes a file containing lines of text.</span></span> <span data-ttu-id="37b9a-186">Cree un archivo *input.txt* en el directorio *mySparkApp*, con el texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="37b9a-186">Create an *input.txt* file in your *mySparkApp* directory, containing the following text:</span></span>

```text
Hello World
This .NET app uses .NET for Apache Spark
This .NET app counts words with Apache Spark
```

## <a name="run-your-net-for-apache-spark-app"></a><span data-ttu-id="37b9a-187">Ejecución de la aplicación de .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="37b9a-187">Run your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="37b9a-188">Ejecute el comando siguiente para compilar la aplicación:</span><span class="sxs-lookup"><span data-stu-id="37b9a-188">Run the following command to build your application:</span></span>

   ```dotnetcli
   dotnet build
   ```

2. <span data-ttu-id="37b9a-189">Ejecute el comando siguiente para enviar la aplicación para que se ejecute en Apache Spark:</span><span class="sxs-lookup"><span data-stu-id="37b9a-189">Run the following command to submit your application to run on Apache Spark:</span></span>

   ```console
   spark-submit \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   --master local \
   microsoft-spark-2.4.x-<version>.jar \
   dotnet HelloSpark.dll
   ```

   > [!NOTE]
   > <span data-ttu-id="37b9a-190">Este comando asume que se ha descargado Apache Spark y se ha agregado a la variable de entorno PATH para poder usar `spark-submit`.</span><span class="sxs-lookup"><span data-stu-id="37b9a-190">This command assumes you have downloaded Apache Spark and added it to your PATH environment variable to be able to use `spark-submit`.</span></span> <span data-ttu-id="37b9a-191">De lo contrario, tendría que usar la ruta de acceso completa (por ejemplo, *C:\bin\apache-spark\bin\spark-submit* o *~/spark/bin/spark-submit*).</span><span class="sxs-lookup"><span data-stu-id="37b9a-191">Otherwise, you'd have to use the full path (for example, *C:\bin\apache-spark\bin\spark-submit* or *~/spark/bin/spark-submit*).</span></span>

3. <span data-ttu-id="37b9a-192">Cuando la aplicación se ejecuta, los datos de recuento de palabras del archivo *input.txt* se escriben en la consola.</span><span class="sxs-lookup"><span data-stu-id="37b9a-192">When your app runs, the word count data of the *input.txt* file is written to the console.</span></span>

<span data-ttu-id="37b9a-193">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="37b9a-193">Congratulations!</span></span> <span data-ttu-id="37b9a-194">Ha creado y ejecutado correctamente una aplicación de .NET para Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="37b9a-194">You successfully authored and ran a .NET for Apache Spark app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="37b9a-195">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="37b9a-195">Next steps</span></span>

<span data-ttu-id="37b9a-196">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="37b9a-196">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="37b9a-197">Preparar el entorno de Windows para .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="37b9a-197">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="37b9a-198">Implementar la primer aplicación .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="37b9a-198">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="37b9a-199">Compilar y ejecutar una aplicación .NET para Apache Spark sencilla</span><span class="sxs-lookup"><span data-stu-id="37b9a-199">Build and run your simple .NET for Apache Spark application</span></span>

<span data-ttu-id="37b9a-200">Para ver un vídeo en el que se explican los pasos anteriores, consulte la [serie de vídeos .NET para Apache Spark 101](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App).</span><span class="sxs-lookup"><span data-stu-id="37b9a-200">To see a video explaining the steps above, checkout the [.NET for Apache Spark 101 video series](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App).</span></span>

<span data-ttu-id="37b9a-201">Eche un vistazo a la página de recursos para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="37b9a-201">Check out the resources page to learn more.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="37b9a-202">Recursos de .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="37b9a-202">.NET for Apache Spark Resources</span></span>](../resources/index.md)
