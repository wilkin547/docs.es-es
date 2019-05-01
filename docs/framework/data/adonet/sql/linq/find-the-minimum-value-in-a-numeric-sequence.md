---
title: Buscar el valor mínimo de una secuencia numérica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 78203093-f242-4572-9b31-9495b10926aa
ms.openlocfilehash: 84002609c550cc2de76f9948bf77f9fd88261f64
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62038459"
---
# <a name="find-the-minimum-value-in-a-numeric-sequence"></a><span data-ttu-id="81ef5-102">Buscar el valor mínimo de una secuencia numérica</span><span class="sxs-lookup"><span data-stu-id="81ef5-102">Find the Minimum Value in a Numeric Sequence</span></span>
<span data-ttu-id="81ef5-103">Utilice al operador <xref:System.Linq.Enumerable.Min%2A> para devolver el valor mínimo de una secuencia de valores numéricos.</span><span class="sxs-lookup"><span data-stu-id="81ef5-103">Use the <xref:System.Linq.Enumerable.Min%2A> operator to return the minimum value from a sequence of numeric values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81ef5-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="81ef5-104">Example</span></span>  
 <span data-ttu-id="81ef5-105">En el ejemplo siguiente se busca el precio unitario más bajo de cualquier producto.</span><span class="sxs-lookup"><span data-stu-id="81ef5-105">The following example finds the lowest unit price of any product.</span></span>  
  
 <span data-ttu-id="81ef5-106">Si ejecuta esta consulta en la base de datos de ejemplo Northwind, el resultado es: `2.5000`.</span><span class="sxs-lookup"><span data-stu-id="81ef5-106">If you run this query against the Northwind sample database, the output is: `2.5000`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#9)]
 [!code-vb[DLinqQueryExamples#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="81ef5-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="81ef5-107">Example</span></span>  
 <span data-ttu-id="81ef5-108">En el ejemplo siguiente se busca el importe con flete más bajo de cualquier pedido.</span><span class="sxs-lookup"><span data-stu-id="81ef5-108">The following example finds the lowest freight amount for any order.</span></span>  
  
 <span data-ttu-id="81ef5-109">Si ejecuta esta consulta en la base de datos de ejemplo Northwind, el resultado es: `0.0200`.</span><span class="sxs-lookup"><span data-stu-id="81ef5-109">If you run this query against the Northwind sample database, the output is: `0.0200`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#10](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#10)]
 [!code-vb[DLinqQueryExamples#10](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#10)]  
  
## <a name="example"></a><span data-ttu-id="81ef5-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="81ef5-110">Example</span></span>  
 <span data-ttu-id="81ef5-111">En el ejemplo siguiente se utiliza Min para encontrar los `Products` que tienen el precio unitario más bajo en cada categoría.</span><span class="sxs-lookup"><span data-stu-id="81ef5-111">The following example uses Min to find the `Products` that have the lowest unit price in each category.</span></span> <span data-ttu-id="81ef5-112">El resultado se organiza por categoría.</span><span class="sxs-lookup"><span data-stu-id="81ef5-112">The output is arranged by category.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#11](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#11)]
 [!code-vb[DLinqQueryExamples#11](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#11)]  
  
 <span data-ttu-id="81ef5-113">Si ejecuta la consulta anterior en la base de datos de ejemplo Northwind, los resultados se parecerán a los siguientes:</span><span class="sxs-lookup"><span data-stu-id="81ef5-113">If you run the previous query against the Northwind sample database, your results will resemble the following:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="81ef5-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="81ef5-114">See also</span></span>

- [<span data-ttu-id="81ef5-115">Consultas de agregado</span><span class="sxs-lookup"><span data-stu-id="81ef5-115">Aggregate Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)
- [<span data-ttu-id="81ef5-116">Descargar bases de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="81ef5-116">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
