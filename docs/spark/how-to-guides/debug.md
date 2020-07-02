---
title: Depuración de una aplicación de .NET para Apache Spark en Windows
description: Sepa cómo depurar una aplicación de .NET para Apache Spark en Windows.
ms.date: 06/25/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 9209d5bdec6dd85f6d21a502fb07204effef1934
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617761"
---
# <a name="debug-a-net-for-apache-spark-application"></a><span data-ttu-id="4aac5-103">Depuración de una aplicación de .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="4aac5-103">Debug a .NET for Apache Spark application</span></span>

<span data-ttu-id="4aac5-104">En este procedimiento se proporcionan los pasos para depurar una aplicación de .NET para Apache Spark en Windows.</span><span class="sxs-lookup"><span data-stu-id="4aac5-104">This how-to provides the steps to debug your .NET for Apache Spark application on Windows.</span></span>

[!INCLUDE [spark-preview-note](../../../includes/spark-preview-note.md)]

## <a name="debug-your-application"></a><span data-ttu-id="4aac5-105">Depuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="4aac5-105">Debug your application</span></span>

<span data-ttu-id="4aac5-106">Abra una ventana nueva del símbolo del sistema y ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="4aac5-106">Open a new command prompt window and run the following command:</span></span>

```shell
spark-submit \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  debug
```

<span data-ttu-id="4aac5-107">Al ejecutar el comando, verá la siguiente salida:</span><span class="sxs-lookup"><span data-stu-id="4aac5-107">When you run the command, you see the following output:</span></span>

```console
***********************************************************************
* .NET Backend running debug mode. Press enter to exit *
***********************************************************************
```

<span data-ttu-id="4aac5-108">En el modo de depuración, DotnetRunner no inicia la aplicación de .NET, sino que espera a que el usuario inicie la aplicación de .NET.</span><span class="sxs-lookup"><span data-stu-id="4aac5-108">In debug mode, DotnetRunner does not launch the .NET application, but instead waits for you to start the .NET app.</span></span> <span data-ttu-id="4aac5-109">Deje abierta esta ventana del símbolo del sistema e inicie la aplicación de .NET a través del depurador de C# para depurar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4aac5-109">Leave this command prompt window open and start your .NET application through C# debugger to debug your application.</span></span> <span data-ttu-id="4aac5-110">Inicie la depuración de .NET con un depurador de C# (el [depurador de Visual Studio para Windows/macOS](https://visualstudio.microsoft.com/vs/) o la [extensión del depurador de C# en Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging)) para depurar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4aac5-110">Start your .NET application with a C# debugger ([Visual Studio Debugger for Windows/macOS](https://visualstudio.microsoft.com/vs/) or [C# Debugger Extension in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging)) to debug your application.</span></span>

## <a name="debug-a-user-defined-function-udf"></a><span data-ttu-id="4aac5-111">Depuración de una función definida por el usuario (UDF)</span><span class="sxs-lookup"><span data-stu-id="4aac5-111">Debug a user-defined function (UDF)</span></span>

> [!NOTE]
> <span data-ttu-id="4aac5-112">Las funciones definidas por el usuario solo se admiten en Windows con el depurador de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4aac5-112">User-defined functions are supported only on Windows with Visual Studio Debugger.</span></span>

<span data-ttu-id="4aac5-113">Antes de ejecutar `spark-submit`, establezca esta variable de entorno:</span><span class="sxs-lookup"><span data-stu-id="4aac5-113">Before running `spark-submit`, set the following environment variable:</span></span>

```bat
set DOTNET_WORKER_DEBUG=1
```

<span data-ttu-id="4aac5-114">Al ejecutar la aplicación de Spark, aparecerá una ventana de `Choose Just-In-Time Debugger`.</span><span class="sxs-lookup"><span data-stu-id="4aac5-114">When you run your Spark application, a `Choose Just-In-Time Debugger` window will pop up.</span></span> <span data-ttu-id="4aac5-115">Elija un depurador de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4aac5-115">Choose a Visual Studio debugger.</span></span>

<span data-ttu-id="4aac5-116">El depurador se interrumpirá en esta ubicación en [TaskRunner.cs](https://github.com/dotnet/spark/blob/5e9c08b430b4bc56b5f42252c4b73437377afaed/src/csharp/Microsoft.Spark.Worker/TaskRunner.cs#L52):</span><span class="sxs-lookup"><span data-stu-id="4aac5-116">The debugger will break at the following location in [TaskRunner.cs](https://github.com/dotnet/spark/blob/5e9c08b430b4bc56b5f42252c4b73437377afaed/src/csharp/Microsoft.Spark.Worker/TaskRunner.cs#L52):</span></span>

```csharp
if (EnvironmentUtils.GetEnvironmentVariableAsBool("DOTNET_WORKER_DEBUG"))
{
    Debugger.Launch(); // <-- The debugger will break here.
}
```

<span data-ttu-id="4aac5-117">Vaya al archivo *.cs* que contiene la UDF que va a depurar y [establezca un punto de interrupción](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints?view=vs-2019).</span><span class="sxs-lookup"><span data-stu-id="4aac5-117">Navigate to the *.cs* file that contains the UDF that you plan to debug, and [set a breakpoint](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints?view=vs-2019).</span></span> <span data-ttu-id="4aac5-118">El punto de interrupción indicará `The breakpoint will not currently be hit`, porque el trabajo todavía no ha cargado el ensamblado que contiene la UDF.</span><span class="sxs-lookup"><span data-stu-id="4aac5-118">The breakpoint will say `The breakpoint will not currently be hit` because the worker hasn't loaded the assembly that contains UDF yet.</span></span>

<span data-ttu-id="4aac5-119">Presione `F5` para continuar la aplicación y, a la larga, se alcanzará el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="4aac5-119">Hit `F5` to continue your application and the breakpoint will eventually be hit.</span></span>

> [!NOTE]
> <span data-ttu-id="4aac5-120">La ventana Choose Just-In-Time Debugger (Elegir el depurador Just-In-Time) aparece para cada tarea.</span><span class="sxs-lookup"><span data-stu-id="4aac5-120">The Choose Just-In-Time Debugger window pops up for each task.</span></span> <span data-ttu-id="4aac5-121">Para evitar un exceso de elementos emergentes, establezca el número de ejecutores en un número bajo.</span><span class="sxs-lookup"><span data-stu-id="4aac5-121">To avoid excessive pop-ups, set the number of executors to a low number.</span></span> <span data-ttu-id="4aac5-122">Por ejemplo, puede usar la opción **--master local[1]** para spark-submit para establecer el número de tareas en 1, lo que inicia una instancia de depurador única.</span><span class="sxs-lookup"><span data-stu-id="4aac5-122">For example, you can use the **--master local[1]** option for spark-submit to set the number of tasks to 1, which launches a single debugger instance.</span></span>

## <a name="debug-scala-code"></a><span data-ttu-id="4aac5-123">Depuración de código de Scala</span><span class="sxs-lookup"><span data-stu-id="4aac5-123">Debug Scala code</span></span>

<span data-ttu-id="4aac5-124">Si tiene que depurar el código de Scala (`DotnetRunner`, `DotnetBackendHandler`, etc.), puede usar el comando siguiente y adjuntar un depurador al proceso en ejecución mediante [IntelliJ](https://www.jetbrains.com/help/idea/attaching-to-local-process.html):</span><span class="sxs-lookup"><span data-stu-id="4aac5-124">If you need to debug the Scala-side code (`DotnetRunner`, `DotnetBackendHandler`, etc.), you can use the following command and attach a debugger to the running process using [IntelliJ](https://www.jetbrains.com/help/idea/attaching-to-local-process.html):</span></span>

```shell
spark-submit \
  --driver-java-options -agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=5005 \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  <path-to-your-app-exe> <argument(s)-to-your-app>
```

<span data-ttu-id="4aac5-125">Después de ejecutar el comando, asocie un depurador al proceso en ejecución mediante [Intellij](https://www.jetbrains.com/help/idea/attaching-to-local-process.html).</span><span class="sxs-lookup"><span data-stu-id="4aac5-125">After you run the command, attach a debugger to the running process using [Intellij](https://www.jetbrains.com/help/idea/attaching-to-local-process.html).</span></span>

## <a name="next-steps"></a><span data-ttu-id="4aac5-126">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="4aac5-126">Next steps</span></span>

* [<span data-ttu-id="4aac5-127">Introducción a .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="4aac5-127">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
* [<span data-ttu-id="4aac5-128">Implementación de una aplicación de .NET para Apache Spark en Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="4aac5-128">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>](../tutorials/hdinsight-deployment.md)
* [<span data-ttu-id="4aac5-129">Implementación de una aplicación de .NET para Apache Spark en Databricks</span><span class="sxs-lookup"><span data-stu-id="4aac5-129">Deploy a .NET for Apache Spark application to Databricks</span></span>](../tutorials/databricks-deployment.md)
* [<span data-ttu-id="4aac5-130">Implementación de una aplicación de .NET para Apache Spark en Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="4aac5-130">Deploy a .NET for Apache Spark application to Amazon EMR Spark</span></span>](../tutorials/amazon-emr-spark-deployment.md)
