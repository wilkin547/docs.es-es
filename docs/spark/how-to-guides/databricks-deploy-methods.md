---
title: Envío de un trabajo de .NET para Apache Spark a Databricks
description: Aprenda a enviar un trabajo de .NET para Apache Spark a Databricks mediante spark-submit y Set Jar.
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: fd04f78c47b34ca07042a4e60e2214f5f1ecac55
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2020
ms.locfileid: "91955002"
---
# <a name="submit-a-net-for-apache-spark-job-to-databricks"></a><span data-ttu-id="594cc-103">Envío de un trabajo de .NET para Apache Spark a Databricks</span><span class="sxs-lookup"><span data-stu-id="594cc-103">Submit a .NET for Apache Spark job to Databricks</span></span>

<span data-ttu-id="594cc-104">Aunque puede ejecutar .NET para trabajos de Apache Spark en clústeres de Databricks, no está disponible de forma integrada.</span><span class="sxs-lookup"><span data-stu-id="594cc-104">You can run your .NET for Apache Spark jobs on Databricks clusters, but it is not available out-of-the-box.</span></span> <span data-ttu-id="594cc-105">Hay dos maneras de implementar un trabajo de .NET para Apache Spark en Databricks: `spark-submit` y Set Jar.</span><span class="sxs-lookup"><span data-stu-id="594cc-105">There are two ways to deploy your .NET for Apache Spark job to Databricks: `spark-submit` and Set Jar.</span></span>

## <a name="deploy-using-spark-submit"></a><span data-ttu-id="594cc-106">Implementación mediante spark-submit</span><span class="sxs-lookup"><span data-stu-id="594cc-106">Deploy using spark-submit</span></span>

<span data-ttu-id="594cc-107">Puede usar el comando [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) para enviar trabajos de .NET para Apache Spark a Databricks.</span><span class="sxs-lookup"><span data-stu-id="594cc-107">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Databricks.</span></span> <span data-ttu-id="594cc-108">`spark-submit` permite el envío solo a un clúster que se crea a petición.</span><span class="sxs-lookup"><span data-stu-id="594cc-108">`spark-submit` allows submission only to a cluster that gets created on-demand.</span></span>

1. <span data-ttu-id="594cc-109">Vaya al área de trabajo de Databricks y cree un trabajo.</span><span class="sxs-lookup"><span data-stu-id="594cc-109">Navigate to your Databricks Workspace and create a job.</span></span> <span data-ttu-id="594cc-110">Elija un título para el trabajo y luego seleccione **Configurar spark-submit**.</span><span class="sxs-lookup"><span data-stu-id="594cc-110">Choose a title for your job, and then select **Configure spark-submit**.</span></span> <span data-ttu-id="594cc-111">Pegue los parámetros siguientes en la configuración del trabajo y seleccione **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="594cc-111">Paste the following parameters in the job configuration, then select **Confirm**.</span></span>

    ```
    ["--files","/dbfs/<path-to>/<app assembly/file to deploy to worker>","--class","org.apache.spark.deploy.dotnet.DotnetRunner","/dbfs/<path-to>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar","/dbfs/<path-to>/<app name>.zip","<app bin name>","app arg1","app arg2"]
    ```

    > [!NOTE]
    > <span data-ttu-id="594cc-112">Actualice el contenido del parámetro anterior en función de los archivos y la configuración específicos.</span><span class="sxs-lookup"><span data-stu-id="594cc-112">Update the contents of the above parameter based on your specific files and configuration.</span></span> <span data-ttu-id="594cc-113">Por ejemplo, haga referencia a la versión del archivo jar Microsoft.Spark que cargó en DBFS y use el nombre adecuado de la aplicación y el archivo zip de la aplicación publicada.</span><span class="sxs-lookup"><span data-stu-id="594cc-113">For instance, reference the version of the Microsoft.Spark jar file that you uploaded to DBFS, and use the appropriate name of your app and published app zip file.</span></span>

2. <span data-ttu-id="594cc-114">Vaya a su trabajo y seleccione **Editar** para configurar el clúster del trabajo.</span><span class="sxs-lookup"><span data-stu-id="594cc-114">Navigate to your job and select **Edit** to configure your job's cluster.</span></span> <span data-ttu-id="594cc-115">Establezca la versión de Databricks Runtime en función de la versión de Apache Spark que desea usar en la implementación.</span><span class="sxs-lookup"><span data-stu-id="594cc-115">Set the Databricks Runtime Version based on the version of Apache Spark you wish to use in your deployment.</span></span> <span data-ttu-id="594cc-116">A continuación, seleccione **Advanced Options > Init Scripts** (Opciones avanzadas > Scripts init) y establezca la ruta de acceso del script init como `dbfs:/spark-dotnet/db-init.sh`.</span><span class="sxs-lookup"><span data-stu-id="594cc-116">Then select **Advanced Options > Init Scripts**, and set Init Script Path as `dbfs:/spark-dotnet/db-init.sh`.</span></span> <span data-ttu-id="594cc-117">Seleccione **Confirmar** para confirmar la configuración del clúster.</span><span class="sxs-lookup"><span data-stu-id="594cc-117">Select **Confirm** to confirm your cluster settings.</span></span>

3. <span data-ttu-id="594cc-118">Vaya a su trabajo y seleccione **Ejecutar ahora** para ejecutar el trabajo en el clúster de Spark recientemente configurado.</span><span class="sxs-lookup"><span data-stu-id="594cc-118">Navigate to your job and select **Run Now** to run your job on your newly configured Spark cluster.</span></span> <span data-ttu-id="594cc-119">La creación del clúster del trabajo tarda unos minutos.</span><span class="sxs-lookup"><span data-stu-id="594cc-119">It takes a few minutes for the job's cluster to be created.</span></span> <span data-ttu-id="594cc-120">Una vez creado, se enviará el trabajo.</span><span class="sxs-lookup"><span data-stu-id="594cc-120">Once it is created, your job will be submitted.</span></span> <span data-ttu-id="594cc-121">Para ver la salida, seleccione **Clústeres** en el menú de la izquierda del área de trabajo del área de trabajo de Databricks y, después, elija **Driver Logs** (Registros de controladores).</span><span class="sxs-lookup"><span data-stu-id="594cc-121">You can view the output by selecting **Clusters** from the left menu of your Databricks workspace, then select **Driver Logs**.</span></span>

## <a name="deploy-using-set-jar"></a><span data-ttu-id="594cc-122">Implementación mediante Set Jar</span><span class="sxs-lookup"><span data-stu-id="594cc-122">Deploy using Set Jar</span></span>

<span data-ttu-id="594cc-123">Como alternativa, puede usar [Set Jar](/azure/databricks/jobs#--create-a-job) en el área de trabajo de Databricks para enviar trabajos de .NET para Apache Spark a Databricks.</span><span class="sxs-lookup"><span data-stu-id="594cc-123">Alternatively, you can use [Set Jar](/azure/databricks/jobs#--create-a-job) in your Databricks workspace to submit .NET for Apache Spark jobs to Databricks.</span></span> <span data-ttu-id="594cc-124">*Set Jar* permite el envío de trabajos a clústeres activos.</span><span class="sxs-lookup"><span data-stu-id="594cc-124">*Set Jar* allows job submission to an existing active cluster.</span></span>

### <a name="one-time-setup"></a><span data-ttu-id="594cc-125">Instalación única</span><span class="sxs-lookup"><span data-stu-id="594cc-125">One-time setup</span></span>

1. <span data-ttu-id="594cc-126">Vaya al clúster de Databricks y seleccione **Trabajos** en el menú de la izquierda y, después, en **Set JAR**.</span><span class="sxs-lookup"><span data-stu-id="594cc-126">Navigate to your Databricks cluster and select **Jobs** from the left-side menu, followed by **Set JAR**.</span></span>

2. <span data-ttu-id="594cc-127">Cargue el archivo `microsoft-spark-<spark-version>-<spark-dotnet-version>.jar` adecuado.</span><span class="sxs-lookup"><span data-stu-id="594cc-127">Upload the appropriate `microsoft-spark-<spark-version>-<spark-dotnet-version>.jar`.</span></span>

3. <span data-ttu-id="594cc-128">Modifique los parámetros siguientes para incluir el nombre correcto del archivo ejecutable que publicó en lugar de `<your-app-name>`:</span><span class="sxs-lookup"><span data-stu-id="594cc-128">Modify the following parameters to include the correct name for the executable that you published in place of `<your-app-name>`:</span></span>

    ```
    Main Class: org.apache.spark.deploy.dotnet.DotnetRunner
    Arguments /dbfs/apps/<your-app-name>.zip <your-app-name>
    ```

4. <span data-ttu-id="594cc-129">Configure el clúster para que apunte a un clúster para el que ya ha establecido el script init.</span><span class="sxs-lookup"><span data-stu-id="594cc-129">Configure the cluster to point to an existing cluster for which you have already set the init script.</span></span>

### <a name="publish-and-run-your-app"></a><span data-ttu-id="594cc-130">Publicación y ejecución de la aplicación</span><span class="sxs-lookup"><span data-stu-id="594cc-130">Publish and run your app</span></span>

1. <span data-ttu-id="594cc-131">Asegúrese de que ha publicado la aplicación y de que el código de aplicación no usa `SparkSession.Stop()`.</span><span class="sxs-lookup"><span data-stu-id="594cc-131">Ensure you have published your app, and that your application code does not use `SparkSession.Stop()`.</span></span>

2. <span data-ttu-id="594cc-132">Use la [CLI de Databricks](/azure/databricks/dev-tools/databricks-cli) para cargar la aplicación en el clúster de Databricks.</span><span class="sxs-lookup"><span data-stu-id="594cc-132">Use [Databricks CLI](/azure/databricks/dev-tools/databricks-cli) to upload your application to your Databricks cluster.</span></span> <span data-ttu-id="594cc-133">Por ejemplo, use el siguiente comando para cargar la aplicación publicada en el clúster:</span><span class="sxs-lookup"><span data-stu-id="594cc-133">For example, use the following command to upload your published app to your cluster:</span></span>

    ```console
    cd <path-to-your-app-publish-directory>
    databricks fs cp <your-app-name>.zip dbfs:/apps/<your-app-name>.zip
    ```

3. <span data-ttu-id="594cc-134">Si tiene funciones definidas por el usuario en la aplicación, sus ensamblados (por ejemplo, los archivos DLL que contienen funciones definidas por el usuario junto con sus dependencias) deben colocarse en el directorio de trabajo de cada *Microsoft.Spark.Worker*.</span><span class="sxs-lookup"><span data-stu-id="594cc-134">If you have any user-defined functions in your app, the app assemblies, such as DLLs that contain user-defined functions along with their dependencies, need to be placed in the working directory of each *Microsoft.Spark.Worker*.</span></span>

    <span data-ttu-id="594cc-135">Carga de los ensamblados de la aplicación en el clúster de Databricks:</span><span class="sxs-lookup"><span data-stu-id="594cc-135">Upload your application assemblies to your Databricks cluster:</span></span>

    ```console
    cd <path-to-your-app-publish-directory>
    databricks fs cp <assembly>.dll dbfs:/apps/dependencies
    ```

    <span data-ttu-id="594cc-136">Quite la marca de comentario y modifique la sección de dependencias de la aplicación en [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) para que apunte a la ruta de acceso de las dependencias de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="594cc-136">Uncomment and modify the app dependencies section in [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) to point to your app dependencies path.</span></span> <span data-ttu-id="594cc-137">A continuación, cargue el archivo *db-init.sh* actualizado en el clúster:</span><span class="sxs-lookup"><span data-stu-id="594cc-137">Then, upload the updated *db-init.sh* to your cluster:</span></span>

    ```console
    cd <path-to-db-init-and-install-worker>
    databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
    ```

4. <span data-ttu-id="594cc-138">Vaya a **Databricks cluster > Jobs > [Job-name] > Run Now** (Clúster de Databricks > Trabajos [nombre del trabajo] > Ejecutar ahora) para ejecutar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="594cc-138">Navigate to **Databricks cluster > Jobs > [Job-name] > Run Now** to run your job.</span></span>

## <a name="next-steps"></a><span data-ttu-id="594cc-139">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="594cc-139">Next steps</span></span>

* [<span data-ttu-id="594cc-140">Introducción a .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="594cc-140">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
* [<span data-ttu-id="594cc-141">Implementación de una aplicación de .NET para Apache Spark en Databricks</span><span class="sxs-lookup"><span data-stu-id="594cc-141">Deploy a .NET for Apache Spark application to Databricks</span></span>](../tutorials/databricks-deployment.md)
* [<span data-ttu-id="594cc-142">Documentación de Azure Databricks</span><span class="sxs-lookup"><span data-stu-id="594cc-142">Azure Databricks Documentation</span></span>](/azure/azure-databricks/)
