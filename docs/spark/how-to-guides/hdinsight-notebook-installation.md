---
title: Instalación de .NET para Apache Spark en cuadernos de Jupyter Notebook en clústeres de Azure HDInsight Spark
description: Aprenda a instalar .NET para Apache Spark en cuadernos de Jupyter de Azure HDInsight.
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: ff6b3a64c01fb9148d3abe3d04579233d11a4f73
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599660"
---
# <a name="install-net-for-apache-spark-on-jupyter-notebooks-on-azure-hdinsight-spark-clusters"></a>Instalación de .NET para Apache Spark en cuadernos de Jupyter Notebook en clústeres de Azure HDInsight Spark

En este artículo se muestra cómo instalar .NET para Apache Spark en cuadernos de Jupyter Notebook en clústeres de Azure HDInsight Spark. Puede implementar .NET para Apache Spark en clústeres de Azure HDInsight mediante una combinación de la línea de comandos y Azure Portal (para más información, consulte [Implementación de una aplicación de .NET para Apache Spark en Azure HDInsight](../tutorials/hdinsight-deployment.md)), pero los cuadernos proporcionan una experiencia más interactiva e iterativa.

Los clústeres de Azure HDInsight ya incluyen cuadernos de Jupyter Notebook, así que todo lo que tiene que hacer es configurar estos para ejecutar .NET para Apache Spark. Para usar .NET para Apache Spark en los cuadernos de Jupyter Notebook, se necesita un REPL de C# para ejecutar el código de C# línea por línea y conservar el estado de ejecución cuando sea necesario. [Try .NET](https://github.com/dotnet/try) se ha integrado como el REPL oficial de .NET.

Para habilitar .NET para Apache Spark mediante la experiencia de Jupyter Notebooks, debe seguir algunos pasos manuales por medio de [Ambari](/azure/hdinsight/hdinsight-hadoop-manage-ambari) y enviar [acciones de script](/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux) en el clúster de HDInsight Spark.

> [!NOTE]
> Esta característica es *experimental* y el equipo de HDInsight Spark no la admite.

## <a name="prerequisites"></a>Requisitos previos

Si aún no tiene uno, cree un clúster de [Azure HDInsight Spark](/azure/hdinsight/spark/apache-spark-jupyter-spark-sql-use-portal#create-an-apache-spark-cluster-in-hdinsight).

1. Vaya a [Azure Portal](https://portal.azure.com) y seleccione **+ Crear un recurso**.

1. Cree un recurso de clúster de Azure HDInsight. Seleccione **Spark 2.4** y **HDI 4.0** durante la creación del clúster.

## <a name="install-net-for-apache-spark"></a>Instalación de .NET para Apache Spark

En Azure Portal, seleccione el **clúster de HDInsight Spark** que creó en el paso anterior.

### <a name="stop-the-livy-server"></a>Detención del servidor de Livy

1. En el portal, seleccione **Información general** y, luego, la **página de inicio de Ambari**. Cuando se le pida, escriba las credenciales de inicio de sesión del clúster.

   ![Detención del servidor de Livy](./media/hdinsight-notebook-installation/select-ambari.png)

2. Seleccione **Spark2** en el menú de navegación izquierdo y, luego, **LIVY FOR SPARK2 SERVER** (LIVY PARA EL SERVIDOR SPARK2).

   ![Detención del servidor de Livy](./media/hdinsight-notebook-installation/select-livyserver.png)

3. Seleccione **hn0... host**.

   ![Detención del servidor de Livy](./media/hdinsight-notebook-installation/select-host.png)

4. Seleccione los puntos suspensivos junto a **Livy for Spark2 Server** (Livy para el servidor Spark2) y elija **Detener**. Cuando se le solicite, seleccione **Aceptar** para continuar.

   Detención de Livy para el servidor Spark2.
   ![Detención del servidor de Livy](./media/hdinsight-notebook-installation/stop-server.png)

5. Repita los pasos anteriores para **hn1... host**.

### <a name="submit-an-hdinsight-script-action"></a>Envío de una acción de script de HDInsight

1. `install-interactive-notebook.sh` es un script que instala .NET para Apache Spark y realiza cambios en Apache Livy y sparkmagic. Antes de enviar una acción de script a HDInsight, debe crear y cargar `install-interactive-notebook.sh`.

   Cree un archivo llamado **install-interactive-notebook.sh** en el equipo local y pegue el contenido de [install-interactive-notebook.sh contents](https://raw.githubusercontent.com/dotnet/spark/master/deployment/HDI-Spark/Notebooks/install-interactive-notebook.sh).

   Cargue el script en un [URI](/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux#understand-script-actions) que sea accesible desde el clúster de HDInsight. Por ejemplo: `https://<my storage account>.blob.core.windows.net/<my container>/<some dir>/install-interactive-notebook.sh`.

2. Ejecute `install-interactive-notebook.sh` en el clúster con las [acciones de script de HDInsight](/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux).

   Vuelva al clúster de HDI en Azure Portal y seleccione **Acciones de script** en las opciones de la izquierda. Se envía una acción de script para implementar el REPL de .NET para Apache Spark en el clúster de HDInsight Spark. Use la configuración siguiente:

   |Propiedad.  |Descripción  |
   |---------|---------|
   | Tipo de script | Personalizados |
   | NOMBRE | *Instalación de la experiencia interactiva de cuadernos de .NET para Apache Spark* |
   | URI de script de Bash | El URI en el que cargó `install-interactive-notebook.sh`. |
   | Tipos de nodo| Principal y de trabajo |
   | Parámetros | Versión de .NET para Apache Spark. Puede comprobar las [versiones de .NET para Apache Spark](https://github.com/dotnet/spark/releases). Por ejemplo, si quiere instalar la versión 1.0.0 de Sparkdotnet, sería `1.0.0`.

   Cuando aparezcan marcas de verificación verdes junto al estado de la acción de script, vaya al siguiente paso.

### <a name="start-the-livy-server"></a>Inicio del servidor de Livy

Siga las instrucciones de la sección [Detención del servidor de Livy](#stop-the-livy-server) para **Iniciar** (en lugar de **Detener**) el servidor de Livy para Spark2 en los hosts **hn0** y **hn1**.

### <a name="set-up-spark-default-configurations"></a>Configuraciones predeterminadas de Spark

1. En el portal, seleccione **Información general** y, luego, la **página de inicio de Ambari**. Cuando se le solicite, escriba las credenciales de inicio de sesión del clúster.

2. Seleccione **Spark2** y **CONFIGS**. A continuación, seleccione **Custom spark2-defaults** (Valores predeterminados de spark2 personalizados).

   ![Establecimiento de las configuraciones](./media/hdinsight-notebook-installation/spark-configs.png)

3. Seleccione **Agregar propiedad...** para agregar la configuración predeterminada de Spark.

   ![Agregar propiedad](./media/hdinsight-notebook-installation/add-property.png)

   Hay tres propiedades individuales. Agréguelas de una en una mediante el tipo de propiedad **TEXT** en el modo de adición de una sola propiedad. Compruebe que no tiene espacios adicionales antes ni después de ninguna de las claves o valores.

   * **Propiedad 1**
       * Clave:&ensp;&ensp;`spark.dotnet.shell.command`
       * Valor: `/usr/share/dotnet-tools/dotnet-try,kernel-server,--default-kernel,csharp`

   * **Propiedad 2** Use la versión de .NET para Apache Spark que se había incluido en la acción de script anterior.
       * Clave:&ensp;&ensp;`spark.dotnet.packages`
       * Valor: `["nuget: Microsoft.Spark, 1.0.0", "nuget: Microsoft.Spark.Extensions.Delta, 1.0.0"]`

   * **Propiedad 3**
       * Clave:&ensp;&ensp;`spark.dotnet.interpreter`
       * Valor: `try`

   Por ejemplo, la siguiente imagen captura el valor para agregar la propiedad 1:

   ![Establecimiento de las configuraciones](./media/hdinsight-notebook-installation/add-sparkconfig.png)

   Después de agregar las tres propiedades, seleccione **GUARDAR**. Si ve una pantalla de advertencia de recomendaciones de configuración, seleccione **PROCEED ANYWAY** (CONTINUAR DE TODOS MODOS).

4. Reinicie los componentes afectados.

   Después de agregar las nuevas propiedades, debe reiniciar los componentes afectados por los cambios. En la parte superior, seleccione **REINICIAR** y, luego, **Reinicio de todas las entradas afectadas** en el menú desplegable.

   ![Establecimiento de las configuraciones](./media/hdinsight-notebook-installation/restart-affected.png)

   Cuando se le solicite, seleccione **CONFIRM RESTART ALL** (CONFIRMAR REINICIAR TODO) y, luego, haga clic en **Aceptar** para finalizar.

## <a name="submit-jobs-through-a-jupyter-notebook"></a>Envío de trabajos mediante un cuaderno de Jupyter Notebook

Después de finalizar los pasos anteriores, ahora puede enviar sus trabajos de .NET para Apache Spark mediante cuadernos de Jupyter Notebook.

1. Cree un cuaderno de .NET para Apache Spark. Inicie un cuaderno de Jupyter Notebook desde el clúster de HDI en Azure Portal.

   ![Inicio de Jupyter Notebook](./media/hdinsight-notebook-installation/launch-notebook.png)

   Luego, seleccione **Nuevo** >  **.NET Spark (C#)** para crear un cuaderno.

   ![Jupyter Notebook](./media/hdinsight-notebook-installation/create-sparkdotnet-notebook.png)

2. Envíe los trabajos mediante .NET para Apache Spark.

   Use el siguiente fragmento de código para crear un dataframe:

   ```csharp
   var df = spark.Range(0,5);
   df.Show();
   ```

   ![Envío de los trabajos de Spark](./media/hdinsight-notebook-installation/create-df.png)

   Use el siguiente fragmento de código para registrar una función definida por el usuario (UDF) y utilizarla con dataframes:

   ```csharp
   var myawesomeudf = Udf<int, string>((id) => $"hello {id}");
   df.Select(myawesomeudf(df["id"])).Show();
   ```

   ![Envío de los trabajos de Spark](./media/hdinsight-notebook-installation/run-udf.png)

## <a name="next-steps"></a>Pasos siguientes

* [Implementación de una aplicación de .NET para Apache Spark en Azure HDInsight](../tutorials/hdinsight-deployment.md)
* [Documentación de HDInsight](/azure/hdinsight/)
