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
# <a name="deploy-a-net-for-apache-spark-application-to-amazon-emr-spark"></a><span data-ttu-id="f5cf3-103">Implementación de .NET para la aplicación Apache Spark en Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="f5cf3-103">Deploy a .NET for Apache Spark application to Amazon EMR Spark</span></span>

<span data-ttu-id="f5cf3-104">En este tutorial se enseña a implementar .NET para Apache Spark aplicación en Amazon EMR Spark.</span><span class="sxs-lookup"><span data-stu-id="f5cf3-104">This tutorial teaches how to deploy a .NET for Apache Spark application to Amazon EMR Spark.</span></span>

<span data-ttu-id="f5cf3-105">En este tutorial, aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="f5cf3-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="f5cf3-106">Preparar Microsoft. Spark. Worker</span><span class="sxs-lookup"><span data-stu-id="f5cf3-106">Prepare Microsoft.Spark.Worker</span></span>
> * <span data-ttu-id="f5cf3-107">Publicación de la aplicación .NET de Spark</span><span class="sxs-lookup"><span data-stu-id="f5cf3-107">Publish your Spark .NET app</span></span>
> * <span data-ttu-id="f5cf3-108">Implementación de la aplicación en Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="f5cf3-108">Deploy your app to Amazon EMR Spark</span></span>
> * <span data-ttu-id="f5cf3-109">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="f5cf3-109">Run your app</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f5cf3-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f5cf3-110">Prerequisites</span></span>

<span data-ttu-id="f5cf3-111">Antes de empezar, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f5cf3-111">Before you start, do the following:</span></span>

* <span data-ttu-id="f5cf3-112">Descargue la [CLI de AWS](https://aws.amazon.com/cli/).</span><span class="sxs-lookup"><span data-stu-id="f5cf3-112">Download the [AWS CLI](https://aws.amazon.com/cli/).</span></span>
* <span data-ttu-id="f5cf3-113">Descargue [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="f5cf3-113">Download [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to your local machine.</span></span> <span data-ttu-id="f5cf3-114">Este es un script de aplicación auxiliar que se usa más adelante para copiar .NET para Apache Spark archivos dependientes en los nodos de trabajo del clúster de Spark.</span><span class="sxs-lookup"><span data-stu-id="f5cf3-114">This is a helper script that you use later to copy .NET for Apache Spark dependent files into your Spark cluster's worker nodes.</span></span>

## <a name="prepare-worker-dependencies"></a><span data-ttu-id="f5cf3-115">Preparación de las dependencias de trabajo</span><span class="sxs-lookup"><span data-stu-id="f5cf3-115">Prepare worker dependencies</span></span>

<span data-ttu-id="f5cf3-116">**Microsoft. Spark. Worker** es un componente de back-end que reside en los nodos de trabajo individuales del clúster de Spark.</span><span class="sxs-lookup"><span data-stu-id="f5cf3-116">**Microsoft.Spark.Worker** is a backend component that lives on the individual worker nodes of your Spark cluster.</span></span> <span data-ttu-id="f5cf3-117">Cuando desee ejecutar una C# función definida por el usuario (UDF), Spark debe saber cómo iniciar .net CLR para ejecutar la UDF.</span><span class="sxs-lookup"><span data-stu-id="f5cf3-117">When you want to execute a C# UDF (user-defined function), Spark needs to understand how to launch the .NET CLR to execute the UDF.</span></span> <span data-ttu-id="f5cf3-118">**Microsoft. Spark. Worker** proporciona una colección de clases para Spark que habilitan esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="f5cf3-118">**Microsoft.Spark.Worker** provides a collection of classes to Spark that enable this functionality.</span></span>

1. <span data-ttu-id="f5cf3-119">Seleccione una versión de [Microsoft. Spark. Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp para implementarla en el clúster.</span><span class="sxs-lookup"><span data-stu-id="f5cf3-119">Select a [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp release to be deployed on your cluster.</span></span>

   <span data-ttu-id="f5cf3-120">Por ejemplo, si quiere `.NET for Apache Spark v0.1.0` usar `netcoreapp2.1`, descargó [Microsoft. Spark. worker. netcoreapp 2.1. Linux-x64-0.1.0. tar. gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span><span class="sxs-lookup"><span data-stu-id="f5cf3-120">For example, if you want `.NET for Apache Spark v0.1.0` using `netcoreapp2.1`, you'd download [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span></span>

2. <span data-ttu-id="f5cf3-121">Cargue `Microsoft.Spark.Worker.<release>.tar.gz` y [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) en un sistema de archivos distribuido (por ejemplo, S3) al que tenga acceso el clúster.</span><span class="sxs-lookup"><span data-stu-id="f5cf3-121">Upload `Microsoft.Spark.Worker.<release>.tar.gz` and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to a distributed file system (e.g., S3) that your cluster has access to.</span></span>

## <a name="prepare-your-net-for-apache-spark-app"></a><span data-ttu-id="f5cf3-122">Preparación de .NET para la aplicación Apache Spark</span><span class="sxs-lookup"><span data-stu-id="f5cf3-122">Prepare your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="f5cf3-123">Siga el tutorial de [Introducción](get-started.md) para compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f5cf3-123">Follow the [Get Started](get-started.md) tutorial to build your app.</span></span>

2. <span data-ttu-id="f5cf3-124">Publique la aplicación .NET de Spark como independiente.</span><span class="sxs-lookup"><span data-stu-id="f5cf3-124">Publish your Spark .NET app as self-contained.</span></span>

   <span data-ttu-id="f5cf3-125">Ejecute el siguiente comando en Linux.</span><span class="sxs-lookup"><span data-stu-id="f5cf3-125">Run the following command on Linux.</span></span>

   ```bash
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. <span data-ttu-id="f5cf3-126">Producir `<your app>.zip` para los archivos publicados.</span><span class="sxs-lookup"><span data-stu-id="f5cf3-126">Produce `<your app>.zip` for the published files.</span></span>

   <span data-ttu-id="f5cf3-127">Ejecute el siguiente comando en Linux con `zip`.</span><span class="sxs-lookup"><span data-stu-id="f5cf3-127">Run the following command on Linux using `zip`.</span></span>

   ```bash
   zip -r <your app>.zip .
   ```

4. <span data-ttu-id="f5cf3-128">Cargue los siguientes elementos en un sistema de archivos distribuido (por ejemplo, S3) al que el clúster tenga acceso:</span><span class="sxs-lookup"><span data-stu-id="f5cf3-128">Upload the following items to a distributed file system (e.g., S3) that your cluster has access to:</span></span>

   * <span data-ttu-id="f5cf3-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: Este archivo jar se incluye como parte del paquete NuGet [Microsoft. Spark](https://www.nuget.org/packages/Microsoft.Spark/) y se encuentra en el directorio de salida de la compilación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f5cf3-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: This jar is included as part of the [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet package and is colocated in your app's build output directory.</span></span>
   * `<your app>.zip`
   * <span data-ttu-id="f5cf3-130">Los archivos (como los archivos de dependencia o los datos comunes accesibles para cada trabajo) o los ensamblados (como los archivos DLL que contienen las funciones definidas por el usuario o las bibliotecas de las que depende la aplicación) se colocarán en el directorio de trabajo de cada ejecutor.</span><span class="sxs-lookup"><span data-stu-id="f5cf3-130">Files (like dependency files or common data accessible to every worker) or assemblies (like DLLs that contain your user-defined functions or libraries that your app depends on) to be placed in the working directory of each executor.</span></span>

## <a name="deploy-to-amazon-emr-spark"></a><span data-ttu-id="f5cf3-131">Implementación en Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="f5cf3-131">Deploy to Amazon EMR Spark</span></span>

<span data-ttu-id="f5cf3-132">[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) es una plataforma de clústeres administrada que simplifica la ejecución de los marcos de Big Data en AWS.</span><span class="sxs-lookup"><span data-stu-id="f5cf3-132">[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) is a managed cluster platform that simplifies running big data frameworks on AWS.</span></span>

> [!NOTE] 
> <span data-ttu-id="f5cf3-133">Amazon EMR Spark está basado en Linux.</span><span class="sxs-lookup"><span data-stu-id="f5cf3-133">Amazon EMR Spark is Linux-based.</span></span> <span data-ttu-id="f5cf3-134">Por lo tanto, si está interesado en implementar la aplicación en Amazon EMR Spark, asegúrese de que la aplicación es .NET Standard compatible y de que usa el compilador de [.net Core](https://dotnet.microsoft.com/download) para compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f5cf3-134">Therefore, if you are interested in deploying your app to Amazon EMR Spark, make sure your app is .NET Standard compatible and that you use the [.NET Core compiler](https://dotnet.microsoft.com/download) to compile your app.</span></span>

### <a name="deploy-microsoftsparkworker"></a><span data-ttu-id="f5cf3-135">Implementación de Microsoft. Spark. Worker</span><span class="sxs-lookup"><span data-stu-id="f5cf3-135">Deploy Microsoft.Spark.Worker</span></span>

<span data-ttu-id="f5cf3-136">Este paso solo es necesario en la creación del clúster.</span><span class="sxs-lookup"><span data-stu-id="f5cf3-136">This step is only required at cluster creation.</span></span>

<span data-ttu-id="f5cf3-137">Ejecute `install-worker.sh` durante la creación del clúster mediante [acciones de bootstrap](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-bootstrap.html).</span><span class="sxs-lookup"><span data-stu-id="f5cf3-137">Run `install-worker.sh` during cluster creation using [Bootstrap Actions](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-bootstrap.html).</span></span>

<span data-ttu-id="f5cf3-138">Ejecute el siguiente comando en Linux con la CLI de AWS.</span><span class="sxs-lookup"><span data-stu-id="f5cf3-138">Run the following command on Linux using AWS CLI.</span></span>

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

## <a name="run-your-app"></a><span data-ttu-id="f5cf3-139">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="f5cf3-139">Run your app</span></span>

<span data-ttu-id="f5cf3-140">Hay dos maneras de ejecutar la aplicación en los pasos de Amazon EMR Spark: Spark-Submit y Amazon EMR.</span><span class="sxs-lookup"><span data-stu-id="f5cf3-140">There are two ways to run your app in Amazon EMR Spark: spark-submit and Amazon EMR Steps.</span></span>

### <a name="use-spark-submit"></a><span data-ttu-id="f5cf3-141">Uso de Spark-Submit</span><span class="sxs-lookup"><span data-stu-id="f5cf3-141">Use spark-submit</span></span>

<span data-ttu-id="f5cf3-142">Puede usar el comando [Spark-Submit](https://spark.apache.org/docs/latest/submitting-applications.html) para enviar .net para trabajos Apache Spark a Amazon EMR Spark.</span><span class="sxs-lookup"><span data-stu-id="f5cf3-142">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Amazon EMR Spark.</span></span>

1. <span data-ttu-id="f5cf3-143">`ssh`en uno de los nodos del clúster.</span><span class="sxs-lookup"><span data-stu-id="f5cf3-143">`ssh` into one of the nodes in the cluster.</span></span>

2. <span data-ttu-id="f5cf3-144">Ejecute `spark-submit`.</span><span class="sxs-lookup"><span data-stu-id="f5cf3-144">Run `spark-submit`.</span></span>

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar \
   s3://mybucket/<some dir>/<your app>.zip <your app> <app args>
   ```

### <a name="use-amazon-emr-steps"></a><span data-ttu-id="f5cf3-145">Usar los pasos de Amazon EMR</span><span class="sxs-lookup"><span data-stu-id="f5cf3-145">Use Amazon EMR Steps</span></span>

<span data-ttu-id="f5cf3-146">[Los pasos de Amazon EMR](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-spark-submit-step.html) se pueden usar para enviar trabajos al marco de Spark instalado en el clúster de EMR.</span><span class="sxs-lookup"><span data-stu-id="f5cf3-146">[Amazon EMR Steps](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-spark-submit-step.html) can be used to submit jobs to the Spark framework installed on the EMR cluster.</span></span>

<span data-ttu-id="f5cf3-147">Ejecute el siguiente comando en Linux con la CLI de AWS.</span><span class="sxs-lookup"><span data-stu-id="f5cf3-147">Run the following command on Linux using AWS CLI.</span></span>

```bash
aws emr add-steps \
--cluster-id j-xxxxxxxxxxxxx \
--steps Type=spark,Name="Spark Program",Args=[--master,yarn,--files,s3://mybucket/<some dir>/<udf assembly>,--class,org.apache.spark.deploy.DotnetRunner,s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar,s3://mybucket/<some dir>/<your app>.zip,<your app>,<app arg 1>,<app arg 2>,...,<app arg n>],ActionOnFailure=CONTINUE
```

## <a name="next-steps"></a><span data-ttu-id="f5cf3-148">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="f5cf3-148">Next steps</span></span>

<span data-ttu-id="f5cf3-149">En este tutorial, ha implementado .NET para Apache Spark aplicación en Amazon EMR Spark.</span><span class="sxs-lookup"><span data-stu-id="f5cf3-149">In this tutorial, you deployed your .NET for Apache Spark application to Amazon EMR Spark.</span></span> <span data-ttu-id="f5cf3-150">Para .NET para Apache Spark proyectos de ejemplo, continúe en GitHub.</span><span class="sxs-lookup"><span data-stu-id="f5cf3-150">For .NET for Apache Spark example projects, continue to GitHub.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f5cf3-151">Ejemplos de .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="f5cf3-151">.NET for Apache Spark samples</span></span>](https://github.com/dotnet/spark/tree/master/examples)
