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
# <a name="deploy-a-net-for-apache-spark-application-to-azure-hdinsight"></a>Implementación de .NET para la aplicación Apache Spark en Azure HDInsight

En este tutorial se enseña a implementar .NET para Apache Spark aplicación en Azure HDInsight.

En este tutorial, aprenderá a:

> [!div class="checklist"]
> * Preparar Microsoft. Spark. Worker
> * Publicación de la aplicación .NET de Spark
> * Implementación de la aplicación en Azure HDInsight
> * Ejecutar la aplicación

## <a name="prerequisites"></a>Requisitos previos

Antes de empezar, haga lo siguiente:

* Descargue [Explorador de Azure Storage](https://azure.microsoft.com/features/storage-explorer/).
* Descargue [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) en el equipo local. Este es un script de aplicación auxiliar que se usa más adelante para copiar .NET para Apache Spark archivos dependientes en los nodos de trabajo del clúster de Spark.

## <a name="prepare-worker-dependencies"></a>Preparación de las dependencias de trabajo

**Microsoft. Spark. Worker** es un componente de back-end que reside en los nodos de trabajo individuales del clúster de Spark. Cuando desee ejecutar una C# función definida por el usuario (UDF), Spark debe saber cómo iniciar .net CLR para ejecutar la UDF. **Microsoft. Spark. Worker** proporciona una colección de clases para Spark que habilitan esta funcionalidad.

1. Seleccione una versión de [Microsoft. Spark. Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp para implementarla en el clúster.

   Por ejemplo, si quiere `.NET for Apache Spark v0.1.0` usar `netcoreapp2.1`, descargó [Microsoft. Spark. worker. netcoreapp 2.1. Linux-x64-0.1.0. tar. gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).

2. Cargue `Microsoft.Spark.Worker.<release>.tar.gz` y [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) en un sistema de archivos distribuido (por ejemplo, HDFS, WASB, ADLS) al que tiene acceso el clúster.

## <a name="prepare-your-net-for-apache-spark-app"></a>Preparación de .NET para la aplicación Apache Spark

1. Siga el tutorial de [Introducción](get-started.md) para compilar la aplicación.

2. Publique la aplicación .NET de Spark como independiente.

   Puede ejecutar el siguiente comando en Linux.

   ```bash
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. Producir `<your app>.zip` para los archivos publicados.

   Puede ejecutar el siguiente comando en Linux con `zip`.

   ```bash
   zip -r <your app>.zip .
   ```

4. Cargue lo siguiente en un sistema de archivos distribuido (por ejemplo, HDFS, WASB, ADLS) al que el clúster tiene acceso:

   * `microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: Este archivo jar se incluye como parte del paquete NuGet [Microsoft. Spark](https://www.nuget.org/packages/Microsoft.Spark/) y se encuentra en el directorio de salida de la compilación de la aplicación.
   * `<your app>.zip`
   * Los archivos (como los archivos de dependencia o los datos comunes accesibles para cada trabajo) o los ensamblados (como los archivos DLL que contienen las `app` funciones definidas por el usuario o las bibliotecas de las que depende) se colocan en el directorio de trabajo de cada ejecutor.

## <a name="deploy-to-azure-hdinsight-spark"></a>Implementar en Azure HDInsight Spark

[Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-overview) es la implementación de Microsoft de Apache Spark en la nube que permite a los usuarios iniciar y configurar clústeres de Spark en Azure. Puede usar los clústeres de HDInsight Spark para procesar los datos almacenados en [Azure Storage](https://azure.microsoft.com/services/storage/) o [Azure Data Lake Storage](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-use-data-lake-storage-gen2).

> [!NOTE]
> Azure HDInsight Spark está basado en Linux. Si está interesado en implementar la aplicación en Azure HDInsight Spark, asegúrese de que la aplicación .NET Standard sea compatible y de que use el compilador de [.net Core](https://dotnet.microsoft.com/download) para compilar la aplicación.

### <a name="deploy-microsoftsparkworker"></a>Implementación de Microsoft. Spark. Worker

Este paso solo es necesario para el clúster.

Ejecute `install-worker.sh` en el clúster con [las acciones de script de HDInsight](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux).

|Parámetro|Value|
|-------|-----|
|Tipo de script|Personalizados|
|NOMBRE|Instalación de Microsoft. Spark. Worker|
|URI de script de Bash|El URI en el que cargó `install-worker.sh`. Por ejemplo, `abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/install-worker.sh`|
|Tipos de nodo|Trabajo|
|Parámetros|Parámetros para `install-worker.sh`. Por ejemplo, si cargó `install-worker.sh` en Azure Data Lake Gen 2, `azure abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz /usr/local/bin`sería.|

![Imagen de acción de script](./media/hdinsight-deployment/deployment-hdi-action-script.png)

## <a name="run-your-app"></a>Ejecutar la aplicación

Puede enviar su trabajo a HDInsight de Azure mediante `spark-submit` o Apache Livy.

### <a name="use-spark-submit"></a>Uso de Spark-Submit

Puede usar el comando [Spark-Submit](https://spark.apache.org/docs/latest/submitting-applications.html) para enviar .net para trabajos Apache Spark a Azure HDInsight.
 
1. `ssh`en uno de los nodos principales del clúster.

1. Ejecutar `spark-submit`:

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar \
   abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip <your app> <app arg 1> <app arg 2> ... <app arg n>
   ```

### <a name="use-apache-livy"></a>Uso de Apache Livy

Puede usar [Apache Livy](https://livy.incubator.apache.org/), la API de REST Apache Spark, para enviar .net para trabajos de Apache Spark a un clúster de Azure HDInsight Spark. Para obtener más información, vea [trabajos remotos con Apache Livy](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface).

Puede ejecutar el siguiente comando en Linux con `curl`:

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

## <a name="next-steps"></a>Pasos siguientes

En este tutorial, ha implementado .NET para Apache Spark aplicación en Azure HDInsight. Para más información sobre HDInsight, continúe con la documentación de HDInsight de Azure.

> [!div class="nextstepaction"]
> [Documentación de HDInsight de Azure](https://docs.microsoft.com/azure/hdinsight/)
