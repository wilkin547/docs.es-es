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
# <a name="how-to-return-rowsets"></a><span data-ttu-id="43872-102">Procedimiento para devolver conjuntos de filas</span><span class="sxs-lookup"><span data-stu-id="43872-102">How to: Return Rowsets</span></span>

<span data-ttu-id="43872-103">Este ejemplo devuelve un conjunto de filas de la base de datos e incluye un parámetro de entrada para filtrar el resultado.</span><span class="sxs-lookup"><span data-stu-id="43872-103">This example returns a rowset from the database, and includes an input parameter to filter the result.</span></span>  
  
 <span data-ttu-id="43872-104">Cuando se ejecuta un procedimiento almacenado que devuelve un conjunto de filas, se usa una clase de *resultado* que almacena las devoluciones del procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="43872-104">When you execute a stored procedure that returns a rowset, you use a *result* class that stores the returns from the stored procedure.</span></span> <span data-ttu-id="43872-105">Para obtener más información, vea [analizar LINQ to SQL código fuente](analyzing-linq-to-sql-source-code.md).</span><span class="sxs-lookup"><span data-stu-id="43872-105">For more information, see [Analyzing LINQ to SQL Source Code](analyzing-linq-to-sql-source-code.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="43872-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="43872-106">Example</span></span>  

 <span data-ttu-id="43872-107">El ejemplo siguiente representa un procedimiento almacenado que devuelve filas de clientes y utiliza un parámetro de entrada para devolver sólo aquellas filas en las que figura "London" como la ciudad del cliente.</span><span class="sxs-lookup"><span data-stu-id="43872-107">The following example represents a stored procedure that returns rows of customers and uses an input parameter to return only those rows that list "London" as the customer city.</span></span> <span data-ttu-id="43872-108">En el ejemplo se supone que hay una clase `CustomersByCityResult` enumerable.</span><span class="sxs-lookup"><span data-stu-id="43872-108">The example assumes an enumerable `CustomersByCityResult` class.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="43872-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="43872-109">See also</span></span>

- [<span data-ttu-id="43872-110">Procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="43872-110">Stored Procedures</span></span>](stored-procedures.md)
- [<span data-ttu-id="43872-111">Descargar bases de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="43872-111">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
