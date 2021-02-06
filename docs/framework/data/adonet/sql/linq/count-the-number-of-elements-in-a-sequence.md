---
description: 'Más información acerca de: contar el número de elementos de una secuencia'
title: Contar el número de elementos de una secuencia
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ccbe5d54-c9eb-4b14-b0ab-f628483c5f99
ms.openlocfilehash: 91030516098e900229a1e131ea0c9a7d8bef4034
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99663084"
---
# <a name="count-the-number-of-elements-in-a-sequence"></a><span data-ttu-id="df533-103">Contar el número de elementos de una secuencia</span><span class="sxs-lookup"><span data-stu-id="df533-103">Count the Number of Elements in a Sequence</span></span>

<span data-ttu-id="df533-104">Utilice al operador <xref:System.Linq.Enumerable.Count%2A> para contar el número de elementos de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="df533-104">Use the <xref:System.Linq.Enumerable.Count%2A> operator to count the number of elements in a sequence.</span></span>  
  
 <span data-ttu-id="df533-105">Al ejecutar esta consulta en la base de datos de ejemplo Northwind, se genera un resultado de `91`.</span><span class="sxs-lookup"><span data-stu-id="df533-105">Running this query against the Northwind sample database produces an output of `91`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df533-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="df533-106">Example</span></span>  

 <span data-ttu-id="df533-107">En el ejemplo siguiente se cuenta el número de `Customers` en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="df533-107">The following example counts the number of `Customers` in the database.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#4)]
 [!code-vb[DLinqQueryExamples#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="df533-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="df533-108">Example</span></span>  

 <span data-ttu-id="df533-109">En el ejemplo siguiente se cuenta el número de productos de la base de datos que no han dejado de fabricarse.</span><span class="sxs-lookup"><span data-stu-id="df533-109">The following example counts the number of products in the database that have not been discontinued.</span></span>  
  
 <span data-ttu-id="df533-110">Al ejecutar este ejemplo en la base de datos de ejemplo Northwind, se genera un resultado de `69`.</span><span class="sxs-lookup"><span data-stu-id="df533-110">Running this example against the Northwind sample database produces an output of `69`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#5)]
 [!code-vb[DLinqQueryExamples#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="df533-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="df533-111">See also</span></span>

- [<span data-ttu-id="df533-112">Consultas de agregado</span><span class="sxs-lookup"><span data-stu-id="df533-112">Aggregate Queries</span></span>](aggregate-queries.md)
- [<span data-ttu-id="df533-113">Descargar bases de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="df533-113">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
