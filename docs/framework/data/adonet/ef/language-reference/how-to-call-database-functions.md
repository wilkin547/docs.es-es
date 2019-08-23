---
title: Procedimiento para llamar a funciones de base de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 79038efa-15bf-464a-83e2-35fe145252ce
ms.openlocfilehash: dd440be3f73eb2f02a269a8cad29f0fe30920836
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936023"
---
# <a name="how-to-call-database-functions"></a><span data-ttu-id="da26d-102">Procedimiento para llamar a funciones de base de datos</span><span class="sxs-lookup"><span data-stu-id="da26d-102">How to: Call Database Functions</span></span>
<span data-ttu-id="da26d-103">La clase <xref:System.Data.Objects.SqlClient.SqlFunctions> contiene métodos que exponen funciones de SQL Server para usarlas en consultas LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="da26d-103">The <xref:System.Data.Objects.SqlClient.SqlFunctions> class contains methods that expose SQL Server functions to use in LINQ to Entities queries.</span></span> <span data-ttu-id="da26d-104">Al usar los métodos <xref:System.Data.Objects.SqlClient.SqlFunctions> en consultas LINQ to Entities, las funciones de base de datos correspondientes se ejecutan en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="da26d-104">When you use <xref:System.Data.Objects.SqlClient.SqlFunctions> methods in LINQ to Entities queries, the corresponding database functions are executed in the database.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="da26d-105">Las funciones de base de datos que realizan un cálculo en un conjunto de valores y devuelven un valor único (también denominadas funciones de agregado de base de datos) se pueden invocar directamente.</span><span class="sxs-lookup"><span data-stu-id="da26d-105">Database functions that perform a calculation on a set of values and return a single value (also known as aggregate database functions) can be directly invoked.</span></span> <span data-ttu-id="da26d-106">Otras funciones canónicas solo se pueden llamar como parte de una consulta LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="da26d-106">Other canonical functions can only be called as part of a LINQ to Entities query.</span></span> <span data-ttu-id="da26d-107">Para llamar directamente a una función de agregado, debe pasar un objeto <xref:System.Data.Objects.ObjectQuery%601> a la función.</span><span class="sxs-lookup"><span data-stu-id="da26d-107">To call an aggregate function directly, you must pass an <xref:System.Data.Objects.ObjectQuery%601> to the function.</span></span> <span data-ttu-id="da26d-108">Para obtener más información, vea el segundo ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="da26d-108">For more information, see the second example below.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="da26d-109">Los métodos de la clase <xref:System.Data.Objects.SqlClient.SqlFunctions> son específicos de las funciones de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="da26d-109">The methods in the <xref:System.Data.Objects.SqlClient.SqlFunctions> class are specific to SQL Server functions.</span></span> <span data-ttu-id="da26d-110">Es posible que otros proveedores dispongan de clases similares que exponen funciones de base de datos.</span><span class="sxs-lookup"><span data-stu-id="da26d-110">Similar classes that expose database functions may be available through other providers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da26d-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="da26d-111">Example</span></span>  
 <span data-ttu-id="da26d-112">En el ejemplo siguiente se usa el [modelo AdventureWorks Sales](https://archive.codeplex.com/?p=msftdbprodsamples).</span><span class="sxs-lookup"><span data-stu-id="da26d-112">The following example uses the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples).</span></span> <span data-ttu-id="da26d-113">En el ejemplo se ejecuta una consulta LINQ to Entities que usa el método <xref:System.Data.Objects.SqlClient.SqlFunctions.CharIndex%2A> para devolver todos los contactos cuyos apellidos empiezan por "Si":</span><span class="sxs-lookup"><span data-stu-id="da26d-113">The example executes a LINQ to Entities query that uses the <xref:System.Data.Objects.SqlClient.SqlFunctions.CharIndex%2A> method to return all contacts whose last name starts with "Si":</span></span>  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#3)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="da26d-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="da26d-114">Example</span></span>  
 <span data-ttu-id="da26d-115">En el ejemplo siguiente se usa el [modelo AdventureWorks Sales](https://archive.codeplex.com/?p=msftdbprodsamples).</span><span class="sxs-lookup"><span data-stu-id="da26d-115">The following example uses the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples).</span></span> <span data-ttu-id="da26d-116">El ejemplo llama directamente al método de agregado <xref:System.Data.Objects.SqlClient.SqlFunctions.ChecksumAggregate%2A>.</span><span class="sxs-lookup"><span data-stu-id="da26d-116">The example calls the aggregate <xref:System.Data.Objects.SqlClient.SqlFunctions.ChecksumAggregate%2A> method directly.</span></span> <span data-ttu-id="da26d-117">Observe que se pasa un objeto <xref:System.Data.Objects.ObjectQuery%601> a la función, lo que permite llamarla aunque no forme parte de una consulta LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="da26d-117">Note that an <xref:System.Data.Objects.ObjectQuery%601> is passed to the function, which allows it to be called without being part of a LINQ to Entities query.</span></span>  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#4)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="da26d-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="da26d-118">See also</span></span>

- [<span data-ttu-id="da26d-119">Llamada a funciones en consultas de LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="da26d-119">Calling Functions in LINQ to Entities Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)
- [<span data-ttu-id="da26d-120">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="da26d-120">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
