---
title: Ejemplos de operadores específicos de conjuntos de datos (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8fdd64af-6ad0-46cd-91c8-dbe26620eeb1
ms.openlocfilehash: 8abcab3bc2e2ee65f7b54581d9144d62cb5d5dd6
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32759990"
---
# <a name="dataset-specific-operator-examples-linq-to-dataset"></a><span data-ttu-id="443ff-102">Ejemplos de operadores específicos de conjuntos de datos (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="443ff-102">DataSet-Specific Operator Examples (LINQ to DataSet)</span></span>
<span data-ttu-id="443ff-103">Los ejemplos de este tema muestran cómo usar los métodos <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> y la clase <xref:System.Data.DataRowComparer>.</span><span class="sxs-lookup"><span data-stu-id="443ff-103">The examples in this topic demonstrate how to use the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method and the <xref:System.Data.DataRowComparer> class.</span></span>  
  
 <span data-ttu-id="443ff-104">El `FillDataSet` método que se usa en estos ejemplos se especifica en [cargar datos en un conjunto de datos](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="443ff-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="443ff-105">Los ejemplos de este tema utilizan las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="443ff-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="443ff-106">Los ejemplos de este tema usan los siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="443ff-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="443ff-107">Para obtener más información, consulte [Cómo: crear un LINQ to DataSet proyecto en Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="443ff-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="copytodatatable"></a><span data-ttu-id="443ff-108">CopyToDataTable</span><span class="sxs-lookup"><span data-stu-id="443ff-108">CopyToDataTable</span></span>  
  
### <a name="example"></a><span data-ttu-id="443ff-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="443ff-109">Example</span></span>  
 <span data-ttu-id="443ff-110">En este ejemplo se carga un <xref:System.Data.DataTable> con resultados de consulta utilizando el método <xref:System.Data.DataTableExtensions.CopyToDataTable%2A>.</span><span class="sxs-lookup"><span data-stu-id="443ff-110">This example loads a <xref:System.Data.DataTable> with query results by using the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#LoadDataTableWithQueryResults](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#loaddatatablewithqueryresults)]
 [!code-vb[DP LINQ to DataSet Examples#LoadDataTableWithQueryResults](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#loaddatatablewithqueryresults)]  
  
## <a name="datarowcomparer"></a><span data-ttu-id="443ff-111">DataRowComparer</span><span class="sxs-lookup"><span data-stu-id="443ff-111">DataRowComparer</span></span>  
  
### <a name="example"></a><span data-ttu-id="443ff-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="443ff-112">Example</span></span>  
 <span data-ttu-id="443ff-113">En este ejemplo se comparan dos filas distintas de datos utilizando <xref:System.Data.DataRowComparer>.</span><span class="sxs-lookup"><span data-stu-id="443ff-113">This example compares two different data rows by using <xref:System.Data.DataRowComparer>.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CompareDifferentDataRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#comparedifferentdatarows)]  
  
## <a name="see-also"></a><span data-ttu-id="443ff-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="443ff-114">See Also</span></span>  
 [<span data-ttu-id="443ff-115">Carga de datos en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="443ff-115">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="443ff-116">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="443ff-116">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
