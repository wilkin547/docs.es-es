---
title: Proveedores de datos .NET Framework
description: Obtenga información sobre cómo se usa un proveedor de datos de .NET Framework para conectarse a una base de datos, ejecutar comandos y recuperar resultados en ADO.NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 03a9fc62-2d24-491a-9fe6-d6bdb6dcb131
ms.openlocfilehash: 2be58251c767c937e817edf1ba19309f0c62ac33
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554741"
---
# <a name="net-framework-data-providers"></a>Proveedores de datos .NET Framework
Un proveedor de datos de .NET Framework se utiliza para conectarse a una base de datos, ejecutar comandos y recuperar resultados. Esos resultados se procesan directamente, se colocan en un <xref:System.Data.DataSet> con el fin de que el usuario pueda verlos cuando los necesite, se combinan con datos de varios orígenes o se utilizan de forma remota entre niveles. .NET Framework proveedores de datos son ligeros, creando una capa mínima entre el origen de datos y el código, lo que aumenta el rendimiento sin sacrificar la funcionalidad.  
  
 En la tabla siguiente se enumeran los proveedores de datos que se incluyen en el .NET Framework.  
  
|proveedor de datos de .NET Framework (.NET Framework data provider)|Descripción|  
|-------------------------------------------------------------------------------|-----------------|  
|Proveedor de datos .NET Framework para SQL Server|Proporciona acceso de datos para Microsoft SQL Server. Utiliza el espacio de nombres <xref:System.Data.SqlClient> .|  
|Proveedor de datos .NET Framework para OLE DB|Para orígenes de datos que se exponen mediante OLE DB. Utiliza el espacio de nombres <xref:System.Data.OleDb> .|  
|Proveedor de datos .NET Framework para ODBC|Para orígenes de datos que se exponen mediante ODBC. Utiliza el espacio de nombres <xref:System.Data.Odbc> .|  
|Proveedor de datos .NET Framework para Oracle|Para orígenes de datos de Oracle. El proveedor de datos de .NET Framework para Oracle es compatible con la versión 8.1.7 y posteriores del software cliente de Oracle y utiliza el <xref:System.Data.OracleClient> espacio de nombres.|  
|Proveedor para EntityClient|Proporciona acceso a datos para las aplicaciones de Entity Data Model (EDM). Utiliza el espacio de nombres <xref:System.Data.EntityClient> .|  
|.NET Framework proveedor de datos para SQL Server Compact 4,0.|Proporciona acceso a datos para Microsoft SQL Server Compact 4,0. Usa el espacio de nombres [System.Data.SqlServerCe](/previous-versions/sql/compact/sql-server-compact-4.0/ec4st0e3(v=vs.100)) .|  
  
## <a name="core-objects-of-net-framework-data-providers"></a>Objetos principales de los proveedores de datos .NET Framework  
 En la tabla siguiente se describen los cuatro objetos principales que componen un .NET Framework proveedor de datos.  
  
|Object|Descripción|  
|------------|-----------------|  
|`Connection`|Establece una conexión a un origen de datos determinado. La clase base para todos los objetos `Connection` es <xref:System.Data.Common.DbConnection> .|  
|`Command`|Ejecuta un comando en un origen de datos. Expone `Parameters` y puede ejecutarse en el ámbito de un objeto `Transaction` desde `Connection`. La clase base para todos los objetos `Command` es <xref:System.Data.Common.DbCommand> .|  
|`DataReader`|Lee un flujo de datos de solo avance y solo lectura desde un origen de datos. La clase base para todos los objetos `DataReader` es <xref:System.Data.Common.DbDataReader> .|  
|`DataAdapter`|Llena un `DataSet` y realiza las actualizaciones necesarias en el origen de datos. La clase base para todos los objetos `DataAdapter` es <xref:System.Data.Common.DbDataAdapter> .|  
  
 Además de las clases principales enumeradas en la tabla anterior de este documento, un proveedor de datos de .NET Framework también contiene las clases que se muestran en la tabla siguiente.  
  
|Object|Descripción|  
|------------|-----------------|  
|`Transaction`|Incluye comandos en las transacciones que se realizan en el origen de datos. La clase base para todos los objetos `Transaction` es <xref:System.Data.Common.DbTransaction> . ADO.NET es también compatible con las transacciones que usan clases en el espacio de nombres <xref:System.Transactions> .|  
|`CommandBuilder`|Un objeto del asistente que genera automáticamente las propiedades de comando de un `DataAdapter` o que obtiene de un procedimiento almacenado información acerca de parámetros con la que puede rellenar la colección `Parameters` de un objeto `Command`. La clase base para todos los objetos `CommandBuilder` es <xref:System.Data.Common.DbCommandBuilder> .|  
|`ConnectionStringBuilder`|Un objeto del asistente que proporciona un modo sencillo de crear y administrar el contenido de las cadenas de conexión utilizadas por los objetos `Connection`. La clase base para todos los objetos `ConnectionStringBuilder` es <xref:System.Data.Common.DbConnectionStringBuilder> .|  
|`Parameter`|Define los parámetros de entrada, salida y valores devueltos para los comandos y procedimientos almacenados. La clase base para todos los objetos `Parameter` es <xref:System.Data.Common.DbParameter> .|  
|`Exception`|Se devuelve cuando se detecta un error en el origen de datos. En el caso de un error detectado en el cliente, .NET Framework proveedores de datos inician una excepción .NET Framework. La clase base para todos los objetos `Exception` es <xref:System.Data.Common.DbException> .|  
|`Error`|Expone la información relacionada con una advertencia o error devueltos por un origen de datos.|  
|`ClientPermission`|Se proporciona para los atributos de seguridad de acceso del código del proveedor de datos .NET Framework. La clase base para todos los objetos `ClientPermission` es <xref:System.Data.Common.DBDataPermission> .|  
  
## <a name="net-framework-data-provider-for-sql-server-sqlclient"></a>Proveedor de datos .NET Framework para SQL Server (SqlClient)  
 El proveedor de datos de .NET Framework para SQL Server (SqlClient) usa su propio protocolo para comunicarse con SQL Server. Es ligero y funciona bien porque está optimizado para tener acceso a una SQL Server directamente sin agregar una capa de conectividad de base de datos (ODBC) OLE DB o abierta. En la siguiente ilustración se compara el proveedor de datos de .NET Framework para SQL Server con el proveedor de datos de .NET Framework para OLE DB. El proveedor de datos de .NET Framework para OLE DB se comunica con un origen de datos de OLE DB a través del componente de servicio OLE DB, que proporciona agrupación de conexiones y servicios de transacción, y el proveedor de OLE DB para el origen de datos.  
  
> [!NOTE]
> El proveedor de datos .NET Framework para ODBC tiene una arquitectura similar a la del proveedor de datos .NET Framework para OLE DB; por ejemplo, llama a un componente de servicio ODBC.  
  
 ![Proveedores de datos](./media/netdataproviders-bpuedev11.gif "NETDataProviders_bpuedev11")  
Comparación del proveedor de datos .NET Framework para SQL Server y el proveedor de datos .NET Framework para OLE DB  
  
 El proveedor de datos de .NET Framework para las clases de SQL Server se encuentra en el <xref:System.Data.SqlClient> espacio de nombres.  
  
 El proveedor de datos de .NET Framework para SQL Server admite transacciones locales y distribuidas. Para las transacciones distribuidas, el proveedor de datos de .NET Framework para SQL Server, de forma predeterminada, se da de alta automáticamente en una transacción y obtiene los detalles de la transacción de los servicios de componentes de Windows o <xref:System.Transactions> . Para obtener más información, consulte [transacciones y simultaneidad](transactions-and-concurrency.md).  
  
 En el siguiente ejemplo de código se muestra cómo puede incluir el espacio de nombres `System.Data.SqlClient` en sus aplicaciones.  
  
```vb  
Imports System.Data.SqlClient  
```  
  
```csharp  
using System.Data.SqlClient;  
```  
  
## <a name="net-framework-data-provider-for-ole-db"></a>Proveedor de datos .NET Framework para OLE DB  
 El proveedor de datos de .NET Framework para OLE DB (OleDb) utiliza OLE DB nativa a través de la interoperabilidad COM para habilitar el acceso a los datos. El proveedor de datos de .NET Framework para OLE DB admite transacciones locales y distribuidas. Para las transacciones distribuidas, el proveedor de datos de .NET Framework para OLE DB, de forma predeterminada, se da de alta automáticamente en una transacción y obtiene los detalles de la transacción de los servicios de componentes de Windows. Para obtener más información, consulte [transacciones y simultaneidad](transactions-and-concurrency.md).  
  
 En la tabla siguiente se muestran los proveedores probados con ADO.NET.  
  
|Controlador|Proveedor|  
|------------|--------------|  
|SQLOLEDB|Proveedor de OLE DB de Microsoft para SQL Server|  
|MSDAORA|Proveedor Microsoft OLE DB para Oracle|  
|Microsoft.Jet.OLEDB.4.0|Proveedor OLE DB para Microsoft Jet|  
  
> [!NOTE]
> No se recomienda utilizar una base de datos de Access (jet) como origen de datos para las aplicaciones multiproceso, como las aplicaciones ASP.NET. Si debe usar jet como origen de datos para una aplicación de ASP.NET, tenga en cuentan que las aplicaciones de ASP.NET que se conectan a una base de datos de Access pueden encontrar problemas de conexión.  
  
 El proveedor de datos de .NET Framework para OLE DB no es compatible con las interfaces OLE DB versión 2,5. OLE DB proveedores que requieran compatibilidad con las interfaces de OLE DB 2,5 no funcionarán correctamente con el proveedor de datos de .NET Framework para OLE DB. Entre ellos se incluye el proveedor Microsoft OLE DB para Exchange y el proveedor Microsoft OLE DB para la publicación en Internet.  
  
 El proveedor de datos de .NET Framework para OLE DB no funciona con el proveedor de OLE DB para ODBC (MSDASQL). Para obtener acceso a un origen de datos ODBC mediante ADO.NET, use el proveedor de datos de .NET Framework para ODBC.  
  
 .NET Framework proveedor de datos para OLE DB clases se encuentran en el <xref:System.Data.OleDb> espacio de nombres. En el siguiente ejemplo de código se muestra cómo puede incluir el espacio de nombres `System.Data.OleDb` en sus aplicaciones.  
  
```vb  
Imports System.Data.OleDb  
```  
  
```csharp  
using System.Data.OleDb;  
```  
  
## <a name="net-framework-data-provider-for-odbc"></a>Proveedor de datos .NET Framework para ODBC  
 El proveedor de datos de .NET Framework para ODBC (ODBC) utiliza el administrador de controladores ODBC (DM) nativo para habilitar el acceso a los datos. El proveedor de datos de ODBC admite tanto transacciones locales como transacciones distribuidas. En el caso de las transacciones distribuidas, el proveedor de datos OBDC se inscribe de forma predeterminada y automática en una transacción y obtiene los detalles a través de los servicios de componentes de Windows. Para obtener más información, consulte [transacciones y simultaneidad](transactions-and-concurrency.md).  
  
 En la tabla siguiente se muestran los controladores ODBC probados con ADO.NET.  
  
|Controlador|  
|------------|  
|SQL Server|  
|Microsoft ODBC para Oracle|  
|Microsoft Access Driver (*.mdb)|  
  
 .NET Framework proveedor de datos para las clases ODBC se encuentran en el <xref:System.Data.Odbc> espacio de nombres.  
  
 En el siguiente ejemplo de código se muestra cómo puede incluir el espacio de nombres `System.Data.Odbc` en sus aplicaciones.  
  
```vb  
Imports System.Data.Odbc  
```  
  
```csharp  
using System.Data.Odbc;  
```  
  
> [!NOTE]
> El proveedor de datos de .NET Framework para ODBC requiere MDAC 2,6 o una versión posterior, y se recomienda MDAC 2,8 SP1. Puede descargar MDAC 2,8 SP1 desde el [centro de descarga de Microsoft](https://www.microsoft.com/download/details.aspx?id=5793).
  
## <a name="net-framework-data-provider-for-oracle"></a>Proveedor de datos .NET Framework para Oracle  
 El proveedor de datos de .NET Framework para Oracle (OracleClient) permite el acceso a los datos de los orígenes de datos de Oracle a través del software de conectividad de cliente de Oracle. El proveedor de datos es compatible con la versión 8.1.7 o posterior del software de cliente de Oracle. El proveedor de datos admite tanto transacciones locales como transacciones distribuidas. Para obtener más información, consulte [transacciones y simultaneidad](transactions-and-concurrency.md).  
  
 El proveedor de datos de .NET Framework para Oracle requiere el software de cliente de Oracle (versión 8.1.7 o una versión posterior) en el sistema para poder conectarse a un origen de datos de Oracle.  
  
 .NET Framework proveedor de datos para las clases de Oracle se encuentran en el <xref:System.Data.OracleClient> espacio de nombres y se incluyen en el `System.Data.OracleClient.dll` ensamblado. Al compilar una aplicación que utiliza el proveedor de datos, debe hacer referencia tanto a `System.Data.dll` como a `System.Data.OracleClient.dll` .  
  
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
 En función del diseño y del origen de datos de la aplicación, la elección de .NET Framework proveedor de datos puede mejorar el rendimiento, la capacidad y la integridad de la aplicación. En la tabla siguiente se describen las ventajas y las limitaciones de cada proveedor de datos de .NET Framework.  
  
|Proveedor|Notas|  
|--------------|-----------|  
|Proveedor de datos .NET Framework para SQL Server|Se recomienda para las aplicaciones de nivel intermedio que usan Microsoft SQL Server.<br /><br /> Se recomienda para las aplicaciones de un solo nivel que usan Microsoft Motor de base de datos (MSDE) o SQL Server.<br /><br /> Se recomienda usar el proveedor de OLE DB para SQL Server (SQLOLEDB) con el proveedor de datos de .NET Framework para OLE DB.|  
|Proveedor de datos .NET Framework para OLE DB|Por SQL Server, se recomienda el proveedor de datos .NET Framework para SQL Server en lugar de este proveedor.<br /><br /> Recomendado para aplicaciones de nivel único que usan bases de datos de Microsoft Access. No se recomienda el uso de bases de datos de Access para una aplicación de nivel medio.|  
|Proveedor de datos .NET Framework para ODBC|Recomendado para aplicaciones de un único nivel y de nivel medio que utilizan orígenes de datos de ODBC.|  
|Proveedor de datos .NET Framework para Oracle|Recomendado para aplicaciones de un único nivel y de nivel medio que utilizan orígenes de datos de Oracle.|  
  
## <a name="entityclient-provider"></a>Proveedor para EntityClient  
 El proveedor EntityClient se usa para obtener acceso a datos basándose en un Entity Data Model (EDM). A diferencia de otros proveedores de datos .NET Framework, no interactúa directamente con ningún origen de datos. En su lugar, usa Entity SQL para comunicarse con el proveedor de datos subyacente. Para obtener más información, consulte [Proveedor de EntityClient para Entity Framework](./ef/entityclient-provider-for-the-entity-framework.md).  
  
## <a name="see-also"></a>Vea también

- [Información general de ADO.NET](ado-net-overview.md)
- [Recuperar y modificar datos en ADO.NET](retrieving-and-modifying-data.md)
