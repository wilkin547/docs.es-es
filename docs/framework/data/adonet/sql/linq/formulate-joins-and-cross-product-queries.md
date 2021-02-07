---
description: 'Más información sobre: formular combinaciones y consultas entre productos'
title: 'Cómo: Formular combinaciones y consultas entre productos'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8072ede-0521-4670-9bec-1778ceeb875b
ms.openlocfilehash: 1adee3576d7b30d6ec9a9c4e920befcd21dd9e85
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739123"
---
# <a name="formulate-joins-and-cross-product-queries"></a><span data-ttu-id="d5a3c-103">Cómo: Formular combinaciones y consultas entre productos</span><span class="sxs-lookup"><span data-stu-id="d5a3c-103">Formulate Joins and Cross-Product Queries</span></span>

<span data-ttu-id="d5a3c-104">En los ejemplos siguientes se muestra cómo combinar los resultados procedentes de varias tablas.</span><span class="sxs-lookup"><span data-stu-id="d5a3c-104">The following examples show how to combine results from multiple tables.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5a3c-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d5a3c-105">Example</span></span>  

 <span data-ttu-id="d5a3c-106">En el ejemplo siguiente se utiliza la navegación de clave externa en la `From` cláusula de Visual Basic ( `from` cláusula en C#) para seleccionar todos los pedidos de los clientes de Londres.</span><span class="sxs-lookup"><span data-stu-id="d5a3c-106">The following example uses foreign key navigation in the `From` clause in Visual Basic (`from` clause in C#) to select all orders for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#47](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#47)]
 [!code-vb[DLinqQueryExamples#47](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#47)]  
  
## <a name="example"></a><span data-ttu-id="d5a3c-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d5a3c-107">Example</span></span>  

 <span data-ttu-id="d5a3c-108">En el ejemplo siguiente se usa la navegación de clave externa en la `Where` cláusula de Visual Basic ( `where` cláusula en C#) para filtrar por fuera de existencias, `Products` cuyo `Supplier` está en el Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="d5a3c-108">The following example uses foreign key navigation in the `Where` clause in Visual Basic (`where` clause in C#) to filter for out-of-stock `Products` whose `Supplier` is in the United States.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#48](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#48)]
 [!code-vb[DLinqQueryExamples#48](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#48)]  
  
## <a name="example"></a><span data-ttu-id="d5a3c-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d5a3c-109">Example</span></span>  

 <span data-ttu-id="d5a3c-110">En el ejemplo siguiente se usa la navegación de clave externa en la `From` cláusula de Visual Basic ( `from` cláusula en C#) para filtrar los empleados de Seattle y mostrar sus territorios.</span><span class="sxs-lookup"><span data-stu-id="d5a3c-110">The following example uses foreign key navigation in the `From` clause in Visual Basic (`from` clause in C#) to filter for employees in Seattle and to list their territories.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#49](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#49)]  
  
## <a name="example"></a><span data-ttu-id="d5a3c-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d5a3c-111">Example</span></span>  

 <span data-ttu-id="d5a3c-112">En el ejemplo siguiente se usa la navegación de clave externa en la `Select` cláusula de Visual Basic ( `select` cláusula en C#) para filtrar los pares de empleados en los que un empleado se comunica con el otro y donde ambos empleados son de la misma `City` .</span><span class="sxs-lookup"><span data-stu-id="d5a3c-112">The following example uses foreign key navigation in the `Select` clause in Visual Basic (`select` clause in C#) to filter for pairs of employees where one employee reports to the other and where both employees are from the same `City`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#50](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#50)]
 [!code-vb[DLinqQueryExamples#50](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50)]  
  
## <a name="example"></a><span data-ttu-id="d5a3c-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d5a3c-113">Example</span></span>  

 <span data-ttu-id="d5a3c-114">En el siguiente Visual Basic ejemplo se buscan todos los clientes y pedidos, se asegura de que los pedidos coinciden con los clientes y se garantiza que, para cada cliente de esa lista, se proporciona un nombre de contacto.</span><span class="sxs-lookup"><span data-stu-id="d5a3c-114">The following Visual Basic example looks for all customers and orders, makes sure that the orders are matched to customers, and guarantees that for every customer in that list, a contact name is provided.</span></span>  
  
 [!code-vb[DLinqQueryExamples#50v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50v)]  
  
## <a name="example"></a><span data-ttu-id="d5a3c-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d5a3c-115">Example</span></span>  

 <span data-ttu-id="d5a3c-116">En el ejemplo siguiente se combinan explícitamente dos tablas y se proyectan los resultados de ambas.</span><span class="sxs-lookup"><span data-stu-id="d5a3c-116">The following example explicitly joins two tables and projects results from both tables.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#51](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#51)]
 [!code-vb[DLinqQueryExamples#51](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#51)]  
  
## <a name="example"></a><span data-ttu-id="d5a3c-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d5a3c-117">Example</span></span>  

 <span data-ttu-id="d5a3c-118">En el ejemplo siguiente se combinan explícitamente tres tablas y se proyectan los resultados de cada una de ellas.</span><span class="sxs-lookup"><span data-stu-id="d5a3c-118">The following example explicitly joins three tables and projects results from each of them.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#52](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#52)]
 [!code-vb[DLinqQueryExamples#52](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#52)]  
  
## <a name="example"></a><span data-ttu-id="d5a3c-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d5a3c-119">Example</span></span>  

 <span data-ttu-id="d5a3c-120">En el ejemplo siguiente se muestra cómo lograr una `LEFT OUTER JOIN` mediante `DefaultIfEmpty()`.</span><span class="sxs-lookup"><span data-stu-id="d5a3c-120">The following example shows how to achieve a `LEFT OUTER JOIN` by using `DefaultIfEmpty()`.</span></span> <span data-ttu-id="d5a3c-121">El método `DefaultIfEmpty()` devuelve null cuando no hay ningún `Order` para `Employee`.</span><span class="sxs-lookup"><span data-stu-id="d5a3c-121">The `DefaultIfEmpty()` method returns null when there is no `Order` for the `Employee`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#53](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#53)]
 [!code-vb[DLinqQueryExamples#53](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#53)]  
  
## <a name="example"></a><span data-ttu-id="d5a3c-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d5a3c-122">Example</span></span>  

 <span data-ttu-id="d5a3c-123">En el ejemplo siguiente se proyecta una expresión `let` que es el resultado de una combinación.</span><span class="sxs-lookup"><span data-stu-id="d5a3c-123">The following example projects a `let` expression resulting from a join.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#54](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#54)]
 [!code-vb[DLinqQueryExamples#54](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#54)]  
  
## <a name="example"></a><span data-ttu-id="d5a3c-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d5a3c-124">Example</span></span>  

 <span data-ttu-id="d5a3c-125">En el ejemplo siguiente se muestra una `join` con una clave compuesta.</span><span class="sxs-lookup"><span data-stu-id="d5a3c-125">The following example shows a `join` with a composite key.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#55](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#55)]
 [!code-vb[DLinqQueryExamples#55](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#55)]  
  
## <a name="example"></a><span data-ttu-id="d5a3c-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d5a3c-126">Example</span></span>  

 <span data-ttu-id="d5a3c-127">En el ejemplo siguiente se muestra cómo construir una `join` de tal forma que una parte acepte valores NULL y la otra no.</span><span class="sxs-lookup"><span data-stu-id="d5a3c-127">The following example shows how to construct a `join` where one side is nullable and the other is not.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#56](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#56)]
 [!code-vb[DLinqQueryExamples#56](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="d5a3c-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5a3c-128">See also</span></span>

- [<span data-ttu-id="d5a3c-129">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="d5a3c-129">Query Examples</span></span>](query-examples.md)
