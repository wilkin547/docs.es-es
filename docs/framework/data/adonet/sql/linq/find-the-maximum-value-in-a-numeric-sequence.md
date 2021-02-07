---
description: 'Más información acerca de: buscar el valor máximo en una secuencia numérica'
title: Buscar el valor máximo de una secuencia numérica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 70d7c058-0280-4815-a008-6f290093591a
ms.openlocfilehash: ab311f29d776c1ef4647967d391c7e4122ae7d38
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99672106"
---
# <a name="find-the-maximum-value-in-a-numeric-sequence"></a><span data-ttu-id="17e03-103">Buscar el valor máximo de una secuencia numérica</span><span class="sxs-lookup"><span data-stu-id="17e03-103">Find the Maximum Value in a Numeric Sequence</span></span>

<span data-ttu-id="17e03-104">Utilice el operador <xref:System.Linq.Enumerable.Max%2A> para buscar el valor máximo de una secuencia de valores numéricos.</span><span class="sxs-lookup"><span data-stu-id="17e03-104">Use the <xref:System.Linq.Enumerable.Max%2A> operator to find the highest value in a sequence of numeric values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17e03-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="17e03-105">Example</span></span>  

 <span data-ttu-id="17e03-106">En el ejemplo siguiente se busca la fecha de la última contratación de cualquier empleado.</span><span class="sxs-lookup"><span data-stu-id="17e03-106">The following example finds the latest date of hire for any employee.</span></span>  
  
 <span data-ttu-id="17e03-107">Si ejecuta esta consulta en la base de datos de ejemplo Northwind, el resultado es: `11/15/1994 12:00:00 AM`.</span><span class="sxs-lookup"><span data-stu-id="17e03-107">If you run this query against the sample Northwind database, the output is: `11/15/1994 12:00:00 AM`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#6)]
 [!code-vb[DLinqQueryExamples#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="17e03-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="17e03-108">Example</span></span>  

 <span data-ttu-id="17e03-109">En el ejemplo siguiente se busca el número máximo de unidades en existencias para cualquier producto.</span><span class="sxs-lookup"><span data-stu-id="17e03-109">The following example finds the most units in stock for any product.</span></span>  
  
 <span data-ttu-id="17e03-110">Si ejecuta este ejemplo en la base de datos de ejemplo Northwind, el resultado es: `125`.</span><span class="sxs-lookup"><span data-stu-id="17e03-110">If you run this example against the sample Northwind database, the output is: `125`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#7)]
 [!code-vb[DLinqQueryExamples#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#7)]  
  
## <a name="example"></a><span data-ttu-id="17e03-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="17e03-111">Example</span></span>  

 <span data-ttu-id="17e03-112">En el ejemplo siguiente se utiliza Max para encontrar los `Products` que tienen el precio unitario más alto en cada categoría.</span><span class="sxs-lookup"><span data-stu-id="17e03-112">The following example uses Max to find the `Products` that have the highest unit price in each category.</span></span> <span data-ttu-id="17e03-113">En este caso, los resultados se muestran por categoría.</span><span class="sxs-lookup"><span data-stu-id="17e03-113">The output then lists the results by category.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#8)]
 [!code-vb[DLinqQueryExamples#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#8)]  
  
 <span data-ttu-id="17e03-114">Si ejecuta la consulta anterior en la base de datos de ejemplo Northwind, los resultados se parecerán a los siguientes:</span><span class="sxs-lookup"><span data-stu-id="17e03-114">If you run the previous query against the Northwind sample database, your results will resemble the following:</span></span>  
  
 `1`  
  
 `Côte de Blaye`  
  
 `2`  
  
 `Vegie-spread`  
  
 `3`  
  
 `Sir Rodney's Marmalade`  
  
 `4`  
  
 `Raclette Courdavault`  
  
 `5`  
  
 `Gnocchi di nonna Alice`  
  
 `6`  
  
 `Thüringer Rostbratwurst`  
  
 `7`  
  
 `Manjimup Dried Apples`  
  
 `8`  
  
 `Carnarvon Tigers`  
  
## <a name="see-also"></a><span data-ttu-id="17e03-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="17e03-115">See also</span></span>

- [<span data-ttu-id="17e03-116">Consultas de agregado</span><span class="sxs-lookup"><span data-stu-id="17e03-116">Aggregate Queries</span></span>](aggregate-queries.md)
- [<span data-ttu-id="17e03-117">Descargar bases de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="17e03-117">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
