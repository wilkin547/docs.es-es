---
title: Implementación de una aplicación de .NET para Apache Spark en Databricks
description: Sepa cómo implementar una aplicación de .NET para Apache Spark en Databricks.
ms.date: 01/23/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 3b00823034cbcb271cb7e169df40122f1144462a
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895714"
---
# <a name="tutorial-deploy-a-net-for-apache-spark-application-to-databricks"></a><span data-ttu-id="57637-103">Tutorial: Implementación de una aplicación de .NET para Apache Spark en Databricks</span><span class="sxs-lookup"><span data-stu-id="57637-103">Tutorial: Deploy a .NET for Apache Spark application to Databricks</span></span>

<span data-ttu-id="57637-104">En este tutorial se enseña cómo implementar la aplicación en la nube a través de Azure Databricks, una plataforma de análisis basada en Apache Spark que ofrece una configuración de un clic, simplifica los flujos de trabajo y ofrece un área de trabajo interactivo que permite la colaboración.</span><span class="sxs-lookup"><span data-stu-id="57637-104">This tutorial teaches you how to deploy your app to the cloud through Azure Databricks, an Apache Spark-based analytics platform with one-click setup, streamlined workflows, and interactive workspace that enables collaboration.</span></span>

<span data-ttu-id="57637-105">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="57637-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="57637-106">Crear un área de trabajo de Azure Databricks.</span><span class="sxs-lookup"><span data-stu-id="57637-106">Create an Azure Databricks workspace.</span></span>
> - <span data-ttu-id="57637-107">Publicar la aplicación de .NET para Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="57637-107">Publish your .NET for Apache Spark app.</span></span>
> - <span data-ttu-id="57637-108">Crear un trabajo y un clúster de Spark.</span><span class="sxs-lookup"><span data-stu-id="57637-108">Create a Spark job and Spark cluster.</span></span>
> - <span data-ttu-id="57637-109">Ejecutar la aplicación en el clúster de Spark.</span><span class="sxs-lookup"><span data-stu-id="57637-109">Run your app on the Spark cluster.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="57637-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="57637-110">Prerequisites</span></span>

<span data-ttu-id="57637-111">Antes de empezar, haga las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="57637-111">Before you start, do the following tasks:</span></span>

* <span data-ttu-id="57637-112">Si no tiene una cuenta de Azure, cree una [cuenta gratuita](https://azure.microsoft.com/free/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="57637-112">If you don't have an Azure account, create a [free account](https://azure.microsoft.com/free/dotnet/).</span></span>
* <span data-ttu-id="57637-113">Inicie sesión en [Azure Portal](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="57637-113">Sign in to the [Azure portal](https://portal.azure.com/).</span></span>
* <span data-ttu-id="57637-114">Complete el tutorial [.NET para Apache Spark: comenzar en 10 minutos](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro).</span><span class="sxs-lookup"><span data-stu-id="57637-114">Complete the [.NET for Apache Spark - Get Started in 10-Minutes](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) tutorial.</span></span>

## <a name="create-an-azure-databricks-workspace"></a><span data-ttu-id="57637-115">Creación de un área de trabajo de Azure Databricks</span><span class="sxs-lookup"><span data-stu-id="57637-115">Create an Azure Databricks workspace</span></span>

> [!Note]
> <span data-ttu-id="57637-116">Este tutorial no puede llevarse a cabo mediante una **suscripción de evaluación gratuita de Azure**.</span><span class="sxs-lookup"><span data-stu-id="57637-116">This tutorial cannot be carried out using **Azure Free Trial Subscription**.</span></span>
> <span data-ttu-id="57637-117">Si tiene una cuenta gratuita, vaya a su perfil y cambiar la suscripción a **pago por uso**.</span><span class="sxs-lookup"><span data-stu-id="57637-117">If you have a free account, go to your profile and change your subscription to **pay-as-you-go**.</span></span> <span data-ttu-id="57637-118">Para más información consulte el sitio de [cuentas gratuitas de Azure](https://azure.microsoft.com/free/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="57637-118">For more information, see [Azure free account](https://azure.microsoft.com/free/dotnet/).</span></span> <span data-ttu-id="57637-119">Después, [quite el límite de gasto](https://docs.microsoft.com/azure/billing/billing-spending-limit#why-you-might-want-to-remove-the-spending-limit) y [solicite un aumento de la cuota](https://docs.microsoft.com/azure/azure-supportability/resource-manager-core-quotas-request) para las vCPU de su región.</span><span class="sxs-lookup"><span data-stu-id="57637-119">Then, [remove the spending limit](https://docs.microsoft.com/azure/billing/billing-spending-limit#why-you-might-want-to-remove-the-spending-limit), and [request a quota increase](https://docs.microsoft.com/azure/azure-supportability/resource-manager-core-quotas-request) for vCPUs in your region.</span></span> <span data-ttu-id="57637-120">Cuando crea su área de trabajo de Azure Databricks, puede seleccionar el plan de tarifa de la **Trial (Premium - 14-Days Free DBUs)** para que el área de trabajo acceda a las DBU Premium de Azure Databricks gratis durante 14 días.</span><span class="sxs-lookup"><span data-stu-id="57637-120">When you create your Azure Databricks workspace, you can select the **Trial (Premium - 14-Days Free DBUs)** pricing tier to give the workspace access to free Premium Azure Databricks DBUs for 14 days.</span></span>

<span data-ttu-id="57637-121">En esta sección, creará un área de trabajo de Azure Databricks mediante Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="57637-121">In this section, you create an Azure Databricks workspace using the Azure portal.</span></span>

1. <span data-ttu-id="57637-122">En Azure Portal, seleccione **Crear un recurso** > **Análisis** > **Azure Databricks**.</span><span class="sxs-lookup"><span data-stu-id="57637-122">In the Azure portal, select **Create a resource** > **Analytics** > **Azure Databricks**.</span></span>

   ![Creación de un recurso de Azure Databricks en Azure Portal](./media/databricks-deployment/create-databricks-resource.png)

2. <span data-ttu-id="57637-124">En **Azure Databricks Service**, proporcione los valores para crear un área de trabajo de Databricks.</span><span class="sxs-lookup"><span data-stu-id="57637-124">Under **Azure Databricks Service**, provide the values to create a Databricks workspace.</span></span>

    |<span data-ttu-id="57637-125">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="57637-125">Property</span></span>  |<span data-ttu-id="57637-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="57637-126">Description</span></span>  |
    |---------|---------|
    |<span data-ttu-id="57637-127">**Workspace name** (Nombre del área de trabajo)</span><span class="sxs-lookup"><span data-stu-id="57637-127">**Workspace name**</span></span>     | <span data-ttu-id="57637-128">Proporcione un nombre para el área de trabajo de Databricks.</span><span class="sxs-lookup"><span data-stu-id="57637-128">Provide a name for your Databricks workspace.</span></span>        |
    |<span data-ttu-id="57637-129">**Suscripción**</span><span class="sxs-lookup"><span data-stu-id="57637-129">**Subscription**</span></span>     | <span data-ttu-id="57637-130">En el cuadro desplegable, seleccione la suscripción de Azure.</span><span class="sxs-lookup"><span data-stu-id="57637-130">From the drop-down, select your Azure subscription.</span></span>        |
    |<span data-ttu-id="57637-131">**Grupos de recursos**</span><span class="sxs-lookup"><span data-stu-id="57637-131">**Resource group**</span></span>     | <span data-ttu-id="57637-132">Especifique si desea crear un nuevo grupo de recursos o utilizar uno existente.</span><span class="sxs-lookup"><span data-stu-id="57637-132">Specify whether you want to create a new resource group or use an existing one.</span></span> <span data-ttu-id="57637-133">Un grupo de recursos es un contenedor que almacena los recursos relacionados con una solución de Azure.</span><span class="sxs-lookup"><span data-stu-id="57637-133">A resource group is a container that holds related resources for an Azure solution.</span></span> <span data-ttu-id="57637-134">Para más información, consulte [Información general del grupo de recursos de Azure](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-overview).</span><span class="sxs-lookup"><span data-stu-id="57637-134">For more information, see [Azure Resource Group overview](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-overview).</span></span> |
    |<span data-ttu-id="57637-135">**Ubicación**</span><span class="sxs-lookup"><span data-stu-id="57637-135">**Location**</span></span>     | <span data-ttu-id="57637-136">Seleccione su región preferida.</span><span class="sxs-lookup"><span data-stu-id="57637-136">Select your preferred region.</span></span> <span data-ttu-id="57637-137">Para obtener información sobre las regiones disponibles, consulte [Servicios de Azure disponibles por región](https://azure.microsoft.com/regions/services/).</span><span class="sxs-lookup"><span data-stu-id="57637-137">For information about available regions, see [Azure services available by region](https://azure.microsoft.com/regions/services/).</span></span>        |
    |<span data-ttu-id="57637-138">**Plan de tarifa**</span><span class="sxs-lookup"><span data-stu-id="57637-138">**Pricing Tier**</span></span>     |  <span data-ttu-id="57637-139">Elija entre **Estándar**, **Premium** o **Evaluación gratuita**.</span><span class="sxs-lookup"><span data-stu-id="57637-139">Choose between **Standard**, **Premium**, or **Trial**.</span></span> <span data-ttu-id="57637-140">Para más información sobre estos planes, consulte la [página de precios de Databricks](https://azure.microsoft.com/pricing/details/databricks/).</span><span class="sxs-lookup"><span data-stu-id="57637-140">For more information on these tiers, see [Databricks pricing page](https://azure.microsoft.com/pricing/details/databricks/).</span></span>       |
    |<span data-ttu-id="57637-141">**Virtual Network**</span><span class="sxs-lookup"><span data-stu-id="57637-141">**Virtual Network**</span></span>     |   <span data-ttu-id="57637-142">No</span><span class="sxs-lookup"><span data-stu-id="57637-142">No</span></span>       |

3. <span data-ttu-id="57637-143">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="57637-143">Select **Create**.</span></span> <span data-ttu-id="57637-144">Se tarda unos minutos en crear el área de trabajo.</span><span class="sxs-lookup"><span data-stu-id="57637-144">The workspace creation takes a few minutes.</span></span> <span data-ttu-id="57637-145">Durante la creación del área de trabajo, puede ver el estado de implementación en **Notificaciones**.</span><span class="sxs-lookup"><span data-stu-id="57637-145">During workspace creation, you can view the deployment status in **Notifications**.</span></span>

## <a name="install-azure-databricks-tools"></a><span data-ttu-id="57637-146">Instalación de las herramientas de Azure Databricks</span><span class="sxs-lookup"><span data-stu-id="57637-146">Install Azure Databricks tools</span></span>

<span data-ttu-id="57637-147">Puede usar la **CLI de Databricks** para conectarse a los clústeres de Azure Databricks y cargar archivos en ellos desde la máquina local.</span><span class="sxs-lookup"><span data-stu-id="57637-147">You can use the **Databricks CLI** to connect to Azure Databricks clusters and upload files to them from your local machine.</span></span> <span data-ttu-id="57637-148">Los clústeres de Databricks tienen acceso a archivos a través del DBFS (Sistema de archivos de Databricks).</span><span class="sxs-lookup"><span data-stu-id="57637-148">Databricks clusters access files through DBFS (Databricks File System).</span></span>

1. <span data-ttu-id="57637-149">La CLI de Databricks requiere Python 3.6 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="57637-149">The Databricks CLI requires Python 3.6 or above.</span></span> <span data-ttu-id="57637-150">Si ya tiene Python instalado, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="57637-150">If you already have Python installed, you can skip this step.</span></span>

   <span data-ttu-id="57637-151">**Para Windows**:</span><span class="sxs-lookup"><span data-stu-id="57637-151">**For Windows:**</span></span>

   [<span data-ttu-id="57637-152">Descargar Python para Windows</span><span class="sxs-lookup"><span data-stu-id="57637-152">Download Python for Windows</span></span>](https://www.python.org/ftp/python/3.7.4/python-3.7.4.exe)

   <span data-ttu-id="57637-153">**Para Linux:** Python viene preinstalado en la mayoría de las distribuciones de Linux.</span><span class="sxs-lookup"><span data-stu-id="57637-153">**For Linux:** Python comes preinstalled on most Linux distributions.</span></span> <span data-ttu-id="57637-154">Ejecute el comando siguiente para ver la versión que se ha instalado:</span><span class="sxs-lookup"><span data-stu-id="57637-154">Run the following command to see which version you have installed:</span></span>

   ```bash
   python3 --version
   ```

2. <span data-ttu-id="57637-155">Use pip para instalar la CLI de Databricks.</span><span class="sxs-lookup"><span data-stu-id="57637-155">Use pip to install the Databricks CLI.</span></span> <span data-ttu-id="57637-156">Python 3.4 y las versiones posteriores incluyen pip de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="57637-156">Python 3.4 and later include pip by default.</span></span> <span data-ttu-id="57637-157">Use pip3 para Python 3.</span><span class="sxs-lookup"><span data-stu-id="57637-157">Use pip3 for Python 3.</span></span> <span data-ttu-id="57637-158">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="57637-158">Run the following command:</span></span>

   ```bash
   pip3 install databricks-cli
   ```

3. <span data-ttu-id="57637-159">Una vez instalada la CLI de Databricks, abra un símbolo del sistema nuevo y ejecute el comando `databricks`.</span><span class="sxs-lookup"><span data-stu-id="57637-159">Once you've installed the Databricks CLI, open a new command prompt and run the command `databricks`.</span></span> <span data-ttu-id="57637-160">Si recibe un aviso **"databricks" no se reconoce como un error de comando interno o externo**, asegúrese de que ha abierto un símbolo del sistema nuevo.</span><span class="sxs-lookup"><span data-stu-id="57637-160">If you receive a **'databricks' is not recognized as an internal or external command error**, make sure you opened a new command prompt.</span></span>

## <a name="set-up-azure-databricks"></a><span data-ttu-id="57637-161">Configuración de Azure Databricks</span><span class="sxs-lookup"><span data-stu-id="57637-161">Set up Azure Databricks</span></span>

<span data-ttu-id="57637-162">Ahora que tiene la CLI de Databricks instalada, debe configurar los detalles de autenticación.</span><span class="sxs-lookup"><span data-stu-id="57637-162">Now that you have the Databricks CLI installed, you need to set up authentication details.</span></span>

1. <span data-ttu-id="57637-163">Ejecute el comando `databricks configure --token` de la CLI de Databricks.</span><span class="sxs-lookup"><span data-stu-id="57637-163">Run the Databricks CLI command `databricks configure --token`.</span></span>

2. <span data-ttu-id="57637-164">Después de ejecutar el comando de configuración, se le pedirá que escriba un host.</span><span class="sxs-lookup"><span data-stu-id="57637-164">After running the configure command, you are prompted to enter a host.</span></span> <span data-ttu-id="57637-165">La dirección URL del host usa el formato: **https://<\Ubicación>.azuredatabricks.net**.</span><span class="sxs-lookup"><span data-stu-id="57637-165">Your host URL uses the format: **https://<\Location>.azuredatabricks.net**.</span></span> <span data-ttu-id="57637-166">Por ejemplo, si ha seleccionado **eastus2** durante la creación del Servicio de Azure Databricks, el host sería **https://eastus2.azuredatabricks.net** .</span><span class="sxs-lookup"><span data-stu-id="57637-166">For instance, if you selected **eastus2** during Azure Databricks Service creation, the host would be **https://eastus2.azuredatabricks.net**.</span></span>

3. <span data-ttu-id="57637-167">Después de escribir el host, se le pedirá que escriba un token.</span><span class="sxs-lookup"><span data-stu-id="57637-167">After entering your host, you are prompted to enter a token.</span></span> <span data-ttu-id="57637-168">En Azure Portal, seleccione **Iniciar área de trabajo** para iniciar el área de trabajo de Azure Databricks.</span><span class="sxs-lookup"><span data-stu-id="57637-168">In the Azure portal, select **Launch Workspace** to launch your Azure Databricks workspace.</span></span>

   ![Inicio del área de trabajo de Azure Databricks](./media/databricks-deployment/launch-databricks-workspace.png)

4. <span data-ttu-id="57637-170">En la página principal del área de trabajo, seleccione **Configuración de usuario**.</span><span class="sxs-lookup"><span data-stu-id="57637-170">On the home page of your workspace, select **User Settings**.</span></span>

   ![Configuración de usuario en el área de trabajo de Azure Databricks](./media/databricks-deployment/databricks-user-settings.png)

5. <span data-ttu-id="57637-172">En la página Configuración de usuario se puede generar un nuevo token.</span><span class="sxs-lookup"><span data-stu-id="57637-172">On the User Settings page, you can generate a new token.</span></span> <span data-ttu-id="57637-173">Copie el token generado y péguelo de nuevo en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="57637-173">Copy the generated token and paste it back into your command prompt.</span></span>

   ![Generación de un token de acceso nuevo en el área de trabajo de Azure Databricks](./media/databricks-deployment/generate-token.png)

<span data-ttu-id="57637-175">Ahora debería poder acceder a cualquier clúster de Azure Databricks que cree y cargar archivos en el DBFS.</span><span class="sxs-lookup"><span data-stu-id="57637-175">You should now be able to access any Azure Databricks clusters you create and upload files to the DBFS.</span></span>

## <a name="download-worker-dependencies"></a><span data-ttu-id="57637-176">Descarga de las dependencias de trabajo</span><span class="sxs-lookup"><span data-stu-id="57637-176">Download worker dependencies</span></span>

1. <span data-ttu-id="57637-177">Microsoft.Spark.Worker ayuda a Apache Spark a ejecutar la aplicación, como cualquier función definida por el usuario (UDF) que se haya escrito.</span><span class="sxs-lookup"><span data-stu-id="57637-177">Microsoft.Spark.Worker helps Apache Spark execute your app, such as any user-defined functions (UDFs) you may have written.</span></span> <span data-ttu-id="57637-178">Descargue [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases/download/v0.6.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz).</span><span class="sxs-lookup"><span data-stu-id="57637-178">Download [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases/download/v0.6.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz).</span></span>

2. <span data-ttu-id="57637-179">*install-worker.sh* es un script que permite copiar archivos dependientes de .NET para Apache Spark en los nodos del clúster.</span><span class="sxs-lookup"><span data-stu-id="57637-179">The *install-worker.sh* is a script that lets you copy .NET for Apache Spark dependent files into the nodes of your cluster.</span></span>

   <span data-ttu-id="57637-180">Cree un nuevo archivo llamado **install-worker.sh** en el equipo local y pegue el [contenido de install-worker.sh](https://raw.githubusercontent.com/dotnet/spark/master/deployment/install-worker.sh) que se encuentra en GitHub.</span><span class="sxs-lookup"><span data-stu-id="57637-180">Create a new file named **install-worker.sh** on your local computer, and paste the [install-worker.sh contents](https://raw.githubusercontent.com/dotnet/spark/master/deployment/install-worker.sh) located on GitHub.</span></span>

3. <span data-ttu-id="57637-181">*db-init.sh* es un script que instala las dependencias en el clúster de Spark de Databricks.</span><span class="sxs-lookup"><span data-stu-id="57637-181">The *db-init.sh* is a script that installs dependencies onto your Databricks Spark cluster.</span></span>

   <span data-ttu-id="57637-182">Cree un nuevo archivo llamado **db-init.sh** en el equipo local y pegue el [contenido de db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) que se encuentra en GitHub.</span><span class="sxs-lookup"><span data-stu-id="57637-182">Create a new file named **db-init.sh** on your local computer, and paste the [db-init.sh contents](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) located on GitHub.</span></span>

   <span data-ttu-id="57637-183">En el archivo que se acaba de crear, establezca la variable `DOTNET_SPARK_RELEASE` en `https://github.com/dotnet/spark/releases/download/v0.6.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz`.</span><span class="sxs-lookup"><span data-stu-id="57637-183">In the file you just created, set the `DOTNET_SPARK_RELEASE` variable to `https://github.com/dotnet/spark/releases/download/v0.6.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz`.</span></span> <span data-ttu-id="57637-184">Deje el resto del archivo *db-init.sh* tal cual.</span><span class="sxs-lookup"><span data-stu-id="57637-184">Leave the rest of the *db-init.sh* file as-is.</span></span>

> [!Note]
> <span data-ttu-id="57637-185">Si usa Windows, compruebe que los fines de línea de los scripts *install-worker.sh* y *db-init.sh* son de estilo Unix (LF).</span><span class="sxs-lookup"><span data-stu-id="57637-185">If you are using Windows, verify that the line-endings in your *install-worker.sh* and *db-init.sh* scripts are Unix-style (LF).</span></span> <span data-ttu-id="57637-186">Se pueden cambiar los fines de línea a través de los editores de texto como Notepad++ y Atom.</span><span class="sxs-lookup"><span data-stu-id="57637-186">You can change line endings through text editors like Notepad++ and Atom.</span></span>

## <a name="publish-your-app"></a><span data-ttu-id="57637-187">Publicar la aplicación</span><span class="sxs-lookup"><span data-stu-id="57637-187">Publish your app</span></span>

<span data-ttu-id="57637-188">Luego, publique la aplicación *mySparkApp* creada en el tutorial [.NET para Apache Spark: comenzar en 10 minutos](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) para asegurarse de que el clúster de Spark tiene acceso a todos los archivos que necesita para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="57637-188">Next, you publish the *mySparkApp* created in the [.NET for Apache Spark - Get Started in 10-Minutes](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) tutorial to ensure your Spark cluster has access to all the files it needs to run your app.</span></span>

1. <span data-ttu-id="57637-189">Para publicar *mySparkApp*, ejecute los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="57637-189">Run the following commands to publish the *mySparkApp*:</span></span>

   ```dotnetcli
   cd mySparkApp
   dotnet publish -c Release -f netcoreapp3.0 -r ubuntu.16.04-x64
   ```

2. <span data-ttu-id="57637-190">Realice las tareas siguientes para comprimir los archivos de la aplicación publicados para que pueda cargarlos fácilmente en el clúster de Spark de Databricks.</span><span class="sxs-lookup"><span data-stu-id="57637-190">Do the following tasks to zip your published app files so that you can easily upload them to your Databricks Spark cluster.</span></span>

   <span data-ttu-id="57637-191">**En Windows:**</span><span class="sxs-lookup"><span data-stu-id="57637-191">**On Windows:**</span></span>

   <span data-ttu-id="57637-192">Vaya a mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64.</span><span class="sxs-lookup"><span data-stu-id="57637-192">Navigate to mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64.</span></span> <span data-ttu-id="57637-193">Luego, haga clic con el botón derecho en la carpeta **Publicar** y seleccione **Enviar a > Carpeta comprimida (en zip)** .</span><span class="sxs-lookup"><span data-stu-id="57637-193">Then, right-click on **Publish** folder and select **Send to > Compressed (zipped) folder**.</span></span> <span data-ttu-id="57637-194">Asigne el nombre **publish.zip** a la carpeta nueva.</span><span class="sxs-lookup"><span data-stu-id="57637-194">Name the new folder **publish.zip**.</span></span>

   <span data-ttu-id="57637-195">**En Linux, ejecute el comando siguiente:**</span><span class="sxs-lookup"><span data-stu-id="57637-195">**On Linux, run the following command:**</span></span>

   ```bash
   zip -r publish.zip .
   ```

## <a name="upload-files"></a><span data-ttu-id="57637-196">Carga de archivos</span><span class="sxs-lookup"><span data-stu-id="57637-196">Upload files</span></span>

<span data-ttu-id="57637-197">En esta sección, se cargan varios archivos en el DBFS con el fin de que el clúster tenga todo lo necesario para ejecutar la aplicación en la nube.</span><span class="sxs-lookup"><span data-stu-id="57637-197">In this section, you upload several files to DBFS so that your cluster has everything it needs to run your app in the cloud.</span></span> <span data-ttu-id="57637-198">Cada vez que cargue un archivo en el DBFS, asegúrese de que está en el directorio en el que se encuentra el archivo en el equipo.</span><span class="sxs-lookup"><span data-stu-id="57637-198">Each time you upload a file to the DBFS, make sure you are in the directory where that file is located on your computer.</span></span>

1. <span data-ttu-id="57637-199">Ejecute los siguientes comandos para cargar *db-init.sh*, *install-worker.sh* y *Microsoft.Spark.Worker* en DBFS:</span><span class="sxs-lookup"><span data-stu-id="57637-199">Run the following commands to upload the *db-init.sh*, *install-worker.sh*, and *Microsoft.Spark.Worker* to DBFS:</span></span>

   ```console
   databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
   databricks fs cp install-worker.sh dbfs:/spark-dotnet/install-worker.sh
   databricks fs cp Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz dbfs:/spark-dotnet/   Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz
   ```

2. <span data-ttu-id="57637-200">Ejecute los comandos siguientes para cargar los archivos restantes que el clúster necesitará para ejecutar la aplicación: la carpeta de publicación comprimida, *Input.txt* y *microsoft-spark-2.4.x-0.3.0.jar*.</span><span class="sxs-lookup"><span data-stu-id="57637-200">Run the following commands to upload the remaining files your cluster will need to run your app: the zipped publish folder, *input.txt*, and *microsoft-spark-2.4.x-0.3.0.jar*.</span></span>

   ```console
   cd mySparkApp
   databricks fs cp input.txt dbfs:/input.txt

   cd mySparkApp\bin\Release\netcoreapp3.0\ubuntu.16.04-x64 directory
   databricks fs cp mySparkApp.zip dbfs:/spark-dotnet/publish.zip
   databricks fs cp microsoft-spark-2.4.x-0.6.0.jar dbfs:/spark-dotnet/microsoft-spark-2.4.x-0.6.0.jar
   ```

## <a name="create-a-job"></a><span data-ttu-id="57637-201">Creación de un trabajo</span><span class="sxs-lookup"><span data-stu-id="57637-201">Create a job</span></span>

<span data-ttu-id="57637-202">La aplicación se ejecuta en Azure Databricks a través de un trabajo que ejecuta **spark-submit**, que es el comando que se usa para ejecutar .NET para trabajos de Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="57637-202">Your app runs on Azure Databricks through a job that runs **spark-submit**, which is the command you use to run .NET for Apache Spark jobs.</span></span>

1. <span data-ttu-id="57637-203">En el área de trabajo de Azure Databricks, seleccione el icono de **Trabajos** y luego **+ Crear trabajo**.</span><span class="sxs-lookup"><span data-stu-id="57637-203">In your Azure Databricks Workspace, select the **Jobs** icon and then **+ Create Job**.</span></span>

   ![Creación de un trabajo de Azure Databricks](./media/databricks-deployment/create-job.png)

2. <span data-ttu-id="57637-205">Elija un título para el trabajo y luego seleccione **Configurar spark-submit**.</span><span class="sxs-lookup"><span data-stu-id="57637-205">Choose a title for your job, and then select **Configure spark-submit**.</span></span>

   ![Configuración de spark-submit para el trabajo de Databricks](./media/databricks-deployment/configure-spark-submit.png)

3. <span data-ttu-id="57637-207">Pegue los parámetros siguientes en la configuración del trabajo.</span><span class="sxs-lookup"><span data-stu-id="57637-207">Paste the following parameters in the job configuration.</span></span> <span data-ttu-id="57637-208">Después, seleccione **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="57637-208">Then, select **Confirm**.</span></span>

   ```
   ["--class","org.apache.spark.deploy.dotnet.DotnetRunner","/dbfs/spark-dotnet/microsoft-spark-2.4.x-0.6.0.jar","/dbfs/spark-dotnet/publish.zip","mySparkApp"]
   ```

## <a name="create-a-cluster"></a><span data-ttu-id="57637-209">Crear un clúster</span><span class="sxs-lookup"><span data-stu-id="57637-209">Create a cluster</span></span>

1. <span data-ttu-id="57637-210">Vaya a su trabajo y seleccione **Editar** para configurar el clúster del trabajo.</span><span class="sxs-lookup"><span data-stu-id="57637-210">Navigate to your job and select **Edit** to configure your job's cluster.</span></span>

2. <span data-ttu-id="57637-211">Establezca el clúster en **Spark 2.4.1**.</span><span class="sxs-lookup"><span data-stu-id="57637-211">Set your cluster to **Spark 2.4.1**.</span></span> <span data-ttu-id="57637-212">Luego, seleccione **Opciones avanzadas** > **Scripts Init**.</span><span class="sxs-lookup"><span data-stu-id="57637-212">Then, select **Advanced Options** > **Init Scripts**.</span></span> <span data-ttu-id="57637-213">Escriba la ruta de acceso del script Init como `dbfs:/spark-dotnet/db-init.sh`.</span><span class="sxs-lookup"><span data-stu-id="57637-213">Set Init Script Path as `dbfs:/spark-dotnet/db-init.sh`.</span></span>

   ![Configuración de un clúster de Spark en Azure Databricks](./media/databricks-deployment/cluster-config.png)

3. <span data-ttu-id="57637-215">Seleccione **Confirmar** para confirmar la configuración del clúster.</span><span class="sxs-lookup"><span data-stu-id="57637-215">Select **Confirm** to confirm your cluster settings.</span></span>

## <a name="run-your-app"></a><span data-ttu-id="57637-216">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="57637-216">Run your app</span></span>

1. <span data-ttu-id="57637-217">Vaya a su trabajo y seleccione **Ejecutar ahora** para ejecutar el trabajo en el clúster de Spark recientemente configurado.</span><span class="sxs-lookup"><span data-stu-id="57637-217">Navigate to your job and select **Run Now** to run your job on your newly configured Spark cluster.</span></span>

2. <span data-ttu-id="57637-218">La creación del clúster del trabajo tarda unos minutos.</span><span class="sxs-lookup"><span data-stu-id="57637-218">It takes a few minutes for the job's cluster to create.</span></span> <span data-ttu-id="57637-219">Una vez creado, se enviará el trabajo y podrá ver el resultado.</span><span class="sxs-lookup"><span data-stu-id="57637-219">Once it is created, your job will be submitted, and you can view the output.</span></span>

3. <span data-ttu-id="57637-220">Seleccione **Clústeres** en el menú de la izquierda y, después, el nombre y la ejecución del trabajo.</span><span class="sxs-lookup"><span data-stu-id="57637-220">Select **Clusters** from the left menu, and then the name and run of your job.</span></span>

4. <span data-ttu-id="57637-221">Seleccione **Registros de controladores** para ver la salida del trabajo.</span><span class="sxs-lookup"><span data-stu-id="57637-221">Select **Driver Logs** to view the output of your job.</span></span> <span data-ttu-id="57637-222">Cuando la aplicación termine de ejecutarse, verá la misma tabla de recuento de palabras de la ejecución local de introducción escrita en la consola de salida estándar.</span><span class="sxs-lookup"><span data-stu-id="57637-222">When your app finishes executing, you see the same word count table from the getting started local run written to the standard output console.</span></span>

   ![Tabla de salida del trabajo de Azure Databricks](./media/databricks-deployment/table-output.png)

   <span data-ttu-id="57637-224">Enhorabuena, ha ejecutado su primera aplicación de .NET para Apache Spark en la nube.</span><span class="sxs-lookup"><span data-stu-id="57637-224">Congratulations, you've run your first .NET for Apache Spark application in the cloud!</span></span>

## <a name="clean-up-resources"></a><span data-ttu-id="57637-225">Limpiar los recursos</span><span class="sxs-lookup"><span data-stu-id="57637-225">Clean up resources</span></span>

<span data-ttu-id="57637-226">Si ya no necesita el área de trabajo de Databricks, puede eliminar el recurso Azure Databricks en Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="57637-226">If you no longer need the Databricks workspace, you can delete your Azure Databricks resource in the Azure portal.</span></span> <span data-ttu-id="57637-227">También puede seleccionar el nombre del grupo de recursos para abrir la página del grupo de recursos y, a continuación, seleccionar **Eliminar grupo de recursos**.</span><span class="sxs-lookup"><span data-stu-id="57637-227">You can also select the resource group name to open the resource group page, and then select **Delete resource group**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="57637-228">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="57637-228">Next steps</span></span>

<span data-ttu-id="57637-229">En este tutorial ha implementado una aplicación de .NET para Apache Spark en Databricks.</span><span class="sxs-lookup"><span data-stu-id="57637-229">In this tutorial, you deployed your .NET for Apache Spark application to Databricks.</span></span> <span data-ttu-id="57637-230">Para más información sobre Databricks, prosiga con la documentación de Azure Databricks.</span><span class="sxs-lookup"><span data-stu-id="57637-230">To learn more about Databricks, continue to the Azure Databricks Documentation.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="57637-231">Documentación de Azure Databricks</span><span class="sxs-lookup"><span data-stu-id="57637-231">Azure Databricks Documentation</span></span>](https://docs.microsoft.com/azure/azure-databricks/)
