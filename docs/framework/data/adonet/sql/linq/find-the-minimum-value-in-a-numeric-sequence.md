---
description: 'Más información acerca de: buscar el valor mínimo en una secuencia numérica'
title: Buscar el valor mínimo de una secuencia numérica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 78203093-f242-4572-9b31-9495b10926aa
ms.openlocfilehash: 6f265c6db3e143bdd5371aa9d30b4dd248e8fe3f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803846"
---
# <a name="find-the-minimum-value-in-a-numeric-sequence"></a><span data-ttu-id="6a855-103">Buscar el valor mínimo de una secuencia numérica</span><span class="sxs-lookup"><span data-stu-id="6a855-103">Find the Minimum Value in a Numeric Sequence</span></span>

<span data-ttu-id="6a855-104">Utilice al operador <xref:System.Linq.Enumerable.Min%2A> para devolver el valor mínimo de una secuencia de valores numéricos.</span><span class="sxs-lookup"><span data-stu-id="6a855-104">Use the <xref:System.Linq.Enumerable.Min%2A> operator to return the minimum value from a sequence of numeric values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a855-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6a855-105">Example</span></span>  

 <span data-ttu-id="6a855-106">En el ejemplo siguiente se busca el precio unitario más bajo de cualquier producto.</span><span class="sxs-lookup"><span data-stu-id="6a855-106">The following example finds the lowest unit price of any product.</span></span>  
  
 <span data-ttu-id="6a855-107">Si ejecuta esta consulta en la base de datos de ejemplo Northwind, el resultado es: `2.5000`.</span><span class="sxs-lookup"><span data-stu-id="6a855-107">If you run this query against the Northwind sample database, the output is: `2.5000`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#9)]
 [!code-vb[DLinqQueryExamples#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="6a855-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6a855-108">Example</span></span>  

 <span data-ttu-id="6a855-109">En el ejemplo siguiente se busca el importe con flete más bajo de cualquier pedido.</span><span class="sxs-lookup"><span data-stu-id="6a855-109">The following example finds the lowest freight amount for any order.</span></span>  
  
 <span data-ttu-id="6a855-110">Si ejecuta esta consulta en la base de datos de ejemplo Northwind, el resultado es: `0.0200`.</span><span class="sxs-lookup"><span data-stu-id="6a855-110">If you run this query against the Northwind sample database, the output is: `0.0200`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#10](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#10)]
 [!code-vb[DLinqQueryExamples#10](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#10)]  
  
## <a name="example"></a><span data-ttu-id="6a855-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6a855-111">Example</span></span>  

 <span data-ttu-id="6a855-112">En el ejemplo siguiente se utiliza Min para encontrar los `Products` que tienen el precio unitario más bajo en cada categoría.</span><span class="sxs-lookup"><span data-stu-id="6a855-112">The following example uses Min to find the `Products` that have the lowest unit price in each category.</span></span> <span data-ttu-id="6a855-113">El resultado se organiza por categoría.</span><span class="sxs-lookup"><span data-stu-id="6a855-113">The output is arranged by category.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#11](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#11)]
 [!code-vb[DLinqQueryExamples#11](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#11)]  
  
 <span data-ttu-id="6a855-114">Si ejecuta la consulta anterior en la base de datos de ejemplo Northwind, los resultados se parecerán a los siguientes:</span><span class="sxs-lookup"><span data-stu-id="6a855-114">If you run the previous query against the Northwind sample database, your results will resemble the following:</span></span>  
  
 `1`  
  
 `Guaraná Fantástica`  
  
 `2`  
  
 `Aniseed Syrup`  
  
 `3`  
  
 `Teatime Chocolate Biscuits`  
  
 `4`  
  
 `Geitost`  
  
 `5`  
  
 `Filo Mix`  
  
 `6`  
  
 `Tourtière`  
  
 `7`  
  
 `Longlife Tofu`  
  
 `8`  
  
 `Konbu`  
  
## <a name="see-also"></a><span data-ttu-id="6a855-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a855-115">See also</span></span>

- [<span data-ttu-id="6a855-116">Consultas de agregado</span><span class="sxs-lookup"><span data-stu-id="6a855-116">Aggregate Queries</span></span>](aggregate-queries.md)
- [<span data-ttu-id="6a855-117">Descargar bases de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="6a855-117">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
