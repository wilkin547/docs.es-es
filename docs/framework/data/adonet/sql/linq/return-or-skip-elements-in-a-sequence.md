---
title: Devolver u omitir elementos de una secuencia
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 81a31acd-e0f1-4bca-9a12-fa1ad5752374
ms.openlocfilehash: 228de9f3b92d45866c98976be08b84988a2db8d7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33359883"
---
# <a name="return-or-skip-elements-in-a-sequence"></a><span data-ttu-id="94e69-102">Devolver u omitir elementos de una secuencia</span><span class="sxs-lookup"><span data-stu-id="94e69-102">Return Or Skip Elements in a Sequence</span></span>
<span data-ttu-id="94e69-103">Utilice el operador <xref:System.Linq.Queryable.Take%2A> para devolver un número determinado de elementos de una secuencia y omitir el resto.</span><span class="sxs-lookup"><span data-stu-id="94e69-103">Use the <xref:System.Linq.Queryable.Take%2A> operator to return a given number of elements in a sequence and then skip over the remainder.</span></span>  
  
 <span data-ttu-id="94e69-104">Utilice el operador <xref:System.Linq.Queryable.Skip%2A> para omitir un número determinado de elementos de una secuencia y devolver el resto.</span><span class="sxs-lookup"><span data-stu-id="94e69-104">Use the <xref:System.Linq.Queryable.Skip%2A> operator to skip over a given number of elements in a sequence and then return the remainder.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="94e69-105"><xref:System.Linq.Enumerable.Take%2A> y <xref:System.Linq.Enumerable.Skip%2A> tienen ciertas limitaciones cuando se utilizan en consultas en SQL Server 2000.</span><span class="sxs-lookup"><span data-stu-id="94e69-105"><xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> have certain limitations when they are used in queries against SQL Server 2000.</span></span> <span data-ttu-id="94e69-106">Para obtener más información, consulte la entrada "Skip y Take excepciones en SQL Server 2000" en [solución de problemas](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="94e69-106">For more information, see the "Skip and Take Exceptions in SQL Server 2000" entry in [Troubleshooting](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="94e69-107"> traduce <xref:System.Linq.Queryable.Skip%2A> utilizando una subconsulta con SQL `NOT EXISTS` cláusula.</span><span class="sxs-lookup"><span data-stu-id="94e69-107"> translates <xref:System.Linq.Queryable.Skip%2A> by using a subquery with the SQL `NOT EXISTS` clause.</span></span> <span data-ttu-id="94e69-108">Esta conversión tiene las limitaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="94e69-108">This translation has the following limitations:</span></span>  
  
-   <span data-ttu-id="94e69-109">El argumento debe ser un conjunto.</span><span class="sxs-lookup"><span data-stu-id="94e69-109">The argument must be a set.</span></span> <span data-ttu-id="94e69-110">No se admiten los conjuntos múltiples, aunque estén ordenados.</span><span class="sxs-lookup"><span data-stu-id="94e69-110">Multisets are not supported, even if ordered.</span></span>  
  
-   <span data-ttu-id="94e69-111">La consulta generada puede ser mucho más compleja que la consulta generada para la consulta base en la que se aplica <xref:System.Linq.Queryable.Skip%2A>.</span><span class="sxs-lookup"><span data-stu-id="94e69-111">The generated query can be much more complex than the query generated for the base query on which <xref:System.Linq.Queryable.Skip%2A> is applied.</span></span> <span data-ttu-id="94e69-112">Esta complejidad puede mermar el rendimiento o incluso hacer que se agote el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="94e69-112">This complexity can cause decrease in performance or even a time-out.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94e69-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="94e69-113">Example</span></span>  
 <span data-ttu-id="94e69-114">En el ejemplo siguiente se utiliza `Take` para seleccionar los cinco primeros `Employees` contratados.</span><span class="sxs-lookup"><span data-stu-id="94e69-114">The following example uses `Take` to select the first five `Employees` hired.</span></span> <span data-ttu-id="94e69-115">Observe que la colección primero se ordena por `HireDate`.</span><span class="sxs-lookup"><span data-stu-id="94e69-115">Note that the collection is first sorted by `HireDate`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#16](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#16)]
 [!code-vb[DLinqQueryExamples#16](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#16)]  
  
## <a name="example"></a><span data-ttu-id="94e69-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="94e69-116">Example</span></span>  
 <span data-ttu-id="94e69-117">En el ejemplo siguiente se utiliza <xref:System.Linq.Queryable.Skip%2A> para seleccionar todos los `Products` excepto los 10 más caros.</span><span class="sxs-lookup"><span data-stu-id="94e69-117">The following example uses <xref:System.Linq.Queryable.Skip%2A> to select all except the 10 most expensive `Products`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#17](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#17)]
 [!code-vb[DLinqQueryExamples#17](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#17)]  
  
## <a name="example"></a><span data-ttu-id="94e69-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="94e69-118">Example</span></span>  
 <span data-ttu-id="94e69-119">En el ejemplo siguiente se combinan los métodos <xref:System.Linq.Queryable.Skip%2A> y <xref:System.Linq.Queryable.Take%2A> para omitir los 50 primeros registros y después devolver los 10 siguientes.</span><span class="sxs-lookup"><span data-stu-id="94e69-119">The following example combines the <xref:System.Linq.Queryable.Skip%2A> and <xref:System.Linq.Queryable.Take%2A> methods to skip the first 50 records and then return the next 10.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#18](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#18)]
 [!code-vb[DLinqQueryExamples#18](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#18)]  
  
 <span data-ttu-id="94e69-120">Las operaciones <xref:System.Linq.Queryable.Take%2A> y <xref:System.Linq.Queryable.Skip%2A> solo están perfectamente definidas para los conjuntos ordenados.</span><span class="sxs-lookup"><span data-stu-id="94e69-120"><xref:System.Linq.Queryable.Take%2A> and <xref:System.Linq.Queryable.Skip%2A> operations are well defined only against ordered sets.</span></span> <span data-ttu-id="94e69-121">La semántica para los conjuntos no ordenados o conjuntos múltiples no está definida.</span><span class="sxs-lookup"><span data-stu-id="94e69-121">The semantics for unordered sets or multisets is undefined.</span></span>  
  
 <span data-ttu-id="94e69-122">Debido a las limitaciones de la ordenación en SQL, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] intenta trasladar la ordenación del argumento del operador <xref:System.Linq.Queryable.Take%2A> o <xref:System.Linq.Queryable.Skip%2A> al resultado del operador.</span><span class="sxs-lookup"><span data-stu-id="94e69-122">Because of the limitations on ordering in SQL, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tries to move the ordering of the argument of the <xref:System.Linq.Queryable.Take%2A> or <xref:System.Linq.Queryable.Skip%2A> operator to the result of the operator.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="94e69-123">La conversión es diferente para [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)] y [!INCLUDE[sqprsqlong](../../../../../../includes/sqprsqlong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94e69-123">Translation is different for [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)] and [!INCLUDE[sqprsqlong](../../../../../../includes/sqprsqlong-md.md)].</span></span> <span data-ttu-id="94e69-124">Si piensa utilizar <xref:System.Linq.Queryable.Skip%2A> con una consulta de cualquier complejidad, utilice [!INCLUDE[sqprsqlong](../../../../../../includes/sqprsqlong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94e69-124">If you plan to use <xref:System.Linq.Queryable.Skip%2A> with a query of any complexity, use [!INCLUDE[sqprsqlong](../../../../../../includes/sqprsqlong-md.md)].</span></span>  
  
 <span data-ttu-id="94e69-125">Considere la siguiente consulta [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="94e69-125">Consider the following [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query for [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)]:</span></span>  
  
 [!code-csharp[DLinqQueryExamples#19](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#19)]
 [!code-vb[DLinqQueryExamples#19](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#19)]  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="94e69-126"> traslada la operación de ordenación al final en el código de SQL, como se observa a continuación:</span><span class="sxs-lookup"><span data-stu-id="94e69-126"> moves the ordering to the end in the SQL code, as follows:</span></span>  
  
```  
SELECT TOP 1 [t0].[CustomerID], [t0].[CompanyName],  
FROM [Customers] AS [t0]  
WHERE (NOT (EXISTS(  
    SELECT NULL AS [EMPTY]  
    FROM (  
        SELECT TOP 1 [t1].[CustomerID]  
        FROM [Customers] AS [t1]  
        WHERE [t1].[City] = @p0  
        ORDER BY [t1].[CustomerID]  
        ) AS [t2]  
    WHERE [t0].[CustomerID] = [t2].[CustomerID]  
    ))) AND ([t0].[City] = @p1)  
ORDER BY [t0].[CustomerID]  
```  
  
 <span data-ttu-id="94e69-127">Cuando se encadenan <xref:System.Linq.Queryable.Take%2A> y <xref:System.Linq.Queryable.Skip%2A>, todos los criterios de ordenación especificados deben ser coherentes.</span><span class="sxs-lookup"><span data-stu-id="94e69-127">When <xref:System.Linq.Queryable.Take%2A> and <xref:System.Linq.Queryable.Skip%2A> are chained together, all the specified ordering must be consistent.</span></span> <span data-ttu-id="94e69-128">De lo contrario, los resultados no están definidos.</span><span class="sxs-lookup"><span data-stu-id="94e69-128">Otherwise, the results are undefined.</span></span>  
  
 <span data-ttu-id="94e69-129">Para los argumentos integrales constantes no negativos basados en la especificación de SQL, tanto <xref:System.Linq.Queryable.Take%2A> como <xref:System.Linq.Queryable.Skip%2A> están perfectamente definidos.</span><span class="sxs-lookup"><span data-stu-id="94e69-129">For non-negative, constant integral arguments based on the SQL specification, both <xref:System.Linq.Queryable.Take%2A> and <xref:System.Linq.Queryable.Skip%2A> are well-defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94e69-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="94e69-130">See Also</span></span>  
 [<span data-ttu-id="94e69-131">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="94e69-131">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [<span data-ttu-id="94e69-132">Traslación del operador de consulta estándar</span><span class="sxs-lookup"><span data-stu-id="94e69-132">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
