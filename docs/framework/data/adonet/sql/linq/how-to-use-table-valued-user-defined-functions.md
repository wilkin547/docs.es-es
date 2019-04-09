---
title: Filtrar para usar funciones definidas por el usuario con valores de tabla
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5a4ae2b4-3290-4aa1-bc95-fc70c51b54cf
ms.openlocfilehash: eedc2e9b997e91ed9fe0038f260aa475d23a0627
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186841"
---
# <a name="how-to-use-table-valued-user-defined-functions"></a><span data-ttu-id="db114-102">Filtrar para usar funciones definidas por el usuario con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="db114-102">How to: Use Table-Valued User-Defined Functions</span></span>
<span data-ttu-id="db114-103">Una función con valores de tabla devuelve un conjunto de filas único (a diferencia de los procedimientos almacenados, que pueden devolver varias formas de resultados).</span><span class="sxs-lookup"><span data-stu-id="db114-103">A table-valued function returns a single rowset (unlike stored procedures, which can return multiple result shapes).</span></span> <span data-ttu-id="db114-104">Dado que el tipo devuelto de una función con valores de tabla es `Table`, una función con valores de tabla se puede usar en cualquier lugar de SQL donde se pueda usar una tabla.</span><span class="sxs-lookup"><span data-stu-id="db114-104">Because the return type of a table-valued function is `Table`, you can use a table-valued function anywhere in SQL that you can use a table.</span></span> <span data-ttu-id="db114-105">La función con valores de tabla se puede tratar como se trataría una tabla.</span><span class="sxs-lookup"><span data-stu-id="db114-105">You can also treat the table-valued function just as you would a table.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db114-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="db114-106">Example</span></span>  
 <span data-ttu-id="db114-107">La función de SQL siguiente declara explícitamente que devuelve `TABLE`.</span><span class="sxs-lookup"><span data-stu-id="db114-107">The following SQL function explicitly states that it returns a `TABLE`.</span></span> <span data-ttu-id="db114-108">Por lo tanto, la estructura de conjunto de filas devuelta se define implícitamente.</span><span class="sxs-lookup"><span data-stu-id="db114-108">Therefore, the returned rowset structure is implicitly defined.</span></span>  
  
```  
CREATE FUNCTION ProductsCostingMoreThan(@cost money)  
RETURNS TABLE  
AS  
RETURN  
    SELECT ProductID, UnitPrice  
    FROM Products  
    WHERE UnitPrice > @cost  
```  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="db114-109">asigna la función como sigue:</span><span class="sxs-lookup"><span data-stu-id="db114-109">maps the function as follows:</span></span>  
  
 [!code-csharp[DLinqUDFS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/northwind-tfunc.cs#1)]
 [!code-vb[DLinqUDFS#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/northwind-tfunc.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="db114-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="db114-110">Example</span></span>  
 <span data-ttu-id="db114-111">El código de SQL siguiente muestra cómo se puede unir a la tabla devuelta por la función y, si no, tratarla como lo haría con cualquier otra tabla:</span><span class="sxs-lookup"><span data-stu-id="db114-111">The following SQL code shows that you can join to the table that the function returns and otherwise treat it as you would any other table:</span></span>  
  
```  
SELECT p2.ProductName, p1.UnitPrice  
FROM dbo.ProductsCostingMoreThan(80.50)  
AS p1 INNER JOIN Products AS p2 ON p1.ProductID = p2.ProductID  
```  
  
 <span data-ttu-id="db114-112">En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], la consulta se presentaría de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="db114-112">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the query would be rendered as follows:</span></span>  
  
 [!code-csharp[DLinqUDFS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#2)]
 [!code-vb[DLinqUDFS#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="db114-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="db114-113">See also</span></span>

- [<span data-ttu-id="db114-114">Funciones definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="db114-114">User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/user-defined-functions.md)
