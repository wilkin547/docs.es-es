---
title: Implementación de .NET para la aplicación Apache Spark en Amazon EMR Spark
description: Descubra cómo implementar .NET para Apache Spark aplicación en Amazon EMR Spark.
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 5414bc20de3bb90a5d2144bd006d1b859e184a39
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2019
ms.locfileid: "69576932"
---
# <a name="deploy-a-net-for-apache-spark-application-to-amazon-emr-spark"></a>Implementación de .NET para la aplicación Apache Spark en Amazon EMR Spark

En este tutorial se enseña a implementar .NET para Apache Spark aplicación en Amazon EMR Spark.

En este tutorial, aprenderá a:

> [!div class="checklist"]
> * Preparar Microsoft. Spark. Worker
> * Publicación de la aplicación .NET de Spark
> * Implementación de la aplicación en Amazon EMR Spark
> * Ejecutar la aplicación

## <a name="prerequisites"></a>Requisitos previos

Antes de empezar, haga lo siguiente:

* Descargue la [CLI de AWS](https://aws.amazon.com/cli/).
* Descargue [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) en el equipo local. Este es un script de aplicación auxiliar que se usa más adelante para copiar .NET para Apache Spark archivos dependientes en los nodos de trabajo del clúster de Spark.

## <a name="prepare-worker-dependencies"></a>Preparación de las dependencias de trabajo

**Microsoft. Spark. Worker** es un componente de back-end que reside en los nodos de trabajo individuales del clúster de Spark. Cuando desee ejecutar una C# función definida por el usuario (UDF), Spark debe saber cómo iniciar .net CLR para ejecutar la UDF. **Microsoft. Spark. Worker** proporciona una colección de clases para Spark que habilitan esta funcionalidad.

1. Seleccione una versión de [Microsoft. Spark. Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp para implementarla en el clúster.

   Por ejemplo, si quiere `.NET for Apache Spark v0.1.0` usar `netcoreapp2.1`, descargó [Microsoft. Spark. worker. netcoreapp 2.1. Linux-x64-0.1.0. tar. gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).

2. Cargue `Microsoft.Spark.Worker.<release>.tar.gz` y [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) en un sistema de archivos distribuido (por ejemplo, S3) al que tenga acceso el clúster.

## <a name="prepare-your-net-for-apache-spark-app"></a>Preparación de .NET para la aplicación Apache Spark

1. Siga el tutorial de [Introducción](get-started.md) para compilar la aplicación.

2. Publique la aplicación .NET de Spark como independiente.

   Ejecute el siguiente comando en Linux.

   ```bash
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. Producir `<your app>.zip` para los archivos publicados.

   Ejecute el siguiente comando en Linux con `zip`.

   ```bash
   zip -r <your app>.zip .
   ```

4. Cargue los siguientes elementos en un sistema de archivos distribuido (por ejemplo, S3) al que el clúster tenga acceso:

   * `microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: Este archivo jar se incluye como parte del paquete NuGet [Microsoft. Spark](https://www.nuget.org/packages/Microsoft.Spark/) y se encuentra en el directorio de salida de la compilación de la aplicación.
   * `<your app>.zip`
   * Los archivos (como los archivos de dependencia o los datos comunes accesibles para cada trabajo) o los ensamblados (como los archivos DLL que contienen las funciones definidas por el usuario o las bibliotecas de las que depende la aplicación) se colocarán en el directorio de trabajo de cada ejecutor.

## <a name="deploy-to-amazon-emr-spark"></a>Implementación en Amazon EMR Spark

[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) es una plataforma de clústeres administrada que simplifica la ejecución de los marcos de Big Data en AWS.

> [!NOTE] 
> Amazon EMR Spark está basado en Linux. Por lo tanto, si está interesado en implementar la aplicación en Amazon EMR Spark, asegúrese de que la aplicación es .NET Standard compatible y de que usa el compilador de [.net Core](https://dotnet.microsoft.com/download) para compilar la aplicación.

### <a name="deploy-microsoftsparkworker"></a>Implementación de Microsoft. Spark. Worker

Este paso solo es necesario en la creación del clúster.

Ejecute `install-worker.sh` durante la creación del clúster mediante [acciones de bootstrap](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-bootstrap.html).

Ejecute el siguiente comando en Linux con la CLI de AWS.

```bash
aws emr create-cluster \
--name "Test cluster" \
--release-label emr-5.23.0 \
--use-default-roles \
--ec2-attributes KeyName=myKey \
--applications Name=Spark \
--instance-count 3 \
--instance-type m1.medium \
--bootstrap-actions Path=s3://mybucket/<some dir>/install-worker.sh,Name="Install Microsoft.Spark.Worker",Args=["aws","s3://mybucket/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz","/usr/local/bin"]
```

## <a name="run-your-app"></a>Ejecutar la aplicación

Hay dos maneras de ejecutar la aplicación en los pasos de Amazon EMR Spark: Spark-Submit y Amazon EMR.

### <a name="use-spark-submit"></a>Uso de Spark-Submit

Puede usar el comando [Spark-Submit](https://spark.apache.org/docs/latest/submitting-applications.html) para enviar .net para trabajos Apache Spark a Amazon EMR Spark.

1. `ssh`en uno de los nodos del clúster.

2. Ejecute `spark-submit`.

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar \
   s3://mybucket/<some dir>/<your app>.zip <your app> <app args>
   ```

### <a name="use-amazon-emr-steps"></a>Usar los pasos de Amazon EMR

[Los pasos de Amazon EMR](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-spark-submit-step.html) se pueden usar para enviar trabajos al marco de Spark instalado en el clúster de EMR.

Ejecute el siguiente comando en Linux con la CLI de AWS.

```bash
aws emr add-steps \
--cluster-id j-xxxxxxxxxxxxx \
--steps Type=spark,Name="Spark Program",Args=[--master,yarn,--files,s3://mybucket/<some dir>/<udf assembly>,--class,org.apache.spark.deploy.DotnetRunner,s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar,s3://mybucket/<some dir>/<your app>.zip,<your app>,<app arg 1>,<app arg 2>,...,<app arg n>],ActionOnFailure=CONTINUE
```

## <a name="next-steps"></a>Pasos siguientes

En este tutorial, ha implementado .NET para Apache Spark aplicación en Amazon EMR Spark. Para .NET para Apache Spark proyectos de ejemplo, continúe en GitHub.

> [!div class="nextstepaction"]
> [Ejemplos de .NET para Apache Spark](https://github.com/dotnet/spark/tree/master/examples)
