---
title: Implementación de una aplicación de .NET para Apache Spark en Azure HDInsight
description: Aprenda a implementar una aplicación de .NET para Apache Spark en HDInsight.
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 9da0e0fd83d70887109c63a5e95ec0b0b31a2edd
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928470"
---
# <a name="deploy-a-net-for-apache-spark-application-to-azure-hdinsight"></a>Implementación de una aplicación de .NET para Apache Spark en Azure HDInsight

En este tutorial aprenderá a implementar una aplicación de .NET para Apache Spark en Azure HDInsight.

En este tutorial aprenderá a:

> [!div class="checklist"]
>
> * Preparar Microsoft.Spark.Worker
> * Publicar la aplicación de .NET para Spark
> * Implementar de una aplicación en Azure HDInsight
> * Ejecutar la aplicación

## <a name="prerequisites"></a>Requisitos previos

Antes de empezar, haga lo siguiente:

* Descargue el [Explorador de Azure Storage](https://azure.microsoft.com/features/storage-explorer/).
* Descargue [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) en el equipo local. Es un script de aplicación auxiliar que usaremos más adelante para copiar archivos dependientes de .NET para Apache Spark en los nodos de trabajo del clúster de Spark.

## <a name="prepare-worker-dependencies"></a>Preparación de las dependencias de trabajo

**Microsoft.Spark.Worker** es un componente back-end que reside en los nodos de trabajo individuales del clúster de Spark. Si quiere ejecutar una función definida por el usuario (UDF) de C#, Spark necesita saber cómo iniciar .NET CLR para ejecutar la UDF. **Microsoft.Spark.Worker** pone a disposición de Spark una colección de clases que habilitan esta funcionalidad.

1. Seleccione una versión netcoreapp de Linux de [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) para implementarla en el clúster.

   Por ejemplo, si quiere que `.NET for Apache Spark v0.1.0` use `netcoreapp2.1`, tendría que descargar [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).

2. Cargue `Microsoft.Spark.Worker.<release>.tar.gz` e [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) en un sistema de archivos distribuido (por ejemplo, HDFS, WASB, ADLS) al que el clúster tenga acceso.

## <a name="prepare-your-net-for-apache-spark-app"></a>Preparación de la aplicación de .NET para Apache Spark

1. Siga el tutorial de [introducción](get-started.md) para crear la aplicación.

2. Publique la aplicación de .NET para Spark como independiente.

   Puede ejecutar el siguiente comando en Linux.

   ```bash
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. Genere `<your app>.zip` para los archivos publicados.

   Puede ejecutar el siguiente comando en Linux usando `zip`.

   ```bash
   zip -r <your app>.zip .
   ```

4. Cargue lo siguiente en un sistema de archivos distribuido (por ejemplo, HDFS, WASB, ADLS) al que el clúster tenga acceso:

   * `microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: Este archivo jar se incluye como parte del paquete NuGet [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/), y se encuentra en el directorio de salida de creación de la aplicación.
   * `<your app>.zip`
   * Los archivos (como los archivos de dependencias o los datos comunes accesibles para todos los trabajos) o los ensamblados (como los archivos DLL que contienen las bibliotecas o las funciones definidas por el usuario de las que `app` depende) se colocarán en el directorio de trabajo de cada ejecutor.

## <a name="deploy-to-azure-hdinsight-spark"></a>Implementar en Azure HDInsight Spark

[Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-overview) es la implementación de Microsoft de Apache Spark en la nube que permite a los usuarios iniciar y configurar clústeres de Spark en Azure. Puede usar clústeres de HDInsight Spark para procesar los datos almacenados en [Azure Storage](https://azure.microsoft.com/services/storage/) o [Azure Data Lake Storage](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-use-data-lake-storage-gen2).

> [!NOTE]
> Azure HDInsight Spark se basa en Linux. Si está interesado en implementar la aplicación en Azure HDInsight Spark, asegúrese de que la aplicación es compatible con .NET Standard y, asimismo, de que usa el [compilador de .NET Core](https://dotnet.microsoft.com/download) para compilar la aplicación.

### <a name="deploy-microsoftsparkworker"></a>Implementación de Microsoft.Spark.Worker

Este paso solo es necesario realizarlo una vez en su clúster.

Ejecute `install-worker.sh` en el clúster con las [acciones de script de HDInsight](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux).

|Parámetro|Valor|
|-------|-----|
|Tipo de script|Personalizados|
|nombre|Instalar Microsoft.Spark.Worker|
|URI de script de Bash|El URI en el que cargó `install-worker.sh`. Por ejemplo, `abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/install-worker.sh`.|
|Tipos de nodo|Trabajo|
|Parámetros|Parámetros en `install-worker.sh`. Por ejemplo, si cargó `install-worker.sh` en Azure Data Lake Gen 2, sería `azure abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz /usr/local/bin`.|

![Imagen de acción de script](./media/hdinsight-deployment/deployment-hdi-action-script.png)

## <a name="run-your-app"></a>Ejecutar la aplicación

Puede enviar su trabajo a Azure HDInsight mediante `spark-submit` o Apache Livy.

### <a name="use-spark-submit"></a>Uso de spark-submit

Puede usar el comando [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) para enviar trabajos de .NET para Apache Spark a Azure HDInsight.
 
1. `ssh` en uno de los nodos principales del clúster.

1. Ejecute `spark-submit`:

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar \
   abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip <your app> <app arg 1> <app arg 2> ... <app arg n>
   ```

### <a name="use-apache-livy"></a>Usar Apache Livy

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

En este tutorial ha implementado una aplicación de .NET para Apache Spark en Azure HDInsight. Para más información sobre HDInsight, continúe con la documentación de Azure HDInsight.

> [!div class="nextstepaction"]
> [Documentación de HDInsight de Azure](https://docs.microsoft.com/azure/hdinsight/)
