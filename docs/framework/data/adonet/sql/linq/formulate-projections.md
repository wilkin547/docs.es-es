---
title: Formular proyecciones
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
ms.openlocfilehash: 0dfd5d951750de2ab918c51dd9f4f2deeb8a6318
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793819"
---
# <a name="formulate-projections"></a><span data-ttu-id="c5219-102">Formular proyecciones</span><span class="sxs-lookup"><span data-stu-id="c5219-102">Formulate Projections</span></span>
<span data-ttu-id="c5219-103">En los siguientes ejemplos se muestra `select` cómo la C# instrucción `Select` in y la instrucción de Visual Basic pueden combinarse con otras características para formar proyecciones de consulta.</span><span class="sxs-lookup"><span data-stu-id="c5219-103">The following examples show how the `select` statement in C# and `Select` statement in Visual Basic can be combined with other features to form query projections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5219-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5219-104">Example</span></span>  
 <span data-ttu-id="c5219-105">En el ejemplo siguiente se `Select` usa la cláusula en`select` Visual Basic ( C#cláusula en) para devolver una secuencia de nombres `Customers`de contacto para.</span><span class="sxs-lookup"><span data-stu-id="c5219-105">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) to return a sequence of contact names for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## <a name="example"></a><span data-ttu-id="c5219-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5219-106">Example</span></span>  
 <span data-ttu-id="c5219-107">En el ejemplo siguiente se `Select` usa la cláusula en`select` Visual Basic ( C#cláusula en) y los *tipos anónimos* para devolver una secuencia de nombres de `Customers`contacto y números de teléfono para.</span><span class="sxs-lookup"><span data-stu-id="c5219-107">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of contact names and telephone numbers for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## <a name="example"></a><span data-ttu-id="c5219-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5219-108">Example</span></span>  
 <span data-ttu-id="c5219-109">En el ejemplo siguiente se `Select` usa la cláusula en`select` Visual Basic ( C#cláusula en) y los *tipos anónimos* para devolver una secuencia de nombres y números de teléfono de los empleados.</span><span class="sxs-lookup"><span data-stu-id="c5219-109">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of names and telephone numbers for employees.</span></span> <span data-ttu-id="c5219-110">Los `FirstName` campos `LastName` y se combinan en un único campo (`Name` `Phone` ) y el nombre `HomePhone` del campo en la secuencia resultante.</span><span class="sxs-lookup"><span data-stu-id="c5219-110">The `FirstName` and `LastName` fields are combined into a single field (`Name`), and the `HomePhone` field is renamed to `Phone` in the resulting sequence.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## <a name="example"></a><span data-ttu-id="c5219-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5219-111">Example</span></span>  
 <span data-ttu-id="c5219-112">En el ejemplo siguiente se `Select` usa la cláusula en`select` Visual Basic ( C#cláusula en) y los *tipos anónimos* para devolver `ProductID`una secuencia de todos los objetos `HalfPrice`y un valor calculado denominado.</span><span class="sxs-lookup"><span data-stu-id="c5219-112">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of all `ProductID`s and a calculated value named `HalfPrice`.</span></span> <span data-ttu-id="c5219-113">Este valor se establece en `UnitPrice` dividido entre 2.</span><span class="sxs-lookup"><span data-stu-id="c5219-113">This value is set to the `UnitPrice` divided by 2.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## <a name="example"></a><span data-ttu-id="c5219-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5219-114">Example</span></span>  
 <span data-ttu-id="c5219-115">En el ejemplo siguiente se `Select` usa la cláusula en`select` Visual Basic ( C#cláusula en) y una *instrucción condicional* para devolver una secuencia de nombre de producto y disponibilidad del producto.</span><span class="sxs-lookup"><span data-stu-id="c5219-115">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and a *conditional statement* to return a sequence of product name and product availability.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## <a name="example"></a><span data-ttu-id="c5219-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5219-116">Example</span></span>  
 <span data-ttu-id="c5219-117">En el ejemplo siguiente se utiliza `Select` una cláusula`select` de Visual Basic C#(cláusula en) y un *tipo conocido* (nombre) para devolver una secuencia de los nombres de los empleados.</span><span class="sxs-lookup"><span data-stu-id="c5219-117">The following example uses a Visual Basic `Select` clause (`select` clause in C#) and a *known type* (Name) to return a sequence of the names of employees.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## <a name="example"></a><span data-ttu-id="c5219-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5219-118">Example</span></span>  
 <span data-ttu-id="c5219-119">En el ejemplo siguiente `Select` se `Where` usa y en`select` Visual Basic `where` ( C#y en) para devolver una *secuencia filtrada* de nombres de contacto para los clientes de Londres.</span><span class="sxs-lookup"><span data-stu-id="c5219-119">The following example uses `Select` and `Where` in Visual Basic (`select` and `where` in C#) to return a *filtered sequence* of contact names for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## <a name="example"></a><span data-ttu-id="c5219-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5219-120">Example</span></span>  
 <span data-ttu-id="c5219-121">En el ejemplo siguiente se `Select` utiliza una cláusula en`select` Visual Basic ( C#cláusula en) y los *tipos anónimos* para devolver un *subconjunto con forma* de los datos sobre los clientes.</span><span class="sxs-lookup"><span data-stu-id="c5219-121">The following example uses a `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a *shaped subset* of the data about customers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#64](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#64)]
 [!code-vb[DLinqQueryExamples#64](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#64)]  
  
## <a name="example"></a><span data-ttu-id="c5219-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5219-122">Example</span></span>  
 <span data-ttu-id="c5219-123">En el ejemplo siguiente se utilizan consultas anidadas para devolver estos resultados:</span><span class="sxs-lookup"><span data-stu-id="c5219-123">The following example uses nested queries to return the following results:</span></span>  
  
- <span data-ttu-id="c5219-124">Una secuencia de todos los pedidos y sus `OrderID` correspondientes.</span><span class="sxs-lookup"><span data-stu-id="c5219-124">A sequence of all orders and their corresponding `OrderID`s.</span></span>  
  
- <span data-ttu-id="c5219-125">Una subsecuencia de los elementos del pedido que tienen descuento.</span><span class="sxs-lookup"><span data-stu-id="c5219-125">A subsequence of the items in the order for which there is a discount.</span></span>  
  
- <span data-ttu-id="c5219-126">La cantidad de dinero que se ahorra si no se incluye el envío en el precio.</span><span class="sxs-lookup"><span data-stu-id="c5219-126">The amount of money saved if the cost of shipping is not included.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#65](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#65)]
 [!code-vb[DLinqQueryExamples#65](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#65)]  
  
## <a name="see-also"></a><span data-ttu-id="c5219-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5219-127">See also</span></span>

- [<span data-ttu-id="c5219-128">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="c5219-128">Query Examples</span></span>](query-examples.md)
