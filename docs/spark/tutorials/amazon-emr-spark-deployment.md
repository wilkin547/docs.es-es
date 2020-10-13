---
title: Implementación de una aplicación de .NET para Apache Spark en Amazon EMR Spark
description: Sepa cómo implementar una aplicación de .NET para Apache Spark en Amazon EMR Spark.
ms.date: 10/09/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 0232896254e93525f2a6f0be05417107cf7f5432
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2020
ms.locfileid: "91955478"
---
# <a name="deploy-a-net-for-apache-spark-application-to-amazon-emr-spark"></a><span data-ttu-id="41969-103">Implementación de una aplicación de .NET para Apache Spark en Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="41969-103">Deploy a .NET for Apache Spark application to Amazon EMR Spark</span></span>

<span data-ttu-id="41969-104">En este tutorial aprenderá a implementar una aplicación de .NET para Apache Spark en Amazon EMR Spark.</span><span class="sxs-lookup"><span data-stu-id="41969-104">This tutorial teaches how to deploy a .NET for Apache Spark application to Amazon EMR Spark.</span></span>

<span data-ttu-id="41969-105">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="41969-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="41969-106">Preparar Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="41969-106">Prepare Microsoft.Spark.Worker</span></span>
> * <span data-ttu-id="41969-107">Publicar la aplicación de .NET para Spark</span><span class="sxs-lookup"><span data-stu-id="41969-107">Publish your Spark .NET app</span></span>
> * <span data-ttu-id="41969-108">Implementar la aplicación en Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="41969-108">Deploy your app to Amazon EMR Spark</span></span>
> * <span data-ttu-id="41969-109">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="41969-109">Run your app</span></span>

## <a name="prerequisites"></a><span data-ttu-id="41969-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="41969-110">Prerequisites</span></span>

<span data-ttu-id="41969-111">Antes de empezar, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="41969-111">Before you start, do the following:</span></span>

* <span data-ttu-id="41969-112">Descargue la [CLI de AWS](https://aws.amazon.com/cli/).</span><span class="sxs-lookup"><span data-stu-id="41969-112">Download the [AWS CLI](https://aws.amazon.com/cli/).</span></span>
* <span data-ttu-id="41969-113">Descargue [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="41969-113">Download [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to your local machine.</span></span> <span data-ttu-id="41969-114">Es un script de aplicación auxiliar que usaremos más adelante para copiar archivos dependientes de .NET para Apache Spark en los nodos de trabajo del clúster de Spark.</span><span class="sxs-lookup"><span data-stu-id="41969-114">This is a helper script that you use later to copy .NET for Apache Spark dependent files into your Spark cluster's worker nodes.</span></span>

## <a name="prepare-worker-dependencies"></a><span data-ttu-id="41969-115">Preparación de las dependencias de trabajo</span><span class="sxs-lookup"><span data-stu-id="41969-115">Prepare worker dependencies</span></span>

<span data-ttu-id="41969-116">**Microsoft.Spark.Worker** es un componente back-end que reside en los nodos de trabajo individuales del clúster de Spark.</span><span class="sxs-lookup"><span data-stu-id="41969-116">**Microsoft.Spark.Worker** is a backend component that lives on the individual worker nodes of your Spark cluster.</span></span> <span data-ttu-id="41969-117">Si quiere ejecutar una función definida por el usuario (UDF) de C#, Spark necesita saber cómo iniciar .NET CLR para ejecutar la UDF.</span><span class="sxs-lookup"><span data-stu-id="41969-117">When you want to execute a C# UDF (user-defined function), Spark needs to understand how to launch the .NET CLR to execute the UDF.</span></span> <span data-ttu-id="41969-118">**Microsoft.Spark.Worker** pone a disposición de Spark una colección de clases que habilitan esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="41969-118">**Microsoft.Spark.Worker** provides a collection of classes to Spark that enable this functionality.</span></span>

1. <span data-ttu-id="41969-119">Seleccione una versión netcoreapp de Linux de [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) para implementarla en el clúster.</span><span class="sxs-lookup"><span data-stu-id="41969-119">Select a [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp release to be deployed on your cluster.</span></span>

   <span data-ttu-id="41969-120">Por ejemplo, si quiere que `.NET for Apache Spark v0.1.0` use `netcoreapp2.1`, tendría que descargar [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span><span class="sxs-lookup"><span data-stu-id="41969-120">For example, if you want `.NET for Apache Spark v0.1.0` using `netcoreapp2.1`, you'd download [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span></span>

2. <span data-ttu-id="41969-121">Cargue `Microsoft.Spark.Worker.<release>.tar.gz` e [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) en un sistema de archivos distribuido (por ejemplo, S3) al que el clúster tenga acceso.</span><span class="sxs-lookup"><span data-stu-id="41969-121">Upload `Microsoft.Spark.Worker.<release>.tar.gz` and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to a distributed file system (e.g., S3) that your cluster has access to.</span></span>

## <a name="prepare-your-net-for-apache-spark-app"></a><span data-ttu-id="41969-122">Preparación de la aplicación de .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="41969-122">Prepare your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="41969-123">Siga el tutorial de [introducción](get-started.md) para crear la aplicación.</span><span class="sxs-lookup"><span data-stu-id="41969-123">Follow the [Get Started](get-started.md) tutorial to build your app.</span></span>

2. <span data-ttu-id="41969-124">Publique la aplicación de .NET para Spark como independiente.</span><span class="sxs-lookup"><span data-stu-id="41969-124">Publish your Spark .NET app as self-contained.</span></span>

   <span data-ttu-id="41969-125">Ejecute el siguiente comando en Linux.</span><span class="sxs-lookup"><span data-stu-id="41969-125">Run the following command on Linux.</span></span>

   ```dotnetcli
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. <span data-ttu-id="41969-126">Genere `<your app>.zip` para los archivos publicados.</span><span class="sxs-lookup"><span data-stu-id="41969-126">Produce `<your app>.zip` for the published files.</span></span>

   <span data-ttu-id="41969-127">Ejecute el siguiente comando en Linux usando `zip`.</span><span class="sxs-lookup"><span data-stu-id="41969-127">Run the following command on Linux using `zip`.</span></span>

   ```bash
   zip -r <your app>.zip .
   ```

4. <span data-ttu-id="41969-128">Cargue los siguientes elementos en un sistema de archivos distribuido (por ejemplo, S3) al que el clúster tenga acceso:</span><span class="sxs-lookup"><span data-stu-id="41969-128">Upload the following items to a distributed file system (e.g., S3) that your cluster has access to:</span></span>

   * <span data-ttu-id="41969-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: Este archivo jar se incluye como parte del paquete NuGet [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/), y se encuentra en el directorio de salida de creación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="41969-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: This jar is included as part of the [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet package and is colocated in your app's build output directory.</span></span>
   * `<your app>.zip`
   * <span data-ttu-id="41969-130">Los archivos (como los archivos de dependencias o los datos comunes accesibles para todos los trabajos) o los ensamblados (como los archivos DLL que contienen las bibliotecas o las funciones definidas por el usuario de las que depende la aplicación) se colocarán en el directorio de trabajo de cada ejecutor.</span><span class="sxs-lookup"><span data-stu-id="41969-130">Files (like dependency files or common data accessible to every worker) or assemblies (like DLLs that contain your user-defined functions or libraries that your app depends on) to be placed in the working directory of each executor.</span></span>

## <a name="deploy-to-amazon-emr-spark"></a><span data-ttu-id="41969-131">Implementación en Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="41969-131">Deploy to Amazon EMR Spark</span></span>

<span data-ttu-id="41969-132">[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) es una plataforma de clúster administrada que simplifica la ejecución de marcos de macrodatos en AWS.</span><span class="sxs-lookup"><span data-stu-id="41969-132">[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) is a managed cluster platform that simplifies running big data frameworks on AWS.</span></span>

> [!NOTE]
> <span data-ttu-id="41969-133">Amazon EMR Spark se basa en Linux.</span><span class="sxs-lookup"><span data-stu-id="41969-133">Amazon EMR Spark is Linux-based.</span></span> <span data-ttu-id="41969-134">Por lo tanto, si está interesado en implementar la aplicación en Amazon EMR Spark, asegúrese de que la aplicación es compatible con .NET Standard y, asimismo, de que usa el [compilador de .NET Core](https://dotnet.microsoft.com/download) para compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="41969-134">Therefore, if you are interested in deploying your app to Amazon EMR Spark, make sure your app is .NET Standard compatible and that you use the [.NET Core compiler](https://dotnet.microsoft.com/download) to compile your app.</span></span>

### <a name="deploy-microsoftsparkworker"></a><span data-ttu-id="41969-135">Implementación de Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="41969-135">Deploy Microsoft.Spark.Worker</span></span>

<span data-ttu-id="41969-136">Este paso solo es necesario realizarlo al crear un clúster.</span><span class="sxs-lookup"><span data-stu-id="41969-136">This step is only required at cluster creation.</span></span>

<span data-ttu-id="41969-137">Ejecute `install-worker.sh` durante la creación del clúster mediante [acciones de arranque](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-bootstrap.html).</span><span class="sxs-lookup"><span data-stu-id="41969-137">Run `install-worker.sh` during cluster creation using [Bootstrap Actions](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-bootstrap.html).</span></span>

<span data-ttu-id="41969-138">Ejecute el siguiente comando en Linux usando la CLI de AWS.</span><span class="sxs-lookup"><span data-stu-id="41969-138">Run the following command on Linux using AWS CLI.</span></span>

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

## <a name="run-your-app"></a><span data-ttu-id="41969-139">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="41969-139">Run your app</span></span>

<span data-ttu-id="41969-140">Hay dos maneras de ejecutar la aplicación en Amazon EMR Spark: con spark-submit o con pasos de Amazon EMR.</span><span class="sxs-lookup"><span data-stu-id="41969-140">There are two ways to run your app in Amazon EMR Spark: spark-submit and Amazon EMR Steps.</span></span>

### <a name="use-spark-submit"></a><span data-ttu-id="41969-141">Uso de spark-submit</span><span class="sxs-lookup"><span data-stu-id="41969-141">Use spark-submit</span></span>

<span data-ttu-id="41969-142">Puede usar el comando [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) para enviar trabajos de .NET para Apache Spark a Amazon EMR Spark.</span><span class="sxs-lookup"><span data-stu-id="41969-142">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Amazon EMR Spark.</span></span>

1. <span data-ttu-id="41969-143">Aplique `ssh` en uno de los nodos del clúster.</span><span class="sxs-lookup"><span data-stu-id="41969-143">`ssh` into one of the nodes in the cluster.</span></span>

2. <span data-ttu-id="41969-144">Ejecute `spark-submit`.</span><span class="sxs-lookup"><span data-stu-id="41969-144">Run `spark-submit`.</span></span>

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar \
   s3://mybucket/<some dir>/<your app>.zip <your app> <app args>
   ```

### <a name="use-amazon-emr-steps"></a><span data-ttu-id="41969-145">Uso de pasos de Amazon EMR</span><span class="sxs-lookup"><span data-stu-id="41969-145">Use Amazon EMR Steps</span></span>

<span data-ttu-id="41969-146">Se pueden usar [pasos de Amazon EMR](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-spark-submit-step.html) para enviar trabajos al marco de Spark instalado en el clúster de EMR.</span><span class="sxs-lookup"><span data-stu-id="41969-146">[Amazon EMR Steps](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-spark-submit-step.html) can be used to submit jobs to the Spark framework installed on the EMR cluster.</span></span>

<span data-ttu-id="41969-147">Ejecute el siguiente comando en Linux usando la CLI de AWS.</span><span class="sxs-lookup"><span data-stu-id="41969-147">Run the following command on Linux using AWS CLI.</span></span>

```bash
aws emr add-steps \
--cluster-id j-xxxxxxxxxxxxx \
--steps Type=spark,Name="Spark Program",Args=[--master,yarn,--files,s3://mybucket/<some dir>/<udf assembly>,--class,org.apache.spark.deploy.dotnet.DotnetRunner,s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar,s3://mybucket/<some dir>/<your app>.zip,<your app>,<app arg 1>,<app arg 2>,...,<app arg n>],ActionOnFailure=CONTINUE
```

## <a name="next-steps"></a><span data-ttu-id="41969-148">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="41969-148">Next steps</span></span>

<span data-ttu-id="41969-149">En este tutorial ha implementado una aplicación de .NET para Apache Spark en Amazon EMR Spark.</span><span class="sxs-lookup"><span data-stu-id="41969-149">In this tutorial, you deployed your .NET for Apache Spark application to Amazon EMR Spark.</span></span> <span data-ttu-id="41969-150">Para ver proyectos de ejemplo de .NET para Apache Spark, continúe en GitHub.</span><span class="sxs-lookup"><span data-stu-id="41969-150">For .NET for Apache Spark example projects, continue to GitHub.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="41969-151">Ejemplos de .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="41969-151">.NET for Apache Spark samples</span></span>](https://github.com/dotnet/spark/tree/master/examples)
