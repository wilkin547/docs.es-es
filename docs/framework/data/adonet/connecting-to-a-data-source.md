---
title: "Conectarse a un origen de datos en ADO.NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Conectarse a un origen de datos en ADO.NET
En ADO.NET se utiliza un objeto **Connection** para conectar con un determinado origen de datos mediante una cadena de conexión en la que se proporciona la información de autenticación necesaria.  El objeto **Connection** utilizado depende del tipo de origen de datos.  
  
 Cada proveedor de datos .NET Framework incluye un objeto <xref:System.Data.Common.DbConnection>: el proveedor de datos .NET Framework para OLE DB incluye un objeto <xref:System.Data.OleDb.OleDbConnection>, el proveedor de datos .NET Framework para SQL Server incluye un objeto <xref:System.Data.SqlClient.SqlConnection>, el proveedor de datos .NET Framework para ODBC incluye un objeto <xref:System.Data.Odbc.OdbcConnection> y el proveedor de datos .NET Framework para Oracle incluye un objeto <xref:System.Data.OracleClient.OracleConnection>.  
  
## En esta sección  
 [Establecer la conexión](../../../../docs/framework/data/adonet/establishing-the-connection.md)  
 Describe cómo se establece una conexión con un origen de datos mediante un objeto **Connection**.  
  
 [Eventos de conexión](../../../../docs/framework/data/adonet/connection-events.md)  
 Describe la forma de usar un evento **InfoMessage** para recuperar mensajes informativos de un origen de datos.  
  
## Vea también  
 [Cadenas de conexión](../../../../docs/framework/data/adonet/connection-strings.md)   
 [Agrupar conexiones](../../../../docs/framework/data/adonet/connection-pooling.md)   
 [Comandos y parámetros](../../../../docs/framework/data/adonet/commands-and-parameters.md)   
 [DataAdapters y DataReaders](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)   
 [Transacciones y simultaneidad](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)