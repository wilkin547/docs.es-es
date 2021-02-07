---
description: 'Más información sobre: ejemplos de sintaxis de expresiones de consulta: restricción (LINQ to DataSet)'
title: 'Ejemplos de sintaxis de expresiones de consulta: Restricción (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1daf42c2-c9f4-4cda-b291-7641b9c6d3fe
ms.openlocfilehash: 06ffaa782a02191be4c9568587824ec1767f1249
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99695988"
---
# <a name="query-expression-syntax-examples-restriction-linq-to-dataset"></a><span data-ttu-id="3d529-103">Ejemplos de sintaxis de expresiones de consulta: Restricción (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="3d529-103">Query Expression Syntax Examples: Restriction (LINQ to DataSet)</span></span>

<span data-ttu-id="3d529-104">Los ejemplos de este tema muestran cómo utilizar el método <xref:System.Linq.Enumerable.Where%2A> para consultar <xref:System.Data.DataSet> utilizando sintaxis de expresión de consultas.</span><span class="sxs-lookup"><span data-stu-id="3d529-104">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Where%2A> method to query a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="3d529-105">El `FillDataSet` método utilizado en estos ejemplos se especifica en [cargar datos en un conjunto de datos](loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="3d529-105">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="3d529-106">Los ejemplos de este tema utilizan las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="3d529-106">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="3d529-107">En los ejemplos de este tema se usan las siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="3d529-107">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
[!code-csharp[DP LINQ to DataSetExamples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
  
 <span data-ttu-id="3d529-108">Para obtener más información, vea [Cómo: crear un proyecto de LINQ to DataSet en Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="3d529-108">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="where"></a><span data-ttu-id="3d529-109">Where</span><span class="sxs-lookup"><span data-stu-id="3d529-109">Where</span></span>  
  
### <a name="example"></a><span data-ttu-id="3d529-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3d529-110">Example</span></span>  

 <span data-ttu-id="3d529-111">Este ejemplo devuelve todos los pedidos en línea.</span><span class="sxs-lookup"><span data-stu-id="3d529-111">This example returns all online orders.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where1)]  
 [!code-vb[DP LINQ to DataSet Examples#Where1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where1)]
  
### <a name="example"></a><span data-ttu-id="3d529-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3d529-112">Example</span></span>  

 <span data-ttu-id="3d529-113">Este ejemplo devuelve los pedidos en los que la cantidad de pedido es superior a 2 e inferior a 6.</span><span class="sxs-lookup"><span data-stu-id="3d529-113">This example returns the orders where the order quantity is greater than 2 and less than 6.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where2)]  
 [!code-vb[DP LINQ to DataSet Examples#Where2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where2)]
  
### <a name="example"></a><span data-ttu-id="3d529-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3d529-114">Example</span></span>  

 <span data-ttu-id="3d529-115">Este ejemplo devuelve todos los productos de color rojo.</span><span class="sxs-lookup"><span data-stu-id="3d529-115">This example returns all red colored products.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where3)]  
 [!code-vb[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where3)]
  
### <a name="example"></a><span data-ttu-id="3d529-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3d529-116">Example</span></span>  

 <span data-ttu-id="3d529-117">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Where%2A> para buscar pedidos efectuados con posterioridad al 1 de diciembre de 2002 y, a continuación, se utiliza el método <xref:System.Data.DataRow.GetChildRows%2A> para obtener los detalles de cada pedido.</span><span class="sxs-lookup"><span data-stu-id="3d529-117">This example uses the <xref:System.Linq.Enumerable.Where%2A> method to find orders that were made after December 1, 2002 and then uses the <xref:System.Data.DataRow.GetChildRows%2A> method to get the details for each order.</span></span>  
  
 [!code-csharp[DP LINQ to DataSetExamples#WhereDrillDown](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#wheredrilldown)]
 [!code-vb[DP LINQ to DataSet Examples#WhereDrillDown](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#wheredrilldown)]  
  
## <a name="see-also"></a><span data-ttu-id="3d529-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d529-118">See also</span></span>

- [<span data-ttu-id="3d529-119">Cargar datos en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="3d529-119">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="3d529-120">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="3d529-120">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="3d529-121">Información general sobre operadores de consulta estándar (C#)</span><span class="sxs-lookup"><span data-stu-id="3d529-121">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="3d529-122">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3d529-122">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
