---
title: Implementación de una aplicación de .NET para Apache Spark en Azure HDInsight
description: Aprenda a implementar una aplicación de .NET para Apache Spark en HDInsight.
ms.date: 10/09/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: f7a3b0c0d972d5cb6dbc6eea818fe794c5060eae
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "94687915"
---
# <a name="tutorial-deploy-a-net-for-apache-spark-application-to-azure-hdinsight"></a><span data-ttu-id="33184-103">Tutorial: Implementación de una aplicación de .NET para Apache Spark en Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="33184-103">Tutorial: Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>

<span data-ttu-id="33184-104">Este tutorial enseña cómo implementar la aplicación de .NET para Apache Spark en la nube a través de un clúster de Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="33184-104">This tutorial teaches you how to deploy your .NET for Apache Spark app to the cloud through an Azure HDInsight cluster.</span></span> <span data-ttu-id="33184-105">HDInsight facilita la creación y configuración de un clúster de Spark en Azure, ya que los clústeres de Spark en HDInsight son compatibles con Azure Storage y Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="33184-105">HDInsight makes it easier to create and configure a Spark cluster in Azure since Spark clusters in HDInsight are compatible with Azure Storage and Azure Data Lake Storage.</span></span>

<span data-ttu-id="33184-106">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="33184-106">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="33184-107">Obtener acceso a las cuentas de almacenamiento mediante el Explorador de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="33184-107">Access your storage accounts using Azure Storage Explorer.</span></span>
> * <span data-ttu-id="33184-108">Crear un clúster de Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="33184-108">Create an Azure HDInsight cluster.</span></span>
> * <span data-ttu-id="33184-109">Publicar la aplicación de .NET para Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="33184-109">Publish your .NET for Apache Spark app.</span></span>
> * <span data-ttu-id="33184-110">Crear y ejecutar una acción de script de HDInsight.</span><span class="sxs-lookup"><span data-stu-id="33184-110">Create and run an HDInsight script action.</span></span>
> * <span data-ttu-id="33184-111">Ejecutar una aplicación de .NET para Apache Spark en un clúster de HDInsight.</span><span class="sxs-lookup"><span data-stu-id="33184-111">Run a .NET for Apache Spark app on an HDInsight cluster.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="33184-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="33184-112">Prerequisites</span></span>

<span data-ttu-id="33184-113">Antes de empezar, haga las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="33184-113">Before you start, do the following tasks:</span></span>

* <span data-ttu-id="33184-114">Si no tiene una suscripción a Azure, cree una [cuenta gratuita](https://azure.microsoft.com/free/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="33184-114">If you don't have an Azure subscription, create a [free account](https://azure.microsoft.com/free/dotnet/).</span></span>
* <span data-ttu-id="33184-115">Inicie sesión en [Azure Portal](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="33184-115">Sign in to the [Azure portal](https://portal.azure.com/).</span></span>
* <span data-ttu-id="33184-116">Instale el Explorador de Azure Storage en el equipo [Windows](https://go.microsoft.com/fwlink/?LinkId=708343&clcid=0x409), [Linux](https://go.microsoft.com/fwlink/?LinkId=722418&clcid=0x409) o [MacOS](https://go.microsoft.com/fwlink/?LinkId=708342&clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="33184-116">Install Azure Storage Explorer on your [Windows](https://go.microsoft.com/fwlink/?LinkId=708343&clcid=0x409), [Linux](https://go.microsoft.com/fwlink/?LinkId=722418&clcid=0x409), or [MacOS](https://go.microsoft.com/fwlink/?LinkId=708342&clcid=0x409) computer.</span></span>
* <span data-ttu-id="33184-117">Complete el tutorial [.NET para Apache Spark: comenzar en 10 minutos](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro).</span><span class="sxs-lookup"><span data-stu-id="33184-117">Complete the [.NET for Apache Spark - Get Started in 10-Minutes](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) tutorial.</span></span>

## <a name="access-your-storage-accounts"></a><span data-ttu-id="33184-118">Acceso a las cuentas de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="33184-118">Access your storage accounts</span></span>

1. <span data-ttu-id="33184-119">Abra el Explorador de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="33184-119">Open Azure Storage Explorer.</span></span>

2. <span data-ttu-id="33184-120">Seleccione **Agregar cuenta** en el menú de la izquierda e inicie sesión en su cuenta de Azure.</span><span class="sxs-lookup"><span data-stu-id="33184-120">Select **Add Account** on the left menu, and sign in to your Azure account.</span></span>

    ![Inicio de sesión en la cuenta de Azure desde el Explorador de Storage](./media/hdinsight-deployment/signin-azure-storage-explorer.png)

   <span data-ttu-id="33184-122">Después de iniciar sesión, debería ver todas las cuentas de almacenamiento que tiene y los recursos que ha cargado en estas.</span><span class="sxs-lookup"><span data-stu-id="33184-122">After you sign in, you should see all storage accounts you have and any resources you have uploaded to your storage accounts.</span></span>

## <a name="create-an-hdinsight-cluster"></a><span data-ttu-id="33184-123">Creación de un clúster de HDInsight</span><span class="sxs-lookup"><span data-stu-id="33184-123">Create an HDInsight cluster</span></span>

> [!IMPORTANT]
> <span data-ttu-id="33184-124">La facturación de los clústeres de HDInsight se prorratea por minuto, incluso si no los está usando.</span><span class="sxs-lookup"><span data-stu-id="33184-124">Billing for HDInsight clusters is prorated per minute, even if you're not using them.</span></span> <span data-ttu-id="33184-125">Por consiguiente, es aconsejable eliminar el clúster al terminar de usarlo.</span><span class="sxs-lookup"><span data-stu-id="33184-125">Be sure to delete your cluster after you have finished using it.</span></span> <span data-ttu-id="33184-126">Para obtener más información, consulte la sección [Limpieza de recursos](#clean-up-resources) de este tutorial.</span><span class="sxs-lookup"><span data-stu-id="33184-126">For more information, see the [Clean up resources](#clean-up-resources) section of this tutorial.</span></span>

1. <span data-ttu-id="33184-127">Visite [Azure Portal](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="33184-127">Visit the [Azure portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="33184-128">Seleccione **+ Crear un recurso**.</span><span class="sxs-lookup"><span data-stu-id="33184-128">Select **+ Create a resource**.</span></span> <span data-ttu-id="33184-129">Después, seleccione **HDInsight** en la categoría **Análisis**.</span><span class="sxs-lookup"><span data-stu-id="33184-129">Then, select **HDInsight** from the **Analytics** category.</span></span>

    ![Creación de un recurso de HDInsight desde Azure Portal](./media/hdinsight-deployment/create-hdinsight-resource.png)

3. <span data-ttu-id="33184-131">En **Datos básicos**, proporcione los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="33184-131">Under **Basics**, provide the following values:</span></span>

    |<span data-ttu-id="33184-132">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="33184-132">Property</span></span>  |<span data-ttu-id="33184-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="33184-133">Description</span></span>  |
    |---------|---------|
    |<span data-ttu-id="33184-134">Suscripción</span><span class="sxs-lookup"><span data-stu-id="33184-134">Subscription</span></span>  | <span data-ttu-id="33184-135">En la lista desplegable, elija una de las suscripciones de Azure activas.</span><span class="sxs-lookup"><span data-stu-id="33184-135">From the drop-down, choose one of your active Azure subscriptions.</span></span> |
    |<span data-ttu-id="33184-136">Resource group</span><span class="sxs-lookup"><span data-stu-id="33184-136">Resource group</span></span> | <span data-ttu-id="33184-137">Especifique si desea crear un nuevo grupo de recursos o utilizar uno existente.</span><span class="sxs-lookup"><span data-stu-id="33184-137">Specify whether you want to create a new resource group or use an existing one.</span></span> <span data-ttu-id="33184-138">Un grupo de recursos es un contenedor que almacena los recursos relacionados con una solución de Azure.</span><span class="sxs-lookup"><span data-stu-id="33184-138">A resource group is a container that holds related resources for an Azure solution.</span></span> |
    |<span data-ttu-id="33184-139">Nombre del clúster</span><span class="sxs-lookup"><span data-stu-id="33184-139">Cluster name</span></span> | <span data-ttu-id="33184-140">Asigne un nombre al clúster de Spark de HDInsight.</span><span class="sxs-lookup"><span data-stu-id="33184-140">Give a name to your HDInsight Spark cluster.</span></span>|
    |<span data-ttu-id="33184-141">Ubicación</span><span class="sxs-lookup"><span data-stu-id="33184-141">Location</span></span>   | <span data-ttu-id="33184-142">Seleccione una ubicación para el grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="33184-142">Select a location for the resource group.</span></span> <span data-ttu-id="33184-143">La plantilla utiliza esta ubicación para crear el clúster, así como para el almacenamiento de clúster predeterminado.</span><span class="sxs-lookup"><span data-stu-id="33184-143">The template uses this location for creating the cluster as well as for the default cluster storage.</span></span> |
    |<span data-ttu-id="33184-144">Tipo de clúster</span><span class="sxs-lookup"><span data-stu-id="33184-144">Cluster type</span></span>| <span data-ttu-id="33184-145">Seleccione **Spark** como el tipo de clúster.</span><span class="sxs-lookup"><span data-stu-id="33184-145">Select **Spark** as the cluster type.</span></span>|
    |<span data-ttu-id="33184-146">Versión del clúster</span><span class="sxs-lookup"><span data-stu-id="33184-146">Cluster version</span></span>|<span data-ttu-id="33184-147">Este campo se rellenará automáticamente con la versión predeterminada una vez que se haya seleccionado el tipo de clúster.</span><span class="sxs-lookup"><span data-stu-id="33184-147">This field will autopopulate with the default version once the cluster type has been selected.</span></span> <span data-ttu-id="33184-148">Seleccione una versión 2.3 o 2.4 de Spark.</span><span class="sxs-lookup"><span data-stu-id="33184-148">Select a 2.3 or 2.4 version of Spark.</span></span>|
    |<span data-ttu-id="33184-149">Nombre de usuario de inicio de sesión del clúster</span><span class="sxs-lookup"><span data-stu-id="33184-149">Cluster login username</span></span>| <span data-ttu-id="33184-150">Escriba el nombre de usuario de inicio de sesión del clúster.</span><span class="sxs-lookup"><span data-stu-id="33184-150">Enter the cluster login username.</span></span>  <span data-ttu-id="33184-151">El nombre predeterminado es *admin*.</span><span class="sxs-lookup"><span data-stu-id="33184-151">The default name is *admin*.</span></span> |
    |<span data-ttu-id="33184-152">Contraseña de inicio de sesión de clúster</span><span class="sxs-lookup"><span data-stu-id="33184-152">Cluster login password</span></span>| <span data-ttu-id="33184-153">Escriba una contraseña de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="33184-153">Enter any login password.</span></span> |
    |<span data-ttu-id="33184-154">Nombre de usuario de Secure Shell (SSH)</span><span class="sxs-lookup"><span data-stu-id="33184-154">Secure Shell (SSH) username</span></span>| <span data-ttu-id="33184-155">Escriba el nombre de usuario de SSH.</span><span class="sxs-lookup"><span data-stu-id="33184-155">Enter the SSH username.</span></span> <span data-ttu-id="33184-156">De manera predeterminada, esta cuenta comparte la contraseña con la cuenta de *nombre de usuario de inicio de sesión del clúster*.</span><span class="sxs-lookup"><span data-stu-id="33184-156">By default, this account shares the same password as the *Cluster Login username* account.</span></span> |

4. <span data-ttu-id="33184-157">Seleccione **Siguiente: Almacenamiento>>** para continuar en la página **Almacenamiento**.</span><span class="sxs-lookup"><span data-stu-id="33184-157">Select **Next: Storage >>** to continue to the **Storage** page.</span></span> <span data-ttu-id="33184-158">En **Almacenamiento**, proporcione los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="33184-158">Under **Storage**, provide the following values:</span></span>

    |<span data-ttu-id="33184-159">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="33184-159">Property</span></span>  |<span data-ttu-id="33184-160">Descripción</span><span class="sxs-lookup"><span data-stu-id="33184-160">Description</span></span>  |
    |---------|---------|
    |<span data-ttu-id="33184-161">Tipo de almacenamiento principal</span><span class="sxs-lookup"><span data-stu-id="33184-161">Primary storage type</span></span>|<span data-ttu-id="33184-162">Use el valor predeterminado **Azure Storage**.</span><span class="sxs-lookup"><span data-stu-id="33184-162">Use the default value **Azure Storage**.</span></span>|
    |<span data-ttu-id="33184-163">Método de selección</span><span class="sxs-lookup"><span data-stu-id="33184-163">Selection method</span></span>|<span data-ttu-id="33184-164">Use el valor predeterminado **Seleccionar de la lista**.</span><span class="sxs-lookup"><span data-stu-id="33184-164">Use the default value **Select from list**.</span></span>|
    |<span data-ttu-id="33184-165">Cuenta de almacenamiento principal</span><span class="sxs-lookup"><span data-stu-id="33184-165">Primary storage account</span></span>|<span data-ttu-id="33184-166">Elija su suscripción y una de sus cuentas de almacenamiento activas en esa suscripción.</span><span class="sxs-lookup"><span data-stu-id="33184-166">Choose your subscription and one of your active storage accounts within that subscription.</span></span>|
    |<span data-ttu-id="33184-167">Contenedor</span><span class="sxs-lookup"><span data-stu-id="33184-167">Container</span></span>|<span data-ttu-id="33184-168">Este contenedor es el contenedor de blobs específico de la cuenta de almacenamiento en la que el clúster busca archivos para ejecutar la aplicación en la nube.</span><span class="sxs-lookup"><span data-stu-id="33184-168">This container is the specific blob container in your storage account where your cluster looks for files to run your app in the cloud.</span></span> <span data-ttu-id="33184-169">Puede asignarle cualquier nombre disponible.</span><span class="sxs-lookup"><span data-stu-id="33184-169">You can give it any available name.</span></span>|

5. <span data-ttu-id="33184-170">Seleccione **Revisar y crear** y, después, **Crear**.</span><span class="sxs-lookup"><span data-stu-id="33184-170">Under **Review + create**, select **Create**.</span></span> <span data-ttu-id="33184-171">La creación del clúster tarda aproximadamente 20 minutos.</span><span class="sxs-lookup"><span data-stu-id="33184-171">It takes about 20 minutes to create the cluster.</span></span> <span data-ttu-id="33184-172">Se debe crear el clúster para poder continuar con el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="33184-172">The cluster must be created before you can continue to the next step.</span></span>

## <a name="publish-your-app"></a><span data-ttu-id="33184-173">Publicar la aplicación</span><span class="sxs-lookup"><span data-stu-id="33184-173">Publish your app</span></span>

<span data-ttu-id="33184-174">Luego, publique la aplicación *mySparkApp* creada en el tutorial [.NET para Apache Spark: comenzar en 10 minutos](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro), que proporciona acceso al clúster de Spark a todos los archivos que necesita para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="33184-174">Next, you publish the *mySparkApp* created in the [.NET for Apache Spark - Get Started in 10-Minutes](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) tutorial, which gives your Spark cluster access to all the files it needs to run your app.</span></span>

1. <span data-ttu-id="33184-175">Para publicar *mySparkApp*, ejecute los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="33184-175">Run the following commands to publish the *mySparkApp*:</span></span>

   <span data-ttu-id="33184-176">**En Windows:**</span><span class="sxs-lookup"><span data-stu-id="33184-176">**On Windows:**</span></span>

   ```dotnetcli
   cd mySparkApp
   dotnet publish -c Release -f netcoreapp3.1 -r win-x64
   ```

   <span data-ttu-id="33184-177">**En Linux:**</span><span class="sxs-lookup"><span data-stu-id="33184-177">**On Linux:**</span></span>

   ```bash
   cd mySparkApp
   foo@bar:~/path/to/app$ dotnet publish -c Release -f netcoreapp3.1 -r ubuntu.16.04-x64
   ```

2. <span data-ttu-id="33184-178">Realice las tareas siguientes para comprimir los archivos de la aplicación publicados para que pueda cargarlos fácilmente en el clúster de HDInsight.</span><span class="sxs-lookup"><span data-stu-id="33184-178">Do the following tasks to zip your published app files so that you can easily upload them to your HDInsight cluster.</span></span> <span data-ttu-id="33184-179">Comprima el contenido de la carpeta de publicación, *publish.zip*, por ejemplo, que se ha creado como resultado del paso 1.</span><span class="sxs-lookup"><span data-stu-id="33184-179">Zip the contents of the publish folder, *publish.zip* for example, that was created as a result of Step 1.</span></span> <span data-ttu-id="33184-180">Todos los elementos ensamblados deben estar en la primera capa del archivo ZIP y no debe haber ninguna capa de carpeta intermedia.</span><span class="sxs-lookup"><span data-stu-id="33184-180">All the assemblies should be in the first layer of the ZIP file and there should be no intermediate folder layer.</span></span> <span data-ttu-id="33184-181">Esto significa que, al descomprimir *publish.zip*, todos los ensamblados se extraen en el directorio de trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="33184-181">This means when you unzip *publish.zip*, all assemblies are extracted into your current working directory.</span></span>

   <span data-ttu-id="33184-182">**En Windows:**</span><span class="sxs-lookup"><span data-stu-id="33184-182">**On Windows:**</span></span>

   <span data-ttu-id="33184-183">Use un programa de extracción, como 7-zip o WinZip, para extraer el archivo en el directorio bin con todos los archivos binarios publicados.</span><span class="sxs-lookup"><span data-stu-id="33184-183">Use an extraction program, like 7-Zip or WinZip, to extract the file into the bin directory with all the published binaries.</span></span>

   <span data-ttu-id="33184-184">**En Linux, ejecute el comando siguiente:**</span><span class="sxs-lookup"><span data-stu-id="33184-184">**On Linux, run the following command:**</span></span>

   ```bash
   zip -r publish.zip
   ```

## <a name="upload-files-to-azure"></a><span data-ttu-id="33184-185">Carga de archivos en Azure</span><span class="sxs-lookup"><span data-stu-id="33184-185">Upload files to Azure</span></span>

<span data-ttu-id="33184-186">Después, use el Explorador de Azure Storage para cargar los cinco archivos siguientes en el contenedor de blobs que se ha elegido para el almacenamiento del clúster:</span><span class="sxs-lookup"><span data-stu-id="33184-186">Next, you use the Azure Storage Explorer to upload the following five files to the blob container you chose for your cluster's storage:</span></span>

* <span data-ttu-id="33184-187">Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="33184-187">Microsoft.Spark.Worker</span></span>
* <span data-ttu-id="33184-188">install-worker.sh</span><span class="sxs-lookup"><span data-stu-id="33184-188">install-worker.sh</span></span>
* <span data-ttu-id="33184-189">publish.zip</span><span class="sxs-lookup"><span data-stu-id="33184-189">publish.zip</span></span>
* <span data-ttu-id="33184-190">microsoft-spark-2-4_2.11-1.0.0.jar</span><span class="sxs-lookup"><span data-stu-id="33184-190">microsoft-spark-2-4_2.11-1.0.0.jar</span></span>
* <span data-ttu-id="33184-191">input.txt</span><span class="sxs-lookup"><span data-stu-id="33184-191">input.txt</span></span>

1. <span data-ttu-id="33184-192">Abra el Explorador de Azure Storage y vaya a la cuenta de almacenamiento en el menú de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="33184-192">Open Azure Storage Explorer and navigate to your storage account from the left menu.</span></span> <span data-ttu-id="33184-193">Explore en profundidad el contenedor de blobs del clúster en **Contenedores de blobs** en su cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="33184-193">Drill down to the blob container for your cluster under **Blob Containers** in your storage account.</span></span>

2. <span data-ttu-id="33184-194">*Microsoft.Spark.Worker* ayuda a Apache Spark a ejecutar la aplicación, como cualquier función definida por el usuario (UDF) que se haya escrito.</span><span class="sxs-lookup"><span data-stu-id="33184-194">*Microsoft.Spark.Worker* helps Apache Spark execute your app, such as any user-defined functions (UDFs) you may have written.</span></span> <span data-ttu-id="33184-195">Descargue [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases/download/v1.0.0/Microsoft.Spark.Worker.netcoreapp3.1.linux-x64-1.0.0.tar.gz).</span><span class="sxs-lookup"><span data-stu-id="33184-195">Download [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases/download/v1.0.0/Microsoft.Spark.Worker.netcoreapp3.1.linux-x64-1.0.0.tar.gz).</span></span> <span data-ttu-id="33184-196">Luego seleccione **Cargar** en el Explorador de Azure Storage para cargar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="33184-196">Then, select **Upload** in Azure Storage Explorer to upload the worker.</span></span>

   ![Carga de archivos en el Explorador de Azure Storage](./media/hdinsight-deployment/upload-files-to-storage.png)

3. <span data-ttu-id="33184-198">*install-worker.sh* es un script que permite copiar archivos dependientes de .NET para Apache Spark en los nodos del clúster.</span><span class="sxs-lookup"><span data-stu-id="33184-198">The *install-worker.sh* is a script that lets you copy .NET for Apache Spark dependent files into the nodes of your cluster.</span></span>

   <span data-ttu-id="33184-199">Cree un archivo con el nombre **install-worker.sh** en el equipo local y pegue el [contenido de install-worker.sh](https://raw.githubusercontent.com/dotnet/spark/master/deployment/install-worker.sh) que se encuentra en GitHub.</span><span class="sxs-lookup"><span data-stu-id="33184-199">Create a new file named **install-worker.sh** in your local computer, and paste the [install-worker.sh contents](https://raw.githubusercontent.com/dotnet/spark/master/deployment/install-worker.sh) located on GitHub.</span></span> <span data-ttu-id="33184-200">Después, cargue *install-worker.sh* en el contenedor de blobs.</span><span class="sxs-lookup"><span data-stu-id="33184-200">Then, upload *install-worker.sh* to your blob container.</span></span>

4. <span data-ttu-id="33184-201">El clúster necesita el archivo *publish.zip* que contiene los archivos publicados de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="33184-201">Your cluster needs the *publish.zip* file that contains your app's published files.</span></span> <span data-ttu-id="33184-202">Vaya a la carpeta publicada, **mySparkApp/bin/Release/netcoreapp3.1/ubuntu.16.04-x64**, y busque **publish.zip**.</span><span class="sxs-lookup"><span data-stu-id="33184-202">Navigate to your published folder, **mySparkApp/bin/Release/netcoreapp3.1/ubuntu.16.04-x64**, and locate **publish.zip**.</span></span> <span data-ttu-id="33184-203">Después, cargue *publish.zip* en el contenedor de blobs.</span><span class="sxs-lookup"><span data-stu-id="33184-203">Then upload *publish.zip* to your blob container.</span></span>

5. <span data-ttu-id="33184-204">El clúster necesita el código de la aplicación que se ha empaquetado como un archivo jar, incluido como parte del paquete NuGet [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) y que se ha colocado en el directorio de salida de compilación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="33184-204">Your cluster needs the application code that is packaged as a jar, included as part of the [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) nuget and colocated in your app's build output directory.</span></span> <span data-ttu-id="33184-205">Vaya a la carpeta publicada, **mySparkApp/bin/Release/netcoreapp3.1/ubuntu.16.04-x64**, y busque **microsoft-spark-2-4_2.11-1.0.0.jar**.</span><span class="sxs-lookup"><span data-stu-id="33184-205">Navigate to your published folder, **mySparkApp/bin/Release/netcoreapp3.1/ubuntu.16.04-x64**, and locate **microsoft-spark-2-4_2.11-1.0.0.jar**.</span></span> <span data-ttu-id="33184-206">Después, cargue el archivo jar en el contenedor de blobs.</span><span class="sxs-lookup"><span data-stu-id="33184-206">Then, upload the jar file to your blob container.</span></span>

   <span data-ttu-id="33184-207">Puede haber varios archivos .jar (para las versiones 2.3.x, 2.4.x y 3.0.x de Spark).</span><span class="sxs-lookup"><span data-stu-id="33184-207">There may be multiple .jar files (for versions 2.3.x, 2.4.x and 3.0.x of Spark).</span></span> <span data-ttu-id="33184-208">Debe elegir el archivo .jar que coincida con la versión de Spark que se haya elegido durante la creación del clúster.</span><span class="sxs-lookup"><span data-stu-id="33184-208">You need to choose the .jar file that matches the version of Spark you chose during cluster creation.</span></span> <span data-ttu-id="33184-209">Por ejemplo, elija *microsoft-spark-2-4_2.11-1.0.0.jar* si ha elegido Spark 2.4 durante la creación del clúster.</span><span class="sxs-lookup"><span data-stu-id="33184-209">For example, choose *microsoft-spark-2-4_2.11-1.0.0.jar* if you chose Spark 2.4 during cluster creation.</span></span>

6. <span data-ttu-id="33184-210">El clúster necesita la entrada a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="33184-210">Your cluster needs the input to your app.</span></span> <span data-ttu-id="33184-211">Vaya al directorio **mySparkApp** y busque **input.txt**.</span><span class="sxs-lookup"><span data-stu-id="33184-211">Navigate to your **mySparkApp** directory and locate **input.txt**.</span></span> <span data-ttu-id="33184-212">Cargue el archivo de entrada en el directorio **user/sshuser** en el contenedor de blobs.</span><span class="sxs-lookup"><span data-stu-id="33184-212">Upload your input file to the **user/sshuser** directory in your blob container.</span></span> <span data-ttu-id="33184-213">Se conectará al clúster mediante SSH y en esta carpeta es donde el clúster buscará su entrada.</span><span class="sxs-lookup"><span data-stu-id="33184-213">You will be connecting to your cluster through ssh, and this folder is where your cluster looks for its input.</span></span> <span data-ttu-id="33184-214">El archivo *input.txt* es el único archivo que se carga en un directorio concreto.</span><span class="sxs-lookup"><span data-stu-id="33184-214">The *input.txt* file is the only file uploaded to a specific directory.</span></span>

## <a name="run-the-hdinsight-script-action"></a><span data-ttu-id="33184-215">Ejecución de la acción de script de HDInsight</span><span class="sxs-lookup"><span data-stu-id="33184-215">Run the HDInsight script action</span></span>

<span data-ttu-id="33184-216">Cuando el clúster se esté ejecutando y haya cargado los archivos en Azure, ejecute el script **install-worker.sh** en el clúster.</span><span class="sxs-lookup"><span data-stu-id="33184-216">Once your cluster is running and you've uploaded your files to Azure, you run the **install-worker.sh** script on the cluster.</span></span>

1. <span data-ttu-id="33184-217">Vaya al clúster de HDInsight de Spark en Azure Portal y luego seleccione **Acciones de script**.</span><span class="sxs-lookup"><span data-stu-id="33184-217">Navigate to your HDInsight Spark cluster in Azure portal, and then select **Script actions**.</span></span>

2. <span data-ttu-id="33184-218">Seleccione **+ Enviar nuevo** y proporcione los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="33184-218">Select **+ Submit new** and provide the following values:</span></span>

   |<span data-ttu-id="33184-219">Propiedad</span><span class="sxs-lookup"><span data-stu-id="33184-219">Property</span></span>  |<span data-ttu-id="33184-220">Descripción</span><span class="sxs-lookup"><span data-stu-id="33184-220">Description</span></span>  |
   |---------|---------|
   | <span data-ttu-id="33184-221">Tipo de script</span><span class="sxs-lookup"><span data-stu-id="33184-221">Script type</span></span> |<span data-ttu-id="33184-222">Personalizados</span><span class="sxs-lookup"><span data-stu-id="33184-222">Custom</span></span>|
   | <span data-ttu-id="33184-223">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="33184-223">Name</span></span> | <span data-ttu-id="33184-224">Instalación del trabajo</span><span class="sxs-lookup"><span data-stu-id="33184-224">Install Worker</span></span>|
   | <span data-ttu-id="33184-225">URI de script de Bash</span><span class="sxs-lookup"><span data-stu-id="33184-225">Bash script URI</span></span> |`https://mystorageaccount.blob.core.windows.net/mycontainer/install-worker.sh` </br> <span data-ttu-id="33184-226">Para confirmar este URI, haga clic con el botón derecho en install-worker.sh en el Explorador de Azure Storage y seleccione Propiedades.</span><span class="sxs-lookup"><span data-stu-id="33184-226">To confirm this URI, right-click on install-worker.sh in Azure Storage Explorer and select Properties.</span></span> |
   | <span data-ttu-id="33184-227">Tipos de nodo</span><span class="sxs-lookup"><span data-stu-id="33184-227">Node type(s)</span></span>| <span data-ttu-id="33184-228">Trabajo</span><span class="sxs-lookup"><span data-stu-id="33184-228">Worker</span></span>|
   | <span data-ttu-id="33184-229">Parámetros</span><span class="sxs-lookup"><span data-stu-id="33184-229">Parameters</span></span> | <span data-ttu-id="33184-230">azure</span><span class="sxs-lookup"><span data-stu-id="33184-230">azure</span></span> </br> wasbs://mycontainer@myStorageAccount.blob.core.windows.net/Microsoft.Spark.Worker.netcoreapp3.1.linux-x64-1.0.0.tar.gz </br> <span data-ttu-id="33184-231">/usr/local/bin</span><span class="sxs-lookup"><span data-stu-id="33184-231">/usr/local/bin</span></span>

3. <span data-ttu-id="33184-232">Seleccione **Crear** para enviar el script.</span><span class="sxs-lookup"><span data-stu-id="33184-232">Select **Create** to submit your script.</span></span>

## <a name="run-your-app"></a><span data-ttu-id="33184-233">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="33184-233">Run your app</span></span>

1. <span data-ttu-id="33184-234">Vaya al clúster de HDInsight de Spark en Azure Portal y luego seleccione **SSH e inicio de sesión del clúster**.</span><span class="sxs-lookup"><span data-stu-id="33184-234">Navigate to your HDInsight Spark cluster in Azure portal, and then select **SSH + Cluster login**.</span></span>

2. <span data-ttu-id="33184-235">Copie la información de inicio de sesión de SSH y pegue el inicio de sesión en un terminal.</span><span class="sxs-lookup"><span data-stu-id="33184-235">Copy the ssh login information and paste the login into a terminal.</span></span> <span data-ttu-id="33184-236">Inicie sesión en el clúster con la contraseña que se ha establecido durante la creación del clúster.</span><span class="sxs-lookup"><span data-stu-id="33184-236">Sign in to your cluster using the password you set during cluster creation.</span></span> <span data-ttu-id="33184-237">Debería ver mensajes de bienvenida a Ubuntu y Spark.</span><span class="sxs-lookup"><span data-stu-id="33184-237">You should see messages welcoming you to Ubuntu and Spark.</span></span>

3. <span data-ttu-id="33184-238">Use el comando **spark-submit** para ejecutar la aplicación en el clúster de HDInsight.</span><span class="sxs-lookup"><span data-stu-id="33184-238">Use the **spark-submit** command to run your app on your HDInsight cluster.</span></span> <span data-ttu-id="33184-239">Recuerde reemplazar **mycontainer** y **mystorageaccount** en el script de ejemplo con los nombres reales del contenedor de blobs y la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="33184-239">Remember to replace **mycontainer** and **mystorageaccount** in the example script with the actual names of your blob container and storage account.</span></span>

   ```bash
   $SPARK_HOME/bin/spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/microsoft-spark-2-4_2.11-1.0.0.jar \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/publish.zip mySparkApp
   ```

   <span data-ttu-id="33184-240">Cuando la aplicación se ejecute, verá la misma tabla de recuento de palabras de la ejecución local de introducción escrita en la consola.</span><span class="sxs-lookup"><span data-stu-id="33184-240">When your app runs, you see the same word count table from the getting started local run written to the console.</span></span> <span data-ttu-id="33184-241">Enhorabuena, ha ejecutado su primera aplicación de .NET para Apache Spark en la nube.</span><span class="sxs-lookup"><span data-stu-id="33184-241">Congratulations, you've run your first .NET for Apache Spark application in the cloud!</span></span>

## <a name="clean-up-resources"></a><span data-ttu-id="33184-242">Limpiar los recursos</span><span class="sxs-lookup"><span data-stu-id="33184-242">Clean up resources</span></span>

<span data-ttu-id="33184-243">HDInsight guarda los datos en Azure Storage, por lo que puede eliminar un clúster de forma segura cuando no se esté usando.</span><span class="sxs-lookup"><span data-stu-id="33184-243">HDInsight saves your data in Azure Storage, so you can safely delete a cluster when it is not in use.</span></span> <span data-ttu-id="33184-244">También se le cobrará por un clúster de HDInsight aunque no se esté usando.</span><span class="sxs-lookup"><span data-stu-id="33184-244">You are also charged for an HDInsight cluster, even when it is not in use.</span></span> <span data-ttu-id="33184-245">Como en muchas ocasiones los cargos por el clúster son mucho más elevados que los cargos por el almacenamiento, desde el punto de vista económico tiene sentido eliminar clústeres cuando no se estén usando.</span><span class="sxs-lookup"><span data-stu-id="33184-245">Since the charges for the cluster are many times more than the charges for storage, it makes economic sense to delete clusters when they are not in use.</span></span>

<span data-ttu-id="33184-246">También puede seleccionar el nombre del grupo de recursos para abrir la página del grupo de recursos y, a continuación, seleccionar **Eliminar grupo de recursos**.</span><span class="sxs-lookup"><span data-stu-id="33184-246">You can also select the resource group name to open the resource group page, and then select **Delete resource group**.</span></span> <span data-ttu-id="33184-247">Al eliminar el grupo de recursos, se eliminan tanto el clúster de HDInsight Spark como la cuenta de almacenamiento predeterminada.</span><span class="sxs-lookup"><span data-stu-id="33184-247">By deleting the resource group, you delete both the HDInsight Spark cluster, and the default storage account.</span></span>

## <a name="next-steps"></a><span data-ttu-id="33184-248">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="33184-248">Next steps</span></span>

<span data-ttu-id="33184-249">En este tutorial ha implementado una aplicación de .NET para Apache Spark en Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="33184-249">In this tutorial, you deployed your .NET for Apache Spark application to Azure HDInsight.</span></span> <span data-ttu-id="33184-250">Para más información sobre HDInsight, continúe con la documentación de Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="33184-250">To learn more about HDInsight, continue to the Azure HDInsight Documentation.</span></span>

> [!div class="nextstepaction"]
> <span data-ttu-id="33184-251">[Envío de trabajos de forma remota en Azure HDInsight](../how-to-guides/hdinsight-deploy-methods.md)
> [Documentación de Azure HDInsight](/azure/hdinsight/)</span><span class="sxs-lookup"><span data-stu-id="33184-251">[Submit jobs remotely on Azure HDInsight](../how-to-guides/hdinsight-deploy-methods.md)
[Azure HDInsight Documentation](/azure/hdinsight/)</span></span>
