---
title: Contar el número de elementos de una secuencia
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ccbe5d54-c9eb-4b14-b0ab-f628483c5f99
ms.openlocfilehash: 928cfd33a187637c6d18da3cccefb22bb2950acf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353842"
---
# <a name="count-the-number-of-elements-in-a-sequence"></a><span data-ttu-id="b5bd9-102">Contar el número de elementos de una secuencia</span><span class="sxs-lookup"><span data-stu-id="b5bd9-102">Count the Number of Elements in a Sequence</span></span>
<span data-ttu-id="b5bd9-103">Utilice al operador <xref:System.Linq.Enumerable.Count%2A> para contar el número de elementos de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="b5bd9-103">Use the <xref:System.Linq.Enumerable.Count%2A> operator to count the number of elements in a sequence.</span></span>  
  
 <span data-ttu-id="b5bd9-104">Al ejecutar esta consulta en la base de datos de ejemplo Northwind, se genera un resultado de `91`.</span><span class="sxs-lookup"><span data-stu-id="b5bd9-104">Running this query against the Northwind sample database produces an output of `91`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5bd9-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b5bd9-105">Example</span></span>  
 <span data-ttu-id="b5bd9-106">En el ejemplo siguiente se cuenta el número de `Customers` en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b5bd9-106">The following example counts the number of `Customers` in the database.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#4)]
 [!code-vb[DLinqQueryExamples#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="b5bd9-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b5bd9-107">Example</span></span>  
 <span data-ttu-id="b5bd9-108">En el ejemplo siguiente se cuenta el número de productos de la base de datos que no han dejado de fabricarse.</span><span class="sxs-lookup"><span data-stu-id="b5bd9-108">The following example counts the number of products in the database that have not been discontinued.</span></span>  
  
 <span data-ttu-id="b5bd9-109">Al ejecutar este ejemplo en la base de datos de ejemplo Northwind, se genera un resultado de `69`.</span><span class="sxs-lookup"><span data-stu-id="b5bd9-109">Running this example against the Northwind sample database produces an output of `69`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#5)]
 [!code-vb[DLinqQueryExamples#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="b5bd9-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5bd9-110">See Also</span></span>  
 [<span data-ttu-id="b5bd9-111">Consultas de agregado</span><span class="sxs-lookup"><span data-stu-id="b5bd9-111">Aggregate Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)  
 [<span data-ttu-id="b5bd9-112">Descargar bases de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="b5bd9-112">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
