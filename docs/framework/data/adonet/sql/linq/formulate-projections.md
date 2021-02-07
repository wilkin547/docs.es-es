---
description: Más información acerca de cómo formular proyecciones
title: Formular proyecciones
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
ms.openlocfilehash: 591bc175426f08aa4273376e4c5efe370d2be756
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99672080"
---
# <a name="formulate-projections"></a><span data-ttu-id="3758f-103">Formular proyecciones</span><span class="sxs-lookup"><span data-stu-id="3758f-103">Formulate Projections</span></span>

<span data-ttu-id="3758f-104">En los siguientes ejemplos se muestra cómo la `select` instrucción en C# y la `Select` instrucción de Visual Basic se pueden combinar con otras características para formar proyecciones de consulta.</span><span class="sxs-lookup"><span data-stu-id="3758f-104">The following examples show how the `select` statement in C# and `Select` statement in Visual Basic can be combined with other features to form query projections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3758f-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3758f-105">Example</span></span>  

 <span data-ttu-id="3758f-106">En el ejemplo siguiente se usa la `Select` cláusula en Visual Basic ( `select` cláusula en C#) para devolver una secuencia de nombres de contacto para `Customers` .</span><span class="sxs-lookup"><span data-stu-id="3758f-106">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) to return a sequence of contact names for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## <a name="example"></a><span data-ttu-id="3758f-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3758f-107">Example</span></span>  

 <span data-ttu-id="3758f-108">En el ejemplo siguiente se usa la `Select` cláusula en Visual Basic ( `select` cláusula en C#) y los *tipos anónimos* para devolver una secuencia de nombres de contacto y números de teléfono para `Customers` .</span><span class="sxs-lookup"><span data-stu-id="3758f-108">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of contact names and telephone numbers for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## <a name="example"></a><span data-ttu-id="3758f-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3758f-109">Example</span></span>  

 <span data-ttu-id="3758f-110">En el ejemplo siguiente se usa la `Select` cláusula en Visual Basic ( `select` cláusula en C#) y los *tipos anónimos* para devolver una secuencia de nombres y números de teléfono de los empleados.</span><span class="sxs-lookup"><span data-stu-id="3758f-110">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of names and telephone numbers for employees.</span></span> <span data-ttu-id="3758f-111">Los `FirstName` `LastName` campos y se combinan en un único campo ( `Name` ) y el `HomePhone` nombre del campo `Phone` en la secuencia resultante.</span><span class="sxs-lookup"><span data-stu-id="3758f-111">The `FirstName` and `LastName` fields are combined into a single field (`Name`), and the `HomePhone` field is renamed to `Phone` in the resulting sequence.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## <a name="example"></a><span data-ttu-id="3758f-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3758f-112">Example</span></span>  

 <span data-ttu-id="3758f-113">En el ejemplo siguiente se usa la `Select` cláusula en Visual Basic ( `select` cláusula en C#) y los *tipos anónimos* para devolver una secuencia de todos los objetos `ProductID` y un valor calculado denominado `HalfPrice` .</span><span class="sxs-lookup"><span data-stu-id="3758f-113">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of all `ProductID`s and a calculated value named `HalfPrice`.</span></span> <span data-ttu-id="3758f-114">Este valor se establece en `UnitPrice` dividido entre 2.</span><span class="sxs-lookup"><span data-stu-id="3758f-114">This value is set to the `UnitPrice` divided by 2.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## <a name="example"></a><span data-ttu-id="3758f-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3758f-115">Example</span></span>  

 <span data-ttu-id="3758f-116">En el ejemplo siguiente se usa la `Select` cláusula en Visual Basic ( `select` cláusula en C#) y una *instrucción condicional* para devolver una secuencia de nombre de producto y disponibilidad del producto.</span><span class="sxs-lookup"><span data-stu-id="3758f-116">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and a *conditional statement* to return a sequence of product name and product availability.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## <a name="example"></a><span data-ttu-id="3758f-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3758f-117">Example</span></span>  

 <span data-ttu-id="3758f-118">En el ejemplo siguiente se utiliza una `Select` cláusula Visual Basic ( `select` cláusula en C#) y un *tipo conocido* (nombre) para devolver una secuencia de los nombres de los empleados.</span><span class="sxs-lookup"><span data-stu-id="3758f-118">The following example uses a Visual Basic `Select` clause (`select` clause in C#) and a *known type* (Name) to return a sequence of the names of employees.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## <a name="example"></a><span data-ttu-id="3758f-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3758f-119">Example</span></span>  

 <span data-ttu-id="3758f-120">En el ejemplo siguiente `Select` se usa y `Where` en Visual Basic ( `select` y `where` en C#) para devolver una *secuencia filtrada* de nombres de contacto para los clientes de Londres.</span><span class="sxs-lookup"><span data-stu-id="3758f-120">The following example uses `Select` and `Where` in Visual Basic (`select` and `where` in C#) to return a *filtered sequence* of contact names for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## <a name="example"></a><span data-ttu-id="3758f-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3758f-121">Example</span></span>  

 <span data-ttu-id="3758f-122">En el ejemplo siguiente se utiliza una `Select` cláusula en Visual Basic ( `select` cláusula en C#) y *tipos anónimos* para devolver un *subconjunto con forma* de los datos sobre los clientes.</span><span class="sxs-lookup"><span data-stu-id="3758f-122">The following example uses a `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a *shaped subset* of the data about customers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#64](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#64)]
 [!code-vb[DLinqQueryExamples#64](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#64)]  
  
## <a name="example"></a><span data-ttu-id="3758f-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3758f-123">Example</span></span>  

 <span data-ttu-id="3758f-124">En el ejemplo siguiente se utilizan consultas anidadas para devolver estos resultados:</span><span class="sxs-lookup"><span data-stu-id="3758f-124">The following example uses nested queries to return the following results:</span></span>  
  
- <span data-ttu-id="3758f-125">Una secuencia de todos los pedidos y sus `OrderID` correspondientes.</span><span class="sxs-lookup"><span data-stu-id="3758f-125">A sequence of all orders and their corresponding `OrderID`s.</span></span>  
  
- <span data-ttu-id="3758f-126">Una subsecuencia de los elementos del pedido que tienen descuento.</span><span class="sxs-lookup"><span data-stu-id="3758f-126">A subsequence of the items in the order for which there is a discount.</span></span>  
  
- <span data-ttu-id="3758f-127">La cantidad de dinero que se ahorra si no se incluye el envío en el precio.</span><span class="sxs-lookup"><span data-stu-id="3758f-127">The amount of money saved if the cost of shipping is not included.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#65](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#65)]
 [!code-vb[DLinqQueryExamples#65](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#65)]  
  
## <a name="see-also"></a><span data-ttu-id="3758f-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="3758f-128">See also</span></span>

- [<span data-ttu-id="3758f-129">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="3758f-129">Query Examples</span></span>](query-examples.md)
