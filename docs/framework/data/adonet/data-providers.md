---
title: Proveedores de datos .NET Framework
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 03a9fc62-2d24-491a-9fe6-d6bdb6dcb131
ms.openlocfilehash: d343f7be3e26575ee9a1e9ccae9f17314db10ac5
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2019
ms.locfileid: "65882114"
---
# <a name="net-framework-data-providers"></a>Proveedores de datos .NET Framework
Un proveedor de datos de .NET Framework se usa para conectarse a una base de datos, ejecutar comandos y recuperar resultados. Esos resultados se procesan directamente, se colocan en un <xref:System.Data.DataSet> con el fin de que el usuario pueda verlos cuando los necesite, se combinan con datos de varios orígenes o se utilizan de forma remota entre niveles. Proveedores de datos .NET framework son ligeros, crean un nivel mínimo entre el origen de datos y el código, aumentar el rendimiento sin sacrificar funcionalidad.  
  
 En la tabla siguiente se enumera los proveedores de datos que se incluyen en .NET Framework.  
  
|proveedor de datos de .NET Framework (.NET Framework data provider)|Descripción|  
|-------------------------------------------------------------------------------|-----------------|  
|Proveedor de datos .NET Framework para SQL Server|Proporciona acceso de datos para Microsoft SQL Server. Utiliza el espacio de nombres <xref:System.Data.SqlClient> .|  
|Proveedor de datos .NET Framework para OLE DB|Para orígenes de datos que se exponen mediante OLE DB. Utiliza el espacio de nombres <xref:System.Data.OleDb> .|  
|Proveedor de datos .NET Framework para ODBC|Para orígenes de datos que se exponen mediante ODBC. Utiliza el espacio de nombres <xref:System.Data.Odbc> .|  
|Proveedor de datos .NET Framework para Oracle|Para orígenes de datos de Oracle. El proveedor de datos de .NET Framework para Oracle admite Oracle versión 8.1.7 del software cliente y versiones posteriores y usa el <xref:System.Data.OracleClient> espacio de nombres.|  
|Proveedor para EntityClient|Proporciona acceso a datos para las aplicaciones de Entity Data Model (EDM). Utiliza el espacio de nombres <xref:System.Data.EntityClient> .|  
|Proveedor de datos de .NET framework para SQL Server Compact 4.0.|Proporciona acceso a datos para Microsoft SQL Server Compact 4.0. Usa el espacio de nombres [System.Data.SqlServerCe](https://docs.microsoft.com/previous-versions/sql/compact/sql-server-compact-4.0/ec4st0e3(v=vs.100)) .|  
  
## <a name="core-objects-of-net-framework-data-providers"></a>Objetos principales de los proveedores de datos .NET Framework  
 En la tabla siguiente se describe los cuatro objetos centrales que constituyen un proveedor de datos de .NET Framework.  
  
|Object|Descripción|  
|------------|-----------------|  
|`Connection`|Establece una conexión a un origen de datos determinado. La clase base para todos los objetos `Connection` es <xref:System.Data.Common.DbConnection> .|  
|`Command`|Ejecuta un comando en un origen de datos. Expone `Parameters` y puede ejecutarse en el ámbito de un objeto `Transaction` desde `Connection`. La clase base para todos los objetos `Command` es <xref:System.Data.Common.DbCommand> .|  
|`DataReader`|Lee un flujo de datos de solo avance y solo lectura desde un origen de datos. La clase base para todos los objetos `DataReader` es <xref:System.Data.Common.DbDataReader> .|  
|`DataAdapter`|Llena un `DataSet` y realiza las actualizaciones necesarias en el origen de datos. La clase base para todos los objetos `DataAdapter` es <xref:System.Data.Common.DbDataAdapter> .|  
  
 Además de las clases principales que se muestran en la tabla anteriormente en este documento, un proveedor de datos de .NET Framework también contiene las clases enumeradas en la tabla siguiente.  
  
|Object|Descripción|  
|------------|-----------------|  
|`Transaction`|Incluye comandos en las transacciones que se realizan en el origen de datos. La clase base para todos los objetos `Transaction` es <xref:System.Data.Common.DbTransaction> . ADO.NET es también compatible con las transacciones que usan clases en el espacio de nombres <xref:System.Transactions> .|  
|`CommandBuilder`|Un objeto del asistente que genera automáticamente las propiedades de comando de un `DataAdapter` o que obtiene de un procedimiento almacenado información acerca de parámetros con la que puede rellenar la colección `Parameters` de un objeto `Command`. La clase base para todos los objetos `CommandBuilder` es <xref:System.Data.Common.DbCommandBuilder> .|  
|`ConnectionStringBuilder`|Un objeto del asistente que proporciona un modo sencillo de crear y administrar el contenido de las cadenas de conexión utilizadas por los objetos `Connection`. La clase base para todos los objetos `ConnectionStringBuilder` es <xref:System.Data.Common.DbConnectionStringBuilder> .|  
|`Parameter`|Define los parámetros de entrada, salida y valores devueltos para los comandos y procedimientos almacenados. La clase base para todos los objetos `Parameter` es <xref:System.Data.Common.DbParameter> .|  
|`Exception`|Se devuelve cuando se detecta un error en el origen de datos. Para un error encontrado en el cliente, los proveedores de datos .NET Framework inician una excepción de .NET Framework. La clase base para todos los objetos `Exception` es <xref:System.Data.Common.DbException> .|  
|`Error`|Expone la información relacionada con una advertencia o error devueltos por un origen de datos.|  
|`ClientPermission`|Se proporciona para los atributos de seguridad de acceso de código proveedores de datos de .NET Framework. La clase base para todos los objetos `ClientPermission` es <xref:System.Data.Common.DBDataPermission> .|  
  
## <a name="net-framework-data-provider-for-sql-server-sqlclient"></a>Proveedor de datos .NET Framework para SQL Server (SqlClient)  
 El proveedor de datos de .NET Framework para SQL Server (SqlClient) usa su propio protocolo para comunicarse con SQL Server. Es ligero y funciona bien porque está optimizado para tener acceso a un servidor SQL Server directamente, sin agregar una capa OLE DB u Open Database Connectivity (ODBC). La siguiente ilustración compara el proveedor de datos de .NET Framework para SQL Server con el proveedor de datos de .NET Framework para OLE DB. El proveedor de datos de .NET Framework para OLE DB se comunica con un origen de datos OLE DB a través del componente de servicio OLE DB, que proporciona agrupación de conexiones y servicios de transacción y el proveedor OLE DB para el origen de datos.  
  
> [!NOTE]
>  El proveedor de datos de .NET Framework para ODBC tiene una arquitectura similar para el proveedor de datos de .NET Framework para OLE DB; Por ejemplo, llama a un componente de servicio ODBC.  
  
 ![Proveedores de datos](../../../../docs/framework/data/adonet/media/netdataproviders-bpuedev11.gif "NETDataProviders_bpuedev11")  
Comparación del proveedor de datos .NET Framework para SQL Server y el proveedor de datos .NET Framework para OLE DB  
  
 El proveedor de datos de .NET Framework para las clases de SQL Server se encuentran en el <xref:System.Data.SqlClient> espacio de nombres.  
  
 El proveedor de datos de .NET Framework para SQL Server admite tanto transacciones locales como distribuidas. Para las transacciones distribuidas, el proveedor de datos de .NET Framework para SQL Server, de forma predeterminada, automáticamente se da de alta en una transacción y obtiene los detalles de los servicios de componentes de Windows o <xref:System.Transactions>. Para obtener más información, consulte [transacciones y simultaneidad](../../../../docs/framework/data/adonet/transactions-and-concurrency.md).  
  
 En el siguiente ejemplo de código se muestra cómo puede incluir el espacio de nombres `System.Data.SqlClient` en sus aplicaciones.  
  
```vb  
Imports System.Data.SqlClient  
```  
  
```csharp  
using System.Data.SqlClient;  
```  
  
## <a name="net-framework-data-provider-for-ole-db"></a>Proveedor de datos .NET Framework para OLE DB  
 El proveedor de datos de .NET Framework para OLE DB (OleDb) usa OLE DB nativo mediante la interoperabilidad COM para habilitar el acceso a datos. El proveedor de datos de .NET Framework para OLE DB admite tanto transacciones locales como distribuidas. Para las transacciones distribuidas, el proveedor de datos de .NET Framework para OLE DB, de forma predeterminada, automáticamente se da de alta en una transacción y obtiene los detalles de los servicios de componentes de Windows. Para obtener más información, consulte [transacciones y simultaneidad](../../../../docs/framework/data/adonet/transactions-and-concurrency.md).  
  
 La siguiente tabla muestra los proveedores que se han probado con ADO.NET.  
  
|Controlador|Proveedor|  
|------------|--------------|  
|SQLOLEDB|Proveedor Microsoft OLE DB para SQL Server|  
|MSDAORA|Proveedor Microsoft OLE DB para Oracle|  
|Microsoft.Jet.OLEDB.4.0|Proveedor OLE DB para Microsoft Jet|  
  
> [!NOTE]
>  No se recomienda usar una base de datos de Access (Jet) como origen de datos para aplicaciones multiproceso, como las aplicaciones ASP.NET. Si debe utilizar Jet como origen de datos para una aplicación ASP.NET, tenga en cuenta que las aplicaciones de ASP.NET para conectarse a una base de datos pueden tener problemas de conexión.  
  
 El proveedor de datos de .NET Framework para OLE DB no admite interfaces de la versión 2.5 de OLE DB. Los proveedores OLE DB que requieren compatibilidad con interfaces OLE DB 2.5 no funcionará correctamente con el proveedor de datos de .NET Framework para OLE DB. Entre ellos se incluye el proveedor Microsoft OLE DB para Exchange y el proveedor Microsoft OLE DB para la publicación en Internet.  
  
 El proveedor de datos de .NET Framework para OLE DB no funciona con el proveedor OLE DB para ODBC (MSDASQL). Para obtener acceso a un origen de datos ODBC mediante ADO.NET, utilice el proveedor de datos de .NET Framework para ODBC.  
  
 Proveedor de datos de .NET framework para OLE DB clases se encuentran en el <xref:System.Data.OleDb> espacio de nombres. En el siguiente ejemplo de código se muestra cómo puede incluir el espacio de nombres `System.Data.OleDb` en sus aplicaciones.  
  
```vb  
Imports System.Data.OleDb  
```  
  
```csharp  
using System.Data.OleDb;  
```  
  
## <a name="net-framework-data-provider-for-odbc"></a>Proveedor de datos .NET Framework para ODBC  
 El proveedor de datos de .NET Framework para ODBC (Odbc) utiliza el Administrador de controladores de ODBC (Nativos) para habilitar el acceso a datos. El proveedor de datos de ODBC admite tanto transacciones locales como transacciones distribuidas. En el caso de las transacciones distribuidas, el proveedor de datos OBDC se inscribe de forma predeterminada y automática en una transacción y obtiene los detalles a través de los servicios de componentes de Windows. Para obtener más información, consulte [transacciones y simultaneidad](../../../../docs/framework/data/adonet/transactions-and-concurrency.md).  
  
 La siguiente tabla muestra los controladores ODBC que se han probado con ADO.NET.  
  
|Controlador|  
|------------|  
|SQL Server|  
|Microsoft ODBC para Oracle|  
|Microsoft Access Driver (*.mdb)|  
  
 .NET framework Data Provider para las clases ODBC se encuentran en el <xref:System.Data.Odbc> espacio de nombres.  
  
 En el siguiente ejemplo de código se muestra cómo puede incluir el espacio de nombres `System.Data.Odbc` en sus aplicaciones.  
  
```vb  
Imports System.Data.Odbc  
```  
  
```csharp  
using System.Data.Odbc;  
```  
  
> [!NOTE]
>  El proveedor de datos de .NET Framework para ODBC necesita MDAC 2.6 o una versión posterior, y se recomienda MDAC 2.8 SP1. Puede descargar MDAC 2.8 SP1 del [Centro para programadores de acceso a datos y almacenamiento](https://go.microsoft.com/fwlink/?linkid=4173).  
  
## <a name="net-framework-data-provider-for-oracle"></a>Proveedor de datos .NET Framework para Oracle  
 El proveedor de datos de .NET Framework para Oracle (OracleClient) habilita el acceso de datos a orígenes de datos de Oracle mediante el software de conectividad de cliente de Oracle. El proveedor de datos es compatible con la versión 8.1.7 o posterior del software de cliente de Oracle. El proveedor de datos admite tanto transacciones locales como transacciones distribuidas. Para obtener más información, consulte [transacciones y simultaneidad](../../../../docs/framework/data/adonet/transactions-and-concurrency.md).  
  
 El proveedor de datos de .NET Framework para Oracle requiere el software cliente de Oracle (versión 8.1.7 o posterior) en el sistema antes de poder conectarse a un origen de datos de Oracle.  
  
 .NET framework Data Provider para las clases de Oracle se encuentran en el <xref:System.Data.OracleClient> espacio de nombres y están incluidas en la `System.Data.OracleClient.dll` ensamblado. Al compilar una aplicación que utiliza el proveedor de datos, debe hacer referencia tanto a `System.Data.dll` como a `System.Data.OracleClient.dll` .  
  
 En el siguiente ejemplo de código se muestra cómo puede incluir el espacio de nombres `System.Data.OracleClient` en sus aplicaciones.  
  
```vb  
Imports System.Data  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data;  
using System.Data.OracleClient;  
```  
  
## <a name="choosing-a-net-framework-data-provider"></a>Elegir un proveedor de datos .NET Framework  
 Dependiendo del origen de datos y diseño para su aplicación, su elección del proveedor de datos de .NET Framework puede mejorar el rendimiento, capacidad y la integridad de la aplicación. En la tabla siguiente se describe las ventajas y limitaciones de cada proveedor de datos .NET Framework.  
  
|Proveedor|Notas|  
|--------------|-----------|  
|Proveedor de datos .NET Framework para SQL Server|Se recomienda para las aplicaciones de nivel medio que utilizan Microsoft SQL Server.<br /><br /> Se recomienda para las aplicaciones de nivel único que utilizan Microsoft Database Engine (MSDE) o SQL Server.<br /><br /> Se recomienda a través del uso del proveedor OLE DB para SQL Server (SQLOLEDB) con el proveedor de datos de .NET Framework para OLE DB.|  
|Proveedor de datos .NET Framework para OLE DB|Para SQL Server, se recomienda el proveedor de datos de .NET Framework para SQL Server en lugar de este proveedor.<br /><br /> Recomendado para aplicaciones de nivel único que usan bases de datos de Microsoft Access. No se recomienda el uso de bases de datos de Access para una aplicación de nivel medio.|  
|Proveedor de datos .NET Framework para ODBC|Recomendado para aplicaciones de un único nivel y de nivel medio que utilizan orígenes de datos de ODBC.|  
|Proveedor de datos .NET Framework para Oracle|Recomendado para aplicaciones de un único nivel y de nivel medio que utilizan orígenes de datos de Oracle.|  
  
## <a name="entityclient-provider"></a>Proveedor para EntityClient  
 El proveedor EntityClient se usa para obtener acceso a datos basándose en un Entity Data Model (EDM). A diferencia de otros proveedores de datos .NET Framework, no interactúa directamente con ningún origen de datos. En su lugar, usa Entity SQL para comunicarse con el proveedor de datos subyacente. Para obtener más información, consulte [proveedor de EntityClient para Entity Framework](./ef/entityclient-provider-for-the-entity-framework.md).  
  
## <a name="see-also"></a>Vea también

- [Información general sobre ADO.NET](../../../../docs/framework/data/adonet/ado-net-overview.md)
- [Recuperar y modificar datos en ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
