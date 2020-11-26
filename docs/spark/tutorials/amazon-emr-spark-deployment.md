---
title: Implementación de una aplicación de .NET para Apache Spark en Amazon EMR Spark
description: Sepa cómo implementar una aplicación de .NET para Apache Spark en Amazon EMR Spark.
ms.date: 10/09/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: dd1cfdf12266b55d9dbc0210479b89ba68c59a38
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688077"
---
# <a name="deploy-a-net-for-apache-spark-application-to-amazon-emr-spark"></a>Implementación de una aplicación de .NET para Apache Spark en Amazon EMR Spark

En este tutorial aprenderá a implementar una aplicación de .NET para Apache Spark en Amazon EMR Spark. [Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) es una plataforma de clúster administrada que simplifica la ejecución de marcos de macrodatos en AWS.

En este tutorial, aprenderá a:

> [!div class="checklist"]
>
> * Preparar Microsoft.Spark.Worker
> * Publicar la aplicación de .NET para Spark
> * Implementar la aplicación en Amazon EMR Spark
> * Ejecutar la aplicación

> [!Note]
> AWS EMR Spark se basa en Linux. Por tanto, si está interesado en implementar la aplicación en AWS EMR Spark, asegúrese de que es compatible con .NET Standard y de que usa el compilador de .NET Core para compilarla.

## <a name="prerequisites"></a>Prerrequisitos

Antes de empezar, haga lo siguiente:

* Descargue la [CLI de AWS](https://aws.amazon.com/cli/).
* Descargue [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) en el equipo local. Es un script de aplicación auxiliar que usaremos más adelante para copiar archivos dependientes de .NET para Apache Spark en los nodos de trabajo del clúster de Spark.

## <a name="prepare-worker-dependencies"></a>Preparación de las dependencias de trabajo

**Microsoft.Spark.Worker** es un componente back-end que reside en los nodos de trabajo individuales del clúster de Spark. Si quiere ejecutar una función definida por el usuario (UDF) de C#, Spark necesita saber cómo iniciar el CLR de .NET para ejecutarla. **Microsoft.Spark.Worker** pone a disposición de Spark una colección de clases que habilitan esta funcionalidad.

1. Seleccione una versión netcoreapp de Linux de [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) para implementarla en el clúster.

   Por ejemplo, si quiere `.NET for Apache Spark v1.0.0` con `netcoreapp3.1`, tendría que descargar [Microsoft.Spark.Worker.netcoreapp3.1.linux-x64-1.0.0.tar.gz](https://github.com/dotnet/spark/releases/download/v1.0.0/Microsoft.Spark.Worker.netcoreapp3.1.linux-x64-1.0.0.tar.gz).

2. Cargue `Microsoft.Spark.Worker.<release>.tar.gz` e [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) en un sistema de archivos distribuido (por ejemplo, S3) al que el clúster tenga acceso.

## <a name="prepare-your-net-for-apache-spark-app"></a>Preparación de la aplicación de .NET para Apache Spark

1. Siga el tutorial de [introducción](get-started.md) para crear la aplicación.

2. Publique la aplicación de .NET para Spark como independiente.

   Ejecute el siguiente comando en Linux.

   ```dotnetcli
   dotnet publish -c Release -f netcoreapp3.1 -r ubuntu.16.04-x64
   ```

3. Genere `<your app>.zip` para los archivos publicados.

   Ejecute el siguiente comando en Linux usando `zip`.

   ```bash
   zip -r <your app>.zip .
   ```

4. Cargue los siguientes elementos en un sistema de archivos distribuido (por ejemplo, S3) al que el clúster tenga acceso:

   * `microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar`: Este archivo jar se incluye como parte del paquete NuGet [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/), y se encuentra en el directorio de salida de creación de la aplicación.
   * `<your app>.zip`
   * Los archivos (como los archivos de dependencias o los datos comunes accesibles para todos los trabajos) o los ensamblados (como los archivos DLL que contienen las bibliotecas o las funciones definidas por el usuario de las que depende la aplicación) se colocarán en el directorio de trabajo de cada ejecutor.

## <a name="deploy-to-amazon-emr-spark"></a>Implementación en Amazon EMR Spark

[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) es una plataforma de clúster administrada que simplifica la ejecución de marcos de macrodatos en AWS.

> [!NOTE]
> Amazon EMR Spark se basa en Linux. Por lo tanto, si está interesado en implementar la aplicación en Amazon EMR Spark, asegúrese de que la aplicación es compatible con .NET Standard y, asimismo, de que usa el [compilador de .NET Core](https://dotnet.microsoft.com/download) para compilar la aplicación.

### <a name="deploy-microsoftsparkworker"></a>Implementación de Microsoft.Spark.Worker

Este paso solo es necesario realizarlo al crear un clúster.

Ejecute `install-worker.sh` durante la creación del clúster mediante [acciones de arranque](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-bootstrap.html).

Ejecute el siguiente comando en Linux usando la CLI de AWS.

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

Hay dos maneras de ejecutar la aplicación en Amazon EMR Spark: con spark-submit o con pasos de Amazon EMR.

### <a name="use-spark-submit"></a>Uso de spark-submit

Puede usar el comando [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) para enviar trabajos de .NET para Apache Spark a Amazon EMR Spark.

1. Aplique `ssh` en uno de los nodos del clúster.

2. Ejecute `spark-submit`.

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar \
   s3://mybucket/<some dir>/<your app>.zip <your app> <app args>
   ```

### <a name="use-amazon-emr-steps"></a>Uso de pasos de Amazon EMR

Se pueden usar [pasos de Amazon EMR](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-spark-submit-step.html) para enviar trabajos al marco de Spark instalado en el clúster de EMR.

Ejecute el siguiente comando en Linux usando la CLI de AWS.

```bash
aws emr add-steps \
--cluster-id j-xxxxxxxxxxxxx \
--steps Type=spark,Name="Spark Program",Args=[--master,yarn,--files,s3://mybucket/<some dir>/<udf assembly>,--class,org.apache.spark.deploy.dotnet.DotnetRunner,s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar,s3://mybucket/<some dir>/<your app>.zip,<your app>,<app arg 1>,<app arg 2>,...,<app arg n>],ActionOnFailure=CONTINUE
```

## <a name="next-steps"></a>Pasos siguientes

En este tutorial ha implementado una aplicación de .NET para Apache Spark en Amazon EMR Spark. Para ver proyectos de ejemplo de .NET para Apache Spark, continúe en GitHub.

> [!div class="nextstepaction"]
> [Ejemplos de .NET para Apache Spark](https://github.com/dotnet/spark/tree/master/examples)
