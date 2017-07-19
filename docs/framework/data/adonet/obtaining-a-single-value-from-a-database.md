---
title: "Obtener un &#250;nico valor de una base de datos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b38526cd-a62a-48cb-822a-e91dfa68e02d
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Obtener un &#250;nico valor de una base de datos
En ocasiones se debe devolver información de bases de datos consistente en un único valor, en lugar de una tabla o un flujo de datos.  Por ejemplo, puede que desee devolver el resultado de una función de agregado como COUNT\(\*\), SUM\(Price\) o AVG\(Quantity\).  El objeto **Command** permite devolver valores únicos mediante el método **ExecuteScalar**.  El método **ExecuteScalar** devuelve como valor escalar el valor correspondiente a la primera columna de la primera fila del conjunto de resultados.  
  
 El ejemplo de código siguiente inserta un valor nuevo en la base de datos utilizando <xref:System.Data.SqlClient.SqlCommand>.  El método <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> se utiliza para devolver el valor de columna de identidad para el registro insertado.  
  
 [!code-csharp[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/CS/source.cs#1)]
 [!code-vb[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/VB/source.vb#1)]  
  
## Vea también  
 [Comandos y parámetros](../../../../docs/framework/data/adonet/commands-and-parameters.md)   
 [Ejecutar un comando](../../../../docs/framework/data/adonet/executing-a-command.md)   
 [DbConnection, DbCommand y DbException](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)