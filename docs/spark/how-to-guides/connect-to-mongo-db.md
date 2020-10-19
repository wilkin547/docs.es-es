---
title: Conexión de .NET para Apache Spark a MongoDB
description: Obtenga información sobre cómo conectarse a la instancia de MongoDB desde la aplicación .NET para Apache Spark.
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 4cb78998ddb54621a84e9d224a814047e3c40246
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2020
ms.locfileid: "91878055"
---
# <a name="connect-net-for-apache-spark-to-mongodb"></a><span data-ttu-id="3c193-103">Conexión de .NET para Apache Spark a MongoDB</span><span class="sxs-lookup"><span data-stu-id="3c193-103">Connect .NET for Apache Spark to MongoDB</span></span>

<span data-ttu-id="3c193-104">En este artículo, obtendrá información sobre cómo conectarse a una instancia de MongoDB desde la aplicación .NET para Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="3c193-104">In this article, you learn how to connect to a MongoDB instance from your .NET for Apache Spark application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3c193-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3c193-105">Prerequisites</span></span>

1. <span data-ttu-id="3c193-106">Debe tener un servidor de MongoDB activo y en ejecución, y agregarle una [base de datos y una colección](https://docs.mongodb.com/manual/core/databases-and-collections/). (Descargue [este servidor de la comunidad](https://www.mongodb.com/try/download/community) para un servidor local, o bien puede probar [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) para un servicio de MongoDB en la nube).</span><span class="sxs-lookup"><span data-stu-id="3c193-106">Have a MongoDB server up and running with a [database and some collection](https://docs.mongodb.com/manual/core/databases-and-collections/) added to it (Download [this community server](https://www.mongodb.com/try/download/community) for a local server or you can try [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) for a cloud MongoDB service.)</span></span>

## <a name="set-up-your-mongodb-instance"></a><span data-ttu-id="3c193-107">Configuración de la instancia de MongoDB</span><span class="sxs-lookup"><span data-stu-id="3c193-107">Set up your MongoDB instance</span></span>

<span data-ttu-id="3c193-108">Para conseguir que .NET para Apache Spark se comunique con la instancia de MongoDB, debe seguir estos pasos para asegurarse de que está configurado correctamente:</span><span class="sxs-lookup"><span data-stu-id="3c193-108">In order to get .NET for Apache Spark to talk to your MongoDB instance you need to make sure it is set up correctly by doing the following:</span></span>

1. <span data-ttu-id="3c193-109">Cree un nombre de usuario y una contraseña para que la aplicación se conecte, y asigne al usuario los permisos y roles necesarios con el comando siguiente a través del shell de Mongo:</span><span class="sxs-lookup"><span data-stu-id="3c193-109">Create a username and password for your application to connect through, and give the user the necessary permissions/roles using the following command through mongo shell:</span></span>

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

2. <span data-ttu-id="3c193-110">Asegúrese de que la dirección IP del equipo en el que se ejecuta la aplicación .NET para Apache Spark esté en la lista de permitidos para que el servidor de MongoDB se pueda conectar a ella.</span><span class="sxs-lookup"><span data-stu-id="3c193-110">Make sure the IP address of the machine your .NET for Apache Spark application is running on is whitelisted for the MongoDB server to be able to connect to.</span></span> <span data-ttu-id="3c193-111">Puede consultar [esta guía](https://docs.atlas.mongodb.com/security/add-ip-address-to-list/) para aprender a hacerlo.</span><span class="sxs-lookup"><span data-stu-id="3c193-111">You can refer to [this guide](https://docs.atlas.mongodb.com/security/add-ip-address-to-list/) to learn how to do that.</span></span>

## <a name="configure-your-net-for-apache-spark-application"></a><span data-ttu-id="3c193-112">Configuración de la aplicación .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="3c193-112">Configure your .NET for Apache Spark application</span></span>

1. <span data-ttu-id="3c193-113">Debe establecer las variables siguientes a fin de configurar la aplicación para que se comunique con la instancia de MongoDB y lea de una colección.</span><span class="sxs-lookup"><span data-stu-id="3c193-113">Have the following variables set to configure your application to talk to the MongoDB instance and read from a collection.</span></span>
    1. <span data-ttu-id="3c193-114">**authURI**: "cadena de conexión que autoriza a la aplicación a conectarse a la instancia de MongoDB necesaria".</span><span class="sxs-lookup"><span data-stu-id="3c193-114">**authURI**: "Connection string authorizing your application to connect to the required MongoDB instance".</span></span> <span data-ttu-id="3c193-115">El formato es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="3c193-115">The format for that is as follows:</span></span>

        ```
        "mongodb+srv://<username>:<password>@<cluster_address>/<database>.<collection>"
        ```

    2. <span data-ttu-id="3c193-116">**username**: nombre de usuario de la cuenta que ha creado en el paso 1 de la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="3c193-116">**username**: Username of the account you created in Step 1 of the previous section</span></span>
    3. <span data-ttu-id="3c193-117">**password**: contraseña de la cuenta de usuario que ha creado.</span><span class="sxs-lookup"><span data-stu-id="3c193-117">**password**: Password of the user account created</span></span>
    4. <span data-ttu-id="3c193-118">**cluster_address**: nombre de host/dirección del clúster de MongoDB.</span><span class="sxs-lookup"><span data-stu-id="3c193-118">**cluster_address**: hostname/address of your MongoDB cluster</span></span>
    5. <span data-ttu-id="3c193-119">**database**: base de datos de MongoDB a la que quiere conectarse.</span><span class="sxs-lookup"><span data-stu-id="3c193-119">**database**: The MongoDB database you want to connect to</span></span>
    6. <span data-ttu-id="3c193-120">**collection**: colección de MongoDB que quiere leer.</span><span class="sxs-lookup"><span data-stu-id="3c193-120">**collection**: The MongoDB collection you want to read.</span></span> <span data-ttu-id="3c193-121">(En este ejemplo se usa el archivo de ejemplo [`people.json`](https://github.com/apache/spark/blob/master/examples/src/main/resources/people.json) estándar proporcionado con cada instalación de Apache Spark).</span><span class="sxs-lookup"><span data-stu-id="3c193-121">(For this example we use the standard [`people.json`](https://github.com/apache/spark/blob/master/examples/src/main/resources/people.json) example file provided with every Apache Spark installation.)</span></span>

2. <span data-ttu-id="3c193-122">Use el formato `com.mongodb.spark.sql.DefaultSource` de `spark.Read()` como se muestra a continuación en un sencillo fragmento de código:</span><span class="sxs-lookup"><span data-stu-id="3c193-122">Use the `com.mongodb.spark.sql.DefaultSource` format is `spark.Read()` as shown below in a simple code snippet:</span></span>

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

## <a name="run-your-application"></a><span data-ttu-id="3c193-123">Ejecución de la aplicación</span><span class="sxs-lookup"><span data-stu-id="3c193-123">Run your application</span></span>

<span data-ttu-id="3c193-124">A fin de ejecutar la aplicación .NET para Apache Spark, debe definir el módulo `mongo-spark-connector` como parte de la definición de compilación en el proyecto de Spark, con `libraryDependency` en `build.sbt` para los proyectos de sbt.</span><span class="sxs-lookup"><span data-stu-id="3c193-124">In order to run your .NET for Apache Spark application, you should define the `mongo-spark-connector` module as part of the build definition in your Spark project, using `libraryDependency` in `build.sbt` for sbt projects.</span></span> <span data-ttu-id="3c193-125">Para entornos de Spark como `spark-submit` (o `spark-shell`), debe usar la opción de línea de comandos `--packages` de esta forma:</span><span class="sxs-lookup"><span data-stu-id="3c193-125">For Spark environments such as `spark-submit` (or `spark-shell`) you should use the `--packages` command-line option like so:</span></span>

```bash
spark-submit --master local --packages org.mongodb.spark:mongo-spark-connector_2.12:3.0.0 --class org.apache.spark.deploy.dotnet.DotnetRunner microsoft-spark-<version>.jar yourApp.exe
```

> [!NOTE]
> <span data-ttu-id="3c193-126">Asegúrese de incluir la versión del paquete correspondiente a la versión de Spark que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="3c193-126">Make sure to include the package version in accordance with the version of Spark being run.</span></span>

<span data-ttu-id="3c193-127">El resultado es el objeto DataFrame (`df`), como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="3c193-127">The result as displayed is the DataFrame (`df`) as shown below:</span></span>

```text
+--------------------+----+-------+
|                 _id| age|   name|
+--------------------+----+-------+
|[5f7c28438029a134...|null|Michael|
|[5f7c287f8029a134...|  30|   Andy|
|[5f7c289a8029a134...|  19| Justin|
+--------------------+----+-------+
```
