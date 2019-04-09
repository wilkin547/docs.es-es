---
title: 'Cómo: Formular combinaciones y consultas entre productos'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8072ede-0521-4670-9bec-1778ceeb875b
ms.openlocfilehash: b0037f56947a86627ee9ea84369527aec859a0f8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180516"
---
# <a name="formulate-joins-and-cross-product-queries"></a><span data-ttu-id="49cb5-102">Cómo: Formular combinaciones y consultas entre productos</span><span class="sxs-lookup"><span data-stu-id="49cb5-102">Formulate Joins and Cross-Product Queries</span></span>
<span data-ttu-id="49cb5-103">En los ejemplos siguientes se muestra cómo combinar los resultados procedentes de varias tablas.</span><span class="sxs-lookup"><span data-stu-id="49cb5-103">The following examples show how to combine results from multiple tables.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49cb5-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="49cb5-104">Example</span></span>  
 <span data-ttu-id="49cb5-105">En el ejemplo siguiente se utiliza la navegación de clave externa en el `From` cláusula en Visual Basic (`from` cláusula en C#) para seleccionar todos los pedidos de clientes en Londres.</span><span class="sxs-lookup"><span data-stu-id="49cb5-105">The following example uses foreign key navigation in the `From` clause in Visual Basic (`from` clause in C#) to select all orders for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#47](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#47)]
 [!code-vb[DLinqQueryExamples#47](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#47)]  
  
## <a name="example"></a><span data-ttu-id="49cb5-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="49cb5-106">Example</span></span>  
 <span data-ttu-id="49cb5-107">En el ejemplo siguiente se utiliza la navegación de clave externa en el `Where` cláusula en Visual Basic (`where` cláusula en C#) para filtrar de existencias `Products` cuyo `Supplier` se encuentra en Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="49cb5-107">The following example uses foreign key navigation in the `Where` clause in Visual Basic (`where` clause in C#) to filter for out-of-stock `Products` whose `Supplier` is in the United States.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#48](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#48)]
 [!code-vb[DLinqQueryExamples#48](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#48)]  
  
## <a name="example"></a><span data-ttu-id="49cb5-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="49cb5-108">Example</span></span>  
 <span data-ttu-id="49cb5-109">En el ejemplo siguiente se utiliza la navegación de clave externa en el `From` cláusula en Visual Basic (`from` cláusula en C#) para filtrar los empleados de Seattle y mostrar sus territorios.</span><span class="sxs-lookup"><span data-stu-id="49cb5-109">The following example uses foreign key navigation in the `From` clause in Visual Basic (`from` clause in C#) to filter for employees in Seattle and to list their territories.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#49](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#49)]  
  
## <a name="example"></a><span data-ttu-id="49cb5-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="49cb5-110">Example</span></span>  
 <span data-ttu-id="49cb5-111">En el ejemplo siguiente se utiliza la navegación de clave externa en el `Select` cláusula en Visual Basic (`select` cláusula en C#) para filtrar los pares de empleados que un empleado subordinado al otro y donde ambos empleados pertenecen a la misma `City`.</span><span class="sxs-lookup"><span data-stu-id="49cb5-111">The following example uses foreign key navigation in the `Select` clause in Visual Basic (`select` clause in C#) to filter for pairs of employees where one employee reports to the other and where both employees are from the same `City`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#50](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#50)]
 [!code-vb[DLinqQueryExamples#50](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50)]  
  
## <a name="example"></a><span data-ttu-id="49cb5-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="49cb5-112">Example</span></span>  
 <span data-ttu-id="49cb5-113">El siguiente ejemplo de Visual Basic busca todos los clientes y pedidos, garantiza que los pedidos estén asociados a los clientes y garantiza que para cada cliente de esa lista, se proporciona un nombre de contacto.</span><span class="sxs-lookup"><span data-stu-id="49cb5-113">The following Visual Basic example looks for all customers and orders, makes sure that the orders are matched to customers, and guarantees that for every customer in that list, a contact name is provided.</span></span>  
  
 [!code-vb[DLinqQueryExamples#50v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50v)]  
  
## <a name="example"></a><span data-ttu-id="49cb5-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="49cb5-114">Example</span></span>  
 <span data-ttu-id="49cb5-115">En el ejemplo siguiente se combinan explícitamente dos tablas y se proyectan los resultados de ambas.</span><span class="sxs-lookup"><span data-stu-id="49cb5-115">The following example explicitly joins two tables and projects results from both tables.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#51](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#51)]
 [!code-vb[DLinqQueryExamples#51](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#51)]  
  
## <a name="example"></a><span data-ttu-id="49cb5-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="49cb5-116">Example</span></span>  
 <span data-ttu-id="49cb5-117">En el ejemplo siguiente se combinan explícitamente tres tablas y se proyectan los resultados de cada una de ellas.</span><span class="sxs-lookup"><span data-stu-id="49cb5-117">The following example explicitly joins three tables and projects results from each of them.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#52](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#52)]
 [!code-vb[DLinqQueryExamples#52](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#52)]  
  
## <a name="example"></a><span data-ttu-id="49cb5-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="49cb5-118">Example</span></span>  
 <span data-ttu-id="49cb5-119">En el ejemplo siguiente se muestra cómo lograr una `LEFT OUTER JOIN` mediante `DefaultIfEmpty()`.</span><span class="sxs-lookup"><span data-stu-id="49cb5-119">The following example shows how to achieve a `LEFT OUTER JOIN` by using `DefaultIfEmpty()`.</span></span> <span data-ttu-id="49cb5-120">El método `DefaultIfEmpty()` devuelve null cuando no hay ningún `Order` para `Employee`.</span><span class="sxs-lookup"><span data-stu-id="49cb5-120">The `DefaultIfEmpty()` method returns null when there is no `Order` for the `Employee`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#53](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#53)]
 [!code-vb[DLinqQueryExamples#53](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#53)]  
  
## <a name="example"></a><span data-ttu-id="49cb5-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="49cb5-121">Example</span></span>  
 <span data-ttu-id="49cb5-122">En el ejemplo siguiente se proyecta una expresión `let` que es el resultado de una combinación.</span><span class="sxs-lookup"><span data-stu-id="49cb5-122">The following example projects a `let` expression resulting from a join.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#54](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#54)]
 [!code-vb[DLinqQueryExamples#54](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#54)]  
  
## <a name="example"></a><span data-ttu-id="49cb5-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="49cb5-123">Example</span></span>  
 <span data-ttu-id="49cb5-124">En el ejemplo siguiente se muestra una `join` con una clave compuesta.</span><span class="sxs-lookup"><span data-stu-id="49cb5-124">The following example shows a `join` with a composite key.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#55](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#55)]
 [!code-vb[DLinqQueryExamples#55](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#55)]  
  
## <a name="example"></a><span data-ttu-id="49cb5-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="49cb5-125">Example</span></span>  
 <span data-ttu-id="49cb5-126">En el ejemplo siguiente se muestra cómo construir una `join` de tal forma que una parte acepte valores NULL y la otra no.</span><span class="sxs-lookup"><span data-stu-id="49cb5-126">The following example shows how to construct a `join` where one side is nullable and the other is not.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#56](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#56)]
 [!code-vb[DLinqQueryExamples#56](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="49cb5-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="49cb5-127">See also</span></span>

- [<span data-ttu-id="49cb5-128">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="49cb5-128">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
