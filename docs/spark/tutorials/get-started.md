---
title: Introducción a .NET para Apache Spark
description: Descubra cómo ejecutar una aplicación .NET para Apache Spark con .NET Core en Windows, macOS y Ubuntu.
ms.date: 10/09/2020
ms.topic: tutorial
ms.custom: mvc
ms.author: luquinta
author: luisquintanilla
ms.openlocfilehash: d4f44d095fffdfa05b82516cfe79700f9e239110
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2020
ms.locfileid: "91955413"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a><span data-ttu-id="3371c-103">Tutorial: Introducción a .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="3371c-103">Tutorial: Get started with .NET for Apache Spark</span></span>

<span data-ttu-id="3371c-104">En este tutorial aprenderá a ejecutar una aplicación .NET para Apache Spark con .NET Core en Windows, macOS y Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="3371c-104">This tutorial teaches you how to run a .NET for Apache Spark app using .NET Core on Windows, macOS, and Ubuntu.</span></span>

<span data-ttu-id="3371c-105">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="3371c-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="3371c-106">Preparar el entorno de .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="3371c-106">Prepare your environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="3371c-107">Implementar la primer aplicación .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="3371c-107">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="3371c-108">Compilar y ejecutar una aplicación .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="3371c-108">Build and run your .NET for Apache Spark application</span></span>

## <a name="prepare-your-environment"></a><span data-ttu-id="3371c-109">Preparación del entorno</span><span class="sxs-lookup"><span data-stu-id="3371c-109">Prepare your environment</span></span>

<span data-ttu-id="3371c-110">Antes de comenzar a escribir la aplicación, debe configurar algunas dependencias de requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="3371c-110">Before you begin writing your app, you need to set up some prerequisite dependencies.</span></span> <span data-ttu-id="3371c-111">Si puede ejecutar `dotnet`, `java`, `spark-shell`, desde el entorno de línea de comandos, el entorno ya está preparado y puede ir directamente a la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="3371c-111">If you can run `dotnet`, `java`, `spark-shell` from your command line environment, then your environment is already prepared and you can skip to the next section.</span></span> <span data-ttu-id="3371c-112">Si no puede ejecutar alguno o ninguno de los comandos, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="3371c-112">If you cannot run any or all of the commands, do the following steps.</span></span>

### <a name="1-install-net"></a><span data-ttu-id="3371c-113">1. Instalación de .NET</span><span class="sxs-lookup"><span data-stu-id="3371c-113">1. Install .NET</span></span>

<span data-ttu-id="3371c-114">Para empezar a compilar aplicaciones .NET, debe descargar e instalar el SDK (kit de desarrollo de software) de .NET.</span><span class="sxs-lookup"><span data-stu-id="3371c-114">To start building .NET apps, you need to download and install the .NET SDK (Software Development Kit).</span></span>

<span data-ttu-id="3371c-115">Descargue e instale el [SDK de .NET Core](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span><span class="sxs-lookup"><span data-stu-id="3371c-115">Download and install the [.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span> <span data-ttu-id="3371c-116">Al instalar el SDK, se agrega la cadena de herramientas `dotnet` a la variable de entorno PATH.</span><span class="sxs-lookup"><span data-stu-id="3371c-116">Installing the SDK adds the `dotnet` toolchain to your PATH.</span></span>

<span data-ttu-id="3371c-117">Una vez instalado el SDK de .NET Core, abra un símbolo del sistema o terminal nuevo y ejecute `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="3371c-117">Once you've installed the .NET Core SDK, open a new command prompt or terminal and run `dotnet`.</span></span>

<span data-ttu-id="3371c-118">Si el comando se ejecuta e imprime información sobre cómo usar dotnet, puede pasar al paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="3371c-118">If the command runs and prints out information about how to use dotnet, can move to the next step.</span></span> <span data-ttu-id="3371c-119">Si recibe un error `'dotnet' is not recognized as an internal or external command`, asegúrese de que ha abierto un símbolo del sistema o terminal **nuevo** antes de ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="3371c-119">If you receive a `'dotnet' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt or terminal before running the command.</span></span>

### <a name="2-install-java"></a><span data-ttu-id="3371c-120">2. Instalación de Java</span><span class="sxs-lookup"><span data-stu-id="3371c-120">2. Install Java</span></span>

<span data-ttu-id="3371c-121">Instale [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) para Windows y MacOS, o bien [OpenJDK 8](https://openjdk.java.net/install/) para Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="3371c-121">Install [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) for Windows and macOS, or [OpenJDK 8](https://openjdk.java.net/install/) for Ubuntu.</span></span>

<span data-ttu-id="3371c-122">Seleccione la versión adecuada según su sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="3371c-122">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="3371c-123">Por ejemplo, seleccione **jdk-8u201-windows-x64.exe** para una máquina Windows x64 (tal como se muestra debajo) o **jdk-8u231-macosx-x64.dmg** para macOS.</span><span class="sxs-lookup"><span data-stu-id="3371c-123">For example, select **jdk-8u201-windows-x64.exe** for a Windows x64 machine (as shown below) or **jdk-8u231-macosx-x64.dmg** for macOS.</span></span> <span data-ttu-id="3371c-124">Después, use el comando `java` para comprobar la instalación.</span><span class="sxs-lookup"><span data-stu-id="3371c-124">Then, use the command `java` to verify the installation.</span></span>

![Descarga de Java](https://dotnet.microsoft.com/static/images/java-jdk-downloads-windows.png?v=6BbJHoNyDO-PyYVciImr5wzh2AW_YHNcyb3p093AwPA)

### <a name="3-install-compression-software"></a><span data-ttu-id="3371c-126">3. Instalación de software de compresión</span><span class="sxs-lookup"><span data-stu-id="3371c-126">3. Install compression software</span></span>

<span data-ttu-id="3371c-127">Apache Spark se descarga como un archivo .tgz comprimido.</span><span class="sxs-lookup"><span data-stu-id="3371c-127">Apache Spark is downloaded as a compressed .tgz file.</span></span> <span data-ttu-id="3371c-128">Use un programa de extracción, como[7-Zip](https://www.7-zip.org/) o [WinZip](https://www.winzip.com/), para extraer el archivo.</span><span class="sxs-lookup"><span data-stu-id="3371c-128">Use an extraction program, like [7-Zip](https://www.7-zip.org/) or [WinZip](https://www.winzip.com/), to extract the file.</span></span>

### <a name="4-install-apache-spark"></a><span data-ttu-id="3371c-129">4. Instalación de Apache Spark</span><span class="sxs-lookup"><span data-stu-id="3371c-129">4. Install Apache Spark</span></span>

<span data-ttu-id="3371c-130">[Descargue e instale](https://spark.apache.org/downloads.html) Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="3371c-130">[Download and install Apache Spark](https://spark.apache.org/downloads.html).</span></span> <span data-ttu-id="3371c-131">Tendrá que seleccionar entre la versión 2.3.\* o 2.4.0, 2.4.1, 2.4.3, o bien 2.4.4 (.NET para Apache Spark no es compatible con otras versiones de Apache Spark).</span><span class="sxs-lookup"><span data-stu-id="3371c-131">You'll need to select from version 2.3.\* or 2.4.0, 2.4.1, 2.4.3, or 2.4.4 (.NET for Apache Spark is not compatible with other versions of Apache Spark).</span></span>

<span data-ttu-id="3371c-132">En los comandos que se usan en los pasos siguientes se supone que ha [descargado e instalado Apache Spark 2.4.1](https://archive.apache.org/dist/spark/spark-2.4.1/spark-2.4.1-bin-hadoop2.7.tgz).</span><span class="sxs-lookup"><span data-stu-id="3371c-132">The commands used in the following steps assume you have [downloaded and installed Apache Spark 2.4.1](https://archive.apache.org/dist/spark/spark-2.4.1/spark-2.4.1-bin-hadoop2.7.tgz).</span></span> <span data-ttu-id="3371c-133">Si prefiere usar otra versión, reemplace **2.4.1** por el número de versión adecuado.</span><span class="sxs-lookup"><span data-stu-id="3371c-133">If you wish to use a different version, replace **2.4.1** with the appropriate version number.</span></span> <span data-ttu-id="3371c-134">Después, extraiga el archivo **.tar** y los archivos de Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="3371c-134">Then, extract the **.tar** file and the Apache Spark files.</span></span>

<span data-ttu-id="3371c-135">Para extraer el archivo **.tar** anidado:</span><span class="sxs-lookup"><span data-stu-id="3371c-135">To extract the nested **.tar** file:</span></span>

* <span data-ttu-id="3371c-136">Busque el archivo **spark-2.4.1-bin-hadoop2.7.tgz** que ha descargado.</span><span class="sxs-lookup"><span data-stu-id="3371c-136">Locate the **spark-2.4.1-bin-hadoop2.7.tgz** file that you downloaded.</span></span>
* <span data-ttu-id="3371c-137">Haga clic con el botón derecho en el archivo y seleccione **7-Zip -> Extraer aquí**.</span><span class="sxs-lookup"><span data-stu-id="3371c-137">Right click on the file and select **7-Zip -> Extract here**.</span></span>
* <span data-ttu-id="3371c-138">Se creará **spark-2.4.1-bin-hadoop2.7.tar** junto con el archivo **.tgz** que ha descargado.</span><span class="sxs-lookup"><span data-stu-id="3371c-138">**spark-2.4.1-bin-hadoop2.7.tar** is created alongside the **.tgz** file you downloaded.</span></span>

<span data-ttu-id="3371c-139">Para extraer los archivos de Apache Spark:</span><span class="sxs-lookup"><span data-stu-id="3371c-139">To extract the Apache Spark files:</span></span>

* <span data-ttu-id="3371c-140">Haga clic con el botón derecho en **spark-2.4.1-bin-hadoop2.7.tar** y seleccione **7-Zip -> Extraer archivos...**</span><span class="sxs-lookup"><span data-stu-id="3371c-140">Right-click on **spark-2.4.1-bin-hadoop2.7.tar** and select **7-Zip -> Extract files...**</span></span>
* <span data-ttu-id="3371c-141">Escriba **C:\bin** en el campo **Extraer en**.</span><span class="sxs-lookup"><span data-stu-id="3371c-141">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="3371c-142">Desactive la casilla situada debajo del campo **Extraer en**.</span><span class="sxs-lookup"><span data-stu-id="3371c-142">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="3371c-143">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3371c-143">Select **OK**.</span></span>
* <span data-ttu-id="3371c-144">Los archivos de Apache Spark se extraen en C:\bin\spark-2.4.1-bin-hadoop2.7\.</span><span class="sxs-lookup"><span data-stu-id="3371c-144">The Apache Spark files are extracted to C:\bin\spark-2.4.1-bin-hadoop2.7\</span></span>

![Instalación de Spark](https://dotnet.microsoft.com/static/images/spark-extract-with-7-zip.png?v=YvjUv54LIxI9FbALPC3h8zSQdyMtK2-NKbFOliG-f8M)

<span data-ttu-id="3371c-146">Ejecute los comandos siguientes para establecer las variables de entorno que se usan para buscar Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="3371c-146">Run the following commands to set the environment variables used to locate Apache Spark.</span></span> <span data-ttu-id="3371c-147">En Windows, asegúrese de ejecutar el símbolo del sistema en modo de administrador.</span><span class="sxs-lookup"><span data-stu-id="3371c-147">On Windows, make sure to run the command prompt in administrator mode.</span></span>

#### <a name="windows"></a>[<span data-ttu-id="3371c-148">Windows</span><span class="sxs-lookup"><span data-stu-id="3371c-148">Windows</span></span>](#tab/windows)

```console
setx /M HADOOP_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
setx /M SPARK_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
setx /M PATH "%PATH%;%HADOOP_HOME%;%SPARK_HOME%\bin"
```

#### <a name="maclinux"></a>[<span data-ttu-id="3371c-149">Mac o Linux:</span><span class="sxs-lookup"><span data-stu-id="3371c-149">Mac/Linux</span></span>](#tab/linux)

```bash
export SPARK_HOME=~/bin/spark-2.4.1-bin-hadoop2.7/
export PATH="$SPARK_HOME/bin:$PATH"
source ~/.bashrc
```

---

<span data-ttu-id="3371c-150">Una vez que se haya instalado todo y establecido las variables de entorno, abra un símbolo del sistema o terminal **nuevo** y ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="3371c-150">Once you've installed everything and set your environment variables, open a **new** command prompt or terminal and run the following command:</span></span>

```text
spark-submit --version
```

<span data-ttu-id="3371c-151">Si el comando se ejecuta e imprime la información de versión, puede pasar al paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="3371c-151">If the command runs and prints version information, you can move to the next step.</span></span>

<span data-ttu-id="3371c-152">Si recibe un error `'spark-submit' is not recognized as an internal or external command`, asegúrese de que ha abierto un símbolo del sistema **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="3371c-152">If you receive a `'spark-submit' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt.</span></span>

### <a name="5-install-net-for-apache-spark"></a><span data-ttu-id="3371c-153">5. Instalación de .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="3371c-153">5. Install .NET for Apache Spark</span></span>

<span data-ttu-id="3371c-154">Descargue la versión [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) de la página de .NET para Apache Spark en GitHub.</span><span class="sxs-lookup"><span data-stu-id="3371c-154">Download the [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) release from the .NET for Apache Spark GitHub.</span></span> <span data-ttu-id="3371c-155">Por ejemplo, si se encuentra en una máquina Windows y planea usar .NET Core, [descargue la versión Windows x64 netcoreapp3.1](https://github.com/dotnet/spark/releases).</span><span class="sxs-lookup"><span data-stu-id="3371c-155">For example if you're on a Windows machine and plan to use .NET Core, [download the Windows x64 netcoreapp3.1 release](https://github.com/dotnet/spark/releases).</span></span>

<span data-ttu-id="3371c-156">Para extraer Microsoft.Spark.Worker:</span><span class="sxs-lookup"><span data-stu-id="3371c-156">To extract the Microsoft.Spark.Worker:</span></span>

* <span data-ttu-id="3371c-157">Busque el archivo **Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip** que ha descargado.</span><span class="sxs-lookup"><span data-stu-id="3371c-157">Locate the **Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip** file that you downloaded.</span></span>
* <span data-ttu-id="3371c-158">Haga clic con el botón derecho y seleccione **7-Zip -> Extraer archivos...**</span><span class="sxs-lookup"><span data-stu-id="3371c-158">Right-click and select **7-Zip -> Extract files...**.</span></span>
* <span data-ttu-id="3371c-159">Escriba **C:\bin** en el campo **Extraer en**.</span><span class="sxs-lookup"><span data-stu-id="3371c-159">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="3371c-160">Desactive la casilla situada debajo del campo **Extraer en**.</span><span class="sxs-lookup"><span data-stu-id="3371c-160">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="3371c-161">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3371c-161">Select **OK**.</span></span>

![Instalación de .NET Spark](https://dotnet.microsoft.com/static/images/dotnet-for-spark-extract-with-7-zip.png?v=jwCyum9mL0mGIi4V5zC7yuvLfcj1_nL-QFFD8TClhZk)

### <a name="6-install-winutils-windows-only"></a><span data-ttu-id="3371c-163">6. Instalación de WinUtils (solo Windows)</span><span class="sxs-lookup"><span data-stu-id="3371c-163">6. Install WinUtils (Windows only)</span></span>

<span data-ttu-id="3371c-164">.NET para Apache Spark requiere que se instale WinUtils junto a Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="3371c-164">.NET for Apache Spark requires WinUtils to be installed alongside Apache Spark.</span></span> <span data-ttu-id="3371c-165">[Descargue winutils.exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe).</span><span class="sxs-lookup"><span data-stu-id="3371c-165">[Download winutils.exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe).</span></span> <span data-ttu-id="3371c-166">Después, copie WinUtils en **C:\bin\spark-2.4.1-bin-hadoop2.7\bin**.</span><span class="sxs-lookup"><span data-stu-id="3371c-166">Then, copy WinUtils into **C:\bin\spark-2.4.1-bin-hadoop2.7\bin**.</span></span>

> [!NOTE]
> <span data-ttu-id="3371c-167">Si usa otra versión de Hadoop (anotada al final del nombre de la carpeta de instalación de Spark) [seleccione la versión de WinUtils](https://github.com/steveloughran/winutils) que sea compatible con la versión de Hadoop.</span><span class="sxs-lookup"><span data-stu-id="3371c-167">If you are using a different version of Hadoop, which is annotated at the end of your Spark install folder name, [select the version of WinUtils](https://github.com/steveloughran/winutils) that's compatible with your version of Hadoop.</span></span>

### <a name="7-set-dotnet_worker_dir-and-check-dependencies"></a><span data-ttu-id="3371c-168">7. Establecimiento de DOTNET_WORKER_DIR y comprobación de las dependencias</span><span class="sxs-lookup"><span data-stu-id="3371c-168">7. Set DOTNET_WORKER_DIR and check dependencies</span></span>

<span data-ttu-id="3371c-169">Ejecute uno de los comandos siguientes para establecer la variable de entorno `DOTNET_WORKER_DIR`, que las aplicaciones .NET usan con el fin de buscar .NET para Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="3371c-169">Run one of the following commands to set the `DOTNET_WORKER_DIR` environment variable, which is used by .NET apps to locate .NET for Apache Spark.</span></span> <span data-ttu-id="3371c-170">Asegúrese de reemplazar `<PATH-DOTNET_WORKER_DIR>` por el directorio donde descargó y extrajo el `Microsoft.Spark.Worker`.</span><span class="sxs-lookup"><span data-stu-id="3371c-170">Make sure to replace `<PATH-DOTNET_WORKER_DIR>` with the directory where you downloaded and extracted the `Microsoft.Spark.Worker`.</span></span> <span data-ttu-id="3371c-171">En Windows, asegúrese de ejecutar el símbolo del sistema en modo de administrador.</span><span class="sxs-lookup"><span data-stu-id="3371c-171">On Windows, make sure to run the command prompt in administrator mode.</span></span>

#### <a name="windows"></a>[<span data-ttu-id="3371c-172">Windows</span><span class="sxs-lookup"><span data-stu-id="3371c-172">Windows</span></span>](#tab/windows)

```console
setx /M DOTNET_WORKER_DIR <PATH-DOTNET-WORKER-DIR>
```

#### <a name="maclinux"></a>[<span data-ttu-id="3371c-173">Mac o Linux:</span><span class="sxs-lookup"><span data-stu-id="3371c-173">Mac/Linux</span></span>](#tab/linux)

```bash
export DOTNET_WORKER_DIR=<PATH-DOTNET-WORKER-DIR>
```

---

<span data-ttu-id="3371c-174">Por último, confirme que puede ejecutar `dotnet`, `java`, `spark-shell` desde la línea de comandos antes de pasar a la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="3371c-174">Finally, double-check that you can run `dotnet`, `java`, `spark-shell` from your command line before you move to the next section.</span></span>

## <a name="write-a-net-for-apache-spark-app"></a><span data-ttu-id="3371c-175">Escritura de una aplicación de .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="3371c-175">Write a .NET for Apache Spark app</span></span>

### <a name="1-create-a-console-app"></a><span data-ttu-id="3371c-176">1. Crear una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="3371c-176">1. Create a console app</span></span>

<span data-ttu-id="3371c-177">En el símbolo del sistema o terminal, ejecute los comandos siguientes para crear una aplicación de consola nueva:</span><span class="sxs-lookup"><span data-stu-id="3371c-177">In your command prompt or terminal, run the following commands to create a new console application:</span></span>

```dotnetcli
dotnet new console -o MySparkApp
cd MySparkApp
```

<span data-ttu-id="3371c-178">El comando `dotnet` crea una aplicación `new` de tipo `console` de forma automática.</span><span class="sxs-lookup"><span data-stu-id="3371c-178">The `dotnet` command creates a `new` application of type `console` for you.</span></span> <span data-ttu-id="3371c-179">El parámetro `-o` crea un directorio denominado *mySparkApp* donde se almacena la aplicación y lo rellena con los archivos necesarios.</span><span class="sxs-lookup"><span data-stu-id="3371c-179">The `-o` parameter creates a directory named *MySparkApp* where your app is stored and populates it with the required files.</span></span> <span data-ttu-id="3371c-180">El comando `cd MySparkApp` cambia el directorio al directorio de la aplicación que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="3371c-180">The `cd MySparkApp` command changes the directory to the app directory you created.</span></span>

### <a name="2-install-nuget-package"></a><span data-ttu-id="3371c-181">2. Instalación del paquete NuGet</span><span class="sxs-lookup"><span data-stu-id="3371c-181">2. Install NuGet package</span></span>

<span data-ttu-id="3371c-182">Para usar .NET para Apache Spark en una aplicación, instale el paquete Microsoft.Spark.</span><span class="sxs-lookup"><span data-stu-id="3371c-182">To use .NET for Apache Spark in an app, install the Microsoft.Spark package.</span></span> <span data-ttu-id="3371c-183">En el símbolo del sistema o terminal, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="3371c-183">In your command prompt or terminal, run the following command:</span></span>

```dotnetcli
dotnet add package Microsoft.Spark
```

> [!NOTE]
> <span data-ttu-id="3371c-184">En este tutorial se usa la versión más reciente del paquete NuGet de `Microsoft.Spark`, a menos que se especifique lo contrario.</span><span class="sxs-lookup"><span data-stu-id="3371c-184">This tutorial uses the latest version of the `Microsoft.Spark` NuGet package unless otherwise specified.</span></span>

### <a name="3-write-your-app"></a><span data-ttu-id="3371c-185">3. Escritura de la aplicación</span><span class="sxs-lookup"><span data-stu-id="3371c-185">3. Write your app</span></span>

<span data-ttu-id="3371c-186">Abra *Program.cs* en Visual Studio Code o cualquier editor de texto, y reemplace todo el código por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3371c-186">Open *Program.cs* in Visual Studio Code, or any text editor, and replace all of the code with the following:</span></span>

```csharp
using Microsoft.Spark.Sql;
using static Microsoft.Spark.Sql.Functions;

namespace MySparkApp
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create Spark session
            SparkSession spark =
                SparkSession
                    .Builder()
                    .AppName("word_count_sample")
                    .GetOrCreate();

            // Create initial DataFrame
            string filePath = args[0];
            DataFrame dataFrame = spark.Read().Text(filePath);

            //Count words
            DataFrame words =
                dataFrame
                    .Select(Split(Col("value")," ").Alias("words"))
                    .Select(Explode(Col("words")).Alias("word"))
                    .GroupBy("word")
                    .Count()
                    .OrderBy(Col("count").Desc());

            // Display results
            words.Show();

            // Stop Spark session
            spark.Stop();
        }
    }
}
```

<span data-ttu-id="3371c-187">El objeto [SparkSession](xref:Microsoft.Spark.Sql.SparkSession) es el punto de entrada de las aplicaciones Apache Spark, que administra el contexto y la información de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3371c-187">[SparkSession](xref:Microsoft.Spark.Sql.SparkSession) is the entrypoint of Apache Spark applications, which manages the context and information of your application.</span></span> <span data-ttu-id="3371c-188">Mediante el método [Text](xref:Microsoft.Spark.Sql.DataFrameReader.Text%2A), los datos de texto del archivo especificado por `filePath` se leen en un [DataFrame](xref:Microsoft.Spark.Sql.DataFrame).</span><span class="sxs-lookup"><span data-stu-id="3371c-188">Using the [Text](xref:Microsoft.Spark.Sql.DataFrameReader.Text%2A) method, the text data from the file specified by the `filePath` is read into a [DataFrame](xref:Microsoft.Spark.Sql.DataFrame).</span></span> <span data-ttu-id="3371c-189">Un DataFrame es una manera de organizar los datos en un conjunto de columnas con nombre.</span><span class="sxs-lookup"><span data-stu-id="3371c-189">A DataFrame is a way of organizing data into a set of named columns.</span></span> <span data-ttu-id="3371c-190">A continuación, se aplica una serie de transformaciones para dividir las frases en el archivo, agrupar cada una de las palabras, contarlas y ordenarlas en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="3371c-190">Then, a series of transformations is applied to split the sentences in the file, group each of the words, count them and order them in descending order.</span></span> <span data-ttu-id="3371c-191">El resultado de estas operaciones se almacena en otro DataFrame.</span><span class="sxs-lookup"><span data-stu-id="3371c-191">The result of these operations is stored in another DataFrame.</span></span> <span data-ttu-id="3371c-192">Tenga en cuenta que, en este momento, no se ha realizado ninguna operación porque .NET para Apache Spark evalúa los datos de forma diferida.</span><span class="sxs-lookup"><span data-stu-id="3371c-192">Note that at this point, no operations have taken place because .NET for Apache Spark lazily evaluates the data.</span></span> <span data-ttu-id="3371c-193">No es hasta que se llama al método [Show](xref:Microsoft.Spark.Sql.DataFrame.Show%2A) para mostrar el contenido del DataFrame transformado `words` en la consola que se ejecutan las operaciones definidas en las líneas anteriores.</span><span class="sxs-lookup"><span data-stu-id="3371c-193">It's not until the [Show](xref:Microsoft.Spark.Sql.DataFrame.Show%2A) method is called to display the contents of the `words` transformed DataFrame to the console that the operations defined in the lines above execute.</span></span> <span data-ttu-id="3371c-194">Cuando ya no necesite la sesión de Spark, use el método [Stop](xref:Microsoft.Spark.Sql.SparkSession.Stop%2A) para detener la sesión.</span><span class="sxs-lookup"><span data-stu-id="3371c-194">Once you no longer need the Spark session, use the [Stop](xref:Microsoft.Spark.Sql.SparkSession.Stop%2A) method to stop your session.</span></span>

### <a name="4-create-data-file"></a><span data-ttu-id="3371c-195">4. Creación del archivo de datos</span><span class="sxs-lookup"><span data-stu-id="3371c-195">4. Create data file</span></span>

<span data-ttu-id="3371c-196">La aplicación procesa un archivo que contiene líneas de texto.</span><span class="sxs-lookup"><span data-stu-id="3371c-196">Your app processes a file containing lines of text.</span></span> <span data-ttu-id="3371c-197">Cree un archivo llamado *input.txt* en el directorio *MySparkApp*, con el texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="3371c-197">Create a file called *input.txt* file in your *MySparkApp* directory, containing the following text:</span></span>

```text
Hello World
This .NET app uses .NET for Apache Spark
This .NET app counts words with Apache Spark
```

<span data-ttu-id="3371c-198">Guarde los cambios y cierre el archivo.</span><span class="sxs-lookup"><span data-stu-id="3371c-198">Save the changes and close the file.</span></span>

## <a name="run-your-net-for-apache-spark-app"></a><span data-ttu-id="3371c-199">Ejecución de la aplicación de .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="3371c-199">Run your .NET for Apache Spark app</span></span>

<span data-ttu-id="3371c-200">Ejecute el comando siguiente para compilar la aplicación:</span><span class="sxs-lookup"><span data-stu-id="3371c-200">Run the following command to build your application:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="3371c-201">Desplácese al directorio de salida de la compilación y use el comando `spark-submit` para enviar la aplicación para que se ejecute en Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="3371c-201">Navigate to your build output directory and use the `spark-submit` command to submit your application to run on Apache Spark.</span></span> <span data-ttu-id="3371c-202">Asegúrese de reemplazar `<version>` por la versión del trabajo de .NET y `<path-of-input.txt>` por la ruta de acceso del archivo *input.txt* donde está almacenado.</span><span class="sxs-lookup"><span data-stu-id="3371c-202">Make sure to replace  `<version>` with the version of your .NET worker and `<path-of-input.txt>` with the path of your *input.txt* file is stored.</span></span>

### <a name="windows"></a>[<span data-ttu-id="3371c-203">Windows</span><span class="sxs-lookup"><span data-stu-id="3371c-203">Windows</span></span>](#tab/windows)

```console
spark-submit ^
--class org.apache.spark.deploy.dotnet.DotnetRunner ^
--master local ^
microsoft-spark-2.4.x-<version>.jar ^
dotnet MySparkApp.dll <path-of-input.txt>
```

### <a name="maclinux"></a>[<span data-ttu-id="3371c-204">Mac o Linux:</span><span class="sxs-lookup"><span data-stu-id="3371c-204">Mac/Linux</span></span>](#tab/linux)

```bash
spark-submit \
--class org.apache.spark.deploy.dotnet.DotnetRunner \
--master local \
microsoft-spark-2.4.x-<version>.jar \
dotnet MySparkApp.dll <path-of-input.txt>
```

---

> [!NOTE]
> <span data-ttu-id="3371c-205">Este comando asume que se ha descargado Apache Spark y se ha agregado a la variable de entorno PATH para poder usar `spark-submit`.</span><span class="sxs-lookup"><span data-stu-id="3371c-205">This command assumes you have downloaded Apache Spark and added it to your PATH environment variable to be able to use `spark-submit`.</span></span> <span data-ttu-id="3371c-206">De lo contrario, tendría que usar la ruta de acceso completa (por ejemplo, *C:\bin\apache-spark\bin\spark-submit* o *~/spark/bin/spark-submit*).</span><span class="sxs-lookup"><span data-stu-id="3371c-206">Otherwise, you'd have to use the full path (for example, *C:\bin\apache-spark\bin\spark-submit* or *~/spark/bin/spark-submit*).</span></span>

<span data-ttu-id="3371c-207">Cuando la aplicación se ejecuta, los datos de recuento de palabras del archivo *input.txt* se escriben en la consola.</span><span class="sxs-lookup"><span data-stu-id="3371c-207">When your app runs, the word count data of the *input.txt* file is written to the console.</span></span>

```console
+------+-----+
|  word|count|
+------+-----+
|  .NET|    3|
|Apache|    2|
|   app|    2|
|  This|    2|
| Spark|    2|
| World|    1|
|counts|    1|
|   for|    1|
| words|    1|
|  with|    1|
| Hello|    1|
|  uses|    1|
+------+-----+
```

<span data-ttu-id="3371c-208">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="3371c-208">Congratulations!</span></span> <span data-ttu-id="3371c-209">Ha creado y ejecutado correctamente una aplicación de .NET para Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="3371c-209">You successfully authored and ran a .NET for Apache Spark app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3371c-210">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="3371c-210">Next steps</span></span>

<span data-ttu-id="3371c-211">En este tutorial, ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="3371c-211">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="3371c-212">Preparar el entorno de .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="3371c-212">Prepare your environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="3371c-213">Implementar la primer aplicación .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="3371c-213">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="3371c-214">Compilar y ejecutar una aplicación .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="3371c-214">Build and run your .NET for Apache Spark application</span></span>

<span data-ttu-id="3371c-215">Para ver un vídeo en el que se explican los pasos anteriores, consulte la [serie de vídeos .NET para Apache Spark 101](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App).</span><span class="sxs-lookup"><span data-stu-id="3371c-215">To see a video explaining the steps above, check out the [.NET for Apache Spark 101 video series](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App).</span></span>

<span data-ttu-id="3371c-216">Eche un vistazo a la página de recursos para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="3371c-216">Check out the resources page to learn more.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="3371c-217">Recursos de .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="3371c-217">.NET for Apache Spark Resources</span></span>](../resources/index.md)
