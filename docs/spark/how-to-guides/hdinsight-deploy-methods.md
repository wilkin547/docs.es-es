---
title: Envío de un trabajo de .NET para Apache Spark a Azure HDInsight
description: Aprenda a enviar un trabajo de .NET para Apache Spark a Azure HDInsight mediante spark-submit y Apache Livy.
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 74be4ecf33a9a881633da0630fa1c1a4bf0b19c6
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688168"
---
# <a name="submit-a-net-for-apache-spark-job-to-azure-hdinsight"></a><span data-ttu-id="d7304-103">Envío de un trabajo de .NET para Apache Spark a Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="d7304-103">Submit a .NET for Apache Spark job to Azure HDInsight</span></span>

<span data-ttu-id="d7304-104">Hay dos maneras de implementar el trabajo de .NET para Apache Spark en HDInsight: `spark-submit` y Apache Livy.</span><span class="sxs-lookup"><span data-stu-id="d7304-104">There are two ways to deploy your .NET for Apache Spark job to HDInsight: `spark-submit` and Apache Livy.</span></span>

## <a name="deploy-using-spark-submit"></a><span data-ttu-id="d7304-105">Implementación mediante spark-submit</span><span class="sxs-lookup"><span data-stu-id="d7304-105">Deploy using spark-submit</span></span>

<span data-ttu-id="d7304-106">Puede usar el comando [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) para enviar trabajos de .NET para Apache Spark a Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="d7304-106">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Azure HDInsight.</span></span>

1. <span data-ttu-id="d7304-107">Vaya al clúster de HDInsight de Spark en Azure Portal y luego seleccione **SSH e inicio de sesión del clúster**.</span><span class="sxs-lookup"><span data-stu-id="d7304-107">Navigate to your HDInsight Spark cluster in Azure portal, and then select **SSH + Cluster login**.</span></span>

2. <span data-ttu-id="d7304-108">Copie la información de inicio de sesión de SSH y pegue el inicio de sesión en un terminal.</span><span class="sxs-lookup"><span data-stu-id="d7304-108">Copy the ssh login information and paste the login into a terminal.</span></span> <span data-ttu-id="d7304-109">Inicie sesión en el clúster con la contraseña que se ha establecido durante la creación del clúster.</span><span class="sxs-lookup"><span data-stu-id="d7304-109">Sign in to your cluster using the password you set during cluster creation.</span></span> <span data-ttu-id="d7304-110">Debería ver mensajes de bienvenida a Ubuntu y Spark.</span><span class="sxs-lookup"><span data-stu-id="d7304-110">You should see messages welcoming you to Ubuntu and Spark.</span></span>

3. <span data-ttu-id="d7304-111">Use el comando **spark-submit** para ejecutar la aplicación en el clúster de HDInsight.</span><span class="sxs-lookup"><span data-stu-id="d7304-111">Use the **spark-submit** command to run your app on your HDInsight cluster.</span></span> <span data-ttu-id="d7304-112">Recuerde reemplazar **mycontainer** y **mystorageaccount** en el script de ejemplo con los nombres reales del contenedor de blobs y la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="d7304-112">Remember to replace **mycontainer** and **mystorageaccount** in the example script with the actual names of your blob container and storage account.</span></span> <span data-ttu-id="d7304-113">Recuerde también reemplazar el archivo microsoft-spark jar por la versión de Spark y .NET para Apache Spark que se use.</span><span class="sxs-lookup"><span data-stu-id="d7304-113">Also remember to replace the microsoft-spark jar with the version of Spark and .NET for Apache Spark being used.</span></span>

   ```bash
   $SPARK_HOME/bin/spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/publish.zip mySparkApp
   ```

## <a name="deploy-using-apache-livy"></a><span data-ttu-id="d7304-114">Implementación mediante Apache Livy</span><span class="sxs-lookup"><span data-stu-id="d7304-114">Deploy using Apache Livy</span></span>

<span data-ttu-id="d7304-115">Puede usar [Apache Livy](https://livy.incubator.apache.org/), la API de REST de Apache Spark, para enviar .NET para trabajos de Apache Spark a un clúster Azure HDInsight Spark.</span><span class="sxs-lookup"><span data-stu-id="d7304-115">You can use [Apache Livy](https://livy.incubator.apache.org/), the Apache Spark REST API, to submit .NET for Apache Spark jobs to an Azure HDInsight Spark cluster.</span></span> <span data-ttu-id="d7304-116">Para más información, vea [Trabajos remotos con Apache Livy](/azure/hdinsight/spark/apache-spark-livy-rest-interface).</span><span class="sxs-lookup"><span data-stu-id="d7304-116">For more information, see [Remote jobs with Apache Livy](/azure/hdinsight/spark/apache-spark-livy-rest-interface).</span></span>

<span data-ttu-id="d7304-117">Puede ejecutar el siguiente comando en Linux usando `curl`:</span><span class="sxs-lookup"><span data-stu-id="d7304-117">You can run the following command on Linux using `curl`:</span></span>

```bash
curl -k -v -X POST "https://<your spark cluster>.azurehdinsight.net/livy/batches" \
-u "<hdinsight username>:<hdinsight password>" \
-H "Content-Type: application/json" \
-H "X-Requested-By: <hdinsight username>" \
-d @- << EOF
{
    "file":"abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar",
    "className":"org.apache.spark.deploy.dotnet.DotnetRunner",
    "files":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<udf assembly>", "abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<file>"],
    "args":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip","<your app>","<app arg 1>","<app arg 2>,"...","<app arg n>"]
}
EOF
```

## <a name="next-steps"></a><span data-ttu-id="d7304-118">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="d7304-118">Next steps</span></span>

* [<span data-ttu-id="d7304-119">Introducción a .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="d7304-119">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
* [<span data-ttu-id="d7304-120">Implementación de una aplicación de .NET para Apache Spark en Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="d7304-120">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>](../tutorials/hdinsight-deployment.md)
* [<span data-ttu-id="d7304-121">Documentación de HDInsight</span><span class="sxs-lookup"><span data-stu-id="d7304-121">HDInsight Documentation</span></span>](/azure/hdinsight/)
