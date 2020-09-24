---
title: 'Ejemplos de sintaxis de consulta basada en métodos: creación de particiones (LINQ)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a582c53f-f203-44ae-a797-d7f169a4fbb5
ms.openlocfilehash: 0ef7176ccffb7037a7d4496cc7d4da7991741d38
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147936"
---
# <a name="method-based-query-syntax-examples-partitioning-linq"></a><span data-ttu-id="345f4-102">Ejemplos de sintaxis de consulta basada en métodos: creación de particiones (LINQ)</span><span class="sxs-lookup"><span data-stu-id="345f4-102">Method-Based Query Syntax Examples: Partitioning (LINQ</span></span>

<span data-ttu-id="345f4-103">Los ejemplos de este tema muestran cómo usar los métodos <xref:System.Linq.Enumerable.Skip%2A>, <xref:System.Linq.Enumerable.SkipWhile%2A>, <xref:System.Linq.Enumerable.Take%2A> y <xref:System.Linq.Enumerable.TakeWhile%2A> para consultar un <xref:System.Data.DataSet> usando la sintaxis de expresión de consultas.</span><span class="sxs-lookup"><span data-stu-id="345f4-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Skip%2A>, <xref:System.Linq.Enumerable.SkipWhile%2A>, <xref:System.Linq.Enumerable.Take%2A>, and <xref:System.Linq.Enumerable.TakeWhile%2A> methods to query a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="345f4-104">El `FillDataSet` método utilizado en estos ejemplos se especifica en [cargar datos en un conjunto de datos](loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="345f4-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="345f4-105">Los ejemplos de este tema utilizan las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="345f4-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="345f4-106">En los ejemplos de este tema se usan las siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="345f4-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="345f4-107">Para obtener más información, vea [Cómo: crear un proyecto de LINQ to DataSet en Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="345f4-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="skip"></a><span data-ttu-id="345f4-108">Omitir</span><span class="sxs-lookup"><span data-stu-id="345f4-108">Skip</span></span>  
  
### <a name="example"></a><span data-ttu-id="345f4-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="345f4-109">Example</span></span>  

 <span data-ttu-id="345f4-110">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Skip%2A> para obtener todos los contactos menos los cinco primeros de la tabla `Contact`.</span><span class="sxs-lookup"><span data-stu-id="345f4-110">This example uses the <xref:System.Linq.Enumerable.Skip%2A> method to get all but the first five contacts of the `Contact` table.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SkipSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#skipsimple)]
 [!code-vb[DP LINQ to DataSet Examples#SkipSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#skipsimple)]  
  
### <a name="example"></a><span data-ttu-id="345f4-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="345f4-111">Example</span></span>  

 <span data-ttu-id="345f4-112">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Skip%2A> para obtener las dos primeras direcciones de Seattle.</span><span class="sxs-lookup"><span data-stu-id="345f4-112">This example uses the <xref:System.Linq.Enumerable.Skip%2A> method to get all but the first two addresses in Seattle.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SkipNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#skipnested)]
 [!code-vb[DP LINQ to DataSet Examples#SkipNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#skipnested)]  
  
## <a name="skipwhile"></a><span data-ttu-id="345f4-113">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="345f4-113">SkipWhile</span></span>  
  
### <a name="example"></a><span data-ttu-id="345f4-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="345f4-114">Example</span></span>  

 <span data-ttu-id="345f4-115">En este ejemplo se utilizan los métodos <xref:System.Linq.Enumerable.OrderBy%2A> y <xref:System.Linq.Enumerable.SkipWhile%2A> para devolver productos de la tabla `Product` con un precio de venta superior a 300,00.</span><span class="sxs-lookup"><span data-stu-id="345f4-115">This example uses <xref:System.Linq.Enumerable.OrderBy%2A> and <xref:System.Linq.Enumerable.SkipWhile%2A> methods to return products from the `Product` table with a list price greater than 300.00.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SkipWhileSimple_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#skipwhilesimple_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SkipWhileSimple_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#skipwhilesimple_mq)]  
  
## <a name="take"></a><span data-ttu-id="345f4-116">Take</span><span class="sxs-lookup"><span data-stu-id="345f4-116">Take</span></span>  
  
### <a name="example"></a><span data-ttu-id="345f4-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="345f4-117">Example</span></span>  

 <span data-ttu-id="345f4-118">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Take%2A> para obtener únicamente los cinco primeros contactos de la tabla `Contact`.</span><span class="sxs-lookup"><span data-stu-id="345f4-118">This example uses the <xref:System.Linq.Enumerable.Take%2A> method to get only the first five contacts from the `Contact` table.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#TakeSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#takesimple)]
 [!code-vb[DP LINQ to DataSet Examples#TakeSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#takesimple)]  
  
### <a name="example"></a><span data-ttu-id="345f4-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="345f4-119">Example</span></span>  

 <span data-ttu-id="345f4-120">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Take%2A> para obtener las tres primeras direcciones de Seattle.</span><span class="sxs-lookup"><span data-stu-id="345f4-120">This example uses the <xref:System.Linq.Enumerable.Take%2A> method to get the first three addresses in Seattle.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#TakeNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#takenested)]
 [!code-vb[DP LINQ to DataSet Examples#TakeNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#takenested)]  
  
## <a name="takewhile"></a><span data-ttu-id="345f4-121">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="345f4-121">TakeWhile</span></span>  
  
### <a name="example"></a><span data-ttu-id="345f4-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="345f4-122">Example</span></span>  

 <span data-ttu-id="345f4-123">En este ejemplo se utilizan los métodos <xref:System.Linq.Enumerable.OrderBy%2A> y <xref:System.Linq.Enumerable.TakeWhile%2A> para devolver de la tabla productos `Product` con un precio de venta inferior a 300,00.</span><span class="sxs-lookup"><span data-stu-id="345f4-123">This example uses <xref:System.Linq.Enumerable.OrderBy%2A> and <xref:System.Linq.Enumerable.TakeWhile%2A> to return products from the `Product` table with a list price less than 300.00.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#TakeWhileSimple_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#takewhilesimple_mq)]
 [!code-vb[DP LINQ to DataSet Examples#TakeWhileSimple_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#takewhilesimple_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="345f4-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="345f4-124">See also</span></span>

- [<span data-ttu-id="345f4-125">Cargar datos en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="345f4-125">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="345f4-126">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="345f4-126">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="345f4-127">Información general sobre operadores de consulta estándar (C#)</span><span class="sxs-lookup"><span data-stu-id="345f4-127">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="345f4-128">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="345f4-128">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
