---
description: 'Más información sobre: devolver el valor medio de una secuencia numérica'
title: Devolver el valor medio de una secuencia numérica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ee3b8673-a2e7-4b2d-9b5c-4972ff9e665d
ms.openlocfilehash: 4e0415c9ef981364fc3d6481ed6455f132e84932
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99663071"
---
# <a name="return-the-average-value-from-a-numeric-sequence"></a><span data-ttu-id="c663c-103">Devolver el valor medio de una secuencia numérica</span><span class="sxs-lookup"><span data-stu-id="c663c-103">Return the Average Value From a Numeric Sequence</span></span>

<span data-ttu-id="c663c-104">El operador <xref:System.Linq.Enumerable.Average%2A> calcula el promedio de una secuencia de valores numéricos.</span><span class="sxs-lookup"><span data-stu-id="c663c-104">The <xref:System.Linq.Enumerable.Average%2A> operator computes the average of a sequence of numeric values.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c663c-105">La conversión de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] de valores enteros en `Average` se calcula como un entero, no como double.</span><span class="sxs-lookup"><span data-stu-id="c663c-105">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translation of `Average` of integer values is computed as an integer, not as a double.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c663c-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c663c-106">Example</span></span>  

 <span data-ttu-id="c663c-107">En el ejemplo siguiente se devuelve el promedio de los valores `Freight` de la tabla `Orders`.</span><span class="sxs-lookup"><span data-stu-id="c663c-107">The following example returns the average of `Freight` values in the `Orders` table.</span></span>  
  
 <span data-ttu-id="c663c-108">Los resultados de la base de datos de ejemplo Northwind serían `78.2442`.</span><span class="sxs-lookup"><span data-stu-id="c663c-108">Results from the sample Northwind database would be `78.2442`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#1)]
 [!code-vb[DLinqQueryExamples#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="c663c-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c663c-109">Example</span></span>  

 <span data-ttu-id="c663c-110">En el ejemplo siguiente se devuelve el promedio de precio unitario de todos los `Products` de la tabla `Products`.</span><span class="sxs-lookup"><span data-stu-id="c663c-110">The following example returns the average of the unit price of all `Products` in the `Products` table.</span></span>  
  
 <span data-ttu-id="c663c-111">Los resultados de la base de datos de ejemplo Northwind serían `28.8663`.</span><span class="sxs-lookup"><span data-stu-id="c663c-111">Results from the sample Northwind database would be `28.8663`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#2)]
 [!code-vb[DLinqQueryExamples#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="c663c-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c663c-112">Example</span></span>  

 <span data-ttu-id="c663c-113">En el ejemplo siguiente se utiliza al operador `Average` para buscar `Products` cuyo precio unitario es más alto que el precio unitario promedio de la categoría a la que pertenece.</span><span class="sxs-lookup"><span data-stu-id="c663c-113">The following example uses the `Average` operator to find those `Products` whose unit price is higher than the average unit price of the category it belongs to.</span></span> <span data-ttu-id="c663c-114">A continuación, el ejemplo muestra los resultados en grupos.</span><span class="sxs-lookup"><span data-stu-id="c663c-114">The example then displays the results in groups.</span></span>  
  
 <span data-ttu-id="c663c-115">Observe que este ejemplo requiere el uso de la palabra clave `var` en C#, porque el tipo de valor devuelto es anónimo.</span><span class="sxs-lookup"><span data-stu-id="c663c-115">Note that this example requires the use of the `var` keyword in C#, because the return type is anonymous.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#3)]
 [!code-vb[DLinqQueryExamples#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#3)]  
  
 <span data-ttu-id="c663c-116">Si ejecuta esta consulta en la base de datos de ejemplo Northwind, los resultados deberían parecerse a los siguientes:</span><span class="sxs-lookup"><span data-stu-id="c663c-116">If you run this query against the Northwind sample database, the results should resemble of the following:</span></span>  
  
 `1`  
  
 `Côte de Blaye`  
  
 `Ipoh Coffee`  
  
 `2`  
  
 `Grandma's Boysenberry Spread`  
  
 `Northwoods Cranberry Sauce`  
  
 `Sirop d'érable`  
  
 `Vegie-spread`  
  
 `3`  
  
 `Sir Rodney's Marmalade`  
  
 `Gumbär Gummibärchen`  
  
 `Schoggi Schokolade`  
  
 `Tarte au sucre`  
  
 `4`  
  
 `Queso Manchego La Pastora`  
  
 `Mascarpone Fabioli`  
  
 `Raclette Courdavault`  
  
 `Camembert Pierrot`  
  
 `Gudbrandsdalsost`  
  
 `Mozzarella di Giovanni`  
  
 `5`  
  
 `Gustaf's Knäckebröd`  
  
 `Gnocchi di nonna Alice`  
  
 `Wimmers gute Semmelknödel`  
  
 `6`  
  
 `Mishi Kobe Niku`  
  
 `Thüringer Rostbratwurst`  
  
 `7`  
  
 `Rössle Sauerkraut`  
  
 `Manjimup Dried Apples`  
  
 `8`  
  
 `Ikura`  
  
 `Carnarvon Tigers`  
  
 `Nord-Ost Matjeshering`  
  
 `Gravad lax`  
  
## <a name="see-also"></a><span data-ttu-id="c663c-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="c663c-117">See also</span></span>

- [<span data-ttu-id="c663c-118">Consultas de agregado</span><span class="sxs-lookup"><span data-stu-id="c663c-118">Aggregate Queries</span></span>](aggregate-queries.md)
