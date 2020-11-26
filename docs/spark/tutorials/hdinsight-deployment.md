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
# <a name="tutorial-deploy-a-net-for-apache-spark-application-to-azure-hdinsight"></a>Tutorial: Implementación de una aplicación de .NET para Apache Spark en Azure HDInsight

Este tutorial enseña cómo implementar la aplicación de .NET para Apache Spark en la nube a través de un clúster de Azure HDInsight. HDInsight facilita la creación y configuración de un clúster de Spark en Azure, ya que los clústeres de Spark en HDInsight son compatibles con Azure Storage y Azure Data Lake Storage.

En este tutorial aprenderá a:

> [!div class="checklist"]
>
> * Obtener acceso a las cuentas de almacenamiento mediante el Explorador de Azure Storage.
> * Crear un clúster de Azure HDInsight.
> * Publicar la aplicación de .NET para Apache Spark.
> * Crear y ejecutar una acción de script de HDInsight.
> * Ejecutar una aplicación de .NET para Apache Spark en un clúster de HDInsight.

## <a name="prerequisites"></a>Requisitos previos

Antes de empezar, haga las tareas siguientes:

* Si no tiene una suscripción a Azure, cree una [cuenta gratuita](https://azure.microsoft.com/free/dotnet/).
* Inicie sesión en [Azure Portal](https://portal.azure.com/).
* Instale el Explorador de Azure Storage en el equipo [Windows](https://go.microsoft.com/fwlink/?LinkId=708343&clcid=0x409), [Linux](https://go.microsoft.com/fwlink/?LinkId=722418&clcid=0x409) o [MacOS](https://go.microsoft.com/fwlink/?LinkId=708342&clcid=0x409).
* Complete el tutorial [.NET para Apache Spark: comenzar en 10 minutos](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro).

## <a name="access-your-storage-accounts"></a>Acceso a las cuentas de almacenamiento

1. Abra el Explorador de Azure Storage.

2. Seleccione **Agregar cuenta** en el menú de la izquierda e inicie sesión en su cuenta de Azure.

    ![Inicio de sesión en la cuenta de Azure desde el Explorador de Storage](./media/hdinsight-deployment/signin-azure-storage-explorer.png)

   Después de iniciar sesión, debería ver todas las cuentas de almacenamiento que tiene y los recursos que ha cargado en estas.

## <a name="create-an-hdinsight-cluster"></a>Creación de un clúster de HDInsight

> [!IMPORTANT]
> La facturación de los clústeres de HDInsight se prorratea por minuto, incluso si no los está usando. Por consiguiente, es aconsejable eliminar el clúster al terminar de usarlo. Para obtener más información, consulte la sección [Limpieza de recursos](#clean-up-resources) de este tutorial.

1. Visite [Azure Portal](https://portal.azure.com).

2. Seleccione **+ Crear un recurso**. Después, seleccione **HDInsight** en la categoría **Análisis**.

    ![Creación de un recurso de HDInsight desde Azure Portal](./media/hdinsight-deployment/create-hdinsight-resource.png)

3. En **Datos básicos**, proporcione los valores siguientes:

    |Propiedad.  |Descripción  |
    |---------|---------|
    |Suscripción  | En la lista desplegable, elija una de las suscripciones de Azure activas. |
    |Resource group | Especifique si desea crear un nuevo grupo de recursos o utilizar uno existente. Un grupo de recursos es un contenedor que almacena los recursos relacionados con una solución de Azure. |
    |Nombre del clúster | Asigne un nombre al clúster de Spark de HDInsight.|
    |Ubicación   | Seleccione una ubicación para el grupo de recursos. La plantilla utiliza esta ubicación para crear el clúster, así como para el almacenamiento de clúster predeterminado. |
    |Tipo de clúster| Seleccione **Spark** como el tipo de clúster.|
    |Versión del clúster|Este campo se rellenará automáticamente con la versión predeterminada una vez que se haya seleccionado el tipo de clúster. Seleccione una versión 2.3 o 2.4 de Spark.|
    |Nombre de usuario de inicio de sesión del clúster| Escriba el nombre de usuario de inicio de sesión del clúster.  El nombre predeterminado es *admin*. |
    |Contraseña de inicio de sesión de clúster| Escriba una contraseña de inicio de sesión. |
    |Nombre de usuario de Secure Shell (SSH)| Escriba el nombre de usuario de SSH. De manera predeterminada, esta cuenta comparte la contraseña con la cuenta de *nombre de usuario de inicio de sesión del clúster*. |

4. Seleccione **Siguiente: Almacenamiento>>** para continuar en la página **Almacenamiento**. En **Almacenamiento**, proporcione los valores siguientes:

    |Propiedad.  |Descripción  |
    |---------|---------|
    |Tipo de almacenamiento principal|Use el valor predeterminado **Azure Storage**.|
    |Método de selección|Use el valor predeterminado **Seleccionar de la lista**.|
    |Cuenta de almacenamiento principal|Elija su suscripción y una de sus cuentas de almacenamiento activas en esa suscripción.|
    |Contenedor|Este contenedor es el contenedor de blobs específico de la cuenta de almacenamiento en la que el clúster busca archivos para ejecutar la aplicación en la nube. Puede asignarle cualquier nombre disponible.|

5. Seleccione **Revisar y crear** y, después, **Crear**. La creación del clúster tarda aproximadamente 20 minutos. Se debe crear el clúster para poder continuar con el paso siguiente.

## <a name="publish-your-app"></a>Publicar la aplicación

Luego, publique la aplicación *mySparkApp* creada en el tutorial [.NET para Apache Spark: comenzar en 10 minutos](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro), que proporciona acceso al clúster de Spark a todos los archivos que necesita para ejecutar la aplicación.

1. Para publicar *mySparkApp*, ejecute los comandos siguientes:

   **En Windows:**

   ```dotnetcli
   cd mySparkApp
   dotnet publish -c Release -f netcoreapp3.1 -r win-x64
   ```

   **En Linux:**

   ```bash
   cd mySparkApp
   foo@bar:~/path/to/app$ dotnet publish -c Release -f netcoreapp3.1 -r ubuntu.16.04-x64
   ```

2. Realice las tareas siguientes para comprimir los archivos de la aplicación publicados para que pueda cargarlos fácilmente en el clúster de HDInsight. Comprima el contenido de la carpeta de publicación, *publish.zip*, por ejemplo, que se ha creado como resultado del paso 1. Todos los elementos ensamblados deben estar en la primera capa del archivo ZIP y no debe haber ninguna capa de carpeta intermedia. Esto significa que, al descomprimir *publish.zip*, todos los ensamblados se extraen en el directorio de trabajo actual.

   **En Windows:**

   Use un programa de extracción, como 7-zip o WinZip, para extraer el archivo en el directorio bin con todos los archivos binarios publicados.

   **En Linux, ejecute el comando siguiente:**

   ```bash
   zip -r publish.zip
   ```

## <a name="upload-files-to-azure"></a>Carga de archivos en Azure

Después, use el Explorador de Azure Storage para cargar los cinco archivos siguientes en el contenedor de blobs que se ha elegido para el almacenamiento del clúster:

* Microsoft.Spark.Worker
* install-worker.sh
* publish.zip
* microsoft-spark-2-4_2.11-1.0.0.jar
* input.txt

1. Abra el Explorador de Azure Storage y vaya a la cuenta de almacenamiento en el menú de la izquierda. Explore en profundidad el contenedor de blobs del clúster en **Contenedores de blobs** en su cuenta de almacenamiento.

2. *Microsoft.Spark.Worker* ayuda a Apache Spark a ejecutar la aplicación, como cualquier función definida por el usuario (UDF) que se haya escrito. Descargue [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases/download/v1.0.0/Microsoft.Spark.Worker.netcoreapp3.1.linux-x64-1.0.0.tar.gz). Luego seleccione **Cargar** en el Explorador de Azure Storage para cargar el trabajo.

   ![Carga de archivos en el Explorador de Azure Storage](./media/hdinsight-deployment/upload-files-to-storage.png)

3. *install-worker.sh* es un script que permite copiar archivos dependientes de .NET para Apache Spark en los nodos del clúster.

   Cree un archivo con el nombre **install-worker.sh** en el equipo local y pegue el [contenido de install-worker.sh](https://raw.githubusercontent.com/dotnet/spark/master/deployment/install-worker.sh) que se encuentra en GitHub. Después, cargue *install-worker.sh* en el contenedor de blobs.

4. El clúster necesita el archivo *publish.zip* que contiene los archivos publicados de la aplicación. Vaya a la carpeta publicada, **mySparkApp/bin/Release/netcoreapp3.1/ubuntu.16.04-x64**, y busque **publish.zip**. Después, cargue *publish.zip* en el contenedor de blobs.

5. El clúster necesita el código de la aplicación que se ha empaquetado como un archivo jar, incluido como parte del paquete NuGet [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) y que se ha colocado en el directorio de salida de compilación de la aplicación. Vaya a la carpeta publicada, **mySparkApp/bin/Release/netcoreapp3.1/ubuntu.16.04-x64**, y busque **microsoft-spark-2-4_2.11-1.0.0.jar**. Después, cargue el archivo jar en el contenedor de blobs.

   Puede haber varios archivos .jar (para las versiones 2.3.x, 2.4.x y 3.0.x de Spark). Debe elegir el archivo .jar que coincida con la versión de Spark que se haya elegido durante la creación del clúster. Por ejemplo, elija *microsoft-spark-2-4_2.11-1.0.0.jar* si ha elegido Spark 2.4 durante la creación del clúster.

6. El clúster necesita la entrada a la aplicación. Vaya al directorio **mySparkApp** y busque **input.txt**. Cargue el archivo de entrada en el directorio **user/sshuser** en el contenedor de blobs. Se conectará al clúster mediante SSH y en esta carpeta es donde el clúster buscará su entrada. El archivo *input.txt* es el único archivo que se carga en un directorio concreto.

## <a name="run-the-hdinsight-script-action"></a>Ejecución de la acción de script de HDInsight

Cuando el clúster se esté ejecutando y haya cargado los archivos en Azure, ejecute el script **install-worker.sh** en el clúster.

1. Vaya al clúster de HDInsight de Spark en Azure Portal y luego seleccione **Acciones de script**.

2. Seleccione **+ Enviar nuevo** y proporcione los valores siguientes:

   |Propiedad  |Descripción  |
   |---------|---------|
   | Tipo de script |Personalizados|
   | NOMBRE | Instalación del trabajo|
   | URI de script de Bash |`https://mystorageaccount.blob.core.windows.net/mycontainer/install-worker.sh` </br> Para confirmar este URI, haga clic con el botón derecho en install-worker.sh en el Explorador de Azure Storage y seleccione Propiedades. |
   | Tipos de nodo| Trabajo|
   | Parámetros | azure </br> wasbs://mycontainer@myStorageAccount.blob.core.windows.net/Microsoft.Spark.Worker.netcoreapp3.1.linux-x64-1.0.0.tar.gz </br> /usr/local/bin

3. Seleccione **Crear** para enviar el script.

## <a name="run-your-app"></a>Ejecutar la aplicación

1. Vaya al clúster de HDInsight de Spark en Azure Portal y luego seleccione **SSH e inicio de sesión del clúster**.

2. Copie la información de inicio de sesión de SSH y pegue el inicio de sesión en un terminal. Inicie sesión en el clúster con la contraseña que se ha establecido durante la creación del clúster. Debería ver mensajes de bienvenida a Ubuntu y Spark.

3. Use el comando **spark-submit** para ejecutar la aplicación en el clúster de HDInsight. Recuerde reemplazar **mycontainer** y **mystorageaccount** en el script de ejemplo con los nombres reales del contenedor de blobs y la cuenta de almacenamiento.

   ```bash
   $SPARK_HOME/bin/spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/microsoft-spark-2-4_2.11-1.0.0.jar \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/publish.zip mySparkApp
   ```

   Cuando la aplicación se ejecute, verá la misma tabla de recuento de palabras de la ejecución local de introducción escrita en la consola. Enhorabuena, ha ejecutado su primera aplicación de .NET para Apache Spark en la nube.

## <a name="clean-up-resources"></a>Limpiar los recursos

HDInsight guarda los datos en Azure Storage, por lo que puede eliminar un clúster de forma segura cuando no se esté usando. También se le cobrará por un clúster de HDInsight aunque no se esté usando. Como en muchas ocasiones los cargos por el clúster son mucho más elevados que los cargos por el almacenamiento, desde el punto de vista económico tiene sentido eliminar clústeres cuando no se estén usando.

También puede seleccionar el nombre del grupo de recursos para abrir la página del grupo de recursos y, a continuación, seleccionar **Eliminar grupo de recursos**. Al eliminar el grupo de recursos, se eliminan tanto el clúster de HDInsight Spark como la cuenta de almacenamiento predeterminada.

## <a name="next-steps"></a>Pasos siguientes

En este tutorial ha implementado una aplicación de .NET para Apache Spark en Azure HDInsight. Para más información sobre HDInsight, continúe con la documentación de Azure HDInsight.

> [!div class="nextstepaction"]
> [Envío de trabajos de forma remota en Azure HDInsight](../how-to-guides/hdinsight-deploy-methods.md)
> [Documentación de Azure HDInsight](/azure/hdinsight/)
