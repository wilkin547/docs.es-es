---
title: 'Cómo: Formular combinaciones y consultas entre productos'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8072ede-0521-4670-9bec-1778ceeb875b
ms.openlocfilehash: b0037f56947a86627ee9ea84369527aec859a0f8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032609"
---
# <a name="formulate-joins-and-cross-product-queries"></a><span data-ttu-id="5bf34-102">Cómo: Formular combinaciones y consultas entre productos</span><span class="sxs-lookup"><span data-stu-id="5bf34-102">Formulate Joins and Cross-Product Queries</span></span>
<span data-ttu-id="5bf34-103">En los ejemplos siguientes se muestra cómo combinar los resultados procedentes de varias tablas.</span><span class="sxs-lookup"><span data-stu-id="5bf34-103">The following examples show how to combine results from multiple tables.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5bf34-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5bf34-104">Example</span></span>  
 <span data-ttu-id="5bf34-105">En el ejemplo siguiente se utiliza la navegación de clave externa en el `From` cláusula en Visual Basic (`from` cláusula en C#) para seleccionar todos los pedidos de clientes en Londres.</span><span class="sxs-lookup"><span data-stu-id="5bf34-105">The following example uses foreign key navigation in the `From` clause in Visual Basic (`from` clause in C#) to select all orders for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#47](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#47)]
 [!code-vb[DLinqQueryExamples#47](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#47)]  
  
## <a name="example"></a><span data-ttu-id="5bf34-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5bf34-106">Example</span></span>  
 <span data-ttu-id="5bf34-107">En el ejemplo siguiente se utiliza la navegación de clave externa en el `Where` cláusula en Visual Basic (`where` cláusula en C#) para filtrar de existencias `Products` cuyo `Supplier` se encuentra en Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="5bf34-107">The following example uses foreign key navigation in the `Where` clause in Visual Basic (`where` clause in C#) to filter for out-of-stock `Products` whose `Supplier` is in the United States.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#48](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#48)]
 [!code-vb[DLinqQueryExamples#48](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#48)]  
  
## <a name="example"></a><span data-ttu-id="5bf34-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5bf34-108">Example</span></span>  
 <span data-ttu-id="5bf34-109">En el ejemplo siguiente se utiliza la navegación de clave externa en el `From` cláusula en Visual Basic (`from` cláusula en C#) para filtrar los empleados de Seattle y mostrar sus territorios.</span><span class="sxs-lookup"><span data-stu-id="5bf34-109">The following example uses foreign key navigation in the `From` clause in Visual Basic (`from` clause in C#) to filter for employees in Seattle and to list their territories.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#49](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#49)]  
  
## <a name="example"></a><span data-ttu-id="5bf34-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5bf34-110">Example</span></span>  
 <span data-ttu-id="5bf34-111">En el ejemplo siguiente se utiliza la navegación de clave externa en el `Select` cláusula en Visual Basic (`select` cláusula en C#) para filtrar los pares de empleados que un empleado subordinado al otro y donde ambos empleados pertenecen a la misma `City`.</span><span class="sxs-lookup"><span data-stu-id="5bf34-111">The following example uses foreign key navigation in the `Select` clause in Visual Basic (`select` clause in C#) to filter for pairs of employees where one employee reports to the other and where both employees are from the same `City`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#50](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#50)]
 [!code-vb[DLinqQueryExamples#50](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50)]  
  
## <a name="example"></a><span data-ttu-id="5bf34-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5bf34-112">Example</span></span>  
 <span data-ttu-id="5bf34-113">El siguiente ejemplo de Visual Basic busca todos los clientes y pedidos, garantiza que los pedidos estén asociados a los clientes y garantiza que para cada cliente de esa lista, se proporciona un nombre de contacto.</span><span class="sxs-lookup"><span data-stu-id="5bf34-113">The following Visual Basic example looks for all customers and orders, makes sure that the orders are matched to customers, and guarantees that for every customer in that list, a contact name is provided.</span></span>  
  
 [!code-vb[DLinqQueryExamples#50v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50v)]  
  
## <a name="example"></a><span data-ttu-id="5bf34-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5bf34-114">Example</span></span>  
 <span data-ttu-id="5bf34-115">En el ejemplo siguiente se combinan explícitamente dos tablas y se proyectan los resultados de ambas.</span><span class="sxs-lookup"><span data-stu-id="5bf34-115">The following example explicitly joins two tables and projects results from both tables.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#51](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#51)]
 [!code-vb[DLinqQueryExamples#51](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#51)]  
  
## <a name="example"></a><span data-ttu-id="5bf34-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5bf34-116">Example</span></span>  
 <span data-ttu-id="5bf34-117">En el ejemplo siguiente se combinan explícitamente tres tablas y se proyectan los resultados de cada una de ellas.</span><span class="sxs-lookup"><span data-stu-id="5bf34-117">The following example explicitly joins three tables and projects results from each of them.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#52](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#52)]
 [!code-vb[DLinqQueryExamples#52](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#52)]  
  
## <a name="example"></a><span data-ttu-id="5bf34-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5bf34-118">Example</span></span>  
 <span data-ttu-id="5bf34-119">En el ejemplo siguiente se muestra cómo lograr una `LEFT OUTER JOIN` mediante `DefaultIfEmpty()`.</span><span class="sxs-lookup"><span data-stu-id="5bf34-119">The following example shows how to achieve a `LEFT OUTER JOIN` by using `DefaultIfEmpty()`.</span></span> <span data-ttu-id="5bf34-120">El método `DefaultIfEmpty()` devuelve null cuando no hay ningún `Order` para `Employee`.</span><span class="sxs-lookup"><span data-stu-id="5bf34-120">The `DefaultIfEmpty()` method returns null when there is no `Order` for the `Employee`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#53](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#53)]
 [!code-vb[DLinqQueryExamples#53](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#53)]  
  
## <a name="example"></a><span data-ttu-id="5bf34-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5bf34-121">Example</span></span>  
 <span data-ttu-id="5bf34-122">En el ejemplo siguiente se proyecta una expresión `let` que es el resultado de una combinación.</span><span class="sxs-lookup"><span data-stu-id="5bf34-122">The following example projects a `let` expression resulting from a join.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#54](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#54)]
 [!code-vb[DLinqQueryExamples#54](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#54)]  
  
## <a name="example"></a><span data-ttu-id="5bf34-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5bf34-123">Example</span></span>  
 <span data-ttu-id="5bf34-124">En el ejemplo siguiente se muestra una `join` con una clave compuesta.</span><span class="sxs-lookup"><span data-stu-id="5bf34-124">The following example shows a `join` with a composite key.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#55](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#55)]
 [!code-vb[DLinqQueryExamples#55](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#55)]  
  
## <a name="example"></a><span data-ttu-id="5bf34-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5bf34-125">Example</span></span>  
 <span data-ttu-id="5bf34-126">En el ejemplo siguiente se muestra cómo construir una `join` de tal forma que una parte acepte valores NULL y la otra no.</span><span class="sxs-lookup"><span data-stu-id="5bf34-126">The following example shows how to construct a `join` where one side is nullable and the other is not.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#56](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#56)]
 [!code-vb[DLinqQueryExamples#56](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="5bf34-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="5bf34-127">See also</span></span>

- [<span data-ttu-id="5bf34-128">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="5bf34-128">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
