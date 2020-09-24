---
title: Contar el número de elementos de una secuencia
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ccbe5d54-c9eb-4b14-b0ab-f628483c5f99
ms.openlocfilehash: d983bc14f4fda04bda0a6f363db4c11f062c4c48
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164355"
---
# <a name="count-the-number-of-elements-in-a-sequence"></a><span data-ttu-id="fb0e1-102">Contar el número de elementos de una secuencia</span><span class="sxs-lookup"><span data-stu-id="fb0e1-102">Count the Number of Elements in a Sequence</span></span>

<span data-ttu-id="fb0e1-103">Utilice al operador <xref:System.Linq.Enumerable.Count%2A> para contar el número de elementos de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="fb0e1-103">Use the <xref:System.Linq.Enumerable.Count%2A> operator to count the number of elements in a sequence.</span></span>  
  
 <span data-ttu-id="fb0e1-104">Al ejecutar esta consulta en la base de datos de ejemplo Northwind, se genera un resultado de `91`.</span><span class="sxs-lookup"><span data-stu-id="fb0e1-104">Running this query against the Northwind sample database produces an output of `91`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb0e1-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fb0e1-105">Example</span></span>  

 <span data-ttu-id="fb0e1-106">En el ejemplo siguiente se cuenta el número de `Customers` en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="fb0e1-106">The following example counts the number of `Customers` in the database.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#4)]
 [!code-vb[DLinqQueryExamples#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="fb0e1-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fb0e1-107">Example</span></span>  

 <span data-ttu-id="fb0e1-108">En el ejemplo siguiente se cuenta el número de productos de la base de datos que no han dejado de fabricarse.</span><span class="sxs-lookup"><span data-stu-id="fb0e1-108">The following example counts the number of products in the database that have not been discontinued.</span></span>  
  
 <span data-ttu-id="fb0e1-109">Al ejecutar este ejemplo en la base de datos de ejemplo Northwind, se genera un resultado de `69`.</span><span class="sxs-lookup"><span data-stu-id="fb0e1-109">Running this example against the Northwind sample database produces an output of `69`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#5)]
 [!code-vb[DLinqQueryExamples#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="fb0e1-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fb0e1-110">See also</span></span>

- [<span data-ttu-id="fb0e1-111">Consultas de agregado</span><span class="sxs-lookup"><span data-stu-id="fb0e1-111">Aggregate Queries</span></span>](aggregate-queries.md)
- [<span data-ttu-id="fb0e1-112">Descargar bases de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="fb0e1-112">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
