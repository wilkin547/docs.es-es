---
title: 'Ejemplos de sintaxis de consulta basada en métodos: operadores de conjuntos (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fa93af15-28af-4b5e-846b-897308410edb
ms.openlocfilehash: 2c95125182a352d3cd2b0b4c51ffac3f74fff5a7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32764819"
---
# <a name="method-based-query-syntax-examples-set-operators-linq-to-dataset"></a><span data-ttu-id="e64b1-102">Ejemplos de sintaxis de consulta basada en métodos: operadores de conjuntos (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="e64b1-102">Method-Based Query Syntax Examples: Set Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="e64b1-103">Los ejemplos de este tema muestran cómo usar el <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A>, y <xref:System.Linq.Enumerable.Union%2A> operadores para realizar operaciones de comparación basadas en valores en conjuntos de filas de datos.[ Cargar datos en un conjunto de datos](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md) vea [comparar objetos DataRow](../../../../docs/framework/data/adonet/comparing-datarows-linq-to-dataset.md) para obtener más información sobre <xref:System.Data.DataRowComparer>.</span><span class="sxs-lookup"><span data-stu-id="e64b1-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A>, and <xref:System.Linq.Enumerable.Union%2A> operators to perform value-based comparison operations on sets of data rows.[Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md) See [Comparing DataRows](../../../../docs/framework/data/adonet/comparing-datarows-linq-to-dataset.md) for more information on <xref:System.Data.DataRowComparer>.</span></span>  
  
 <span data-ttu-id="e64b1-104">El `FillDataSet` método que se usa en estos ejemplos se especifica en [cargar datos en un conjunto de datos](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="e64b1-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="e64b1-105">Los ejemplos de este tema utilizan las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="e64b1-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="e64b1-106">Los ejemplos de este tema usan los siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="e64b1-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="e64b1-107">Para obtener más información, consulte [Cómo: crear un LINQ to DataSet proyecto en Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="e64b1-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="distinct"></a><span data-ttu-id="e64b1-108">Distinct</span><span class="sxs-lookup"><span data-stu-id="e64b1-108">Distinct</span></span>  
  
### <a name="example"></a><span data-ttu-id="e64b1-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e64b1-109">Example</span></span>  
 <span data-ttu-id="e64b1-110">Este ejemplo usa el método <xref:System.Linq.Enumerable.Distinct%2A> para quitar elementos duplicados de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="e64b1-110">This example uses the <xref:System.Linq.Enumerable.Distinct%2A> method to remove duplicate elements in a sequence.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#distinctrows)]
 [!code-vb[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#distinctrows)]  
  
## <a name="except"></a><span data-ttu-id="e64b1-111">Except</span><span class="sxs-lookup"><span data-stu-id="e64b1-111">Except</span></span>  
  
### <a name="example"></a><span data-ttu-id="e64b1-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e64b1-112">Example</span></span>  
 <span data-ttu-id="e64b1-113">Este ejemplo usa el método <xref:System.Linq.Enumerable.Except%2A> para devolver contactos que aparecen en la primera tabla pero no en la segunda.</span><span class="sxs-lookup"><span data-stu-id="e64b1-113">This example uses the <xref:System.Linq.Enumerable.Except%2A> method to return contacts that appear in the first table but not in the second.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#except2)]
 [!code-vb[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#except2)]  
  
## <a name="intersect"></a><span data-ttu-id="e64b1-114">Formar intersección</span><span class="sxs-lookup"><span data-stu-id="e64b1-114">Intersect</span></span>  
  
### <a name="example"></a><span data-ttu-id="e64b1-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e64b1-115">Example</span></span>  
 <span data-ttu-id="e64b1-116">Este ejemplo usa el método <xref:System.Linq.Enumerable.Intersect%2A> para devolver contactos que aparecen en ambas tablas.</span><span class="sxs-lookup"><span data-stu-id="e64b1-116">This example uses the <xref:System.Linq.Enumerable.Intersect%2A> method to return contacts that appear in both tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#intersect2)]
 [!code-vb[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#intersect2)]  
  
## <a name="union"></a><span data-ttu-id="e64b1-117">Unión</span><span class="sxs-lookup"><span data-stu-id="e64b1-117">Union</span></span>  
  
### <a name="example"></a><span data-ttu-id="e64b1-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e64b1-118">Example</span></span>  
 <span data-ttu-id="e64b1-119">Este ejemplo usa el método <xref:System.Linq.Enumerable.Union%2A> para devolver contactos únicos de cualquiera de las dos tablas.</span><span class="sxs-lookup"><span data-stu-id="e64b1-119">This example uses the <xref:System.Linq.Enumerable.Union%2A> method to return unique contacts from either of the two tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#union2)]
 [!code-vb[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#union2)]  
  
## <a name="see-also"></a><span data-ttu-id="e64b1-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="e64b1-120">See Also</span></span>  
 [<span data-ttu-id="e64b1-121">Carga de datos en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="e64b1-121">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="e64b1-122">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="e64b1-122">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="e64b1-123">Información general sobre operadores de consulta estándar</span><span class="sxs-lookup"><span data-stu-id="e64b1-123">Standard Query Operators Overview</span></span>](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
