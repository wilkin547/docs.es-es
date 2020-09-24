---
title: Procedimiento para devolver conjuntos de filas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 725718f5-da29-4841-9f53-aafef64ba977
ms.openlocfilehash: be03107db73ed230a87c2518e7825461afc2bc7b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155749"
---
# <a name="how-to-return-rowsets"></a>Procedimiento para devolver conjuntos de filas

Este ejemplo devuelve un conjunto de filas de la base de datos e incluye un parámetro de entrada para filtrar el resultado.  
  
 Cuando se ejecuta un procedimiento almacenado que devuelve un conjunto de filas, se usa una clase de *resultado* que almacena las devoluciones del procedimiento almacenado. Para obtener más información, vea [analizar LINQ to SQL código fuente](analyzing-linq-to-sql-source-code.md).  
  
## <a name="example"></a>Ejemplo  

 El ejemplo siguiente representa un procedimiento almacenado que devuelve filas de clientes y utiliza un parámetro de entrada para devolver sólo aquellas filas en las que figura "London" como la ciudad del cliente. En el ejemplo se supone que hay una clase `CustomersByCityResult` enumerable.  
  
```sql  
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

- [Procedimientos almacenados](stored-procedures.md)
- [Descargar bases de datos de ejemplo](downloading-sample-databases.md)
