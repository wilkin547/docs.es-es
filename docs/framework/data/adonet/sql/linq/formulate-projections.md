---
title: Formular proyecciones
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: bb22ddd4882d9885c55301a6fdc6a0eb336b49af
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="formulate-projections"></a><span data-ttu-id="10f60-102">Formular proyecciones</span><span class="sxs-lookup"><span data-stu-id="10f60-102">Formulate Projections</span></span>
<span data-ttu-id="10f60-103">En los ejemplos siguientes se muestra cómo la instrucción `select` en C# y la instrucción `Select` en [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] se puede combinar con otras características para formar proyecciones de consulta.</span><span class="sxs-lookup"><span data-stu-id="10f60-103">The following examples show how the `select` statement in C# and `Select` statement in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] can be combined with other features to form query projections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10f60-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="10f60-104">Example</span></span>  
 <span data-ttu-id="10f60-105">En el ejemplo siguiente se usa el `Select` cláusula en [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` cláusula en C#) para devolver una secuencia de nombres de contacto para `Customers`.</span><span class="sxs-lookup"><span data-stu-id="10f60-105">The following example uses the `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) to return a sequence of contact names for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## <a name="example"></a><span data-ttu-id="10f60-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="10f60-106">Example</span></span>  
 <span data-ttu-id="10f60-107">En el ejemplo siguiente se usa el `Select` cláusula en [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` cláusula en C#) y *tipos anónimos* para devolver una secuencia de nombres de contacto y números de teléfono de `Customers`.</span><span class="sxs-lookup"><span data-stu-id="10f60-107">The following example uses the `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) and *anonymous types* to return a sequence of contact names and telephone numbers for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## <a name="example"></a><span data-ttu-id="10f60-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="10f60-108">Example</span></span>  
 <span data-ttu-id="10f60-109">En el ejemplo siguiente se usa el `Select` cláusula en [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` cláusula en C#) y *tipos anónimos* para devolver una secuencia de nombres y números de teléfono de los empleados.</span><span class="sxs-lookup"><span data-stu-id="10f60-109">The following example uses the `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) and *anonymous types* to return a sequence of names and telephone numbers for employees.</span></span> <span data-ttu-id="10f60-110">El `FirstName` y `LastName` campos se combinan en un único campo (`Name`) y el `HomePhone` campo cambia a `Phone` en la secuencia resultante.</span><span class="sxs-lookup"><span data-stu-id="10f60-110">The `FirstName` and `LastName` fields are combined into a single field (`Name`), and the `HomePhone` field is renamed to `Phone` in the resulting sequence.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## <a name="example"></a><span data-ttu-id="10f60-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="10f60-111">Example</span></span>  
 <span data-ttu-id="10f60-112">En el ejemplo siguiente se usa el `Select` cláusula en [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` cláusula en C#) y *tipos anónimos* para devolver una secuencia de todos los `ProductID`s y un valor calculado denominado `HalfPrice`.</span><span class="sxs-lookup"><span data-stu-id="10f60-112">The following example uses the `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) and *anonymous types* to return a sequence of all `ProductID`s and a calculated value named `HalfPrice`.</span></span> <span data-ttu-id="10f60-113">Este valor se establece en `UnitPrice` dividido entre 2.</span><span class="sxs-lookup"><span data-stu-id="10f60-113">This value is set to the `UnitPrice` divided by 2.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## <a name="example"></a><span data-ttu-id="10f60-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="10f60-114">Example</span></span>  
 <span data-ttu-id="10f60-115">En el ejemplo siguiente se usa el `Select` cláusula en [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` cláusula en C#) y un *instrucción condicional* para devolver una secuencia de nombre de producto y disponibilidad de los productos.</span><span class="sxs-lookup"><span data-stu-id="10f60-115">The following example uses the `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) and a *conditional statement* to return a sequence of product name and product availability.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## <a name="example"></a><span data-ttu-id="10f60-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="10f60-116">Example</span></span>  
 <span data-ttu-id="10f60-117">En el ejemplo siguiente se usa un [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] `Select` cláusula (`select` cláusula en C#) y un *tipo conocido* (nombre) para devolver una secuencia de los nombres de los empleados.</span><span class="sxs-lookup"><span data-stu-id="10f60-117">The following example uses a [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] `Select` clause (`select` clause in C#) and a *known type* (Name) to return a sequence of the names of employees.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## <a name="example"></a><span data-ttu-id="10f60-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="10f60-118">Example</span></span>  
 <span data-ttu-id="10f60-119">En el ejemplo siguiente se utiliza `Select` y `Where` en [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` y `where` en C#) para devolver un *secuencia filtrada* de nombres de contacto para los clientes de Londres.</span><span class="sxs-lookup"><span data-stu-id="10f60-119">The following example uses `Select` and `Where` in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` and `where` in C#) to return a *filtered sequence* of contact names for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## <a name="example"></a><span data-ttu-id="10f60-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="10f60-120">Example</span></span>  
 <span data-ttu-id="10f60-121">En el ejemplo siguiente se usa un `Select` cláusula en [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` cláusula en C#) y *tipos anónimos* para devolver un *subconjunto con forma* de los datos sobre los clientes.</span><span class="sxs-lookup"><span data-stu-id="10f60-121">The following example uses a `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) and *anonymous types* to return a *shaped subset* of the data about customers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#64](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#64)]
 [!code-vb[DLinqQueryExamples#64](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#64)]  
  
## <a name="example"></a><span data-ttu-id="10f60-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="10f60-122">Example</span></span>  
 <span data-ttu-id="10f60-123">En el ejemplo siguiente se utilizan consultas anidadas para devolver estos resultados:</span><span class="sxs-lookup"><span data-stu-id="10f60-123">The following example uses nested queries to return the following results:</span></span>  
  
-   <span data-ttu-id="10f60-124">Una secuencia de todos los pedidos y sus `OrderID` correspondientes.</span><span class="sxs-lookup"><span data-stu-id="10f60-124">A sequence of all orders and their corresponding `OrderID`s.</span></span>  
  
-   <span data-ttu-id="10f60-125">Una subsecuencia de los elementos del pedido que tienen descuento.</span><span class="sxs-lookup"><span data-stu-id="10f60-125">A subsequence of the items in the order for which there is a discount.</span></span>  
  
-   <span data-ttu-id="10f60-126">La cantidad de dinero que se ahorra si no se incluye el envío en el precio.</span><span class="sxs-lookup"><span data-stu-id="10f60-126">The amount of money saved if the cost of shipping is not included.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#65](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#65)]
 [!code-vb[DLinqQueryExamples#65](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#65)]  
  
## <a name="see-also"></a><span data-ttu-id="10f60-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="10f60-127">See Also</span></span>  
 [<span data-ttu-id="10f60-128">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="10f60-128">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
