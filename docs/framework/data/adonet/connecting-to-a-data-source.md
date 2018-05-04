---
title: Conectarse a un origen de datos en ADO.NET
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: 27653c3e1f14e08fc8b5e1225a441072778a0cc8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="connecting-to-a-data-source-in-adonet"></a>Conectarse a un origen de datos en ADO.NET
En ADO.NET se utiliza un **conexión** objeto para conectarse a un origen de datos específico mediante el suministro de información de autenticación necesaria en una cadena de conexión. El **conexión** objeto utilizado depende del tipo de origen de datos.  
  
 Cada proveedor de datos .NET Framework incluye un objeto <xref:System.Data.Common.DbConnection>: el proveedor de datos .NET Framework para OLE DB incluye un objeto <xref:System.Data.OleDb.OleDbConnection>, el proveedor de datos .NET Framework para SQL Server incluye un objeto <xref:System.Data.SqlClient.SqlConnection>, el proveedor de datos .NET Framework para ODBC incluye un objeto <xref:System.Data.Odbc.OdbcConnection> y el proveedor de datos .NET Framework para Oracle incluye un objeto <xref:System.Data.OracleClient.OracleConnection>.  
  
## <a name="in-this-section"></a>En esta sección  
 [Establecimiento de la conexión](../../../../docs/framework/data/adonet/establishing-the-connection.md)  
 Describe cómo usar un **conexión** objeto que se va a establecer una conexión con un origen de datos.  
  
 [Eventos de conexión](../../../../docs/framework/data/adonet/connection-events.md)  
 Describe cómo usar un **InfoMessage** eventos para recuperar mensajes informativos de un origen de datos.  
  
## <a name="see-also"></a>Vea también  
 [Cadenas de conexión](../../../../docs/framework/data/adonet/connection-strings.md)  
 [Agrupación de conexiones](../../../../docs/framework/data/adonet/connection-pooling.md)  
 [Comandos y parámetros](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [Objetos DataAdapter y DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [Transacciones y simultaneidad](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
