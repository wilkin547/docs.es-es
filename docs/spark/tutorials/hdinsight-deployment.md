---
title: Implementación de una aplicación de .NET para Apache Spark en Azure HDInsight
description: Aprenda a implementar una aplicación de .NET para Apache Spark en HDInsight.
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 81d1af1fd4e3329c4a289eea388edf8af57d7c4e
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70243947"
---
# <a name="deploy-a-net-for-apache-spark-application-to-azure-hdinsight"></a><span data-ttu-id="4f715-103">Implementación de una aplicación de .NET para Apache Spark en Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="4f715-103">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>

<span data-ttu-id="4f715-104">En este tutorial aprenderá a implementar una aplicación de .NET para Apache Spark en Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="4f715-104">This tutorial teaches how to deploy a .NET for Apache Spark application to Azure HDInsight.</span></span>

<span data-ttu-id="4f715-105">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="4f715-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="4f715-106">Preparar Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="4f715-106">Prepare Microsoft.Spark.Worker</span></span>
> * <span data-ttu-id="4f715-107">Publicar la aplicación de .NET para Spark</span><span class="sxs-lookup"><span data-stu-id="4f715-107">Publish your Spark .NET app</span></span>
> * <span data-ttu-id="4f715-108">Implementar de una aplicación en Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="4f715-108">Deploy your app to Azure HDInsight</span></span>
> * <span data-ttu-id="4f715-109">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="4f715-109">Run your app</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4f715-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4f715-110">Prerequisites</span></span>

<span data-ttu-id="4f715-111">Antes de empezar, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4f715-111">Before you start, do the following:</span></span>

* <span data-ttu-id="4f715-112">Descargue el [Explorador de Azure Storage](https://azure.microsoft.com/features/storage-explorer/).</span><span class="sxs-lookup"><span data-stu-id="4f715-112">Download [Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/).</span></span>
* <span data-ttu-id="4f715-113">Descargue [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="4f715-113">Download [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to your local machine.</span></span> <span data-ttu-id="4f715-114">Es un script de aplicación auxiliar que usaremos más adelante para copiar archivos dependientes de .NET para Apache Spark en los nodos de trabajo del clúster de Spark.</span><span class="sxs-lookup"><span data-stu-id="4f715-114">This is a helper script that you use later to copy .NET for Apache Spark dependent files into your Spark cluster's worker nodes.</span></span>

## <a name="prepare-worker-dependencies"></a><span data-ttu-id="4f715-115">Preparación de las dependencias de trabajo</span><span class="sxs-lookup"><span data-stu-id="4f715-115">Prepare worker dependencies</span></span>

<span data-ttu-id="4f715-116">**Microsoft.Spark.Worker** es un componente back-end que reside en los nodos de trabajo individuales del clúster de Spark.</span><span class="sxs-lookup"><span data-stu-id="4f715-116">**Microsoft.Spark.Worker** is a backend component that lives on the individual worker nodes of your Spark cluster.</span></span> <span data-ttu-id="4f715-117">Si quiere ejecutar una función definida por el usuario (UDF) de C#, Spark necesita saber cómo iniciar .NET CLR para ejecutar la UDF.</span><span class="sxs-lookup"><span data-stu-id="4f715-117">When you want to execute a C# UDF (user-defined function), Spark needs to understand how to launch the .NET CLR to execute the UDF.</span></span> <span data-ttu-id="4f715-118">**Microsoft.Spark.Worker** pone a disposición de Spark una colección de clases que habilitan esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="4f715-118">**Microsoft.Spark.Worker** provides a collection of classes to Spark that enable this functionality.</span></span>

1. <span data-ttu-id="4f715-119">Seleccione una versión netcoreapp de Linux de [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) para implementarla en el clúster.</span><span class="sxs-lookup"><span data-stu-id="4f715-119">Select a [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp release to be deployed on your cluster.</span></span>

   <span data-ttu-id="4f715-120">Por ejemplo, si quiere que `.NET for Apache Spark v0.1.0` use `netcoreapp2.1`, tendría que descargar [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span><span class="sxs-lookup"><span data-stu-id="4f715-120">For example, if you want `.NET for Apache Spark v0.1.0` using `netcoreapp2.1`, you'd download [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span></span>

2. <span data-ttu-id="4f715-121">Cargue `Microsoft.Spark.Worker.<release>.tar.gz` e [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) en un sistema de archivos distribuido (por ejemplo, HDFS, WASB, ADLS) al que el clúster tenga acceso.</span><span class="sxs-lookup"><span data-stu-id="4f715-121">Upload `Microsoft.Spark.Worker.<release>.tar.gz` and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to a distributed file system (e.g., HDFS, WASB, ADLS) that your cluster has access to.</span></span>

## <a name="prepare-your-net-for-apache-spark-app"></a><span data-ttu-id="4f715-122">Preparación de la aplicación de .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="4f715-122">Prepare your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="4f715-123">Siga el tutorial de [introducción](get-started.md) para crear la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4f715-123">Follow the [Get Started](get-started.md) tutorial to build your app.</span></span>

2. <span data-ttu-id="4f715-124">Publique la aplicación de .NET para Spark como independiente.</span><span class="sxs-lookup"><span data-stu-id="4f715-124">Publish your Spark .NET app as self-contained.</span></span>

   <span data-ttu-id="4f715-125">Puede ejecutar el siguiente comando en Linux.</span><span class="sxs-lookup"><span data-stu-id="4f715-125">You can run the following command on Linux.</span></span>

   ```bash
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. <span data-ttu-id="4f715-126">Genere `<your app>.zip` para los archivos publicados.</span><span class="sxs-lookup"><span data-stu-id="4f715-126">Produce `<your app>.zip` for the published files.</span></span>

   <span data-ttu-id="4f715-127">Puede ejecutar el siguiente comando en Linux usando `zip`.</span><span class="sxs-lookup"><span data-stu-id="4f715-127">You can run the following command on Linux using `zip`.</span></span>

   ```bash
   zip -r <your app>.zip .
   ```

4. <span data-ttu-id="4f715-128">Cargue lo siguiente en un sistema de archivos distribuido (por ejemplo, HDFS, WASB, ADLS) al que el clúster tenga acceso:</span><span class="sxs-lookup"><span data-stu-id="4f715-128">Upload the following to a distributed file system (e.g., HDFS, WASB, ADLS) that your cluster has access to:</span></span>

   * <span data-ttu-id="4f715-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: Este archivo jar se incluye como parte del paquete NuGet [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/), y se encuentra en el directorio de salida de creación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4f715-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: This jar is included as part of the [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet package and is colocated in your app's build output directory.</span></span>
   * `<your app>.zip`
   * <span data-ttu-id="4f715-130">Los archivos (como los archivos de dependencias o los datos comunes accesibles para todos los trabajos) o los ensamblados (como los archivos DLL que contienen las bibliotecas o las funciones definidas por el usuario de las que `app` depende) se colocarán en el directorio de trabajo de cada ejecutor.</span><span class="sxs-lookup"><span data-stu-id="4f715-130">Files (like dependency files or common data accessible to every worker) or Assemblies (like DLLs that contain your user-defined functions or libraries that your `app` depends on) to be placed in the working directory of each executor.</span></span>

## <a name="deploy-to-azure-hdinsight-spark"></a><span data-ttu-id="4f715-131">Implementar en Azure HDInsight Spark</span><span class="sxs-lookup"><span data-stu-id="4f715-131">Deploy to Azure HDInsight Spark</span></span>

<span data-ttu-id="4f715-132">[Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-overview) es la implementación de Microsoft de Apache Spark en la nube que permite a los usuarios iniciar y configurar clústeres de Spark en Azure.</span><span class="sxs-lookup"><span data-stu-id="4f715-132">[Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-overview) is the Microsoft implementation of Apache Spark in the cloud that allows users to launch and configure Spark clusters in Azure.</span></span> <span data-ttu-id="4f715-133">Puede usar clústeres de HDInsight Spark para procesar los datos almacenados en [Azure Storage](https://azure.microsoft.com/services/storage/) o [Azure Data Lake Storage](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-use-data-lake-storage-gen2).</span><span class="sxs-lookup"><span data-stu-id="4f715-133">You can use HDInsight Spark clusters to process your data stored in [Azure Storage](https://azure.microsoft.com/services/storage/) or [Azure Data Lake Storage](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-use-data-lake-storage-gen2).</span></span>

> [!NOTE]
> <span data-ttu-id="4f715-134">Azure HDInsight Spark se basa en Linux.</span><span class="sxs-lookup"><span data-stu-id="4f715-134">Azure HDInsight Spark is Linux-based.</span></span> <span data-ttu-id="4f715-135">Si está interesado en implementar la aplicación en Azure HDInsight Spark, asegúrese de que la aplicación es compatible con .NET Standard y, asimismo, de que usa el [compilador de .NET Core](https://dotnet.microsoft.com/download) para compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4f715-135">If you are interested in deploying your app to Azure HDInsight Spark, make sure your app is .NET Standard compatible and that you use the [.NET Core compiler](https://dotnet.microsoft.com/download) to compile your app.</span></span>

### <a name="deploy-microsoftsparkworker"></a><span data-ttu-id="4f715-136">Implementación de Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="4f715-136">Deploy Microsoft.Spark.Worker</span></span>

<span data-ttu-id="4f715-137">Este paso solo es necesario realizarlo una vez en su clúster.</span><span class="sxs-lookup"><span data-stu-id="4f715-137">This step is only required once for your cluster.</span></span>

<span data-ttu-id="4f715-138">Ejecute `install-worker.sh` en el clúster con las [acciones de script de HDInsight](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux).</span><span class="sxs-lookup"><span data-stu-id="4f715-138">Run `install-worker.sh` on the cluster using [HDInsight Script Actions](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux).</span></span>

|<span data-ttu-id="4f715-139">Parámetro</span><span class="sxs-lookup"><span data-stu-id="4f715-139">Setting</span></span>|<span data-ttu-id="4f715-140">Valor</span><span class="sxs-lookup"><span data-stu-id="4f715-140">Value</span></span>|
|-------|-----|
|<span data-ttu-id="4f715-141">Tipo de script</span><span class="sxs-lookup"><span data-stu-id="4f715-141">Script type</span></span>|<span data-ttu-id="4f715-142">Personalizados</span><span class="sxs-lookup"><span data-stu-id="4f715-142">Custom</span></span>|
|<span data-ttu-id="4f715-143">nombre</span><span class="sxs-lookup"><span data-stu-id="4f715-143">Name</span></span>|<span data-ttu-id="4f715-144">Instalar Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="4f715-144">Install Microsoft.Spark.Worker</span></span>|
|<span data-ttu-id="4f715-145">URI de script de Bash</span><span class="sxs-lookup"><span data-stu-id="4f715-145">Bash script URI</span></span>|<span data-ttu-id="4f715-146">El URI en el que cargó `install-worker.sh`.</span><span class="sxs-lookup"><span data-stu-id="4f715-146">The URI to which you uploaded `install-worker.sh`.</span></span> <span data-ttu-id="4f715-147">Por ejemplo, `abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/install-worker.sh`.</span><span class="sxs-lookup"><span data-stu-id="4f715-147">For example, `abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/install-worker.sh`</span></span>|
|<span data-ttu-id="4f715-148">Tipos de nodo</span><span class="sxs-lookup"><span data-stu-id="4f715-148">Node type(s)</span></span>|<span data-ttu-id="4f715-149">Trabajo</span><span class="sxs-lookup"><span data-stu-id="4f715-149">Worker</span></span>|
|<span data-ttu-id="4f715-150">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4f715-150">Parameters</span></span>|<span data-ttu-id="4f715-151">Parámetros en `install-worker.sh`.</span><span class="sxs-lookup"><span data-stu-id="4f715-151">Parameters to `install-worker.sh`.</span></span> <span data-ttu-id="4f715-152">Por ejemplo, si cargó `install-worker.sh` en Azure Data Lake Gen 2, sería `azure abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz /usr/local/bin`.</span><span class="sxs-lookup"><span data-stu-id="4f715-152">For example, if you uploaded `install-worker.sh` to Azure Data Lake Gen 2 then it would be `azure abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz /usr/local/bin`.</span></span>|

![Imagen de acción de script](./media/hdinsight-deployment/deployment-hdi-action-script.png)

## <a name="run-your-app"></a><span data-ttu-id="4f715-154">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="4f715-154">Run your app</span></span>

<span data-ttu-id="4f715-155">Puede enviar su trabajo a Azure HDInsight mediante `spark-submit` o Apache Livy.</span><span class="sxs-lookup"><span data-stu-id="4f715-155">You can submit your job to Azure HDInsight using `spark-submit` or Apache Livy.</span></span>

### <a name="use-spark-submit"></a><span data-ttu-id="4f715-156">Uso de spark-submit</span><span class="sxs-lookup"><span data-stu-id="4f715-156">Use spark-submit</span></span>

<span data-ttu-id="4f715-157">Puede usar el comando [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) para enviar trabajos de .NET para Apache Spark a Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="4f715-157">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Azure HDInsight.</span></span>
 
1. <span data-ttu-id="4f715-158">`ssh` en uno de los nodos principales del clúster.</span><span class="sxs-lookup"><span data-stu-id="4f715-158">`ssh` into one of the head nodes in your cluster.</span></span>

1. <span data-ttu-id="4f715-159">Ejecute `spark-submit`:</span><span class="sxs-lookup"><span data-stu-id="4f715-159">Run `spark-submit`:</span></span>

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar \
   abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip <your app> <app arg 1> <app arg 2> ... <app arg n>
   ```

### <a name="use-apache-livy"></a><span data-ttu-id="4f715-160">Usar Apache Livy</span><span class="sxs-lookup"><span data-stu-id="4f715-160">Use Apache Livy</span></span>

<span data-ttu-id="4f715-161">Puede usar [Apache Livy](https://livy.incubator.apache.org/), la API de REST de Apache Spark, para enviar .NET para trabajos de Apache Spark a un clúster Azure HDInsight Spark.</span><span class="sxs-lookup"><span data-stu-id="4f715-161">You can use [Apache Livy](https://livy.incubator.apache.org/), the Apache Spark REST API, to submit .NET for Apache Spark jobs to an Azure HDInsight Spark cluster.</span></span> <span data-ttu-id="4f715-162">Para más información, vea [Trabajos remotos con Apache Livy](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface).</span><span class="sxs-lookup"><span data-stu-id="4f715-162">For more information, see [Remote jobs with Apache Livy](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface).</span></span>

<span data-ttu-id="4f715-163">Puede ejecutar el siguiente comando en Linux usando `curl`:</span><span class="sxs-lookup"><span data-stu-id="4f715-163">You can run the following command on Linux using `curl`:</span></span>

```bash
curl -k -v -X POST "https://<your spark cluster>.azurehdinsight.net/livy/batches" \
-u "<hdinsight username>:<hdinsight password>" \
-H "Content-Type: application/json" \
-H "X-Requested-By: <hdinsight username>" \
-d @- << EOF
{
    "file":"abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar",
    "className":"org.apache.spark.deploy.dotnet.DotnetRunner",
    "files":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<udf assembly>", "abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<file>"],
    "args":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip","<your app>","<app arg 1>","<app arg 2>,"...","<app arg n>"]
}
EOF
```

## <a name="next-steps"></a><span data-ttu-id="4f715-164">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="4f715-164">Next steps</span></span>

<span data-ttu-id="4f715-165">En este tutorial ha implementado una aplicación de .NET para Apache Spark en Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="4f715-165">In this tutorial, you deployed your .NET for Apache Spark application to Azure HDInsight.</span></span> <span data-ttu-id="4f715-166">Para más información sobre HDInsight, continúe con la documentación de Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="4f715-166">To learn more about HDInsight, continue to the Azure HDInsight Documentation.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4f715-167">Documentación de HDInsight de Azure</span><span class="sxs-lookup"><span data-stu-id="4f715-167">Azure HDInsight Documentation</span></span>](https://docs.microsoft.com/azure/hdinsight/)
