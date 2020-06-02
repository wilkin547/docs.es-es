---
title: Conectar con un origen de datos
deescription: Learn about Connection objects, used to connect to data sources in ADO.NET. The Connection object you choose depends on the type of data source.
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: a14fe179cf2fc8714a54e52252c53bd71346cad3
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287082"
---
# <a name="connecting-to-a-data-source-in-adonet"></a>Conectarse a un origen de datos en ADO.NET

En ADO.NET, se usa un objeto de **conexión** para conectarse a un origen de datos específico proporcionando la información de autenticación necesaria en una cadena de conexión. El objeto de **conexión** que se utiliza depende del tipo de origen de datos.  
  
 Cada proveedor de datos .NET Framework incluye un objeto <xref:System.Data.Common.DbConnection>: el proveedor de datos .NET Framework para OLE DB incluye un objeto <xref:System.Data.OleDb.OleDbConnection>, el proveedor de datos .NET Framework para SQL Server incluye un objeto <xref:System.Data.SqlClient.SqlConnection>, el proveedor de datos .NET Framework para ODBC incluye un objeto <xref:System.Data.Odbc.OdbcConnection> y el proveedor de datos .NET Framework para Oracle incluye un objeto <xref:System.Data.OracleClient.OracleConnection>.  
  
## <a name="in-this-section"></a>En esta sección  
 [Establecimiento de la conexión](establishing-the-connection.md)\
 Describe cómo utilizar un objeto de **conexión** para establecer una conexión a un origen de datos.  
  
 [Eventos de conexión](connection-events.md)\
 Describe cómo usar un evento **InfoMessage** para recuperar mensajes informativos de un origen de datos.  
  
## <a name="see-also"></a>Consulte también

- [Cadenas de conexión](connection-strings.md)
- [Agrupar conexiones](connection-pooling.md)
- [Comandos y parámetros](commands-and-parameters.md)
- [Objetos DataAdapter y DataReader](dataadapters-and-datareaders.md)
- [Transacciones y simultaneidad](transactions-and-concurrency.md)
- [Información general de ADO.NET](ado-net-overview.md)
