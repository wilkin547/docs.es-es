---
title: Envío de un trabajo de .NET para Apache Spark a Azure HDInsight
description: Aprenda a enviar un trabajo de .NET para Apache Spark a Azure HDInsight mediante spark-submit y Apache Livy.
ms.date: 11/19/2019
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 83359f7f613b500a4ce121ce1612cda0ad1191ab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "79185798"
---
# <a name="submit-a-net-for-apache-spark-job-to-azure-hdinsight"></a><span data-ttu-id="fb943-103">Envío de un trabajo de .NET para Apache Spark a Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="fb943-103">Submit a .NET for Apache Spark job to Azure HDInsight</span></span>

<span data-ttu-id="fb943-104">Hay dos maneras de implementar el trabajo de .NET para Apache Spark en HDInsight: `spark-submit` y Apache Livy.</span><span class="sxs-lookup"><span data-stu-id="fb943-104">There are two ways to deploy your .NET for Apache Spark job to HDInsight: `spark-submit` and Apache Livy.</span></span>

## <a name="deploy-using-spark-submit"></a><span data-ttu-id="fb943-105">Implementación mediante spark-submit</span><span class="sxs-lookup"><span data-stu-id="fb943-105">Deploy using spark-submit</span></span>

<span data-ttu-id="fb943-106">Puede usar el comando [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) para enviar trabajos de .NET para Apache Spark a Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="fb943-106">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Azure HDInsight.</span></span>

1. <span data-ttu-id="fb943-107">Vaya al clúster de HDInsight de Spark en Azure Portal y luego seleccione **SSH e inicio de sesión del clúster**.</span><span class="sxs-lookup"><span data-stu-id="fb943-107">Navigate to your HDInsight Spark cluster in Azure portal, and then select **SSH + Cluster login**.</span></span>

2. <span data-ttu-id="fb943-108">Copie la información de inicio de sesión de SSH y pegue el inicio de sesión en un terminal.</span><span class="sxs-lookup"><span data-stu-id="fb943-108">Copy the ssh login information and paste the login into a terminal.</span></span> <span data-ttu-id="fb943-109">Inicie sesión en el clúster con la contraseña que se ha establecido durante la creación del clúster.</span><span class="sxs-lookup"><span data-stu-id="fb943-109">Sign in to your cluster using the password you set during cluster creation.</span></span> <span data-ttu-id="fb943-110">Debería ver mensajes de bienvenida a Ubuntu y Spark.</span><span class="sxs-lookup"><span data-stu-id="fb943-110">You should see messages welcoming you to Ubuntu and Spark.</span></span>

3. <span data-ttu-id="fb943-111">Use el comando **spark-submit** para ejecutar la aplicación en el clúster de HDInsight.</span><span class="sxs-lookup"><span data-stu-id="fb943-111">Use the **spark-submit** command to run your app on your HDInsight cluster.</span></span> <span data-ttu-id="fb943-112">Recuerde reemplazar **mycontainer** y **mystorageaccount** en el script de ejemplo con los nombres reales del contenedor de blobs y la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="fb943-112">Remember to replace **mycontainer** and **mystorageaccount** in the example script with the actual names of your blob container and storage account.</span></span> <span data-ttu-id="fb943-113">Además, asegúrese de reemplazar `microsoft-spark-2.3.x-0.6.0.jar` por el archivo .jar adecuado que esté usando para la implementación.</span><span class="sxs-lookup"><span data-stu-id="fb943-113">Also, be sure to replace `microsoft-spark-2.3.x-0.6.0.jar` with the appropriate jar file you're using for deployment.</span></span> <span data-ttu-id="fb943-114">`2.3.x` representa la versión de Apache Spark, y `0.6.0`, la del [trabajo de .NET para Apache Spark](https://github.com/dotnet/spark/releases).</span><span class="sxs-lookup"><span data-stu-id="fb943-114">`2.3.x` represents the version of Apache Spark, and `0.6.0` represents the version of the [.NET for Apache Spark worker](https://github.com/dotnet/spark/releases).</span></span>

   ```bash
   $SPARK_HOME/bin/spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/microsoft-spark-2.3.x-0.6.0.jar \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/publish.zip mySparkApp
   ```

## <a name="deploy-using-apache-livy"></a><span data-ttu-id="fb943-115">Implementación mediante Apache Livy</span><span class="sxs-lookup"><span data-stu-id="fb943-115">Deploy using Apache Livy</span></span>

<span data-ttu-id="fb943-116">Puede usar [Apache Livy](https://livy.incubator.apache.org/), la API de REST de Apache Spark, para enviar .NET para trabajos de Apache Spark a un clúster Azure HDInsight Spark.</span><span class="sxs-lookup"><span data-stu-id="fb943-116">You can use [Apache Livy](https://livy.incubator.apache.org/), the Apache Spark REST API, to submit .NET for Apache Spark jobs to an Azure HDInsight Spark cluster.</span></span> <span data-ttu-id="fb943-117">Para más información, vea [Trabajos remotos con Apache Livy](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface).</span><span class="sxs-lookup"><span data-stu-id="fb943-117">For more information, see [Remote jobs with Apache Livy](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface).</span></span>

<span data-ttu-id="fb943-118">Puede ejecutar el siguiente comando en Linux usando `curl`:</span><span class="sxs-lookup"><span data-stu-id="fb943-118">You can run the following command on Linux using `curl`:</span></span>

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

## <a name="next-steps"></a><span data-ttu-id="fb943-119">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="fb943-119">Next steps</span></span>

* [<span data-ttu-id="fb943-120">Introducción a .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="fb943-120">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
* [<span data-ttu-id="fb943-121">Implementación de una aplicación de .NET para Apache Spark en Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="fb943-121">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>](../tutorials/hdinsight-deployment.md)
* [<span data-ttu-id="fb943-122">Documentación de HDInsight</span><span class="sxs-lookup"><span data-stu-id="fb943-122">HDInsight Documentation</span></span>](https://docs.microsoft.com/azure/hdinsight/)
