---
title: Conectarse a un origen de datos en ADO.NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0d21c571b659e9d7aef65893db18b034d614e2af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="connecting-to-a-data-source-in-adonet"></a>Conectarse a un origen de datos en ADO.NET
En ADO.NET se utiliza un **conexión** objeto para conectarse a un origen de datos específico mediante el suministro de información de autenticación necesaria en una cadena de conexión. El **conexión** objeto utilizado depende del tipo de origen de datos.  
  
 Cada proveedor de datos .NET Framework incluye un objeto <xref:System.Data.Common.DbConnection>: el proveedor de datos .NET Framework para OLE DB incluye un objeto <xref:System.Data.OleDb.OleDbConnection>, el proveedor de datos .NET Framework para SQL Server incluye un objeto <xref:System.Data.SqlClient.SqlConnection>, el proveedor de datos .NET Framework para ODBC incluye un objeto <xref:System.Data.Odbc.OdbcConnection> y el proveedor de datos .NET Framework para Oracle incluye un objeto <xref:System.Data.OracleClient.OracleConnection>.  
  
## <a name="in-this-section"></a>En esta sección  
 [Establecer la conexión](../../../../docs/framework/data/adonet/establishing-the-connection.md)  
 Describe cómo usar un **conexión** objeto que se va a establecer una conexión con un origen de datos.  
  
 [Eventos de conexión](../../../../docs/framework/data/adonet/connection-events.md)  
 Describe cómo usar un **InfoMessage** eventos para recuperar mensajes informativos de un origen de datos.  
  
## <a name="see-also"></a>Vea también  
 [Cadenas de conexión](../../../../docs/framework/data/adonet/connection-strings.md)  
 [Agrupación de conexiones](../../../../docs/framework/data/adonet/connection-pooling.md)  
 [Comandos y parámetros](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [Objetos DataAdapter y DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [Las transacciones y simultaneidad](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
