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
# <a name="connect-to-azure-data-lake-storage-gen-2-or-wasb-account"></a>Conexión a una cuenta de Azure Data Lake Storage Gen 2 o WASB

En este artículo, aprenderá a conectarse a una cuenta de Azure Data Lake Storage (ADLS) Gen 2 o Windows Azure Storage Blob (WASB) a través de una instancia de [.NET para Apache Spark](https://github.com/dotnet/spark) que se ejecuta de forma local en el equipo Windows.

## <a name="set-up-the-environment"></a>Configuración del entorno

1. Descargue la distribución Apache Spark compilada sin Hadoop desde el [sitio web oficial](https://archive.apache.org/dist/spark/) (elija una versión [compatible con .NET para Apache Spark](https://github.com/dotnet/spark#supported-apache-spark)) y extráigala en un directorio. Establezca la variable de entorno `SPARK_HOME` en este directorio.
2. Descargue [aquí](http://hadoop.apache.org/releases.html) el archivo binario de Apache Hadoop, extráigalo en una carpeta y establezca la variable de entorno `HADOOP_HOME` en esta carpeta.
3. Descargue los archivos `winutils.exe` y `hadoop.dll` desde [esta ubicación](https://github.com/cdarlint/winutils) (en función de la versión de Hadoop instalada en el paso anterior) y colóquelos en la carpeta bin de Hadoop. Estos archivos binarios son necesarios en Windows para que todo se configure correctamente (esto se explica en detalle en la [wiki de Apache](https://cwiki.apache.org/confluence/display/HADOOP2/WindowsProblems)).
4. Para configurar la instalación de Hadoop, realice los cambios siguientes en el archivo `%HADOOP_HOME%\etc\hadoop\hadoop-env.cmd`:
    1. Establezca la propiedad `JAVA_HOME` mediante la ruta de acceso de DOS (ya que a Hadoop no le gustan los espacios en `JAVA_HOME`). Debería tener este aspecto: `C:\Progra~1\Java\jdk1.8.0_241` (Apunta a cualquier versión de Java que haya instalado en el equipo local).
    2. Anexe `%HADOOP_HOME%\share\hadoop\tools\lib\*` a `HADOOP_CLASSPATH`.
    El archivo `hadoop-env.cmd` final debe tener un aspecto similar al siguiente:

    ![Archivo hadoop-env.cmd final](./media/connect-external-sources/hadoop-env.png)

## <a name="configure-your-storage-account-in-hadoop"></a>Configuración de la cuenta de almacenamiento en Hadoop

1. Abra la cuenta de almacenamiento de ADLS Gen 2 o WASB a la que quiera conectarse a través de [Azure Portal](https://portal.azure.com), abra el panel **Claves de acceso** de la hoja **Configuración** y copie el valor de **Clave** en clave1.
2. Ahora, a fin de configurar Hadoop para acceder a la cuenta de ADLS Gen2, tendrá que editar el archivo `core-site.xml` (ubicado en `%HADOOP_HOME%\etc\hadoop\`) que contiene la configuración de todo el clúster. Agregue las propiedades siguientes dentro de las etiquetas `<configuration>` de este archivo:

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

    Si intenta conectarse a una cuenta de WASB, reemplace `dfs` por `blob` en los nombres de propiedad. Por ejemplo, `fs.azure.account.auth.type.YOUR_ACCOUNT_NAME.blob.core.windows.net`.
3. Puede probar la conectividad a la cuenta de almacenamiento desde Hadoop si ejecuta el comando siguiente desde el directorio `%HADOOP_HOME%`:

    ```bash
    bin\hdfs dfs -ls <URI to your account>
    ```

Esto debería mostrar una lista de todos los archivos o carpetas en la ruta de acceso proporcionada por el URI.

> [!NOTE]
> El formato para derivar el URI de la cuenta de almacenamiento es el siguiente:
>
> ```
> For ADLS: abfs[s]://<file_system>@<account_name>.dfs.core.windows.net/<path>/<file_name>
> For WASB: wasb[s]://<file_system>@<account_name>.blob.core.windows.net/<path>/<file_name>
> ```

## <a name="connect-to-your-storage-account"></a>Conexión a la cuenta de almacenamiento

1. Si el comando anterior ha funcionado, ya puede pasar a acceder a esta cuenta de almacenamiento a través de Spark. En primer lugar, ejecute el comando `hadoop classpath` desde la línea de comandos dentro de `%HADOOP_HOME%` y copie la salida.
2. Establezca la salida del comando ejecutado en el paso 1 en el valor de la variable de entorno `SPARK_DIST_CLASSPATH`.
3. Ahora debería poder acceder a la cuenta de almacenamiento de ADLS o WASB a través de .NET para Spark mediante el URI de abfs, como se muestra en el ejemplo siguiente. (En este ejemplo se usa el archivo de ejemplo [`people.json`](https://github.com/apache/spark/blob/master/examples/src/main/resources/people.json) estándar proporcionado con cada instalación de Apache Spark).:

    ```csharp
    SparkSession spark = SparkSession
       .Builder()
       .AppName("Connect to Azure Storage locally")
       .GetOrCreate();
    DataFrame df = spark.Read().Json("wasbs://file_system@account_name.blob.core.windows.net/path/people.json");
    //DataFrame df = spark.Read().Json("abfss://file_system@account_name.dfs.core.windows.net/path/file.json");
    df.Show();
    ```

    El resultado es el objeto DataFrame (`df`), como se muestra a continuación:

    ```text
    +----+-------+
    | age|   name|
    +----+-------+
    |null|Michael|
    |  30|   Andy|
    |  19| Justin|
    +----+-------+
    ```
