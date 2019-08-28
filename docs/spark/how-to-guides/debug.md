---
title: Depuración de una aplicación de .NET para Apache Spark en Windows
description: Sepa cómo depurar una aplicación de .NET para Apache Spark en Windows.
ms.date: 08/15/2019
ms.topic: how-to
ms.custom: mvc
ms.openlocfilehash: 08142bd45c475ddd131053213ebdea5f843fa736
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69667673"
---
# <a name="debug-a-net-for-apache-spark-application"></a><span data-ttu-id="9f8d6-103">Depuración de una aplicación de .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="9f8d6-103">Debug a .NET for Apache Spark application</span></span>

<span data-ttu-id="9f8d6-104">En este procedimiento encontrará los comandos que hay que ejecutar para depurar la aplicación de .NET para Apache Spark y el código de Scala en Windows.</span><span class="sxs-lookup"><span data-stu-id="9f8d6-104">This how-to provides the commands you need to run to debug your .NET for Apache Spark application and Scala code on Windows.</span></span>

## <a name="debug-your-application"></a><span data-ttu-id="9f8d6-105">Depuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="9f8d6-105">Debug your application</span></span>

<span data-ttu-id="9f8d6-106">Abra una nueva ventana del símbolo del sistema y ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9f8d6-106">Open a new command prompt window, run the following:</span></span>

```shell
spark-submit \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  debug
```

<span data-ttu-id="9f8d6-107">Al ejecutar el comando, verá la siguiente salida:</span><span class="sxs-lookup"><span data-stu-id="9f8d6-107">When you run the command, you see the following output:</span></span>

```
***********************************************************************
* .NET Backend running debug mode. Press enter to exit *
***********************************************************************
```

<span data-ttu-id="9f8d6-108">En este modo de depuración, `DotnetRunner` no inicia la aplicación .NET, sino que espera a que se conecte.</span><span class="sxs-lookup"><span data-stu-id="9f8d6-108">In this debug mode, `DotnetRunner` does not launch the .NET application, but it waits for it to connect.</span></span> <span data-ttu-id="9f8d6-109">Deje abierta esta ventana del símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="9f8d6-109">Leave this command prompt window open.</span></span>

<span data-ttu-id="9f8d6-110">Ahora puede ejecutar la aplicación .NET con cualquier depurador para depurarla.</span><span class="sxs-lookup"><span data-stu-id="9f8d6-110">Now you can run your .NET application with any debugger to debug your application.</span></span>

## <a name="debug-scala-code"></a><span data-ttu-id="9f8d6-111">Depuración de código de Scala</span><span class="sxs-lookup"><span data-stu-id="9f8d6-111">Debug Scala code</span></span>

<span data-ttu-id="9f8d6-112">Si necesita depurar el código de Scala, como `DotnetRunner` o `DotnetBackendHandler`, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="9f8d6-112">If you need to debug the Scala side code, such as `DotnetRunner` or `DotnetBackendHandler`, run the following command:</span></span>

```shell
spark-submit \
  --driver-java-options -agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=5005 \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  <path-to-your-app-exe> <argument(s)-to-your-app>
```

<span data-ttu-id="9f8d6-113">Después de ejecutar el comando, asocie un depurador al proceso en ejecución mediante [Intellij](https://www.jetbrains.com/help/idea/attaching-to-local-process.html).</span><span class="sxs-lookup"><span data-stu-id="9f8d6-113">After you run the command, attach a debugger to the running process using [Intellij](https://www.jetbrains.com/help/idea/attaching-to-local-process.html).</span></span>

## <a name="next-steps"></a><span data-ttu-id="9f8d6-114">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="9f8d6-114">Next steps</span></span>

* [<span data-ttu-id="9f8d6-115">Introducción a .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="9f8d6-115">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
* [<span data-ttu-id="9f8d6-116">Implementación de una aplicación de .NET para Apache Spark en Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="9f8d6-116">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>](../tutorials/hdinsight-deployment.md)
* [<span data-ttu-id="9f8d6-117">Implementación de una aplicación de .NET para Apache Spark en Databricks</span><span class="sxs-lookup"><span data-stu-id="9f8d6-117">Deploy a .NET for Apache Spark application to Databricks</span></span>](../tutorials/databricks-deployment.md)
* [<span data-ttu-id="9f8d6-118">Implementación de una aplicación de .NET para Apache Spark en Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="9f8d6-118">Deploy a .NET for Apache Spark application to Amazon EMR Spark</span></span>](../tutorials/amazon-emr-spark-deployment.md)