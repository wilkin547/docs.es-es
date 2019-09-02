---
title: Implementación de una aplicación de .NET para Apache Spark en Databricks
description: Sepa cómo implementar una aplicación de .NET para Apache Spark en Databricks.
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 77c2d93ae324b6acbf8fc8dc25cd3e4d1a652f48
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2019
ms.locfileid: "70107350"
---
# <a name="deploy-a-net-for-apache-spark-application-to-databricks"></a>Implementación de una aplicación de .NET para Apache Spark en Databricks

En este tutorial aprenderá a implementar una aplicación de .NET para Apache Spark en Databricks.

En este tutorial aprenderá a:

> [!div class="checklist"]
> - Preparar Microsoft.Spark.Worker
> - Publicar la aplicación de .NET para Spark
> - Implementar una aplicación en Databricks
> - Ejecutar la aplicación

## <a name="prerequisites"></a>Requisitos previos

Antes de empezar, haga lo siguiente:

- Descargue la [CLI de Databricks](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html).
- Descargue [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) en el equipo local. Es un script de aplicación auxiliar que usaremos más adelante para copiar archivos dependientes de .NET para Apache Spark en los nodos de trabajo del clúster de Spark.

## <a name="prepare-worker-dependencies"></a>Preparación de las dependencias de trabajo

**Microsoft.Spark.Worker** es un componente back-end que reside en los nodos de trabajo individuales del clúster de Spark. Si quiere ejecutar una función definida por el usuario (UDF) de C#, Spark necesita saber cómo iniciar .NET CLR para ejecutar la UDF. **Microsoft.Spark.Worker** pone a disposición de Spark una colección de clases que habilitan esta funcionalidad.

1. Seleccione una versión netcoreapp de Linux de [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) para implementarla en el clúster.

   Por ejemplo, si quiere que `.NET for Apache Spark v0.1.0` use `netcoreapp2.1`, tendría que descargar [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).

2. Cargue `Microsoft.Spark.Worker.<release>.tar.gz` e [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) en un sistema de archivos distribuido (por ejemplo, DBFS) al que el clúster tenga acceso.

## <a name="prepare-your-net-for-apache-spark-app"></a>Preparación de la aplicación de .NET para Apache Spark

1. Siga el tutorial de [introducción](get-started.md) para crear la aplicación.

2. Publique la aplicación de .NET para Spark como independiente.

   Puede ejecutar el siguiente comando en Linux.

   ```bash
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. Genere `<your app>.zip` para los archivos publicados.

   Puede ejecutar el siguiente comando en Linux usando `zip`.

   ```bash
   zip -r <your app>.zip .
   ```

4. Cargue lo siguiente en un sistema de archivos distribuido (por ejemplo, DBFS) al que el clúster tenga acceso:

   - `microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: Este archivo jar se incluye como parte del paquete NuGet [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/), y se encuentra en el directorio de salida de creación de la aplicación.
   - `<your app>.zip`
   - Los archivos (como los archivos de dependencias o los datos comunes accesibles para todos los trabajos) o los ensamblados (como los archivos DLL que contienen las bibliotecas o las funciones definidas por el usuario de las que depende la aplicación) se colocarán en el directorio de trabajo de cada ejecutor.

## <a name="deploy-to-databricks"></a>Implementación en Databricks

[Databricks](https://databricks.com) es una plataforma que permite el procesamiento de macrodatos en la nube mediante Apache Spark.

> [!Note] 
> [Azure Databricks](https://azure.microsoft.com/services/databricks/) y [AWS Databricks](https://databricks.com/aws) se basan en Linux. Por lo tanto, si está interesado en implementar la aplicación en Databricks, asegúrese de que la aplicación es compatible con .NET Standard y, asimismo, de que usa el [compilador de .NET Core](https://dotnet.microsoft.com/download) para compilar la aplicación.

Databricks permite enviar las aplicaciones de .NET para Apache Spark a un clúster activo existente, o bien crear un clúster cada vez que un trabajo se inicie. Esto requiere instalar **Microsoft.Spark.Worker** antes de enviar la aplicación de .NET para Apache Spark.

### <a name="deploy-microsoftsparkworker"></a>Implementación de Microsoft.Spark.Worker

Este paso solo es necesario realizarlo una vez en un clúster.

1. Descargue [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) e [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh
) en el equipo local.

2. Modifique **db-init.sh** para que apunte a la versión de **Microsoft.Spark.Worker** que quiera descargar e instalar en el clúster.

3. Instale la [CLI de Databricks](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html).

4. [Configure los detalles de autenticación](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html#set-up-authentication) de la CLI de Databricks.

5. Cargue los archivos en el clúster de Databricks mediante el siguiente comando:

   ```bash
   cd <path-to-db-init-and-install-worker>
   databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
   databricks fs cp install-worker.sh dbfs:/spark-dotnet/install-worker.sh
   ```

6. Acceda al área de trabajo de Databricks. Seleccione  **Clústeres** en el menú de la izquierda y, después, seleccione **Crear clúster**.

7. Después de configurar el clúster correctamente, defina el **script Init** y cree el clúster.

   ![Imagen de acción de script](./media/databricks-deployment/deployment-databricks-init-script.png)

## <a name="run-your-app"></a>Ejecutar la aplicación 

Puede usar `set JAR` o `spark-submit` para enviar el trabajo a Databricks.

### <a name="use-set-jar"></a>Uso de Set JAR

[Set JAR](https://docs.databricks.com/user-guide/jobs.html#create-a-job) permite enviar un trabajo a un clúster activo existente.

#### <a name="one-time-setup"></a>Instalación única

1. Vaya al clúster de Databricks y seleccione **Trabajos** en el menú de la izquierda. Después, seleccione **Set JAR**.

2. Cargue el archivo `microsoft-spark-<spark-version>-<spark-dotnet-version>.jar` adecuado.

3. Establezca los parámetros de forma adecuada.

   ```
   Main Class: org.apache.spark.deploy.DotnetRunner
   Arguments /dbfs/apps/<your-app-name>.zip <your-app-main-class>
   ```
 
4. Configure el **clúster** para que apunte al clúster existente para el que creó el **script Init** en la sección anterior.

#### <a name="publish-and-run-your-app"></a>Publicación y ejecución de la aplicación

1. Use la [CLI de Databricks](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html) para cargar la aplicación en el clúster de Databricks.

      ```bash
      cd <path-to-your-app-publish-directory>
      databricks fs cp <your-app-name>.zip dbfs:/apps/<your-app-name>.zip
      ```

2. Este paso solo es necesario si los ensamblados de la aplicación (por ejemplo, los archivos DLL que contienen funciones definidas por el usuario junto con sus dependencias) deben colocarse en el directorio de trabajo de cada **Microsoft.Spark.Worker**.

   - Carga de los ensamblados de la aplicación en el clúster de Databricks
      
      ```bash
      cd <path-to-your-app-publish-directory>
      databricks fs cp <assembly>.dll dbfs:/apps/dependencies
      ```

   - Quite la marca de comentario y modifique la sección de dependencias de la aplicación en [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) para que apunte a la ruta de acceso de las dependencias de la aplicación y cargue en el clúster de Databricks.
   
      ```bash
      cd <path-to-db-init-and-install-worker>
      databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
      ```
   
   - Reinicie el clúster.

3. Vaya al clúster de Databricks en el área de trabajo de Databricks. En **Trabajos**, seleccione el trabajo y, después, seleccione **Ejecutar ahora** para ejecutar el trabajo.

### <a name="use-spark-submit"></a>Uso de spark-submit

El comando [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) permite enviar un trabajo a un clúster nuevo.

1. [Cree un trabajo](https://docs.databricks.com/user-guide/jobs.html) y seleccione **Configurar spark-submit**.

2. Configure `spark-submit` con los siguientes parámetros:

      ```bash
      ["--files","/dbfs/<path-to>/<app assembly/file to deploy to worker>","--class","org.apache.spark.deploy.DotnetRunner","/dbfs/<path-to>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar","/dbfs/<path-to>/<app name>.zip","<app bin name>","app arg1","app arg2"]
      ```

3. Vaya al clúster de Databricks en el área de trabajo de Databricks. En **Trabajos**, seleccione el trabajo y, después, seleccione **Ejecutar ahora** para ejecutar el trabajo.

## <a name="next-steps"></a>Pasos siguientes

En este tutorial ha implementado una aplicación de .NET para Apache Spark en Databricks. Para más información sobre Databricks, prosiga con la documentación de Azure Databricks.

> [!div class="nextstepaction"]
> [Documentación de Azure Databricks](https://docs.microsoft.com/azure/azure-databricks/)
