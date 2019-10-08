---
title: Procedimiento para devolver conjuntos de filas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 725718f5-da29-4841-9f53-aafef64ba977
ms.openlocfilehash: b853a6f2175009cbcbc01c14a6732b98e37e1a7f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003062"
---
# <a name="how-to-return-rowsets"></a><span data-ttu-id="17bb8-102">Procedimiento para devolver conjuntos de filas</span><span class="sxs-lookup"><span data-stu-id="17bb8-102">How to: Return Rowsets</span></span>
<span data-ttu-id="17bb8-103">Este ejemplo devuelve un conjunto de filas de la base de datos e incluye un parámetro de entrada para filtrar el resultado.</span><span class="sxs-lookup"><span data-stu-id="17bb8-103">This example returns a rowset from the database, and includes an input parameter to filter the result.</span></span>  
  
 <span data-ttu-id="17bb8-104">Cuando se ejecuta un procedimiento almacenado que devuelve un conjunto de filas, se usa una clase de *resultado* que almacena las devoluciones del procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="17bb8-104">When you execute a stored procedure that returns a rowset, you use a *result* class that stores the returns from the stored procedure.</span></span> <span data-ttu-id="17bb8-105">Para obtener más información, vea [analizar LINQ to SQL código fuente](analyzing-linq-to-sql-source-code.md).</span><span class="sxs-lookup"><span data-stu-id="17bb8-105">For more information, see [Analyzing LINQ to SQL Source Code](analyzing-linq-to-sql-source-code.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="17bb8-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="17bb8-106">Example</span></span>  
 <span data-ttu-id="17bb8-107">El ejemplo siguiente representa un procedimiento almacenado que devuelve filas de clientes y utiliza un parámetro de entrada para devolver sólo aquellas filas en las que figura "London" como la ciudad del cliente.</span><span class="sxs-lookup"><span data-stu-id="17bb8-107">The following example represents a stored procedure that returns rows of customers and uses an input parameter to return only those rows that list "London" as the customer city.</span></span> <span data-ttu-id="17bb8-108">En el ejemplo se supone que hay una clase `CustomersByCityResult` enumerable.</span><span class="sxs-lookup"><span data-stu-id="17bb8-108">The example assumes an enumerable `CustomersByCityResult` class.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="17bb8-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="17bb8-109">See also</span></span>

- [<span data-ttu-id="17bb8-110">Procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="17bb8-110">Stored Procedures</span></span>](stored-procedures.md)
- [<span data-ttu-id="17bb8-111">Descargar bases de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="17bb8-111">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
