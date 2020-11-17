---
title: Uso de Jupyter Notebooks
titleSuffix: .NET for Apache Spark
description: Uso de .NET para Apache Spark en entornos interactivos como Jupyter Notebook, Jupyter Lab o Visual Studio Code (VS Code)
ms.author: luquinta
author: luisquintanilla
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc, how-to
ms.openlocfilehash: eb285465fcacc3e7d4ee60765c30497dcefbc737
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "94441068"
---
# <a name="use-net-for-apache-spark-in-jupyter-notebooks"></a><span data-ttu-id="ef612-103">Uso de .NET para Apache Spark en cuadernos de Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="ef612-103">Use .NET for Apache Spark in Jupyter notebooks</span></span>

<span data-ttu-id="ef612-104">En este artículo, aprenderá a ejecutar trabajos de .NET para Apache Spark de forma interactiva en Jupyter Notebook y Visual Studio Code (VS Code) con .NET Interactive.</span><span class="sxs-lookup"><span data-stu-id="ef612-104">In this article, you learn how to run .NET for Apache Spark jobs interactively in Jupyter Notebook and Visual Studio Code (VS Code) with .NET Interactive.</span></span>

## <a name="about-jupyter"></a><span data-ttu-id="ef612-105">Acerca de Jupyter</span><span class="sxs-lookup"><span data-stu-id="ef612-105">About Jupyter</span></span>

<span data-ttu-id="ef612-106">[Jupyter](https://jupyter.org/) es un entorno informático multiplataforma de código abierto que permite a los usuarios crear prototipos y desarrollar aplicaciones de forma interactiva.</span><span class="sxs-lookup"><span data-stu-id="ef612-106">[Jupyter](https://jupyter.org/) is an open-source, cross-platform computing environment that provides a way for users to prototype and develop applications interactively.</span></span> <span data-ttu-id="ef612-107">Puede interactuar con Jupyter a través de una amplia variedad de interfaces como Jupyter Notebook, Jupyter Lab y VS Code.</span><span class="sxs-lookup"><span data-stu-id="ef612-107">You can interact with Jupyter through a wide variety of interfaces such as Jupyter Notebook, Jupyter Lab, and VS Code.</span></span>

<span data-ttu-id="ef612-108">En el contexto de .NET, [.NET Interactive](https://github.com/dotnet/interactive), una herramienta global de .NET Core, proporciona un kernel para escribir código de .NET (C# o F#) en entornos informáticos interactivos como Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="ef612-108">In the context of .NET, [.NET Interactive](https://github.com/dotnet/interactive), a .NET Core global tool, provides a kernel for writing .NET code (C#/F#) in interactive computing environments such as Jupyter Notebook.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ef612-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ef612-109">Prerequisites</span></span>

- [<span data-ttu-id="ef612-110">SDK de .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="ef612-110">.NET Core 3.1 SDK</span></span>](../../core/install/index.yml)
- [<span data-ttu-id="ef612-111">Spark de Apache</span><span class="sxs-lookup"><span data-stu-id="ef612-111">Apache Spark</span></span>](https://spark.apache.org/downloads.html)
- [<span data-ttu-id="ef612-112">Trabajo de .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="ef612-112">Apache Spark .NET Worker</span></span>](https://github.com/dotnet/spark/releases)

<span data-ttu-id="ef612-113">Vea el [tutorial de introducción](../tutorials/get-started.md) para obtener más información sobre cómo configurar el entorno de .NET para Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="ef612-113">See the [getting started tutorial](../tutorials/get-started.md) for more information on setting up your .NET for Apache Spark environment.</span></span>

## <a name="prepare-environment"></a><span data-ttu-id="ef612-114">Preparación del entorno</span><span class="sxs-lookup"><span data-stu-id="ef612-114">Prepare environment</span></span>

<span data-ttu-id="ef612-115">Para trabajar con cuadernos de Jupyter Notebook, necesitará dos cosas.</span><span class="sxs-lookup"><span data-stu-id="ef612-115">To work with Jupyter Notebooks, you'll need two things.</span></span>

1. <span data-ttu-id="ef612-116">Instalar la [herramienta global de .NET .NET Interactive](https://github.com/dotnet/interactive/blob/main/docs/NotebooksLocalExperience.md).</span><span class="sxs-lookup"><span data-stu-id="ef612-116">Install the [.NET Interactive global .NET tool](https://github.com/dotnet/interactive/blob/main/docs/NotebooksLocalExperience.md)</span></span>
1. <span data-ttu-id="ef612-117">Descargar el paquete NuGet `Microsoft.Spark`.</span><span class="sxs-lookup"><span data-stu-id="ef612-117">Download the `Microsoft.Spark` NuGet package.</span></span>
    1. <span data-ttu-id="ef612-118">Vaya hasta la página del paquete NuGet [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/).</span><span class="sxs-lookup"><span data-stu-id="ef612-118">Navigate to the [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet package page.</span></span>

        > [!IMPORTANT]
        > <span data-ttu-id="ef612-119">De forma predeterminada, se descarga la versión más reciente del paquete.</span><span class="sxs-lookup"><span data-stu-id="ef612-119">By default, the latest version of the package is downloaded.</span></span> <span data-ttu-id="ef612-120">**Asegúrese de que la versión que descarga es la misma que la del trabajo de .NET para Apache Spark.**</span><span class="sxs-lookup"><span data-stu-id="ef612-120">**Make sure that the version you download is the same as your Apache Spark .NET Worker.**</span></span>

    1. <span data-ttu-id="ef612-121">En el panel **Info** (Información), seleccione **Download package** (Descargar paquete) para descargar la versión más reciente del paquete.</span><span class="sxs-lookup"><span data-stu-id="ef612-121">In the **Info** pane, select **Download package** to download the latest version of the package.</span></span> <span data-ttu-id="ef612-122">El nombre del paquete es similar a *microsoft.spark.[VERSIÓN_DEL_PAQUETE].nupkg*.</span><span class="sxs-lookup"><span data-stu-id="ef612-122">The name of the package is similar to  *microsoft.spark.[PACKAGE-VERSION].nupkg*.</span></span>
    1. <span data-ttu-id="ef612-123">Descomprima el paquete descargado.</span><span class="sxs-lookup"><span data-stu-id="ef612-123">Unzip the downloaded package.</span></span> <span data-ttu-id="ef612-124">El directorio descomprimido debe contener un subdirectorio con el nombre *jars*.</span><span class="sxs-lookup"><span data-stu-id="ef612-124">The unzipped directory should contain a subdirectory called *jars*.</span></span> <span data-ttu-id="ef612-125">Anote la ruta de acceso, ya que se usará más adelante.</span><span class="sxs-lookup"><span data-stu-id="ef612-125">Take note of the path since it's used at a later time.</span></span>

## <a name="start-net-for-apache-spark"></a><span data-ttu-id="ef612-126">Inicio de .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="ef612-126">Start .NET for Apache Spark</span></span>

<span data-ttu-id="ef612-127">Ejecute el comando siguiente para iniciar .NET para Apache Spark en modo de depuración.</span><span class="sxs-lookup"><span data-stu-id="ef612-127">Run the following command to start .NET for Apache Spark in debug mode.</span></span> <span data-ttu-id="ef612-128">Este comando `spark-submit` inicia un proceso y espera conexiones de un objeto [SparkSession](xref:Microsoft.Spark.Sql.SparkSession).</span><span class="sxs-lookup"><span data-stu-id="ef612-128">This `spark-submit` command starts a process and waits for connections from a [SparkSession](xref:Microsoft.Spark.Sql.SparkSession).</span></span> <span data-ttu-id="ef612-129">Asegúrese de proporcionar la ruta de acceso al archivo `microsoft-spark-<version>.jar` de la versión correspondiente de .NET para Apache Spark que use.</span><span class="sxs-lookup"><span data-stu-id="ef612-129">Make sure to provide the path to the `microsoft-spark-<version>.jar` for the respective version of .NET for Apache Spark you're using.</span></span>

<span data-ttu-id="ef612-130">**Ubuntu**</span><span class="sxs-lookup"><span data-stu-id="ef612-130">**Ubuntu**</span></span>

```bash
spark-submit \
    --class org.apache.spark.deploy.dotnet.DotnetRunner \
    --master local \
    <path-to-microsoft-spark-jar> \
    debug
```

<span data-ttu-id="ef612-131">**Windows**</span><span class="sxs-lookup"><span data-stu-id="ef612-131">**Windows**</span></span>

```cmd
spark-submit ^
    --class org.apache.spark.deploy.dotnet.DotnetRunner ^
    --master local ^
    <path-to-microsoft-spark-jar> ^
    debug
```

## <a name="create-a-notebook"></a><span data-ttu-id="ef612-132">Creación de un cuaderno</span><span class="sxs-lookup"><span data-stu-id="ef612-132">Create a notebook</span></span>

<span data-ttu-id="ef612-133">Puede usar diferentes interfaces para interactuar con Jupyter.</span><span class="sxs-lookup"><span data-stu-id="ef612-133">You can use different interfaces to interact with Jupyter.</span></span> <span data-ttu-id="ef612-134">Para una interfaz basada en el explorador, use cuadernos de Jupyter Notebook o Jupyter Lab.</span><span class="sxs-lookup"><span data-stu-id="ef612-134">For a browser-based interface, use Jupyter Notebooks or Jupyter Lab.</span></span> <span data-ttu-id="ef612-135">Para una experiencia de editor local, use VS Code.</span><span class="sxs-lookup"><span data-stu-id="ef612-135">For a local editor experience, use VS Code.</span></span>

### <a name="jupyter-notebooks--jupyter-lab"></a><span data-ttu-id="ef612-136">Cuadernos de Jupyter Notebook y Jupyter Lab</span><span class="sxs-lookup"><span data-stu-id="ef612-136">Jupyter Notebooks & Jupyter Lab</span></span>

1. <span data-ttu-id="ef612-137">En otro símbolo del sistema, inicie Jupyter Notebook o Jupyter Lab con uno de los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ef612-137">In another command prompt, start Jupyter Notebook or Jupyter Lab using one of the commands below:</span></span>

    <span data-ttu-id="ef612-138">**Jupyter Notebook**</span><span class="sxs-lookup"><span data-stu-id="ef612-138">**Jupyter Notebook**</span></span>

    ```bash
    jupyter notebook
    ```

    <span data-ttu-id="ef612-139">**Jupyter Lab**</span><span class="sxs-lookup"><span data-stu-id="ef612-139">**Jupyter Lab**</span></span>

    ```bash
    jupyter lab
    ```

    <span data-ttu-id="ef612-140">Estos comandos inician una ventana del explorador con la interfaz de Jupyter Notebook o Jupyter Lab.</span><span class="sxs-lookup"><span data-stu-id="ef612-140">These commands launch a browser window with the Jupyter Notebook or Jupyter Lab interface.</span></span>

1. <span data-ttu-id="ef612-141">En el explorador, cree un cuaderno.</span><span class="sxs-lookup"><span data-stu-id="ef612-141">In the browser, create a new notebook.</span></span>

    <span data-ttu-id="ef612-142">**Jupyter Notebook**</span><span class="sxs-lookup"><span data-stu-id="ef612-142">**Jupyter Notebook**</span></span>

    <span data-ttu-id="ef612-143">Seleccione **Nuevo > .NET (C#)** o **Nuevo > .NET (F#)**</span><span class="sxs-lookup"><span data-stu-id="ef612-143">Select **New > .NET (C#)** or **New > .NET (F#)**</span></span>

    <span data-ttu-id="ef612-144">**Jupyter Lab**</span><span class="sxs-lookup"><span data-stu-id="ef612-144">**Jupyter Lab**</span></span>

    <span data-ttu-id="ef612-145">En la ventana Launcher, seleccione **.NET (C#)** o **.NET (F#)**</span><span class="sxs-lookup"><span data-stu-id="ef612-145">In the Launcher window, select **.NET (C#)** or **.NET (F#)**</span></span>

### <a name="visual-studio-code-preview"></a><span data-ttu-id="ef612-146">Visual Studio Code (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="ef612-146">Visual Studio Code (preview)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ef612-147">Para usar cuadernos de Jupyter Notebook en VS Code, debe instalar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ef612-147">To use Jupyter Notebooks in VS Code, you have to install:</span></span>
>
>- [<span data-ttu-id="ef612-148">VS Code Insiders</span><span class="sxs-lookup"><span data-stu-id="ef612-148">VS Code Insiders</span></span>](https://code.visualstudio.com/insiders/)
>- [<span data-ttu-id="ef612-149">La extensión .NET Interactive Notebooks</span><span class="sxs-lookup"><span data-stu-id="ef612-149">.NET Interactive Notebooks extension</span></span>](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.dotnet-interactive-vscode)

1. <span data-ttu-id="ef612-150">Abra VS Code.</span><span class="sxs-lookup"><span data-stu-id="ef612-150">Open VS Code.</span></span>
1. <span data-ttu-id="ef612-151">Abra la paleta de comandos **Ver > Paleta de comandos**.</span><span class="sxs-lookup"><span data-stu-id="ef612-151">Open the command palette **View > Command Palette**.</span></span>

    <span data-ttu-id="ef612-152">Cuando aparezca la paleta de comandos, escriba el comando siguiente para crear un cuaderno de .NET Interactive:</span><span class="sxs-lookup"><span data-stu-id="ef612-152">When the command palette appears, enter the following command to create a new .NET Interactive notebook:</span></span>

    ```text
    >.NET Interactive: Create new blank notebook
    ```

    <span data-ttu-id="ef612-153">Como alternativa, si quiere abrir un cuaderno de .NET Interactive existente con la extensión *.ipynb*, use el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="ef612-153">Alternatively, if you want to open an existing .NET Interactive notebook with the *.ipynb* extension, use the following command:</span></span>

    ```text
    >.NET Interactive: Open notebook
    ```

## <a name="initialize-a-spark-session"></a><span data-ttu-id="ef612-154">Inicialización de una sesión de Spark</span><span class="sxs-lookup"><span data-stu-id="ef612-154">Initialize a Spark Session</span></span>

1. <span data-ttu-id="ef612-155">Cuando se abra el cuaderno, instale el paquete NuGet `Microsoft.Spark`.</span><span class="sxs-lookup"><span data-stu-id="ef612-155">When the notebook opens, install the `Microsoft.Spark` NuGet package.</span></span> <span data-ttu-id="ef612-156">Asegúrese de que la versión que instala es la misma que la del trabajo de .NET.</span><span class="sxs-lookup"><span data-stu-id="ef612-156">Make sure the version you install is the same as the .NET Worker.</span></span>

    ```text
    #r "nuget:Microsoft.Spark, 0.12.1"
    ```

1. <span data-ttu-id="ef612-157">Agregue la siguiente instrucción using al cuaderno.</span><span class="sxs-lookup"><span data-stu-id="ef612-157">Add the following using statement to the notebook.</span></span>

    ```csharp
    using Microsoft.Spark.Sql;
    ```

1. <span data-ttu-id="ef612-158">Inicialice el objeto [SparkSession](xref:Microsoft.Spark.Sql.SparkSession).</span><span class="sxs-lookup"><span data-stu-id="ef612-158">Initialize your [SparkSession](xref:Microsoft.Spark.Sql.SparkSession).</span></span>

    ```csharp
    var sparkSession =
    SparkSession
        .Builder()
        .AppName("dotnet-interactive-spark")
        .GetOrCreate();
    ```

<span data-ttu-id="ef612-159">El cuaderno debe ser similar al de la imagen siguiente.</span><span class="sxs-lookup"><span data-stu-id="ef612-159">The notebook should look similar to the one in the following image.</span></span> <span data-ttu-id="ef612-160">En este ejemplo se usa VS Code, pero Jupyter Notebook y Jupyter Lab deberían tener un aspecto similar.</span><span class="sxs-lookup"><span data-stu-id="ef612-160">This example uses VS Code, but Jupyter Notebook and Jupyter Lab should look about the same.</span></span>

> [!div class="mx-imgBorder"]
<span data-ttu-id="ef612-161">![.NET para Apache Spark, Jupyter Notebook y VS Code](media/dotnet-spark-jupyter-notebooks/jupyter-notebooks-dotnet-spark-vscode.png)</span><span class="sxs-lookup"><span data-stu-id="ef612-161">![.NET for Apache Spark Jupyter Notebook VS Code](media/dotnet-spark-jupyter-notebooks/jupyter-notebooks-dotnet-spark-vscode.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="ef612-162">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="ef612-162">Next Steps</span></span>

- [<span data-ttu-id="ef612-163">Introducción a .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="ef612-163">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
- [<span data-ttu-id="ef612-164">Predicción de opiniones con .NET para Apache Spark y ML.NET</span><span class="sxs-lookup"><span data-stu-id="ef612-164">Predict sentiment using .NET for Apache Spark and ML.NET</span></span>](../tutorials/ml-sentiment-analysis.md)
- <span data-ttu-id="ef612-165">Para obtener más información sobre .NET Interactive, vea la [documentación de .NET Interactive](https://github.com/dotnet/interactive/blob/main/docs/README.md).</span><span class="sxs-lookup"><span data-stu-id="ef612-165">For more information on .NET Interactive, see the [.NET Interactive documentation](https://github.com/dotnet/interactive/blob/main/docs/README.md).</span></span>
