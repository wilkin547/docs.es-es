---
title: Procedimiento para llamar a funciones canónicas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b3d84873-7403-4957-8e20-b4ae39f50214
ms.openlocfilehash: acfbdbaf21fe1d454b68dfef5bf4f88d8020ea65
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204455"
---
# <a name="how-to-call-canonical-functions"></a><span data-ttu-id="c7b3a-102">Procedimiento para llamar a funciones canónicas</span><span class="sxs-lookup"><span data-stu-id="c7b3a-102">How to: Call Canonical Functions</span></span>

<span data-ttu-id="c7b3a-103">La clase <xref:System.Data.Objects.EntityFunctions> contiene métodos que exponen funciones canónicas para usarlas en consultas LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="c7b3a-103">The <xref:System.Data.Objects.EntityFunctions> class contains methods that expose canonical functions to use in LINQ to Entities queries.</span></span> <span data-ttu-id="c7b3a-104">Para obtener información sobre las funciones canónicas, vea [Funciones canónicas](canonical-functions.md).</span><span class="sxs-lookup"><span data-stu-id="c7b3a-104">For information about canonical functions, see [Canonical Functions](canonical-functions.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c7b3a-105">Los métodos <xref:System.Data.Objects.EntityFunctions.AsUnicode%2A> y <xref:System.Data.Objects.EntityFunctions.AsNonUnicode%2A> de la clase <xref:System.Data.Objects.EntityFunctions> no tienen equivalentes de función canónica.</span><span class="sxs-lookup"><span data-stu-id="c7b3a-105">The <xref:System.Data.Objects.EntityFunctions.AsUnicode%2A> and <xref:System.Data.Objects.EntityFunctions.AsNonUnicode%2A> methods in the <xref:System.Data.Objects.EntityFunctions> class do not have canonical function equivalents.</span></span>  
  
 <span data-ttu-id="c7b3a-106">Las funciones canónicas que realizan un cálculo en un conjunto de valores y devuelven un valor único (también denominadas funciones canónicas de agregado) se pueden invocar directamente.</span><span class="sxs-lookup"><span data-stu-id="c7b3a-106">Canonical functions that perform a calculation on a set of values and return a single value (also known as aggregate canonical functions) can be directly invoked.</span></span> <span data-ttu-id="c7b3a-107">Otras funciones canónicas solo se pueden llamar como parte de una consulta LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="c7b3a-107">Other canonical functions can only be called as part of a LINQ to Entities query.</span></span> <span data-ttu-id="c7b3a-108">Para llamar directamente a una función de agregado, debe pasar un objeto <xref:System.Data.Objects.ObjectQuery%601> a la función.</span><span class="sxs-lookup"><span data-stu-id="c7b3a-108">To call an aggregate function directly, you must pass an <xref:System.Data.Objects.ObjectQuery%601> to the function.</span></span> <span data-ttu-id="c7b3a-109">Para obtener más información, vea el segundo ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c7b3a-109">For more information, see the second example below.</span></span>  
  
 <span data-ttu-id="c7b3a-110">Puede llamar a algunas funciones canónicas utilizando los métodos de Common Language Runtime (CLR) en consultas LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="c7b3a-110">You can call some canonical functions by using common language runtime (CLR) methods in LINQ to Entities queries.</span></span> <span data-ttu-id="c7b3a-111">Para obtener una lista de los métodos de CLR que se asignan a funciones canónicas, vea [asignación del método a la función canónica](clr-method-to-canonical-function-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="c7b3a-111">For a list of CLR methods that map to canonical functions, see [CLR Method to Canonical Function Mapping](clr-method-to-canonical-function-mapping.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7b3a-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c7b3a-112">Example</span></span>  

 <span data-ttu-id="c7b3a-113">En el ejemplo siguiente se usa el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span><span class="sxs-lookup"><span data-stu-id="c7b3a-113">The following example uses the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span></span> <span data-ttu-id="c7b3a-114">En el ejemplo se ejecuta una consulta LINQ to Entities que utiliza el método <xref:System.Data.Objects.EntityFunctions.DiffDays%2A> para devolver todos los productos para los que la diferencia entre `SellEndDate` y `SellStartDate` es menor a 365 días:</span><span class="sxs-lookup"><span data-stu-id="c7b3a-114">The example executes a LINQ to Entities query that uses the <xref:System.Data.Objects.EntityFunctions.DiffDays%2A> method to return all products for which the difference between `SellEndDate` and `SellStartDate` is less than 365 days:</span></span>  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#1)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="c7b3a-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c7b3a-115">Example</span></span>  

 <span data-ttu-id="c7b3a-116">En el ejemplo siguiente se usa el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span><span class="sxs-lookup"><span data-stu-id="c7b3a-116">The following example uses the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span></span> <span data-ttu-id="c7b3a-117">El ejemplo llama directamente al método de agregado <xref:System.Data.Objects.EntityFunctions.StandardDeviation%2A> para devolver la desviación estándar de subtotales `SalesOrderHeader`.</span><span class="sxs-lookup"><span data-stu-id="c7b3a-117">The example calls the aggregate <xref:System.Data.Objects.EntityFunctions.StandardDeviation%2A> method directly to return the standard deviation of `SalesOrderHeader` subtotals.</span></span> <span data-ttu-id="c7b3a-118">Observe que se pasa un objeto <xref:System.Data.Objects.ObjectQuery%601> a la función, lo que permite llamarla aunque no forme parte de una consulta LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="c7b3a-118">Note that an <xref:System.Data.Objects.ObjectQuery%601> is passed to the function, which allows it to be called without being part of a LINQ to Entities query.</span></span>  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#2)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="c7b3a-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c7b3a-119">See also</span></span>

- [<span data-ttu-id="c7b3a-120">Llamar a funciones en consultas de LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="c7b3a-120">Calling Functions in LINQ to Entities Queries</span></span>](calling-functions-in-linq-to-entities-queries.md)
- [<span data-ttu-id="c7b3a-121">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="c7b3a-121">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
