---
title: Implementación de .NET para la aplicación Apache Spark en Azure HDInsight
description: Descubra cómo implementar .NET para Apache Spark aplicación en HDInsight.
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 4769c194520790ce217d46d1d3197b20742d4f1a
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2019
ms.locfileid: "69576952"
---
# <a name="deploy-a-net-for-apache-spark-application-to-azure-hdinsight"></a><span data-ttu-id="6b7c4-103">Implementación de .NET para la aplicación Apache Spark en Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="6b7c4-103">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>

<span data-ttu-id="6b7c4-104">En este tutorial se enseña a implementar .NET para Apache Spark aplicación en Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-104">This tutorial teaches how to deploy a .NET for Apache Spark application to Azure HDInsight.</span></span>

<span data-ttu-id="6b7c4-105">En este tutorial, aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="6b7c4-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="6b7c4-106">Preparar Microsoft. Spark. Worker</span><span class="sxs-lookup"><span data-stu-id="6b7c4-106">Prepare Microsoft.Spark.Worker</span></span>
> * <span data-ttu-id="6b7c4-107">Publicación de la aplicación .NET de Spark</span><span class="sxs-lookup"><span data-stu-id="6b7c4-107">Publish your Spark .NET app</span></span>
> * <span data-ttu-id="6b7c4-108">Implementación de la aplicación en Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="6b7c4-108">Deploy your app to Azure HDInsight</span></span>
> * <span data-ttu-id="6b7c4-109">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="6b7c4-109">Run your app</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6b7c4-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6b7c4-110">Prerequisites</span></span>

<span data-ttu-id="6b7c4-111">Antes de empezar, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6b7c4-111">Before you start, do the following:</span></span>

* <span data-ttu-id="6b7c4-112">Descargue [Explorador de Azure Storage](https://azure.microsoft.com/features/storage-explorer/).</span><span class="sxs-lookup"><span data-stu-id="6b7c4-112">Download [Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/).</span></span>
* <span data-ttu-id="6b7c4-113">Descargue [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-113">Download [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to your local machine.</span></span> <span data-ttu-id="6b7c4-114">Este es un script de aplicación auxiliar que se usa más adelante para copiar .NET para Apache Spark archivos dependientes en los nodos de trabajo del clúster de Spark.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-114">This is a helper script that you use later to copy .NET for Apache Spark dependent files into your Spark cluster's worker nodes.</span></span>

## <a name="prepare-worker-dependencies"></a><span data-ttu-id="6b7c4-115">Preparación de las dependencias de trabajo</span><span class="sxs-lookup"><span data-stu-id="6b7c4-115">Prepare worker dependencies</span></span>

<span data-ttu-id="6b7c4-116">**Microsoft. Spark. Worker** es un componente de back-end que reside en los nodos de trabajo individuales del clúster de Spark.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-116">**Microsoft.Spark.Worker** is a backend component that lives on the individual worker nodes of your Spark cluster.</span></span> <span data-ttu-id="6b7c4-117">Cuando desee ejecutar una C# función definida por el usuario (UDF), Spark debe saber cómo iniciar .net CLR para ejecutar la UDF.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-117">When you want to execute a C# UDF (user-defined function), Spark needs to understand how to launch the .NET CLR to execute the UDF.</span></span> <span data-ttu-id="6b7c4-118">**Microsoft. Spark. Worker** proporciona una colección de clases para Spark que habilitan esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-118">**Microsoft.Spark.Worker** provides a collection of classes to Spark that enable this functionality.</span></span>

1. <span data-ttu-id="6b7c4-119">Seleccione una versión de [Microsoft. Spark. Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp para implementarla en el clúster.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-119">Select a [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp release to be deployed on your cluster.</span></span>

   <span data-ttu-id="6b7c4-120">Por ejemplo, si quiere `.NET for Apache Spark v0.1.0` usar `netcoreapp2.1`, descargó [Microsoft. Spark. worker. netcoreapp 2.1. Linux-x64-0.1.0. tar. gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span><span class="sxs-lookup"><span data-stu-id="6b7c4-120">For example, if you want `.NET for Apache Spark v0.1.0` using `netcoreapp2.1`, you'd download [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span></span>

2. <span data-ttu-id="6b7c4-121">Cargue `Microsoft.Spark.Worker.<release>.tar.gz` y [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) en un sistema de archivos distribuido (por ejemplo, HDFS, WASB, ADLS) al que tiene acceso el clúster.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-121">Upload `Microsoft.Spark.Worker.<release>.tar.gz` and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to a distributed file system (e.g., HDFS, WASB, ADLS) that your cluster has access to.</span></span>

## <a name="prepare-your-net-for-apache-spark-app"></a><span data-ttu-id="6b7c4-122">Preparación de .NET para la aplicación Apache Spark</span><span class="sxs-lookup"><span data-stu-id="6b7c4-122">Prepare your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="6b7c4-123">Siga el tutorial de [Introducción](get-started.md) para compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-123">Follow the [Get Started](get-started.md) tutorial to build your app.</span></span>

2. <span data-ttu-id="6b7c4-124">Publique la aplicación .NET de Spark como independiente.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-124">Publish your Spark .NET app as self-contained.</span></span>

   <span data-ttu-id="6b7c4-125">Puede ejecutar el siguiente comando en Linux.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-125">You can run the following command on Linux.</span></span>

   ```bash
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. <span data-ttu-id="6b7c4-126">Producir `<your app>.zip` para los archivos publicados.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-126">Produce `<your app>.zip` for the published files.</span></span>

   <span data-ttu-id="6b7c4-127">Puede ejecutar el siguiente comando en Linux con `zip`.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-127">You can run the following command on Linux using `zip`.</span></span>

   ```bash
   zip -r <your app>.zip .
   ```

4. <span data-ttu-id="6b7c4-128">Cargue lo siguiente en un sistema de archivos distribuido (por ejemplo, HDFS, WASB, ADLS) al que el clúster tiene acceso:</span><span class="sxs-lookup"><span data-stu-id="6b7c4-128">Upload the following to a distributed file system (e.g., HDFS, WASB, ADLS) that your cluster has access to:</span></span>

   * <span data-ttu-id="6b7c4-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: Este archivo jar se incluye como parte del paquete NuGet [Microsoft. Spark](https://www.nuget.org/packages/Microsoft.Spark/) y se encuentra en el directorio de salida de la compilación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: This jar is included as part of the [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet package and is colocated in your app's build output directory.</span></span>
   * `<your app>.zip`
   * <span data-ttu-id="6b7c4-130">Los archivos (como los archivos de dependencia o los datos comunes accesibles para cada trabajo) o los ensamblados (como los archivos DLL que contienen las `app` funciones definidas por el usuario o las bibliotecas de las que depende) se colocan en el directorio de trabajo de cada ejecutor.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-130">Files (like dependency files or common data accessible to every worker) or Assemblies (like DLLs that contain your user-defined functions or libraries that your `app` depends on) to be placed in the working directory of each executor.</span></span>

## <a name="deploy-to-azure-hdinsight-spark"></a><span data-ttu-id="6b7c4-131">Implementar en Azure HDInsight Spark</span><span class="sxs-lookup"><span data-stu-id="6b7c4-131">Deploy to Azure HDInsight Spark</span></span>

<span data-ttu-id="6b7c4-132">[Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-overview) es la implementación de Microsoft de Apache Spark en la nube que permite a los usuarios iniciar y configurar clústeres de Spark en Azure.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-132">[Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-overview) is the Microsoft implementation of Apache Spark in the cloud that allows users to launch and configure Spark clusters in Azure.</span></span> <span data-ttu-id="6b7c4-133">Puede usar los clústeres de HDInsight Spark para procesar los datos almacenados en [Azure Storage](https://azure.microsoft.com/services/storage/) o [Azure Data Lake Storage](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-use-data-lake-storage-gen2).</span><span class="sxs-lookup"><span data-stu-id="6b7c4-133">You can use HDInsight Spark clusters to process your data stored in [Azure Storage](https://azure.microsoft.com/services/storage/) or [Azure Data Lake Storage](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-use-data-lake-storage-gen2).</span></span>

> [!NOTE]
> <span data-ttu-id="6b7c4-134">Azure HDInsight Spark está basado en Linux.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-134">Azure HDInsight Spark is Linux-based.</span></span> <span data-ttu-id="6b7c4-135">Si está interesado en implementar la aplicación en Azure HDInsight Spark, asegúrese de que la aplicación .NET Standard sea compatible y de que use el compilador de [.net Core](https://dotnet.microsoft.com/download) para compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-135">If you are interested in deploying your app to Azure HDInsight Spark, make sure your app is .NET Standard compatible and that you use the [.NET Core compiler](https://dotnet.microsoft.com/download) to compile your app.</span></span>

### <a name="deploy-microsoftsparkworker"></a><span data-ttu-id="6b7c4-136">Implementación de Microsoft. Spark. Worker</span><span class="sxs-lookup"><span data-stu-id="6b7c4-136">Deploy Microsoft.Spark.Worker</span></span>

<span data-ttu-id="6b7c4-137">Este paso solo es necesario para el clúster.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-137">This step is only required once for your cluster.</span></span>

<span data-ttu-id="6b7c4-138">Ejecute `install-worker.sh` en el clúster con [las acciones de script de HDInsight](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux).</span><span class="sxs-lookup"><span data-stu-id="6b7c4-138">Run `install-worker.sh` on the cluster using [HDInsight Script Actions](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux).</span></span>

|<span data-ttu-id="6b7c4-139">Parámetro</span><span class="sxs-lookup"><span data-stu-id="6b7c4-139">Setting</span></span>|<span data-ttu-id="6b7c4-140">Value</span><span class="sxs-lookup"><span data-stu-id="6b7c4-140">Value</span></span>|
|-------|-----|
|<span data-ttu-id="6b7c4-141">Tipo de script</span><span class="sxs-lookup"><span data-stu-id="6b7c4-141">Script type</span></span>|<span data-ttu-id="6b7c4-142">Personalizados</span><span class="sxs-lookup"><span data-stu-id="6b7c4-142">Custom</span></span>|
|<span data-ttu-id="6b7c4-143">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="6b7c4-143">Name</span></span>|<span data-ttu-id="6b7c4-144">Instalación de Microsoft. Spark. Worker</span><span class="sxs-lookup"><span data-stu-id="6b7c4-144">Install Microsoft.Spark.Worker</span></span>|
|<span data-ttu-id="6b7c4-145">URI de script de Bash</span><span class="sxs-lookup"><span data-stu-id="6b7c4-145">Bash script URI</span></span>|<span data-ttu-id="6b7c4-146">El URI en el que cargó `install-worker.sh`.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-146">The URI to which you uploaded `install-worker.sh`.</span></span> <span data-ttu-id="6b7c4-147">Por ejemplo, `abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/install-worker.sh`</span><span class="sxs-lookup"><span data-stu-id="6b7c4-147">For example, `abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/install-worker.sh`</span></span>|
|<span data-ttu-id="6b7c4-148">Tipos de nodo</span><span class="sxs-lookup"><span data-stu-id="6b7c4-148">Node type(s)</span></span>|<span data-ttu-id="6b7c4-149">Trabajo</span><span class="sxs-lookup"><span data-stu-id="6b7c4-149">Worker</span></span>|
|<span data-ttu-id="6b7c4-150">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6b7c4-150">Parameters</span></span>|<span data-ttu-id="6b7c4-151">Parámetros para `install-worker.sh`.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-151">Parameters to `install-worker.sh`.</span></span> <span data-ttu-id="6b7c4-152">Por ejemplo, si cargó `install-worker.sh` en Azure Data Lake Gen 2, `azure abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz /usr/local/bin`sería.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-152">For example, if you uploaded `install-worker.sh` to Azure Data Lake Gen 2 then it would be `azure abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz /usr/local/bin`.</span></span>|

![Imagen de acción de script](./media/hdinsight-deployment/deployment-hdi-action-script.png)

## <a name="run-your-app"></a><span data-ttu-id="6b7c4-154">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="6b7c4-154">Run your app</span></span>

<span data-ttu-id="6b7c4-155">Puede enviar su trabajo a HDInsight de Azure mediante `spark-submit` o Apache Livy.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-155">You can submit your job to Azure HDInsight using `spark-submit` or Apache Livy.</span></span>

### <a name="use-spark-submit"></a><span data-ttu-id="6b7c4-156">Uso de Spark-Submit</span><span class="sxs-lookup"><span data-stu-id="6b7c4-156">Use spark-submit</span></span>

<span data-ttu-id="6b7c4-157">Puede usar el comando [Spark-Submit](https://spark.apache.org/docs/latest/submitting-applications.html) para enviar .net para trabajos Apache Spark a Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-157">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Azure HDInsight.</span></span>
 
1. <span data-ttu-id="6b7c4-158">`ssh`en uno de los nodos principales del clúster.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-158">`ssh` into one of the head nodes in your cluster.</span></span>

1. <span data-ttu-id="6b7c4-159">Ejecutar `spark-submit`:</span><span class="sxs-lookup"><span data-stu-id="6b7c4-159">Run `spark-submit`:</span></span>

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar \
   abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip <your app> <app arg 1> <app arg 2> ... <app arg n>
   ```

### <a name="use-apache-livy"></a><span data-ttu-id="6b7c4-160">Uso de Apache Livy</span><span class="sxs-lookup"><span data-stu-id="6b7c4-160">Use Apache Livy</span></span>

<span data-ttu-id="6b7c4-161">Puede usar [Apache Livy](https://livy.incubator.apache.org/), la API de REST Apache Spark, para enviar .net para trabajos de Apache Spark a un clúster de Azure HDInsight Spark.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-161">You can use [Apache Livy](https://livy.incubator.apache.org/), the Apache Spark REST API, to submit .NET for Apache Spark jobs to an Azure HDInsight Spark cluster.</span></span> <span data-ttu-id="6b7c4-162">Para obtener más información, vea [trabajos remotos con Apache Livy](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface).</span><span class="sxs-lookup"><span data-stu-id="6b7c4-162">For more information, see [Remote jobs with Apache Livy](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface).</span></span>

<span data-ttu-id="6b7c4-163">Puede ejecutar el siguiente comando en Linux con `curl`:</span><span class="sxs-lookup"><span data-stu-id="6b7c4-163">You can run the following command on Linux using `curl`:</span></span>

```bash
curl -k -v -X POST "https://<your spark cluster>.azurehdinsight.net/livy/batches" \
-u "<hdinsight username>:<hdinsight password>" \
-H "Content-Type: application/json" \
-H "X-Requested-By: <hdinsight username>" \
-d @- << EOF
{
    "file":"abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar",
    "className":"org.apache.spark.deploy.DotnetRunner",
    "files":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<udf assembly>", "abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<file>"],
    "args":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip","<your app>","<app arg 1>","<app arg 2>,"...","<app arg n>"]
}
EOF
```

## <a name="next-steps"></a><span data-ttu-id="6b7c4-164">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="6b7c4-164">Next steps</span></span>

<span data-ttu-id="6b7c4-165">En este tutorial, ha implementado .NET para Apache Spark aplicación en Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-165">In this tutorial, you deployed your .NET for Apache Spark application to Azure HDInsight.</span></span> <span data-ttu-id="6b7c4-166">Para más información sobre HDInsight, continúe con la documentación de HDInsight de Azure.</span><span class="sxs-lookup"><span data-stu-id="6b7c4-166">To learn more about HDInsight, continue to the Azure HDInsight Documentation.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6b7c4-167">Documentación de HDInsight de Azure</span><span class="sxs-lookup"><span data-stu-id="6b7c4-167">Azure HDInsight Documentation</span></span>](https://docs.microsoft.com/azure/hdinsight/)
