---
title: Instalación de .NET para Apache Spark en cuadernos de Jupyter Notebook en clústeres de Azure HDInsight Spark
description: Aprenda a instalar .NET para Apache Spark en cuadernos de Jupyter de Azure HDInsight.
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 100991a5c6e07f9e7c21a64f53310f91d381873c
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104875504"
---
# <a name="install-net-for-apache-spark-on-jupyter-notebooks-on-azure-hdinsight-spark-clusters"></a><span data-ttu-id="bc907-103">Instalación de .NET para Apache Spark en cuadernos de Jupyter Notebook en clústeres de Azure HDInsight Spark</span><span class="sxs-lookup"><span data-stu-id="bc907-103">Install .NET for Apache Spark on Jupyter Notebooks on Azure HDInsight Spark clusters</span></span>

<span data-ttu-id="bc907-104">En este artículo se muestra cómo instalar .NET para Apache Spark en cuadernos de Jupyter Notebook en clústeres de Azure HDInsight Spark.</span><span class="sxs-lookup"><span data-stu-id="bc907-104">This article teaches you how to install .NET for Apache Spark on Jupyter Notebooks on Azure HDInsight Spark clusters.</span></span> <span data-ttu-id="bc907-105">Puede implementar .NET para Apache Spark en clústeres de Azure HDInsight mediante una combinación de la línea de comandos y Azure Portal (para más información, consulte [Implementación de una aplicación de .NET para Apache Spark en Azure HDInsight](../tutorials/hdinsight-deployment.md)), pero los cuadernos proporcionan una experiencia más interactiva e iterativa.</span><span class="sxs-lookup"><span data-stu-id="bc907-105">You can deploy .NET for Apache Spark on Azure HDInsight clusters through a combination of the command line and the Azure portal (for more information, see [how to deploy a .NET for Apache Spark application to Azure HDInsight](../tutorials/hdinsight-deployment.md)), but notebooks provide a more interactive and iterative experience.</span></span>

<span data-ttu-id="bc907-106">Los clústeres de Azure HDInsight ya incluyen cuadernos de Jupyter Notebook, así que todo lo que tiene que hacer es configurar estos para ejecutar .NET para Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="bc907-106">Azure HDInsight clusters already come with Jupyter Notebooks, so all you have to do is configure the Jupyter Notebooks to run .NET for Apache Spark.</span></span> <span data-ttu-id="bc907-107">Para usar .NET para Apache Spark en los cuadernos de Jupyter Notebook, se necesita un REPL de C# para ejecutar el código de C# línea por línea y conservar el estado de ejecución cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="bc907-107">To use .NET for Apache Spark in your Jupyter Notebooks, a C# REPL is needed to execute your C# code line-by-line and to preserve execution state when necessary.</span></span> <span data-ttu-id="bc907-108">[Try .NET](https://github.com/dotnet/try) se ha integrado como el REPL oficial de .NET.</span><span class="sxs-lookup"><span data-stu-id="bc907-108">[Try .NET](https://github.com/dotnet/try) has been integrated as the official .NET REPL.</span></span>

<span data-ttu-id="bc907-109">Para habilitar .NET para Apache Spark mediante la experiencia de Jupyter Notebooks, debe seguir algunos pasos manuales por medio de [Ambari](/azure/hdinsight/hdinsight-hadoop-manage-ambari) y enviar [acciones de script](/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux) en el clúster de HDInsight Spark.</span><span class="sxs-lookup"><span data-stu-id="bc907-109">To enable .NET for Apache Spark through the Jupyter Notebooks experience, you need to follow a few manual steps through [Ambari](/azure/hdinsight/hdinsight-hadoop-manage-ambari) and submit [script actions](/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux) on the HDInsight Spark cluster.</span></span>

> [!NOTE]
> <span data-ttu-id="bc907-110">Esta característica es *experimental* y el equipo de HDInsight Spark no la admite.</span><span class="sxs-lookup"><span data-stu-id="bc907-110">This feature is *experimental* and is not supported by the HDInsight Spark team.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bc907-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="bc907-111">Prerequisites</span></span>

<span data-ttu-id="bc907-112">Si aún no tiene uno, cree un clúster de [Azure HDInsight Spark](/azure/hdinsight/spark/apache-spark-jupyter-spark-sql-use-portal#create-an-apache-spark-cluster-in-hdinsight).</span><span class="sxs-lookup"><span data-stu-id="bc907-112">If you don't already have one, create an [Azure HDInsight Spark](/azure/hdinsight/spark/apache-spark-jupyter-spark-sql-use-portal#create-an-apache-spark-cluster-in-hdinsight) cluster.</span></span>

1. <span data-ttu-id="bc907-113">Vaya a [Azure Portal](https://portal.azure.com) y seleccione **+ Crear un recurso**.</span><span class="sxs-lookup"><span data-stu-id="bc907-113">Visit the [Azure portal](https://portal.azure.com) and select **+ Create a Resource**.</span></span>

1. <span data-ttu-id="bc907-114">Cree un recurso de clúster de Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="bc907-114">Create a new Azure HDInsight cluster resource.</span></span> <span data-ttu-id="bc907-115">Seleccione **Spark 2.4** y **HDI 4.0** durante la creación del clúster.</span><span class="sxs-lookup"><span data-stu-id="bc907-115">Select **Spark 2.4** and **HDI 4.0** during cluster creation.</span></span>

## <a name="install-net-for-apache-spark"></a><span data-ttu-id="bc907-116">Instalación de .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="bc907-116">Install .NET for Apache Spark</span></span>

<span data-ttu-id="bc907-117">En Azure Portal, seleccione el **clúster de HDInsight Spark** que creó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="bc907-117">In the Azure portal, select the **HDInsight Spark cluster** you created in the previous step.</span></span>

### <a name="stop-the-livy-server"></a><span data-ttu-id="bc907-118">Detención del servidor de Livy</span><span class="sxs-lookup"><span data-stu-id="bc907-118">Stop the Livy server</span></span>

1. <span data-ttu-id="bc907-119">En el portal, seleccione **Información general** y, luego, la **página de inicio de Ambari**.</span><span class="sxs-lookup"><span data-stu-id="bc907-119">From the portal, select **Overview**, and then select **Ambari home**.</span></span> <span data-ttu-id="bc907-120">Cuando se le pida, escriba las credenciales de inicio de sesión del clúster.</span><span class="sxs-lookup"><span data-stu-id="bc907-120">If prompted, enter the login credentials for the cluster.</span></span>

   ![Seleccione Página principal de Ambari en Paneles de clústeres.](./media/hdinsight-notebook-installation/select-ambari.png)

2. <span data-ttu-id="bc907-122">Seleccione **Spark2** en el menú de navegación izquierdo y, luego, **LIVY FOR SPARK2 SERVER** (LIVY PARA EL SERVIDOR SPARK2).</span><span class="sxs-lookup"><span data-stu-id="bc907-122">Select **Spark2** from the left navigation menu, and select **LIVY FOR SPARK2 SERVER**.</span></span>

   ![Seleccione Livy para el servidor Spark2.](./media/hdinsight-notebook-installation/select-livyserver.png)

3. <span data-ttu-id="bc907-124">Seleccione **hn0... host**.</span><span class="sxs-lookup"><span data-stu-id="bc907-124">Select **hn0... host**.</span></span>

   ![Hosts en los que se muestra "hno..." seleccionado](./media/hdinsight-notebook-installation/select-host.png)

4. <span data-ttu-id="bc907-126">Seleccione los puntos suspensivos junto a **Livy for Spark2 Server** (Livy para el servidor Spark2) y elija **Detener**.</span><span class="sxs-lookup"><span data-stu-id="bc907-126">Select the ellipsis next to **Livy for Spark2 Server** and select **Stop**.</span></span> <span data-ttu-id="bc907-127">Cuando se le solicite, seleccione **Aceptar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="bc907-127">When prompted, select **OK** to proceed.</span></span>

   <span data-ttu-id="bc907-128">Detención de Livy para el servidor Spark2.</span><span class="sxs-lookup"><span data-stu-id="bc907-128">Stop Livy for Spark2 Server.</span></span>
   <span data-ttu-id="bc907-129">![Seleccione los puntos suspensivos y después Detener](./media/hdinsight-notebook-installation/stop-server.png)</span><span class="sxs-lookup"><span data-stu-id="bc907-129">![Select the ellipsis and then Stop](./media/hdinsight-notebook-installation/stop-server.png)</span></span>

5. <span data-ttu-id="bc907-130">Repita los pasos anteriores para **hn1... host**.</span><span class="sxs-lookup"><span data-stu-id="bc907-130">Repeat the previous steps for **hn1... host**.</span></span>

### <a name="submit-an-hdinsight-script-action"></a><span data-ttu-id="bc907-131">Envío de una acción de script de HDInsight</span><span class="sxs-lookup"><span data-stu-id="bc907-131">Submit an HDInsight script action</span></span>

1. <span data-ttu-id="bc907-132">`install-interactive-notebook.sh` es un script que instala .NET para Apache Spark y realiza cambios en Apache Livy y sparkmagic.</span><span class="sxs-lookup"><span data-stu-id="bc907-132">The `install-interactive-notebook.sh` is a script that installs .NET for Apache Spark and makes changes to Apache Livy and sparkmagic.</span></span> <span data-ttu-id="bc907-133">Antes de enviar una acción de script a HDInsight, debe crear y cargar `install-interactive-notebook.sh`.</span><span class="sxs-lookup"><span data-stu-id="bc907-133">Before you submit a script action to HDInsight, you need to create and upload `install-interactive-notebook.sh`.</span></span>

   <span data-ttu-id="bc907-134">Cree un archivo llamado **install-interactive-notebook.sh** en el equipo local y pegue el contenido de [install-interactive-notebook.sh contents](https://raw.githubusercontent.com/dotnet/spark/main/deployment/HDI-Spark/Notebooks/install-interactive-notebook.sh).</span><span class="sxs-lookup"><span data-stu-id="bc907-134">Create a new file named **install-interactive-notebook.sh** in your local computer and paste the contents of [install-interactive-notebook.sh contents](https://raw.githubusercontent.com/dotnet/spark/main/deployment/HDI-Spark/Notebooks/install-interactive-notebook.sh).</span></span>

   <span data-ttu-id="bc907-135">Cargue el script en un [URI](/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux#understand-script-actions) que sea accesible desde el clúster de HDInsight.</span><span class="sxs-lookup"><span data-stu-id="bc907-135">Upload the script to a [URI](/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux#understand-script-actions) that's accessible from the HDInsight cluster.</span></span> <span data-ttu-id="bc907-136">Por ejemplo: `https://<my storage account>.blob.core.windows.net/<my container>/<some dir>/install-interactive-notebook.sh`.</span><span class="sxs-lookup"><span data-stu-id="bc907-136">For example, `https://<my storage account>.blob.core.windows.net/<my container>/<some dir>/install-interactive-notebook.sh`.</span></span>

2. <span data-ttu-id="bc907-137">Ejecute `install-interactive-notebook.sh` en el clúster con las [acciones de script de HDInsight](/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux).</span><span class="sxs-lookup"><span data-stu-id="bc907-137">Run `install-interactive-notebook.sh` on the cluster using [HDInsight Script Actions](/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux).</span></span>

   <span data-ttu-id="bc907-138">Vuelva al clúster de HDI en Azure Portal y seleccione **Acciones de script** en las opciones de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="bc907-138">Return to your HDI cluster in the Azure portal, and select **Script actions** from the options on the left.</span></span> <span data-ttu-id="bc907-139">Se envía una acción de script para implementar el REPL de .NET para Apache Spark en el clúster de HDInsight Spark.</span><span class="sxs-lookup"><span data-stu-id="bc907-139">You submit one script action to deploy the .NET for Apache Spark REPL on your HDInsight Spark cluster.</span></span> <span data-ttu-id="bc907-140">Use la configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="bc907-140">Use the following settings:</span></span>

   |<span data-ttu-id="bc907-141">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="bc907-141">Property</span></span>  |<span data-ttu-id="bc907-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="bc907-142">Description</span></span>  |
   |---------|---------|
   | <span data-ttu-id="bc907-143">Tipo de script</span><span class="sxs-lookup"><span data-stu-id="bc907-143">Script type</span></span> | <span data-ttu-id="bc907-144">Personalizados</span><span class="sxs-lookup"><span data-stu-id="bc907-144">Custom</span></span> |
   | <span data-ttu-id="bc907-145">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="bc907-145">Name</span></span> | <span data-ttu-id="bc907-146">*Instalación de la experiencia interactiva de cuadernos de .NET para Apache Spark*</span><span class="sxs-lookup"><span data-stu-id="bc907-146">*Install .NET for Apache Spark Interactive Notebook Experience*</span></span> |
   | <span data-ttu-id="bc907-147">URI de script de Bash</span><span class="sxs-lookup"><span data-stu-id="bc907-147">Bash script URI</span></span> | <span data-ttu-id="bc907-148">El URI en el que cargó `install-interactive-notebook.sh`.</span><span class="sxs-lookup"><span data-stu-id="bc907-148">The URI to which you uploaded `install-interactive-notebook.sh`.</span></span> |
   | <span data-ttu-id="bc907-149">Tipos de nodo</span><span class="sxs-lookup"><span data-stu-id="bc907-149">Node type(s)</span></span>| <span data-ttu-id="bc907-150">Principal y de trabajo</span><span class="sxs-lookup"><span data-stu-id="bc907-150">Head and Worker</span></span> |
   | <span data-ttu-id="bc907-151">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bc907-151">Parameters</span></span> | <span data-ttu-id="bc907-152">Versión de .NET para Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="bc907-152">.NET for Apache Spark version.</span></span> <span data-ttu-id="bc907-153">Puede comprobar las [versiones de .NET para Apache Spark](https://github.com/dotnet/spark/releases).</span><span class="sxs-lookup"><span data-stu-id="bc907-153">You can check [.NET for Apache Spark releases](https://github.com/dotnet/spark/releases).</span></span> <span data-ttu-id="bc907-154">Por ejemplo, si quiere instalar la versión 1.0.0 de Sparkdotnet, sería `1.0.0`.</span><span class="sxs-lookup"><span data-stu-id="bc907-154">For example, if you want to install Sparkdotnet version 1.0.0 then it would be `1.0.0`.</span></span>

   <span data-ttu-id="bc907-155">Cuando aparezcan marcas de verificación verdes junto al estado de la acción de script, vaya al siguiente paso.</span><span class="sxs-lookup"><span data-stu-id="bc907-155">Move to the next step when green checkmarks appear next to the status of the script action.</span></span>

### <a name="start-the-livy-server"></a><span data-ttu-id="bc907-156">Inicio del servidor de Livy</span><span class="sxs-lookup"><span data-stu-id="bc907-156">Start the Livy server</span></span>

<span data-ttu-id="bc907-157">Siga las instrucciones de la sección [Detención del servidor de Livy](#stop-the-livy-server) para **Iniciar** (en lugar de **Detener**) el servidor de Livy para Spark2 en los hosts **hn0** y **hn1**.</span><span class="sxs-lookup"><span data-stu-id="bc907-157">Follow the instructions in the [Stop Livy server](#stop-the-livy-server) section to **Start** (rather than **Stop**) the Livy for Spark2 Server for hosts **hn0** and **hn1**.</span></span>

### <a name="set-up-spark-default-configurations"></a><span data-ttu-id="bc907-158">Configuraciones predeterminadas de Spark</span><span class="sxs-lookup"><span data-stu-id="bc907-158">Set up Spark default configurations</span></span>

1. <span data-ttu-id="bc907-159">En el portal, seleccione **Información general** y, luego, la **página de inicio de Ambari**.</span><span class="sxs-lookup"><span data-stu-id="bc907-159">From the portal, select **Overview**, and then select **Ambari home**.</span></span> <span data-ttu-id="bc907-160">Cuando se le solicite, escriba las credenciales de inicio de sesión del clúster.</span><span class="sxs-lookup"><span data-stu-id="bc907-160">If prompted, enter the cluster login credentials for the cluster.</span></span>

2. <span data-ttu-id="bc907-161">Seleccione **Spark2** y **CONFIGS**.</span><span class="sxs-lookup"><span data-stu-id="bc907-161">Select **Spark2** and **CONFIGS**.</span></span> <span data-ttu-id="bc907-162">A continuación, seleccione **Custom spark2-defaults** (Valores predeterminados de spark2 personalizados).</span><span class="sxs-lookup"><span data-stu-id="bc907-162">Then, select **Custom spark2-defaults**.</span></span>

   ![Pestaña Configuraciones de Ambari](./media/hdinsight-notebook-installation/spark-configs.png)

3. <span data-ttu-id="bc907-164">Seleccione **Agregar propiedad** para agregar la configuración predeterminada de Spark.</span><span class="sxs-lookup"><span data-stu-id="bc907-164">Select **Add Property** to add Spark default settings.</span></span>

   ![Agregar propiedad](./media/hdinsight-notebook-installation/add-property.png)

   <span data-ttu-id="bc907-166">Hay tres propiedades individuales.</span><span class="sxs-lookup"><span data-stu-id="bc907-166">There are three individual properties.</span></span> <span data-ttu-id="bc907-167">Agréguelas de una en una mediante el tipo de propiedad **TEXT** en el modo de adición de una sola propiedad.</span><span class="sxs-lookup"><span data-stu-id="bc907-167">Add them one at a time using the **TEXT** property type in Single property add mode.</span></span> <span data-ttu-id="bc907-168">Compruebe que no tiene espacios adicionales antes ni después de ninguna de las claves o valores.</span><span class="sxs-lookup"><span data-stu-id="bc907-168">Check that you don't have any extra spaces before or after any of the keys/values.</span></span>

   * <span data-ttu-id="bc907-169">**Propiedad 1**</span><span class="sxs-lookup"><span data-stu-id="bc907-169">**Property 1**</span></span>
       * <span data-ttu-id="bc907-170">Clave:&ensp;&ensp;`spark.dotnet.shell.command`</span><span class="sxs-lookup"><span data-stu-id="bc907-170">Key:&ensp;&ensp;`spark.dotnet.shell.command`</span></span>
       * <span data-ttu-id="bc907-171">Valor: `/usr/share/dotnet-tools/dotnet-try,kernel-server,--default-kernel,csharp`</span><span class="sxs-lookup"><span data-stu-id="bc907-171">Value: `/usr/share/dotnet-tools/dotnet-try,kernel-server,--default-kernel,csharp`</span></span>

   * <span data-ttu-id="bc907-172">**Propiedad 2** Use la versión de .NET para Apache Spark que se había incluido en la acción de script anterior.</span><span class="sxs-lookup"><span data-stu-id="bc907-172">**Property 2** Use the version of .NET for Apache Spark which you had included in the previous script action.</span></span>
       * <span data-ttu-id="bc907-173">Clave:&ensp;&ensp;`spark.dotnet.packages`</span><span class="sxs-lookup"><span data-stu-id="bc907-173">Key:&ensp;&ensp;`spark.dotnet.packages`</span></span>
       * <span data-ttu-id="bc907-174">Valor: `["nuget: Microsoft.Spark, 1.0.0", "nuget: Microsoft.Spark.Extensions.Delta, 1.0.0"]`</span><span class="sxs-lookup"><span data-stu-id="bc907-174">Value: `["nuget: Microsoft.Spark, 1.0.0", "nuget: Microsoft.Spark.Extensions.Delta, 1.0.0"]`</span></span>

   * <span data-ttu-id="bc907-175">**Propiedad 3**</span><span class="sxs-lookup"><span data-stu-id="bc907-175">**Property 3**</span></span>
       * <span data-ttu-id="bc907-176">Clave:&ensp;&ensp;`spark.dotnet.interpreter`</span><span class="sxs-lookup"><span data-stu-id="bc907-176">Key:&ensp;&ensp;`spark.dotnet.interpreter`</span></span>
       * <span data-ttu-id="bc907-177">Valor: `try`</span><span class="sxs-lookup"><span data-stu-id="bc907-177">Value: `try`</span></span>

   <span data-ttu-id="bc907-178">Por ejemplo, la siguiente imagen captura el valor para agregar la propiedad 1:</span><span class="sxs-lookup"><span data-stu-id="bc907-178">For example, the following image captures the setting for adding property 1:</span></span>

   ![Adición de una propiedad de texto](./media/hdinsight-notebook-installation/add-sparkconfig.png)

   <span data-ttu-id="bc907-180">Después de agregar las tres propiedades, seleccione **GUARDAR**.</span><span class="sxs-lookup"><span data-stu-id="bc907-180">After adding the three properties, select **SAVE**.</span></span> <span data-ttu-id="bc907-181">Si ve una pantalla de advertencia de recomendaciones de configuración, seleccione **PROCEED ANYWAY** (CONTINUAR DE TODOS MODOS).</span><span class="sxs-lookup"><span data-stu-id="bc907-181">If you see a warning screen of config recommendations, select **PROCEED ANYWAY**.</span></span>

4. <span data-ttu-id="bc907-182">Reinicie los componentes afectados.</span><span class="sxs-lookup"><span data-stu-id="bc907-182">Restart affected components.</span></span>

   <span data-ttu-id="bc907-183">Después de agregar las nuevas propiedades, debe reiniciar los componentes afectados por los cambios.</span><span class="sxs-lookup"><span data-stu-id="bc907-183">After adding the new properties, you need to restart components that were affected by the changes.</span></span> <span data-ttu-id="bc907-184">En la parte superior, seleccione **REINICIAR** y, luego, **Reinicio de todas las entradas afectadas** en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="bc907-184">At the top, select **RESTART**, and then **Restart All Affected** from the drop-down.</span></span>

   ![Pestaña Configuraciones con Reiniciar > Reinicio de todas las entradas afectadas](./media/hdinsight-notebook-installation/restart-affected.png)

   <span data-ttu-id="bc907-186">Cuando se le solicite, seleccione **CONFIRM RESTART ALL** (CONFIRMAR REINICIAR TODO) y, luego, haga clic en **Aceptar** para finalizar.</span><span class="sxs-lookup"><span data-stu-id="bc907-186">When prompted, select **CONFIRM RESTART ALL** to continue, then click **OK** to finish.</span></span>

## <a name="submit-jobs-through-a-jupyter-notebook"></a><span data-ttu-id="bc907-187">Envío de trabajos mediante un cuaderno de Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="bc907-187">Submit jobs through a Jupyter Notebook</span></span>

<span data-ttu-id="bc907-188">Después de finalizar los pasos anteriores, ahora puede enviar sus trabajos de .NET para Apache Spark mediante cuadernos de Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="bc907-188">After finishing the previous steps, you can now submit your .NET for Apache Spark jobs through Jupyter Notebooks.</span></span>

1. <span data-ttu-id="bc907-189">Cree un cuaderno de .NET para Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="bc907-189">Create a new .NET for Apache Spark notebook.</span></span> <span data-ttu-id="bc907-190">Inicie un cuaderno de Jupyter Notebook desde el clúster de HDI en Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="bc907-190">Launch a Jupyter Notebook from your HDI cluster in the Azure portal.</span></span>

   ![Inicio de Jupyter Notebook](./media/hdinsight-notebook-installation/launch-notebook.png)

   <span data-ttu-id="bc907-192">Luego, seleccione **Nuevo** >  **.NET Spark (C#)** para crear un cuaderno.</span><span class="sxs-lookup"><span data-stu-id="bc907-192">Then, select **New** > **.NET Spark (C#)** to create a notebook.</span></span>

   ![Jupyter Notebook](./media/hdinsight-notebook-installation/create-sparkdotnet-notebook.png)

2. <span data-ttu-id="bc907-194">Envíe los trabajos mediante .NET para Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="bc907-194">Submit jobs using .NET for Apache Spark.</span></span>

   <span data-ttu-id="bc907-195">Use el siguiente fragmento de código para crear un dataframe:</span><span class="sxs-lookup"><span data-stu-id="bc907-195">Use the following code snippet to create a DataFrame:</span></span>

   ```csharp
   var df = spark.Range(0,5);
   df.Show();
   ```

   ![Creación de un elemento DataFrame en la que se muestra la ejecución del comando](./media/hdinsight-notebook-installation/create-df.png)

   <span data-ttu-id="bc907-197">Use el siguiente fragmento de código para registrar una función definida por el usuario (UDF) y utilizarla con dataframes:</span><span class="sxs-lookup"><span data-stu-id="bc907-197">Use the following code snippet to register a user-defined function (UDF) and use the UDF with DataFrames:</span></span>

   ```csharp
   var myawesomeudf = Udf<int, string>((id) => $"hello {id}");
   df.Select(myawesomeudf(df["id"])).Show();
   ```

   ![Registro y uso de una UDF](./media/hdinsight-notebook-installation/run-udf.png)

## <a name="next-steps"></a><span data-ttu-id="bc907-199">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="bc907-199">Next steps</span></span>

* [<span data-ttu-id="bc907-200">Implementación de una aplicación de .NET para Apache Spark en Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="bc907-200">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>](../tutorials/hdinsight-deployment.md)
* [<span data-ttu-id="bc907-201">Documentación de HDInsight</span><span class="sxs-lookup"><span data-stu-id="bc907-201">HDInsight Documentation</span></span>](/azure/hdinsight/)
