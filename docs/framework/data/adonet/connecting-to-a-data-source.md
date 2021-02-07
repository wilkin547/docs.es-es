---
description: Más información acerca de cómo conectarse a un origen de datos en ADO.NET
title: Conectar con un origen de datos
deescription: Learn about Connection objects, used to connect to data sources in ADO.NET. The Connection object you choose depends on the type of data source.
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: 0bf66b9dc609a704cf89380e2376f50197e047a7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99663890"
---
# <a name="connecting-to-a-data-source-in-adonet"></a>Conectarse a un origen de datos en ADO.NET

En ADO.NET, se usa un objeto de **conexión** para conectarse a un origen de datos específico proporcionando la información de autenticación necesaria en una cadena de conexión. El objeto **Connection** utilizado depende del tipo de origen de datos.  
  
 Cada proveedor de datos .NET Framework incluye un objeto <xref:System.Data.Common.DbConnection>: el proveedor de datos .NET Framework para OLE DB incluye un objeto <xref:System.Data.OleDb.OleDbConnection>, el proveedor de datos .NET Framework para SQL Server incluye un objeto <xref:System.Data.SqlClient.SqlConnection>, el proveedor de datos .NET Framework para ODBC incluye un objeto <xref:System.Data.Odbc.OdbcConnection> y el proveedor de datos .NET Framework para Oracle incluye un objeto <xref:System.Data.OracleClient.OracleConnection>.  
  
## <a name="in-this-section"></a>En esta sección  

 [Establecimiento de la conexión](establishing-the-connection.md)\
 Describe cómo se establece una conexión con un origen de datos mediante un objeto **Connection**.  
  
 [Eventos de conexión](connection-events.md)\
 Describe la forma de usar un evento **InfoMessage** para recuperar mensajes informativos de un origen de datos.  
  
## <a name="see-also"></a>Vea también

- [Cadenas de conexión](connection-strings.md)
- [Agrupar conexiones](connection-pooling.md)
- [Comandos y parámetros](commands-and-parameters.md)
- [Objetos DataAdapter y DataReader](dataadapters-and-datareaders.md)
- [Transacciones y simultaneidad](transactions-and-concurrency.md)
- [Información general de ADO.NET](ado-net-overview.md)
