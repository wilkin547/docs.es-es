---
title: Implementación de una aplicación de .NET para Apache Spark en Databricks
description: Sepa cómo implementar una aplicación de .NET para Apache Spark en Databricks.
ms.date: 10/09/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: d17fd5002d47dcde804cb43fc27edb2c2c9be595
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688155"
---
# <a name="tutorial-deploy-a-net-for-apache-spark-application-to-databricks"></a>Tutorial: Implementación de una aplicación de .NET para Apache Spark en Databricks

En este tutorial se enseña cómo implementar la aplicación en la nube a través de Azure Databricks, una plataforma de análisis basada en Apache Spark que ofrece una configuración de un clic, simplifica los flujos de trabajo y ofrece un área de trabajo interactivo que permite la colaboración.

En este tutorial aprenderá a:

> [!div class="checklist"]
>
> - Crear un área de trabajo de Azure Databricks.
> - Publicar la aplicación de .NET para Apache Spark.
> - Crear un trabajo y un clúster de Spark.
> - Ejecutar la aplicación en el clúster de Spark.

## <a name="prerequisites"></a>Requisitos previos

Antes de empezar, haga las tareas siguientes:

* Si no tiene una cuenta de Azure, cree una [cuenta gratuita](https://azure.microsoft.com/free/dotnet/).
* Inicie sesión en [Azure Portal](https://portal.azure.com/).
* Complete el tutorial [.NET para Apache Spark: comenzar en 10 minutos](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro).

## <a name="create-an-azure-databricks-workspace"></a>Creación de un área de trabajo de Azure Databricks

> [!Note]
> Este tutorial no puede llevarse a cabo mediante una **suscripción de evaluación gratuita de Azure**.
> Si tiene una cuenta gratuita, vaya a su perfil y cambiar la suscripción a **pago por uso**. Para más información consulte el sitio de [cuentas gratuitas de Azure](https://azure.microsoft.com/free/dotnet/). Después, [quite el límite de gasto](/azure/billing/billing-spending-limit#why-you-might-want-to-remove-the-spending-limit) y [solicite un aumento de la cuota](/azure/azure-supportability/resource-manager-core-quotas-request) para las vCPU de su región. Cuando crea su área de trabajo de Azure Databricks, puede seleccionar el plan de tarifa de la **Trial (Premium - 14-Days Free DBUs)** para que el área de trabajo acceda a las DBU Premium de Azure Databricks gratis durante 14 días.

En esta sección, creará un área de trabajo de Azure Databricks mediante Azure Portal.

1. En Azure Portal, seleccione **Crear un recurso** > **Análisis** > **Azure Databricks**.

   ![Creación de un recurso de Azure Databricks en Azure Portal](./media/databricks-deployment/create-databricks-resource.png)

2. En **Azure Databricks Service**, proporcione los valores para crear un área de trabajo de Databricks.

    |Propiedad.  |Descripción  |
    |---------|---------|
    |**Workspace name** (Nombre del área de trabajo)     | Proporcione un nombre para el área de trabajo de Databricks.        |
    |**Suscripción**     | En el cuadro desplegable, seleccione la suscripción de Azure.        |
    |**Grupos de recursos**     | Especifique si desea crear un nuevo grupo de recursos o utilizar uno existente. Un grupo de recursos es un contenedor que almacena los recursos relacionados con una solución de Azure. Para más información, consulte [Información general del grupo de recursos de Azure](/azure/azure-resource-manager/resource-group-overview). |
    |**Ubicación**     | Seleccione su región preferida. Para obtener información sobre las regiones disponibles, consulte [Servicios de Azure disponibles por región](https://azure.microsoft.com/regions/services/).        |
    |**Plan de tarifa**     |  Elija entre **Estándar**, **Premium** o **Evaluación gratuita**. Para más información sobre estos planes, consulte la [página de precios de Databricks](https://azure.microsoft.com/pricing/details/databricks/).       |
    |**Virtual Network**     |   No       |

3. Seleccione **Crear**. Se tarda unos minutos en crear el área de trabajo. Durante la creación del área de trabajo, puede ver el estado de implementación en **Notificaciones**.

## <a name="install-azure-databricks-tools"></a>Instalación de las herramientas de Azure Databricks

Puede usar la **CLI de Databricks** para conectarse a los clústeres de Azure Databricks y cargar archivos en ellos desde la máquina local. Los clústeres de Databricks tienen acceso a archivos a través del DBFS (Sistema de archivos de Databricks).

1. La CLI de Databricks requiere Python 3.6 o una versión posterior. Si ya tiene Python instalado, puede omitir este paso.

   **Para Windows**:

   [Descargar Python para Windows](https://www.python.org/ftp/python/3.7.4/python-3.7.4.exe)

   **Para Linux:** Python viene preinstalado en la mayoría de las distribuciones de Linux. Ejecute el comando siguiente para ver la versión que se ha instalado:

   ```bash
   python3 --version
   ```

2. Use pip para instalar la CLI de Databricks. Python 3.4 y las versiones posteriores incluyen pip de forma predeterminada. Use pip3 para Python 3. Ejecute el siguiente comando:

   ```bash
   pip3 install databricks-cli
   ```

3. Una vez instalada la CLI de Databricks, abra un símbolo del sistema nuevo y ejecute el comando `databricks`. Si recibe un aviso **"databricks" no se reconoce como un error de comando interno o externo**, asegúrese de que ha abierto un símbolo del sistema nuevo.

## <a name="set-up-azure-databricks"></a>Configuración de Azure Databricks

Ahora que tiene la CLI de Databricks instalada, debe configurar los detalles de autenticación.

1. Ejecute el comando `databricks configure --token` de la CLI de Databricks.

2. Después de ejecutar el comando de configuración, se le pedirá que escriba un host. La dirección URL del host usa el formato: `https://<Location>.azuredatabricks.net`. Por ejemplo, si ha seleccionado **eastus2** durante la creación del Servicio de Azure Databricks, el host sería `https://eastus2.azuredatabricks.net`.

3. Después de escribir el host, se le pedirá que escriba un token. En Azure Portal, seleccione **Iniciar área de trabajo** para iniciar el área de trabajo de Azure Databricks.

   ![Inicio del área de trabajo de Azure Databricks](./media/databricks-deployment/launch-databricks-workspace.png)

4. En la página principal del área de trabajo, seleccione **Configuración de usuario**.

   ![Configuración de usuario en el área de trabajo de Azure Databricks](./media/databricks-deployment/databricks-user-settings.png)

5. En la página Configuración de usuario se puede generar un nuevo token. Copie el token generado y péguelo de nuevo en el símbolo del sistema.

   ![Generación de un token de acceso nuevo en el área de trabajo de Azure Databricks](./media/databricks-deployment/generate-token.png)

Ahora debería poder acceder a cualquier clúster de Azure Databricks que cree y cargar archivos en el DBFS.

## <a name="download-worker-dependencies"></a>Descarga de las dependencias de trabajo

> [!Note]
> Azure y AWS Databricks se basan en Linux. Por lo tanto, si está interesado en implementar la aplicación en Databricks, asegúrese de que la aplicación es compatible con .NET Standard y, asimismo, de que usa el compilador de .NET Core para compilar la aplicación.

1. Microsoft.Spark.Worker ayuda a Apache Spark a ejecutar la aplicación, como cualquier función definida por el usuario (UDF) que se haya escrito. Descargue [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases/download/v1.0.0/Microsoft.Spark.Worker.netcoreapp3.1.linux-x64-1.0.0.tar.gz).

2. *install-worker.sh* es un script que permite copiar archivos dependientes de .NET para Apache Spark en los nodos del clúster.

   Cree un nuevo archivo llamado **install-worker.sh** en el equipo local y pegue el [contenido de install-worker.sh](https://raw.githubusercontent.com/dotnet/spark/master/deployment/install-worker.sh) que se encuentra en GitHub.

3. *db-init.sh* es un script que instala las dependencias en el clúster de Spark de Databricks.

   Cree un nuevo archivo llamado **db-init.sh** en el equipo local y pegue el [contenido de db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) que se encuentra en GitHub.

   En el archivo que se acaba de crear, establezca la variable `DOTNET_SPARK_RELEASE` en `https://github.com/dotnet/spark/releases/download/v1.0.0/Microsoft.Spark.Worker.netcoreapp3.1.linux-x64-1.0.0.tar.gz`. Deje el resto del archivo *db-init.sh* tal cual.

> [!Note]
> Si usa Windows, compruebe que los fines de línea de los scripts *install-worker.sh* y *db-init.sh* son de estilo Unix (LF). Se pueden cambiar los fines de línea a través de los editores de texto como Notepad++ y Atom.

## <a name="publish-your-app"></a>Publicar la aplicación

Luego, publique la aplicación *mySparkApp* creada en el tutorial [.NET para Apache Spark: comenzar en 10 minutos](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) para asegurarse de que el clúster de Spark tiene acceso a todos los archivos que necesita para ejecutar la aplicación.

1. Para publicar *mySparkApp*, ejecute los comandos siguientes:

   ```dotnetcli
   cd mySparkApp
   dotnet publish -c Release -f netcoreapp3.1 -r ubuntu.16.04-x64
   ```

2. Realice las tareas siguientes para comprimir los archivos de la aplicación publicados para que pueda cargarlos fácilmente en el clúster de Spark de Databricks.

   **En Windows:**

   Vaya a mySparkApp/bin/Release/netcoreapp3.1/ubuntu.16.04-x64. Luego, haga clic con el botón derecho en la carpeta **Publicar** y seleccione **Enviar a > Carpeta comprimida (en zip)** . Asigne el nombre **publish.zip** a la carpeta nueva.

   **En Linux, ejecute el comando siguiente:**

   ```bash
   zip -r publish.zip .
   ```

## <a name="upload-files"></a>Carga de archivos

En esta sección, se cargan varios archivos en el DBFS con el fin de que el clúster tenga todo lo necesario para ejecutar la aplicación en la nube. Cada vez que cargue un archivo en el DBFS, asegúrese de que está en el directorio en el que se encuentra el archivo en el equipo.

1. Ejecute los siguientes comandos para cargar *db-init.sh*, *install-worker.sh* y *Microsoft.Spark.Worker* en DBFS:

   ```console
   databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
   databricks fs cp install-worker.sh dbfs:/spark-dotnet/install-worker.sh
   databricks fs cp Microsoft.Spark.Worker.netcoreapp3.1.linux-x64-1.0.0.tar.gz dbfs:/spark-dotnet/Microsoft.Spark.Worker.netcoreapp3.1.linux-x64-1.0.0.tar.gz
   ```

2. Ejecute los comandos siguientes para cargar los archivos restantes que el clúster necesitará para ejecutar la aplicación: la carpeta de publicación comprimida, *input.txt* y *microsoft-spark-2-4_2.11-1.0.0.jar*.

   ```console
   cd mySparkApp
   databricks fs cp input.txt dbfs:/input.txt

   cd mySparkApp\bin\Release\netcoreapp3.1\ubuntu.16.04-x64 directory
   databricks fs cp publish.zip dbfs:/spark-dotnet/publish.zip
   databricks fs cp microsoft-spark-2-4_2.11-1.0.0.jar dbfs:/spark-dotnet/microsoft-spark-2-4_2.11-1.0.0.jar
   ```

## <a name="create-a-job"></a>Creación de un trabajo

La aplicación se ejecuta en Azure Databricks a través de un trabajo que ejecuta **spark-submit**, que es el comando que se usa para ejecutar .NET para trabajos de Apache Spark.

1. En el área de trabajo de Azure Databricks, seleccione el icono de **Trabajos** y luego **+ Crear trabajo**.

   ![Creación de un trabajo de Azure Databricks](./media/databricks-deployment/create-job.png)

2. Elija un título para el trabajo y luego seleccione **Configurar spark-submit**.

   ![Configuración de spark-submit para el trabajo de Databricks](./media/databricks-deployment/configure-spark-submit.png)

3. Pegue los parámetros siguientes en la configuración del trabajo. Después, seleccione **Confirmar**.

   ```
   ["--class","org.apache.spark.deploy.dotnet.DotnetRunner","/dbfs/spark-dotnet/microsoft-spark-2-4_2.11-1.0.0.jar","/dbfs/spark-dotnet/publish.zip","mySparkApp"]
   ```

## <a name="create-a-cluster"></a>Crear un clúster

1. Vaya a su trabajo y seleccione **Editar** para configurar el clúster del trabajo.

2. Establezca el clúster en **Spark 2.4.1**. Luego, seleccione **Opciones avanzadas** > **Scripts Init**. Escriba la ruta de acceso del script Init como `dbfs:/spark-dotnet/db-init.sh`.

   ![Configuración de un clúster de Spark en Azure Databricks](./media/databricks-deployment/cluster-config.png)

3. Seleccione **Confirmar** para confirmar la configuración del clúster.

## <a name="run-your-app"></a>Ejecutar la aplicación

1. Vaya a su trabajo y seleccione **Ejecutar ahora** para ejecutar el trabajo en el clúster de Spark recientemente configurado.

2. La creación del clúster del trabajo tarda unos minutos. Una vez creado, se enviará el trabajo y podrá ver el resultado.

3. Seleccione **Clústeres** en el menú de la izquierda y, después, el nombre y la ejecución del trabajo.

4. Seleccione **Registros de controladores** para ver la salida del trabajo. Cuando la aplicación termine de ejecutarse, verá la misma tabla de recuento de palabras de la ejecución local de introducción escrita en la consola de salida estándar.

   ![Tabla de salida del trabajo de Azure Databricks](./media/databricks-deployment/table-output.png)

   Enhorabuena, ha ejecutado la primera aplicación de .NET para Apache Spark en Azure Databricks.

## <a name="clean-up-resources"></a>Limpiar los recursos

Si ya no necesita el área de trabajo de Databricks, puede eliminar el recurso Azure Databricks en Azure Portal. También puede seleccionar el nombre del grupo de recursos para abrir la página del grupo de recursos y, a continuación, seleccionar **Eliminar grupo de recursos**.

## <a name="next-steps"></a>Pasos siguientes

En este tutorial ha implementado una aplicación de .NET para Apache Spark en Databricks. Para más información sobre Databricks, prosiga con la documentación de Azure Databricks.

> [!div class="nextstepaction"]
> [Documentación de Azure Databricks](/azure/azure-databricks/)
