---
title: Conexión de .NET para Apache Spark a SQL Server
description: Obtenga información sobre cómo conectarse a una instancia de SQL Server desde la aplicación .NET para Apache Spark.
ms.author: nidutta
author: Niharikadutta
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: b20710000d8717b5df238aa9a782371fbe586037
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2020
ms.locfileid: "92224026"
---
# <a name="connect-net-for-apache-spark-to-sql-server"></a><span data-ttu-id="06f05-103">Conexión de .NET para Apache Spark a SQL Server</span><span class="sxs-lookup"><span data-stu-id="06f05-103">Connect .NET for Apache Spark to SQL Server</span></span>

<span data-ttu-id="06f05-104">En este artículo, obtendrá información sobre cómo conectarse a una instancia de SQL Server desde la aplicación [.NET para Apache Spark](https://github.com/dotnet/spark).</span><span class="sxs-lookup"><span data-stu-id="06f05-104">In this article, you learn how to connect to an SQL server instance from your [.NET for Apache Spark](https://github.com/dotnet/spark) application.</span></span>

## <a name="configure-sql-server-to-grant-your-application-access"></a><span data-ttu-id="06f05-105">Configuración de SQL Server para conceder acceso a la aplicación</span><span class="sxs-lookup"><span data-stu-id="06f05-105">Configure SQL Server to grant your application access</span></span>

1. <span data-ttu-id="06f05-106">Seleccione la autenticación de SQL Server para agregar un usuario y una contraseña de inicio de sesión a la instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="06f05-106">Add a login user and password choosing SQL Server authentication to your SQL Server instance.</span></span>
2. <span data-ttu-id="06f05-107">Conceda a ese usuario que inicia sesión los permisos necesarios en el nivel de base de datos correspondiente, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="06f05-107">Give that login user necessary permissions at the relevant database level as shown below:</span></span>

    ![Permisos de SQL Server](./media/connect-external-sources/SqlServerAuth.png)

3. <span data-ttu-id="06f05-109">Asegúrese de que se permite el puerto predeterminado para SQL Server `1433` a través del firewall.</span><span class="sxs-lookup"><span data-stu-id="06f05-109">Make sure the default port for SQL Server `1433` is allowed through the firewall.</span></span>
4. <span data-ttu-id="06f05-110">Abra el administrador de configuración de SQL para habilitar TCP/IP a través de la configuración de red, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="06f05-110">Open SQL configure manager to enable TCP/IP through the network configuration as shown below:</span></span>

    ![Habilitación de TCP/IP para SQL Server](./media/connect-external-sources/SqlServerTCPIP.png)

    <span data-ttu-id="06f05-112">Además, observe el valor de **Escuchar todo** de la pestaña anterior, en **Protocolo** .</span><span class="sxs-lookup"><span data-stu-id="06f05-112">Also note the value of **Listen All** in above tab under **Protocol** .</span></span>

5. <span data-ttu-id="06f05-113">Configure el puerto TCP/IP en 1433 para todas las direcciones IP necesarias si `Listen All` está establecido en `No`.</span><span class="sxs-lookup"><span data-stu-id="06f05-113">Configure the TCP/IP port to 1433 for all required IP addresses if the `Listen All` is set to `No`.</span></span> <span data-ttu-id="06f05-114">De lo contrario, establezca el puerto TCP en IPAll.</span><span class="sxs-lookup"><span data-stu-id="06f05-114">Otherwise, set the TCP Port in IPAll.</span></span>

    ![Puerto TCP/IP para SQL Server](./media/connect-external-sources/SQLServerTCPIIPPort.png)

## <a name="connect-to-sql-server-from-your-application"></a><span data-ttu-id="06f05-116">Conexión a SQL Server desde la aplicación</span><span class="sxs-lookup"><span data-stu-id="06f05-116">Connect to SQL Server from your application</span></span>

1. <span data-ttu-id="06f05-117">Use Microsoft JDBC Driver para SQL Server a fin de proporcionar conectividad de base de datos a través de la aplicación (se puede descargar desde [este sitio web oficial](https://docs.microsoft.com/sql/connect/jdbc/download-microsoft-jdbc-driver-for-sql-server?view=sql-server-ver15)).</span><span class="sxs-lookup"><span data-stu-id="06f05-117">Use the Microsoft JDBC Driver for SQL Server to provide database connectivity through your application (download from [this official website](https://docs.microsoft.com/sql/connect/jdbc/download-microsoft-jdbc-driver-for-sql-server?view=sql-server-ver15)).</span></span>
2. <span data-ttu-id="06f05-118">Establezca las configuraciones siguientes para conectarse a la instancia de SQL Server y a la base de datos desde la aplicación:</span><span class="sxs-lookup"><span data-stu-id="06f05-118">Set the following configurations to connect to the SQL server instance and database from your application:</span></span>
    1. <span data-ttu-id="06f05-119">**connection_url** : la dirección URL que se usa para conectarse a la instancia o base de datos de SQL Server, con el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="06f05-119">**connection_url** : This is the URL used to connect to the SQL server instance/database and has the following format:</span></span>

        ```
        jdbc:sqlserver://<SQL_server_IP_address>:1433;instanceName=<instance_name>;databaseName=<database_name>;
        ```

    2. <span data-ttu-id="06f05-120">**dbtable** : nombre de la tabla a la que se accede.</span><span class="sxs-lookup"><span data-stu-id="06f05-120">**dbtable** : Name of table being accessed.</span></span>
    3. <span data-ttu-id="06f05-121">**user** : usuario de inicio de sesión configurado en el paso 1 de la configuración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="06f05-121">**user** : Login user set up in Step 1 of configuring the SQL server.</span></span>
    4. <span data-ttu-id="06f05-122">**password** : contraseña del usuario configurado en el paso 1 de la configuración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="06f05-122">**password** : Password of user set up in Step 1 of configuring the SQL server.</span></span>
3. <span data-ttu-id="06f05-123">Use la configuración anterior en el código de la aplicación para leer los datos de una tabla, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="06f05-123">Use the above configuration in your application code to read the data from a table as shown below:</span></span>

    ```csharp
    static void Main()
    {
        SparkSession spark = SparkSession
            .Builder()
            .AppName("Connect to SQL Server")
            .GetOrCreate();

        string connection_url = "<URL to connect to SQL server instance>";
        string dbtable = "<database table to access>";
        string user = "<Login user name>";
        string password = "<Login user password>";

        DataFrame jdbcDF = spark.Read()
            .Format("jdbc")
            .Option("driver", "com.microsoft.sqlserver.jdbc.SQLServerDriver")
            .Option("url", connection_url)
            .Option("dbtable", dbtable)
            .Option("user", user)
            .Option("password", password).Load();
        jdbcDF.Show(); // Displays the content of the SQL table as a DataFrame
    }
    ```
