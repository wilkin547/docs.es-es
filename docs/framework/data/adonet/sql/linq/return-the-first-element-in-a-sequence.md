---
title: Devolver el primer elemento de una secuencia
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ccdc3777-b2c2-44e3-a627-abef8d79a555
ms.openlocfilehash: dca917b3c12b0f9923cc9ea34a2568c412a09831
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033454"
---
# <a name="return-the-first-element-in-a-sequence"></a><span data-ttu-id="c6034-102">Devolver el primer elemento de una secuencia</span><span class="sxs-lookup"><span data-stu-id="c6034-102">Return the First Element in a Sequence</span></span>
<span data-ttu-id="c6034-103">Utilice el operador <xref:System.Linq.Enumerable.First%2A> para devolver el primer elemento de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="c6034-103">Use the <xref:System.Linq.Enumerable.First%2A> operator to return the first element in a sequence.</span></span> <span data-ttu-id="c6034-104">Las consultas que usan <xref:System.Linq.Enumerable.First%2A> se ejecutan inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="c6034-104">Queries that use <xref:System.Linq.Enumerable.First%2A> are executed immediately.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="c6034-105">no admite el operador <xref:System.Linq.Enumerable.Last%2A>.</span><span class="sxs-lookup"><span data-stu-id="c6034-105">does not support the <xref:System.Linq.Enumerable.Last%2A> operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6034-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c6034-106">Example</span></span>  
 <span data-ttu-id="c6034-107">El código siguiente busca el primer `Shipper` de una tabla:</span><span class="sxs-lookup"><span data-stu-id="c6034-107">The following code finds the first `Shipper` in a table:</span></span>  
  
 <span data-ttu-id="c6034-108">Si ejecuta esta consulta en la base de datos de ejemplo Northwind, los resultados son</span><span class="sxs-lookup"><span data-stu-id="c6034-108">If you run this query against the Northwind sample database, the results are</span></span>  
  
 <span data-ttu-id="c6034-109">`ID = 1, Company = Speedy Express`.</span><span class="sxs-lookup"><span data-stu-id="c6034-109">`ID = 1, Company = Speedy Express`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#14](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#14)]
 [!code-vb[DLinqQueryExamples#14](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="c6034-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c6034-110">Example</span></span>  
 <span data-ttu-id="c6034-111">El código siguiente busca el `Customer` único cuyo `CustomerID` es BONAP.</span><span class="sxs-lookup"><span data-stu-id="c6034-111">The following code finds the single `Customer` that has the `CustomerID` BONAP.</span></span>  
  
 <span data-ttu-id="c6034-112">Si ejecuta esta consulta en la base de datos de ejemplo Northwind, los resultados son `ID = BONAP, Contact = Laurence Lebihan`.</span><span class="sxs-lookup"><span data-stu-id="c6034-112">If you run this query against the Northwind sample database, the results are `ID = BONAP, Contact = Laurence Lebihan`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#15](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#15)]
 [!code-vb[DLinqQueryExamples#15](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="c6034-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6034-113">See also</span></span>

- [<span data-ttu-id="c6034-114">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="c6034-114">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [<span data-ttu-id="c6034-115">Descargar bases de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="c6034-115">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
