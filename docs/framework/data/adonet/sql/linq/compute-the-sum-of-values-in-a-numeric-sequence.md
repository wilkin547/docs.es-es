---
description: 'Más información sobre: calcular la suma de los valores de una secuencia numérica'
title: Calcular la suma de valores de una secuencia numérica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 24e335b0-984e-4825-8721-0a91b533b7c3
ms.openlocfilehash: c4eb066b9286335111d96d32437291da9ea2d49a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712550"
---
# <a name="compute-the-sum-of-values-in-a-numeric-sequence"></a><span data-ttu-id="3f032-103">Calcular la suma de valores de una secuencia numérica</span><span class="sxs-lookup"><span data-stu-id="3f032-103">Compute the Sum of Values in a Numeric Sequence</span></span>

<span data-ttu-id="3f032-104">Utilice el operador <xref:System.Linq.Enumerable.Sum%2A> para calcular la suma de los valores numéricos de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="3f032-104">Use the <xref:System.Linq.Enumerable.Sum%2A> operator to compute the sum of numeric values in a sequence.</span></span>  
  
 <span data-ttu-id="3f032-105">Tenga en cuenta las características siguientes del operador `Sum` en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="3f032-105">Note the following characteristics of the `Sum` operator in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span></span>  
  
- <span data-ttu-id="3f032-106">El operador de consulta estándar de agregado `Sum` se evalúa como cero para una secuencia vacía o una secuencia que solo contiene valores nulos.</span><span class="sxs-lookup"><span data-stu-id="3f032-106">The Standard Query Operator aggregate operator `Sum` evaluates to zero for an empty sequence or a sequence that contains only nulls.</span></span> <span data-ttu-id="3f032-107">En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], la semántica de SQL se mantiene invariable.</span><span class="sxs-lookup"><span data-stu-id="3f032-107">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the semantics of SQL are left unchanged.</span></span> <span data-ttu-id="3f032-108">Por esta razón, `Sum` se evalúa como Null en lugar de cero en el caso de secuencias vacías o secuencias que solo contienen valores nulos.</span><span class="sxs-lookup"><span data-stu-id="3f032-108">For this reason, `Sum` evaluates to null instead of to zero for an empty sequence or for a sequence that contains only nulls.</span></span>  
  
- <span data-ttu-id="3f032-109">En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] se aplican las restricciones de SQL para los agregados en los resultados intermedios.</span><span class="sxs-lookup"><span data-stu-id="3f032-109">SQL limitations on intermediate results apply to aggregates in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="3f032-110">La suma de las cantidades de enteros de 32 bits no se calcula mediante resultados de 64 bits y se puede producir un desbordamiento para la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] traducción de `Sum` .</span><span class="sxs-lookup"><span data-stu-id="3f032-110">Sum of 32-bit integer quantities is not computed by using 64-bit results, and overflow can occur for the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translation of `Sum`.</span></span> <span data-ttu-id="3f032-111">Esta posibilidad existe aun cuando la implementación del operador de consulta estándar no produzca un desbordamiento para la secuencia en memoria correspondiente.</span><span class="sxs-lookup"><span data-stu-id="3f032-111">This possibility exists even if the Standard Query Operator implementation does not cause an overflow for the corresponding in-memory sequence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f032-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3f032-112">Example</span></span>  

 <span data-ttu-id="3f032-113">En el ejemplo siguiente se busca el flete total de todos los pedidos de la tabla `Order`.</span><span class="sxs-lookup"><span data-stu-id="3f032-113">The following example finds the total freight of all orders in the `Order` table.</span></span>  
  
 <span data-ttu-id="3f032-114">Si ejecuta esta consulta en la base de datos de ejemplo Northwind, el resultado es: `64942.6900`.</span><span class="sxs-lookup"><span data-stu-id="3f032-114">If you run this query against the Northwind sample database, the output is: `64942.6900`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#12](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#12)]
 [!code-vb[DLinqQueryExamples#12](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="3f032-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3f032-115">Example</span></span>  

 <span data-ttu-id="3f032-116">En el ejemplo siguiente se busca el número total de unidades pedidas para todos los productos.</span><span class="sxs-lookup"><span data-stu-id="3f032-116">The following example finds the total number of units on order for all products.</span></span>  
  
 <span data-ttu-id="3f032-117">Si ejecuta esta consulta en la base de datos de ejemplo Northwind, el resultado es: `780`.</span><span class="sxs-lookup"><span data-stu-id="3f032-117">If you run this query against the Northwind sample database, the output is: `780`.</span></span>  
  
 <span data-ttu-id="3f032-118">Tenga en cuenta que debe convertir los tipos `short` (por ejemplo, `UnitsOnOrder`) porque `Sum` no tiene una sobrecarga para ellos.</span><span class="sxs-lookup"><span data-stu-id="3f032-118">Note that you must cast `short` types (for example, `UnitsOnOrder`) because `Sum` has no overload for short types.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#13](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#13)]
 [!code-vb[DLinqQueryExamples#13](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#13)]  
  
## <a name="see-also"></a><span data-ttu-id="3f032-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f032-119">See also</span></span>

- [<span data-ttu-id="3f032-120">Consultas de agregado</span><span class="sxs-lookup"><span data-stu-id="3f032-120">Aggregate Queries</span></span>](aggregate-queries.md)
- [<span data-ttu-id="3f032-121">Descargar bases de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="3f032-121">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
