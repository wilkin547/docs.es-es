---
title: Implementación de una aplicación de .NET para Apache Spark en Databricks
description: Sepa cómo implementar una aplicación de .NET para Apache Spark en Databricks.
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 3c9169e2936742c82ba27327ac07f0aa1b4c645c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70254040"
---
# <a name="deploy-a-net-for-apache-spark-application-to-databricks"></a><span data-ttu-id="a5a80-103">Implementación de una aplicación de .NET para Apache Spark en Databricks</span><span class="sxs-lookup"><span data-stu-id="a5a80-103">Deploy a .NET for Apache Spark application to Databricks</span></span>

<span data-ttu-id="a5a80-104">En este tutorial aprenderá a implementar una aplicación de .NET para Apache Spark en Databricks.</span><span class="sxs-lookup"><span data-stu-id="a5a80-104">This tutorial teaches how to deploy a .NET for Apache Spark application to Databricks.</span></span>

<span data-ttu-id="a5a80-105">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="a5a80-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
> - <span data-ttu-id="a5a80-106">Preparar Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="a5a80-106">Prepare Microsoft.Spark.Worker</span></span>
> - <span data-ttu-id="a5a80-107">Publicar la aplicación de .NET para Spark</span><span class="sxs-lookup"><span data-stu-id="a5a80-107">Publish your Spark .NET app</span></span>
> - <span data-ttu-id="a5a80-108">Implementar una aplicación en Databricks</span><span class="sxs-lookup"><span data-stu-id="a5a80-108">Deploy your app to Databricks</span></span>
> - <span data-ttu-id="a5a80-109">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="a5a80-109">Run your app</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a5a80-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a5a80-110">Prerequisites</span></span>

<span data-ttu-id="a5a80-111">Antes de empezar, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a5a80-111">Before you start, do the following:</span></span>

- <span data-ttu-id="a5a80-112">Descargue la [CLI de Databricks](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html).</span><span class="sxs-lookup"><span data-stu-id="a5a80-112">Download the [Databricks CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html).</span></span>
- <span data-ttu-id="a5a80-113">Descargue [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="a5a80-113">Download [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to your local machine.</span></span> <span data-ttu-id="a5a80-114">Es un script de aplicación auxiliar que usaremos más adelante para copiar archivos dependientes de .NET para Apache Spark en los nodos de trabajo del clúster de Spark.</span><span class="sxs-lookup"><span data-stu-id="a5a80-114">This is a helper script that you use later to copy .NET for Apache Spark dependent files into your Spark cluster's worker nodes.</span></span>

## <a name="prepare-worker-dependencies"></a><span data-ttu-id="a5a80-115">Preparación de las dependencias de trabajo</span><span class="sxs-lookup"><span data-stu-id="a5a80-115">Prepare worker dependencies</span></span>

<span data-ttu-id="a5a80-116">**Microsoft.Spark.Worker** es un componente back-end que reside en los nodos de trabajo individuales del clúster de Spark.</span><span class="sxs-lookup"><span data-stu-id="a5a80-116">**Microsoft.Spark.Worker** is a back-end component that lives on the individual worker nodes of your Spark cluster.</span></span> <span data-ttu-id="a5a80-117">Si quiere ejecutar una función definida por el usuario (UDF) de C#, Spark necesita saber cómo iniciar .NET CLR para ejecutar la UDF.</span><span class="sxs-lookup"><span data-stu-id="a5a80-117">When you want to execute a C# UDF (user-defined function), Spark needs to understand how to launch the .NET CLR to execute the UDF.</span></span> <span data-ttu-id="a5a80-118">**Microsoft.Spark.Worker** pone a disposición de Spark una colección de clases que habilitan esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="a5a80-118">**Microsoft.Spark.Worker** provides a collection of classes to Spark that enable this functionality.</span></span>

1. <span data-ttu-id="a5a80-119">Seleccione una versión netcoreapp de Linux de [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) para implementarla en el clúster.</span><span class="sxs-lookup"><span data-stu-id="a5a80-119">Select a [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp release to be deployed on your cluster.</span></span>

   <span data-ttu-id="a5a80-120">Por ejemplo, si quiere que `.NET for Apache Spark v0.1.0` use `netcoreapp2.1`, tendría que descargar [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span><span class="sxs-lookup"><span data-stu-id="a5a80-120">For example, if you want `.NET for Apache Spark v0.1.0` using `netcoreapp2.1`, you'd download [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span></span>

2. <span data-ttu-id="a5a80-121">Cargue `Microsoft.Spark.Worker.<release>.tar.gz` e [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) en un sistema de archivos distribuido (por ejemplo, DBFS) al que el clúster tenga acceso.</span><span class="sxs-lookup"><span data-stu-id="a5a80-121">Upload `Microsoft.Spark.Worker.<release>.tar.gz` and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to a distributed file system (for example, DBFS) that your cluster has access to.</span></span>

## <a name="prepare-your-net-for-apache-spark-app"></a><span data-ttu-id="a5a80-122">Preparación de la aplicación de .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="a5a80-122">Prepare your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="a5a80-123">Siga el tutorial de [introducción](get-started.md) para crear la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a5a80-123">Follow the [Get Started](get-started.md) tutorial to build your app.</span></span>

2. <span data-ttu-id="a5a80-124">Publique la aplicación de .NET para Spark como independiente.</span><span class="sxs-lookup"><span data-stu-id="a5a80-124">Publish your Spark .NET app as self-contained.</span></span>

   <span data-ttu-id="a5a80-125">Puede ejecutar el siguiente comando en Linux.</span><span class="sxs-lookup"><span data-stu-id="a5a80-125">You can run the following command on Linux.</span></span>

   ```bash
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. <span data-ttu-id="a5a80-126">Genere `<your app>.zip` para los archivos publicados.</span><span class="sxs-lookup"><span data-stu-id="a5a80-126">Produce `<your app>.zip` for the published files.</span></span>

   <span data-ttu-id="a5a80-127">Puede ejecutar el siguiente comando en Linux usando `zip`.</span><span class="sxs-lookup"><span data-stu-id="a5a80-127">You can run the following command on Linux using `zip`.</span></span>

   ```bash
   zip -r <your app>.zip .
   ```

4. <span data-ttu-id="a5a80-128">Cargue lo siguiente en un sistema de archivos distribuido (por ejemplo, DBFS) al que el clúster tenga acceso:</span><span class="sxs-lookup"><span data-stu-id="a5a80-128">Upload the following to a distributed file system (for example, DBFS) that your cluster has access to:</span></span>

   - <span data-ttu-id="a5a80-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: Este archivo jar se incluye como parte del paquete NuGet [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/), y se encuentra en el directorio de salida de creación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a5a80-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: This jar is included as part of the [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet package and is colocated in your app's build output directory.</span></span>
   - `<your app>.zip`
   - <span data-ttu-id="a5a80-130">Los archivos (como los archivos de dependencias o los datos comunes accesibles para todos los trabajos) o los ensamblados (como los archivos DLL que contienen las bibliotecas o las funciones definidas por el usuario de las que depende la aplicación) se colocarán en el directorio de trabajo de cada ejecutor.</span><span class="sxs-lookup"><span data-stu-id="a5a80-130">Files (like dependency files or common data accessible to every worker) or assemblies (like DLLs that contain your user-defined functions or libraries that your app depends on) to be placed in the working directory of each executor.</span></span>

## <a name="deploy-to-databricks"></a><span data-ttu-id="a5a80-131">Implementación en Databricks</span><span class="sxs-lookup"><span data-stu-id="a5a80-131">Deploy to Databricks</span></span>

<span data-ttu-id="a5a80-132">[Databricks](https://databricks.com) es una plataforma que permite el procesamiento de macrodatos en la nube mediante Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="a5a80-132">[Databricks](https://databricks.com) is a platform that provides cloud-based big data processing using Apache Spark.</span></span>

> [!Note] 
> <span data-ttu-id="a5a80-133">[Azure Databricks](https://azure.microsoft.com/services/databricks/) y [AWS Databricks](https://databricks.com/aws) se basan en Linux.</span><span class="sxs-lookup"><span data-stu-id="a5a80-133">[Azure Databricks](https://azure.microsoft.com/services/databricks/) and [AWS Databricks](https://databricks.com/aws) are Linux-based.</span></span> <span data-ttu-id="a5a80-134">Por lo tanto, si está interesado en implementar la aplicación en Databricks, asegúrese de que la aplicación es compatible con .NET Standard y, asimismo, de que usa el [compilador de .NET Core](https://dotnet.microsoft.com/download) para compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a5a80-134">Therefore, if you are interested in deploying your app to Databricks, make sure your app is .NET Standard compatible and that you use [.NET Core compiler](https://dotnet.microsoft.com/download) to compile your app.</span></span>

<span data-ttu-id="a5a80-135">Databricks permite enviar las aplicaciones de .NET para Apache Spark a un clúster activo existente, o bien crear un clúster cada vez que un trabajo se inicie.</span><span class="sxs-lookup"><span data-stu-id="a5a80-135">Databricks allows you to submit .NET for Apache Spark apps to an existing active cluster or create a new cluster every time you launch a job.</span></span> <span data-ttu-id="a5a80-136">Esto requiere instalar **Microsoft.Spark.Worker** antes de enviar la aplicación de .NET para Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="a5a80-136">This requires the **Microsoft.Spark.Worker** to be installed before you submit a .NET for Apache Spark app.</span></span>

### <a name="deploy-microsoftsparkworker"></a><span data-ttu-id="a5a80-137">Implementación de Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="a5a80-137">Deploy Microsoft.Spark.Worker</span></span>

<span data-ttu-id="a5a80-138">Este paso solo es necesario realizarlo una vez en un clúster.</span><span class="sxs-lookup"><span data-stu-id="a5a80-138">This step is only required once for a cluster.</span></span>

1. <span data-ttu-id="a5a80-139">Descargue [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) e [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh
) en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="a5a80-139">Download [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh
) onto your local machine.</span></span>

2. <span data-ttu-id="a5a80-140">Modifique **db-init.sh** para que apunte a la versión de **Microsoft.Spark.Worker** que quiera descargar e instalar en el clúster.</span><span class="sxs-lookup"><span data-stu-id="a5a80-140">Modify **db-init.sh** to point to the **Microsoft.Spark.Worker** release you want to download and install on your cluster.</span></span>

3. <span data-ttu-id="a5a80-141">Instale la [CLI de Databricks](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html).</span><span class="sxs-lookup"><span data-stu-id="a5a80-141">Install the [Databricks CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html).</span></span>

4. <span data-ttu-id="a5a80-142">[Configure los detalles de autenticación](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html#set-up-authentication) de la CLI de Databricks.</span><span class="sxs-lookup"><span data-stu-id="a5a80-142">[Setup authentication](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html#set-up-authentication) details for the Databricks CLI.</span></span>

5. <span data-ttu-id="a5a80-143">Cargue los archivos en el clúster de Databricks mediante el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a5a80-143">Upload the files to your Databricks cluster using the following command:</span></span>

   ```bash
   cd <path-to-db-init-and-install-worker>
   databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
   databricks fs cp install-worker.sh dbfs:/spark-dotnet/install-worker.sh
   ```

6. <span data-ttu-id="a5a80-144">Acceda al área de trabajo de Databricks.</span><span class="sxs-lookup"><span data-stu-id="a5a80-144">Go to your Databricks workspace.</span></span> <span data-ttu-id="a5a80-145">Seleccione  **Clústeres** en el menú de la izquierda y, después, seleccione **Crear clúster**.</span><span class="sxs-lookup"><span data-stu-id="a5a80-145">Select **Clusters** from the left-side menu, and then select **Create Cluster**.</span></span>

7. <span data-ttu-id="a5a80-146">Después de configurar el clúster correctamente, defina el **script Init** y cree el clúster.</span><span class="sxs-lookup"><span data-stu-id="a5a80-146">After configuring the cluster appropriately, set the **Init Script** and create the cluster.</span></span>

   ![Imagen de acción de script](./media/databricks-deployment/deployment-databricks-init-script.png)

## <a name="run-your-app"></a><span data-ttu-id="a5a80-148">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="a5a80-148">Run your app</span></span> 

<span data-ttu-id="a5a80-149">Puede usar `set JAR` o `spark-submit` para enviar el trabajo a Databricks.</span><span class="sxs-lookup"><span data-stu-id="a5a80-149">You can use `set JAR` or `spark-submit` to submit your job to Databricks.</span></span>

### <a name="use-set-jar"></a><span data-ttu-id="a5a80-150">Uso de Set JAR</span><span class="sxs-lookup"><span data-stu-id="a5a80-150">Use Set JAR</span></span>

<span data-ttu-id="a5a80-151">[Set JAR](https://docs.databricks.com/user-guide/jobs.html#create-a-job) permite enviar un trabajo a un clúster activo existente.</span><span class="sxs-lookup"><span data-stu-id="a5a80-151">[Set JAR](https://docs.databricks.com/user-guide/jobs.html#create-a-job) allows you to submit a job to an existing active cluster.</span></span>

#### <a name="one-time-setup"></a><span data-ttu-id="a5a80-152">Instalación única</span><span class="sxs-lookup"><span data-stu-id="a5a80-152">One-time setup</span></span>

1. <span data-ttu-id="a5a80-153">Vaya al clúster de Databricks y seleccione **Trabajos** en el menú de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="a5a80-153">Go to your Databricks cluster and select **Jobs** from the left-side menu.</span></span> <span data-ttu-id="a5a80-154">Después, seleccione **Set JAR**.</span><span class="sxs-lookup"><span data-stu-id="a5a80-154">Then select **Set JAR**.</span></span>

2. <span data-ttu-id="a5a80-155">Cargue el archivo `microsoft-spark-<spark-version>-<spark-dotnet-version>.jar` adecuado.</span><span class="sxs-lookup"><span data-stu-id="a5a80-155">Upload the appropriate `microsoft-spark-<spark-version>-<spark-dotnet-version>.jar` file.</span></span>

3. <span data-ttu-id="a5a80-156">Establezca los parámetros de forma adecuada.</span><span class="sxs-lookup"><span data-stu-id="a5a80-156">Set the parameters appropriately.</span></span>

   ```
   Main Class: org.apache.spark.deploy.dotnet.DotnetRunner
   Arguments /dbfs/apps/<your-app-name>.zip <your-app-main-class>
   ```
 
4. <span data-ttu-id="a5a80-157">Configure el **clúster** para que apunte al clúster existente para el que creó el **script Init** en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="a5a80-157">Configure the **Cluster** to point to the existing cluster you created the **Init Script** for in the previous section.</span></span>

#### <a name="publish-and-run-your-app"></a><span data-ttu-id="a5a80-158">Publicación y ejecución de la aplicación</span><span class="sxs-lookup"><span data-stu-id="a5a80-158">Publish and run your app</span></span>

1. <span data-ttu-id="a5a80-159">Use la [CLI de Databricks](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html) para cargar la aplicación en el clúster de Databricks.</span><span class="sxs-lookup"><span data-stu-id="a5a80-159">Use the [Databricks CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html) to upload your application to your Databricks cluster.</span></span>

      ```bash
      cd <path-to-your-app-publish-directory>
      databricks fs cp <your-app-name>.zip dbfs:/apps/<your-app-name>.zip
      ```

2. <span data-ttu-id="a5a80-160">Este paso solo es necesario si los ensamblados de la aplicación (por ejemplo, los archivos DLL que contienen funciones definidas por el usuario junto con sus dependencias) deben colocarse en el directorio de trabajo de cada **Microsoft.Spark.Worker**.</span><span class="sxs-lookup"><span data-stu-id="a5a80-160">This step is only required if your app assemblies (for example, DLLs that contain user-defined functions along with their dependencies) need to be placed in the working directory of each **Microsoft.Spark.Worker**.</span></span>

   - <span data-ttu-id="a5a80-161">Carga de los ensamblados de la aplicación en el clúster de Databricks</span><span class="sxs-lookup"><span data-stu-id="a5a80-161">Upload your application assemblies to your Databricks cluster</span></span>
      
      ```bash
      cd <path-to-your-app-publish-directory>
      databricks fs cp <assembly>.dll dbfs:/apps/dependencies
      ```

   - <span data-ttu-id="a5a80-162">Quite la marca de comentario y modifique la sección de dependencias de la aplicación en [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) para que apunte a la ruta de acceso de las dependencias de la aplicación y cargue en el clúster de Databricks.</span><span class="sxs-lookup"><span data-stu-id="a5a80-162">Uncomment and modify the app dependencies section in [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) to point to your app dependencies path and upload to your Databricks cluster.</span></span>
   
      ```bash
      cd <path-to-db-init-and-install-worker>
      databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
      ```
   
   - <span data-ttu-id="a5a80-163">Reinicie el clúster.</span><span class="sxs-lookup"><span data-stu-id="a5a80-163">Restart your cluster.</span></span>

3. <span data-ttu-id="a5a80-164">Vaya al clúster de Databricks en el área de trabajo de Databricks.</span><span class="sxs-lookup"><span data-stu-id="a5a80-164">Go to your Databricks cluster in your Databricks workspace.</span></span> <span data-ttu-id="a5a80-165">En **Trabajos**, seleccione el trabajo y, después, seleccione **Ejecutar ahora** para ejecutar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="a5a80-165">Under **Jobs**, select your job and then select **Run Now** to run your job.</span></span>

### <a name="use-spark-submit"></a><span data-ttu-id="a5a80-166">Uso de spark-submit</span><span class="sxs-lookup"><span data-stu-id="a5a80-166">Use spark-submit</span></span>

<span data-ttu-id="a5a80-167">El comando [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) permite enviar un trabajo a un clúster nuevo.</span><span class="sxs-lookup"><span data-stu-id="a5a80-167">The [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command allows you to submit a job to a new cluster.</span></span>

1. <span data-ttu-id="a5a80-168">[Cree un trabajo](https://docs.databricks.com/user-guide/jobs.html) y seleccione **Configurar spark-submit**.</span><span class="sxs-lookup"><span data-stu-id="a5a80-168">[Create a Job](https://docs.databricks.com/user-guide/jobs.html) and select **Configure spark-submit**.</span></span>

2. <span data-ttu-id="a5a80-169">Configure `spark-submit` con los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="a5a80-169">Configure `spark-submit` with the following parameters:</span></span>

      ```bash
      ["--files","/dbfs/<path-to>/<app assembly/file to deploy to worker>","--class","org.apache.spark.deploy.dotnet.DotnetRunner","/dbfs/<path-to>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar","/dbfs/<path-to>/<app name>.zip","<app bin name>","app arg1","app arg2"]
      ```

3. <span data-ttu-id="a5a80-170">Vaya al clúster de Databricks en el área de trabajo de Databricks.</span><span class="sxs-lookup"><span data-stu-id="a5a80-170">Go to your Databricks cluster in your Databricks workspace.</span></span> <span data-ttu-id="a5a80-171">En **Trabajos**, seleccione el trabajo y, después, seleccione **Ejecutar ahora** para ejecutar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="a5a80-171">Under **Jobs**, select your job and then select **Run Now** to run your job.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a5a80-172">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a5a80-172">Next steps</span></span>

<span data-ttu-id="a5a80-173">En este tutorial ha implementado una aplicación de .NET para Apache Spark en Databricks.</span><span class="sxs-lookup"><span data-stu-id="a5a80-173">In this tutorial, you deployed your .NET for Apache Spark application to Databricks.</span></span> <span data-ttu-id="a5a80-174">Para más información sobre Databricks, prosiga con la documentación de Azure Databricks.</span><span class="sxs-lookup"><span data-stu-id="a5a80-174">To learn more about Databricks, continue to the Azure Databricks Documentation.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a5a80-175">Documentación de Azure Databricks</span><span class="sxs-lookup"><span data-stu-id="a5a80-175">Azure Databricks Documentation</span></span>](https://docs.microsoft.com/azure/azure-databricks/)
