---
title: 'Ejemplos de sintaxis de expresiones de consulta: Restricción (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1daf42c2-c9f4-4cda-b291-7641b9c6d3fe
ms.openlocfilehash: 6ec4eac6c0fb2d044e429e88d50c619aa38de4b2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149198"
---
# <a name="query-expression-syntax-examples-restriction-linq-to-dataset"></a><span data-ttu-id="9cd8f-102">Ejemplos de sintaxis de expresiones de consulta: Restricción (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="9cd8f-102">Query Expression Syntax Examples: Restriction (LINQ to DataSet)</span></span>
<span data-ttu-id="9cd8f-103">Los ejemplos de este tema muestran cómo utilizar el método <xref:System.Linq.Enumerable.Where%2A> para consultar <xref:System.Data.DataSet> utilizando sintaxis de expresión de consultas.</span><span class="sxs-lookup"><span data-stu-id="9cd8f-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Where%2A> method to query a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="9cd8f-104">El `FillDataSet` método utilizado en estos ejemplos se especifica en Carga de [datos en un conjunto de datos](loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="9cd8f-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="9cd8f-105">Los ejemplos de este tema utilizan las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="9cd8f-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="9cd8f-106">Los ejemplos de este `using` / `Imports` tema utilizan las siguientes instrucciones:</span><span class="sxs-lookup"><span data-stu-id="9cd8f-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
[!code-csharp[DP LINQ to DataSetExamples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
  
 <span data-ttu-id="9cd8f-107">Para obtener más información, vea [Cómo: crear un proyecto LINQ to DataSet en Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="9cd8f-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="where"></a><span data-ttu-id="9cd8f-108">Where</span><span class="sxs-lookup"><span data-stu-id="9cd8f-108">Where</span></span>  
  
### <a name="example"></a><span data-ttu-id="9cd8f-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9cd8f-109">Example</span></span>  
 <span data-ttu-id="9cd8f-110">Este ejemplo devuelve todos los pedidos en línea.</span><span class="sxs-lookup"><span data-stu-id="9cd8f-110">This example returns all online orders.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where1)]  
 [!code-vb[DP LINQ to DataSet Examples#Where1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where1)]
  
### <a name="example"></a><span data-ttu-id="9cd8f-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9cd8f-111">Example</span></span>  
 <span data-ttu-id="9cd8f-112">Este ejemplo devuelve los pedidos en los que la cantidad de pedido es superior a 2 e inferior a 6.</span><span class="sxs-lookup"><span data-stu-id="9cd8f-112">This example returns the orders where the order quantity is greater than 2 and less than 6.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where2)]  
 [!code-vb[DP LINQ to DataSet Examples#Where2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where2)]
  
### <a name="example"></a><span data-ttu-id="9cd8f-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9cd8f-113">Example</span></span>  
 <span data-ttu-id="9cd8f-114">Este ejemplo devuelve todos los productos de color rojo.</span><span class="sxs-lookup"><span data-stu-id="9cd8f-114">This example returns all red colored products.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where3)]  
 [!code-vb[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where3)]
  
### <a name="example"></a><span data-ttu-id="9cd8f-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9cd8f-115">Example</span></span>  
 <span data-ttu-id="9cd8f-116">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Where%2A> para buscar pedidos efectuados con posterioridad al 1 de diciembre de 2002 y, a continuación, se utiliza el método <xref:System.Data.DataRow.GetChildRows%2A> para obtener los detalles de cada pedido.</span><span class="sxs-lookup"><span data-stu-id="9cd8f-116">This example uses the <xref:System.Linq.Enumerable.Where%2A> method to find orders that were made after December 1, 2002 and then uses the <xref:System.Data.DataRow.GetChildRows%2A> method to get the details for each order.</span></span>  
  
 [!code-csharp[DP LINQ to DataSetExamples#WhereDrillDown](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#wheredrilldown)]
 [!code-vb[DP LINQ to DataSet Examples#WhereDrillDown](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#wheredrilldown)]  
  
## <a name="see-also"></a><span data-ttu-id="9cd8f-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9cd8f-117">See also</span></span>

- [<span data-ttu-id="9cd8f-118">Carga de datos en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="9cd8f-118">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="9cd8f-119">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="9cd8f-119">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="9cd8f-120">Información general sobre operadores de consulta estándar (C#)</span><span class="sxs-lookup"><span data-stu-id="9cd8f-120">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="9cd8f-121">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9cd8f-121">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
