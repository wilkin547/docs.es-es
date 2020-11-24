---
title: Conexión de .NET para Apache Spark a MongoDB
description: Obtenga información sobre cómo conectarse a la instancia de MongoDB desde la aplicación .NET para Apache Spark.
ms.author: nidutta
author: Niharikadutta
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 945e494e8a027d438bf4659d989da6033a13f6f0
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "94687608"
---
# <a name="connect-net-for-apache-spark-to-mongodb"></a>Conexión de .NET para Apache Spark a MongoDB

En este artículo, obtendrá información sobre cómo conectarse a una instancia de MongoDB desde la aplicación .NET para Apache Spark.

## <a name="prerequisites"></a>Requisitos previos

1. Debe tener un servidor de MongoDB activo y en ejecución, y agregarle una [base de datos y una colección](https://docs.mongodb.com/manual/core/databases-and-collections/). (Descargue [este servidor de la comunidad](https://www.mongodb.com/try/download/community) para un servidor local, o bien puede probar [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) para un servicio de MongoDB en la nube).

## <a name="set-up-your-mongodb-instance"></a>Configuración de la instancia de MongoDB

Para conseguir que .NET para Apache Spark se comunique con la instancia de MongoDB, debe seguir estos pasos para asegurarse de que está configurado correctamente:

1. Cree un nombre de usuario y una contraseña para que la aplicación se conecte, y asigne al usuario los permisos y roles necesarios con el comando siguiente a través del shell de Mongo:

    ```bash
    use database
    db.createUser(
      {
        user: "mySparkUser",
        pwd: "<password>",
        roles: [ { role: "userAdminAnyDatabase", db: "admin" }, "readWriteAnyDatabase" ]
      }
    )
    ```

2. Asegúrese de que la dirección IP del equipo en el que se ejecuta la aplicación .NET para Apache Spark esté en la lista de permitidos para que el servidor de MongoDB se pueda conectar a ella. Puede consultar [esta guía](https://docs.atlas.mongodb.com/security/add-ip-address-to-list/) para aprender a hacerlo.

## <a name="configure-your-net-for-apache-spark-application"></a>Configuración de la aplicación .NET para Apache Spark

1. Debe establecer las variables siguientes a fin de configurar la aplicación para que se comunique con la instancia de MongoDB y lea de una colección.
    1. **authURI**: "cadena de conexión que autoriza a la aplicación a conectarse a la instancia de MongoDB necesaria". El formato es el siguiente:

        ```
        "mongodb+srv://<username>:<password>@<cluster_address>/<database>.<collection>"
        ```

    2. **username**: nombre de usuario de la cuenta que ha creado en el paso 1 de la sección anterior.
    3. **password**: contraseña de la cuenta de usuario que ha creado.
    4. **cluster_address**: nombre de host/dirección del clúster de MongoDB.
    5. **database**: base de datos de MongoDB a la que quiere conectarse.
    6. **collection**: colección de MongoDB que quiere leer. (En este ejemplo se usa el archivo de ejemplo [`people.json`](https://github.com/apache/spark/blob/master/examples/src/main/resources/people.json) estándar proporcionado con cada instalación de Apache Spark).

2. Use el formato `com.mongodb.spark.sql.DefaultSource` de `spark.Read()` como se muestra a continuación en un sencillo fragmento de código:

    ```csharp
    class Program
    {
        static void Main()
        {
            var authURI = "mongodb+srv://<username>:<password>@<cluster_address>/<database>.<collection>?retryWrites=true&w=majority";
            SparkSession spark = SparkSession
                .Builder()
                .AppName("Connect to Mongo DB example")
                .Config("spark.mongodb.input.uri", authURI)
                .GetOrCreate();

            DataFrame df = spark.Read().Format("com.mongodb.spark.sql.DefaultSource").Load();
            df.PrintSchema();
            df.Show();
            spark.Stop();
        }
    }
    ```

## <a name="run-your-application"></a>Ejecución de la aplicación

A fin de ejecutar la aplicación .NET para Apache Spark, debe definir el módulo `mongo-spark-connector` como parte de la definición de compilación en el proyecto de Spark, con `libraryDependency` en `build.sbt` para los proyectos de sbt. Para entornos de Spark como `spark-submit` (o `spark-shell`), debe usar la opción de línea de comandos `--packages` de esta forma:

```bash
spark-submit --master local --packages org.mongodb.spark:mongo-spark-connector_2.12:3.0.0 --class org.apache.spark.deploy.dotnet.DotnetRunner microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar yourApp.exe
```

> [!NOTE]
> Asegúrese de incluir la versión del paquete correspondiente a la versión de Spark que se ejecuta.

El resultado es el objeto DataFrame (`df`), como se muestra a continuación:

```text
+--------------------+----+-------+
|                 _id| age|   name|
+--------------------+----+-------+
|[5f7c28438029a134...|null|Michael|
|[5f7c287f8029a134...|  30|   Andy|
|[5f7c289a8029a134...|  19| Justin|
+--------------------+----+-------+
```
