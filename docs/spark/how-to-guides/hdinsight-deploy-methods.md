---
title: Envío de un trabajo de .NET para Apache Spark a Azure HDInsight
description: Aprenda a enviar un trabajo de .NET para Apache Spark a Azure HDInsight mediante spark-submit y Apache Livy.
ms.date: 11/19/2019
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: d558234a53cc22d65540a380ac7f5b3ac03ba0ae
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868023"
---
# <a name="submit-a-net-for-apache-spark-job-to-azure-hdinsight"></a>Envío de un trabajo de .NET para Apache Spark a Azure HDInsight

Hay dos maneras de implementar el trabajo de .NET para Apache Spark en HDInsight: `spark-submit` y Apache Livy.

## <a name="deploy-using-spark-submit"></a>Implementación mediante spark-submit

Puede usar el comando [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) para enviar trabajos de .NET para Apache Spark a Azure HDInsight.
 
1. Vaya al clúster de HDInsight de Spark en Azure Portal y luego seleccione **SSH e inicio de sesión del clúster**.

2. Copie la información de inicio de sesión de SSH y pegue el inicio de sesión en un terminal. Inicie sesión en el clúster con la contraseña que se ha establecido durante la creación del clúster. Debería ver mensajes de bienvenida a Ubuntu y Spark.

3. Use el comando **spark-submit** para ejecutar la aplicación en el clúster de HDInsight. Recuerde reemplazar **mycontainer** y **mystorageaccount** en el script de ejemplo con los nombres reales del contenedor de blobs y la cuenta de almacenamiento. Además, asegúrese de reemplazar `microsoft-spark-2.3.x-0.6.0.jar` por el archivo .jar adecuado que esté usando para la implementación. `2.3.x` representa la versión de Apache Spark, y `0.6.0`, la del [trabajo de .NET para Apache Spark](https://github.com/dotnet/spark/releases).

   ```bash
   $SPARK_HOME/bin/spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/microsoft-spark-2.3.x-0.6.0.jar \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/publish.zip mySparkApp
   ```

## <a name="deploy-using-apache-livy"></a>Implementación mediante Apache Livy

Puede usar [Apache Livy](https://livy.incubator.apache.org/), la API de REST de Apache Spark, para enviar .NET para trabajos de Apache Spark a un clúster Azure HDInsight Spark. Para más información, vea [Trabajos remotos con Apache Livy](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface).

Puede ejecutar el siguiente comando en Linux usando `curl`:

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

## <a name="next-steps"></a>Pasos siguientes

* [Introducción a .NET para Apache Spark](../tutorials/get-started.md)
* [Implementación de una aplicación de .NET para Apache Spark en Azure HDInsight](../tutorials/hdinsight-deployment.md)
* [Documentación de HDInsight](https://docs.microsoft.com/azure/hdinsight/)
