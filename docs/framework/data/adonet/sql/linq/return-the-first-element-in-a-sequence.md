---
title: Devolver el primer elemento de una secuencia
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ccdc3777-b2c2-44e3-a627-abef8d79a555
ms.openlocfilehash: 39cf9270b08fce64590fef418bb428c5a781b0e9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963806"
---
# <a name="return-the-first-element-in-a-sequence"></a><span data-ttu-id="dfef4-102">Devolver el primer elemento de una secuencia</span><span class="sxs-lookup"><span data-stu-id="dfef4-102">Return the First Element in a Sequence</span></span>
<span data-ttu-id="dfef4-103">Utilice el operador <xref:System.Linq.Enumerable.First%2A> para devolver el primer elemento de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="dfef4-103">Use the <xref:System.Linq.Enumerable.First%2A> operator to return the first element in a sequence.</span></span> <span data-ttu-id="dfef4-104">Las consultas que usan <xref:System.Linq.Enumerable.First%2A> se ejecutan inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="dfef4-104">Queries that use <xref:System.Linq.Enumerable.First%2A> are executed immediately.</span></span>  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="dfef4-105">no admite el operador <xref:System.Linq.Enumerable.Last%2A>.</span><span class="sxs-lookup"><span data-stu-id="dfef4-105">does not support the <xref:System.Linq.Enumerable.Last%2A> operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dfef4-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dfef4-106">Example</span></span>  
 <span data-ttu-id="dfef4-107">El código siguiente busca el primer `Shipper` de una tabla:</span><span class="sxs-lookup"><span data-stu-id="dfef4-107">The following code finds the first `Shipper` in a table:</span></span>  
  
 <span data-ttu-id="dfef4-108">Si ejecuta esta consulta en la base de datos de ejemplo Northwind, los resultados son</span><span class="sxs-lookup"><span data-stu-id="dfef4-108">If you run this query against the Northwind sample database, the results are</span></span>  
  
 <span data-ttu-id="dfef4-109">`ID = 1, Company = Speedy Express`.</span><span class="sxs-lookup"><span data-stu-id="dfef4-109">`ID = 1, Company = Speedy Express`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#14](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#14)]
 [!code-vb[DLinqQueryExamples#14](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="dfef4-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dfef4-110">Example</span></span>  
 <span data-ttu-id="dfef4-111">El código siguiente busca el `Customer` único cuyo `CustomerID` es BONAP.</span><span class="sxs-lookup"><span data-stu-id="dfef4-111">The following code finds the single `Customer` that has the `CustomerID` BONAP.</span></span>  
  
 <span data-ttu-id="dfef4-112">Si ejecuta esta consulta en la base de datos de ejemplo Northwind, los resultados son `ID = BONAP, Contact = Laurence Lebihan`.</span><span class="sxs-lookup"><span data-stu-id="dfef4-112">If you run this query against the Northwind sample database, the results are `ID = BONAP, Contact = Laurence Lebihan`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#15](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#15)]
 [!code-vb[DLinqQueryExamples#15](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="dfef4-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="dfef4-113">See also</span></span>

- [<span data-ttu-id="dfef4-114">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="dfef4-114">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [<span data-ttu-id="dfef4-115">Descargar bases de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="dfef4-115">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
