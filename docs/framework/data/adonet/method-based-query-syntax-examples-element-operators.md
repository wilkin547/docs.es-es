---
title: 'Ejemplos de sintaxis de consulta basada en métodos: operadores de elementos (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: eedf2fbd-f407-4f62-bb1a-c00eb001b1dd
ms.openlocfilehash: 2a52bf4a2a4999257377c7303cb6d362136d73a5
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44135106"
---
# <a name="method-based-query-syntax-examples-element-operators-linq-to-dataset"></a><span data-ttu-id="7cdf3-102">Ejemplos de sintaxis de consulta basada en métodos: operadores de elementos (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="7cdf3-102">Method-Based Query Syntax Examples: Element Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="7cdf3-103">Los ejemplos de este tema muestran cómo usar los métodos <xref:System.Linq.Enumerable.First%2A> y <xref:System.Linq.Enumerable.ElementAt%2A> para obtener elementos <xref:System.Data.DataRow> de un <xref:System.Data.DataSet> usando la sintaxis de expresiones de consulta.</span><span class="sxs-lookup"><span data-stu-id="7cdf3-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> and <xref:System.Linq.Enumerable.ElementAt%2A> methods to get <xref:System.Data.DataRow> elements from a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="7cdf3-104">El `FillDataSet` método usado en estos ejemplos se especifica en [cargar datos en un conjunto de datos](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="7cdf3-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="7cdf3-105">Los ejemplos de este tema utilizan las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="7cdf3-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="7cdf3-106">Los ejemplos de este tema usan los siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="7cdf3-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
[!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]   
[!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]     

 <span data-ttu-id="7cdf3-107">Para obtener más información, consulte [Cómo: crear un LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="7cdf3-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="elementat"></a><span data-ttu-id="7cdf3-108">ElementAt</span><span class="sxs-lookup"><span data-stu-id="7cdf3-108">ElementAt</span></span>  
  
### <a name="example"></a><span data-ttu-id="7cdf3-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7cdf3-109">Example</span></span>  
 <span data-ttu-id="7cdf3-110">Este ejemplo usa el método <xref:System.Linq.Enumerable.ElementAt%2A> para recuperar la quinta dirección donde `PostalCode` == "M4B 1V7".</span><span class="sxs-lookup"><span data-stu-id="7cdf3-110">This example uses the <xref:System.Linq.Enumerable.ElementAt%2A> method to retrieve the fifth address where `PostalCode` == "M4B 1V7".</span></span>  
  
[!code-csharp[DP LINQ to DataSet Examples#ElementAt](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#elementat)]   
[!code-vb[DP LINQ to DataSet Examples#ElementAt](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#elementat)]     
  
## <a name="first"></a><span data-ttu-id="7cdf3-111">First</span><span class="sxs-lookup"><span data-stu-id="7cdf3-111">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="7cdf3-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7cdf3-112">Example</span></span>  
 <span data-ttu-id="7cdf3-113">Este ejemplo usar el método <xref:System.Linq.Enumerable.First%2A> para devolver el primer contacto cuyo nombre es 'Brooke'.</span><span class="sxs-lookup"><span data-stu-id="7cdf3-113">This example uses the <xref:System.Linq.Enumerable.First%2A> method to return the first contact whose first name is 'Brooke'.</span></span>  
  
[!code-csharp[DP LINQ to DataSet Examples#FirstSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#firstsimple)]   
[!code-vb[DP LINQ to DataSet Examples#FirstSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#firstsimple)] 
  
## <a name="see-also"></a><span data-ttu-id="7cdf3-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="7cdf3-114">See Also</span></span>  
 [<span data-ttu-id="7cdf3-115">Carga de datos en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="7cdf3-115">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="7cdf3-116">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="7cdf3-116">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="7cdf3-117">Información general sobre operadores de consulta estándar</span><span class="sxs-lookup"><span data-stu-id="7cdf3-117">Standard Query Operators Overview</span></span>](https://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
