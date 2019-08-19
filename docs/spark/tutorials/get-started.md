---
title: Introducción a .NET para Apache Spark
description: Descubra cómo ejecutar una aplicación .NET para Apache Spark con .NET Core en Windows.
ms.date: 06/27/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 7ce7d7aec6c15385d3d797d5a548519eea33b764
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "69577012"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a><span data-ttu-id="0bf05-103">Tutorial: Introducción a .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="0bf05-103">Tutorial: Get started with .NET for Apache Spark</span></span>

<span data-ttu-id="0bf05-104">En este tutorial aprenderá a ejecutar una aplicación .NET para Apache Spark con .NET Core en Windows.</span><span class="sxs-lookup"><span data-stu-id="0bf05-104">This tutorial teaches you how to run a .NET for Apache Spark app using .NET Core on Windows.</span></span>

<span data-ttu-id="0bf05-105">En este tutorial, aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="0bf05-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="0bf05-106">Preparar el entorno de Windows para .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="0bf05-106">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="0bf05-107">Descargar **Microsoft. Spark. Worker**</span><span class="sxs-lookup"><span data-stu-id="0bf05-107">Download the **Microsoft.Spark.Worker**</span></span>
> * <span data-ttu-id="0bf05-108">Compilar y ejecutar una aplicación .NET simple para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="0bf05-108">Build and run a simple .NET for Apache Spark application</span></span>

## <a name="prepare-your-environment"></a><span data-ttu-id="0bf05-109">Preparación del entorno</span><span class="sxs-lookup"><span data-stu-id="0bf05-109">Prepare your environment</span></span>

<span data-ttu-id="0bf05-110">Antes de empezar, asegúrese de que puede ejecutar `dotnet`, `java`, `mvn`, `spark-shell` desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="0bf05-110">Before you begin, make sure you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line.</span></span> <span data-ttu-id="0bf05-111">Si el entorno ya está preparado, puede ir directamente a la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="0bf05-111">If your environment is already prepared, you can skip to the next section.</span></span> <span data-ttu-id="0bf05-112">Si no puede ejecutar ninguno o todos los comandos, siga los pasos que se indican a continuación.</span><span class="sxs-lookup"><span data-stu-id="0bf05-112">If you cannot run any or all of the commands, follow the steps below.</span></span>

1. <span data-ttu-id="0bf05-113">Descargue e instale el [SDK de .net Core 2.1 x](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span><span class="sxs-lookup"><span data-stu-id="0bf05-113">Download and install the [.NET Core 2.1x SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span> <span data-ttu-id="0bf05-114">Al instalar el SDK, `dotnet` se agrega la cadena de herramientas a la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="0bf05-114">Installing the SDK adds the `dotnet` toolchain to your PATH.</span></span> <span data-ttu-id="0bf05-115">Use el comando `dotnet --version` de PowerShell para comprobar la instalación.</span><span class="sxs-lookup"><span data-stu-id="0bf05-115">Use the PowerShell command `dotnet --version` to verify the installation.</span></span>

2. <span data-ttu-id="0bf05-116">Instale [visual studio 2017](https://www.visualstudio.com/downloads/) o [Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/) con las actualizaciones más recientes.</span><span class="sxs-lookup"><span data-stu-id="0bf05-116">Install [Visual Studio 2017](https://www.visualstudio.com/downloads/) or [Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/) with the latest updates.</span></span> <span data-ttu-id="0bf05-117">Puede usar Community, Professional o Enterprise.</span><span class="sxs-lookup"><span data-stu-id="0bf05-117">You can use Community, Professional, or Enterprise.</span></span> <span data-ttu-id="0bf05-118">La versión de la comunidad es gratuita.</span><span class="sxs-lookup"><span data-stu-id="0bf05-118">The Community version is free.</span></span>

   <span data-ttu-id="0bf05-119">Elija las siguientes cargas de trabajo durante la instalación:</span><span class="sxs-lookup"><span data-stu-id="0bf05-119">Choose the following workloads during installation:</span></span>
      * <span data-ttu-id="0bf05-120">Desarrollo de escritorio de .NET</span><span class="sxs-lookup"><span data-stu-id="0bf05-120">.NET desktop development</span></span>
          * <span data-ttu-id="0bf05-121">Todos los componentes necesarios</span><span class="sxs-lookup"><span data-stu-id="0bf05-121">All required components</span></span>
          * <span data-ttu-id="0bf05-122">Herramientas de desarrollo de .NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="0bf05-122">.NET Framework 4.6.1 Development Tools</span></span>
      * <span data-ttu-id="0bf05-123">Desarrollo multiplataforma de .NET Core</span><span class="sxs-lookup"><span data-stu-id="0bf05-123">.NET Core cross-platform development</span></span>
          * <span data-ttu-id="0bf05-124">Todos los componentes necesarios</span><span class="sxs-lookup"><span data-stu-id="0bf05-124">All required components</span></span>

3. <span data-ttu-id="0bf05-125">Instale [Java 1,8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).</span><span class="sxs-lookup"><span data-stu-id="0bf05-125">Install [Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).</span></span>

    * <span data-ttu-id="0bf05-126">Seleccione la versión adecuada para su sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="0bf05-126">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="0bf05-127">Por ejemplo, seleccione **JDK-8u201-Windows-x64. exe** para un equipo Windows x64.</span><span class="sxs-lookup"><span data-stu-id="0bf05-127">For example, select **jdk-8u201-windows-x64.exe** for a Windows x64 machine.</span></span>
    * <span data-ttu-id="0bf05-128">Use el comando `java -version` de PowerShell para comprobar la instalación.</span><span class="sxs-lookup"><span data-stu-id="0bf05-128">Use the PowerShell command `java -version` to verify the installation.</span></span>

4. <span data-ttu-id="0bf05-129">Instale [Apache Maven 3.6.0 +](https://maven.apache.org/download.cgi).</span><span class="sxs-lookup"><span data-stu-id="0bf05-129">Install [Apache Maven 3.6.0+](https://maven.apache.org/download.cgi).</span></span>
    * <span data-ttu-id="0bf05-130">Descargue [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.zip).</span><span class="sxs-lookup"><span data-stu-id="0bf05-130">Download [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.zip).</span></span>
    * <span data-ttu-id="0bf05-131">Extraer en un directorio local.</span><span class="sxs-lookup"><span data-stu-id="0bf05-131">Extract to a local directory.</span></span> <span data-ttu-id="0bf05-132">Por ejemplo, `c:\bin\apache-maven-3.6.0\`.</span><span class="sxs-lookup"><span data-stu-id="0bf05-132">For example, `c:\bin\apache-maven-3.6.0\`.</span></span>
    * <span data-ttu-id="0bf05-133">Agregue Apache Maven a la [variable de entorno PATH](https://www.java.com/en/download/help/path.xml).</span><span class="sxs-lookup"><span data-stu-id="0bf05-133">Add Apache Maven to your [PATH environment variable](https://www.java.com/en/download/help/path.xml).</span></span> <span data-ttu-id="0bf05-134">Si extrajo a `c:\bin\apache-maven-3.6.0\`, agregaría `c:\bin\apache-maven-3.6.0\bin` a la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="0bf05-134">If you extracted to `c:\bin\apache-maven-3.6.0\`, you would add `c:\bin\apache-maven-3.6.0\bin` to your PATH.</span></span>
    * <span data-ttu-id="0bf05-135">Use el comando `mvn -version` de PowerShell para comprobar la instalación.</span><span class="sxs-lookup"><span data-stu-id="0bf05-135">Use the PowerShell command `mvn -version` to verify the installation.</span></span>

5. <span data-ttu-id="0bf05-136">Instale [Apache Spark 2.3 +](https://spark.apache.org/downloads.html).</span><span class="sxs-lookup"><span data-stu-id="0bf05-136">Install [Apache Spark 2.3+](https://spark.apache.org/downloads.html).</span></span> <span data-ttu-id="0bf05-137">Apache Spark 2.4 + no es compatible.</span><span class="sxs-lookup"><span data-stu-id="0bf05-137">Apache Spark 2.4+ isn't supported.</span></span>
    * <span data-ttu-id="0bf05-138">Descargue [Apache Spark 2.3 +](https://spark.apache.org/downloads.html) y extráigalo en una carpeta local con una herramienta como [7-zip](https://www.7-zip.org/) o [WinZip](https://www.winzip.com/).</span><span class="sxs-lookup"><span data-stu-id="0bf05-138">Download [Apache Spark 2.3+](https://spark.apache.org/downloads.html) and extract it into a local folder using a tool like [7-zip](https://www.7-zip.org/) or [WinZip](https://www.winzip.com/).</span></span> <span data-ttu-id="0bf05-139">Por ejemplo, puede extraerlo a `c:\bin\spark-2.3.2-bin-hadoop2.7\`.</span><span class="sxs-lookup"><span data-stu-id="0bf05-139">For example, you might extract it to `c:\bin\spark-2.3.2-bin-hadoop2.7\`.</span></span>
    * <span data-ttu-id="0bf05-140">Agregue Apache Spark a la [variable de entorno PATH](https://www.java.com/en/download/help/path.xml).</span><span class="sxs-lookup"><span data-stu-id="0bf05-140">Add Apache Spark to your [PATH environment variable](https://www.java.com/en/download/help/path.xml).</span></span> <span data-ttu-id="0bf05-141">Si extrajo a `c:\bin\spark-2.3.2-bin-hadoop2.7\`, agregaría `c:\bin\spark-2.3.2-bin-hadoop2.7\bin` a la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="0bf05-141">If you extracted to `c:\bin\spark-2.3.2-bin-hadoop2.7\`, you would add `c:\bin\spark-2.3.2-bin-hadoop2.7\bin` to your PATH.</span></span>
    * <span data-ttu-id="0bf05-142">Agregue una [nueva variable](https://www.java.com/en/download/help/path.xml) de entorno `SPARK_HOME`denominada.</span><span class="sxs-lookup"><span data-stu-id="0bf05-142">Add a [new environment variable](https://www.java.com/en/download/help/path.xml) called `SPARK_HOME`.</span></span> <span data-ttu-id="0bf05-143">Si extrajo a `C:\bin\spark-2.3.2-bin-hadoop2.7\`, use `C:\bin\spark-2.3.2-bin-hadoop2.7\` para el **valor**de la variable.</span><span class="sxs-lookup"><span data-stu-id="0bf05-143">If you extracted to `C:\bin\spark-2.3.2-bin-hadoop2.7\`, use  `C:\bin\spark-2.3.2-bin-hadoop2.7\` for the **Variable value**.</span></span>
    * <span data-ttu-id="0bf05-144">Compruebe que puede ejecutar `spark-shell` desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="0bf05-144">Verify you are able to run `spark-shell` from your command line.</span></span>

6. <span data-ttu-id="0bf05-145">Configure [ausencia archivo winutils](https://github.com/steveloughran/winutils).</span><span class="sxs-lookup"><span data-stu-id="0bf05-145">Set up [WinUtils](https://github.com/steveloughran/winutils).</span></span>
    * <span data-ttu-id="0bf05-146">Descargue el archivo binario **ausencia archivo winutils. exe** del [repositorio ausencia archivo winutils](https://github.com/steveloughran/winutils).</span><span class="sxs-lookup"><span data-stu-id="0bf05-146">Download the **winutils.exe** binary from [WinUtils repository](https://github.com/steveloughran/winutils).</span></span> <span data-ttu-id="0bf05-147">Seleccione la versión de Hadoop con la que se compiló la distribución de Spark.</span><span class="sxs-lookup"><span data-stu-id="0bf05-147">Select the version of Hadoop the Spark distribution was compiled with.</span></span> <span data-ttu-id="0bf05-148">Por ejemplo, se usa **Hadoop-2.7.1** para **Spark 2.3.2**.</span><span class="sxs-lookup"><span data-stu-id="0bf05-148">For example, you use **hadoop-2.7.1** for **Spark 2.3.2**.</span></span> <span data-ttu-id="0bf05-149">La versión de Hadoop se anota al final del nombre de la carpeta de instalación de Spark.</span><span class="sxs-lookup"><span data-stu-id="0bf05-149">The Hadoop version is annotated at the end of your Spark install folder name.</span></span>
    * <span data-ttu-id="0bf05-150">Guarde el archivo binario de **ausencia archivo winutils. exe** en el directorio que prefiera.</span><span class="sxs-lookup"><span data-stu-id="0bf05-150">Save the **winutils.exe** binary to a directory of your choice.</span></span> <span data-ttu-id="0bf05-151">Por ejemplo, `c:\hadoop\bin`.</span><span class="sxs-lookup"><span data-stu-id="0bf05-151">For example, `c:\hadoop\bin`.</span></span>
    * <span data-ttu-id="0bf05-152">Se `HADOOP_HOME` establece para reflejar el directorio con **ausencia archivo winutils. exe** sin `bin`.</span><span class="sxs-lookup"><span data-stu-id="0bf05-152">Set `HADOOP_HOME` to reflect the directory with **winutils.exe** without `bin`.</span></span> <span data-ttu-id="0bf05-153">Por ejemplo, `c:\hadoop`.</span><span class="sxs-lookup"><span data-stu-id="0bf05-153">For example, `c:\hadoop`.</span></span>
    * <span data-ttu-id="0bf05-154">Establezca la variable de entorno PATH en `%HADOOP_HOME%\bin`include.</span><span class="sxs-lookup"><span data-stu-id="0bf05-154">Set the PATH environment variable to include `%HADOOP_HOME%\bin`.</span></span>

<span data-ttu-id="0bf05-155">Haga doble comprobación de que puede `dotnet`ejecutar `java`, `mvn`, `spark-shell` , desde la línea de comandos antes de pasar a la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="0bf05-155">Double check that you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line before you move to the next section.</span></span>

## <a name="download-the-microsoftsparkworker-release"></a><span data-ttu-id="0bf05-156">Descargar la versión Microsoft. Spark. Worker</span><span class="sxs-lookup"><span data-stu-id="0bf05-156">Download the Microsoft.Spark.Worker release</span></span>

1. <span data-ttu-id="0bf05-157">Descargue la versión [Microsoft. Spark. Worker](https://github.com/dotnet/spark/releases) de la página .net para Apache Spark de las versiones de github en la máquina local.</span><span class="sxs-lookup"><span data-stu-id="0bf05-157">Download the [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) release from the .NET for Apache Spark GitHub Releases page to your local machine.</span></span> <span data-ttu-id="0bf05-158">Por ejemplo, puede descargarla en la ruta de acceso `c:\bin\Microsoft.Spark.Worker\`,.</span><span class="sxs-lookup"><span data-stu-id="0bf05-158">For example, you might download it to the path, `c:\bin\Microsoft.Spark.Worker\`.</span></span>

2. <span data-ttu-id="0bf05-159">Cree una [nueva variable](https://www.java.com/en/download/help/path.xml) de entorno `DotnetWorkerPath` denominada y establézcala en el directorio donde descargó y extrajo **Microsoft. Spark. Worker**.</span><span class="sxs-lookup"><span data-stu-id="0bf05-159">Create a [new environment variable](https://www.java.com/en/download/help/path.xml) called `DotnetWorkerPath` and set it to the directory where you downloaded and extracted the **Microsoft.Spark.Worker**.</span></span> <span data-ttu-id="0bf05-160">Por ejemplo, `c:\bin\Microsoft.Spark.Worker`.</span><span class="sxs-lookup"><span data-stu-id="0bf05-160">For example, `c:\bin\Microsoft.Spark.Worker`.</span></span>

## <a name="clone-the-net-for-apache-spark-github-repo"></a><span data-ttu-id="0bf05-161">Clonar el repositorio de .NET para Apache Spark GitHub</span><span class="sxs-lookup"><span data-stu-id="0bf05-161">Clone the .NET for Apache Spark GitHub repo</span></span>

<span data-ttu-id="0bf05-162">Use el siguiente comando de [GitBash](https://gitforwindows.org/) para clonar el Apache Spark de .net para el repositorio en la máquina.</span><span class="sxs-lookup"><span data-stu-id="0bf05-162">Use the following [GitBash](https://gitforwindows.org/) command to clone the .NET for Apache Spark repo to your machine.</span></span>

```bash
git clone https://github.com/dotnet/spark.git c:\github\dotnet-spark
```

## <a name="write-a-net-for-apache-spark-app"></a><span data-ttu-id="0bf05-163">Escritura de .NET para la aplicación Apache Spark</span><span class="sxs-lookup"><span data-stu-id="0bf05-163">Write a .NET for Apache Spark app</span></span>

1. <span data-ttu-id="0bf05-164">Abra **Visual Studio** y vaya a **archivo > crear nuevo proyecto > aplicación de consola (.net Core)** .</span><span class="sxs-lookup"><span data-stu-id="0bf05-164">Open **Visual Studio** and navigate to **File > Create New Project > Console App (.NET Core)**.</span></span> <span data-ttu-id="0bf05-165">Asigne a la aplicación el nombre **HelloSpark**.</span><span class="sxs-lookup"><span data-stu-id="0bf05-165">Name the application **HelloSpark**.</span></span>

2. <span data-ttu-id="0bf05-166">Instale el [paquete NuGet Microsoft. Spark](https://www.nuget.org/profiles/spark).</span><span class="sxs-lookup"><span data-stu-id="0bf05-166">Install the [Microsoft.Spark NuGet package](https://www.nuget.org/profiles/spark).</span></span> <span data-ttu-id="0bf05-167">Para obtener más información sobre la instalación de paquetes NuGet, consulte [diferentes formas de instalar un paquete Nuget](https://docs.microsoft.com/nuget/consume-packages/ways-to-install-a-package).</span><span class="sxs-lookup"><span data-stu-id="0bf05-167">For more information on installing NuGet packages, see [Different ways to install a NuGet Package](https://docs.microsoft.com/nuget/consume-packages/ways-to-install-a-package).</span></span>

3. <span data-ttu-id="0bf05-168">En **Explorador de soluciones**, Abra **Program.CS** y escriba el código C# siguiente:</span><span class="sxs-lookup"><span data-stu-id="0bf05-168">In **Solution Explorer**, open **Program.cs** and write the following C# code:</span></span>

   ```csharp
     var spark = SparkSession.Builder().GetOrCreate();
     var df = spark.Read().Json("people.json");
     df.Show();
   ```

4. <span data-ttu-id="0bf05-169">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="0bf05-169">Build the solution.</span></span>

## <a name="run-your-net-for-apache-spark-app"></a><span data-ttu-id="0bf05-170">Ejecución de .NET para la aplicación Apache Spark</span><span class="sxs-lookup"><span data-stu-id="0bf05-170">Run your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="0bf05-171">Abra **PowerShell** y cambie el directorio a la carpeta donde se almacena la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0bf05-171">Open **PowerShell** and change the directory to the folder where your app is stored.</span></span>

   ```powershell
   cd <your-app-output-directory>
   ```

2. <span data-ttu-id="0bf05-172">Cree un archivo denominado **People. JSON** con el siguiente contenido:</span><span class="sxs-lookup"><span data-stu-id="0bf05-172">Create a file called **people.json** with the following content:</span></span>

   ```json
   {"name":"Michael"}
   {"name":"Andy", "age":30}
   {"name":"Justin", "age":19}
   ```

3. <span data-ttu-id="0bf05-173">Use el siguiente comando de PowerShell para ejecutar la aplicación:</span><span class="sxs-lookup"><span data-stu-id="0bf05-173">Use the following PowerShell command to run your app:</span></span>

   ```powershell
    spark-submit `
    --class org.apache.spark.deploy.dotnet.DotnetRunner `
    --master local `
    microsoft-spark-2.4.x-<version>.jar `
    dotnet HelloSpark.dll
    ```

<span data-ttu-id="0bf05-174">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="0bf05-174">Congratulations!</span></span> <span data-ttu-id="0bf05-175">Ha creado y ejecutado correctamente .NET para Apache Spark aplicación.</span><span class="sxs-lookup"><span data-stu-id="0bf05-175">You successfully authored and ran a .NET for Apache Spark app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0bf05-176">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="0bf05-176">Next steps</span></span>

<span data-ttu-id="0bf05-177">En este tutorial aprendió lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0bf05-177">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="0bf05-178">Preparar el entorno de Windows para .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="0bf05-178">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="0bf05-179">Descargar **Microsoft. Spark. Worker**</span><span class="sxs-lookup"><span data-stu-id="0bf05-179">Download the **Microsoft.Spark.Worker**</span></span>
> * <span data-ttu-id="0bf05-180">Compilar y ejecutar una aplicación .NET simple para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="0bf05-180">Build and run a simple .NET for Apache Spark application</span></span>

<span data-ttu-id="0bf05-181">Consulte la página de recursos para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="0bf05-181">Check out the resources page to learn more.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="0bf05-182">.NET para recursos de Apache Spark</span><span class="sxs-lookup"><span data-stu-id="0bf05-182">.NET for Apache Spark Resources</span></span>](../resources/index.md)
