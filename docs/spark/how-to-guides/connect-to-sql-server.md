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
# <a name="connect-net-for-apache-spark-to-sql-server"></a>Conexión de .NET para Apache Spark a SQL Server

En este artículo, obtendrá información sobre cómo conectarse a una instancia de SQL Server desde la aplicación [.NET para Apache Spark](https://github.com/dotnet/spark).

## <a name="configure-sql-server-to-grant-your-application-access"></a>Configuración de SQL Server para conceder acceso a la aplicación

1. Seleccione la autenticación de SQL Server para agregar un usuario y una contraseña de inicio de sesión a la instancia de SQL Server.
2. Conceda a ese usuario que inicia sesión los permisos necesarios en el nivel de base de datos correspondiente, como se muestra a continuación:

    ![Permisos de SQL Server](./media/connect-external-sources/SqlServerAuth.png)

3. Asegúrese de que se permite el puerto predeterminado para SQL Server `1433` a través del firewall.
4. Abra el administrador de configuración de SQL para habilitar TCP/IP a través de la configuración de red, como se muestra a continuación:

    ![Habilitación de TCP/IP para SQL Server](./media/connect-external-sources/SqlServerTCPIP.png)

    Además, observe el valor de **Escuchar todo** de la pestaña anterior, en **Protocolo** .

5. Configure el puerto TCP/IP en 1433 para todas las direcciones IP necesarias si `Listen All` está establecido en `No`. De lo contrario, establezca el puerto TCP en IPAll.

    ![Puerto TCP/IP para SQL Server](./media/connect-external-sources/SQLServerTCPIIPPort.png)

## <a name="connect-to-sql-server-from-your-application"></a>Conexión a SQL Server desde la aplicación

1. Use Microsoft JDBC Driver para SQL Server a fin de proporcionar conectividad de base de datos a través de la aplicación (se puede descargar desde [este sitio web oficial](https://docs.microsoft.com/sql/connect/jdbc/download-microsoft-jdbc-driver-for-sql-server?view=sql-server-ver15)).
2. Establezca las configuraciones siguientes para conectarse a la instancia de SQL Server y a la base de datos desde la aplicación:
    1. **connection_url** : la dirección URL que se usa para conectarse a la instancia o base de datos de SQL Server, con el formato siguiente:

        ```
        jdbc:sqlserver://<SQL_server_IP_address>:1433;instanceName=<instance_name>;databaseName=<database_name>;
        ```

    2. **dbtable** : nombre de la tabla a la que se accede.
    3. **user** : usuario de inicio de sesión configurado en el paso 1 de la configuración de SQL Server.
    4. **password** : contraseña del usuario configurado en el paso 1 de la configuración de SQL Server.
3. Use la configuración anterior en el código de la aplicación para leer los datos de una tabla, como se muestra a continuación:

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
