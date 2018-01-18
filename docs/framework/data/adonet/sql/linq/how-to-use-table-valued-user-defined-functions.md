---
title: "Cómo: Usar funciones con valores de tabla definidas por el usuario"
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
ms.assetid: 5a4ae2b4-3290-4aa1-bc95-fc70c51b54cf
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c8ec97e0d083ccdd17a97db571d58aae9afbeea8
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-use-table-valued-user-defined-functions"></a>Cómo: Usar funciones con valores de tabla definidas por el usuario
Una función con valores de tabla devuelve un conjunto de filas único (a diferencia de los procedimientos almacenados, que pueden devolver varias formas de resultados). Dado que el tipo devuelto de una función con valores de tabla es `Table`, una función con valores de tabla se puede usar en cualquier lugar de SQL donde se pueda usar una tabla. La función con valores de tabla se puede tratar como se trataría una tabla.  
  
## <a name="example"></a>Ejemplo  
 La función de SQL siguiente declara explícitamente que devuelve `TABLE`. Por lo tanto, la estructura de conjunto de filas devuelta se define implícitamente.  
  
```  
CREATE FUNCTION ProductsCostingMoreThan(@cost money)  
RETURNS TABLE  
AS  
RETURN  
    SELECT ProductID, UnitPrice  
    FROM Products  
    WHERE UnitPrice > @cost  
```  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] asigna la función de la manera siguiente:  
  
 [!code-csharp[DLinqUDFS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/northwind-tfunc.cs#1)]
 [!code-vb[DLinqUDFS#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/northwind-tfunc.vb#1)]  
  
## <a name="example"></a>Ejemplo  
 El código de SQL siguiente muestra cómo se puede unir a la tabla devuelta por la función y, si no, tratarla como lo haría con cualquier otra tabla:  
  
```  
SELECT p2.ProductName, p1.UnitPrice  
FROM dbo.ProductsCostingMoreThan(80.50)  
AS p1 INNER JOIN Products AS p2 ON p1.ProductID = p2.ProductID  
```  
  
 En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], la consulta se presentaría de la siguiente manera:  
  
 [!code-csharp[DLinqUDFS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#2)]
 [!code-vb[DLinqUDFS#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#2)]  
  
## <a name="see-also"></a>Vea también  
 [Funciones definidas por el usuario](../../../../../../docs/framework/data/adonet/sql/linq/user-defined-functions.md)
