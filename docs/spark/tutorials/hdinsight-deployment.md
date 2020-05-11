---
title: Implementación de una aplicación de .NET para Apache Spark en Azure HDInsight
description: Aprenda a implementar una aplicación de .NET para Apache Spark en HDInsight.
ms.date: 01/23/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 6b8dbe395a5db9631433a5821f5ef2b9ade556f6
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895698"
---
# <a name="tutorial-deploy-a-net-for-apache-spark-application-to-azure-hdinsight"></a><span data-ttu-id="089d9-103">Tutorial: Implementación de una aplicación de .NET para Apache Spark en Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="089d9-103">Tutorial: Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>

<span data-ttu-id="089d9-104">Este tutorial enseña cómo implementar la aplicación de .NET para Apache Spark en la nube a través de un clúster de Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="089d9-104">This tutorial teaches you how to deploy your .NET for Apache Spark app to the cloud through an Azure HDInsight cluster.</span></span> <span data-ttu-id="089d9-105">HDInsight facilita la creación y configuración de un clúster de Spark en Azure, ya que los clústeres de Spark en HDInsight son compatibles con Azure Storage y Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="089d9-105">HDInsight makes it easier to create and configure a Spark cluster in Azure since Spark clusters in HDInsight are compatible with Azure Storage and Azure Data Lake Storage.</span></span>

<span data-ttu-id="089d9-106">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="089d9-106">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="089d9-107">Obtener acceso a las cuentas de almacenamiento mediante el Explorador de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="089d9-107">Access your storage accounts using Azure Storage Explorer.</span></span>
> * <span data-ttu-id="089d9-108">Crear un clúster de Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="089d9-108">Create an Azure HDInsight cluster.</span></span>
> * <span data-ttu-id="089d9-109">Publicar la aplicación de .NET para Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="089d9-109">Publish your .NET for Apache Spark app.</span></span>
> * <span data-ttu-id="089d9-110">Crear y ejecutar una acción de script de HDInsight.</span><span class="sxs-lookup"><span data-stu-id="089d9-110">Create and run an HDInsight script action.</span></span>
> * <span data-ttu-id="089d9-111">Ejecutar una aplicación de .NET para Apache Spark en un clúster de HDInsight.</span><span class="sxs-lookup"><span data-stu-id="089d9-111">Run a .NET for Apache Spark app on an HDInsight cluster.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="089d9-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="089d9-112">Prerequisites</span></span>

<span data-ttu-id="089d9-113">Antes de empezar, haga las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="089d9-113">Before you start, do the following tasks:</span></span>

* <span data-ttu-id="089d9-114">Si no tiene una suscripción a Azure, cree una [cuenta gratuita](https://azure.microsoft.com/free/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="089d9-114">If you don't have an Azure subscription, create a [free account](https://azure.microsoft.com/free/dotnet/).</span></span>
* <span data-ttu-id="089d9-115">Inicie sesión en [Azure Portal](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="089d9-115">Sign in to the [Azure portal](https://portal.azure.com/).</span></span>
* <span data-ttu-id="089d9-116">Instale el Explorador de Azure Storage en el equipo [Windows](https://go.microsoft.com/fwlink/?LinkId=708343&clcid=0x409), [Linux](https://go.microsoft.com/fwlink/?LinkId=722418&clcid=0x409) o [MacOS](https://go.microsoft.com/fwlink/?LinkId=708342&clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="089d9-116">Install Azure Storage Explorer on your [Windows](https://go.microsoft.com/fwlink/?LinkId=708343&clcid=0x409), [Linux](https://go.microsoft.com/fwlink/?LinkId=722418&clcid=0x409), or [MacOS](https://go.microsoft.com/fwlink/?LinkId=708342&clcid=0x409) computer.</span></span>
* <span data-ttu-id="089d9-117">Complete el tutorial [.NET para Apache Spark: comenzar en 10 minutos](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro).</span><span class="sxs-lookup"><span data-stu-id="089d9-117">Complete the [.NET for Apache Spark - Get Started in 10-Minutes](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) tutorial.</span></span>

## <a name="access-your-storage-accounts"></a><span data-ttu-id="089d9-118">Acceso a las cuentas de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="089d9-118">Access your storage accounts</span></span>

1. <span data-ttu-id="089d9-119">Abra el Explorador de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="089d9-119">Open Azure Storage Explorer.</span></span>

2. <span data-ttu-id="089d9-120">Seleccione **Agregar cuenta** en el menú de la izquierda e inicie sesión en su cuenta de Azure.</span><span class="sxs-lookup"><span data-stu-id="089d9-120">Select **Add Account** on the left menu, and sign in to your Azure account.</span></span>

    ![Inicio de sesión en la cuenta de Azure desde el Explorador de Storage](./media/hdinsight-deployment/signin-azure-storage-explorer.png)

   <span data-ttu-id="089d9-122">Después de iniciar sesión, debería ver todas las cuentas de almacenamiento que tiene y los recursos que ha cargado en estas.</span><span class="sxs-lookup"><span data-stu-id="089d9-122">After you sign in, you should see all storage accounts you have and any resources you have uploaded to your storage accounts.</span></span>

## <a name="create-an-hdinsight-cluster"></a><span data-ttu-id="089d9-123">Creación de un clúster de HDInsight</span><span class="sxs-lookup"><span data-stu-id="089d9-123">Create an HDInsight cluster</span></span>

> [!IMPORTANT]
> <span data-ttu-id="089d9-124">La facturación de los clústeres de HDInsight se prorratea por minuto, incluso si no los está usando.</span><span class="sxs-lookup"><span data-stu-id="089d9-124">Billing for HDInsight clusters is prorated per minute, even if you're not using them.</span></span> <span data-ttu-id="089d9-125">Por consiguiente, es aconsejable eliminar el clúster al terminar de usarlo.</span><span class="sxs-lookup"><span data-stu-id="089d9-125">Be sure to delete your cluster after you have finished using it.</span></span> <span data-ttu-id="089d9-126">Para obtener más información, consulte la sección [Limpieza de recursos](#clean-up-resources) de este tutorial.</span><span class="sxs-lookup"><span data-stu-id="089d9-126">For more information, see the [Clean up resources](#clean-up-resources) section of this tutorial.</span></span>

1. <span data-ttu-id="089d9-127">Visite [Azure Portal](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="089d9-127">Visit the [Azure portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="089d9-128">Seleccione **+ Crear un recurso**.</span><span class="sxs-lookup"><span data-stu-id="089d9-128">Select **+ Create a resource**.</span></span> <span data-ttu-id="089d9-129">Después, seleccione **HDInsight** en la categoría **Análisis**.</span><span class="sxs-lookup"><span data-stu-id="089d9-129">Then, select **HDInsight** from the **Analytics** category.</span></span>

    ![Creación de un recurso de HDInsight desde Azure Portal](./media/hdinsight-deployment/create-hdinsight-resource.png)

3. <span data-ttu-id="089d9-131">En **Datos básicos**, proporcione los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="089d9-131">Under **Basics**, provide the following values:</span></span>

    |<span data-ttu-id="089d9-132">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="089d9-132">Property</span></span>  |<span data-ttu-id="089d9-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="089d9-133">Description</span></span>  |
    |---------|---------|
    |<span data-ttu-id="089d9-134">Suscripción</span><span class="sxs-lookup"><span data-stu-id="089d9-134">Subscription</span></span>  | <span data-ttu-id="089d9-135">En la lista desplegable, elija una de las suscripciones de Azure activas.</span><span class="sxs-lookup"><span data-stu-id="089d9-135">From the drop-down, choose one of your active Azure subscriptions.</span></span> |
    |<span data-ttu-id="089d9-136">Resource group</span><span class="sxs-lookup"><span data-stu-id="089d9-136">Resource group</span></span> | <span data-ttu-id="089d9-137">Especifique si desea crear un nuevo grupo de recursos o utilizar uno existente.</span><span class="sxs-lookup"><span data-stu-id="089d9-137">Specify whether you want to create a new resource group or use an existing one.</span></span> <span data-ttu-id="089d9-138">Un grupo de recursos es un contenedor que almacena los recursos relacionados con una solución de Azure.</span><span class="sxs-lookup"><span data-stu-id="089d9-138">A resource group is a container that holds related resources for an Azure solution.</span></span> |
    |<span data-ttu-id="089d9-139">Nombre del clúster</span><span class="sxs-lookup"><span data-stu-id="089d9-139">Cluster name</span></span> | <span data-ttu-id="089d9-140">Asigne un nombre al clúster de Spark de HDInsight.</span><span class="sxs-lookup"><span data-stu-id="089d9-140">Give a name to your HDInsight Spark cluster.</span></span>|
    |<span data-ttu-id="089d9-141">Ubicación</span><span class="sxs-lookup"><span data-stu-id="089d9-141">Location</span></span>   | <span data-ttu-id="089d9-142">Seleccione una ubicación para el grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="089d9-142">Select a location for the resource group.</span></span> <span data-ttu-id="089d9-143">La plantilla utiliza esta ubicación para crear el clúster, así como para el almacenamiento de clúster predeterminado.</span><span class="sxs-lookup"><span data-stu-id="089d9-143">The template uses this location for creating the cluster as well as for the default cluster storage.</span></span> |
    |<span data-ttu-id="089d9-144">Tipo de clúster</span><span class="sxs-lookup"><span data-stu-id="089d9-144">Cluster type</span></span>| <span data-ttu-id="089d9-145">Seleccione **Spark** como el tipo de clúster.</span><span class="sxs-lookup"><span data-stu-id="089d9-145">Select **Spark** as the cluster type.</span></span>|
    |<span data-ttu-id="089d9-146">Versión del clúster</span><span class="sxs-lookup"><span data-stu-id="089d9-146">Cluster version</span></span>|<span data-ttu-id="089d9-147">Este campo se rellenará automáticamente con la versión predeterminada una vez que se haya seleccionado el tipo de clúster.</span><span class="sxs-lookup"><span data-stu-id="089d9-147">This field will autopopulate with the default version once the cluster type has been selected.</span></span> <span data-ttu-id="089d9-148">Seleccione una versión 2.3 o 2.4 de Spark.</span><span class="sxs-lookup"><span data-stu-id="089d9-148">Select a 2.3 or 2.4 version of Spark.</span></span>|
    |<span data-ttu-id="089d9-149">Nombre de usuario de inicio de sesión del clúster</span><span class="sxs-lookup"><span data-stu-id="089d9-149">Cluster login username</span></span>| <span data-ttu-id="089d9-150">Escriba el nombre de usuario de inicio de sesión del clúster.</span><span class="sxs-lookup"><span data-stu-id="089d9-150">Enter the cluster login username.</span></span>  <span data-ttu-id="089d9-151">El nombre predeterminado es *admin*.</span><span class="sxs-lookup"><span data-stu-id="089d9-151">The default name is *admin*.</span></span> |
    |<span data-ttu-id="089d9-152">Contraseña de inicio de sesión de clúster</span><span class="sxs-lookup"><span data-stu-id="089d9-152">Cluster login password</span></span>| <span data-ttu-id="089d9-153">Escriba una contraseña de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="089d9-153">Enter any login password.</span></span> |
    |<span data-ttu-id="089d9-154">Nombre de usuario de Secure Shell (SSH)</span><span class="sxs-lookup"><span data-stu-id="089d9-154">Secure Shell (SSH) username</span></span>| <span data-ttu-id="089d9-155">Escriba el nombre de usuario de SSH.</span><span class="sxs-lookup"><span data-stu-id="089d9-155">Enter the SSH username.</span></span> <span data-ttu-id="089d9-156">De manera predeterminada, esta cuenta comparte la contraseña con la cuenta de *nombre de usuario de inicio de sesión del clúster*.</span><span class="sxs-lookup"><span data-stu-id="089d9-156">By default, this account shares the same password as the *Cluster Login username* account.</span></span> |

4. <span data-ttu-id="089d9-157">Seleccione **Siguiente: Almacenamiento>>** para continuar en la página **Almacenamiento**.</span><span class="sxs-lookup"><span data-stu-id="089d9-157">Select **Next: Storage >>** to continue to the **Storage** page.</span></span> <span data-ttu-id="089d9-158">En **Almacenamiento**, proporcione los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="089d9-158">Under **Storage**, provide the following values:</span></span>

    |<span data-ttu-id="089d9-159">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="089d9-159">Property</span></span>  |<span data-ttu-id="089d9-160">Descripción</span><span class="sxs-lookup"><span data-stu-id="089d9-160">Description</span></span>  |
    |---------|---------|
    |<span data-ttu-id="089d9-161">Tipo de almacenamiento principal</span><span class="sxs-lookup"><span data-stu-id="089d9-161">Primary storage type</span></span>|<span data-ttu-id="089d9-162">Use el valor predeterminado **Azure Storage**.</span><span class="sxs-lookup"><span data-stu-id="089d9-162">Use the default value **Azure Storage**.</span></span>|
    |<span data-ttu-id="089d9-163">Método de selección</span><span class="sxs-lookup"><span data-stu-id="089d9-163">Selection method</span></span>|<span data-ttu-id="089d9-164">Use el valor predeterminado **Seleccionar de la lista**.</span><span class="sxs-lookup"><span data-stu-id="089d9-164">Use the default value **Select from list**.</span></span>|
    |<span data-ttu-id="089d9-165">Cuenta de almacenamiento principal</span><span class="sxs-lookup"><span data-stu-id="089d9-165">Primary storage account</span></span>|<span data-ttu-id="089d9-166">Elija su suscripción y una de sus cuentas de almacenamiento activas en esa suscripción.</span><span class="sxs-lookup"><span data-stu-id="089d9-166">Choose your subscription and one of your active storage accounts within that subscription.</span></span>|
    |<span data-ttu-id="089d9-167">Contenedor</span><span class="sxs-lookup"><span data-stu-id="089d9-167">Container</span></span>|<span data-ttu-id="089d9-168">Este contenedor es el contenedor de blobs específico de la cuenta de almacenamiento en la que el clúster busca archivos para ejecutar la aplicación en la nube.</span><span class="sxs-lookup"><span data-stu-id="089d9-168">This container is the specific blob container in your storage account where your cluster looks for files to run your app in the cloud.</span></span> <span data-ttu-id="089d9-169">Puede asignarle cualquier nombre disponible.</span><span class="sxs-lookup"><span data-stu-id="089d9-169">You can give it any available name.</span></span>|

5. <span data-ttu-id="089d9-170">Seleccione **Revisar y crear** y, después, **Crear**.</span><span class="sxs-lookup"><span data-stu-id="089d9-170">Under **Review + create**, select **Create**.</span></span> <span data-ttu-id="089d9-171">La creación del clúster tarda aproximadamente 20 minutos.</span><span class="sxs-lookup"><span data-stu-id="089d9-171">It takes about 20 minutes to create the cluster.</span></span> <span data-ttu-id="089d9-172">Se debe crear el clúster para poder continuar con el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="089d9-172">The cluster must be created before you can continue to the next step.</span></span>

## <a name="publish-your-app"></a><span data-ttu-id="089d9-173">Publicar la aplicación</span><span class="sxs-lookup"><span data-stu-id="089d9-173">Publish your app</span></span>

<span data-ttu-id="089d9-174">Luego, publique la aplicación *mySparkApp* creada en el tutorial [.NET para Apache Spark: comenzar en 10 minutos](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro), que proporciona acceso al clúster de Spark a todos los archivos que necesita para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="089d9-174">Next, you publish the *mySparkApp* created in the [.NET for Apache Spark - Get Started in 10-Minutes](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) tutorial, which gives your Spark cluster access to all the files it needs to run your app.</span></span>

1. <span data-ttu-id="089d9-175">Para publicar *mySparkApp*, ejecute los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="089d9-175">Run the following commands to publish the *mySparkApp*:</span></span>

   <span data-ttu-id="089d9-176">**En Windows:**</span><span class="sxs-lookup"><span data-stu-id="089d9-176">**On Windows:**</span></span>

   ```dotnetcli
   cd mySparkApp
   dotnet publish -c Release -f netcoreapp3.0 -r ubuntu.16.04-x64
   ```

   <span data-ttu-id="089d9-177">**En Linux:**</span><span class="sxs-lookup"><span data-stu-id="089d9-177">**On Linux:**</span></span>

   ```bash
   cd mySparkApp
   foo@bar:~/path/to/app$ dotnet publish -c Release -f netcoreapp3.0 -r ubuntu.16.04-x64
   ```

2. <span data-ttu-id="089d9-178">Realice las tareas siguientes para comprimir los archivos de la aplicación publicados para que pueda cargarlos fácilmente en el clúster de HDInsight.</span><span class="sxs-lookup"><span data-stu-id="089d9-178">Do the following tasks to zip your published app files so that you can easily upload them to your HDInsight cluster.</span></span>

   <span data-ttu-id="089d9-179">**En Windows:**</span><span class="sxs-lookup"><span data-stu-id="089d9-179">**On Windows:**</span></span>

   <span data-ttu-id="089d9-180">Vaya a *mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64*.</span><span class="sxs-lookup"><span data-stu-id="089d9-180">Navigate to *mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64*.</span></span> <span data-ttu-id="089d9-181">Luego, haga clic con el botón derecho en la carpeta **Publicar** y seleccione **Enviar a > Carpeta comprimida (en zip)** .</span><span class="sxs-lookup"><span data-stu-id="089d9-181">Then, right-click on **Publish** folder and select **Send to > Compressed (zipped) folder**.</span></span> <span data-ttu-id="089d9-182">Asigne el nombre **publish.zip** a la carpeta nueva.</span><span class="sxs-lookup"><span data-stu-id="089d9-182">Name the new folder **publish.zip**.</span></span>

   <span data-ttu-id="089d9-183">**En Linux, ejecute el comando siguiente:**</span><span class="sxs-lookup"><span data-stu-id="089d9-183">**On Linux, run the following command:**</span></span>

   ```bash
   zip -r publish.zip
   ```

## <a name="upload-files-to-azure"></a><span data-ttu-id="089d9-184">Carga de archivos en Azure</span><span class="sxs-lookup"><span data-stu-id="089d9-184">Upload files to Azure</span></span>

<span data-ttu-id="089d9-185">Después, use el Explorador de Azure Storage para cargar los cinco archivos siguientes en el contenedor de blobs que se ha elegido para el almacenamiento del clúster:</span><span class="sxs-lookup"><span data-stu-id="089d9-185">Next, you use the Azure Storage Explorer to upload the following five files to the blob container you chose for your cluster's storage:</span></span>

* <span data-ttu-id="089d9-186">Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="089d9-186">Microsoft.Spark.Worker</span></span>
* <span data-ttu-id="089d9-187">install-worker.sh</span><span class="sxs-lookup"><span data-stu-id="089d9-187">install-worker.sh</span></span>
* <span data-ttu-id="089d9-188">publish.zip</span><span class="sxs-lookup"><span data-stu-id="089d9-188">publish.zip</span></span>
* <span data-ttu-id="089d9-189">microsoft-spark-2.3.x-0.3.0.jar</span><span class="sxs-lookup"><span data-stu-id="089d9-189">microsoft-spark-2.3.x-0.3.0.jar</span></span>
* <span data-ttu-id="089d9-190">input.txt.</span><span class="sxs-lookup"><span data-stu-id="089d9-190">input.txt.</span></span>

1. <span data-ttu-id="089d9-191">Abra el Explorador de Azure Storage y vaya a la cuenta de almacenamiento en el menú de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="089d9-191">Open Azure Storage Explorer and navigate to your storage account from the left menu.</span></span> <span data-ttu-id="089d9-192">Explore en profundidad el contenedor de blobs del clúster en **Contenedores de blobs** en su cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="089d9-192">Drill down to the blob container for your cluster under **Blob Containers** in your storage account.</span></span>

2. <span data-ttu-id="089d9-193">*Microsoft.Spark.Worker* ayuda a Apache Spark a ejecutar la aplicación, como cualquier función definida por el usuario (UDF) que se haya escrito.</span><span class="sxs-lookup"><span data-stu-id="089d9-193">*Microsoft.Spark.Worker* helps Apache Spark execute your app, such as any user-defined functions (UDFs) you may have written.</span></span> <span data-ttu-id="089d9-194">Descargue [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases/download/v0.3.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.3.0.tar.gz).</span><span class="sxs-lookup"><span data-stu-id="089d9-194">Download [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases/download/v0.3.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.3.0.tar.gz).</span></span> <span data-ttu-id="089d9-195">Luego seleccione **Cargar** en el Explorador de Azure Storage para cargar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="089d9-195">Then, select **Upload** in Azure Storage Explorer to upload the worker.</span></span>

   ![Carga de archivos en el Explorador de Azure Storage](./media/hdinsight-deployment/upload-files-to-storage.png)

3. <span data-ttu-id="089d9-197">*install-worker.sh* es un script que permite copiar archivos dependientes de .NET para Apache Spark en los nodos del clúster.</span><span class="sxs-lookup"><span data-stu-id="089d9-197">The *install-worker.sh* is a script that lets you copy .NET for Apache Spark dependent files into the nodes of your cluster.</span></span>

   <span data-ttu-id="089d9-198">Cree un nuevo archivo llamado **install-worker.sh** en el equipo local y pegue el [contenido de install-worker.sh](https://raw.githubusercontent.com/dotnet/spark/master/deployment/install-worker.sh) que se encuentra en GitHub.</span><span class="sxs-lookup"><span data-stu-id="089d9-198">Create a new file named **install-worker.sh** your local computer, and paste the [install-worker.sh contents](https://raw.githubusercontent.com/dotnet/spark/master/deployment/install-worker.sh) located on GitHub.</span></span> <span data-ttu-id="089d9-199">Después, cargue *install-worker.sh* en el contenedor de blobs.</span><span class="sxs-lookup"><span data-stu-id="089d9-199">Then, upload *install-worker.sh* to your blob container.</span></span>

4. <span data-ttu-id="089d9-200">El clúster necesita el archivo publish.zip que contiene los archivos publicados de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="089d9-200">Your cluster needs the publish.zip file that contains your app's published files.</span></span> <span data-ttu-id="089d9-201">Vaya a la carpeta publicada, **mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64** y busque **publish.zip**.</span><span class="sxs-lookup"><span data-stu-id="089d9-201">Navigate to your published folder, **mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64**, and locate **publish.zip**.</span></span> <span data-ttu-id="089d9-202">Después, cargue *publish.zip* en el contenedor de blobs.</span><span class="sxs-lookup"><span data-stu-id="089d9-202">Then upload *publish.zip* to your blob container.</span></span>

5. <span data-ttu-id="089d9-203">El clúster necesita el código de aplicación que se ha empaquetado en un archivo jar.</span><span class="sxs-lookup"><span data-stu-id="089d9-203">Your cluster needs the application code that was packaged into a jar file.</span></span> <span data-ttu-id="089d9-204">Vaya a la carpeta publicada, **mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64** y busque **microsoft-spark-2.3.x-0.3.0.jar**.</span><span class="sxs-lookup"><span data-stu-id="089d9-204">Navigate to your published folder, **mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64**, and locate **microsoft-spark-2.3.x-0.3.0.jar**.</span></span> <span data-ttu-id="089d9-205">Después, cargue el archivo jar en el contenedor de blobs.</span><span class="sxs-lookup"><span data-stu-id="089d9-205">Then, upload the jar file to your blob container.</span></span>

   <span data-ttu-id="089d9-206">Puede haber varios archivos .jar (para las versiones 2.3.x y 2.4.x de Spark).</span><span class="sxs-lookup"><span data-stu-id="089d9-206">There may be multiple .jar files (for versions 2.3.x and 2.4.x of Spark).</span></span> <span data-ttu-id="089d9-207">Debe elegir el archivo .jar que coincida con la versión de Spark que se haya elegido durante la creación del clúster.</span><span class="sxs-lookup"><span data-stu-id="089d9-207">You need to choose the .jar file that matches the version of Spark you chose during cluster creation.</span></span> <span data-ttu-id="089d9-208">Por ejemplo, elija *microsoft-spark-2.3.x-0.3.0.jar* si se ha elegido Spark 2.3.2 durante la creación del clúster.</span><span class="sxs-lookup"><span data-stu-id="089d9-208">For example, choose *microsoft-spark-2.3.x-0.3.0.jar* if you chose Spark 2.3.2 during cluster creation.</span></span>

6. <span data-ttu-id="089d9-209">El clúster necesita la entrada a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="089d9-209">Your cluster needs the input to your app.</span></span> <span data-ttu-id="089d9-210">Vaya al directorio **mySparkApp** y busque **input.txt**.</span><span class="sxs-lookup"><span data-stu-id="089d9-210">Navigate to your **mySparkApp** directory and locate **input.txt**.</span></span> <span data-ttu-id="089d9-211">Cargue el archivo de entrada en el directorio **user/sshuser** en el contenedor de blobs.</span><span class="sxs-lookup"><span data-stu-id="089d9-211">Upload your input file to the **user/sshuser** directory in your blob container.</span></span> <span data-ttu-id="089d9-212">Se conectará al clúster mediante SSH y en esta carpeta es donde el clúster buscará su entrada.</span><span class="sxs-lookup"><span data-stu-id="089d9-212">You will be connecting to your cluster through ssh, and this folder is where your cluster looks for its input.</span></span> <span data-ttu-id="089d9-213">El archivo *input.txt* es el único archivo que se carga en un directorio concreto.</span><span class="sxs-lookup"><span data-stu-id="089d9-213">The *input.txt* file is the only file uploaded to a specific directory.</span></span>

## <a name="run-the-hdinsight-script-action"></a><span data-ttu-id="089d9-214">Ejecución de la acción de script de HDInsight</span><span class="sxs-lookup"><span data-stu-id="089d9-214">Run the HDInsight script action</span></span>

<span data-ttu-id="089d9-215">Cuando el clúster se esté ejecutando y haya cargado los archivos en Azure, ejecute el script **install-worker.sh** en el clúster.</span><span class="sxs-lookup"><span data-stu-id="089d9-215">Once your cluster is running and you've uploaded your files to Azure, you run the **install-worker.sh** script on the cluster.</span></span>

1. <span data-ttu-id="089d9-216">Vaya al clúster de HDInsight de Spark en Azure Portal y luego seleccione **Acciones de script**.</span><span class="sxs-lookup"><span data-stu-id="089d9-216">Navigate to your HDInsight Spark cluster in Azure portal, and then select **Script actions**.</span></span>

2. <span data-ttu-id="089d9-217">Seleccione **+ Enviar nuevo** y proporcione los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="089d9-217">Select **+ Submit new** and provide the following values:</span></span>

   |<span data-ttu-id="089d9-218">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="089d9-218">Property</span></span>  |<span data-ttu-id="089d9-219">Descripción</span><span class="sxs-lookup"><span data-stu-id="089d9-219">Description</span></span>  |
   |---------|---------|
   | <span data-ttu-id="089d9-220">Tipo de script</span><span class="sxs-lookup"><span data-stu-id="089d9-220">Script type</span></span> |<span data-ttu-id="089d9-221">Personalizados</span><span class="sxs-lookup"><span data-stu-id="089d9-221">Custom</span></span>|
   | <span data-ttu-id="089d9-222">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="089d9-222">Name</span></span> | <span data-ttu-id="089d9-223">Instalación del trabajo</span><span class="sxs-lookup"><span data-stu-id="089d9-223">Install Worker</span></span>|
   | <span data-ttu-id="089d9-224">URI de script de Bash</span><span class="sxs-lookup"><span data-stu-id="089d9-224">Bash script URI</span></span> |https://mystorageaccount.blob.core.windows.net/mycontainer/install-worker.sh </br> <span data-ttu-id="089d9-225">Para confirmar este URI, haga clic con el botón derecho en install-worker.sh en el Explorador de Azure Storage y seleccione Propiedades.</span><span class="sxs-lookup"><span data-stu-id="089d9-225">To confirm this URI, right-click on install-worker.sh in Azure Storage Explorer and select Properties.</span></span> |
   | <span data-ttu-id="089d9-226">Tipos de nodo</span><span class="sxs-lookup"><span data-stu-id="089d9-226">Node type(s)</span></span>| <span data-ttu-id="089d9-227">Trabajo</span><span class="sxs-lookup"><span data-stu-id="089d9-227">Worker</span></span>|
   | <span data-ttu-id="089d9-228">Parámetros</span><span class="sxs-lookup"><span data-stu-id="089d9-228">Parameters</span></span> | <span data-ttu-id="089d9-229">azure</span><span class="sxs-lookup"><span data-stu-id="089d9-229">azure</span></span> </br> wasbs://mycontainer@myStorageAccount.blob.core.windows.net/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz </br> <span data-ttu-id="089d9-230">/usr/local/bin</span><span class="sxs-lookup"><span data-stu-id="089d9-230">/usr/local/bin</span></span>

3. <span data-ttu-id="089d9-231">Seleccione **Crear** para enviar el script.</span><span class="sxs-lookup"><span data-stu-id="089d9-231">Select **Create** to submit your script.</span></span>

## <a name="run-your-app"></a><span data-ttu-id="089d9-232">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="089d9-232">Run your app</span></span>

1. <span data-ttu-id="089d9-233">Vaya al clúster de HDInsight de Spark en Azure Portal y luego seleccione **SSH e inicio de sesión del clúster**.</span><span class="sxs-lookup"><span data-stu-id="089d9-233">Navigate to your HDInsight Spark cluster in Azure portal, and then select **SSH + Cluster login**.</span></span>

2. <span data-ttu-id="089d9-234">Copie la información de inicio de sesión de SSH y pegue el inicio de sesión en un terminal.</span><span class="sxs-lookup"><span data-stu-id="089d9-234">Copy the ssh login information and paste the login into a terminal.</span></span> <span data-ttu-id="089d9-235">Inicie sesión en el clúster con la contraseña que se ha establecido durante la creación del clúster.</span><span class="sxs-lookup"><span data-stu-id="089d9-235">Sign in to your cluster using the password you set during cluster creation.</span></span> <span data-ttu-id="089d9-236">Debería ver mensajes de bienvenida a Ubuntu y Spark.</span><span class="sxs-lookup"><span data-stu-id="089d9-236">You should see messages welcoming you to Ubuntu and Spark.</span></span>

3. <span data-ttu-id="089d9-237">Use el comando **spark-submit** para ejecutar la aplicación en el clúster de HDInsight.</span><span class="sxs-lookup"><span data-stu-id="089d9-237">Use the **spark-submit** command to run your app on your HDInsight cluster.</span></span> <span data-ttu-id="089d9-238">Recuerde reemplazar **mycontainer** y **mystorageaccount** en el script de ejemplo con los nombres reales del contenedor de blobs y la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="089d9-238">Remember to replace **mycontainer** and **mystorageaccount** in the example script with the actual names of your blob container and storage account.</span></span>

   ```bash
   $SPARK_HOME/bin/spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/microsoft-spark-2.3.x-0.6.0.jar \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/publish.zip mySparkApp
   ```

   <span data-ttu-id="089d9-239">Cuando la aplicación se ejecute, verá la misma tabla de recuento de palabras de la ejecución local de introducción escrita en la consola.</span><span class="sxs-lookup"><span data-stu-id="089d9-239">When your app runs, you see the same word count table from the getting started local run written to the console.</span></span> <span data-ttu-id="089d9-240">Enhorabuena, ha ejecutado su primera aplicación de .NET para Apache Spark en la nube.</span><span class="sxs-lookup"><span data-stu-id="089d9-240">Congratulations, you've run your first .NET for Apache Spark application in the cloud!</span></span>

## <a name="clean-up-resources"></a><span data-ttu-id="089d9-241">Limpiar los recursos</span><span class="sxs-lookup"><span data-stu-id="089d9-241">Clean up resources</span></span>

<span data-ttu-id="089d9-242">HDInsight guarda los datos en Azure Storage, por lo que puede eliminar un clúster de forma segura cuando no se esté usando.</span><span class="sxs-lookup"><span data-stu-id="089d9-242">HDInsight saves your data in Azure Storage, so you can safely delete a cluster when it is not in use.</span></span> <span data-ttu-id="089d9-243">También se le cobrará por un clúster de HDInsight aunque no se esté usando.</span><span class="sxs-lookup"><span data-stu-id="089d9-243">You are also charged for an HDInsight cluster, even when it is not in use.</span></span> <span data-ttu-id="089d9-244">Como en muchas ocasiones los cargos por el clúster son mucho más elevados que los cargos por el almacenamiento, desde el punto de vista económico tiene sentido eliminar clústeres cuando no se estén usando.</span><span class="sxs-lookup"><span data-stu-id="089d9-244">Since the charges for the cluster are many times more than the charges for storage, it makes economic sense to delete clusters when they are not in use.</span></span>

<span data-ttu-id="089d9-245">También puede seleccionar el nombre del grupo de recursos para abrir la página del grupo de recursos y, a continuación, seleccionar **Eliminar grupo de recursos**.</span><span class="sxs-lookup"><span data-stu-id="089d9-245">You can also select the resource group name to open the resource group page, and then select **Delete resource group**.</span></span> <span data-ttu-id="089d9-246">Al eliminar el grupo de recursos, se eliminan tanto el clúster de HDInsight Spark como la cuenta de almacenamiento predeterminada.</span><span class="sxs-lookup"><span data-stu-id="089d9-246">By deleting the resource group, you delete both the HDInsight Spark cluster, and the default storage account.</span></span>

## <a name="next-steps"></a><span data-ttu-id="089d9-247">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="089d9-247">Next steps</span></span>

<span data-ttu-id="089d9-248">En este tutorial ha implementado una aplicación de .NET para Apache Spark en Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="089d9-248">In this tutorial, you deployed your .NET for Apache Spark application to Azure HDInsight.</span></span> <span data-ttu-id="089d9-249">Para más información sobre HDInsight, continúe con la documentación de Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="089d9-249">To learn more about HDInsight, continue to the Azure HDInsight Documentation.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="089d9-250">Documentación de HDInsight de Azure</span><span class="sxs-lookup"><span data-stu-id="089d9-250">Azure HDInsight Documentation</span></span>](https://docs.microsoft.com/azure/hdinsight/)
