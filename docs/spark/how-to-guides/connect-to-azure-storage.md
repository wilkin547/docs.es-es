---
title: Conexión al almacenamiento remoto desde el equipo local
description: Conéctese a cuentas de Azure Storage mediante .NET para Apache Spark desde el equipo local.
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 09e92b0cae848f9c98b691a11842f131f613396b
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2020
ms.locfileid: "91878049"
---
# <a name="connect-to-azure-data-lake-storage-gen-2-or-wasb-account"></a><span data-ttu-id="d66f4-103">Conexión a una cuenta de Azure Data Lake Storage Gen 2 o WASB</span><span class="sxs-lookup"><span data-stu-id="d66f4-103">Connect to Azure Data Lake Storage Gen 2 or WASB account</span></span>

<span data-ttu-id="d66f4-104">En este artículo, aprenderá a conectarse a una cuenta de Azure Data Lake Storage (ADLS) Gen 2 o Windows Azure Storage Blob (WASB) a través de una instancia de [.NET para Apache Spark](https://github.com/dotnet/spark) que se ejecuta de forma local en el equipo Windows.</span><span class="sxs-lookup"><span data-stu-id="d66f4-104">In this article, you learn how to connect to an Azure Data Lake Storage (ADLS) Gen 2 or Windows Azure Storage Blob (WASB) account through an instance of [.NET for Apache Spark](https://github.com/dotnet/spark) running locally on your Windows machine.</span></span>

## <a name="set-up-the-environment"></a><span data-ttu-id="d66f4-105">Configuración del entorno</span><span class="sxs-lookup"><span data-stu-id="d66f4-105">Set up the environment</span></span>

1. <span data-ttu-id="d66f4-106">Descargue la distribución Apache Spark compilada sin Hadoop desde el [sitio web oficial](https://archive.apache.org/dist/spark/) (elija una versión [compatible con .NET para Apache Spark](https://github.com/dotnet/spark#supported-apache-spark)) y extráigala en un directorio.</span><span class="sxs-lookup"><span data-stu-id="d66f4-106">Download the Apache Spark distribution built without Hadoop from [official website](https://archive.apache.org/dist/spark/) (choose a version [supported by .NET for Apache Spark](https://github.com/dotnet/spark#supported-apache-spark)), and extract it to a directory.</span></span> <span data-ttu-id="d66f4-107">Establezca la variable de entorno `SPARK_HOME` en este directorio.</span><span class="sxs-lookup"><span data-stu-id="d66f4-107">Set the environment variable `SPARK_HOME` to this directory.</span></span>
2. <span data-ttu-id="d66f4-108">Descargue [aquí](http://hadoop.apache.org/releases.html) el archivo binario de Apache Hadoop, extráigalo en una carpeta y establezca la variable de entorno `HADOOP_HOME` en esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="d66f4-108">Download the Apache Hadoop binary from [here](http://hadoop.apache.org/releases.html) and extract to a folder, and set your `HADOOP_HOME` environment variable to this folder.</span></span>
3. <span data-ttu-id="d66f4-109">Descargue los archivos `winutils.exe` y `hadoop.dll` desde [esta ubicación](https://github.com/cdarlint/winutils) (en función de la versión de Hadoop instalada en el paso anterior) y colóquelos en la carpeta bin de Hadoop.</span><span class="sxs-lookup"><span data-stu-id="d66f4-109">Download the `winutils.exe` and `hadoop.dll` files from [this location](https://github.com/cdarlint/winutils) (depending on the version of Hadoop installed in the previous step) and put them in the bin folder of your Hadoop.</span></span> <span data-ttu-id="d66f4-110">Estos archivos binarios son necesarios en Windows para que todo se configure correctamente (esto se explica en detalle en la [wiki de Apache](https://cwiki.apache.org/confluence/display/HADOOP2/WindowsProblems)).</span><span class="sxs-lookup"><span data-stu-id="d66f4-110">These binaries are needed on Windows in order to get everything setup correctly (this is explained in detail in the [Apache wiki here](https://cwiki.apache.org/confluence/display/HADOOP2/WindowsProblems)).</span></span>
4. <span data-ttu-id="d66f4-111">Para configurar la instalación de Hadoop, realice los cambios siguientes en el archivo `%HADOOP_HOME%\etc\hadoop\hadoop-env.cmd`:</span><span class="sxs-lookup"><span data-stu-id="d66f4-111">Configure your Hadoop installation by making the following changes to your `%HADOOP_HOME%\etc\hadoop\hadoop-env.cmd` file:</span></span>
    1. <span data-ttu-id="d66f4-112">Establezca la propiedad `JAVA_HOME` mediante la ruta de acceso de DOS (ya que a Hadoop no le gustan los espacios en `JAVA_HOME`).</span><span class="sxs-lookup"><span data-stu-id="d66f4-112">Set the `JAVA_HOME` property using the DOS path (since Hadoop doesn't like spaces in `JAVA_HOME`).</span></span> <span data-ttu-id="d66f4-113">Debería tener este aspecto: `C:\Progra~1\Java\jdk1.8.0_241` (Apunta a cualquier versión de Java que haya instalado en el equipo local).</span><span class="sxs-lookup"><span data-stu-id="d66f4-113">This should look something like this: `C:\Progra~1\Java\jdk1.8.0_241` (Pointing to whatever version of Java you have installed on your local machine).</span></span>
    2. <span data-ttu-id="d66f4-114">Anexe `%HADOOP_HOME%\share\hadoop\tools\lib\*` a `HADOOP_CLASSPATH`.</span><span class="sxs-lookup"><span data-stu-id="d66f4-114">Append `%HADOOP_HOME%\share\hadoop\tools\lib\*` to `HADOOP_CLASSPATH`.</span></span>
    <span data-ttu-id="d66f4-115">El archivo `hadoop-env.cmd` final debe tener un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="d66f4-115">Your final `hadoop-env.cmd` file should look something like this:</span></span>

    ![Archivo hadoop-env.cmd final](./media/connect-external-sources/hadoop-env.png)

## <a name="configure-your-storage-account-in-hadoop"></a><span data-ttu-id="d66f4-117">Configuración de la cuenta de almacenamiento en Hadoop</span><span class="sxs-lookup"><span data-stu-id="d66f4-117">Configure your storage account in Hadoop</span></span>

1. <span data-ttu-id="d66f4-118">Abra la cuenta de almacenamiento de ADLS Gen 2 o WASB a la que quiera conectarse a través de [Azure Portal](https://portal.azure.com), abra el panel **Claves de acceso** de la hoja **Configuración** y copie el valor de **Clave** en clave1.</span><span class="sxs-lookup"><span data-stu-id="d66f4-118">Open the ADLS Gen 2 or WASB storage account you want to connect to through the [Azure portal](https://portal.azure.com) and open the **Access keys** panel under the **Settings** blade and copy the value of **Key** from under key1.</span></span>
2. <span data-ttu-id="d66f4-119">Ahora, a fin de configurar Hadoop para acceder a la cuenta de ADLS Gen2, tendrá que editar el archivo `core-site.xml` (ubicado en `%HADOOP_HOME%\etc\hadoop\`) que contiene la configuración de todo el clúster.</span><span class="sxs-lookup"><span data-stu-id="d66f4-119">Now in order to configure Hadoop to access your ADLS Gen2 account you would have to edit your `core-site.xml` (located in `%HADOOP_HOME%\etc\hadoop\` ) file which contains cluster-wide configuration.</span></span> <span data-ttu-id="d66f4-120">Agregue las propiedades siguientes dentro de las etiquetas `<configuration>` de este archivo:</span><span class="sxs-lookup"><span data-stu-id="d66f4-120">Add the following properties inside the `<configuration>` tags in this file:</span></span>

    ```xml
    <configuration>
      <property>
        <name>fs.azure.account.auth.type.YOUR_ACCOUNT_NAME.dfs.core.windows.net</name>
        <value>SharedKey</value>
        <description></description>
      </property>
      <property>
        <name>fs.azure.account.key.YOUR_ACCOUNT_NAME.dfs.core.windows.net</name>
        <value>YOUR ACCESS KEY (copied from Step 1)</value>
        <description>The secret password. Never share these.</description>
      </property>
    </configuration>
    ```

    <span data-ttu-id="d66f4-121">Si intenta conectarse a una cuenta de WASB, reemplace `dfs` por `blob` en los nombres de propiedad.</span><span class="sxs-lookup"><span data-stu-id="d66f4-121">If you are trying to connect to a WASB account, replace `dfs` with `blob` in the property names.</span></span> <span data-ttu-id="d66f4-122">Por ejemplo, `fs.azure.account.auth.type.YOUR_ACCOUNT_NAME.blob.core.windows.net`.</span><span class="sxs-lookup"><span data-stu-id="d66f4-122">For example, `fs.azure.account.auth.type.YOUR_ACCOUNT_NAME.blob.core.windows.net`.</span></span>
3. <span data-ttu-id="d66f4-123">Puede probar la conectividad a la cuenta de almacenamiento desde Hadoop si ejecuta el comando siguiente desde el directorio `%HADOOP_HOME%`:</span><span class="sxs-lookup"><span data-stu-id="d66f4-123">You can test the connectivity to your Storage Account from Hadoop by running the following command from your `%HADOOP_HOME%` directory:</span></span>

    ```bash
    bin\hdfs dfs -ls <URI to your account>
    ```

<span data-ttu-id="d66f4-124">Esto debería mostrar una lista de todos los archivos o carpetas en la ruta de acceso proporcionada por el URI.</span><span class="sxs-lookup"><span data-stu-id="d66f4-124">This should display a list of all files/folders in the path provided by your URI.</span></span>

> [!NOTE]
> <span data-ttu-id="d66f4-125">El formato para derivar el URI de la cuenta de almacenamiento es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="d66f4-125">The format to derive the URI to your Storage account is as follows:</span></span>
>
> ```
> For ADLS: abfs[s]://<file_system>@<account_name>.dfs.core.windows.net/<path>/<file_name>
> For WASB: wasb[s]://<file_system>@<account_name>.blob.core.windows.net/<path>/<file_name>
> ```

## <a name="connect-to-your-storage-account"></a><span data-ttu-id="d66f4-126">Conexión a la cuenta de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="d66f4-126">Connect to your storage account</span></span>

1. <span data-ttu-id="d66f4-127">Si el comando anterior ha funcionado, ya puede pasar a acceder a esta cuenta de almacenamiento a través de Spark.</span><span class="sxs-lookup"><span data-stu-id="d66f4-127">If the above command worked, you can now move on to accessing this storage account through Spark.</span></span> <span data-ttu-id="d66f4-128">En primer lugar, ejecute el comando `hadoop classpath` desde la línea de comandos dentro de `%HADOOP_HOME%` y copie la salida.</span><span class="sxs-lookup"><span data-stu-id="d66f4-128">First run the command `hadoop classpath` from the commandline inside `%HADOOP_HOME%` and copy the output.</span></span>
2. <span data-ttu-id="d66f4-129">Establezca la salida del comando ejecutado en el paso 1 en el valor de la variable de entorno `SPARK_DIST_CLASSPATH`.</span><span class="sxs-lookup"><span data-stu-id="d66f4-129">Set the output of the command run in Step 1 to the value of environment variable `SPARK_DIST_CLASSPATH`.</span></span>
3. <span data-ttu-id="d66f4-130">Ahora debería poder acceder a la cuenta de almacenamiento de ADLS o WASB a través de .NET para Spark mediante el URI de abfs, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="d66f4-130">Now you should be able to access your ADLS or WASB storage account through Spark .NET using the abfs URI as shown in the simple example below.</span></span> <span data-ttu-id="d66f4-131">(En este ejemplo se usa el archivo de ejemplo [`people.json`](https://github.com/apache/spark/blob/master/examples/src/main/resources/people.json) estándar proporcionado con cada instalación de Apache Spark).:</span><span class="sxs-lookup"><span data-stu-id="d66f4-131">(For this example we use the standard [`people.json`](https://github.com/apache/spark/blob/master/examples/src/main/resources/people.json) example file provided with every Apache Spark installation.):</span></span>

    ```csharp
    SparkSession spark = SparkSession
       .Builder()
       .AppName("Connect to Azure Storage locally")
       .GetOrCreate();
    DataFrame df = spark.Read().Json("wasbs://file_system@account_name.blob.core.windows.net/path/people.json");
    //DataFrame df = spark.Read().Json("abfss://file_system@account_name.dfs.core.windows.net/path/file.json");
    df.Show();
    ```

    <span data-ttu-id="d66f4-132">El resultado es el objeto DataFrame (`df`), como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="d66f4-132">The result as displayed is the DataFrame (`df`) as shown below:</span></span>

    ```text
    +----+-------+
    | age|   name|
    +----+-------+
    |null|Michael|
    |  30|   Andy|
    |  19| Justin|
    +----+-------+
    ```
