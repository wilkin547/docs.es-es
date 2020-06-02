---
title: Procedimiento para usar funciones definidas por el usuario con valores de tabla
description: Use estos ejemplos para obtener información sobre cómo crear una función con valores de tabla, que devuelve un conjunto de filas único. Use esta función con valores de tabla como una tabla.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5a4ae2b4-3290-4aa1-bc95-fc70c51b54cf
ms.openlocfilehash: 44866367393e321d7dd2db965e2fad8a2e6b63e9
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286331"
---
# <a name="how-to-use-table-valued-user-defined-functions"></a><span data-ttu-id="5871b-104">Procedimiento para usar funciones definidas por el usuario con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="5871b-104">How to: Use Table-Valued User-Defined Functions</span></span>
<span data-ttu-id="5871b-105">Una función con valores de tabla devuelve un conjunto de filas único (a diferencia de los procedimientos almacenados, que pueden devolver varias formas de resultados).</span><span class="sxs-lookup"><span data-stu-id="5871b-105">A table-valued function returns a single rowset (unlike stored procedures, which can return multiple result shapes).</span></span> <span data-ttu-id="5871b-106">Dado que el tipo devuelto de una función con valores de tabla es `Table`, una función con valores de tabla se puede usar en cualquier lugar de SQL donde se pueda usar una tabla.</span><span class="sxs-lookup"><span data-stu-id="5871b-106">Because the return type of a table-valued function is `Table`, you can use a table-valued function anywhere in SQL that you can use a table.</span></span> <span data-ttu-id="5871b-107">La función con valores de tabla se puede tratar como se trataría una tabla.</span><span class="sxs-lookup"><span data-stu-id="5871b-107">You can also treat the table-valued function just as you would a table.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5871b-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5871b-108">Example</span></span>  
 <span data-ttu-id="5871b-109">La función de SQL siguiente declara explícitamente que devuelve `TABLE`.</span><span class="sxs-lookup"><span data-stu-id="5871b-109">The following SQL function explicitly states that it returns a `TABLE`.</span></span> <span data-ttu-id="5871b-110">Por lo tanto, la estructura de conjunto de filas devuelta se define implícitamente.</span><span class="sxs-lookup"><span data-stu-id="5871b-110">Therefore, the returned rowset structure is implicitly defined.</span></span>  
  
```sql
CREATE FUNCTION ProductsCostingMoreThan(@cost money)  
RETURNS TABLE  
AS  
RETURN  
    SELECT ProductID, UnitPrice  
    FROM Products  
    WHERE UnitPrice > @cost  
```  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="5871b-111">asigna la función de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="5871b-111">maps the function as follows:</span></span>  
  
 [!code-csharp[DLinqUDFS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/northwind-tfunc.cs#1)]
 [!code-vb[DLinqUDFS#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/northwind-tfunc.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="5871b-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5871b-112">Example</span></span>  
 <span data-ttu-id="5871b-113">El código de SQL siguiente muestra cómo se puede unir a la tabla devuelta por la función y, si no, tratarla como lo haría con cualquier otra tabla:</span><span class="sxs-lookup"><span data-stu-id="5871b-113">The following SQL code shows that you can join to the table that the function returns and otherwise treat it as you would any other table:</span></span>  
  
```sql
SELECT p2.ProductName, p1.UnitPrice  
FROM dbo.ProductsCostingMoreThan(80.50)  
AS p1 INNER JOIN Products AS p2 ON p1.ProductID = p2.ProductID  
```  
  
 <span data-ttu-id="5871b-114">En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], la consulta se presentaría de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="5871b-114">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the query would be rendered as follows:</span></span>  
  
 [!code-csharp[DLinqUDFS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#2)]
 [!code-vb[DLinqUDFS#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="5871b-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5871b-115">See also</span></span>

- [<span data-ttu-id="5871b-116">Funciones definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="5871b-116">User-Defined Functions</span></span>](user-defined-functions.md)
