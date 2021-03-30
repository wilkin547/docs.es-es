---
title: Implementación de una aplicación de .NET para Apache Spark en Databricks
description: Sepa cómo implementar una aplicación de .NET para Apache Spark en Databricks.
ms.date: 10/09/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: e751953937279a5f9f78f777bac8a5ca510a2f87
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104876973"
---
# <a name="tutorial-deploy-a-net-for-apache-spark-application-to-databricks"></a><span data-ttu-id="95305-103">Tutorial: Implementación de una aplicación de .NET para Apache Spark en Databricks</span><span class="sxs-lookup"><span data-stu-id="95305-103">Tutorial: Deploy a .NET for Apache Spark application to Databricks</span></span>

<span data-ttu-id="95305-104">En este tutorial se enseña cómo implementar la aplicación en la nube a través de Azure Databricks, una plataforma de análisis basada en Apache Spark que ofrece una configuración de un clic, simplifica los flujos de trabajo y ofrece un área de trabajo interactivo que permite la colaboración.</span><span class="sxs-lookup"><span data-stu-id="95305-104">This tutorial teaches you how to deploy your app to the cloud through Azure Databricks, an Apache Spark-based analytics platform with one-click setup, streamlined workflows, and interactive workspace that enables collaboration.</span></span>

<span data-ttu-id="95305-105">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="95305-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="95305-106">Crear un área de trabajo de Azure Databricks.</span><span class="sxs-lookup"><span data-stu-id="95305-106">Create an Azure Databricks workspace.</span></span>
> - <span data-ttu-id="95305-107">Publicar la aplicación de .NET para Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="95305-107">Publish your .NET for Apache Spark app.</span></span>
> - <span data-ttu-id="95305-108">Crear un trabajo y un clúster de Spark.</span><span class="sxs-lookup"><span data-stu-id="95305-108">Create a Spark job and Spark cluster.</span></span>
> - <span data-ttu-id="95305-109">Ejecutar la aplicación en el clúster de Spark.</span><span class="sxs-lookup"><span data-stu-id="95305-109">Run your app on the Spark cluster.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="95305-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="95305-110">Prerequisites</span></span>

<span data-ttu-id="95305-111">Antes de empezar, haga las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="95305-111">Before you start, do the following tasks:</span></span>

* <span data-ttu-id="95305-112">Si no tiene una cuenta de Azure, cree una [cuenta gratuita](https://azure.microsoft.com/free/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="95305-112">If you don't have an Azure account, create a [free account](https://azure.microsoft.com/free/dotnet/).</span></span>
* <span data-ttu-id="95305-113">Inicie sesión en [Azure Portal](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="95305-113">Sign in to the [Azure portal](https://portal.azure.com/).</span></span>
* <span data-ttu-id="95305-114">Complete el tutorial [.NET para Apache Spark: comenzar en 10 minutos](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro).</span><span class="sxs-lookup"><span data-stu-id="95305-114">Complete the [.NET for Apache Spark - Get Started in 10-Minutes](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) tutorial.</span></span>

## <a name="create-an-azure-databricks-workspace"></a><span data-ttu-id="95305-115">Creación de un área de trabajo de Azure Databricks</span><span class="sxs-lookup"><span data-stu-id="95305-115">Create an Azure Databricks workspace</span></span>

> [!Note]
> <span data-ttu-id="95305-116">Este tutorial no puede llevarse a cabo mediante una **suscripción de evaluación gratuita de Azure**.</span><span class="sxs-lookup"><span data-stu-id="95305-116">This tutorial cannot be carried out using **Azure Free Trial Subscription**.</span></span>
> <span data-ttu-id="95305-117">Si tiene una cuenta gratuita, vaya a su perfil y cambiar la suscripción a **pago por uso**.</span><span class="sxs-lookup"><span data-stu-id="95305-117">If you have a free account, go to your profile and change your subscription to **pay-as-you-go**.</span></span> <span data-ttu-id="95305-118">Para más información consulte el sitio de [cuentas gratuitas de Azure](https://azure.microsoft.com/free/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="95305-118">For more information, see [Azure free account](https://azure.microsoft.com/free/dotnet/).</span></span> <span data-ttu-id="95305-119">Después, [quite el límite de gasto](/azure/billing/billing-spending-limit#why-you-might-want-to-remove-the-spending-limit) y [solicite un aumento de la cuota](/azure/azure-supportability/resource-manager-core-quotas-request) para las vCPU de su región.</span><span class="sxs-lookup"><span data-stu-id="95305-119">Then, [remove the spending limit](/azure/billing/billing-spending-limit#why-you-might-want-to-remove-the-spending-limit), and [request a quota increase](/azure/azure-supportability/resource-manager-core-quotas-request) for vCPUs in your region.</span></span> <span data-ttu-id="95305-120">Cuando crea su área de trabajo de Azure Databricks, puede seleccionar el plan de tarifa de la **Trial (Premium - 14-Days Free DBUs)** para que el área de trabajo acceda a las DBU Premium de Azure Databricks gratis durante 14 días.</span><span class="sxs-lookup"><span data-stu-id="95305-120">When you create your Azure Databricks workspace, you can select the **Trial (Premium - 14-Days Free DBUs)** pricing tier to give the workspace access to free Premium Azure Databricks DBUs for 14 days.</span></span>

<span data-ttu-id="95305-121">En esta sección, creará un área de trabajo de Azure Databricks mediante Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="95305-121">In this section, you create an Azure Databricks workspace using the Azure portal.</span></span>

1. <span data-ttu-id="95305-122">En Azure Portal, seleccione **Crear un recurso** > **Análisis** > **Azure Databricks**.</span><span class="sxs-lookup"><span data-stu-id="95305-122">In the Azure portal, select **Create a resource** > **Analytics** > **Azure Databricks**.</span></span>

   ![Creación de un recurso de Azure Databricks en Azure Portal](./media/databricks-deployment/create-databricks-resource.png)

2. <span data-ttu-id="95305-124">En **Azure Databricks Service**, proporcione los valores para crear un área de trabajo de Databricks.</span><span class="sxs-lookup"><span data-stu-id="95305-124">Under **Azure Databricks Service**, provide the values to create a Databricks workspace.</span></span>

    |<span data-ttu-id="95305-125">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="95305-125">Property</span></span>  |<span data-ttu-id="95305-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="95305-126">Description</span></span>  |
    |---------|---------|
    |<span data-ttu-id="95305-127">**Workspace name** (Nombre del área de trabajo)</span><span class="sxs-lookup"><span data-stu-id="95305-127">**Workspace name**</span></span>     | <span data-ttu-id="95305-128">Proporcione un nombre para el área de trabajo de Databricks.</span><span class="sxs-lookup"><span data-stu-id="95305-128">Provide a name for your Databricks workspace.</span></span>        |
    |<span data-ttu-id="95305-129">**Suscripción**</span><span class="sxs-lookup"><span data-stu-id="95305-129">**Subscription**</span></span>     | <span data-ttu-id="95305-130">En el cuadro desplegable, seleccione la suscripción de Azure.</span><span class="sxs-lookup"><span data-stu-id="95305-130">From the drop-down, select your Azure subscription.</span></span>        |
    |<span data-ttu-id="95305-131">**Grupos de recursos**</span><span class="sxs-lookup"><span data-stu-id="95305-131">**Resource group**</span></span>     | <span data-ttu-id="95305-132">Especifique si desea crear un nuevo grupo de recursos o utilizar uno existente.</span><span class="sxs-lookup"><span data-stu-id="95305-132">Specify whether you want to create a new resource group or use an existing one.</span></span> <span data-ttu-id="95305-133">Un grupo de recursos es un contenedor que almacena los recursos relacionados con una solución de Azure.</span><span class="sxs-lookup"><span data-stu-id="95305-133">A resource group is a container that holds related resources for an Azure solution.</span></span> <span data-ttu-id="95305-134">Para más información, consulte [Información general del grupo de recursos de Azure](/azure/azure-resource-manager/resource-group-overview).</span><span class="sxs-lookup"><span data-stu-id="95305-134">For more information, see [Azure Resource Group overview](/azure/azure-resource-manager/resource-group-overview).</span></span> |
    |<span data-ttu-id="95305-135">**Ubicación**</span><span class="sxs-lookup"><span data-stu-id="95305-135">**Location**</span></span>     | <span data-ttu-id="95305-136">Seleccione su región preferida.</span><span class="sxs-lookup"><span data-stu-id="95305-136">Select your preferred region.</span></span> <span data-ttu-id="95305-137">Para obtener información sobre las regiones disponibles, consulte [Servicios de Azure disponibles por región](https://azure.microsoft.com/regions/services/).</span><span class="sxs-lookup"><span data-stu-id="95305-137">For information about available regions, see [Azure services available by region](https://azure.microsoft.com/regions/services/).</span></span>        |
    |<span data-ttu-id="95305-138">**Plan de tarifa**</span><span class="sxs-lookup"><span data-stu-id="95305-138">**Pricing Tier**</span></span>     |  <span data-ttu-id="95305-139">Elija entre **Estándar**, **Premium** o **Evaluación gratuita**.</span><span class="sxs-lookup"><span data-stu-id="95305-139">Choose between **Standard**, **Premium**, or **Trial**.</span></span> <span data-ttu-id="95305-140">Para más información sobre estos planes, consulte la [página de precios de Databricks](https://azure.microsoft.com/pricing/details/databricks/).</span><span class="sxs-lookup"><span data-stu-id="95305-140">For more information on these tiers, see [Databricks pricing page](https://azure.microsoft.com/pricing/details/databricks/).</span></span>       |
    |<span data-ttu-id="95305-141">**Virtual Network**</span><span class="sxs-lookup"><span data-stu-id="95305-141">**Virtual Network**</span></span>     |   <span data-ttu-id="95305-142">No</span><span class="sxs-lookup"><span data-stu-id="95305-142">No</span></span>       |

3. <span data-ttu-id="95305-143">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="95305-143">Select **Create**.</span></span> <span data-ttu-id="95305-144">Se tarda unos minutos en crear el área de trabajo.</span><span class="sxs-lookup"><span data-stu-id="95305-144">The workspace creation takes a few minutes.</span></span> <span data-ttu-id="95305-145">Durante la creación del área de trabajo, puede ver el estado de implementación en **Notificaciones**.</span><span class="sxs-lookup"><span data-stu-id="95305-145">During workspace creation, you can view the deployment status in **Notifications**.</span></span>

## <a name="install-azure-databricks-tools"></a><span data-ttu-id="95305-146">Instalación de las herramientas de Azure Databricks</span><span class="sxs-lookup"><span data-stu-id="95305-146">Install Azure Databricks tools</span></span>

<span data-ttu-id="95305-147">Puede usar la **CLI de Databricks** para conectarse a los clústeres de Azure Databricks y cargar archivos en ellos desde la máquina local.</span><span class="sxs-lookup"><span data-stu-id="95305-147">You can use the **Databricks CLI** to connect to Azure Databricks clusters and upload files to them from your local machine.</span></span> <span data-ttu-id="95305-148">Los clústeres de Databricks tienen acceso a archivos a través del DBFS (Sistema de archivos de Databricks).</span><span class="sxs-lookup"><span data-stu-id="95305-148">Databricks clusters access files through DBFS (Databricks File System).</span></span>

1. <span data-ttu-id="95305-149">La CLI de Databricks requiere Python 3.6 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="95305-149">The Databricks CLI requires Python 3.6 or above.</span></span> <span data-ttu-id="95305-150">Si ya tiene Python instalado, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="95305-150">If you already have Python installed, you can skip this step.</span></span>

   <span data-ttu-id="95305-151">**Para Windows**:</span><span class="sxs-lookup"><span data-stu-id="95305-151">**For Windows:**</span></span>

   [<span data-ttu-id="95305-152">Descargar Python para Windows</span><span class="sxs-lookup"><span data-stu-id="95305-152">Download Python for Windows</span></span>](https://www.python.org/ftp/python/3.7.4/python-3.7.4.exe)

   <span data-ttu-id="95305-153">**Para Linux:** Python viene preinstalado en la mayoría de las distribuciones de Linux.</span><span class="sxs-lookup"><span data-stu-id="95305-153">**For Linux:** Python comes preinstalled on most Linux distributions.</span></span> <span data-ttu-id="95305-154">Ejecute el comando siguiente para ver la versión que se ha instalado:</span><span class="sxs-lookup"><span data-stu-id="95305-154">Run the following command to see which version you have installed:</span></span>

   ```bash
   python3 --version
   ```

2. <span data-ttu-id="95305-155">Use pip para instalar la CLI de Databricks.</span><span class="sxs-lookup"><span data-stu-id="95305-155">Use pip to install the Databricks CLI.</span></span> <span data-ttu-id="95305-156">Python 3.4 y las versiones posteriores incluyen pip de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="95305-156">Python 3.4 and later include pip by default.</span></span> <span data-ttu-id="95305-157">Use pip3 para Python 3.</span><span class="sxs-lookup"><span data-stu-id="95305-157">Use pip3 for Python 3.</span></span> <span data-ttu-id="95305-158">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="95305-158">Run the following command:</span></span>

   ```bash
   pip3 install databricks-cli
   ```

3. <span data-ttu-id="95305-159">Una vez instalada la CLI de Databricks, abra un símbolo del sistema nuevo y ejecute el comando `databricks`.</span><span class="sxs-lookup"><span data-stu-id="95305-159">Once you've installed the Databricks CLI, open a new command prompt and run the command `databricks`.</span></span> <span data-ttu-id="95305-160">Si recibe un aviso **"databricks" no se reconoce como un error de comando interno o externo**, asegúrese de que ha abierto un símbolo del sistema nuevo.</span><span class="sxs-lookup"><span data-stu-id="95305-160">If you receive a **'databricks' is not recognized as an internal or external command error**, make sure you opened a new command prompt.</span></span>

## <a name="set-up-azure-databricks"></a><span data-ttu-id="95305-161">Configuración de Azure Databricks</span><span class="sxs-lookup"><span data-stu-id="95305-161">Set up Azure Databricks</span></span>

<span data-ttu-id="95305-162">Ahora que tiene la CLI de Databricks instalada, debe configurar los detalles de autenticación.</span><span class="sxs-lookup"><span data-stu-id="95305-162">Now that you have the Databricks CLI installed, you need to set up authentication details.</span></span>

1. <span data-ttu-id="95305-163">Ejecute el comando `databricks configure --token` de la CLI de Databricks.</span><span class="sxs-lookup"><span data-stu-id="95305-163">Run the Databricks CLI command `databricks configure --token`.</span></span>

2. <span data-ttu-id="95305-164">Después de ejecutar el comando de configuración, se le pedirá que escriba un host.</span><span class="sxs-lookup"><span data-stu-id="95305-164">After running the configure command, you are prompted to enter a host.</span></span> <span data-ttu-id="95305-165">La dirección URL del host usa el formato: `https://<Location>.azuredatabricks.net`.</span><span class="sxs-lookup"><span data-stu-id="95305-165">Your host URL uses the format: `https://<Location>.azuredatabricks.net`.</span></span> <span data-ttu-id="95305-166">Por ejemplo, si ha seleccionado **eastus2** durante la creación del Servicio de Azure Databricks, el host sería `https://eastus2.azuredatabricks.net`.</span><span class="sxs-lookup"><span data-stu-id="95305-166">For instance, if you selected **eastus2** during Azure Databricks Service creation, the host would be `https://eastus2.azuredatabricks.net`.</span></span>

3. <span data-ttu-id="95305-167">Después de escribir el host, se le pedirá que escriba un token.</span><span class="sxs-lookup"><span data-stu-id="95305-167">After entering your host, you are prompted to enter a token.</span></span> <span data-ttu-id="95305-168">En Azure Portal, seleccione **Iniciar área de trabajo** para iniciar el área de trabajo de Azure Databricks.</span><span class="sxs-lookup"><span data-stu-id="95305-168">In the Azure portal, select **Launch Workspace** to launch your Azure Databricks workspace.</span></span>

   ![Inicio del área de trabajo de Azure Databricks](./media/databricks-deployment/launch-databricks-workspace.png)

4. <span data-ttu-id="95305-170">En la página principal del área de trabajo, seleccione **Configuración de usuario**.</span><span class="sxs-lookup"><span data-stu-id="95305-170">On the home page of your workspace, select **User Settings**.</span></span>

   ![Configuración de usuario en el área de trabajo de Azure Databricks](./media/databricks-deployment/databricks-user-settings.png)

5. <span data-ttu-id="95305-172">En la página Configuración de usuario se puede generar un nuevo token.</span><span class="sxs-lookup"><span data-stu-id="95305-172">On the User Settings page, you can generate a new token.</span></span> <span data-ttu-id="95305-173">Copie el token generado y péguelo de nuevo en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="95305-173">Copy the generated token and paste it back into your command prompt.</span></span>

   ![Generación de un token de acceso nuevo en el área de trabajo de Azure Databricks](./media/databricks-deployment/generate-token.png)

<span data-ttu-id="95305-175">Ahora debería poder acceder a cualquier clúster de Azure Databricks que cree y cargar archivos en el DBFS.</span><span class="sxs-lookup"><span data-stu-id="95305-175">You should now be able to access any Azure Databricks clusters you create and upload files to the DBFS.</span></span>

## <a name="download-worker-dependencies"></a><span data-ttu-id="95305-176">Descarga de las dependencias de trabajo</span><span class="sxs-lookup"><span data-stu-id="95305-176">Download worker dependencies</span></span>

> [!Note]
> <span data-ttu-id="95305-177">Azure y AWS Databricks se basan en Linux.</span><span class="sxs-lookup"><span data-stu-id="95305-177">Azure and AWS Databricks are Linux-based.</span></span> <span data-ttu-id="95305-178">Por lo tanto, si está interesado en implementar la aplicación en Databricks, asegúrese de que la aplicación es compatible con .NET Standard y, asimismo, de que usa el compilador de .NET Core para compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="95305-178">Therefore, if you are interested in deploying your app to Databricks, make sure your app is .NET Standard compatible and that you use .NET Core compiler to compile your app.</span></span>

1. <span data-ttu-id="95305-179">Microsoft.Spark.Worker ayuda a Apache Spark a ejecutar la aplicación, como cualquier función definida por el usuario (UDF) que se haya escrito.</span><span class="sxs-lookup"><span data-stu-id="95305-179">Microsoft.Spark.Worker helps Apache Spark execute your app, such as any user-defined functions (UDFs) you may have written.</span></span> <span data-ttu-id="95305-180">Descargue [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases/download/v1.0.0/Microsoft.Spark.Worker.netcoreapp3.1.linux-x64-1.0.0.tar.gz).</span><span class="sxs-lookup"><span data-stu-id="95305-180">Download [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases/download/v1.0.0/Microsoft.Spark.Worker.netcoreapp3.1.linux-x64-1.0.0.tar.gz).</span></span>

2. <span data-ttu-id="95305-181">*install-worker.sh* es un script que permite copiar archivos dependientes de .NET para Apache Spark en los nodos del clúster.</span><span class="sxs-lookup"><span data-stu-id="95305-181">The *install-worker.sh* is a script that lets you copy .NET for Apache Spark dependent files into the nodes of your cluster.</span></span>

   <span data-ttu-id="95305-182">Cree un nuevo archivo llamado **install-worker.sh** en el equipo local y pegue el [contenido de install-worker.sh](https://raw.githubusercontent.com/dotnet/spark/main/deployment/install-worker.sh) que se encuentra en GitHub.</span><span class="sxs-lookup"><span data-stu-id="95305-182">Create a new file named **install-worker.sh** on your local computer, and paste the [install-worker.sh contents](https://raw.githubusercontent.com/dotnet/spark/main/deployment/install-worker.sh) located on GitHub.</span></span>

3. <span data-ttu-id="95305-183">*db-init.sh* es un script que instala las dependencias en el clúster de Spark de Databricks.</span><span class="sxs-lookup"><span data-stu-id="95305-183">The *db-init.sh* is a script that installs dependencies onto your Databricks Spark cluster.</span></span>

   <span data-ttu-id="95305-184">Cree un nuevo archivo llamado **db-init.sh** en el equipo local y pegue el [contenido de db-init.sh](https://github.com/dotnet/spark/blob/main/deployment/db-init.sh) que se encuentra en GitHub.</span><span class="sxs-lookup"><span data-stu-id="95305-184">Create a new file named **db-init.sh** on your local computer, and paste the [db-init.sh contents](https://github.com/dotnet/spark/blob/main/deployment/db-init.sh) located on GitHub.</span></span>

   <span data-ttu-id="95305-185">En el archivo que se acaba de crear, establezca la variable `DOTNET_SPARK_RELEASE` en `https://github.com/dotnet/spark/releases/download/v1.0.0/Microsoft.Spark.Worker.netcoreapp3.1.linux-x64-1.0.0.tar.gz`.</span><span class="sxs-lookup"><span data-stu-id="95305-185">In the file you just created, set the `DOTNET_SPARK_RELEASE` variable to `https://github.com/dotnet/spark/releases/download/v1.0.0/Microsoft.Spark.Worker.netcoreapp3.1.linux-x64-1.0.0.tar.gz`.</span></span> <span data-ttu-id="95305-186">Deje el resto del archivo *db-init.sh* tal cual.</span><span class="sxs-lookup"><span data-stu-id="95305-186">Leave the rest of the *db-init.sh* file as-is.</span></span>

> [!Note]
> <span data-ttu-id="95305-187">Si usa Windows, compruebe que los fines de línea de los scripts *install-worker.sh* y *db-init.sh* son de estilo Unix (LF).</span><span class="sxs-lookup"><span data-stu-id="95305-187">If you are using Windows, verify that the line-endings in your *install-worker.sh* and *db-init.sh* scripts are Unix-style (LF).</span></span> <span data-ttu-id="95305-188">Se pueden cambiar los fines de línea a través de los editores de texto como Notepad++ y Atom.</span><span class="sxs-lookup"><span data-stu-id="95305-188">You can change line endings through text editors like Notepad++ and Atom.</span></span>

## <a name="publish-your-app"></a><span data-ttu-id="95305-189">Publicar la aplicación</span><span class="sxs-lookup"><span data-stu-id="95305-189">Publish your app</span></span>

<span data-ttu-id="95305-190">Luego, publique la aplicación *mySparkApp* creada en el tutorial [.NET para Apache Spark: comenzar en 10 minutos](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) para asegurarse de que el clúster de Spark tiene acceso a todos los archivos que necesita para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="95305-190">Next, you publish the *mySparkApp* created in the [.NET for Apache Spark - Get Started in 10-Minutes](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) tutorial to ensure your Spark cluster has access to all the files it needs to run your app.</span></span>

1. <span data-ttu-id="95305-191">Para publicar *mySparkApp*, ejecute los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="95305-191">Run the following commands to publish the *mySparkApp*:</span></span>

   ```dotnetcli
   cd mySparkApp
   dotnet publish -c Release -f netcoreapp3.1 -r ubuntu.16.04-x64
   ```

2. <span data-ttu-id="95305-192">Realice las tareas siguientes para comprimir los archivos de la aplicación publicados para que pueda cargarlos fácilmente en el clúster de Spark de Databricks.</span><span class="sxs-lookup"><span data-stu-id="95305-192">Do the following tasks to zip your published app files so that you can easily upload them to your Databricks Spark cluster.</span></span>

   <span data-ttu-id="95305-193">**En Windows:**</span><span class="sxs-lookup"><span data-stu-id="95305-193">**On Windows:**</span></span>

   <span data-ttu-id="95305-194">Vaya a mySparkApp/bin/Release/netcoreapp3.1/ubuntu.16.04-x64.</span><span class="sxs-lookup"><span data-stu-id="95305-194">Navigate to mySparkApp/bin/Release/netcoreapp3.1/ubuntu.16.04-x64.</span></span> <span data-ttu-id="95305-195">Luego, haga clic con el botón derecho en la carpeta **Publicar** y seleccione **Enviar a > Carpeta comprimida (en zip)** .</span><span class="sxs-lookup"><span data-stu-id="95305-195">Then, right-click on **Publish** folder and select **Send to > Compressed (zipped) folder**.</span></span> <span data-ttu-id="95305-196">Asigne el nombre **publish.zip** a la carpeta nueva.</span><span class="sxs-lookup"><span data-stu-id="95305-196">Name the new folder **publish.zip**.</span></span>

   <span data-ttu-id="95305-197">**En Linux, ejecute el comando siguiente:**</span><span class="sxs-lookup"><span data-stu-id="95305-197">**On Linux, run the following command:**</span></span>

   ```bash
   zip -r publish.zip .
   ```

## <a name="upload-files"></a><span data-ttu-id="95305-198">Carga de archivos</span><span class="sxs-lookup"><span data-stu-id="95305-198">Upload files</span></span>

<span data-ttu-id="95305-199">En esta sección, se cargan varios archivos en el DBFS con el fin de que el clúster tenga todo lo necesario para ejecutar la aplicación en la nube.</span><span class="sxs-lookup"><span data-stu-id="95305-199">In this section, you upload several files to DBFS so that your cluster has everything it needs to run your app in the cloud.</span></span> <span data-ttu-id="95305-200">Cada vez que cargue un archivo en el DBFS, asegúrese de que está en el directorio en el que se encuentra el archivo en el equipo.</span><span class="sxs-lookup"><span data-stu-id="95305-200">Each time you upload a file to the DBFS, make sure you are in the directory where that file is located on your computer.</span></span>

1. <span data-ttu-id="95305-201">Ejecute los siguientes comandos para cargar *db-init.sh*, *install-worker.sh* y *Microsoft.Spark.Worker* en DBFS:</span><span class="sxs-lookup"><span data-stu-id="95305-201">Run the following commands to upload the *db-init.sh*, *install-worker.sh*, and *Microsoft.Spark.Worker* to DBFS:</span></span>

   ```console
   databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
   databricks fs cp install-worker.sh dbfs:/spark-dotnet/install-worker.sh
   databricks fs cp Microsoft.Spark.Worker.netcoreapp3.1.linux-x64-1.0.0.tar.gz dbfs:/spark-dotnet/Microsoft.Spark.Worker.netcoreapp3.1.linux-x64-1.0.0.tar.gz
   ```

2. <span data-ttu-id="95305-202">Ejecute los comandos siguientes para cargar los archivos restantes que el clúster necesitará para ejecutar la aplicación: la carpeta de publicación comprimida, *input.txt* y *microsoft-spark-2-4_2.11-1.0.0.jar*.</span><span class="sxs-lookup"><span data-stu-id="95305-202">Run the following commands to upload the remaining files your cluster will need to run your app: the zipped publish folder, *input.txt*, and *microsoft-spark-2-4_2.11-1.0.0.jar*.</span></span>

   ```console
   cd mySparkApp
   databricks fs cp input.txt dbfs:/input.txt

   cd mySparkApp\bin\Release\netcoreapp3.1\ubuntu.16.04-x64 directory
   databricks fs cp publish.zip dbfs:/spark-dotnet/publish.zip
   databricks fs cp microsoft-spark-2-4_2.11-1.0.0.jar dbfs:/spark-dotnet/microsoft-spark-2-4_2.11-1.0.0.jar
   ```

## <a name="create-a-job"></a><span data-ttu-id="95305-203">Creación de un trabajo</span><span class="sxs-lookup"><span data-stu-id="95305-203">Create a job</span></span>

<span data-ttu-id="95305-204">La aplicación se ejecuta en Azure Databricks a través de un trabajo que ejecuta **spark-submit**, que es el comando que se usa para ejecutar .NET para trabajos de Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="95305-204">Your app runs on Azure Databricks through a job that runs **spark-submit**, which is the command you use to run .NET for Apache Spark jobs.</span></span>

1. <span data-ttu-id="95305-205">En el área de trabajo de Azure Databricks, seleccione el icono de **Trabajos** y luego **+ Crear trabajo**.</span><span class="sxs-lookup"><span data-stu-id="95305-205">In your Azure Databricks Workspace, select the **Jobs** icon and then **+ Create Job**.</span></span>

   ![Creación de un trabajo de Azure Databricks](./media/databricks-deployment/create-job.png)

2. <span data-ttu-id="95305-207">Elija un título para el trabajo y luego seleccione **Configurar spark-submit**.</span><span class="sxs-lookup"><span data-stu-id="95305-207">Choose a title for your job, and then select **Configure spark-submit**.</span></span>

   ![Configuración de spark-submit para el trabajo de Databricks](./media/databricks-deployment/configure-spark-submit.png)

3. <span data-ttu-id="95305-209">Pegue los parámetros siguientes en la configuración del trabajo.</span><span class="sxs-lookup"><span data-stu-id="95305-209">Paste the following parameters in the job configuration.</span></span> <span data-ttu-id="95305-210">Después, seleccione **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="95305-210">Then, select **Confirm**.</span></span>

   ```
   ["--class","org.apache.spark.deploy.dotnet.DotnetRunner","/dbfs/spark-dotnet/microsoft-spark-2-4_2.11-1.0.0.jar","/dbfs/spark-dotnet/publish.zip","mySparkApp"]
   ```

## <a name="create-a-cluster"></a><span data-ttu-id="95305-211">Crear un clúster</span><span class="sxs-lookup"><span data-stu-id="95305-211">Create a cluster</span></span>

1. <span data-ttu-id="95305-212">Vaya a su trabajo y seleccione **Editar** para configurar el clúster del trabajo.</span><span class="sxs-lookup"><span data-stu-id="95305-212">Navigate to your job and select **Edit** to configure your job's cluster.</span></span>

2. <span data-ttu-id="95305-213">Establezca el clúster en **Spark 2.4.1**.</span><span class="sxs-lookup"><span data-stu-id="95305-213">Set your cluster to **Spark 2.4.1**.</span></span> <span data-ttu-id="95305-214">Luego, seleccione **Opciones avanzadas** > **Scripts Init**.</span><span class="sxs-lookup"><span data-stu-id="95305-214">Then, select **Advanced Options** > **Init Scripts**.</span></span> <span data-ttu-id="95305-215">Escriba la ruta de acceso del script Init como `dbfs:/spark-dotnet/db-init.sh`.</span><span class="sxs-lookup"><span data-stu-id="95305-215">Set Init Script Path as `dbfs:/spark-dotnet/db-init.sh`.</span></span>

   ![Configuración de un clúster de Spark en Azure Databricks](./media/databricks-deployment/cluster-config.png)

3. <span data-ttu-id="95305-217">Seleccione **Confirmar** para confirmar la configuración del clúster.</span><span class="sxs-lookup"><span data-stu-id="95305-217">Select **Confirm** to confirm your cluster settings.</span></span>

## <a name="run-your-app"></a><span data-ttu-id="95305-218">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="95305-218">Run your app</span></span>

1. <span data-ttu-id="95305-219">Vaya a su trabajo y seleccione **Ejecutar ahora** para ejecutar el trabajo en el clúster de Spark recientemente configurado.</span><span class="sxs-lookup"><span data-stu-id="95305-219">Navigate to your job and select **Run Now** to run your job on your newly configured Spark cluster.</span></span>

2. <span data-ttu-id="95305-220">La creación del clúster del trabajo tarda unos minutos.</span><span class="sxs-lookup"><span data-stu-id="95305-220">It takes a few minutes for the job's cluster to create.</span></span> <span data-ttu-id="95305-221">Una vez creado, se enviará el trabajo y podrá ver el resultado.</span><span class="sxs-lookup"><span data-stu-id="95305-221">Once it is created, your job will be submitted, and you can view the output.</span></span>

3. <span data-ttu-id="95305-222">Seleccione **Clústeres** en el menú de la izquierda y, después, el nombre y la ejecución del trabajo.</span><span class="sxs-lookup"><span data-stu-id="95305-222">Select **Clusters** from the left menu, and then the name and run of your job.</span></span>

4. <span data-ttu-id="95305-223">Seleccione **Registros de controladores** para ver la salida del trabajo.</span><span class="sxs-lookup"><span data-stu-id="95305-223">Select **Driver Logs** to view the output of your job.</span></span> <span data-ttu-id="95305-224">Cuando la aplicación termine de ejecutarse, verá la misma tabla de recuento de palabras de la ejecución local de introducción escrita en la consola de salida estándar.</span><span class="sxs-lookup"><span data-stu-id="95305-224">When your app finishes executing, you see the same word count table from the getting started local run written to the standard output console.</span></span>

   ![Tabla de salida del trabajo de Azure Databricks](./media/databricks-deployment/table-output.png)

   <span data-ttu-id="95305-226">Enhorabuena, ha ejecutado la primera aplicación de .NET para Apache Spark en Azure Databricks.</span><span class="sxs-lookup"><span data-stu-id="95305-226">Congratulations, you've run your first .NET for Apache Spark application in Azure Databricks!</span></span>

## <a name="clean-up-resources"></a><span data-ttu-id="95305-227">Limpiar los recursos</span><span class="sxs-lookup"><span data-stu-id="95305-227">Clean up resources</span></span>

<span data-ttu-id="95305-228">Si ya no necesita el área de trabajo de Databricks, puede eliminar el recurso Azure Databricks en Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="95305-228">If you no longer need the Databricks workspace, you can delete your Azure Databricks resource in the Azure portal.</span></span> <span data-ttu-id="95305-229">También puede seleccionar el nombre del grupo de recursos para abrir la página del grupo de recursos y, a continuación, seleccionar **Eliminar grupo de recursos**.</span><span class="sxs-lookup"><span data-stu-id="95305-229">You can also select the resource group name to open the resource group page, and then select **Delete resource group**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="95305-230">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="95305-230">Next steps</span></span>

<span data-ttu-id="95305-231">En este tutorial ha implementado una aplicación de .NET para Apache Spark en Databricks.</span><span class="sxs-lookup"><span data-stu-id="95305-231">In this tutorial, you deployed your .NET for Apache Spark application to Databricks.</span></span> <span data-ttu-id="95305-232">Para más información sobre Databricks, prosiga con la documentación de Azure Databricks.</span><span class="sxs-lookup"><span data-stu-id="95305-232">To learn more about Databricks, continue to the Azure Databricks Documentation.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="95305-233">Documentación de Azure Databricks</span><span class="sxs-lookup"><span data-stu-id="95305-233">Azure Databricks Documentation</span></span>](/azure/azure-databricks/)
