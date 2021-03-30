---
title: Envío de un trabajo de .NET para Apache Spark a Databricks
description: Aprenda a enviar un trabajo de .NET para Apache Spark a Databricks mediante spark-submit y Set Jar.
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 39be961ad67da3f8593cb98e1bad8df354f28893
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104875582"
---
# <a name="submit-a-net-for-apache-spark-job-to-databricks"></a>Envío de un trabajo de .NET para Apache Spark a Databricks

Aunque puede ejecutar .NET para trabajos de Apache Spark en clústeres de Databricks, no está disponible de forma integrada. Hay dos maneras de implementar un trabajo de .NET para Apache Spark en Databricks: `spark-submit` y Set Jar.

## <a name="deploy-using-spark-submit"></a>Implementación mediante spark-submit

Puede usar el comando [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) para enviar trabajos de .NET para Apache Spark a Databricks. `spark-submit` permite el envío solo a un clúster que se crea a petición.

1. Vaya al área de trabajo de Databricks y cree un trabajo. Elija un título para el trabajo y luego seleccione **Configurar spark-submit**. Pegue los parámetros siguientes en la configuración del trabajo y seleccione **Confirmar**.

    ```
    ["--files","/dbfs/<path-to>/<app assembly/file to deploy to worker>","--class","org.apache.spark.deploy.dotnet.DotnetRunner","/dbfs/<path-to>/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar","/dbfs/<path-to>/<app name>.zip","<app bin name>","app arg1","app arg2"]
    ```

    > [!NOTE]
    > Actualice el contenido del parámetro anterior en función de los archivos y la configuración específicos. Por ejemplo, haga referencia a la versión del archivo jar Microsoft.Spark que cargó en DBFS y use el nombre adecuado de la aplicación y el archivo zip de la aplicación publicada.

2. Vaya a su trabajo y seleccione **Editar** para configurar el clúster del trabajo. Establezca la versión de Databricks Runtime en función de la versión de Apache Spark que desea usar en la implementación. A continuación, seleccione **Advanced Options > Init Scripts** (Opciones avanzadas > Scripts init) y establezca la ruta de acceso del script init como `dbfs:/spark-dotnet/db-init.sh`. Seleccione **Confirmar** para confirmar la configuración del clúster.

3. Vaya a su trabajo y seleccione **Ejecutar ahora** para ejecutar el trabajo en el clúster de Spark recientemente configurado. La creación del clúster del trabajo tarda unos minutos. Una vez creado, se enviará el trabajo. Para ver la salida, seleccione **Clústeres** en el menú de la izquierda del área de trabajo del área de trabajo de Databricks y, después, elija **Driver Logs** (Registros de controladores).

## <a name="deploy-using-set-jar"></a>Implementación mediante Set Jar

Como alternativa, puede usar [Set Jar](/azure/databricks/jobs#--create-a-job) en el área de trabajo de Databricks para enviar trabajos de .NET para Apache Spark a Databricks. *Set Jar* permite el envío de trabajos a clústeres activos.

### <a name="one-time-setup"></a>Instalación única

1. Vaya al clúster de Databricks y seleccione **Trabajos** en el menú de la izquierda y, después, en **Set JAR**.

2. Cargue el archivo `microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar` adecuado.

3. Modifique los parámetros siguientes para incluir el nombre correcto del archivo ejecutable que publicó en lugar de `<your-app-name>`:

    ```
    Main Class: org.apache.spark.deploy.dotnet.DotnetRunner
    Arguments /dbfs/apps/<your-app-name>.zip <your-app-name>
    ```

4. Configure el clúster para que apunte a un clúster para el que ya ha establecido el script init.

### <a name="publish-and-run-your-app"></a>Publicación y ejecución de la aplicación

1. Asegúrese de que ha publicado la aplicación y de que el código de aplicación no usa `SparkSession.Stop()`.

2. Use la [CLI de Databricks](/azure/databricks/dev-tools/databricks-cli) para cargar la aplicación en el clúster de Databricks. Por ejemplo, use el siguiente comando para cargar la aplicación publicada en el clúster:

    ```console
    cd <path-to-your-app-publish-directory>
    databricks fs cp <your-app-name>.zip dbfs:/apps/<your-app-name>.zip
    ```

3. Si tiene funciones definidas por el usuario en la aplicación, sus ensamblados (por ejemplo, los archivos DLL que contienen funciones definidas por el usuario junto con sus dependencias) deben colocarse en el directorio de trabajo de cada *Microsoft.Spark.Worker*.

    Carga de los ensamblados de la aplicación en el clúster de Databricks:

    ```console
    cd <path-to-your-app-publish-directory>
    databricks fs cp <assembly>.dll dbfs:/apps/dependencies
    ```

    Quite la marca de comentario y modifique la sección de dependencias de la aplicación en [db-init.sh](https://github.com/dotnet/spark/blob/main/deployment/db-init.sh) para que apunte a la ruta de acceso de las dependencias de la aplicación. A continuación, cargue el archivo *db-init.sh* actualizado en el clúster:

    ```console
    cd <path-to-db-init-and-install-worker>
    databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
    ```

4. Vaya a **Databricks cluster > Jobs > [Job-name] > Run Now** (Clúster de Databricks > Trabajos [nombre del trabajo] > Ejecutar ahora) para ejecutar el trabajo.

## <a name="next-steps"></a>Pasos siguientes

* [Introducción a .NET para Apache Spark](../tutorials/get-started.md)
* [Implementación de una aplicación de .NET para Apache Spark en Databricks](../tutorials/databricks-deployment.md)
* [Documentación de Azure Databricks](/azure/azure-databricks/)
