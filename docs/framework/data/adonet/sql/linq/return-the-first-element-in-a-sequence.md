---
description: 'Más información sobre: devolver el primer elemento de una secuencia'
title: Devolver el primer elemento de una secuencia
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ccdc3777-b2c2-44e3-a627-abef8d79a555
ms.openlocfilehash: 004e9a1f03677f6ba49916404b1c44408df40dfa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99663019"
---
# <a name="return-the-first-element-in-a-sequence"></a><span data-ttu-id="7de7b-103">Devolver el primer elemento de una secuencia</span><span class="sxs-lookup"><span data-stu-id="7de7b-103">Return the First Element in a Sequence</span></span>

<span data-ttu-id="7de7b-104">Utilice el operador <xref:System.Linq.Enumerable.First%2A> para devolver el primer elemento de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="7de7b-104">Use the <xref:System.Linq.Enumerable.First%2A> operator to return the first element in a sequence.</span></span> <span data-ttu-id="7de7b-105">Las consultas que usan <xref:System.Linq.Enumerable.First%2A> se ejecutan inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="7de7b-105">Queries that use <xref:System.Linq.Enumerable.First%2A> are executed immediately.</span></span>  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="7de7b-106">no admite el operador <xref:System.Linq.Enumerable.Last%2A>.</span><span class="sxs-lookup"><span data-stu-id="7de7b-106">does not support the <xref:System.Linq.Enumerable.Last%2A> operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7de7b-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7de7b-107">Example</span></span>  

 <span data-ttu-id="7de7b-108">El código siguiente busca el primer `Shipper` de una tabla:</span><span class="sxs-lookup"><span data-stu-id="7de7b-108">The following code finds the first `Shipper` in a table:</span></span>  
  
 <span data-ttu-id="7de7b-109">Si ejecuta esta consulta en la base de datos de ejemplo Northwind, los resultados son</span><span class="sxs-lookup"><span data-stu-id="7de7b-109">If you run this query against the Northwind sample database, the results are</span></span>  
  
 <span data-ttu-id="7de7b-110">`ID = 1, Company = Speedy Express`.</span><span class="sxs-lookup"><span data-stu-id="7de7b-110">`ID = 1, Company = Speedy Express`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#14](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#14)]
 [!code-vb[DLinqQueryExamples#14](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="7de7b-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7de7b-111">Example</span></span>  

 <span data-ttu-id="7de7b-112">El código siguiente busca el `Customer` único cuyo `CustomerID` es BONAP.</span><span class="sxs-lookup"><span data-stu-id="7de7b-112">The following code finds the single `Customer` that has the `CustomerID` BONAP.</span></span>  
  
 <span data-ttu-id="7de7b-113">Si ejecuta esta consulta en la base de datos de ejemplo Northwind, los resultados son `ID = BONAP, Contact = Laurence Lebihan`.</span><span class="sxs-lookup"><span data-stu-id="7de7b-113">If you run this query against the Northwind sample database, the results are `ID = BONAP, Contact = Laurence Lebihan`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#15](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#15)]
 [!code-vb[DLinqQueryExamples#15](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="7de7b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="7de7b-114">See also</span></span>

- [<span data-ttu-id="7de7b-115">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="7de7b-115">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="7de7b-116">Descargar bases de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="7de7b-116">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
