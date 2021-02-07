---
description: 'Más información sobre: ejemplos de sintaxis de expresiones de consulta: proyección (LINQ to DataSet)'
title: 'Ejemplos de sintaxis de expresiones de consulta: Proyección (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 48c9f5ed-76bf-4228-ab10-5217bbb295a3
ms.openlocfilehash: 710426108304d5b3fa38004fb37d234ed206733c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99663526"
---
# <a name="query-expression-syntax-examples-projection--linq-to-dataset"></a><span data-ttu-id="2b531-103">Ejemplos de sintaxis de expresiones de consulta: Proyección (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="2b531-103">Query Expression Syntax Examples: Projection  (LINQ to DataSet)</span></span>

<span data-ttu-id="2b531-104">Los ejemplos de este tema muestran cómo usar los métodos <xref:System.Linq.Enumerable.Select%2A> y <xref:System.Linq.Enumerable.SelectMany%2A> para consultar un <xref:System.Data.DataSet> usando la sintaxis de expresión de consultas.</span><span class="sxs-lookup"><span data-stu-id="2b531-104">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Select%2A> and <xref:System.Linq.Enumerable.SelectMany%2A> methods to query a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="2b531-105">El `FillDataSet` método utilizado en estos ejemplos se especifica en [cargar datos en un conjunto de datos](loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="2b531-105">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="2b531-106">Los ejemplos de este tema utilizan las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="2b531-106">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="2b531-107">En los ejemplos de este tema se usan las siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="2b531-107">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="2b531-108">Para obtener más información, vea [Cómo: crear un proyecto de LINQ to DataSet en Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="2b531-108">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="select"></a><span data-ttu-id="2b531-109">Seleccionar</span><span class="sxs-lookup"><span data-stu-id="2b531-109">Select</span></span>  
  
### <a name="example"></a><span data-ttu-id="2b531-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2b531-110">Example</span></span>  

 <span data-ttu-id="2b531-111">Este ejemplo utiliza <xref:System.Linq.Enumerable.Select%2A> para devolver todas las filas de la tabla `Product` y mostrar los nombres de producto.</span><span class="sxs-lookup"><span data-stu-id="2b531-111">This example uses the <xref:System.Linq.Enumerable.Select%2A> method to return all the rows from the `Product` table and display the product names.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectSimple1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectsimple1)]
 [!code-vb[DP LINQ to DataSet Examples#SelectSimple1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectsimple1)]  
  
### <a name="example"></a><span data-ttu-id="2b531-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2b531-112">Example</span></span>  

 <span data-ttu-id="2b531-113">Este ejemplo utiliza <xref:System.Linq.Enumerable.Select%2A> para devolver una secuencia de nombres de producto solamente.</span><span class="sxs-lookup"><span data-stu-id="2b531-113">This example uses <xref:System.Linq.Enumerable.Select%2A> to return a sequence of only product names.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectSimple2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectsimple2)]
 [!code-vb[DP LINQ to DataSet Examples#SelectSimple2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectsimple2)]  
  
## <a name="selectmany"></a><span data-ttu-id="2b531-114">SelectMany</span><span class="sxs-lookup"><span data-stu-id="2b531-114">SelectMany</span></span>  
  
### <a name="example"></a><span data-ttu-id="2b531-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2b531-115">Example</span></span>  

 <span data-ttu-id="2b531-116">En este ejemplo se utiliza `From …, …` (el equivalente del método <xref:System.Linq.Enumerable.SelectMany%2A>) para seleccionar todos los pedidos en los que `TotalDue` es inferior a 500,00.</span><span class="sxs-lookup"><span data-stu-id="2b531-116">This example uses `From …, …` (the equivalent of the <xref:System.Linq.Enumerable.SelectMany%2A> method) to select all orders where `TotalDue` is less than 500.00.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectManyCompoundFrom](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectmanycompoundfrom)]
 [!code-vb[DP LINQ to DataSet Examples#SelectManyCompoundFrom](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectmanycompoundfrom)]  
  
### <a name="example"></a><span data-ttu-id="2b531-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2b531-117">Example</span></span>  

 <span data-ttu-id="2b531-118">En este ejemplo se utiliza `From …, …` (el equivalente del método <xref:System.Linq.Enumerable.SelectMany%2A>) para seleccionar todos los pedidos efectuados a partir del 1 de octubre.</span><span class="sxs-lookup"><span data-stu-id="2b531-118">This example uses `From …, …` (the equivalent of the <xref:System.Linq.Enumerable.SelectMany%2A> method) to select all orders where the order was made on October 1, 2002 or later.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectManyCompoundFrom2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectmanycompoundfrom2)]
 [!code-vb[DP LINQ to DataSet Examples#SelectManyCompoundFrom2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectmanycompoundfrom2)]  
  
### <a name="example"></a><span data-ttu-id="2b531-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2b531-119">Example</span></span>  

 <span data-ttu-id="2b531-120">En este ejemplo se utiliza `From …, …` (el equivalente al método <xref:System.Linq.Enumerable.SelectMany%2A>) para seleccionar todos los pedidos en los que el total del pedido es superior a 10.000,00 y utiliza la asignación `From` para evitar que se solicite dos veces el total.</span><span class="sxs-lookup"><span data-stu-id="2b531-120">This example uses a `From …, …` (the equivalent of the <xref:System.Linq.Enumerable.SelectMany%2A> method) to select all orders where the order total is greater than 10000.00 and uses `From` assignment to avoid requesting the total twice.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectManyFromAssignment](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectmanyfromassignment)]
 [!code-vb[DP LINQ to DataSet Examples#SelectManyFromAssignment](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectmanyfromassignment)]  
  
## <a name="see-also"></a><span data-ttu-id="2b531-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b531-121">See also</span></span>

- [<span data-ttu-id="2b531-122">Cargar datos en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="2b531-122">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="2b531-123">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="2b531-123">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="2b531-124">Información general sobre operadores de consulta estándar (C#)</span><span class="sxs-lookup"><span data-stu-id="2b531-124">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="2b531-125">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2b531-125">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
