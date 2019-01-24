---
title: Procedimiento Devolver conjuntos de filas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 725718f5-da29-4841-9f53-aafef64ba977
ms.openlocfilehash: b9fcbd8aa74740a66fa6caca18067ac473891f4e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587221"
---
# <a name="how-to-return-rowsets"></a>Procedimiento Devolver conjuntos de filas
Este ejemplo devuelve un conjunto de filas de la base de datos e incluye un parámetro de entrada para filtrar el resultado.  
  
 Cuando se ejecuta un procedimiento almacenado que devuelve un conjunto de filas, usa un *resultado* clase que almacena la devuelve desde el procedimiento almacenado. Para obtener más información, consulte [analizar código LINQ to SQL origen](../../../../../../docs/framework/data/adonet/sql/linq/analyzing-linq-to-sql-source-code.md).  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente representa un procedimiento almacenado que devuelve filas de clientes y utiliza un parámetro de entrada para devolver sólo aquellas filas en las que figura "London" como la ciudad del cliente. En el ejemplo se supone que hay una clase `CustomersByCityResult` enumerable.  
  
```  
CREATE PROCEDURE [dbo].[Customers By City]  
    (@param1 NVARCHAR(20))  
AS  
BEGIN  
    -- SET NOCOUNT ON added to prevent extra result sets from  
    -- interfering with SELECT statements.  
    SET NOCOUNT ON;  
    SELECT CustomerID, ContactName, CompanyName, City from Customers  
        as c where c.City=@param1  
END  
```  
  
 [!code-csharp[DLinqSprox#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#1)]
 [!code-vb[DLinqSprox#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#1)]  
  
## <a name="see-also"></a>Vea también
- [Procedimientos almacenados](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
- [Descargar bases de datos de ejemplo](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
