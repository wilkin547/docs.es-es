---
title: "Obtener un valor único de una base de datos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: b38526cd-a62a-48cb-822a-e91dfa68e02d
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 41c3547d203a9958d3ad84303469c1e9591e6bd3
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="obtaining-a-single-value-from-a-database"></a>Obtener un valor único de una base de datos
En ocasiones se debe devolver información de bases de datos consistente en un único valor, en lugar de una tabla o un flujo de datos. Por ejemplo, puede que desee devolver el resultado de una función de agregado como COUNT (\*), SUM (price) o AVG (Quantity). El **comando** objeto proporciona la capacidad de devolver valores únicos mediante el **ExecuteScalar** método. El **ExecuteScalar** método devuelve, como un valor escalar, el valor de la primera columna de la primera fila del conjunto de resultados.  
  
 El ejemplo de código siguiente inserta un valor nuevo en la base de datos utilizando <xref:System.Data.SqlClient.SqlCommand>. El método <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> se utiliza para devolver el valor de columna de identidad para el registro insertado.  
  
 [!code-csharp[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/CS/source.cs#1)]
 [!code-vb[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/VB/source.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 [Comandos y parámetros](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [Ejecución de un comando](../../../../docs/framework/data/adonet/executing-a-command.md)  
 [DbConnection, DbCommand y DbException](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
