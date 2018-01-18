---
title: "Cómo: Llamar a funciones alineadas definidas por el usuario"
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
ms.assetid: f80d4327-b6a5-4aa8-a743-e95d09a2a02e
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: f84d6c2c75844ab265259339ed8f72e42419f63a
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-call-user-defined-functions-inline"></a>Cómo: Llamar a funciones alineadas definidas por el usuario
Aunque se puede llamar a funciones alineadas definidas por el usuario, las funciones que se incluyen en una consulta cuya ejecución está diferida no se ejecutan hasta que se ejecute la consulta. Para obtener más información, vea [Introduction to LINQ queries (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md) [Introducción a las consultas LINQ (C#)].  
  
 Al llamar a la misma función fuera de una consulta, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] crea una consulta simple a partir de la expresión de llamada al método. A continuación se muestra la sintaxis de SQL (el parámetro `@p0` se enlaza a la constante pasada):  
  
```  
SELECT dbo.ReverseCustName(@p0)  
```  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] crea lo siguiente:  
  
 [!code-csharp[DLinqUDFS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#4)]
 [!code-vb[DLinqUDFS#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#4)]  
  
## <a name="example"></a>Ejemplo  
 En la siguiente [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] consulta, se puede ver una llamada alineada al método generado de función definida por el usuario `ReverseCustName`. La función no se ejecuta inmediatamente, porque la ejecución de la consulta está diferida. El código SQL compilado para esta consulta realiza la conversión a una llamada a la función definida por el usuario en la base de datos (vea el código SQL que se encuentra después de la consulta).  
  
 [!code-csharp[DLinqUDFS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#5)]
 [!code-vb[DLinqUDFS#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#5)]  
  
```  
SELECT [t0].[ContactName],  
    dbo.ReverseCustName([t0].[ContactTitle]) AS [Title]  
FROM [Customers] AS [t0]  
```  
  
## <a name="see-also"></a>Vea también  
 [Funciones definidas por el usuario](../../../../../../docs/framework/data/adonet/sql/linq/user-defined-functions.md)
